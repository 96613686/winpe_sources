# GetOfflineHardwareUID

- ea: `0x180060040`
- end: `0x180060352`
- name: `GetOfflineHardwareUID`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18005fc60`

## callees

- `0x180057c6c`
- `0x18005b914`
- `0x18005d690`
- `0x18005fc38`
- `0x180060040`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060083`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800602ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006032e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800602ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006032e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060115`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800601db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060115`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800601db`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180060058`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180060058`

## string_xrefs

- `0x180060051`: `clipc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetOfflineHardwareUID(_QWORD *a1)
{
  HMODULE LibraryW; // rax
  int v3; // ebx
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v6)(__int64, __int64 *, int *, SIZE_T *); // rsi
  int v7; // eax
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rdi
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // esi
  __int64 v14; // rdx
  int v15; // r9d
  _WORD *v16; // r10
  int v17; // r8d
  _WORD *i; // rdx
  int v20; // [rsp+20h] [rbp-30h]
  int v21; // [rsp+20h] [rbp-30h]
  HLOCAL v22; // [rsp+40h] [rbp-10h] BYREF
  HMODULE v23; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  SIZE_T uBytes; // [rsp+88h] [rbp+38h] BYREF
  int v26; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int8 *v27; // [rsp+98h] [rbp+48h] BYREF

  LibraryW = LoadLibraryW(L"clipc.dll");
  v23 = LibraryW;
  if ( !LibraryW )
  {
    v3 = -2147418113;
    v4 = 267;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\deviceid.cpp",
      (const char *)(unsigned int)v3,
      v20);
    goto LABEL_35;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetOfflineDeviceUniqueID");
  v6 = (__int64 (__fastcall *)(__int64, __int64 *, int *, SIZE_T *))ProcAddress;
  if ( !ProcAddress )
  {
    v3 = -2147418113;
    v4 = 280;
    goto LABEL_9;
  }
  v26 = 0;
  LODWORD(uBytes) = 0;
  v20 = 0;
  v7 = ((__int64 (__fastcall *)(__int64, __int64 *, int *, SIZE_T *))ProcAddress)(16, qword_1800D0DE0, &v26, &uBytes);
  v3 = 0;
  if ( v7 != -2147024774 )
    v3 = v7;
  if ( v3 < 0 )
  {
    v4 = 301;
    goto LABEL_9;
  }
  v8 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)uBytes);
  v9 = v8;
  v27 = v8;
  if ( !v8 )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\deviceid.cpp",
      (const char *)0x8007000ELL,
      0);
    goto LABEL_35;
  }
  v21 = (int)v8;
  v10 = v6(16, qword_1800D0DE0, &v26, &uBytes);
  v3 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 314;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\deviceid.cpp",
      (const char *)v11,
      v21);
    goto LABEL_34;
  }
  LODWORD(v27) = 0;
  if ( !(_DWORD)uBytes )
  {
    v3 = -2147024809;
    goto LABEL_32;
  }
  v3 = ULongLongToULong(2LL * (unsigned int)uBytes, (unsigned int *)&v27);
  if ( v3 < 0 )
  {
LABEL_32:
    v11 = (unsigned int)v3;
    v12 = 317;
    goto LABEL_33;
  }
  v13 = (_DWORD)v27 + 1;
  if ( (int)v27 + 1 < (unsigned int)v27 )
  {
    v3 = -2147024362;
    goto LABEL_32;
  }
  v22 = LocalAlloc(0, 2LL * v13);
  if ( !v22 )
  {
    v3 = -2147024882;
    v14 = 320;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\deviceid.cpp",
      (const char *)(unsigned int)v3,
      v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
LABEL_34:
    LocalFree(v9);
    goto LABEL_35;
  }
  LODWORD(v27) = 0;
  if ( !(_DWORD)uBytes )
    goto LABEL_29;
  v3 = ULongLongToULong(2LL * (unsigned int)uBytes, (unsigned int *)&v27);
  if ( v3 < 0 )
  {
LABEL_30:
    v14 = 322;
    goto LABEL_20;
  }
  if ( (int)v27 + 1 < (unsigned int)v27 )
  {
    v3 = -2147024362;
    goto LABEL_30;
  }
  if ( (int)v27 + 1 > v13 )
  {
LABEL_29:
    v3 = -2147024809;
    goto LABEL_30;
  }
  v17 = 1;
  for ( i = v16; v17 != v15; ++v17 )
  {
    *i = a0123456789abcd_0[(unsigned __int64)v9[v17 - 1] >> 4];
    i[1] = a0123456789abcd_0[v9[v17 - 1] & 0xF];
    i += 2;
  }
  *i = a0123456789abcd_0[(unsigned __int64)v9[v17 - 1] >> 4];
  i[1] = a0123456789abcd_0[v9[v17 - 1] & 0xF];
  i[2] = 0;
  v22 = 0;
  *a1 = v16;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  LocalFree(v9);
  v3 = 0;
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v23);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180060040  push    rbp
0x180060042  push    rbx
0x180060043  push    rsi
0x180060044  push    rdi
0x180060045  push    r14
0x180060047  mov     rbp, rsp
0x18006004a  sub     rsp, 50h
0x18006004e  mov     r14, rcx
0x180060051  lea     rcx, aClipcDll; "clipc.dll"
0x180060058  call    cs:__imp_LoadLibraryW
0x18006005f  nop     dword ptr [rax+rax+00h]
0x180060064  mov     [rbp+var_8], rax
0x180060068  test    rax, rax
0x18006006b  jnz     short loc_180060079
0x18006006d  mov     ebx, 8000FFFFh
0x180060072  mov     edx, 10Bh
0x180060077  jmp     short loc_1800600F8
0x180060079  lea     rdx, aGetofflinedevi; "GetOfflineDeviceUniqueID"
0x180060080  mov     rcx, rax; hModule
0x180060083  call    cs:__imp_GetProcAddress
0x18006008a  nop     dword ptr [rax+rax+00h]
0x18006008f  mov     rsi, rax
0x180060092  test    rax, rax
0x180060095  jnz     short loc_1800600A3
0x180060097  mov     ebx, 8000FFFFh
0x18006009c  mov     edx, 118h
0x1800600a1  jmp     short loc_1800600F8
0x1800600a3  mov     [rbp+arg_10], 0
0x1800600aa  mov     dword ptr [rbp+uBytes], 0
0x1800600b1  mov     [rsp+50h+var_20], 0
0x1800600ba  mov     [rsp+50h+var_28], 0
0x1800600c3  mov     qword ptr [rsp+50h+var_30], 0; int
0x1800600cc  lea     r9, [rbp+uBytes]
0x1800600d0  lea     r8, [rbp+arg_10]
0x1800600d4  lea     rdx, qword_1800D0DE0
0x1800600db  mov     ecx, 10h
0x1800600e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600e5  xor     ebx, ebx
0x1800600e7  cmp     eax, 8007007Ah
0x1800600ec  cmovnz  ebx, eax
0x1800600ef  test    ebx, ebx
0x1800600f1  jns     short loc_180060110
0x1800600f3  mov     edx, 12Dh; void *
0x1800600f8  mov     rcx, [rbp+28h]; this
0x1800600fc  mov     r9d, ebx; char *
0x1800600ff  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x180060106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006010b  jmp     loc_18006033B
0x180060110  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180060113  xor     ecx, ecx; uFlags
0x180060115  call    cs:__imp_LocalAlloc
0x18006011c  nop     dword ptr [rax+rax+00h]
0x180060121  mov     rdi, rax
0x180060124  mov     [rbp+arg_18], rax
0x180060128  test    rax, rax
0x18006012b  jnz     short loc_180060150
0x18006012d  mov     rcx, [rbp+28h]; this
0x180060131  mov     ebx, 8007000Eh
0x180060136  mov     r9d, ebx; char *
0x180060139  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x180060140  mov     edx, 131h; void *
0x180060145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006014a  nop
0x18006014b  jmp     loc_18006033B
0x180060150  mov     [rsp+50h+var_20], 0
0x180060159  mov     [rsp+50h+var_28], 0
0x180060162  mov     qword ptr [rsp+50h+var_30], rdi; int
0x180060167  lea     r9, [rbp+uBytes]
0x18006016b  lea     r8, [rbp+arg_10]
0x18006016f  lea     rdx, qword_1800D0DE0
0x180060176  mov     ecx, 10h
0x18006017b  mov     rax, rsi
0x18006017e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060183  mov     ebx, eax
0x180060185  test    eax, eax
0x180060187  jns     short loc_180060196
0x180060189  mov     r9d, eax
0x18006018c  mov     edx, 13Ah
0x180060191  jmp     loc_18006031A
0x180060196  mov     dword ptr [rbp+arg_18], 0
0x18006019d  mov     eax, dword ptr [rbp+uBytes]
0x1800601a0  test    eax, eax
0x1800601a2  jz      loc_18006030D
0x1800601a8  mov     ecx, eax
0x1800601aa  add     rcx, rcx; unsigned __int64
0x1800601ad  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800601b1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800601b6  mov     ebx, eax
0x1800601b8  test    eax, eax
0x1800601ba  js      loc_180060312
0x1800601c0  mov     eax, dword ptr [rbp+arg_18]
0x1800601c3  lea     esi, [rax+1]
0x1800601c6  cmp     esi, eax
0x1800601c8  jnb     short loc_1800601D4
0x1800601ca  mov     ebx, 80070216h
0x1800601cf  jmp     loc_180060312
0x1800601d4  mov     edx, esi
0x1800601d6  add     rdx, rdx; uBytes
0x1800601d9  xor     ecx, ecx; uFlags
0x1800601db  call    cs:__imp_LocalAlloc
0x1800601e2  nop     dword ptr [rax+rax+00h]
0x1800601e7  mov     r10, rax
0x1800601ea  mov     [rbp+var_10], rax
0x1800601ee  test    rax, rax
0x1800601f1  jnz     short loc_18006021E
0x1800601f3  mov     ebx, 8007000Eh
0x1800601f8  mov     edx, 140h; void *
0x1800601fd  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x180060204  mov     r9d, ebx; char *
0x180060207  mov     rcx, [rbp+28h]; this
0x18006020b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060210  lea     rcx, [rbp+var_10]
0x180060214  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060219  jmp     loc_18006032B
0x18006021e  mov     dword ptr [rbp+arg_18], 0
0x180060225  mov     r9d, dword ptr [rbp+uBytes]
0x180060229  test    r9d, r9d
0x18006022c  jz      loc_1800602FE
0x180060232  mov     ecx, r9d
0x180060235  add     rcx, rcx; unsigned __int64
0x180060238  lea     rdx, [rbp+arg_18]; unsigned int *
0x18006023c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180060241  mov     ebx, eax
0x180060243  test    eax, eax
0x180060245  js      loc_180060303
0x18006024b  mov     eax, dword ptr [rbp+arg_18]
0x18006024e  lea     ecx, [rax+1]
0x180060251  cmp     ecx, eax
0x180060253  jnb     short loc_18006025F
0x180060255  mov     ebx, 80070216h
0x18006025a  jmp     loc_180060303
0x18006025f  cmp     ecx, esi
0x180060261  ja      loc_1800602FE
0x180060267  mov     r8d, 1
0x18006026d  mov     rdx, r10
0x180060270  lea     r11, a0123456789abcd_0; "0123456789ABCDEF"
0x180060277  cmp     r9d, r8d
0x18006027a  jz      short loc_1800602AE
0x18006027c  lea     eax, [r8-1]
0x180060280  mov     ecx, eax
0x180060282  movzx   eax, byte ptr [rax+rdi]
0x180060286  shr     rax, 4
0x18006028a  movzx   eax, word ptr [r11+rax*2]
0x18006028f  mov     [rdx], ax
0x180060292  movzx   eax, byte ptr [rcx+rdi]
0x180060296  and     eax, 0Fh
0x180060299  movzx   eax, word ptr [r11+rax*2]
0x18006029e  mov     [rdx+2], ax
0x1800602a2  add     rdx, 4
0x1800602a6  inc     r8d
0x1800602a9  cmp     r8d, r9d
0x1800602ac  jnz     short loc_18006027C
0x1800602ae  lea     eax, [r8-1]
0x1800602b2  mov     ecx, eax
0x1800602b4  movzx   eax, byte ptr [rax+rdi]
0x1800602b8  shr     rax, 4
0x1800602bc  movzx   eax, word ptr [r11+rax*2]
0x1800602c1  mov     [rdx], ax
0x1800602c4  movzx   eax, byte ptr [rcx+rdi]
0x1800602c8  and     eax, 0Fh
0x1800602cb  movzx   eax, word ptr [r11+rax*2]
0x1800602d0  mov     [rdx+2], ax
0x1800602d4  xor     eax, eax
0x1800602d6  mov     [rdx+4], ax
0x1800602da  mov     [rbp+var_10], rax
0x1800602de  mov     [r14], r10
0x1800602e1  lea     rcx, [rbp+var_10]
0x1800602e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800602ea  nop
0x1800602eb  mov     rcx, rdi; hMem
0x1800602ee  call    cs:__imp_LocalFree
0x1800602f5  nop     dword ptr [rax+rax+00h]
0x1800602fa  xor     ebx, ebx
0x1800602fc  jmp     short loc_18006033B
0x1800602fe  mov     ebx, 80070057h
0x180060303  mov     edx, 142h
0x180060308  jmp     loc_1800601FD
0x18006030d  mov     ebx, 80070057h
0x180060312  mov     r9d, ebx; char *
0x180060315  mov     edx, 13Dh; void *
0x18006031a  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x180060321  mov     rcx, [rbp+28h]; this
0x180060325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006032a  nop
0x18006032b  mov     rcx, rdi; hMem
0x18006032e  call    cs:__imp_LocalFree
0x180060335  nop     dword ptr [rax+rax+00h]
0x18006033a  nop
0x18006033b  lea     rcx, [rbp+var_8]
0x18006033f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180060344  mov     eax, ebx
0x180060346  add     rsp, 50h
0x18006034a  pop     r14
0x18006034c  pop     rdi
0x18006034d  pop     rsi
0x18006034e  pop     rbx
0x18006034f  pop     rbp
0x180060350  retn
```
