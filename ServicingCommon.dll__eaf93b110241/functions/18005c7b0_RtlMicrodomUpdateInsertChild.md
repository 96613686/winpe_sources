# RtlMicrodomUpdateInsertChild

- ea: `0x18005c7b0`
- end: `0x18005c92c`
- name: `RtlMicrodomUpdateInsertChild`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18005b3f0`
- `0x18005b57c`
- `0x18005c7b0`

## string_xrefs

- `0x18005c7e0`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c820`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c84c`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c87d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c8ae`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c7fe`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005c7f3`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005c833`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005c85f`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005c890`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18005c8c1`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`

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
0x18005c7b0  mov     [rsp-18h+arg_8], rbx
0x18005c7b5  push    rbp
0x18005c7b6  push    rsi
0x18005c7b7  push    rdi
0x18005c7b8  mov     rbp, rsp
0x18005c7bb  sub     rsp, 50h
0x18005c7bf  mov     rax, cs:__security_cookie
0x18005c7c6  xor     rax, rsp
0x18005c7c9  mov     [rbp+var_8], rax
0x18005c7cd  mov     rbx, [rbp+arg_20]
0x18005c7d1  mov     rdi, r9
0x18005c7d4  mov     [rbp+var_10], 0
0x18005c7db  test    rcx, rcx
0x18005c7de  jnz     short loc_18005C81B
0x18005c7e0  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c7e7  mov     [rbp+var_20], 6ECh
0x18005c7ef  mov     [rbp+var_30], rax
0x18005c7f3  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c7fa  mov     [rbp+var_28], rax
0x18005c7fe  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005c805  lea     rdx, [rbp+var_30]
0x18005c809  mov     [rbp+var_18], rax
0x18005c80d  lea     rcx, [rbp+var_10]
0x18005c811  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c816  jmp     loc_18005C912
0x18005c81b  test    rdi, rdi
0x18005c81e  jnz     short loc_18005C847
0x18005c820  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c827  mov     [rbp+var_20], 6EDh
0x18005c82f  mov     [rbp+var_30], rax
0x18005c833  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c83a  mov     [rbp+var_28], rax
0x18005c83e  lea     rax, aPtoinsertinto0; "pToInsertInto != 0"
0x18005c845  jmp     short loc_18005C805
0x18005c847  test    rbx, rbx
0x18005c84a  jnz     short loc_18005C873
0x18005c84c  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c853  mov     [rbp+var_20], 6EEh
0x18005c85b  mov     [rbp+var_30], rax
0x18005c85f  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c866  mov     [rbp+var_28], rax
0x18005c86a  lea     rax, aPtoinsert0; "pToInsert != 0"
0x18005c871  jmp     short loc_18005C805
0x18005c873  and     edx, 1
0x18005c876  lea     eax, [rdx-1]
0x18005c879  test    edx, eax
0x18005c87b  jz      short loc_18005C8A7
0x18005c87d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c884  mov     [rbp+var_20], 6EFh
0x18005c88c  mov     [rbp+var_30], rax
0x18005c890  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c897  mov     [rbp+var_28], rax
0x18005c89b  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x18005c8a2  jmp     loc_18005C805
0x18005c8a7  cmp     qword ptr [r9+28h], 0
0x18005c8ac  jnz     short loc_18005C8D8
0x18005c8ae  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c8b5  mov     [rbp+var_20], 6F0h
0x18005c8bd  mov     [rbp+var_30], rax
0x18005c8c1  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c8c8  mov     [rbp+var_28], rax
0x18005c8cc  lea     rax, aPtoinsertintoE; "pToInsertInto->Element != 0"
0x18005c8d3  jmp     loc_18005C805
0x18005c8d8  mov     rax, [rbx+38h]
0x18005c8dc  or      esi, 0FFFFFFFFh
0x18005c8df  test    edx, edx
0x18005c8e1  cmovnz  esi, r8d
0x18005c8e5  mov     rcx, [rax+70h]; this
0x18005c8e9  test    rcx, rcx
0x18005c8ec  jz      short loc_18005C8FA
0x18005c8ee  mov     rdx, rbx; struct CChildNode *
0x18005c8f1  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005c8f6  test    eax, eax
0x18005c8f8  js      short loc_18005C912
0x18005c8fa  mov     rcx, [rdi+28h]; this
0x18005c8fe  mov     r8d, esi; unsigned int
0x18005c901  mov     rdx, rbx; struct CChildNode *
0x18005c904  call    ?InsertChild@CElementModification@@QEAAJPEAVCChildNode@@K@Z; CElementModification::InsertChild(CChildNode *,ulong)
0x18005c909  xor     ecx, ecx
0x18005c90b  test    eax, eax
0x18005c90d  cmovs   ecx, eax
0x18005c910  mov     eax, ecx
0x18005c912  mov     rcx, [rbp+var_8]
0x18005c916  xor     rcx, rsp; StackCookie
0x18005c919  call    __security_check_cookie
0x18005c91e  mov     rbx, [rsp+50h+arg_8]
0x18005c923  add     rsp, 50h
0x18005c927  pop     rdi
0x18005c928  pop     rsi
0x18005c929  pop     rbp
0x18005c92a  retn
```
