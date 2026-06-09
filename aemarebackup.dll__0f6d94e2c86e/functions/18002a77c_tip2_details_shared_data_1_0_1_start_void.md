# tip2::details::shared_data<1,0,1>::start(void)

- ea: `0x18002a77c`
- end: `0x18002a984`
- name: `?start@?$shared_data@$00$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180026a18`

## callees

- `0x180004ea0`
- `0x18002a4ec`
- `0x18002a77c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a8fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a8fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a85b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a8e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a85b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a8e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a918`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8bc`
- `ole32!CoTaskMemFree` at `0x18002a943`
- `ole32!CoTaskMemFree` at `0x18002a943`

## string_xrefs

- `0x18002a854`: `kernelbase.dll`
- `0x18002a8dd`: `kernelbase.dll`
- `0x18002a868`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,1>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  _OWORD *v7; // r12
  __int64 v8; // rsi
  unsigned int v9; // r15d
  char v10; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r13
  __int64 v14; // rsi
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
  v7 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v8 = tip2::details::shared_data<1,0,1>::serialize_data(a1, &pv, 1, v6);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v19 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_9;
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
LABEL_9:
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
      goto LABEL_15;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v16;
    if ( v16 )
LABEL_15:
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
0x18002a77c  mov     [rsp-8+arg_10], rbx
0x18002a781  push    rbp
0x18002a782  push    rsi
0x18002a783  push    rdi
0x18002a784  push    r12
0x18002a786  push    r13
0x18002a788  push    r14
0x18002a78a  push    r15
0x18002a78c  lea     rbp, [rsp-790h]
0x18002a794  sub     rsp, 890h
0x18002a79b  mov     rax, cs:__security_cookie
0x18002a7a2  xor     rax, rsp
0x18002a7a5  mov     [rbp+7C0h+var_40], rax
0x18002a7ac  mov     r14, rdx
0x18002a7af  mov     rbx, rcx
0x18002a7b2  lea     rdi, [rcx+0C0h]
0x18002a7b9  mov     rcx, rdi; lpCriticalSection
0x18002a7bc  call    cs:__imp_EnterCriticalSection
0x18002a7c2  mov     [rsp+8C0h+pv], 0
0x18002a7cb  mov     [rsp+8C0h+var_868], 0
0x18002a7d0  lea     rax, [rsp+8C0h+var_867]
0x18002a7d5  mov     [rbp+7C0h+var_60], rax
0x18002a7dc  lea     rax, [rbp+7C0h+var_67]
0x18002a7e3  mov     [rbp+7C0h+var_50], rax
0x18002a7ea  mov     [rsp+8C0h+var_867], 80408040h
0x18002a7f2  mov     [rsp+8C0h+var_863], 0
0x18002a7f7  lea     rax, [rsp+8C0h+var_862]
0x18002a7fc  mov     [rbp+7C0h+var_58], rax
0x18002a803  lea     r12, [rbx+90h]
0x18002a80a  test    dword ptr [rbx+40h], 800h
0x18002a811  jz      short loc_18002A82B
0x18002a813  mov     r8d, 1
0x18002a819  lea     rdx, [rsp+8C0h+pv]
0x18002a81e  mov     rcx, rbx
0x18002a821  call    ?serialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002a826  mov     rsi, rax
0x18002a829  jmp     short loc_18002A82D
0x18002a82b  xor     esi, esi
0x18002a82d  mov     r15d, [rbx+14h]
0x18002a831  mov     r13b, [rbx+20h]
0x18002a835  mov     eax, [rbx+10h]
0x18002a838  mov     [rsp+8C0h+var_880], eax
0x18002a83c  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002a843  test    rax, rax
0x18002a846  jnz     short loc_18002A892
0x18002a848  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002a84f  test    rax, rax
0x18002a852  jnz     short loc_18002A868
0x18002a854  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002a85b  call    cs:__imp_GetModuleHandleW
0x18002a861  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002a868  lea     rdx, aTestcreate; "TestCreate"
0x18002a86f  mov     rcx, rax; hModule
0x18002a872  call    cs:__imp_GetProcAddress
0x18002a878  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002a87f  test    rax, rax
0x18002a882  jnz     short loc_18002A892
0x18002a884  xorps   xmm0, xmm0
0x18002a887  movdqu  xmmword ptr [r12], xmm0
0x18002a88d  xor     r13d, r13d
0x18002a890  jmp     short loc_18002A8B0
0x18002a892  mov     [rsp+8C0h+var_898], r12
0x18002a897  mov     [rsp+8C0h+var_8A0], rsi
0x18002a89c  mov     r9d, r15d
0x18002a89f  mov     r8b, r13b
0x18002a8a2  xor     edx, edx
0x18002a8a4  mov     ecx, [rsp+8C0h+var_880]
0x18002a8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8ad  mov     r13, rax
0x18002a8b0  mov     rsi, [rbx+0F0h]
0x18002a8b7  test    rsi, rsi
0x18002a8ba  jz      short loc_18002A91E
0x18002a8bc  call    cs:__imp_GetLastError
0x18002a8c2  mov     r15d, eax
0x18002a8c5  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18002a8cc  test    rax, rax
0x18002a8cf  jnz     short loc_18002A90D
0x18002a8d1  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002a8d8  test    rax, rax
0x18002a8db  jnz     short loc_18002A8F1
0x18002a8dd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002a8e4  call    cs:__imp_GetModuleHandleW
0x18002a8ea  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002a8f1  lea     rdx, aTestclose; "TestClose"
0x18002a8f8  mov     rcx, rax; hModule
0x18002a8fb  call    cs:__imp_GetProcAddress
0x18002a901  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18002a908  test    rax, rax
0x18002a90b  jz      short loc_18002A915
0x18002a90d  mov     rcx, rsi
0x18002a910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a915  mov     ecx, r15d; dwErrCode
0x18002a918  call    cs:__imp_SetLastError
0x18002a91e  mov     [rbx+0F0h], r13
0x18002a925  mov     dword ptr [rbx+0B8h], 1
0x18002a92f  movups  xmm0, xmmword ptr [r12]
0x18002a934  movdqu  xmmword ptr [r14], xmm0
0x18002a939  mov     rcx, [rsp+8C0h+pv]; pv
0x18002a93e  test    rcx, rcx
0x18002a941  jz      short loc_18002A949
0x18002a943  call    cs:__imp_CoTaskMemFree
0x18002a949  test    rdi, rdi
0x18002a94c  jz      short loc_18002A957
0x18002a94e  mov     rcx, rdi; lpCriticalSection
0x18002a951  call    cs:__imp_LeaveCriticalSection
0x18002a957  mov     rax, r14
0x18002a95a  mov     rcx, [rbp+7C0h+var_40]
0x18002a961  xor     rcx, rsp; StackCookie
0x18002a964  call    __security_check_cookie
0x18002a969  mov     rbx, [rsp+8C0h+arg_10]
0x18002a971  add     rsp, 890h
0x18002a978  pop     r15
0x18002a97a  pop     r14
0x18002a97c  pop     r13
0x18002a97e  pop     r12
0x18002a980  pop     rdi
0x18002a981  pop     rsi
0x18002a982  pop     rbp
0x18002a983  retn
```
