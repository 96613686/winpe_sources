# tip2::details::shared_data<0,0,1>::start(void)

- ea: `0x1800cc570`
- end: `0x1800cc78a`
- name: `?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c7cec`

## callees

- `0x180002bf0`
- `0x1800cc2e0`
- `0x1800cc570`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc679`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc701`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc679`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc701`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cc662`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cc6ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cc662`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cc6ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc757`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc757`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc5b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc5b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cc71e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cc71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc6c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cc749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cc749`

## string_xrefs

- `0x1800cc65b`: `kernelbase.dll`
- `0x1800cc6e3`: `kernelbase.dll`
- `0x1800cc66f`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,1>::start(__int64 a1, _OWORD *a2)
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
    v8 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
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
0x1800cc570  mov     [rsp-8+arg_10], rbx
0x1800cc575  push    rbp
0x1800cc576  push    rsi
0x1800cc577  push    rdi
0x1800cc578  push    r12
0x1800cc57a  push    r13
0x1800cc57c  push    r14
0x1800cc57e  push    r15
0x1800cc580  lea     rbp, [rsp-790h]
0x1800cc588  sub     rsp, 890h
0x1800cc58f  mov     rax, cs:__security_cookie
0x1800cc596  xor     rax, rsp
0x1800cc599  mov     [rbp+7C0h+var_40], rax
0x1800cc5a0  mov     r13, rdx
0x1800cc5a3  mov     rbx, rcx
0x1800cc5a6  lea     rsi, [rcx+0C0h]
0x1800cc5ad  mov     rcx, rsi; lpCriticalSection
0x1800cc5b0  call    cs:__imp_EnterCriticalSection
0x1800cc5b6  mov     [rsp+8C0h+pv], 0
0x1800cc5bf  mov     [rsp+8C0h+var_868], 0
0x1800cc5c4  lea     rax, [rsp+8C0h+var_867]
0x1800cc5c9  mov     [rbp+7C0h+var_60], rax
0x1800cc5d0  lea     rax, [rbp+7C0h+var_67]
0x1800cc5d7  mov     [rbp+7C0h+var_50], rax
0x1800cc5de  mov     [rsp+8C0h+var_867], 80408040h
0x1800cc5e6  mov     [rsp+8C0h+var_863], 0
0x1800cc5eb  lea     rax, [rsp+8C0h+var_862]
0x1800cc5f0  mov     [rbp+7C0h+var_58], rax
0x1800cc5f7  test    dword ptr [rbx+40h], 800h
0x1800cc5fe  jz      short loc_1800CC60D
0x1800cc600  test    dword ptr [rbx+14h], 8000h
0x1800cc607  jnz     short loc_1800CC60D
0x1800cc609  mov     al, 1
0x1800cc60b  jmp     short loc_1800CC60F
0x1800cc60d  xor     al, al
0x1800cc60f  lea     r14, [rbx+90h]
0x1800cc616  test    al, al
0x1800cc618  jz      short loc_1800CC632
0x1800cc61a  mov     r8d, 1
0x1800cc620  lea     rdx, [rsp+8C0h+pv]
0x1800cc625  mov     rcx, rbx
0x1800cc628  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800cc62d  mov     r15, rax
0x1800cc630  jmp     short loc_1800CC635
0x1800cc632  xor     r15d, r15d
0x1800cc635  mov     edi, [rbx+14h]
0x1800cc638  mov     r12b, [rbx+20h]
0x1800cc63c  mov     eax, [rbx+10h]
0x1800cc63f  mov     [rsp+8C0h+var_880], eax
0x1800cc643  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800cc64a  test    rax, rax
0x1800cc64d  jnz     short loc_1800CC698
0x1800cc64f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800cc656  test    rax, rax
0x1800cc659  jnz     short loc_1800CC66F
0x1800cc65b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800cc662  call    cs:__imp_GetModuleHandleW
0x1800cc668  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800cc66f  lea     rdx, aTestcreate; "TestCreate"
0x1800cc676  mov     rcx, rax; hModule
0x1800cc679  call    cs:__imp_GetProcAddress
0x1800cc67f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800cc686  test    rax, rax
0x1800cc689  jnz     short loc_1800CC698
0x1800cc68b  xorps   xmm0, xmm0
0x1800cc68e  movdqu  xmmword ptr [r14], xmm0
0x1800cc693  xor     r12d, r12d
0x1800cc696  jmp     short loc_1800CC6B6
0x1800cc698  mov     [rsp+8C0h+var_898], r14
0x1800cc69d  mov     [rsp+8C0h+var_8A0], r15
0x1800cc6a2  mov     r9d, edi
0x1800cc6a5  mov     r8b, r12b
0x1800cc6a8  xor     edx, edx
0x1800cc6aa  mov     ecx, [rsp+8C0h+var_880]
0x1800cc6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc6b3  mov     r12, rax
0x1800cc6b6  mov     rdi, [rbx+0F0h]
0x1800cc6bd  test    rdi, rdi
0x1800cc6c0  jz      short loc_1800CC724
0x1800cc6c2  call    cs:__imp_GetLastError
0x1800cc6c8  mov     r15d, eax
0x1800cc6cb  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800cc6d2  test    rax, rax
0x1800cc6d5  jnz     short loc_1800CC713
0x1800cc6d7  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800cc6de  test    rax, rax
0x1800cc6e1  jnz     short loc_1800CC6F7
0x1800cc6e3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800cc6ea  call    cs:__imp_GetModuleHandleW
0x1800cc6f0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800cc6f7  lea     rdx, aTestclose; "TestClose"
0x1800cc6fe  mov     rcx, rax; hModule
0x1800cc701  call    cs:__imp_GetProcAddress
0x1800cc707  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800cc70e  test    rax, rax
0x1800cc711  jz      short loc_1800CC71B
0x1800cc713  mov     rcx, rdi
0x1800cc716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc71b  mov     ecx, r15d; dwErrCode
0x1800cc71e  call    cs:__imp_SetLastError
0x1800cc724  mov     [rbx+0F0h], r12
0x1800cc72b  mov     dword ptr [rbx+0B8h], 1
0x1800cc735  movups  xmm0, xmmword ptr [r14]
0x1800cc739  movdqu  xmmword ptr [r13+0], xmm0
0x1800cc73f  mov     rcx, [rsp+8C0h+pv]; pv
0x1800cc744  test    rcx, rcx
0x1800cc747  jz      short loc_1800CC74F
0x1800cc749  call    cs:__imp_CoTaskMemFree
0x1800cc74f  test    rsi, rsi
0x1800cc752  jz      short loc_1800CC75D
0x1800cc754  mov     rcx, rsi; lpCriticalSection
0x1800cc757  call    cs:__imp_LeaveCriticalSection
0x1800cc75d  mov     rax, r13
0x1800cc760  mov     rcx, [rbp+7C0h+var_40]
0x1800cc767  xor     rcx, rsp; StackCookie
0x1800cc76a  call    __security_check_cookie
0x1800cc76f  mov     rbx, [rsp+8C0h+arg_10]
0x1800cc777  add     rsp, 890h
0x1800cc77e  pop     r15
0x1800cc780  pop     r14
0x1800cc782  pop     r13
0x1800cc784  pop     r12
0x1800cc786  pop     rdi
0x1800cc787  pop     rsi
0x1800cc788  pop     rbp
0x1800cc789  retn
```
