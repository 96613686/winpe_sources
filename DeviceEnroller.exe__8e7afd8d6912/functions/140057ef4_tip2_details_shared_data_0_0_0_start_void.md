# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x140057ef4`
- end: `0x14005810e`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140052fc0`

## callees

- `0x1400042f0`
- `0x140057c30`
- `0x140057ef4`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140057ffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058085`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140057ffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058085`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140057fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005806e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140057fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005806e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140057f34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140057f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400580db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400580db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058046`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400580a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400580a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400580cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400580cd`

## string_xrefs

- `0x140057fdf`: `kernelbase.dll`
- `0x140058067`: `kernelbase.dll`
- `0x140057ff3`: `TestCreate`

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
0x140057ef4  mov     [rsp-8+arg_10], rbx
0x140057ef9  push    rbp
0x140057efa  push    rsi
0x140057efb  push    rdi
0x140057efc  push    r12
0x140057efe  push    r13
0x140057f00  push    r14
0x140057f02  push    r15
0x140057f04  lea     rbp, [rsp-790h]
0x140057f0c  sub     rsp, 890h
0x140057f13  mov     rax, cs:__security_cookie
0x140057f1a  xor     rax, rsp
0x140057f1d  mov     [rbp+7C0h+var_40], rax
0x140057f24  mov     r13, rdx
0x140057f27  mov     rbx, rcx
0x140057f2a  lea     rsi, [rcx+0C0h]
0x140057f31  mov     rcx, rsi; lpCriticalSection
0x140057f34  call    cs:__imp_EnterCriticalSection
0x140057f3a  mov     [rsp+8C0h+pv], 0
0x140057f43  mov     [rsp+8C0h+var_868], 0
0x140057f48  lea     rax, [rsp+8C0h+var_867]
0x140057f4d  mov     [rbp+7C0h+var_60], rax
0x140057f54  lea     rax, [rbp+7C0h+var_67]
0x140057f5b  mov     [rbp+7C0h+var_50], rax
0x140057f62  mov     [rsp+8C0h+var_867], 80408040h
0x140057f6a  mov     [rsp+8C0h+var_863], 0
0x140057f6f  lea     rax, [rsp+8C0h+var_862]
0x140057f74  mov     [rbp+7C0h+var_58], rax
0x140057f7b  test    dword ptr [rbx+40h], 800h
0x140057f82  jz      short loc_140057F91
0x140057f84  test    dword ptr [rbx+14h], 8000h
0x140057f8b  jnz     short loc_140057F91
0x140057f8d  mov     al, 1
0x140057f8f  jmp     short loc_140057F93
0x140057f91  xor     al, al
0x140057f93  lea     r14, [rbx+90h]
0x140057f9a  test    al, al
0x140057f9c  jz      short loc_140057FB6
0x140057f9e  mov     r8d, 1
0x140057fa4  lea     rdx, [rsp+8C0h+pv]
0x140057fa9  mov     rcx, rbx
0x140057fac  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140057fb1  mov     r15, rax
0x140057fb4  jmp     short loc_140057FB9
0x140057fb6  xor     r15d, r15d
0x140057fb9  mov     edi, [rbx+14h]
0x140057fbc  mov     r12b, [rbx+20h]
0x140057fc0  mov     eax, [rbx+10h]
0x140057fc3  mov     [rsp+8C0h+var_880], eax
0x140057fc7  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x140057fce  test    rax, rax
0x140057fd1  jnz     short loc_14005801C
0x140057fd3  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140057fda  test    rax, rax
0x140057fdd  jnz     short loc_140057FF3
0x140057fdf  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140057fe6  call    cs:__imp_GetModuleHandleW
0x140057fec  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140057ff3  lea     rdx, aTestcreate; "TestCreate"
0x140057ffa  mov     rcx, rax; hModule
0x140057ffd  call    cs:__imp_GetProcAddress
0x140058003  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14005800a  test    rax, rax
0x14005800d  jnz     short loc_14005801C
0x14005800f  xorps   xmm0, xmm0
0x140058012  movdqu  xmmword ptr [r14], xmm0
0x140058017  xor     r12d, r12d
0x14005801a  jmp     short loc_14005803A
0x14005801c  mov     [rsp+8C0h+var_898], r14
0x140058021  mov     [rsp+8C0h+var_8A0], r15
0x140058026  mov     r9d, edi
0x140058029  mov     r8b, r12b
0x14005802c  xor     edx, edx
0x14005802e  mov     ecx, [rsp+8C0h+var_880]
0x140058032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058037  mov     r12, rax
0x14005803a  mov     rdi, [rbx+0F0h]
0x140058041  test    rdi, rdi
0x140058044  jz      short loc_1400580A8
0x140058046  call    cs:__imp_GetLastError
0x14005804c  mov     r15d, eax
0x14005804f  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x140058056  test    rax, rax
0x140058059  jnz     short loc_140058097
0x14005805b  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140058062  test    rax, rax
0x140058065  jnz     short loc_14005807B
0x140058067  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14005806e  call    cs:__imp_GetModuleHandleW
0x140058074  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14005807b  lea     rdx, aTestclose; "TestClose"
0x140058082  mov     rcx, rax; hModule
0x140058085  call    cs:__imp_GetProcAddress
0x14005808b  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x140058092  test    rax, rax
0x140058095  jz      short loc_14005809F
0x140058097  mov     rcx, rdi
0x14005809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005809f  mov     ecx, r15d; dwErrCode
0x1400580a2  call    cs:__imp_SetLastError
0x1400580a8  mov     [rbx+0F0h], r12
0x1400580af  mov     dword ptr [rbx+0B8h], 1
0x1400580b9  movups  xmm0, xmmword ptr [r14]
0x1400580bd  movdqu  xmmword ptr [r13+0], xmm0
0x1400580c3  mov     rcx, [rsp+8C0h+pv]; pv
0x1400580c8  test    rcx, rcx
0x1400580cb  jz      short loc_1400580D3
0x1400580cd  call    cs:__imp_CoTaskMemFree
0x1400580d3  test    rsi, rsi
0x1400580d6  jz      short loc_1400580E1
0x1400580d8  mov     rcx, rsi; lpCriticalSection
0x1400580db  call    cs:__imp_LeaveCriticalSection
0x1400580e1  mov     rax, r13
0x1400580e4  mov     rcx, [rbp+7C0h+var_40]
0x1400580eb  xor     rcx, rsp; StackCookie
0x1400580ee  call    __security_check_cookie
0x1400580f3  mov     rbx, [rsp+8C0h+arg_10]
0x1400580fb  add     rsp, 890h
0x140058102  pop     r15
0x140058104  pop     r14
0x140058106  pop     r13
0x140058108  pop     r12
0x14005810a  pop     rdi
0x14005810b  pop     rsi
0x14005810c  pop     rbp
0x14005810d  retn
```
