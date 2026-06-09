# AfdGetFreeConnection

- ea: `0x1400044fc`
- end: `0x1400047bd`
- name: `AfdGetFreeConnection`
- size: `705`
- prototype: `__int64 __fastcall(__int64, char, __int64 *)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003d20`
- `0x14002e9c0`
- `0x1400338b8`
- `0x14004baa0`
- `0x14004d5b0`
- `0x140059ab0`

## callees

- `0x1400044fc`
- `0x1400049b0`
- `0x14001c708`
- `0x1400391b8`
- `0x140047690`
- `0x14004d4e4`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000453b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000477c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000453b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000477c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000460b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000460b`
- `ntoskrnl!ExQueryDepthSList` at `0x1400045eb`
- `ntoskrnl!ExQueryDepthSList` at `0x1400045eb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400045ae`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400045ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400045c3`
- `ntoskrnl!IofCompleteRequest` at `0x1400045c3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000459b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000459b`

## pseudocode

```c
__int64 __fastcall AfdGetFreeConnection(__int64 a1, char a2, __int64 *a3)
{
  PSLIST_ENTRY v6; // rax
  PSLIST_ENTRY v7; // rsi
  struct _SLIST_ENTRY *v8; // rbp
  __int64 v9; // rdi
  signed __int64 v10; // rax
  bool v11; // cc
  signed __int64 v12; // rax
  __int64 result; // rax
  int v14; // eax
  signed __int32 v15; // ecx
  __int64 v16; // rdx
  int v17; // ecx
  union _SLIST_HEADER *v18; // rcx
  PSLIST_ENTRY v19; // rax
  KIRQL Irql; // [rsp+80h] [rbp+18h] BYREF
  struct _SLIST_ENTRY *v21; // [rsp+88h] [rbp+20h] BYREF

  v21 = 0;
  if ( a3 )
  {
    *a3 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(a1 + 160));
        v7 = v6;
        if ( !v6 )
          goto LABEL_17;
        v8 = v6 - 11;
        v9 = _InterlockedExchange64((volatile __int64 *)&v6[-9].Next + 1, 0);
        v21 = v6 - 11;
        if ( v9 )
        {
          if ( _InterlockedExchange64((volatile __int64 *)(v9 + 104), 0) )
          {
            *a3 = v9;
            return (__int64)&v6[-11];
          }
          Irql = 0;
          AfdCleanupSuperAccept(v9, -1073741536);
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
          IofCompleteRequest((PIRP)v9, AfdPriorityBoost);
        }
        if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
          break;
LABEL_12:
        v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v7[-8], 0xFFFFFFFFFFFFFFFFuLL);
        v11 = v10 <= 1;
        v12 = v10 - 1;
        if ( v11 )
        {
          if ( v12 )
            __fastfail(0xEu);
          AfdCloseConnection((__int64)v8);
        }
      }
      if ( *(int *)(a1 + 176) < 0 || ExQueryDepthSList((PSLIST_HEADER)(a1 + 144)) >= 0x7FFFu )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 176));
        goto LABEL_12;
      }
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), v8 + 11);
    }
  }
LABEL_17:
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
      return 0;
    if ( a3 )
    {
      v14 = *(_DWORD *)(a1 + 8);
      v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 176), 1u);
      v16 = *(unsigned __int16 *)(a1 + 190);
      v17 = v15 + 1;
      if ( (v14 & 2) != 0 )
      {
        if ( v17 > (int)v16 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 176));
LABEL_23:
          AFD_PCW_INCREMENT_REJECTED_CONNECTIONS();
          return 0;
        }
      }
      else if ( v17 == (_DWORD)v16 )
      {
        LOBYTE(v16) = 1;
        AfdTLHandleListenBacklog(a1, v16, 0);
      }
      else if ( v17 > 5 * (int)v16 )
      {
        if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 176)) == 8 * (int)v16 / 0xAu )
          AfdTLHandleListenBacklog(a1, 0, 0);
        goto LABEL_23;
      }
    }
    if ( (int)AfdCreateConnection(
                a1,
                *(void **)(a1 + 272),
                *(void **)(a1 + 256),
                0,
                1u,
                0,
                *(struct _KPROCESS **)(a1 + 48),
                (__int64 *)&v21) < 0 )
      return 0;
    result = (__int64)v21;
    if ( a3 )
      HIDWORD(v21->Next) |= 0x40000u;
  }
  else
  {
    if ( a2 )
      v18 = (union _SLIST_HEADER *)(*(_QWORD *)(a1 + 280) + 32LL);
    else
      v18 = (union _SLIST_HEADER *)(a1 + 144);
    v19 = ExpInterlockedPopEntrySList(v18);
    if ( !v19 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 0x200) == 0 )
        return 0;
      goto LABEL_23;
    }
    return (__int64)&v19[-11];
  }
  return result;
}

```

