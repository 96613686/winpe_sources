# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180027f20`
- end: `0x18002813a`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800221d4`
- `0x18002252c`
- `0x18007e778`
- `0x180082ad4`
- `0x180082bd8`

## callees

- `0x1800060a0`
- `0x180027c5c`
- `0x180027f20`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028029`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800280b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028029`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800280b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028012`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002809a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028012`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002809a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028107`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280f9`

## string_xrefs

- `0x18002800b`: `kernelbase.dll`
- `0x180028093`: `kernelbase.dll`
- `0x18002801f`: `TestCreate`

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
0x180027f20  mov     [rsp-8+arg_10], rbx
0x180027f25  push    rbp
0x180027f26  push    rsi
0x180027f27  push    rdi
0x180027f28  push    r12
0x180027f2a  push    r13
0x180027f2c  push    r14
0x180027f2e  push    r15
0x180027f30  lea     rbp, [rsp-790h]
0x180027f38  sub     rsp, 890h
0x180027f3f  mov     rax, cs:__security_cookie
0x180027f46  xor     rax, rsp
0x180027f49  mov     [rbp+7C0h+var_40], rax
0x180027f50  mov     r13, rdx
0x180027f53  mov     rbx, rcx
0x180027f56  lea     rsi, [rcx+0C0h]
0x180027f5d  mov     rcx, rsi; lpCriticalSection
0x180027f60  call    cs:__imp_EnterCriticalSection
0x180027f66  mov     [rsp+8C0h+pv], 0
0x180027f6f  mov     [rsp+8C0h+var_868], 0
0x180027f74  lea     rax, [rsp+8C0h+var_867]
0x180027f79  mov     [rbp+7C0h+var_60], rax
0x180027f80  lea     rax, [rbp+7C0h+var_67]
0x180027f87  mov     [rbp+7C0h+var_50], rax
0x180027f8e  mov     [rsp+8C0h+var_867], 80408040h
0x180027f96  mov     [rsp+8C0h+var_863], 0
0x180027f9b  lea     rax, [rsp+8C0h+var_862]
0x180027fa0  mov     [rbp+7C0h+var_58], rax
0x180027fa7  test    dword ptr [rbx+40h], 800h
0x180027fae  jz      short loc_180027FBD
0x180027fb0  test    dword ptr [rbx+14h], 8000h
0x180027fb7  jnz     short loc_180027FBD
0x180027fb9  mov     al, 1
0x180027fbb  jmp     short loc_180027FBF
0x180027fbd  xor     al, al
0x180027fbf  lea     r14, [rbx+90h]
0x180027fc6  test    al, al
0x180027fc8  jz      short loc_180027FE2
0x180027fca  mov     r8d, 1
0x180027fd0  lea     rdx, [rsp+8C0h+pv]
0x180027fd5  mov     rcx, rbx
0x180027fd8  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180027fdd  mov     r15, rax
0x180027fe0  jmp     short loc_180027FE5
0x180027fe2  xor     r15d, r15d
0x180027fe5  mov     edi, [rbx+14h]
0x180027fe8  mov     r12b, [rbx+20h]
0x180027fec  mov     eax, [rbx+10h]
0x180027fef  mov     [rsp+8C0h+var_880], eax
0x180027ff3  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180027ffa  test    rax, rax
0x180027ffd  jnz     short loc_180028048
0x180027fff  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180028006  test    rax, rax
0x180028009  jnz     short loc_18002801F
0x18002800b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180028012  call    cs:__imp_GetModuleHandleW
0x180028018  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002801f  lea     rdx, aTestcreate; "TestCreate"
0x180028026  mov     rcx, rax; hModule
0x180028029  call    cs:__imp_GetProcAddress
0x18002802f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180028036  test    rax, rax
0x180028039  jnz     short loc_180028048
0x18002803b  xorps   xmm0, xmm0
0x18002803e  movdqu  xmmword ptr [r14], xmm0
0x180028043  xor     r12d, r12d
0x180028046  jmp     short loc_180028066
0x180028048  mov     [rsp+8C0h+var_898], r14
0x18002804d  mov     [rsp+8C0h+var_8A0], r15
0x180028052  mov     r9d, edi
0x180028055  mov     r8b, r12b
0x180028058  xor     edx, edx
0x18002805a  mov     ecx, [rsp+8C0h+var_880]
0x18002805e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028063  mov     r12, rax
0x180028066  mov     rdi, [rbx+0F0h]
0x18002806d  test    rdi, rdi
0x180028070  jz      short loc_1800280D4
0x180028072  call    cs:__imp_GetLastError
0x180028078  mov     r15d, eax
0x18002807b  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180028082  test    rax, rax
0x180028085  jnz     short loc_1800280C3
0x180028087  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002808e  test    rax, rax
0x180028091  jnz     short loc_1800280A7
0x180028093  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002809a  call    cs:__imp_GetModuleHandleW
0x1800280a0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800280a7  lea     rdx, aTestclose; "TestClose"
0x1800280ae  mov     rcx, rax; hModule
0x1800280b1  call    cs:__imp_GetProcAddress
0x1800280b7  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800280be  test    rax, rax
0x1800280c1  jz      short loc_1800280CB
0x1800280c3  mov     rcx, rdi
0x1800280c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280cb  mov     ecx, r15d; dwErrCode
0x1800280ce  call    cs:__imp_SetLastError
0x1800280d4  mov     [rbx+0F0h], r12
0x1800280db  mov     dword ptr [rbx+0B8h], 1
0x1800280e5  movups  xmm0, xmmword ptr [r14]
0x1800280e9  movdqu  xmmword ptr [r13+0], xmm0
0x1800280ef  mov     rcx, [rsp+8C0h+pv]; pv
0x1800280f4  test    rcx, rcx
0x1800280f7  jz      short loc_1800280FF
0x1800280f9  call    cs:__imp_CoTaskMemFree
0x1800280ff  test    rsi, rsi
0x180028102  jz      short loc_18002810D
0x180028104  mov     rcx, rsi; lpCriticalSection
0x180028107  call    cs:__imp_LeaveCriticalSection
0x18002810d  mov     rax, r13
0x180028110  mov     rcx, [rbp+7C0h+var_40]
0x180028117  xor     rcx, rsp; StackCookie
0x18002811a  call    __security_check_cookie
0x18002811f  mov     rbx, [rsp+8C0h+arg_10]
0x180028127  add     rsp, 890h
0x18002812e  pop     r15
0x180028130  pop     r14
0x180028132  pop     r13
0x180028134  pop     r12
0x180028136  pop     rdi
0x180028137  pop     rsi
0x180028138  pop     rbp
0x180028139  retn
```
