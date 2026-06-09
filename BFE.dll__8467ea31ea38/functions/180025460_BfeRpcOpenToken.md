# BfeRpcOpenToken

- ea: `0x180025460`
- end: `0x180025528`
- name: `BfeRpcOpenToken`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180009aa0`
- `0x18000ad28`
- `0x180022360`
- `0x180025460`
- `0x180025530`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180025513`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180025513`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002550a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002550a`

## pseudocode

```c
__int64 __fastcall BfeRpcOpenToken(__int64 a1, __int64 a2, __int64 a3, DWORD *a4, _QWORD *a5, _QWORD *a6)
{
  __int64 v8; // rax
  RPC_STATUS v9; // edi
  __int64 v10; // rax
  HANDLE CurrentProcess; // rax
  __int64 v13; // rax
  __int64 v14; // [rsp+30h] [rbp-58h] BYREF
  _OWORD TlsValue[2]; // [rsp+38h] [rbp-50h] BYREF

  v14 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  v8 = BfeCallCreate(a1, a2, 4, 1, TlsValue);
  v9 = v8;
  if ( !v8 )
  {
    v10 = BfeDriverTokenQuery(a3, &v14);
    v9 = v10;
    if ( !v10 )
    {
      CurrentProcess = GetCurrentProcess();
      *a4 = GetProcessId(CurrentProcess);
      v13 = v14;
      *a5 = v14;
      *a6 = v13;
    }
  }
  BfeCallDestroy((__int64 *)TlsValue);
  BfeRpcRaiseExceptionIfError(v9);
  return 0;
}

```

## disassembly

```asm
0x180025460  push    rbx
0x180025462  push    rsi
0x180025463  push    rdi
0x180025464  push    r14
0x180025466  push    r15
0x180025468  sub     rsp, 60h
0x18002546c  mov     rax, cs:__security_cookie
0x180025473  xor     rax, rsp
0x180025476  mov     [rsp+88h+var_30], rax
0x18002547b  mov     r14, [rsp+88h+arg_20]
0x180025483  lea     rax, [rsp+88h+TlsValue]
0x180025488  mov     r15, [rsp+88h+arg_28]
0x180025490  xorps   xmm0, xmm0
0x180025493  mov     rsi, r9
0x180025496  mov     [rsp+88h+var_58], 0
0x18002549f  mov     r9d, 1; int
0x1800254a5  mov     [rsp+88h+lpTlsValue], rax; lpTlsValue
0x1800254aa  mov     rbx, r8
0x1800254ad  movups  [rsp+88h+TlsValue], xmm0
0x1800254b2  lea     r8d, [r9+3]; int
0x1800254b6  movups  [rsp+88h+var_40], xmm0
0x1800254bb  call    BfeCallCreate
0x1800254c0  mov     rdi, rax
0x1800254c3  test    rax, rax
0x1800254c6  jnz     short loc_1800254DD
0x1800254c8  lea     rdx, [rsp+88h+var_58]
0x1800254cd  mov     rcx, rbx
0x1800254d0  call    BfeDriverTokenQuery
0x1800254d5  mov     rdi, rax
0x1800254d8  test    rax, rax
0x1800254db  jz      short loc_18002550A
0x1800254dd  lea     rcx, [rsp+88h+TlsValue]
0x1800254e2  call    BfeCallDestroy
0x1800254e7  mov     rcx, rdi; exception
0x1800254ea  call    BfeRpcRaiseExceptionIfError
0x1800254ef  xor     eax, eax
0x1800254f1  mov     rcx, [rsp+88h+var_30]
0x1800254f6  xor     rcx, rsp; StackCookie
0x1800254f9  call    __security_check_cookie
0x1800254fe  add     rsp, 60h
0x180025502  pop     r15
0x180025504  pop     r14
0x180025506  pop     rdi
0x180025507  pop     rsi
0x180025508  pop     rbx
0x180025509  retn
0x18002550a  call    cs:__imp_GetCurrentProcess
0x180025510  mov     rcx, rax; Process
0x180025513  call    cs:__imp_GetProcessId
0x180025519  mov     [rsi], eax
0x18002551b  mov     rax, [rsp+88h+var_58]
0x180025520  mov     [r14], rax
0x180025523  mov     [r15], rax
0x180025526  jmp     short loc_1800254DD
```
