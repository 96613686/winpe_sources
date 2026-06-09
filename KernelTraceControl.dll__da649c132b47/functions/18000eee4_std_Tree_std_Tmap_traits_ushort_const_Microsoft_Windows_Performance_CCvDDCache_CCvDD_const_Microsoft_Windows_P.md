# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> const &)

- ea: `0x18000eee4`
- end: `0x18000efee`
- name: `?insert@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@_N@2@AEBU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@2@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e058`

## callees

- `0x18000ebf4`
- `0x18000eee4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ef1c`
- `msvcrt!_wcsicmp` at `0x18000efbc`
- `msvcrt!_wcsicmp` at `0x18000ef1c`
- `msvcrt!_wcsicmp` at `0x18000efbc`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(
        __int64 a1,
        __int64 a2,
        const wchar_t **a3)
{
  __int64 *v3; // rdi
  bool v7; // r14
  __int64 v8; // rbx
  int v9; // eax
  __int64 *v10; // rbx
  char v11; // r8
  __int64 *v12; // rax
  __int64 v13; // rax
  __int64 i; // rax
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(__int64 **)(a1 + 8);
  v7 = 1;
  v8 = v3[1];
  while ( !*(_BYTE *)(v8 + 41) )
  {
    v3 = (__int64 *)v8;
    v9 = _wcsicmp(*a3, *(const wchar_t **)(v8 + 24));
    v7 = v9 < 0;
    if ( v9 >= 0 )
      v8 = *(_QWORD *)(v8 + 16);
    else
      v8 = *(_QWORD *)v8;
  }
  v10 = v3;
  if ( v7 )
  {
    if ( v3 == **(__int64 ***)(a1 + 8) )
    {
      v11 = 1;
      goto LABEL_9;
    }
    if ( *((_BYTE *)v3 + 41) )
    {
      v10 = (__int64 *)v3[2];
    }
    else
    {
      v13 = *v3;
      if ( *(_BYTE *)(*v3 + 41) )
      {
        for ( i = v3[1]; !*(_BYTE *)(i + 41) && v10 == *(__int64 **)i; i = *(_QWORD *)(i + 8) )
          v10 = (__int64 *)i;
        if ( !*((_BYTE *)v10 + 41) )
          v10 = (__int64 *)i;
      }
      else
      {
        do
        {
          v10 = (__int64 *)v13;
          v13 = *(_QWORD *)(v13 + 16);
        }
        while ( !*(_BYTE *)(v13 + 41) );
      }
    }
  }
  if ( _wcsicmp((const wchar_t *)v10[3], *a3) >= 0 )
  {
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
    return a2;
  }
  v11 = v7;
LABEL_9:
  v12 = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(
          a1,
          &v16,
          v11,
          v3,
          (__int64)a3);
  *(_BYTE *)(a2 + 8) = 1;
  *(_QWORD *)a2 = *v12;
  return a2;
}

```

## disassembly

```asm
0x18000eee4  mov     [rsp+arg_8], rbx
0x18000eee9  mov     [rsp+arg_10], rbp
0x18000eeee  mov     [rsp+arg_18], rsi
0x18000eef3  push    rdi
0x18000eef4  push    r14
0x18000eef6  push    r15
0x18000eef8  sub     rsp, 30h
0x18000eefc  mov     rdi, [rcx+8]
0x18000ef00  mov     r15, r8
0x18000ef03  mov     rsi, rdx
0x18000ef06  mov     rbp, rcx
0x18000ef09  mov     r14b, 1
0x18000ef0c  mov     rbx, [rdi+8]
0x18000ef10  jmp     short loc_18000EF36
0x18000ef12  mov     rdx, [rbx+18h]; String2
0x18000ef16  mov     rdi, rbx
0x18000ef19  mov     rcx, [r15]; String1
0x18000ef1c  call    cs:__imp__wcsicmp
0x18000ef22  test    eax, eax
0x18000ef24  sets    r14b
0x18000ef28  test    r14b, r14b
0x18000ef2b  jz      short loc_18000EF32
0x18000ef2d  mov     rbx, [rbx]
0x18000ef30  jmp     short loc_18000EF36
0x18000ef32  mov     rbx, [rbx+10h]
0x18000ef36  cmp     byte ptr [rbx+29h], 0
0x18000ef3a  jz      short loc_18000EF12
0x18000ef3c  mov     rbx, rdi
0x18000ef3f  test    r14b, r14b
0x18000ef42  jz      short loc_18000EFB5
0x18000ef44  mov     rax, [rbp+8]
0x18000ef48  cmp     rdi, [rax]
0x18000ef4b  jnz     short loc_18000EF71
0x18000ef4d  mov     r8b, 1
0x18000ef50  mov     r9, rdi
0x18000ef53  mov     [rsp+48h+var_28], r15
0x18000ef58  lea     rdx, [rsp+48h+arg_0]
0x18000ef5d  mov     rcx, rbp
0x18000ef60  call    ?_Insert@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &)
0x18000ef65  mov     byte ptr [rsi+8], 1
0x18000ef69  mov     rcx, [rax]
0x18000ef6c  mov     [rsi], rcx
0x18000ef6f  jmp     short loc_18000EFD2
0x18000ef71  cmp     byte ptr [rdi+29h], 0
0x18000ef75  jz      short loc_18000EF7D
0x18000ef77  mov     rbx, [rdi+10h]
0x18000ef7b  jmp     short loc_18000EFB5
0x18000ef7d  mov     rax, [rdi]
0x18000ef80  cmp     byte ptr [rax+29h], 0
0x18000ef84  jnz     short loc_18000EF95
0x18000ef86  mov     rbx, rax
0x18000ef89  mov     rax, [rax+10h]
0x18000ef8d  cmp     byte ptr [rax+29h], 0
0x18000ef91  jz      short loc_18000EF86
0x18000ef93  jmp     short loc_18000EFB5
0x18000ef95  mov     rax, [rdi+8]
0x18000ef99  jmp     short loc_18000EFA7
0x18000ef9b  cmp     rbx, [rax]
0x18000ef9e  jnz     short loc_18000EFAD
0x18000efa0  mov     rbx, rax
0x18000efa3  mov     rax, [rax+8]
0x18000efa7  cmp     byte ptr [rax+29h], 0
0x18000efab  jz      short loc_18000EF9B
0x18000efad  cmp     byte ptr [rbx+29h], 0
0x18000efb1  cmovz   rbx, rax
0x18000efb5  mov     rdx, [r15]; String2
0x18000efb8  mov     rcx, [rbx+18h]; String1
0x18000efbc  call    cs:__imp__wcsicmp
0x18000efc2  test    eax, eax
0x18000efc4  jns     short loc_18000EFCB
0x18000efc6  mov     r8b, r14b
0x18000efc9  jmp     short loc_18000EF50
0x18000efcb  mov     [rsi], rbx
0x18000efce  mov     byte ptr [rsi+8], 0
0x18000efd2  mov     rbx, [rsp+48h+arg_8]
0x18000efd7  mov     rax, rsi
0x18000efda  mov     rsi, [rsp+48h+arg_18]
0x18000efdf  mov     rbp, [rsp+48h+arg_10]
0x18000efe4  add     rsp, 30h
0x18000efe8  pop     r15
0x18000efea  pop     r14
0x18000efec  pop     rdi
0x18000efed  retn
```
