# AppReadiness::Service::FindUserBySessionIdAndUserContext(ulong,unsigned __int64)

- ea: `0x180027068`
- end: `0x180027152`
- name: `?FindUserBySessionIdAndUserContext@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@K_K@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025d64`
- `0x180026c10`
- `0x180047f34`

## callees

- `0x180002958`
- `0x18000b464`
- `0x180027068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027132`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002709b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002709b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800270e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800270e1`

## pseudocode

```c
_QWORD *__fastcall AppReadiness::Service::FindUserBySessionIdAndUserContext(
        RTL_SRWLOCK *a1,
        _QWORD *a2,
        int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v4; // rsi
  char *Ptr; // rbx
  char *v10; // r15
  __int64 v11; // rcx
  DWORD ReturnLength; // [rsp+60h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+10h] BYREF

  v4 = a1 + 19;
  *a2 = 0;
  AcquireSRWLockShared(a1 + 19);
  Ptr = (char *)a1[20].Ptr;
  v10 = (char *)a1[21].Ptr;
  while ( Ptr != v10 )
  {
    v11 = *(_QWORD *)Ptr;
    TokenInformation = 0;
    ReturnLength = 4;
    if ( GetTokenInformation(*(HANDLE *)(v11 + 112), TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( TokenInformation == a3 && ReturnLength == 4 && *(_QWORD *)(*(_QWORD *)Ptr + 96LL) == a4 )
        break;
    }
    Ptr += 8;
  }
  if ( Ptr != a1[21].Ptr )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(Ptr);
    *a2 = *(_QWORD *)Ptr;
  }
  if ( v4 )
    ReleaseSRWLockShared(v4);
  return a2;
}

```

## disassembly

```asm
0x180027068  mov     [rsp+arg_10], rbx
0x18002706d  mov     [rsp+arg_18], rbp
0x180027072  push    rsi
0x180027073  push    rdi
0x180027074  push    r12
0x180027076  push    r14
0x180027078  push    r15
0x18002707a  sub     rsp, 30h
0x18002707e  lea     rsi, [rcx+98h]
0x180027085  mov     qword ptr [rdx], 0
0x18002708c  mov     rbp, rcx
0x18002708f  mov     r12, r9
0x180027092  mov     rcx, rsi; SRWLock
0x180027095  mov     r14d, r8d
0x180027098  mov     rdi, rdx
0x18002709b  call    cs:__imp_AcquireSRWLockShared
0x1800270a1  mov     rbx, [rbp+0A0h]
0x1800270a8  mov     r15, [rbp+0A8h]
0x1800270af  jmp     short loc_180027106
0x1800270b1  mov     rcx, [rbx]
0x1800270b4  lea     rax, [rsp+58h+arg_0]
0x1800270b9  mov     r9d, 4; TokenInformationLength
0x1800270bf  mov     [rsp+58h+TokenInformation], 0
0x1800270c7  mov     [rsp+58h+arg_0], 4
0x1800270cf  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800270d4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800270d9  mov     rcx, [rcx+70h]; TokenHandle
0x1800270dd  lea     edx, [r9+8]; TokenInformationClass
0x1800270e1  call    cs:__imp_GetTokenInformation
0x1800270e7  test    eax, eax
0x1800270e9  jz      short loc_180027102
0x1800270eb  cmp     [rsp+58h+TokenInformation], r14d
0x1800270f0  jnz     short loc_180027102
0x1800270f2  cmp     [rsp+58h+arg_0], 4
0x1800270f7  jnz     short loc_180027102
0x1800270f9  mov     rax, [rbx]
0x1800270fc  cmp     [rax+60h], r12
0x180027100  jz      short loc_18002710B
0x180027102  add     rbx, 8
0x180027106  cmp     rbx, r15
0x180027109  jnz     short loc_1800270B1
0x18002710b  cmp     rbx, [rbp+0A8h]
0x180027112  jz      short loc_18002712A
0x180027114  mov     rcx, rdi
0x180027117  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002711c  mov     rcx, rbx
0x18002711f  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x180027124  mov     rax, [rbx]
0x180027127  mov     [rdi], rax
0x18002712a  test    rsi, rsi
0x18002712d  jz      short loc_180027138
0x18002712f  mov     rcx, rsi; SRWLock
0x180027132  call    cs:__imp_ReleaseSRWLockShared
0x180027138  mov     rbx, [rsp+58h+arg_10]
0x18002713d  mov     rax, rdi
0x180027140  mov     rbp, [rsp+58h+arg_18]
0x180027145  add     rsp, 30h
0x180027149  pop     r15
0x18002714b  pop     r14
0x18002714d  pop     r12
0x18002714f  pop     rdi
0x180027150  pop     rsi
0x180027151  retn
```
