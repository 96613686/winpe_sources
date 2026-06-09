# UlpCreateRequestQueue

- ea: `0x1400955b8`
- end: `0x14009590d`
- name: `UlpCreateRequestQueue`
- size: `853`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, HANDLE Handle, ULONG_PTR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a337c`

## callees

- `0x14000a350`
- `0x1400636bc`
- `0x1400953bc`
- `0x1400955b8`
- `0x140095914`
- `0x140095d7c`
- `0x140095f50`
- `0x14009620c`
- `0x1400cdf0c`
- `0x1400ceb54`
- `0x1400d02f4`
- `0x1400d724c`
- `0x1401c5a0c`
- `0x1401c6088`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140095729`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x14017bea2`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140095729`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x14017bea2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14009575a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14009575a`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140095705`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14017be79`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140095705`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14017be79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400956b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140095735`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14017beae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400956b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140095735`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14017beae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400956a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400956a7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095652`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095652`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009563a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400956f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14017be66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009563a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400956f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14017be66`

## pseudocode

```c
__int64 __fastcall UlpCreateRequestQueue(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        HANDLE Handle,
        ULONG_PTR *a8)
{
  ULONG_PTR v8; // rsi
  const UNICODE_STRING *v9; // rdi
  __int64 *v12; // r14
  __int64 v13; // rsi
  int Consumer; // edi
  __int64 v16; // r13
  ULONG_PTR *v17; // rcx
  ULONG_PTR v18; // rdx
  int v19; // eax
  ULONG_PTR v20; // rdx
  int v21; // eax
  ULONG_PTR v22; // rbx
  ULONG_PTR v23; // rax
  ULONG_PTR v24; // r8
  void *v25; // rbx
  ULONG_PTR v26; // [rsp+68h] [rbp-18h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+70h] [rbp-10h] BYREF

  v8 = 0;
  v26 = 0;
  v9 = (const UNICODE_STRING *)a3;
  BugCheckParameter2[0] = 0;
  v12 = (__int64 *)(a3 + 8);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_qllSqqLqq((unsigned __int16)a2, HIWORD(a2), a3, a1, a2, SBYTE2(a2), *v12, a4, a5, a6, (char)Handle, (char)a8);
    v8 = v26;
  }
  *a8 = 0;
  if ( a6 - 1 <= 1 )
  {
    if ( *v12 )
    {
      Consumer = UlpValidateRequestQueueName(v9);
      if ( Consumer < 0 )
      {
LABEL_34:
        v8 = v26;
        goto LABEL_37;
      }
      v9 = (const UNICODE_STRING *)a3;
LABEL_6:
      KeEnterCriticalRegion();
      v13 = a1 + 4144;
      ExAcquirePushLockExclusiveEx(a1 + 4144, 0);
      if ( *v12 && UlpFindRequestQueue(a1, v9, 1) )
      {
        Consumer = -1073741771;
        goto LABEL_9;
      }
      Consumer = UlListenerObjectAccessCheck(a5, L"RequestQueue");
      if ( Consumer >= 0 )
      {
        Consumer = UlpAllocateRequestQueue(a1, a2, a3, a4, &v26);
        if ( Consumer >= 0 )
        {
          Consumer = UlpAllocateConsumer(a5, a6, BugCheckParameter2);
          if ( Consumer >= 0 )
          {
            v22 = v26;
            if ( *(_BYTE *)(v26 + 144) )
            {
              Consumer = UlCreateAutoServerSession(Handle, *(_BYTE *)(a5 + 64), v26);
              if ( Consumer < 0 )
                goto LABEL_9;
              v22 = v26;
            }
            KeEnterCriticalRegion();
            ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v22 + 280));
            UlpAttachConsumerToRequestQueue(v26, BugCheckParameter2[0]);
            ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v26 + 280));
            KeLeaveCriticalRegion();
            RtlInsertEntryHashTable(
              (PRTL_DYNAMIC_HASH_TABLE)(a1 + 4152),
              (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v26 + 176),
              1u,
              0);
            v16 = a1 + 4192;
            v17 = *(ULONG_PTR **)(v16 + 8);
            if ( *v17 != v16 )
              __fastfail(3u);
            v23 = v26 + 200;
            *(_QWORD *)(v26 + 200) = v16;
            *(_QWORD *)(v23 + 8) = v17;
            *v17 = v23;
            v24 = BugCheckParameter2[0];
            *(_QWORD *)(v16 + 8) = v23;
            *a8 = v24;
            if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
              WPP_SF_qZqL((_DWORD)v17, 75, v24, v26, v26 + 160, v24, a6);
          }
        }
      }