## disassembly

```asm
0x1400044fc  mov     rax, rsp
0x1400044ff  mov     [rax+8], rbx
0x140004503  mov     [rax+10h], rbp
0x140004507  push    rsi
0x140004508  push    rdi
0x140004509  push    r12
0x14000450b  push    r14
0x14000450d  push    r15
0x14000450f  sub     rsp, 40h
0x140004513  mov     qword ptr [rax+20h], 0
0x14000451b  mov     r14, r8
0x14000451e  mov     r15b, dl
0x140004521  mov     rbx, rcx
0x140004524  test    r8, r8
0x140004527  jz      loc_140004660
0x14000452d  mov     qword ptr [r8], 0
0x140004534  lea     rcx, [rbx+0A0h]; ListHead
0x14000453b  call    cs:__imp_ExpInterlockedPopEntrySList
0x140004542  nop     dword ptr [rax+rax+00h]
0x140004547  mov     rsi, rax
0x14000454a  test    rax, rax
0x14000454d  jz      loc_140004660
0x140004553  xor     edi, edi
0x140004555  lea     rbp, [rax-0B0h]
0x14000455c  xchg    rdi, [rax-88h]
0x140004563  mov     [rsp+68h+arg_18], rbp
0x14000456b  test    rdi, rdi
0x14000456e  jz      short loc_1400045CF
0x140004570  xor     eax, eax
0x140004572  xchg    rax, [rdi+68h]
0x140004576  test    rax, rax
0x140004579  jnz     loc_140004655
0x14000457f  mov     edx, 0C0000120h
0x140004584  mov     [rsp+68h+Irql], al
0x14000458b  mov     rcx, rdi
0x14000458e  call    AfdCleanupSuperAccept
0x140004593  lea     rcx, [rsp+68h+Irql]; Irql
0x14000459b  call    cs:__imp_IoAcquireCancelSpinLock
0x1400045a2  nop     dword ptr [rax+rax+00h]
0x1400045a7  mov     cl, [rsp+68h+Irql]; Irql
0x1400045ae  call    cs:__imp_IoReleaseCancelSpinLock
0x1400045b5  nop     dword ptr [rax+rax+00h]
0x1400045ba  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400045c0  mov     rcx, rdi; Irp
0x1400045c3  call    cs:__imp_IofCompleteRequest
0x1400045ca  nop     dword ptr [rax+rax+00h]
0x1400045cf  mov     eax, [rbx+8]
0x1400045d2  bt      eax, 8
0x1400045d6  jb      short loc_140004623
0x1400045d8  cmp     dword ptr [rbx+0B0h], 0
0x1400045df  jl      short loc_14000461C
0x1400045e1  lea     rdi, [rbx+90h]
0x1400045e8  mov     rcx, rdi; SListHead
0x1400045eb  call    cs:__imp_ExQueryDepthSList
0x1400045f2  nop     dword ptr [rax+rax+00h]
0x1400045f7  mov     ecx, 7FFFh
0x1400045fc  cmp     ax, cx
0x1400045ff  jnb     short loc_14000461C
0x140004601  lea     rdx, [rbp+0B0h]; ListEntry
0x140004608  mov     rcx, rdi; ListHead
0x14000460b  call    cs:__imp_ExpInterlockedPushEntrySList
0x140004612  nop     dword ptr [rax+rax+00h]
0x140004617  jmp     loc_140004534
0x14000461c  lock inc dword ptr [rbx+0B0h]
0x140004623  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004627  lock xadd [rsi-80h], rax
0x14000462d  sub     rax, 1
0x140004631  jg      loc_140004534
0x140004637  test    rax, rax
0x14000463a  jnz     short loc_140004649
0x14000463c  mov     rcx, rbp
0x14000463f  call    AfdCloseConnection
0x140004644  jmp     loc_140004534
0x140004649  mov     ecx, 0Eh
0x14000464e  int     29h; Win8: RtlFailFast(ecx)
0x140004650  jmp     loc_140004534
0x140004655  mov     [r14], rdi
0x140004658  mov     rax, rbp
0x14000465b  jmp     loc_1400047A5
0x140004660  mov     eax, [rbx+8]
0x140004663  bt      eax, 8
0x140004667  jnb     loc_140004763
0x14000466d  mov     eax, [rbx+8]
0x140004670  bt      eax, 0Bh
0x140004674  jb      short loc_1400046AA
0x140004676  test    r14, r14
0x140004679  jz      short loc_1400046C2
0x14000467b  mov     eax, [rbx+8]
0x14000467e  mov     ecx, 1
0x140004683  lock xadd [rbx+0B0h], ecx
0x14000468b  movzx   edx, word ptr [rbx+0BEh]
0x140004692  inc     ecx
0x140004694  bt      eax, 1
0x140004698  jnb     short loc_1400046B1
0x14000469a  cmp     ecx, edx
0x14000469c  jle     short loc_1400046C2
0x14000469e  lock dec dword ptr [rbx+0B0h]
0x1400046a5  call    AFD_PCW_INCREMENT_REJECTED_CONNECTIONS
0x1400046aa  xor     eax, eax
0x1400046ac  jmp     loc_1400047A5
0x1400046b1  cmp     ecx, edx
0x1400046b3  jnz     short loc_140004720
0x1400046b5  xor     r8d, r8d
0x1400046b8  mov     dl, 1
0x1400046ba  mov     rcx, rbx
0x1400046bd  call    AfdTLHandleListenBacklog
0x1400046c2  mov     r8, [rbx+100h]
0x1400046c9  lea     rax, [rsp+68h+arg_18]
0x1400046d1  mov     rdx, [rbx+110h]
0x1400046d8  xor     r9d, r9d
0x1400046db  mov     [rsp+68h+var_30], rax
0x1400046e0  mov     rcx, rbx
0x1400046e3  mov     rax, [rbx+30h]
0x1400046e7  mov     [rsp+68h+var_38], rax
0x1400046ec  mov     [rsp+68h+var_40], 0
0x1400046f4  mov     [rsp+68h+var_48], 1
0x1400046fc  call    AfdCreateConnection
0x140004701  test    eax, eax
0x140004703  js      short loc_1400046AA
0x140004705  mov     rax, [rsp+68h+arg_18]
0x14000470d  test    r14, r14
0x140004710  jz      loc_1400047A5
0x140004716  bts     dword ptr [rax+4], 12h
0x14000471b  jmp     loc_1400047A5
0x140004720  lea     eax, [rdx+rdx*4]
0x140004723  cmp     ecx, eax
0x140004725  jle     short loc_1400046C2
0x140004727  or      r8d, 0FFFFFFFFh
0x14000472b  lock xadd [rbx+0B0h], r8d
0x140004734  lea     ecx, ds:0[rdx*8]
0x14000473b  mov     eax, 0CCCCCCCDh
0x140004740  mul     ecx
0x140004742  dec     r8d
0x140004745  shr     edx, 3
0x140004748  cmp     r8d, edx
0x14000474b  jnz     loc_1400046A5
0x140004751  xor     r8d, r8d
0x140004754  xor     edx, edx
0x140004756  mov     rcx, rbx
0x140004759  call    AfdTLHandleListenBacklog
0x14000475e  jmp     loc_1400046A5
0x140004763  test    r15b, r15b
0x140004766  jz      short loc_140004775
0x140004768  mov     rcx, [rbx+118h]
0x14000476f  add     rcx, 20h ; ' '
0x140004773  jmp     short loc_14000477C
0x140004775  lea     rcx, [rbx+90h]; ListHead
0x14000477c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140004783  nop     dword ptr [rax+rax+00h]
0x140004788  test    rax, rax
0x14000478b  jnz     short loc_14000479F
0x14000478d  mov     eax, [rbx+8]
0x140004790  bt      eax, 9
0x140004794  jnb     loc_1400046AA
0x14000479a  jmp     loc_1400046A5
0x14000479f  add     rax, 0FFFFFFFFFFFFFF50h
0x1400047a5  mov     rbx, [rsp+68h+arg_0]
0x1400047aa  mov     rbp, [rsp+68h+arg_8]
0x1400047af  add     rsp, 40h
0x1400047b3  pop     r15
0x1400047b5  pop     r14
0x1400047b7  pop     r12
0x1400047b9  pop     rdi
0x1400047ba  pop     rsi
0x1400047bb  retn
```
