# CDPComActivityStoreReader::Initialize(char const *)

- ea: `0x18001b230`
- end: `0x18001b2cb`
- name: `?Initialize@CDPComActivityStoreReader@@UEAAJPEBD@Z`
- size: `155`
- prototype: `__int64 __fastcall(CDPComActivityStoreReader *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001b230`
- `0x180020198`
- `0x1800250a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b279`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b279`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b2b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b2b3`
- `cdp!CDPCreateActivityStoreReaderInternal` at `0x18001b299`
- `cdp!CDPCreateActivityStoreReaderInternal` at `0x18001b299`

## pseudocode

```c
__int64 __fastcall CDPComActivityStoreReader::Initialize(RTL_SRWLOCK *this, const char *a2, __int64 a3, __int64 a4)
{
  RTL_SRWLOCK *v7; // rdi
  unsigned int v8; // ebx
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF

  if ( a2 )
  {
    v7 = this + 9;
    AcquireSRWLockExclusive(this + 9);
    v9[1] = this + 7;
    v9[0] = 0;
    v8 = CDPCreateActivityStoreReaderInternal(a2, v9);
    cdp::detail::address_of<ICDPActivityStoreReader>::~address_of<ICDPActivityStoreReader>(v9);
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    return v8;
  }
  else
  {
    v10 = -2147024809;
    v11 = 45;
    Log<long &,char const (&)[33],int>((__int64)this, 0, &v10, a4, &v11);
    return v10;
  }
}

```

## disassembly

```asm
0x18001b230  mov     rax, rsp
0x18001b233  mov     [rax+8], rbx
0x18001b237  mov     [rax+20h], rsi
0x18001b23b  push    rdi
0x18001b23c  sub     rsp, 40h
0x18001b240  mov     rbx, rdx
0x18001b243  mov     rsi, rcx
0x18001b246  test    rdx, rdx
0x18001b249  jnz     short loc_18001B272
0x18001b24b  mov     dword ptr [rax+10h], 80070057h
0x18001b252  mov     dword ptr [rax+18h], 2Dh ; '-'
0x18001b259  lea     rax, [rax+18h]
0x18001b25d  mov     [rsp+48h+var_28], rax
0x18001b262  lea     r8, [rsp+48h+arg_8]
0x18001b267  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18001b26c  mov     eax, [rsp+48h+arg_8]
0x18001b270  jmp     short loc_18001B2BB
0x18001b272  lea     rdi, [rcx+48h]
0x18001b276  mov     rcx, rdi; SRWLock
0x18001b279  call    cs:__imp_AcquireSRWLockExclusive
0x18001b27f  lea     rax, [rsi+38h]
0x18001b283  mov     [rsp+48h+var_10], rax
0x18001b288  mov     [rsp+48h+var_18], 0
0x18001b291  lea     rdx, [rsp+48h+var_18]
0x18001b296  mov     rcx, rbx
0x18001b299  call    cs:__imp_CDPCreateActivityStoreReaderInternal
0x18001b29f  mov     ebx, eax
0x18001b2a1  lea     rcx, [rsp+48h+var_18]
0x18001b2a6  call    ??1?$address_of@VICDPActivityStoreReader@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityStoreReader>::~address_of<ICDPActivityStoreReader>(void)
0x18001b2ab  test    rdi, rdi
0x18001b2ae  jz      short loc_18001B2B9
0x18001b2b0  mov     rcx, rdi; SRWLock
0x18001b2b3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b2b9  mov     eax, ebx
0x18001b2bb  mov     rbx, [rsp+48h+arg_0]
0x18001b2c0  mov     rsi, [rsp+48h+arg_18]
0x18001b2c5  add     rsp, 40h
0x18001b2c9  pop     rdi
0x18001b2ca  retn
```
