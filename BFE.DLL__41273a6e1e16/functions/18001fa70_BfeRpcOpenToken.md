# BfeRpcOpenToken

- ea: `0x18001fa70`
- end: `0x18001fb45`
- name: `BfeRpcOpenToken`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000a070`
- `0x18000b3d4`
- `0x18001fa70`
- `0x18001fb4c`
- `0x180024a5c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001fb2a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001fb2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fb1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fb1b`

## pseudocode

```c
__int64 __fastcall BfeRpcOpenToken(int a1, int a2, __int64 a3, DWORD *a4, _QWORD *a5, _QWORD *a6)
{
  __int64 v8; // rdi
  __int64 v9; // rax
  HANDLE CurrentProcess; // rax
  __int64 v12; // rax
  __int64 v13; // [rsp+30h] [rbp-58h] BYREF
  _OWORD TlsValue[2]; // [rsp+38h] [rbp-50h] BYREF

  v13 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  v8 = BfeCallCreate(a1, a2, 4, 1, TlsValue);
  if ( !v8 )
  {
    v9 = BfeDriverTokenQuery(a3, &v13);
    LODWORD(v8) = v9;
    if ( !v9 )
    {
      CurrentProcess = GetCurrentProcess();
      *a4 = GetProcessId(CurrentProcess);
      v12 = v13;
      *a5 = v13;
      *a6 = v12;
    }
  }
  BfeCallDestroy(TlsValue);
  BfeRpcRaiseExceptionIfError(v8);
  return 0;
}

```

## disassembly

```asm
0x18001fa70  push    rbx
0x18001fa72  push    rsi
0x18001fa73  push    rdi
0x18001fa74  push    r14
0x18001fa76  push    r15
0x18001fa78  sub     rsp, 60h
0x18001fa7c  mov     rax, cs:__security_cookie
0x18001fa83  xor     rax, rsp
0x18001fa86  mov     [rsp+88h+var_30], rax
0x18001fa8b  mov     r14, [rsp+88h+arg_20]
0x18001fa93  lea     rax, [rsp+88h+TlsValue]
0x18001fa98  mov     r15, [rsp+88h+arg_28]
0x18001faa0  xorps   xmm0, xmm0
0x18001faa3  mov     rsi, r9
0x18001faa6  mov     [rsp+88h+var_58], 0
0x18001faaf  mov     r9d, 1; int
0x18001fab5  mov     [rsp+88h+lpTlsValue], rax; lpTlsValue
0x18001faba  mov     rbx, r8
0x18001fabd  movups  [rsp+88h+TlsValue], xmm0
0x18001fac2  lea     r8d, [r9+3]; int
0x18001fac6  movups  [rsp+88h+var_40], xmm0
0x18001facb  call    BfeCallCreate
0x18001fad0  mov     rdi, rax
0x18001fad3  test    rax, rax
0x18001fad6  jnz     short loc_18001FAED
0x18001fad8  lea     rdx, [rsp+88h+var_58]
0x18001fadd  mov     rcx, rbx
0x18001fae0  call    BfeDriverTokenQuery
0x18001fae5  mov     rdi, rax
0x18001fae8  test    rax, rax
0x18001faeb  jz      short loc_18001FB1B
0x18001faed  lea     rcx, [rsp+88h+TlsValue]
0x18001faf2  call    BfeCallDestroy
0x18001faf7  mov     rcx, rdi; exception
0x18001fafa  call    BfeRpcRaiseExceptionIfError
0x18001faff  xor     eax, eax
0x18001fb01  mov     rcx, [rsp+88h+var_30]
0x18001fb06  xor     rcx, rsp; StackCookie
0x18001fb09  call    __security_check_cookie
0x18001fb0e  add     rsp, 60h
0x18001fb12  pop     r15
0x18001fb14  pop     r14
0x18001fb16  pop     rdi
0x18001fb17  pop     rsi
0x18001fb18  pop     rbx
0x18001fb19  retn
0x18001fb1b  call    cs:__imp_GetCurrentProcess
0x18001fb22  nop     dword ptr [rax+rax+00h]
0x18001fb27  mov     rcx, rax; Process
0x18001fb2a  call    cs:__imp_GetProcessId
0x18001fb31  nop     dword ptr [rax+rax+00h]
0x18001fb36  mov     [rsi], eax
0x18001fb38  mov     rax, [rsp+88h+var_58]
0x18001fb3d  mov     [r14], rax
0x18001fb40  mov     [r15], rax
0x18001fb43  jmp     short loc_18001FAED
```
