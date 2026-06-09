# ATL::CAtlMap<ulong,Base::Stopwatch,ATL::CElementTraits<ulong>,ATL::CElementTraits<Base::Stopwatch>>::Rehash(uint)

- ea: `0x1800059a4`
- end: `0x180005ace`
- name: `?Rehash@?$CAtlMap@KVStopwatch@Base@@V?$CElementTraits@K@ATL@@V?$CElementTraits@VStopwatch@Base@@@4@@ATL@@QEAAXI@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180004128`
- `0x180004c6c`

## callees

- `0x180002172`
- `0x180002420`
- `0x180002650`
- `0x180004554`
- `0x180005104`
- `0x1800059a4`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005aa4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005aa4`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Base::Stopwatch,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Base::Stopwatch>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  unsigned int *v5; // rsi
  unsigned __int128 v6; // rax
  _QWORD *v7; // rax
  int v8; // edx
  _QWORD *v9; // r14
  __int64 i; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // rdx

  v3 = a2;
  if ( !a2 )
    v3 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           *(_QWORD *)(a1 + 8));
  v5 = (unsigned int *)(a1 + 16);
  if ( v3 != *(_DWORD *)(a1 + 16) )
  {
    if ( *(_QWORD *)a1 )
    {
      v6 = v3 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v3, 8u) )
        *(_QWORD *)&v6 = -1;
      BYTE8(v6) = 1;
      v7 = BasePrivate::New(v6, *((unsigned __int64 *)&v6 + 1), a3);
      v9 = v7;
      if ( !v7 )
        ATL::BaseAtlThrow((BasePrivate *)0x8007000ELL, v8);
      memset_0(v7, 0, 8LL * v3);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
        if ( v11 )
        {
          do
          {
            v12 = *(_QWORD *)(v11 + 40);
            v13 = *(_DWORD *)(v11 + 48) % v3;
            *(_QWORD *)(v11 + 40) = v9[v13];
            v9[(unsigned int)v13] = v11;
            v11 = v12;
          }
          while ( v12 );
        }
      }
      if ( *(_QWORD *)a1 )
        free(*(void **)a1);
      *(_QWORD *)a1 = v9;
      *v5 = v3;
      ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(a1);
    }
    else
    {
      ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(
        (void **)a1,
        v3,
        0);
    }
  }
}

```

## disassembly

```asm
0x1800059a4  mov     [rsp+arg_8], edx
0x1800059a8  mov     [rsp+arg_0], rcx
0x1800059ad  push    rbx
0x1800059ae  push    rsi
0x1800059af  push    rdi
0x1800059b0  push    r14
0x1800059b2  push    r15
0x1800059b4  sub     rsp, 30h
0x1800059b8  mov     edi, edx
0x1800059ba  mov     rbx, rcx
0x1800059bd  test    edx, edx
0x1800059bf  jnz     short loc_1800059D0
0x1800059c1  mov     rdx, [rcx+8]
0x1800059c5  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x1800059ca  mov     edi, eax
0x1800059cc  mov     [rsp+58h+arg_8], eax
0x1800059d0  lea     rsi, [rbx+10h]
0x1800059d4  mov     [rsp+58h+var_38], rsi
0x1800059d9  cmp     edi, [rsi]
0x1800059db  jz      loc_180005AB7
0x1800059e1  mov     [rsp+58h+arg_10], 0
0x1800059ea  cmp     qword ptr [rbx], 0
0x1800059ee  jnz     short loc_180005A02
0x1800059f0  xor     r8d, r8d
0x1800059f3  mov     edx, edi
0x1800059f5  mov     rcx, rbx
0x1800059f8  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x1800059fd  jmp     loc_180005AB7
0x180005a02  mov     r15d, edi
0x180005a05  mov     [rsp+58h+arg_18], r15
0x180005a0a  mov     eax, 8
0x180005a0f  mul     r15
0x180005a12  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005a19  cmovb   rax, rcx
0x180005a1d  mov     dl, 1; unsigned __int64
0x180005a1f  mov     rcx, rax; Size
0x180005a22  call    ?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180005a27  mov     r14, rax
0x180005a2a  mov     [rsp+58h+arg_10], rax
0x180005a2f  jmp     short loc_180005A49
0x180005a31  mov     rbx, [rsp+58h+arg_0]
0x180005a36  mov     edi, [rsp+58h+arg_8]
0x180005a3a  mov     r14, [rsp+58h+arg_10]
0x180005a3f  mov     r15, [rsp+58h+arg_18]
0x180005a44  mov     rsi, [rsp+58h+var_38]
0x180005a49  test    r14, r14
0x180005a4c  jz      short loc_180005AC3
0x180005a4e  lea     r8, ds:0[r15*8]; Size
0x180005a56  xor     edx, edx; Val
0x180005a58  mov     rcx, r14; void *
0x180005a5b  call    memset_0
0x180005a60  xor     r9d, r9d
0x180005a63  cmp     [rsi], r9d
0x180005a66  jbe     short loc_180005A9C
0x180005a68  mov     rax, [rbx]
0x180005a6b  mov     r10, [rax+r9*8]
0x180005a6f  test    r10, r10
0x180005a72  jz      short loc_180005A94
0x180005a74  mov     r8, [r10+28h]
0x180005a78  xor     edx, edx
0x180005a7a  mov     eax, [r10+30h]
0x180005a7e  div     edi
0x180005a80  mov     rax, [r14+rdx*8]
0x180005a84  mov     [r10+28h], rax
0x180005a88  mov     [r14+rdx*8], r10
0x180005a8c  mov     r10, r8
0x180005a8f  test    r8, r8
0x180005a92  jnz     short loc_180005A74
0x180005a94  inc     r9d
0x180005a97  cmp     r9d, [rsi]
0x180005a9a  jb      short loc_180005A68
0x180005a9c  mov     rcx, [rbx]; Block
0x180005a9f  test    rcx, rcx
0x180005aa2  jz      short loc_180005AAA
0x180005aa4  call    cs:__imp_free
0x180005aaa  mov     [rbx], r14
0x180005aad  mov     [rsi], edi
0x180005aaf  mov     rcx, rbx
0x180005ab2  call    ?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)
0x180005ab7  add     rsp, 30h
0x180005abb  pop     r15
0x180005abd  pop     r14
0x180005abf  pop     rdi
0x180005ac0  pop     rsi
0x180005ac1  pop     rbx
0x180005ac2  retn
0x180005ac3  mov     ecx, 8007000Eh; int
0x180005ac8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
