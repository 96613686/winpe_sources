# Broker::BILayer::EnumerateEventIds(_GUID const &)

- ea: `0x180013ac8`
- end: `0x180013be8`
- name: `?EnumerateEventIds@BILayer@Broker@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBU_GUID@@@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011cd4`

## callees

- `0x180009e94`
- `0x180011f5c`
- `0x180013ac8`
- `0x1800165da`
- `0x18001a070`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiEnumerateBrokeredEvents` at `0x180013b1c`
- `api-ms-win-core-bicltapi-l1-1-6!BiEnumerateBrokeredEvents` at `0x180013b1c`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180013bd6`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180013bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Broker::BILayer::EnumerateEventIds(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  int v4; // edi
  void **pExceptionObject; // [rsp+38h] [rbp-28h] BYREF
  __int128 v7; // [rsp+40h] [rbp-20h]
  int v8; // [rsp+50h] [rbp-10h]
  int v9; // [rsp+58h] [rbp-8h]
  unsigned int v10; // [rsp+90h] [rbp+30h] BYREF
  __int64 v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = 0;
  v11 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = BiEnumerateBrokeredEvents(a2, &v10, &v11);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v3);
    v7 = 0;
    v8 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v9 = v4;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  std::vector<_GUID>::_Insert_counted_range<_GUID *>(a1, a1[1], v11, (16LL * v10) >> 4);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v10, v4);
  if ( v11 )
    BiFreeMemory();
  return a1;
}

```

## disassembly

```asm
0x180013ac8  mov     [rsp-18h+arg_0], rcx
0x180013acd  push    rbp
0x180013ace  push    rbx
0x180013acf  push    rdi
0x180013ad0  mov     rbp, rsp
0x180013ad3  sub     rsp, 60h
0x180013ad7  mov     rax, rdx
0x180013ada  mov     rbx, rcx
0x180013add  mov     [rbp+var_30], 0
0x180013ae4  mov     [rbp+arg_10], 0
0x180013aeb  mov     [rbp+arg_18], 0
0x180013af3  mov     qword ptr [rcx], 0
0x180013afa  mov     qword ptr [rcx+8], 0
0x180013b02  mov     qword ptr [rcx+10h], 0
0x180013b0a  mov     [rbp+var_30], 1
0x180013b11  lea     r8, [rbp+arg_18]
0x180013b15  lea     rdx, [rbp+arg_10]
0x180013b19  mov     rcx, rax
0x180013b1c  call    cs:__imp_BiEnumerateBrokeredEvents
0x180013b22  mov     edi, eax
0x180013b24  test    eax, eax
0x180013b26  jns     short loc_180013B80
0x180013b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b2f  test    byte ptr [rcx+1Ch], 1
0x180013b33  jz      short loc_180013B53
0x180013b35  cmp     byte ptr [rcx+19h], 2
0x180013b39  jb      short loc_180013B53
0x180013b3b  mov     edx, 0Eh
0x180013b40  mov     r9d, eax
0x180013b43  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180013b4a  mov     rcx, [rcx+10h]
0x180013b4e  call    WPP_SF_d
0x180013b53  xorps   xmm0, xmm0
0x180013b56  movups  [rbp+var_20], xmm0
0x180013b5a  mov     [rbp+var_10], 6
0x180013b61  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180013b68  mov     [rbp+pExceptionObject], rax
0x180013b6c  mov     [rbp+var_8], edi
0x180013b6f  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180013b76  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013b7a  call    _CxxThrowException_0
0x180013b80  mov     r8, [rbp+arg_18]
0x180013b84  mov     r9d, [rbp+arg_10]
0x180013b88  shl     r9, 4
0x180013b8c  sar     r9, 4
0x180013b90  mov     rdx, [rbx+8]
0x180013b94  mov     rcx, rbx
0x180013b97  call    ??$_Insert_counted_range@PEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@1@PEAU_GUID@@_K@Z; std::vector<_GUID>::_Insert_counted_range<_GUID *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,_GUID *,unsigned __int64)
0x180013b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ba3  test    byte ptr [rcx+1Ch], 1
0x180013ba7  jz      short loc_180013BCD
0x180013ba9  cmp     byte ptr [rcx+19h], 5
0x180013bad  jb      short loc_180013BCD
0x180013baf  mov     edx, 0Fh
0x180013bb4  mov     [rsp+60h+var_40], edi
0x180013bb8  mov     r9d, [rbp+arg_10]
0x180013bbc  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180013bc3  mov     rcx, [rcx+10h]
0x180013bc7  call    WPP_SF_dd
0x180013bcc  nop
0x180013bcd  mov     rcx, [rbp+arg_18]
0x180013bd1  test    rcx, rcx
0x180013bd4  jz      short loc_180013BDC
0x180013bd6  call    cs:__imp_BiFreeMemory
0x180013bdc  mov     rax, rbx
0x180013bdf  add     rsp, 60h
0x180013be3  pop     rdi
0x180013be4  pop     rbx
0x180013be5  pop     rbp
0x180013be6  retn
```
