# CObjectArray::~CObjectArray(void)

- ea: `0x180003200`
- end: `0x18000336e`
- name: `??1CObjectArray@@QEAA@XZ`
- size: `366`
- prototype: `void __fastcall(CObjectArray *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002fa0`

## callees

- `0x180003200`
- `0x1800041d0`
- `0x180051a04`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800032b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800032e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800032b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800032e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000330c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000330c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800032c5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800032c5`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000328e`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000328e`

## string_xrefs

- `0x1800032a3`: `comctl32.dll`
- `0x1800032d9`: `comctl32.dll`

## pseudocode

```c
void __fastcall CObjectArray::~CObjectArray(CObjectArray *this)
{
  __int64 v1; // rsi
  FARPROC ProcAddress; // rax
  HMODULE Library; // rbx
  HANDLE v5; // rcx
  __int64 v6; // rcx
  ULONG_PTR Cookie; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( !v1 )
    goto LABEL_18;
  ProcAddress = (FARPROC)qword_1800701E8;
  if ( qword_1800701E8 != -1 )
    goto LABEL_16;
  Library = g_hinstCC;
  if ( !g_hinstCC )
  {
    v5 = g_hActCtx;
    Cookie = 0;
    if ( g_hActCtx != (HANDLE)qword_1800701E8 )
      goto LABEL_22;
    if ( hModule )
    {
      if ( hModule == (HMODULE)qword_1800701E8 )
      {
LABEL_9:
        g_hinstCC = 0;
        goto LABEL_13;
      }
      SHFusionInitializeFromModuleID(hModule);
      v5 = g_hActCtx;
      if ( g_hActCtx != (HANDLE)-1LL )
      {
LABEL_22:
        if ( !ActivateActCtx(v5, &Cookie) )
          goto LABEL_9;
      }
    }
    Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
    if ( Cookie )
      DeactivateActCtx(0, Cookie);
    g_hinstCC = Library;
    if ( !Library )
    {
LABEL_13:
      g_hinstCC = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
      Library = g_hinstCC;
      if ( !g_hinstCC )
      {
        qword_1800701E8 = 0;
        goto LABEL_18;
      }
    }
  }
  ProcAddress = GetProcAddress(Library, (LPCSTR)0x184);
  qword_1800701E8 = (__int64)ProcAddress;
LABEL_16:
  if ( ProcAddress )
    ((void (__fastcall *)(__int64, __int64 (__fastcall *)(struct CObjectArray::OBJECTARRAYITEM *, void *), _QWORD))ProcAddress)(
      v1,
      CObjectArray::s_DestroyObjectItem,
      0);
LABEL_18:
  CDSA_Base<unsigned short [64]>::Destroy((char *)this + 128);
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
}

```

## disassembly

```asm
0x180003200  sub     rsp, 28h
0x180003204  mov     [rsp+28h+arg_10], rbp
0x180003209  xor     ebp, ebp
0x18000320b  mov     [rsp+28h+arg_18], rsi
0x180003210  mov     rsi, [rcx+78h]
0x180003214  mov     [rsp+28h+var_8], rdi
0x180003219  mov     rdi, rcx
0x18000321c  mov     [rcx+78h], rbp
0x180003220  test    rsi, rsi
0x180003223  jz      loc_180003335
0x180003229  mov     rax, cs:qword_1800701E8
0x180003230  mov     [rsp+28h+arg_8], rbx
0x180003235  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003239  jnz     loc_180003319
0x18000323f  mov     rbx, cs:g_hinstCC
0x180003246  test    rbx, rbx
0x180003249  jnz     loc_180003304
0x18000324f  mov     rcx, cs:g_hActCtx
0x180003256  mov     [rsp+28h+Cookie], rbp
0x18000325b  cmp     rcx, rax
0x18000325e  jnz     short loc_180003289
0x180003260  mov     rcx, cs:hModule; hModule
0x180003267  test    rcx, rcx
0x18000326a  jz      short loc_1800032A1
0x18000326c  cmp     rcx, rax
0x18000326f  jz      short loc_180003298
0x180003271  mov     edx, cs:dword_180070DB8
0x180003277  call    SHFusionInitializeFromModuleID
0x18000327c  mov     rcx, cs:g_hActCtx; hActCtx
0x180003283  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003287  jz      short loc_1800032A1
0x180003289  lea     rdx, [rsp+28h+Cookie]; lpCookie
0x18000328e  call    cs:__imp_ActivateActCtx
0x180003294  test    eax, eax
0x180003296  jnz     short loc_1800032A1
0x180003298  mov     cs:g_hinstCC, rbp
0x18000329f  jmp     short loc_1800032D7
0x1800032a1  xor     edx, edx; hFile
0x1800032a3  lea     rcx, LibFileName; "comctl32.dll"
0x1800032aa  mov     r8d, 4000h; dwFlags
0x1800032b0  call    cs:__imp_LoadLibraryExW
0x1800032b6  mov     rdx, [rsp+28h+Cookie]; ulCookie
0x1800032bb  mov     rbx, rax
0x1800032be  test    rdx, rdx
0x1800032c1  jz      short loc_1800032CB
0x1800032c3  xor     ecx, ecx; dwFlags
0x1800032c5  call    cs:__imp_DeactivateActCtx
0x1800032cb  mov     cs:g_hinstCC, rbx
0x1800032d2  test    rbx, rbx
0x1800032d5  jnz     short loc_180003304
0x1800032d7  xor     edx, edx; hFile
0x1800032d9  lea     rcx, LibFileName; "comctl32.dll"
0x1800032e0  mov     r8d, 4000h; dwFlags
0x1800032e6  call    cs:__imp_LoadLibraryExW
0x1800032ec  mov     cs:g_hinstCC, rax
0x1800032f3  mov     rbx, rax
0x1800032f6  test    rax, rax
0x1800032f9  jnz     short loc_180003304
0x1800032fb  mov     cs:qword_1800701E8, rbp
0x180003302  jmp     short loc_180003330
0x180003304  mov     edx, 184h; lpProcName
0x180003309  mov     rcx, rbx; hModule
0x18000330c  call    cs:__imp_GetProcAddress
0x180003312  mov     cs:qword_1800701E8, rax
0x180003319  test    rax, rax
0x18000331c  jz      short loc_180003330
0x18000331e  xor     r8d, r8d
0x180003321  lea     rdx, ?s_DestroyObjectItem@CObjectArray@@CAHPEAUOBJECTARRAYITEM@1@PEAX@Z; CObjectArray::s_DestroyObjectItem(CObjectArray::OBJECTARRAYITEM *,void *)
0x180003328  mov     rcx, rsi
0x18000332b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003330  mov     rbx, [rsp+28h+arg_8]
0x180003335  lea     rcx, [rdi+80h]
0x18000333c  call    ?Destroy@?$CDSA_Base@$$BY0EA@G@@QEAAHXZ; CDSA_Base<ushort [64]>::Destroy(void)
0x180003341  mov     rcx, [rdi+70h]
0x180003345  mov     rdi, [rsp+28h+var_8]
0x18000334a  mov     rsi, [rsp+28h+arg_18]
0x18000334f  mov     rbp, [rsp+28h+arg_10]
0x180003354  test    rcx, rcx
0x180003357  jz      short loc_180003369
0x180003359  mov     rax, [rcx]
0x18000335c  mov     rax, [rax+18h]
0x180003360  add     rsp, 28h
0x180003364  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003369  add     rsp, 28h
0x18000336d  retn
```
