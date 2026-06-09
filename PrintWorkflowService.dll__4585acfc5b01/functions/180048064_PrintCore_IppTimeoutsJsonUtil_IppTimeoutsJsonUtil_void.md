# PrintCore::IppTimeoutsJsonUtil::IppTimeoutsJsonUtil(void)

- ea: `0x180048064`
- end: `0x1800480f6`
- name: `??0IppTimeoutsJsonUtil@PrintCore@@QEAA@XZ`
- size: `146`
- prototype: `__int64 __fastcall(PrintCore::IppTimeoutsJsonUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800496a4`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x18001da30`
- `0x180048064`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800480bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800480bc`

## string_xrefs

- `0x18004809b`: `Windows.Data.Json.JsonValue`
- `0x1800480ce`: `OneCoreUap\Internal\Printscan\inc\IppTimeoutsJsonUtils.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PrintCore::IppTimeoutsJsonUtil *__fastcall PrintCore::IppTimeoutsJsonUtil::IppTimeoutsJsonUtil(
        PrintCore::IppTimeoutsJsonUtil *this)
{
  int ActivationFactory; // eax
  int v4; // [rsp+20h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (int)this;
  *(_QWORD *)this = 0;
  v6 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, this);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\IppTimeoutsJsonUtils.hxx",
      (const char *)(unsigned int)ActivationFactory,
      v4);
  return this;
}

```

## disassembly

```asm
0x180048064  push    rbx
0x180048066  sub     rsp, 50h
0x18004806a  mov     rax, cs:__security_cookie
0x180048071  xor     rax, rsp
0x180048074  mov     [rsp+58h+var_10], rax
0x180048079  mov     rbx, rcx
0x18004807c  mov     qword ptr [rsp+58h+var_38], rcx; int
0x180048081  mov     qword ptr [rcx], 0
0x180048088  mov     [rsp+58h+var_18], 0
0x180048091  mov     r9d, 1Bh; unsigned int
0x180048097  lea     r8d, [r9+1]; unsigned int
0x18004809b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800480a2  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x1800480a7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800480ac  nop
0x1800480ad  mov     r8, rbx
0x1800480b0  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800480b7  mov     rcx, [rsp+58h+var_18]
0x1800480bc  call    cs:__imp_RoGetActivationFactory
0x1800480c2  mov     rcx, [rsp+58h]; this
0x1800480c7  test    eax, eax
0x1800480c9  jns     short loc_1800480E0
0x1800480cb  mov     r9d, eax; char *
0x1800480ce  lea     r8, aOnecoreuapInte_5; "OneCoreUap\\Internal\\Printscan\\inc\\I"...
0x1800480d5  mov     edx, 1Ch; void *
0x1800480da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800480e0  mov     rax, rbx
0x1800480e3  mov     rcx, [rsp+58h+var_10]
0x1800480e8  xor     rcx, rsp; StackCookie
0x1800480eb  call    __security_check_cookie
0x1800480f0  add     rsp, 50h
0x1800480f4  pop     rbx
0x1800480f5  retn
```
