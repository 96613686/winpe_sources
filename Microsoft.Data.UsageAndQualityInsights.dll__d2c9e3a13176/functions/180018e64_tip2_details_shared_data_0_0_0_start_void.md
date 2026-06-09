# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180018e64`
- end: `0x18001907e`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012998`
- `0x180012aa4`
- `0x18001ac5c`
- `0x18001c060`
- `0x18002b6a8`
- `0x1800366f4`
- `0x180046cf0`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`
- `0x1800f4eb4`

## callees

- `0x1800033d0`
- `0x180018ba0`
- `0x180018e64`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018fde`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018fde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018ff5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001904b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001904b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ea4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001903d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001903d`

## string_xrefs

- `0x180018f4f`: `kernelbase.dll`
- `0x180018fd7`: `kernelbase.dll`
- `0x180018f63`: `TestCreate`

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
0x180018e64  mov     [rsp-8+arg_10], rbx
0x180018e69  push    rbp
0x180018e6a  push    rsi
0x180018e6b  push    rdi
0x180018e6c  push    r12
0x180018e6e  push    r13
0x180018e70  push    r14
0x180018e72  push    r15
0x180018e74  lea     rbp, [rsp-790h]
0x180018e7c  sub     rsp, 890h
0x180018e83  mov     rax, cs:__security_cookie
0x180018e8a  xor     rax, rsp
0x180018e8d  mov     [rbp+7C0h+var_40], rax
0x180018e94  mov     r13, rdx
0x180018e97  mov     rbx, rcx
0x180018e9a  lea     rsi, [rcx+0C0h]
0x180018ea1  mov     rcx, rsi; lpCriticalSection
0x180018ea4  call    cs:__imp_EnterCriticalSection
0x180018eaa  mov     [rsp+8C0h+pv], 0
0x180018eb3  mov     [rsp+8C0h+var_868], 0
0x180018eb8  lea     rax, [rsp+8C0h+var_867]
0x180018ebd  mov     [rbp+7C0h+var_60], rax
0x180018ec4  lea     rax, [rbp+7C0h+var_67]
0x180018ecb  mov     [rbp+7C0h+var_50], rax
0x180018ed2  mov     [rsp+8C0h+var_867], 80408040h
0x180018eda  mov     [rsp+8C0h+var_863], 0
0x180018edf  lea     rax, [rsp+8C0h+var_862]
0x180018ee4  mov     [rbp+7C0h+var_58], rax
0x180018eeb  test    dword ptr [rbx+40h], 800h
0x180018ef2  jz      short loc_180018F01
0x180018ef4  test    dword ptr [rbx+14h], 8000h
0x180018efb  jnz     short loc_180018F01
0x180018efd  mov     al, 1
0x180018eff  jmp     short loc_180018F03
0x180018f01  xor     al, al
0x180018f03  lea     r14, [rbx+90h]
0x180018f0a  test    al, al
0x180018f0c  jz      short loc_180018F26
0x180018f0e  mov     r8d, 1
0x180018f14  lea     rdx, [rsp+8C0h+pv]
0x180018f19  mov     rcx, rbx
0x180018f1c  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180018f21  mov     r15, rax
0x180018f24  jmp     short loc_180018F29
0x180018f26  xor     r15d, r15d
0x180018f29  mov     edi, [rbx+14h]
0x180018f2c  mov     r12b, [rbx+20h]
0x180018f30  mov     eax, [rbx+10h]
0x180018f33  mov     [rsp+8C0h+var_880], eax
0x180018f37  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180018f3e  test    rax, rax
0x180018f41  jnz     short loc_180018F8C
0x180018f43  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018f4a  test    rax, rax
0x180018f4d  jnz     short loc_180018F63
0x180018f4f  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180018f56  call    cs:__imp_GetModuleHandleW
0x180018f5c  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018f63  lea     rdx, aTestcreate; "TestCreate"
0x180018f6a  mov     rcx, rax; hModule
0x180018f6d  call    cs:__imp_GetProcAddress
0x180018f73  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180018f7a  test    rax, rax
0x180018f7d  jnz     short loc_180018F8C
0x180018f7f  xorps   xmm0, xmm0
0x180018f82  movdqu  xmmword ptr [r14], xmm0
0x180018f87  xor     r12d, r12d
0x180018f8a  jmp     short loc_180018FAA
0x180018f8c  mov     [rsp+8C0h+var_898], r14
0x180018f91  mov     [rsp+8C0h+var_8A0], r15
0x180018f96  mov     r9d, edi
0x180018f99  mov     r8b, r12b
0x180018f9c  xor     edx, edx
0x180018f9e  mov     ecx, [rsp+8C0h+var_880]
0x180018fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fa7  mov     r12, rax
0x180018faa  mov     rdi, [rbx+0F0h]
0x180018fb1  test    rdi, rdi
0x180018fb4  jz      short loc_180019018
0x180018fb6  call    cs:__imp_GetLastError
0x180018fbc  mov     r15d, eax
0x180018fbf  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018fc6  test    rax, rax
0x180018fc9  jnz     short loc_180019007
0x180018fcb  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018fd2  test    rax, rax
0x180018fd5  jnz     short loc_180018FEB
0x180018fd7  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180018fde  call    cs:__imp_GetModuleHandleW
0x180018fe4  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018feb  lea     rdx, aTestclose; "TestClose"
0x180018ff2  mov     rcx, rax; hModule
0x180018ff5  call    cs:__imp_GetProcAddress
0x180018ffb  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180019002  test    rax, rax
0x180019005  jz      short loc_18001900F
0x180019007  mov     rcx, rdi
0x18001900a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001900f  mov     ecx, r15d; dwErrCode
0x180019012  call    cs:__imp_SetLastError
0x180019018  mov     [rbx+0F0h], r12
0x18001901f  mov     dword ptr [rbx+0B8h], 1
0x180019029  movups  xmm0, xmmword ptr [r14]
0x18001902d  movdqu  xmmword ptr [r13+0], xmm0
0x180019033  mov     rcx, [rsp+8C0h+pv]; pv
0x180019038  test    rcx, rcx
0x18001903b  jz      short loc_180019043
0x18001903d  call    cs:__imp_CoTaskMemFree
0x180019043  test    rsi, rsi
0x180019046  jz      short loc_180019051
0x180019048  mov     rcx, rsi; lpCriticalSection
0x18001904b  call    cs:__imp_LeaveCriticalSection
0x180019051  mov     rax, r13
0x180019054  mov     rcx, [rbp+7C0h+var_40]
0x18001905b  xor     rcx, rsp; StackCookie
0x18001905e  call    __security_check_cookie
0x180019063  mov     rbx, [rsp+8C0h+arg_10]
0x18001906b  add     rsp, 890h
0x180019072  pop     r15
0x180019074  pop     r14
0x180019076  pop     r13
0x180019078  pop     r12
0x18001907a  pop     rdi
0x18001907b  pop     rsi
0x18001907c  pop     rbp
0x18001907d  retn
```
