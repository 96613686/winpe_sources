# Broker::BrokerBase::GetInstance(_GUID const &)

- ea: `0x1800058e0`
- end: `0x1800059ef`
- name: `?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z`
- size: `271`
- prototype: `_QWORD *__fastcall(_QWORD *, const void *)`
- caller_count: `25`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800051b0`
- `0x1800052a0`
- `0x180005390`
- `0x180005580`
- `0x180009460`
- `0x180009bb0`
- `0x180009ee0`
- `0x18000b190`
- `0x18000b2b0`
- `0x18000c420`
- `0x18000eb80`
- `0x18000fd10`
- `0x1800109f0`
- `0x180012300`
- `0x1800124b0`
- `0x18001364c`
- `0x180015340`
- `0x180016b50`
- `0x180016c50`
- `0x180016cf0`
- `0x180016d80`
- `0x180016e80`
- `0x180016fb0`
- `0x180017090`
- `0x18001ab8c`

## callees

- `0x1800058e0`
- `0x18001659e`
- `0x1800165da`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800059a0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800059a0`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005907`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005907`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Broker::BrokerBase::GetInstance(_QWORD *a1, const void *a2)
{
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v6; // rbx
  char v7; // cl
  __int64 *v8; // rax
  __int64 v9; // rax
  void **pExceptionObject; // [rsp+38h] [rbp-60h] BYREF
  __int128 v12; // [rsp+40h] [rbp-58h]
  int v13; // [rsp+50h] [rbp-48h]

  RtlAcquireSRWLockShared(&Broker::g_BrokersLock);
  v4 = Broker::g_Brokers;
  v5 = *(_QWORD *)(Broker::g_Brokers + 8);
  DWORD1(v12) = 0;
  v6 = Broker::g_Brokers;
  if ( !*(_BYTE *)(v5 + 25) )
  {
    do
    {
      if ( memcmp_0((const void *)(v5 + 32), a2, 0x10u) < 0 )
      {
        v7 = 1;
      }
      else
      {
        v7 = 0;
        v6 = v5;
      }
      v8 = (__int64 *)(v5 + 16);
      if ( !v7 )
        v8 = (__int64 *)v5;
      v5 = *v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *(_BYTE *)(v6 + 25) || memcmp_0(a2, (const void *)(v6 + 32), 0x10u) < 0 )
    v6 = v4;
  if ( v6 == v4 )
  {
    v12 = 0;
    v13 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  *a1 = 0;
  a1[1] = 0;
  v9 = *(_QWORD *)(v6 + 56);
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  *a1 = *(_QWORD *)(v6 + 48);
  a1[1] = *(_QWORD *)(v6 + 56);
  RtlReleaseSRWLockShared(&Broker::g_BrokersLock);
  return a1;
}

```

## disassembly

```asm
0x1800058e0  push    rbx
0x1800058e2  push    rbp
0x1800058e3  push    rsi
0x1800058e4  push    rdi
0x1800058e5  push    r12
0x1800058e7  push    r14
0x1800058e9  push    r15
0x1800058eb  sub     rsp, 60h
0x1800058ef  mov     r14, rdx
0x1800058f2  mov     rdi, rcx
0x1800058f5  xor     r15d, r15d
0x1800058f8  lea     r12, ?g_BrokersLock@Broker@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Broker::g_BrokersLock
0x1800058ff  mov     [rsp+98h+var_70], r12
0x180005904  mov     rcx, r12
0x180005907  call    cs:__imp_RtlAcquireSRWLockShared
0x18000590d  mov     [rsp+98h+var_68], 1
0x180005912  mov     rbp, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x180005919  mov     rsi, [rbp+8]
0x18000591d  xor     eax, eax
0x18000591f  mov     [rsp+98h+var_54], eax
0x180005923  mov     rbx, rbp
0x180005926  cmp     [rsi+19h], al
0x180005929  jnz     short loc_180005959
0x18000592b  lea     rcx, [rsi+20h]; Buf1
0x18000592f  mov     r8d, 10h; Size
0x180005935  mov     rdx, r14; Buf2
0x180005938  call    memcmp_0
0x18000593d  test    eax, eax
0x18000593f  js      short loc_1800059B8
0x180005941  xor     cl, cl
0x180005943  mov     rbx, rsi
0x180005946  lea     rax, [rsi+10h]
0x18000594a  test    cl, cl
0x18000594c  cmovz   rax, rsi
0x180005950  mov     rsi, [rax]
0x180005953  cmp     byte ptr [rsi+19h], 0
0x180005957  jz      short loc_18000592B
0x180005959  cmp     byte ptr [rbx+19h], 0
0x18000595d  jnz     short loc_1800059BC
0x18000595f  lea     rdx, [rbx+20h]; Buf2
0x180005963  mov     r8d, 10h; Size
0x180005969  mov     rcx, r14; Buf1
0x18000596c  call    memcmp_0
0x180005971  test    eax, eax
0x180005973  js      short loc_1800059BC
0x180005975  cmp     rbx, rbp
0x180005978  jz      short loc_1800059C1
0x18000597a  mov     [rdi], r15
0x18000597d  mov     [rdi+8], r15
0x180005981  mov     rax, [rbx+38h]
0x180005985  test    rax, rax
0x180005988  jz      short loc_18000598E
0x18000598a  lock inc dword ptr [rax+8]
0x18000598e  mov     rax, [rbx+30h]
0x180005992  mov     [rdi], rax
0x180005995  mov     rax, [rbx+38h]
0x180005999  mov     [rdi+8], rax
0x18000599d  mov     rcx, r12
0x1800059a0  call    cs:__imp_RtlReleaseSRWLockShared
0x1800059a6  mov     rax, rdi
0x1800059a9  add     rsp, 60h
0x1800059ad  pop     r15
0x1800059af  pop     r14
0x1800059b1  pop     r12
0x1800059b3  pop     rdi
0x1800059b4  pop     rsi
0x1800059b5  pop     rbp
0x1800059b6  pop     rbx
0x1800059b7  retn
0x1800059b8  mov     cl, 1
0x1800059ba  jmp     short loc_180005946
0x1800059bc  mov     rbx, rbp
0x1800059bf  jmp     short loc_180005975
0x1800059c1  xorps   xmm0, xmm0
0x1800059c4  movups  xmmword ptr [rsp+40h], xmm0
0x1800059c9  mov     [rsp+98h+var_48], 3
0x1800059d1  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800059d8  mov     [rsp+98h+pExceptionObject], rax
0x1800059dd  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800059e4  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800059e9  call    _CxxThrowException_0
```
