# ComlessCoCreate(_GUID const &,_GUID const &,ulong,void * *,ushort const *,_COMLESS_CO_DLL_DATA &)

- ea: `0x18009406c`
- end: `0x18009416c`
- name: `?ComlessCoCreate@@YAJAEBU_GUID@@0KPEAPEAXPEBGAEAU_COMLESS_CO_DLL_DATA@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned int, void **, LPCWSTR lpLibFileName, struct _COMLESS_CO_DLL_DATA *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180093910`
- `0x180093ce0`
- `0x180093eb0`

## callees

- `0x18009406c`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180094154`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180094154`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094138`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094138`

## string_xrefs

- `0x18009414a`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall ComlessCoCreate(
        const struct _GUID *a1,
        const struct _GUID *a2,
        __int64 a3,
        void **a4,
        LPCWSTR lpLibFileName,
        struct _COMLESS_CO_DLL_DATA *a6)
{
  struct _COMLESS_CO_DLL_DATA *v6; // rdi
  __int64 (__fastcall *v10)(const struct _GUID *, GUID *, __int64 *); // rax
  unsigned int v11; // ebx
  int v12; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v6 = a6;
  *a4 = 0;
  v16 = 0;
  if ( !*((_QWORD *)v6 + 1) )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
    *(_QWORD *)v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)v6 + 1, (__int64)ProcAddress);
    }
  }
  v10 = (__int64 (__fastcall *)(const struct _GUID *, GUID *, __int64 *))*((_QWORD *)v6 + 1);
  v11 = -2147467259;
  if ( v10 )
  {
    v12 = v10(a1, &IID_IClassFactory, &v16);
    v11 = v12;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v16 + 24LL))(
                  v16,
                  0,
                  a2,
                  a4),
          v11 = v12,
          v12 < 0) )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v12);
    }
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v11;
}

```

## disassembly

```asm
0x18009406c  mov     [rsp+arg_0], rbx
0x180094071  mov     [rsp+arg_8], rbp
0x180094076  push    rsi
0x180094077  push    rdi
0x180094078  push    r14
0x18009407a  sub     rsp, 30h
0x18009407e  mov     rdi, [rsp+48h+arg_28]
0x180094083  mov     rsi, r9
0x180094086  mov     qword ptr [r9], 0
0x18009408d  mov     r14, rdx
0x180094090  mov     rbp, rcx
0x180094093  mov     [rsp+48h+arg_18], 0
0x18009409c  cmp     qword ptr [rdi+8], 0
0x1800940a1  jz      loc_18009412B
0x1800940a7  mov     rax, [rdi+8]
0x1800940ab  mov     ebx, 80004005h
0x1800940b0  test    rax, rax
0x1800940b3  jz      short loc_1800940EE
0x1800940b5  lea     r8, [rsp+48h+arg_18]
0x1800940ba  mov     rcx, rbp
0x1800940bd  lea     rdx, IID_IClassFactory
0x1800940c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940c9  mov     ebx, eax
0x1800940cb  test    eax, eax
0x1800940cd  js      short loc_180094119
0x1800940cf  mov     rcx, [rsp+48h+arg_18]
0x1800940d4  mov     r9, rsi
0x1800940d7  mov     r8, r14
0x1800940da  xor     edx, edx
0x1800940dc  mov     rax, [rcx]
0x1800940df  mov     rax, [rax+18h]
0x1800940e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940e8  mov     ebx, eax
0x1800940ea  test    eax, eax
0x1800940ec  js      short loc_180094119
0x1800940ee  mov     rcx, [rsp+48h+arg_18]
0x1800940f3  test    rcx, rcx
0x1800940f6  jz      short loc_180094104
0x1800940f8  mov     rdx, [rcx]
0x1800940fb  mov     rax, [rdx+10h]
0x1800940ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094104  mov     rbp, [rsp+48h+arg_8]
0x180094109  mov     eax, ebx
0x18009410b  mov     rbx, [rsp+48h+arg_0]
0x180094110  add     rsp, 30h
0x180094114  pop     r14
0x180094116  pop     rdi
0x180094117  pop     rsi
0x180094118  retn
0x180094119  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180094120  jz      short loc_1800940EE
0x180094122  mov     ecx, eax; int
0x180094124  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180094129  jmp     short loc_1800940EE
0x18009412b  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x180094130  xor     edx, edx; hFile
0x180094132  mov     r8d, 800h; dwFlags
0x180094138  call    cs:__imp_LoadLibraryExW
0x18009413e  mov     [rdi], rax
0x180094141  test    rax, rax
0x180094144  jz      loc_1800940A7
0x18009414a  lea     rdx, ProcName; "DllGetClassObject"
0x180094151  mov     rcx, rax; hModule
0x180094154  call    cs:__imp_GetProcAddress
0x18009415a  test    rax, rax
0x18009415d  jz      loc_1800940A7
0x180094163  xchg    rax, [rdi+8]
0x180094167  jmp     loc_1800940A7
```