LABEL_9:
      ExReleasePushLockExclusiveEx(v13, 0);
      KeLeaveCriticalRegion();
      if ( Consumer >= 0 )
        goto LABEL_10;
      goto LABEL_34;
    }
    if ( a6 == 1 )
      goto LABEL_6;
  }
  Consumer = -1073741811;
LABEL_37:
  if ( v8 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v8 + 280));
    v25 = *(void **)(v26 + 136);
    *(_QWORD *)(v26 + 136) = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v26 + 280));
    KeLeaveCriticalRegion();
    if ( v25 )
      UlDeleteAutoServerSession(v25);
    v18 = v26;
    v19 = _InterlockedDecrement((volatile signed __int32 *)v26);
    if ( UxDebugCheckRefcount && v19 <= -1 )
      UlBugCheckEx(3u, v18, 1u, v19);
    if ( !v19 )
      UlFreeRequestQueue((PVOID)v26);
  }
  v20 = BugCheckParameter2[0];
  if ( BugCheckParameter2[0] )
  {
    v21 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2[0]);
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, v20, 1u, v21);
    UlpFreeConsumer((PVOID)BugCheckParameter2[0]);
  }
LABEL_10:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 76, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, *a8, Consumer);
  return (unsigned int)Consumer;
}

```

## disassembly

```asm
0x1400955b8  mov     [rsp-38h+arg_0], rbx
0x1400955bd  mov     [rsp-38h+arg_18], r9
0x1400955c2  mov     [rsp-38h+arg_10], r8
0x1400955c7  push    rbp
0x1400955c8  push    rsi
0x1400955c9  push    rdi
0x1400955ca  push    r12
0x1400955cc  push    r13
0x1400955ce  push    r14
0x1400955d0  push    r15
0x1400955d2  mov     rbp, rsp
0x1400955d5  sub     rsp, 80h
0x1400955dc  xor     esi, esi
0x1400955de  mov     dword ptr [rbp+Signature], 1
0x1400955e5  mov     [rbp+var_18], rsi
0x1400955e9  mov     rdi, r8
0x1400955ec  mov     [rbp+BugCheckParameter2], rsi
0x1400955f0  mov     ebx, edx
0x1400955f2  mov     r13, rcx
0x1400955f5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400955fc  lea     r14, [r8+8]
0x140095600  mov     r15d, [rbp+arg_28]
0x140095604  mov     r12, [rbp+arg_20]
0x140095608  jnz     loc_140095801
0x14009560e  mov     rax, [rbp+arg_38]
0x140095612  mov     qword ptr [rax], 0
0x140095619  lea     eax, [r15-1]
0x14009561d  cmp     eax, 1
0x140095620  ja      loc_140095849
0x140095626  cmp     qword ptr [r14], 0
0x14009562a  jnz     loc_140095853
0x140095630  cmp     r15d, 1
0x140095634  jnz     loc_140095849
0x14009563a  call    cs:__imp_KeEnterCriticalRegion
0x140095641  nop     dword ptr [rax+rax+00h]
0x140095646  lea     rsi, [r13+1030h]
0x14009564d  xor     edx, edx
0x14009564f  mov     rcx, rsi
0x140095652  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140095659  nop     dword ptr [rax+rax+00h]
0x14009565e  cmp     qword ptr [r14], 0
0x140095662  jnz     loc_14009586E
0x140095668  lea     rdx, aRequestqueue; "RequestQueue"
0x14009566f  mov     rcx, r12
0x140095672  call    UlListenerObjectAccessCheck
0x140095677  mov     edi, eax
0x140095679  test    eax, eax
0x14009567b  js      short loc_1400956A2
0x14009567d  mov     r9, [rbp+arg_18]
0x140095681  lea     rax, [rbp+var_18]
0x140095685  mov     r8, [rbp+arg_10]
0x140095689  mov     edx, ebx
0x14009568b  mov     rcx, r13
0x14009568e  mov     [rsp+80h+var_60], rax
0x140095693  call    UlpAllocateRequestQueue
0x140095698  mov     edi, eax
0x14009569a  test    eax, eax
0x14009569c  jns     loc_140095890
0x1400956a2  xor     edx, edx
0x1400956a4  mov     rcx, rsi
0x1400956a7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400956ae  nop     dword ptr [rax+rax+00h]
0x1400956b3  call    cs:__imp_KeLeaveCriticalRegion
0x1400956ba  nop     dword ptr [rax+rax+00h]
0x1400956bf  test    edi, edi
0x1400956c1  js      loc_1400958DE
0x1400956c7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400956ce  jnz     loc_1400958E7
0x1400956d4  mov     rbx, [rsp+80h+arg_0]
0x1400956dc  mov     eax, edi
0x1400956de  add     rsp, 80h
0x1400956e5  pop     r15
0x1400956e7  pop     r14
0x1400956e9  pop     r13
0x1400956eb  pop     r12
0x1400956ed  pop     rdi
0x1400956ee  pop     rsi
0x1400956ef  pop     rbp
0x1400956f0  retn
0x1400956f2  call    cs:__imp_KeEnterCriticalRegion
0x1400956f9  nop     dword ptr [rax+rax+00h]
0x1400956fe  mov     rcx, [rbx+118h]
0x140095705  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x14009570c  nop     dword ptr [rax+rax+00h]
0x140095711  mov     rdx, [rbp+BugCheckParameter2]; ULONG_PTR
0x140095715  mov     rcx, [rbp+var_18]; BugCheckParameter2
0x140095719  call    UlpAttachConsumerToRequestQueue
0x14009571e  mov     rcx, [rbp+var_18]
0x140095722  mov     rcx, [rcx+118h]
0x140095729  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140095730  nop     dword ptr [rax+rax+00h]
0x140095735  call    cs:__imp_KeLeaveCriticalRegion
0x14009573c  nop     dword ptr [rax+rax+00h]
0x140095741  mov     rdx, [rbp+var_18]
0x140095745  lea     rcx, [r13+1038h]; HashTable
0x14009574c  mov     r8d, dword ptr [rbp+Signature]; Signature
0x140095750  add     rdx, 0B0h; Entry
0x140095757  xor     r9d, r9d; Context
0x14009575a  call    cs:__imp_RtlInsertEntryHashTable
0x140095761  nop     dword ptr [rax+rax+00h]
0x140095766  add     r13, 1060h
0x14009576d  mov     rcx, [r13+8]
0x140095771  cmp     [rcx], r13
0x140095774  jz      loc_14017BDFC
0x14009577a  mov     ecx, 3
0x14009577f  int     29h; Win8: RtlFailFast(ecx)
0x140095781  mov     rdx, [rbp+var_18]; BugCheckParameter2
0x140095785  mov     eax, r15d
0x140095788  lock xadd [rdx], eax
0x14009578c  add     eax, r15d
0x14009578f  cmp     cs:UxDebugCheckRefcount, r14b
0x140095796  jnz     short loc_1400957DC
0x140095798  test    eax, eax
0x14009579a  jnz     short loc_1400957A5
0x14009579c  mov     rcx, [rbp+var_18]; P
0x1400957a0  call    UlFreeRequestQueue
0x1400957a5  mov     rdx, [rbp+BugCheckParameter2]; BugCheckParameter2
0x1400957a9  test    rdx, rdx
0x1400957ac  jz      loc_1400956C7
0x1400957b2  mov     eax, r15d
0x1400957b5  lock xadd [rdx], eax
0x1400957b9  add     eax, r15d
0x1400957bc  cmp     cs:UxDebugCheckRefcount, r14b
0x1400957c3  jz      short loc_1400957F3
0x1400957c5  cmp     eax, r15d
0x1400957c8  jg      short loc_1400957F3
0x1400957ca  mov     ecx, 3; BugCheckParameter1
0x1400957cf  movsxd  r9, eax; BugCheckParameter4
0x1400957d2  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400957d6  call    UlBugCheckEx
0x1400957dc  cmp     eax, r15d
0x1400957df  jg      short loc_140095798
0x1400957e1  mov     ecx, 3; BugCheckParameter1
0x1400957e6  movsxd  r9, eax; BugCheckParameter4
0x1400957e9  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400957ed  call    UlBugCheckEx
0x1400957f3  mov     rcx, [rbp+BugCheckParameter2]; P
0x1400957f7  call    UlpFreeConsumer
0x1400957fc  jmp     loc_1400956C7
0x140095801  mov     rax, [rbp+arg_38]
0x140095805  mov     [rsp+80h+var_28], rax
0x14009580a  mov     rax, [rbp+Handle]
0x14009580e  mov     [rsp+80h+var_30], rax
0x140095813  mov     rax, [r14]
0x140095816  mov     [rsp+80h+var_38], r15d
0x14009581b  mov     [rsp+80h+var_40], r12
0x140095820  mov     [rsp+80h+var_48], r9
0x140095825  mov     r9, r13
0x140095828  mov     [rsp+80h+var_50], rax
0x14009582d  shr     edx, 10h
0x140095830  movzx   ecx, bx
0x140095833  mov     [rsp+80h+var_58], edx
0x140095837  mov     dword ptr [rsp+80h+var_60], ecx
0x14009583b  call    WPP_SF_qllSqqLqq
0x140095840  mov     rsi, [rbp+var_18]
0x140095844  jmp     loc_14009560E
0x140095849  mov     edi, 0C000000Dh
0x14009584e  jmp     loc_14017BE56
0x140095853  lea     rdx, [rbp+Signature]
0x140095857  mov     rcx, rdi; String
0x14009585a  call    UlpValidateRequestQueueName
0x14009585f  mov     edi, eax
0x140095861  test    eax, eax
0x140095863  js      short loc_1400958DE
0x140095865  mov     rdi, [rbp+arg_10]
0x140095869  jmp     loc_14009563A
0x14009586e  mov     r8d, dword ptr [rbp+Signature]
0x140095872  mov     rdx, rdi
0x140095875  mov     rcx, r13
0x140095878  call    UlpFindRequestQueue
0x14009587d  test    rax, rax
0x140095880  jz      loc_140095668
0x140095886  mov     edi, 0C0000035h
0x14009588b  jmp     loc_1400956A2
0x140095890  lea     r8, [rbp+BugCheckParameter2]
0x140095894  mov     edx, r15d
0x140095897  mov     rcx, r12
0x14009589a  call    UlpAllocateConsumer
0x14009589f  mov     edi, eax
0x1400958a1  test    eax, eax
0x1400958a3  js      loc_1400956A2
0x1400958a9  mov     rbx, [rbp+var_18]
0x1400958ad  cmp     byte ptr [rbx+90h], 0
0x1400958b4  jz      loc_1400956F2
0x1400958ba  mov     dl, [r12+40h]
0x1400958bf  mov     r8, rbx
0x1400958c2  mov     rcx, [rbp+Handle]; Handle
0x1400958c6  call    UlCreateAutoServerSession
0x1400958cb  mov     edi, eax
0x1400958cd  test    eax, eax
0x1400958cf  js      loc_1400956A2
0x1400958d5  mov     rbx, [rbp+var_18]
0x1400958d9  jmp     loc_1400956F2
0x1400958de  mov     rsi, [rbp+var_18]
0x1400958e2  jmp     loc_14017BE56
0x1400958e7  mov     rax, [rbp+arg_38]
0x1400958eb  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400958f2  mov     edx, 4Ch ; 'L'
0x1400958f7  mov     dword ptr [rsp+80h+var_60], edi
0x1400958fb  mov     ecx, 408h
0x140095900  mov     r9, [rax]
0x140095903  call    WPP_SF_qD
0x140095908  jmp     loc_1400956D4
0x14017bdfc  mov     rax, [rbp+var_18]
0x14017be00  add     rax, 0C8h
0x14017be06  mov     [rax], r13
0x14017be09  mov     [rax+8], rcx
0x14017be0d  mov     [rcx], rax
0x14017be10  mov     r8, [rbp+BugCheckParameter2]
0x14017be14  mov     [r13+8], rax
0x14017be18  mov     rax, [rbp+arg_38]
0x14017be1c  mov     [rax], r8
0x14017be1f  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x14017be26  jz      loc_1400956A2
0x14017be2c  mov     r9, [rbp+var_18]
0x14017be30  mov     edx, 4Bh ; 'K'
0x14017be35  mov     dword ptr [rsp+80h+var_50], r15d
0x14017be3a  mov     qword ptr [rsp+80h+var_58], r8
0x14017be3f  lea     rax, [r9+0A0h]
0x14017be46  mov     [rsp+80h+var_60], rax
0x14017be4b  call    WPP_SF_qZqL
0x14017be50  nop
0x14017be51  jmp     loc_1400956A2
0x14017be56  or      r15d, 0FFFFFFFFh
0x14017be5a  xor     r14d, r14d
0x14017be5d  test    rsi, rsi
0x14017be60  jz      loc_1400957A5
0x14017be66  call    cs:__imp_KeEnterCriticalRegion
0x14017be6d  nop     dword ptr [rax+rax+00h]
0x14017be72  mov     rcx, [rsi+118h]
0x14017be79  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x14017be80  nop     dword ptr [rax+rax+00h]
0x14017be85  mov     rax, [rbp+var_18]
0x14017be89  mov     rbx, [rax+88h]
0x14017be90  mov     [rax+88h], r14
0x14017be97  mov     rcx, [rbp+var_18]
0x14017be9b  mov     rcx, [rcx+118h]
0x14017bea2  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x14017bea9  nop     dword ptr [rax+rax+00h]
0x14017beae  call    cs:__imp_KeLeaveCriticalRegion
0x14017beb5  nop     dword ptr [rax+rax+00h]
0x14017beba  test    rbx, rbx
0x14017bebd  jz      loc_140095781
0x14017bec3  mov     rcx, rbx
0x14017bec6  call    UlDeleteAutoServerSession
0x14017becb  nop
0x14017becc  jmp     loc_140095781
```
