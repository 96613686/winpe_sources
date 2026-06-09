# _anonymous_namespace_::AddVariantContent

- ea: `0x18003b65c`
- end: `0x18003b73b`
- name: `_anonymous_namespace_::AddVariantContent`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800774d4`

## callees

- `0x180012bc4`
- `0x180031540`
- `0x180037c5c`
- `0x18003b65c`
- `0x18003b7a8`
- `0x180068514`
- `0x180077cc4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18003b6cd`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b6cd`

## string_xrefs

- `0x18003b710`: `onecore\windows\accessibletech\uiamanager\dll\protobufhelper.cpp`
- `0x18003b69d`: `onecore\windows\accessibletech\uiamanager\dll\namedpipeservices.cpp`

## pseudocode

```c
void __fastcall anonymous_namespace_::AddVariantContent(UiaManagerProto::VariantMsg *a1, __int64 a2)
{
  OLECHAR *v2; // rdi
  struct UiaManagerProto::WstringMsg *v3; // rbx
  unsigned __int64 v4; // rax
  int v5; // edx
  _QWORD *v6; // r8
  int v7; // [rsp+20h] [rbp-18h]
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_WORD *)a2 )
  {
    switch ( *(_WORD *)a2 )
    {
      case 3:
        UiaManagerProto::VariantMsg::_internal_set_int_payload(a1, *(_DWORD *)(a2 + 8));
        break;
      case 8:
        v2 = *(OLECHAR **)(a2 + 8);
        v3 = UiaManagerProto::VariantMsg::_internal_mutable_string_payload(a1);
        v4 = 2LL * SysStringLen(v2);
        if ( v4 > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\protobufhelper.cpp",
            (const char *)0x80070216LL,
            v7);
        v6 = (_QWORD *)(*((_QWORD *)v3 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (*((_BYTE *)v3 + 8) & 1) != 0 )
          v6 = (_QWORD *)*v6;
        LOBYTE(v5) = 0;
        google::protobuf::internal::ArenaStringPtr::SetBytes<google::protobuf::internal::ArenaStringPtr::EmptyDefault>(
          (_DWORD)v3 + 16,
          v5,
          (_DWORD)v2,
          v4,
          (__int64)v6);
        break;
      case 0xB:
        UiaManagerProto::VariantMsg::_internal_set_bool_payload(a1, *(_WORD *)(a2 + 8) == 0xFFFF);
        break;
      default:
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipeservices.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Trying to serialize an unsupported VARIANT type",
          v8);
    }
  }
}

```

## disassembly

```asm
0x18003b65c  mov     [rsp+arg_0], rbx
0x18003b661  push    rdi
0x18003b662  sub     rsp, 30h
0x18003b666  cmp     word ptr [rdx], 0
0x18003b66a  jz      loc_18003B730
0x18003b670  cmp     word ptr [rdx], 3
0x18003b674  jz      loc_18003B728
0x18003b67a  cmp     word ptr [rdx], 8
0x18003b67e  jz      short loc_18003B6BE
0x18003b680  cmp     word ptr [rdx], 0Bh
0x18003b684  jz      short loc_18003B6AF
0x18003b686  mov     rcx, [rsp+38h]; this
0x18003b68b  lea     rax, aTryingToSerial; "Trying to serialize an unsupported VARI"...
0x18003b692  mov     r9d, 8000FFFFh; char *
0x18003b698  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003b69d  lea     r8, aOnecoreWindows; "onecore\\windows\\accessibletech\\uiama"...
0x18003b6a4  mov     edx, 28h ; '('; void *
0x18003b6a9  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b6af  cmp     word ptr [rdx+8], 0FFFFh
0x18003b6b4  setz    dl; bool
0x18003b6b7  call    ?_internal_set_bool_payload@VariantMsg@UiaManagerProto@@AEAAX_N@Z; UiaManagerProto::VariantMsg::_internal_set_bool_payload(bool)
0x18003b6bc  jmp     short loc_18003B730
0x18003b6be  mov     rdi, [rdx+8]
0x18003b6c2  call    ?_internal_mutable_string_payload@VariantMsg@UiaManagerProto@@AEAAPEAVWstringMsg@2@XZ; UiaManagerProto::VariantMsg::_internal_mutable_string_payload(void)
0x18003b6c7  mov     rcx, rdi; pbstr
0x18003b6ca  mov     rbx, rax
0x18003b6cd  call    cs:__imp_SysStringLen
0x18003b6d3  mov     eax, eax
0x18003b6d5  mov     ecx, 0FFFFFFFFh
0x18003b6da  add     rax, rax
0x18003b6dd  cmp     rax, rcx
0x18003b6e0  ja      short loc_18003B70B
0x18003b6e2  mov     r8, [rbx+8]
0x18003b6e6  and     r8, 0FFFFFFFFFFFFFFFCh
0x18003b6ea  test    byte ptr [rbx+8], 1
0x18003b6ee  jz      short loc_18003B6F3
0x18003b6f0  mov     r8, [r8]
0x18003b6f3  mov     qword ptr [rsp+38h+var_18], r8
0x18003b6f8  lea     rcx, [rbx+10h]
0x18003b6fc  mov     r8, rdi
0x18003b6ff  mov     r9d, eax
0x18003b702  xor     dl, dl
0x18003b704  call    ??$SetBytes@UEmptyDefault@ArenaStringPtr@internal@protobuf@google@@@ArenaStringPtr@internal@protobuf@google@@QEAAXUEmptyDefault@0123@PEBX_KPEAVArena@23@@Z; google::protobuf::internal::ArenaStringPtr::SetBytes<google::protobuf::internal::ArenaStringPtr::EmptyDefault>(google::protobuf::internal::ArenaStringPtr::EmptyDefault,void const *,unsigned __int64,google::protobuf::Arena *)
0x18003b709  jmp     short loc_18003B730
0x18003b70b  mov     rcx, [rsp+38h]; this
0x18003b710  lea     r8, aOnecoreWindows_26; "onecore\\windows\\accessibletech\\uiama"...
0x18003b717  mov     r9d, 80070216h; char *
0x18003b71d  mov     edx, 34h ; '4'; void *
0x18003b722  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b728  mov     edx, [rdx+8]; int
0x18003b72b  call    ?_internal_set_int_payload@VariantMsg@UiaManagerProto@@AEAAXH@Z; UiaManagerProto::VariantMsg::_internal_set_int_payload(int)
0x18003b730  mov     rbx, [rsp+38h+arg_0]
0x18003b735  add     rsp, 30h
0x18003b739  pop     rdi
0x18003b73a  retn
```
