# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::Rehash(uint)

- ea: `0x180005ad4`
- end: `0x180005bfe`
- name: `?Rehash@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@QEAAXI@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800041b4`
- `0x180004dd8`

## callees

- `0x180002172`
- `0x180002420`
- `0x180002650`
- `0x180004554`
- `0x180005104`
- `0x180005ad4`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005bd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005bd4`

## pseudocode

```c
void __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::Rehash(
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
            v12 = *(_QWORD *)(v11 + 72);
            v13 = *(_DWORD *)(v11 + 80) % v3;
            *(_QWORD *)(v11 + 72) = v9[v13];
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
0x180005ad4  mov     [rsp+arg_8], edx
0x180005ad8  mov     [rsp+arg_0], rcx
0x180005add  push    rbx
0x180005ade  push    rsi
0x180005adf  push    rdi
0x180005ae0  push    r14
0x180005ae2  push    r15
0x180005ae4  sub     rsp, 30h
0x180005ae8  mov     edi, edx
0x180005aea  mov     rbx, rcx
0x180005aed  test    edx, edx
0x180005aef  jnz     short loc_180005B00
0x180005af1  mov     rdx, [rcx+8]
0x180005af5  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180005afa  mov     edi, eax
0x180005afc  mov     [rsp+58h+arg_8], eax
0x180005b00  lea     rsi, [rbx+10h]
0x180005b04  mov     [rsp+58h+var_38], rsi
0x180005b09  cmp     edi, [rsi]
0x180005b0b  jz      loc_180005BE7
0x180005b11  mov     [rsp+58h+arg_10], 0
0x180005b1a  cmp     qword ptr [rbx], 0
0x180005b1e  jnz     short loc_180005B32
0x180005b20  xor     r8d, r8d
0x180005b23  mov     edx, edi
0x180005b25  mov     rcx, rbx
0x180005b28  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x180005b2d  jmp     loc_180005BE7
0x180005b32  mov     r15d, edi
0x180005b35  mov     [rsp+58h+arg_18], r15
0x180005b3a  mov     eax, 8
0x180005b3f  mul     r15
0x180005b42  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005b49  cmovb   rax, rcx
0x180005b4d  mov     dl, 1; unsigned __int64
0x180005b4f  mov     rcx, rax; Size
0x180005b52  call    ?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180005b57  mov     r14, rax
0x180005b5a  mov     [rsp+58h+arg_10], rax
0x180005b5f  jmp     short loc_180005B79
0x180005b61  mov     rbx, [rsp+58h+arg_0]
0x180005b66  mov     edi, [rsp+58h+arg_8]
0x180005b6a  mov     r14, [rsp+58h+arg_10]
0x180005b6f  mov     r15, [rsp+58h+arg_18]
0x180005b74  mov     rsi, [rsp+58h+var_38]
0x180005b79  test    r14, r14
0x180005b7c  jz      short loc_180005BF3
0x180005b7e  lea     r8, ds:0[r15*8]; Size
0x180005b86  xor     edx, edx; Val
0x180005b88  mov     rcx, r14; void *
0x180005b8b  call    memset_0
0x180005b90  xor     r9d, r9d
0x180005b93  cmp     [rsi], r9d
0x180005b96  jbe     short loc_180005BCC
0x180005b98  mov     rax, [rbx]
0x180005b9b  mov     r10, [rax+r9*8]
0x180005b9f  test    r10, r10
0x180005ba2  jz      short loc_180005BC4
0x180005ba4  mov     r8, [r10+48h]
0x180005ba8  xor     edx, edx
0x180005baa  mov     eax, [r10+50h]
0x180005bae  div     edi
0x180005bb0  mov     rax, [r14+rdx*8]
0x180005bb4  mov     [r10+48h], rax
0x180005bb8  mov     [r14+rdx*8], r10
0x180005bbc  mov     r10, r8
0x180005bbf  test    r8, r8
0x180005bc2  jnz     short loc_180005BA4
0x180005bc4  inc     r9d
0x180005bc7  cmp     r9d, [rsi]
0x180005bca  jb      short loc_180005B98
0x180005bcc  mov     rcx, [rbx]; Block
0x180005bcf  test    rcx, rcx
0x180005bd2  jz      short loc_180005BDA
0x180005bd4  call    cs:__imp_free
0x180005bda  mov     [rbx], r14
0x180005bdd  mov     [rsi], edi
0x180005bdf  mov     rcx, rbx
0x180005be2  call    ?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)
0x180005be7  add     rsp, 30h
0x180005beb  pop     r15
0x180005bed  pop     r14
0x180005bef  pop     rdi
0x180005bf0  pop     rsi
0x180005bf1  pop     rbx
0x180005bf2  retn
0x180005bf3  mov     ecx, 8007000Eh; int
0x180005bf8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
