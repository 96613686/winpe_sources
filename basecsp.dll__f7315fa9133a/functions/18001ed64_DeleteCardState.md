# DeleteCardState

- ea: `0x18001ed64`
- end: `0x18001ee8e`
- name: `DeleteCardState`
- size: `298`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001d470`
- `0x180023ed8`

## callees

- `0x18000c67c`
- `0x18000ccb0`
- `0x18000de80`
- `0x18001d494`
- `0x18001ed64`
- `0x1800282ac`
- `0x18002a798`
- `0x18002bf00`
- `0x18002c920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001edcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001edcd`

## pseudocode

```c
__int64 __fastcall DeleteCardState(struct _CARD_STATE *a1, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD v11[7]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 624);
  v11[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v11[1] = 0;
  if ( *((_DWORD *)a1 + 166) )
  {
    CspEnterCriticalSection(v2);
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v11, v2);
  }
  TransactionManagerForceEndTransaction(a1);
  v11[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v11);
  if ( *((_DWORD *)a1 + 166) )
    DeleteCriticalSection(v2);
  v5 = *((_QWORD *)a1 + 69);
  if ( v5 )
  {
    CspFreeH(v5);
    *((_QWORD *)a1 + 69) = 0;
  }
  v6 = *((_QWORD *)a1 + 71);
  if ( v6 )
  {
    CspFreeH(v6);
    *((_QWORD *)a1 + 71) = 0;
  }
  v7 = *((_QWORD *)a1 + 84);
  if ( v7 )
  {
    ScCacheDeleteCache(v7);
    *((_QWORD *)a1 + 84) = 0;
  }
  v8 = *((_QWORD *)a1 + 85);
  if ( v8 )
  {
    ScCacheDeleteCache(v8);
    *((_QWORD *)a1 + 85) = 0;
  }
  if ( *((_QWORD *)a1 + 1) )
    CleanupCardData((char *)a1 + 8, a2);
  if ( *((_QWORD *)a1 + 2) )
    *((_QWORD *)a1 + 2) = 0;
  v9 = *((_QWORD *)a1 + 76);
  if ( v9 )
  {
    CspFreeH(v9);
    *((_QWORD *)a1 + 76) = 0;
  }
  if ( *((_QWORD *)a1 + 73) )
    PinCacheFlush((char *)a1 + 584, 0, 1);
  return CspFreeH(a1);
}

```

## disassembly

```asm
0x18001ed64  push    rbx
0x18001ed66  push    rbp
0x18001ed67  push    rsi
0x18001ed68  push    rdi
0x18001ed69  push    r14
0x18001ed6b  sub     rsp, 30h
0x18001ed6f  xor     ebp, ebp
0x18001ed71  lea     r14, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001ed78  lea     rdi, [rcx+270h]
0x18001ed7f  mov     esi, edx
0x18001ed81  mov     rbx, rcx
0x18001ed84  mov     [rsp+58h+var_38], r14
0x18001ed89  mov     [rsp+58h+var_30], rbp
0x18001ed8e  cmp     [rcx+298h], ebp
0x18001ed94  jz      short loc_18001EDAB
0x18001ed96  mov     rcx, rdi
0x18001ed99  call    CspEnterCriticalSection
0x18001ed9e  mov     rdx, rdi
0x18001eda1  lea     rcx, [rsp+58h+var_38]
0x18001eda6  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001edab  mov     rcx, rbx; struct _CARD_STATE *
0x18001edae  call    TransactionManagerForceEndTransaction
0x18001edb3  lea     rcx, [rsp+58h+var_38]
0x18001edb8  mov     [rsp+58h+var_38], r14
0x18001edbd  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001edc2  cmp     [rbx+298h], ebp
0x18001edc8  jz      short loc_18001EDD3
0x18001edca  mov     rcx, rdi; lpCriticalSection
0x18001edcd  call    cs:__imp_DeleteCriticalSection
0x18001edd3  mov     rcx, [rbx+228h]
0x18001edda  test    rcx, rcx
0x18001eddd  jz      short loc_18001EDEB
0x18001eddf  call    CspFreeH
0x18001ede4  mov     [rbx+228h], rbp
0x18001edeb  mov     rcx, [rbx+238h]
0x18001edf2  test    rcx, rcx
0x18001edf5  jz      short loc_18001EE03
0x18001edf7  call    CspFreeH
0x18001edfc  mov     [rbx+238h], rbp
0x18001ee03  mov     rcx, [rbx+2A0h]
0x18001ee0a  test    rcx, rcx
0x18001ee0d  jz      short loc_18001EE1B
0x18001ee0f  call    ScCacheDeleteCache
0x18001ee14  mov     [rbx+2A0h], rbp
0x18001ee1b  mov     rcx, [rbx+2A8h]
0x18001ee22  test    rcx, rcx
0x18001ee25  jz      short loc_18001EE33
0x18001ee27  call    ScCacheDeleteCache
0x18001ee2c  mov     [rbx+2A8h], rbp
0x18001ee33  lea     rcx, [rbx+8]
0x18001ee37  cmp     [rcx], rbp
0x18001ee3a  jz      short loc_18001EE43
0x18001ee3c  mov     edx, esi
0x18001ee3e  call    CleanupCardData
0x18001ee43  cmp     [rbx+10h], rbp
0x18001ee47  jz      short loc_18001EE4D
0x18001ee49  mov     [rbx+10h], rbp
0x18001ee4d  mov     rcx, [rbx+260h]
0x18001ee54  test    rcx, rcx
0x18001ee57  jz      short loc_18001EE65
0x18001ee59  call    CspFreeH
0x18001ee5e  mov     [rbx+260h], rbp
0x18001ee65  lea     rcx, [rbx+248h]
0x18001ee6c  cmp     [rcx], rbp
0x18001ee6f  jz      short loc_18001EE7C
0x18001ee71  xor     edx, edx
0x18001ee73  lea     r8d, [rdx+1]
0x18001ee77  call    PinCacheFlush
0x18001ee7c  mov     rcx, rbx
0x18001ee7f  add     rsp, 30h
0x18001ee83  pop     r14
0x18001ee85  pop     rdi
0x18001ee86  pop     rsi
0x18001ee87  pop     rbp
0x18001ee88  pop     rbx
0x18001ee89  jmp     CspFreeH
```
