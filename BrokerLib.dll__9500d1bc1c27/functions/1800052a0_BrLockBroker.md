# BrLockBroker

- ea: `0x1800052a0`
- end: `0x18000537b`
- name: `BrLockBroker`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052a0`
- `0x1800058e0`
- `0x180009e94`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180005329`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005329`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800052ce`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800052ce`

## pseudocode

```c
__int64 __fastcall BrLockBroker(const void *a1, int a2)
{
  volatile signed __int32 *v3; // rbx
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  volatile signed __int32 *v6; // [rsp+30h] [rbp-18h]

  if ( a1 )
  {
    Broker::BrokerBase::GetInstance(&v5, a1);
    if ( a2 )
      RtlAcquireSRWLockShared(v5);
    else
      RtlAcquireSRWLockExclusive(v5);
    v3 = v6;
    if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
    return 0;
  }
  else
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, 87);
    return 87;
  }
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp+arg_8], rbx
0x1800052a5  mov     [rsp+arg_10], rsi
0x1800052aa  push    rdi
0x1800052ab  sub     rsp, 40h
0x1800052af  mov     ebx, edx
0x1800052b1  xor     esi, esi
0x1800052b3  test    rcx, rcx
0x1800052b6  jz      short loc_180005332
0x1800052b8  mov     rdx, rcx
0x1800052bb  lea     rcx, [rsp+48h+var_20]
0x1800052c0  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800052c5  mov     rcx, [rsp+48h+var_20]
0x1800052ca  test    ebx, ebx
0x1800052cc  jnz     short loc_180005329
0x1800052ce  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800052d4  mov     rbx, [rsp+48h+var_18]
0x1800052d9  test    rbx, rbx
0x1800052dc  jz      short loc_180005317
0x1800052de  mov     edi, 0FFFFFFFFh
0x1800052e3  mov     eax, edi
0x1800052e5  lock xadd [rbx+8], eax
0x1800052ea  cmp     eax, 1
0x1800052ed  jnz     short loc_180005317
0x1800052ef  mov     rax, [rbx]
0x1800052f2  mov     rcx, rbx
0x1800052f5  mov     rax, [rax]
0x1800052f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fd  lock xadd [rbx+0Ch], edi
0x180005302  cmp     edi, 1
0x180005305  jnz     short loc_180005317
0x180005307  mov     rax, [rbx]
0x18000530a  mov     rcx, rbx
0x18000530d  mov     rax, [rax+8]
0x180005311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005316  nop
0x180005317  mov     eax, esi
0x180005319  mov     rbx, [rsp+48h+arg_8]
0x18000531e  mov     rsi, [rsp+48h+arg_10]
0x180005323  add     rsp, 40h
0x180005327  pop     rdi
0x180005328  retn
0x180005329  call    cs:__imp_RtlAcquireSRWLockShared
0x18000532f  nop
0x180005330  jmp     short loc_1800052D4
0x180005332  mov     ebx, 57h ; 'W'
0x180005337  jmp     short loc_180005349
0x180005339  jmp     short loc_180005345
0x18000533b  mov     ebx, [rsp+48h+arg_0]
0x18000533f  test    ebx, ebx
0x180005341  jz      short loc_180005377
0x180005343  jmp     short loc_180005349
0x180005345  mov     ebx, [rsp+48h+arg_0]
0x180005349  mov     rcx, cs:WPP_GLOBAL_Control
0x180005350  test    dword ptr [rcx+1Ch], 800h
0x180005357  jz      short loc_180005377
0x180005359  cmp     byte ptr [rcx+19h], 2
0x18000535d  jb      short loc_180005377
0x18000535f  mov     edx, 0Fh
0x180005364  mov     r9d, ebx
0x180005367  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000536e  mov     rcx, [rcx+10h]
0x180005372  call    WPP_SF_d
0x180005377  mov     eax, ebx
0x180005379  jmp     short loc_180005319
```
