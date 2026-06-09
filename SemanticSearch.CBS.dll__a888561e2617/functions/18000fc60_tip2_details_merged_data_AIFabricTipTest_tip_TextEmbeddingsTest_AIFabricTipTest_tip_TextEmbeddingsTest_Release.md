# tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)

- ea: `0x18000fc60`
- end: `0x18000fcd0`
- name: `?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ`
- size: `112`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a710`
- `0x18000ac90`
- `0x18000afa0`
- `0x18000b2a0`
- `0x18000cf50`
- `0x18001bcf0`
- `0x180033f70`
- `0x180034400`
- `0x1800353b0`

## callees

- `0x18000fc60`
- `0x180010910`
- `0x180010e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcb8`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 66);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable';
    if ( *((_QWORD *)pv + 30) && (pv[7] & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(pv + 2), 4u);
    tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>((__int64)(pv + 2));
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000fc60  mov     [rsp+arg_8], rbx
0x18000fc65  push    rdi
0x18000fc66  sub     rsp, 20h
0x18000fc6a  mov     rdi, rcx
0x18000fc6d  mov     ebx, 0FFFFFFFFh
0x18000fc72  lock xadd [rcx+108h], ebx
0x18000fc7a  sub     ebx, 1
0x18000fc7d  jnz     short loc_18000FCC3
0x18000fc7f  lea     rax, ??_7?$merged_data@U_tip_ImageEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable'
0x18000fc86  mov     [rsp+28h+arg_0], rsi
0x18000fc8b  mov     [rcx], rax
0x18000fc8e  cmp     qword ptr [rcx+0F0h], 0
0x18000fc96  jz      short loc_18000FCAC
0x18000fc98  test    byte ptr [rcx+1Ch], 1
0x18000fc9c  jnz     short loc_18000FCAC
0x18000fc9e  mov     edx, 4
0x18000fca3  add     rcx, 8
0x18000fca7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000fcac  lea     rcx, [rdi+8]
0x18000fcb0  call    ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
0x18000fcb5  mov     rcx, rdi; pv
0x18000fcb8  call    cs:__imp_CoTaskMemFree
0x18000fcbe  mov     rsi, [rsp+28h+arg_0]
0x18000fcc3  mov     eax, ebx
0x18000fcc5  mov     rbx, [rsp+28h+arg_8]
0x18000fcca  add     rsp, 20h
0x18000fcce  pop     rdi
0x18000fccf  retn
```
