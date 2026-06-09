# Broker::BILayer::EnumerateUserContexts(void)

- ea: `0x18000d700`
- end: `0x18000d816`
- name: `?EnumerateUserContexts@BILayer@Broker@@YA?AV?$vector@_KV?$allocator@_K@std@@@std@@XZ`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180009e94`
- `0x18000d700`
- `0x18000d81c`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiEnumerateUserContexts` at `0x18000d74e`
- `api-ms-win-core-bicltapi-l1-1-6!BiEnumerateUserContexts` at `0x18000d74e`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000d804`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x18000d804`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Broker::BILayer::EnumerateUserContexts(_QWORD *a1)
{
  int v2; // eax
  int v3; // edi
  void **pExceptionObject; // [rsp+28h] [rbp-28h] BYREF
  __int128 v6; // [rsp+30h] [rbp-20h]
  int v7; // [rsp+40h] [rbp-10h]
  int v8; // [rsp+48h] [rbp-8h]
  unsigned int v9; // [rsp+78h] [rbp+28h] BYREF
  __int64 v10; // [rsp+80h] [rbp+30h] BYREF

  v10 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v9 = 0;
  v2 = BiEnumerateUserContexts(&v9, &v10);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v2);
    v6 = 0;
    v7 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v8 = v3;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  std::vector<unsigned __int64>::_Insert_counted_range<unsigned __int64 *>(a1, a1[1], v10, (8LL * v9) >> 3);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v9);
  if ( v10 )
    BiFreeMemory();
  return a1;
}

```

## disassembly

```asm
0x18000d700  mov     [rsp-18h+arg_0], rcx
0x18000d705  push    rbp
0x18000d706  push    rbx
0x18000d707  push    rdi
0x18000d708  mov     rbp, rsp
0x18000d70b  sub     rsp, 50h
0x18000d70f  mov     rbx, rcx
0x18000d712  mov     [rbp+var_30], 0
0x18000d719  mov     [rbp+arg_10], 0
0x18000d721  mov     qword ptr [rcx], 0
0x18000d728  mov     qword ptr [rcx+8], 0
0x18000d730  mov     qword ptr [rcx+10h], 0
0x18000d738  mov     [rbp+var_30], 1
0x18000d73f  mov     [rbp+arg_8], 0
0x18000d746  lea     rdx, [rbp+arg_10]
0x18000d74a  lea     rcx, [rbp+arg_8]
0x18000d74e  call    cs:__imp_BiEnumerateUserContexts
0x18000d754  mov     edi, eax
0x18000d756  test    eax, eax
0x18000d758  jns     short loc_18000D7B2
0x18000d75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d761  test    byte ptr [rcx+1Ch], 1
0x18000d765  jz      short loc_18000D785
0x18000d767  cmp     byte ptr [rcx+19h], 2
0x18000d76b  jb      short loc_18000D785
0x18000d76d  mov     edx, 21h ; '!'
0x18000d772  mov     r9d, eax
0x18000d775  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000d77c  mov     rcx, [rcx+10h]
0x18000d780  call    WPP_SF_d
0x18000d785  xorps   xmm0, xmm0
0x18000d788  movups  [rbp+var_20], xmm0
0x18000d78c  mov     [rbp+var_10], 6
0x18000d793  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18000d79a  mov     [rbp+pExceptionObject], rax
0x18000d79e  mov     [rbp+var_8], edi
0x18000d7a1  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18000d7a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d7ac  call    _CxxThrowException_0
0x18000d7b2  mov     r8, [rbp+arg_10]
0x18000d7b6  mov     r9d, [rbp+arg_8]
0x18000d7ba  shl     r9, 3
0x18000d7be  sar     r9, 3
0x18000d7c2  mov     rdx, [rbx+8]
0x18000d7c6  mov     rcx, rbx
0x18000d7c9  call    ??$_Insert_counted_range@PEA_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_K@std@@@std@@@1@PEA_K_K@Z; std::vector<unsigned __int64>::_Insert_counted_range<unsigned __int64 *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned __int64>>>,unsigned __int64 *,unsigned __int64)
0x18000d7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7d5  test    byte ptr [rcx+1Ch], 1
0x18000d7d9  jz      short loc_18000D7FB
0x18000d7db  cmp     byte ptr [rcx+19h], 5
0x18000d7df  jb      short loc_18000D7FB
0x18000d7e1  mov     edx, 22h ; '"'
0x18000d7e6  mov     r9d, [rbp+arg_8]
0x18000d7ea  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000d7f1  mov     rcx, [rcx+10h]
0x18000d7f5  call    WPP_SF_d
0x18000d7fa  nop
0x18000d7fb  mov     rcx, [rbp+arg_10]
0x18000d7ff  test    rcx, rcx
0x18000d802  jz      short loc_18000D80A
0x18000d804  call    cs:__imp_BiFreeMemory
0x18000d80a  mov     rax, rbx
0x18000d80d  add     rsp, 50h
0x18000d811  pop     rdi
0x18000d812  pop     rbx
0x18000d813  pop     rbp
0x18000d814  retn
```
