# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180053db0`
- end: `0x180053f5a`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f8ec`
- `0x18002f924`
- `0x18002fa8c`
- `0x18002fb70`
- `0x18002fc30`

## callees

- `0x180004ca0`
- `0x180053bb4`
- `0x180053db0`
- `0x180054cd8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180053ebc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180053ebc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053f27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053f27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053df0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f19`

## string_xrefs

- `0x180053eb5`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // edx
  int v6; // r8d
  char v7; // al
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // r12
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+39h] [rbp-C7h] BYREF
  char v18; // [rsp+3Dh] [rbp-C3h]
  char v19; // [rsp+3Eh] [rbp-C2h] BYREF
  char v20; // [rsp+839h] [rbp+739h] BYREF
  int *v21; // [rsp+840h] [rbp+740h]
  char *v22; // [rsp+848h] [rbp+748h]
  char *v23; // [rsp+850h] [rbp+750h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v16 = 0;
  v21 = &v17;
  v23 = &v20;
  v17 = -2143256512;
  v18 = 0;
  v22 = &v19;
  if ( (*(_DWORD *)(a1 + 64) & 0x800) == 0 || (v7 = 1, (*(_DWORD *)(a1 + 20) & 0x8000) != 0) )
    v7 = 0;
  if ( v7 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  LOBYTE(v6) = *(_BYTE *)(a1 + 32);
  v9 = TestCreate(*(_DWORD *)(a1 + 16), v5, v6, *(_DWORD *)(a1 + 20), v8, a1 + 144);
  v10 = *(_QWORD *)(a1 + 240);
  if ( v10 )
  {
    LastError = GetLastError();
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_12;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_12:
      ((void (__fastcall *)(__int64))ProcAddress)(v10);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v9;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *(_OWORD *)(a1 + 144);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x180053db0  mov     [rsp-8+arg_10], rbx
0x180053db5  push    rbp
0x180053db6  push    rsi
0x180053db7  push    rdi
0x180053db8  push    r12
0x180053dba  push    r13
0x180053dbc  push    r14
0x180053dbe  push    r15
0x180053dc0  lea     rbp, [rsp-770h]
0x180053dc8  sub     rsp, 870h
0x180053dcf  mov     rax, cs:__security_cookie
0x180053dd6  xor     rax, rsp
0x180053dd9  mov     [rbp+7A0h+var_40], rax
0x180053de0  mov     r15, rdx
0x180053de3  mov     rdi, rcx
0x180053de6  lea     rsi, [rcx+0C0h]
0x180053ded  mov     rcx, rsi; lpCriticalSection
0x180053df0  call    cs:__imp_EnterCriticalSection
0x180053df6  xor     ecx, ecx
0x180053df8  mov     [rsp+8A0h+pv], rcx
0x180053dfd  mov     [rsp+8A0h+var_868], cl
0x180053e01  lea     rax, [rsp+8A0h+var_867]
0x180053e06  mov     [rbp+7A0h+var_60], rax
0x180053e0d  lea     rax, [rbp+7A0h+var_67]
0x180053e14  mov     [rbp+7A0h+var_50], rax
0x180053e1b  mov     [rsp+8A0h+var_867], 80408040h
0x180053e23  mov     [rsp+8A0h+var_863], cl
0x180053e27  lea     rax, [rsp+8A0h+var_862]
0x180053e2c  mov     [rbp+7A0h+var_58], rax
0x180053e33  test    dword ptr [rdi+40h], 800h
0x180053e3a  jz      short loc_180053E47
0x180053e3c  test    dword ptr [rdi+14h], 8000h
0x180053e43  mov     al, 1
0x180053e45  jz      short loc_180053E49
0x180053e47  mov     al, cl
0x180053e49  lea     r14, [rdi+90h]
0x180053e50  test    al, al
0x180053e52  jz      short loc_180053E69
0x180053e54  mov     r8d, 1
0x180053e5a  lea     rdx, [rsp+8A0h+pv]
0x180053e5f  mov     rcx, rdi
0x180053e62  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180053e67  jmp     short loc_180053E6C
0x180053e69  mov     rax, rcx
0x180053e6c  mov     [rsp+8A0h+var_878], r14
0x180053e71  mov     [rsp+8A0h+var_880], rax
0x180053e76  mov     r9d, [rdi+14h]
0x180053e7a  mov     r8b, [rdi+20h]
0x180053e7e  mov     ecx, [rdi+10h]
0x180053e81  call    TestCreate
0x180053e86  mov     r13, rax
0x180053e89  mov     r12, [rdi+0F0h]
0x180053e90  test    r12, r12
0x180053e93  jz      short loc_180053EF5
0x180053e95  call    cs:__imp_GetLastError
0x180053e9b  mov     ebx, eax
0x180053e9d  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180053ea4  test    rax, rax
0x180053ea7  jnz     short loc_180053EE5
0x180053ea9  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180053eb0  test    rax, rax
0x180053eb3  jnz     short loc_180053EC9
0x180053eb5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180053ebc  call    cs:__imp_GetModuleHandleW
0x180053ec2  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180053ec9  lea     rdx, aTestclose; "TestClose"
0x180053ed0  mov     rcx, rax; hModule
0x180053ed3  call    cs:__imp_GetProcAddress
0x180053ed9  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180053ee0  test    rax, rax
0x180053ee3  jz      short loc_180053EED
0x180053ee5  mov     rcx, r12
0x180053ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eed  mov     ecx, ebx; dwErrCode
0x180053eef  call    cs:__imp_SetLastError
0x180053ef5  mov     [rdi+0F0h], r13
0x180053efc  mov     dword ptr [rdi+0B8h], 1
0x180053f06  movups  xmm0, xmmword ptr [r14]
0x180053f0a  movdqu  xmmword ptr [r15], xmm0
0x180053f0f  mov     rcx, [rsp+8A0h+pv]; pv
0x180053f14  test    rcx, rcx
0x180053f17  jz      short loc_180053F1F
0x180053f19  call    cs:__imp_CoTaskMemFree
0x180053f1f  test    rsi, rsi
0x180053f22  jz      short loc_180053F2D
0x180053f24  mov     rcx, rsi; lpCriticalSection
0x180053f27  call    cs:__imp_LeaveCriticalSection
0x180053f2d  mov     rax, r15
0x180053f30  mov     rcx, [rbp+7A0h+var_40]
0x180053f37  xor     rcx, rsp; StackCookie
0x180053f3a  call    __security_check_cookie
0x180053f3f  mov     rbx, [rsp+8A0h+arg_10]
0x180053f47  add     rsp, 870h
0x180053f4e  pop     r15
0x180053f50  pop     r14
0x180053f52  pop     r13
0x180053f54  pop     r12
0x180053f56  pop     rdi
0x180053f57  pop     rsi
0x180053f58  pop     rbp
0x180053f59  retn
```
