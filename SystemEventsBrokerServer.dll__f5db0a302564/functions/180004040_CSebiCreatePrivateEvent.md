# _CSebiCreatePrivateEvent

- ea: `0x180004040`
- end: `0x180004247`
- name: `_CSebiCreatePrivateEvent`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180004040`
- `0x180005a50`
- `0x180009740`
- `0x180027010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004114`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004114`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004126`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004126`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411a`

## pseudocode

```c
__int64 __fastcall CSebiCreatePrivateEvent(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  CBroker::SebBroker *v7; // rbx
  volatile signed __int32 *v8; // rbx
  unsigned int Event; // esi
  _QWORD *v10; // rcx
  char *v12; // rdi
  char v13; // bl
  __int64 v14; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  _OWORD v17[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v18; // [rsp+60h] [rbp-18h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  *a3 = 0;
  *a4 = 0;
  v7 = CBroker::SebBroker::Instance;
  if ( !CBroker::SebBroker::Instance
    || (v12 = (char *)CBroker::SebBroker::Instance + 8,
        RtlAcquireSRWLockExclusive((char *)CBroker::SebBroker::Instance + 8),
        GetCurrentThreadId(),
        v13 = *(_BYTE *)v7,
        RtlReleaseSRWLockExclusive(v12),
        !v13) )
  {
    v8 = 0;
LABEL_6:
    Event = 21;
LABEL_7:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v8 = (volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1);
  if ( *(&CBroker::SebBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1) + 2);
    v8 = (volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1);
  }
  if ( !CBroker::SebBroker::Instance )
    goto LABEL_6;
  if ( *(_DWORD *)(a2 + 8) != 4124 )
  {
    Event = 87;
    goto LABEL_7;
  }
  if ( *(_QWORD *)a2 )
  {
    v15 = *(_OWORD *)(a2 + 16);
    v17[0] = *(_OWORD *)a2;
    v16 = *(_OWORD *)(a2 + 32);
    v17[1] = v15;
    *(_QWORD *)&v15 = *(_QWORD *)(a2 + 48);
    v17[2] = v16;
    v18 = v15;
    Event = _SebiCreateEvent(v14, (const struct _CSebiSystemEventCreationParameter *)v17, 0, a3, a4);
    goto LABEL_7;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  Event = 87;
LABEL_8:
  if ( (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_d(v10[2], 26, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, Event);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return Event;
}

```

## disassembly

```asm
0x180004040  mov     rax, rsp
0x180004043  mov     [rax+20h], rbx
0x180004047  push    rsi
0x180004048  sub     rsp, 70h
0x18000404c  mov     [rax+10h], r14
0x180004050  mov     rsi, r9
0x180004053  mov     [rax+18h], r15
0x180004057  mov     r14, r8
0x18000405a  mov     r15, rdx
0x18000405d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004064  test    byte ptr [rcx+1Ch], 8
0x180004068  jz      short loc_180004074
0x18000406a  cmp     byte ptr [rcx+19h], 4
0x18000406e  jnb     loc_1800041DE
0x180004074  xor     eax, eax
0x180004076  mov     [rsp+78h+arg_0], rdi
0x18000407e  mov     [r14], rax
0x180004081  mov     [rsi], rax
0x180004084  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000408b  test    rbx, rbx
0x18000408e  jnz     short loc_18000410D
0x180004090  xor     ebx, ebx
0x180004092  mov     esi, 15h
0x180004097  mov     rcx, cs:WPP_GLOBAL_Control
0x18000409e  mov     r15, [rsp+78h+arg_10]
0x1800040a6  mov     r14, [rsp+78h+arg_8]
0x1800040ae  test    byte ptr [rcx+1Ch], 8
0x1800040b2  jnz     loc_1800041B7
0x1800040b8  test    rbx, rbx
0x1800040bb  jz      short loc_1800040F5
0x1800040bd  mov     edi, 0FFFFFFFFh
0x1800040c2  mov     eax, edi
0x1800040c4  lock xadd [rbx+8], eax
0x1800040c9  cmp     eax, 1
0x1800040cc  jnz     short loc_1800040F5
0x1800040ce  mov     rax, [rbx]
0x1800040d1  mov     rcx, rbx
0x1800040d4  mov     rax, [rax]
0x1800040d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040dc  lock xadd [rbx+0Ch], edi
0x1800040e1  cmp     edi, 1
0x1800040e4  jnz     short loc_1800040F5
0x1800040e6  mov     rax, [rbx]
0x1800040e9  mov     rcx, rbx
0x1800040ec  mov     rax, [rax+8]
0x1800040f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f5  mov     rdi, [rsp+78h+arg_0]
0x1800040fd  mov     eax, esi
0x1800040ff  mov     rbx, [rsp+78h+arg_18]
0x180004107  add     rsp, 70h
0x18000410b  pop     rsi
0x18000410c  retn
0x18000410d  lea     rdi, [rbx+8]
0x180004111  mov     rcx, rdi
0x180004114  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000411a  call    cs:__imp_GetCurrentThreadId
0x180004120  movzx   ebx, byte ptr [rbx]
0x180004123  mov     rcx, rdi
0x180004126  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000412c  test    bl, bl
0x18000412e  jz      loc_180004090
0x180004134  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000413b  test    rbx, rbx
0x18000413e  jz      short loc_18000414B
0x180004140  lock inc dword ptr [rbx+8]
0x180004144  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000414b  cmp     qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A, 0; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180004153  jz      loc_180004092
0x180004159  cmp     dword ptr [r15+8], 101Ch
0x180004161  jnz     loc_1800041F8
0x180004167  mov     rax, [r15]
0x18000416a  test    eax, eax
0x18000416c  jz      loc_180004202
0x180004172  movups  xmm0, xmmword ptr [r15]
0x180004176  mov     r9, r14
0x180004179  xor     r8d, r8d
0x18000417c  movups  xmm1, xmmword ptr [r15+10h]
0x180004181  lea     rdx, [rsp+78h+var_48]
0x180004186  mov     [rsp+78h+var_58], rsi
0x18000418b  movaps  [rsp+78h+var_48], xmm0
0x180004190  movups  xmm0, xmmword ptr [r15+20h]
0x180004195  movaps  [rsp+78h+var_38], xmm1
0x18000419a  movsd   xmm1, qword ptr [r15+30h]
0x1800041a0  movaps  [rsp+78h+var_28], xmm0
0x1800041a5  movsd   [rsp+78h+var_18], xmm1
0x1800041ab  call    ?_SebiCreateEvent@@YAKPEAXU_CSebiSystemEventCreationParameter@@PEAU_CustomData@CBroker@@PEAU_CBROKERED_EVENT_ID@@PEAPEAX@Z; _SebiCreateEvent(void *,_CSebiSystemEventCreationParameter,CBroker::_CustomData *,_CBROKERED_EVENT_ID *,void * *)
0x1800041b0  mov     esi, eax
0x1800041b2  jmp     loc_180004097
0x1800041b7  cmp     byte ptr [rcx+19h], 4
0x1800041bb  jb      loc_1800040B8
0x1800041c1  mov     rcx, [rcx+10h]
0x1800041c5  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800041cc  mov     edx, 1Ah
0x1800041d1  mov     r9d, esi
0x1800041d4  call    WPP_SF_d
0x1800041d9  jmp     loc_1800040B8
0x1800041de  mov     rcx, [rcx+10h]
0x1800041e2  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800041e9  mov     edx, 18h
0x1800041ee  call    WPP_SF_
0x1800041f3  jmp     loc_180004074
0x1800041f8  mov     esi, 57h ; 'W'
0x1800041fd  jmp     loc_180004097
0x180004202  shr     rax, 20h
0x180004206  test    eax, eax
0x180004208  jnz     loc_180004172
0x18000420e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004215  test    byte ptr [rcx+1Ch], 8
0x180004219  jz      short loc_18000423D
0x18000421b  cmp     byte ptr [rcx+19h], 4
0x18000421f  jb      short loc_18000423D
0x180004221  mov     rcx, [rcx+10h]
0x180004225  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18000422c  mov     edx, 19h
0x180004231  call    WPP_SF_
0x180004236  mov     rcx, cs:WPP_GLOBAL_Control
0x18000423d  mov     esi, 57h ; 'W'
0x180004242  jmp     loc_18000409E
```
