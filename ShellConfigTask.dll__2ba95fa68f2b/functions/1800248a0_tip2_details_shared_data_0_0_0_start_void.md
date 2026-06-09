# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x1800248a0`
- end: `0x180024aba`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b7fc`
- `0x18001f1c4`
- `0x18001f604`
- `0x18001f998`
- `0x18001fd50`
- `0x180028844`
- `0x18002bc5c`
- `0x18002bf50`
- `0x18002d050`

## callees

- `0x180002590`
- `0x1800245dc`
- `0x1800248a0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024992`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024a1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024992`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024a1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800249a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024a31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800249a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a79`

## string_xrefs

- `0x18002498b`: `kernelbase.dll`
- `0x180024a13`: `kernelbase.dll`
- `0x18002499f`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r14
  __int64 v8; // r15
  unsigned int v9; // edi
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rdi
  DWORD LastError; // r15d
  FARPROC v16; // rax
  HMODULE v17; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  char v24; // [rsp+5Eh] [rbp-A2h] BYREF
  char v25; // [rsp+859h] [rbp+759h] BYREF
  int *v26; // [rsp+860h] [rbp+760h]
  char *v27; // [rsp+868h] [rbp+768h]
  char *v28; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v21 = 0;
  v26 = &v22;
  v28 = &v25;
  v22 = -2143256512;
  v23 = 0;
  v27 = &v24;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v19 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_13;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_13:
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v19,
            0,
            v5,
            v9,
            v8,
            a1 + 144);
  }
  else
  {
    *v7 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    LastError = GetLastError();
    v16 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_19;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v16;
    if ( v16 )
LABEL_19:
      ((void (__fastcall *)(__int64))v16)(v14);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v7;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x1800248a0  mov     [rsp-8+arg_10], rbx
0x1800248a5  push    rbp
0x1800248a6  push    rsi
0x1800248a7  push    rdi
0x1800248a8  push    r12
0x1800248aa  push    r13
0x1800248ac  push    r14
0x1800248ae  push    r15
0x1800248b0  lea     rbp, [rsp-790h]
0x1800248b8  sub     rsp, 890h
0x1800248bf  mov     rax, cs:__security_cookie
0x1800248c6  xor     rax, rsp
0x1800248c9  mov     [rbp+7C0h+var_40], rax
0x1800248d0  mov     r13, rdx
0x1800248d3  mov     rbx, rcx
0x1800248d6  lea     rsi, [rcx+0C0h]
0x1800248dd  mov     rcx, rsi; lpCriticalSection
0x1800248e0  call    cs:__imp_EnterCriticalSection
0x1800248e6  mov     [rsp+8C0h+pv], 0
0x1800248ef  mov     [rsp+8C0h+var_868], 0
0x1800248f4  lea     rax, [rsp+8C0h+var_867]
0x1800248f9  mov     [rbp+7C0h+var_60], rax
0x180024900  lea     rax, [rbp+7C0h+var_67]
0x180024907  mov     [rbp+7C0h+var_50], rax
0x18002490e  mov     [rsp+8C0h+var_867], 80408040h
0x180024916  mov     [rsp+8C0h+var_863], 0
0x18002491b  lea     rax, [rsp+8C0h+var_862]
0x180024920  mov     [rbp+7C0h+var_58], rax
0x180024927  test    dword ptr [rbx+40h], 800h
0x18002492e  jz      short loc_18002493D
0x180024930  test    dword ptr [rbx+14h], 8000h
0x180024937  jnz     short loc_18002493D
0x180024939  mov     al, 1
0x18002493b  jmp     short loc_18002493F
0x18002493d  xor     al, al
0x18002493f  lea     r14, [rbx+90h]
0x180024946  test    al, al
0x180024948  jz      short loc_180024962
0x18002494a  mov     r8d, 1
0x180024950  lea     rdx, [rsp+8C0h+pv]
0x180024955  mov     rcx, rbx
0x180024958  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002495d  mov     r15, rax
0x180024960  jmp     short loc_180024965
0x180024962  xor     r15d, r15d
0x180024965  mov     edi, [rbx+14h]
0x180024968  mov     r12b, [rbx+20h]
0x18002496c  mov     eax, [rbx+10h]
0x18002496f  mov     [rsp+8C0h+var_880], eax
0x180024973  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002497a  test    rax, rax
0x18002497d  jnz     short loc_1800249C8
0x18002497f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180024986  test    rax, rax
0x180024989  jnz     short loc_18002499F
0x18002498b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180024992  call    cs:__imp_GetModuleHandleW
0x180024998  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002499f  lea     rdx, aTestcreate; "TestCreate"
0x1800249a6  mov     rcx, rax; hModule
0x1800249a9  call    cs:__imp_GetProcAddress
0x1800249af  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800249b6  test    rax, rax
0x1800249b9  jnz     short loc_1800249C8
0x1800249bb  xorps   xmm0, xmm0
0x1800249be  movdqu  xmmword ptr [r14], xmm0
0x1800249c3  xor     r12d, r12d
0x1800249c6  jmp     short loc_1800249E6
0x1800249c8  mov     [rsp+8C0h+var_898], r14
0x1800249cd  mov     [rsp+8C0h+var_8A0], r15
0x1800249d2  mov     r9d, edi
0x1800249d5  mov     r8b, r12b
0x1800249d8  xor     edx, edx
0x1800249da  mov     ecx, [rsp+8C0h+var_880]
0x1800249de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249e3  mov     r12, rax
0x1800249e6  mov     rdi, [rbx+0F0h]
0x1800249ed  test    rdi, rdi
0x1800249f0  jz      short loc_180024A54
0x1800249f2  call    cs:__imp_GetLastError
0x1800249f8  mov     r15d, eax
0x1800249fb  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180024a02  test    rax, rax
0x180024a05  jnz     short loc_180024A43
0x180024a07  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180024a0e  test    rax, rax
0x180024a11  jnz     short loc_180024A27
0x180024a13  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180024a1a  call    cs:__imp_GetModuleHandleW
0x180024a20  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180024a27  lea     rdx, aTestclose; "TestClose"
0x180024a2e  mov     rcx, rax; hModule
0x180024a31  call    cs:__imp_GetProcAddress
0x180024a37  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180024a3e  test    rax, rax
0x180024a41  jz      short loc_180024A4B
0x180024a43  mov     rcx, rdi
0x180024a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a4b  mov     ecx, r15d; dwErrCode
0x180024a4e  call    cs:__imp_SetLastError
0x180024a54  mov     [rbx+0F0h], r12
0x180024a5b  mov     dword ptr [rbx+0B8h], 1
0x180024a65  movups  xmm0, xmmword ptr [r14]
0x180024a69  movdqu  xmmword ptr [r13+0], xmm0
0x180024a6f  mov     rcx, [rsp+8C0h+pv]; pv
0x180024a74  test    rcx, rcx
0x180024a77  jz      short loc_180024A7F
0x180024a79  call    cs:__imp_CoTaskMemFree
0x180024a7f  test    rsi, rsi
0x180024a82  jz      short loc_180024A8D
0x180024a84  mov     rcx, rsi; lpCriticalSection
0x180024a87  call    cs:__imp_LeaveCriticalSection
0x180024a8d  mov     rax, r13
0x180024a90  mov     rcx, [rbp+7C0h+var_40]
0x180024a97  xor     rcx, rsp; StackCookie
0x180024a9a  call    __security_check_cookie
0x180024a9f  mov     rbx, [rsp+8C0h+arg_10]
0x180024aa7  add     rsp, 890h
0x180024aae  pop     r15
0x180024ab0  pop     r14
0x180024ab2  pop     r13
0x180024ab4  pop     r12
0x180024ab6  pop     rdi
0x180024ab7  pop     rsi
0x180024ab8  pop     rbp
0x180024ab9  retn
```
