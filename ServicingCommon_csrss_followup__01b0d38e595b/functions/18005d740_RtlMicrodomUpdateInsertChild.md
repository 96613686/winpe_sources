# RtlMicrodomUpdateInsertChild

- ea: `0x18005d740`
- end: `0x18005d8bc`
- name: `RtlMicrodomUpdateInsertChild`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005c360`
- `0x18005c4ec`
- `0x18005d740`

## string_xrefs

- `0x18005d770`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d7b0`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d7dc`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d80d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d83e`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d78e`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005d783`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005d7c3`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005d7ef`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005d820`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005d851`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateInsertChild(
        __int64 a1,
        char a2,
        unsigned int a3,
        __int64 a4,
        struct CChildNode *a5)
{
  const char *v6; // rax
  __int64 result; // rax
  int v8; // edx
  unsigned int v9; // esi
  CElementModification *v10; // rcx
  int inserted; // eax
  unsigned int v12; // ecx
  const char *v13; // [rsp+20h] [rbp-30h] BYREF
  const char *v14; // [rsp+28h] [rbp-28h]
  __int64 v15; // [rsp+30h] [rbp-20h]
  const char *v16; // [rsp+38h] [rbp-18h]
  int v17; // [rsp+40h] [rbp-10h] BYREF

  v17 = 0;
  if ( !a1 )
  {
    v15 = 1772;
    v13 = "onecore\\base\\xml\\udom_modify.cpp";
    v14 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v6 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v16 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v13);
  }
  if ( !a4 )
  {
    v15 = 1773;
    v13 = "onecore\\base\\xml\\udom_modify.cpp";
    v14 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v6 = "pToInsertInto != 0";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v15 = 1774;
    v13 = "onecore\\base\\xml\\udom_modify.cpp";
    v14 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v6 = "pToInsert != 0";
    goto LABEL_3;
  }
  v8 = a2 & 1;
  if ( ((v8 - 1) & v8) != 0 )
  {
    v15 = 1775;
    v13 = "onecore\\base\\xml\\udom_modify.cpp";
    v14 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v6 = "No more than one flag set check failed: Flags";
    goto LABEL_3;
  }
  if ( !*(_QWORD *)(a4 + 40) )
  {
    v15 = 1776;
    v13 = "onecore\\base\\xml\\udom_modify.cpp";
    v14 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v6 = "pToInsertInto->Element != 0";
    goto LABEL_3;
  }
  v9 = -1;
  if ( v8 )
    v9 = a3;
  v10 = *(CElementModification **)(*((_QWORD *)a5 + 7) + 112LL);
  if ( !v10 || (result = CElementModification::RemoveChild(v10, a5), (int)result >= 0) )
  {
    inserted = CElementModification::InsertChild(*(CElementModification **)(a4 + 40), a5, v9);
    v12 = 0;
    if ( inserted < 0 )
      return (unsigned int)inserted;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18005d740  mov     [rsp-18h+arg_8], rbx
0x18005d745  push    rbp
0x18005d746  push    rsi
0x18005d747  push    rdi
0x18005d748  mov     rbp, rsp
0x18005d74b  sub     rsp, 50h
0x18005d74f  mov     rax, cs:__security_cookie
0x18005d756  xor     rax, rsp
0x18005d759  mov     [rbp+var_8], rax
0x18005d75d  mov     rbx, [rbp+arg_20]
0x18005d761  mov     rdi, r9
0x18005d764  mov     [rbp+var_10], 0
0x18005d76b  test    rcx, rcx
0x18005d76e  jnz     short loc_18005D7AB
0x18005d770  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d777  mov     [rbp+var_20], 6ECh
0x18005d77f  mov     [rbp+var_30], rax
0x18005d783  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005d78a  mov     [rbp+var_28], rax
0x18005d78e  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005d795  lea     rdx, [rbp+var_30]
0x18005d799  mov     [rbp+var_18], rax
0x18005d79d  lea     rcx, [rbp+var_10]
0x18005d7a1  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d7a6  jmp     loc_18005D8A2
0x18005d7ab  test    rdi, rdi
0x18005d7ae  jnz     short loc_18005D7D7
0x18005d7b0  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d7b7  mov     [rbp+var_20], 6EDh
0x18005d7bf  mov     [rbp+var_30], rax
0x18005d7c3  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005d7ca  mov     [rbp+var_28], rax
0x18005d7ce  lea     rax, aPtoinsertinto0; "pToInsertInto != 0"
0x18005d7d5  jmp     short loc_18005D795
0x18005d7d7  test    rbx, rbx
0x18005d7da  jnz     short loc_18005D803
0x18005d7dc  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d7e3  mov     [rbp+var_20], 6EEh
0x18005d7eb  mov     [rbp+var_30], rax
0x18005d7ef  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005d7f6  mov     [rbp+var_28], rax
0x18005d7fa  lea     rax, aPtoinsert0; "pToInsert != 0"
0x18005d801  jmp     short loc_18005D795
0x18005d803  and     edx, 1
0x18005d806  lea     eax, [rdx-1]
0x18005d809  test    edx, eax
0x18005d80b  jz      short loc_18005D837
0x18005d80d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d814  mov     [rbp+var_20], 6EFh
0x18005d81c  mov     [rbp+var_30], rax
0x18005d820  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005d827  mov     [rbp+var_28], rax
0x18005d82b  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x18005d832  jmp     loc_18005D795
0x18005d837  cmp     qword ptr [r9+28h], 0
0x18005d83c  jnz     short loc_18005D868
0x18005d83e  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d845  mov     [rbp+var_20], 6F0h
0x18005d84d  mov     [rbp+var_30], rax
0x18005d851  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005d858  mov     [rbp+var_28], rax
0x18005d85c  lea     rax, aPtoinsertintoE; "pToInsertInto->Element != 0"
0x18005d863  jmp     loc_18005D795
0x18005d868  mov     rax, [rbx+38h]
0x18005d86c  or      esi, 0FFFFFFFFh
0x18005d86f  test    edx, edx
0x18005d871  cmovnz  esi, r8d
0x18005d875  mov     rcx, [rax+70h]; this
0x18005d879  test    rcx, rcx
0x18005d87c  jz      short loc_18005D88A
0x18005d87e  mov     rdx, rbx; struct CChildNode *
0x18005d881  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005d886  test    eax, eax
0x18005d888  js      short loc_18005D8A2
0x18005d88a  mov     rcx, [rdi+28h]; this
0x18005d88e  mov     r8d, esi; unsigned int
0x18005d891  mov     rdx, rbx; struct CChildNode *
0x18005d894  call    ?InsertChild@CElementModification@@QEAAJPEAVCChildNode@@K@Z; CElementModification::InsertChild(CChildNode *,ulong)
0x18005d899  xor     ecx, ecx
0x18005d89b  test    eax, eax
0x18005d89d  cmovs   ecx, eax
0x18005d8a0  mov     eax, ecx
0x18005d8a2  mov     rcx, [rbp+var_8]
0x18005d8a6  xor     rcx, rsp; StackCookie
0x18005d8a9  call    __security_check_cookie
0x18005d8ae  mov     rbx, [rsp+50h+arg_8]
0x18005d8b3  add     rsp, 50h
0x18005d8b7  pop     rdi
0x18005d8b8  pop     rsi
0x18005d8b9  pop     rbp
0x18005d8ba  retn
```
