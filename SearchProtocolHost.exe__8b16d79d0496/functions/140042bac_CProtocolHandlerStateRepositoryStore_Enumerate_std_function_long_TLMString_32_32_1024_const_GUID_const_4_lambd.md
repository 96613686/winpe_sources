# `CProtocolHandlerStateRepositoryStore::Enumerate(std::function<long (TLMString<32,32,1024> const &,_GUID &)> const &)'::`4'::_lambda_1_::operator()(wchar_t const *,wchar_t const *)

- ea: `0x140042bac`
- end: `0x140042c87`
- name: `??R_lambda_1_@?3??Enumerate@CProtocolHandlerStateRepositoryStore@@EEAAJAEBV?$function@$$A6AJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@AEAU_GUID@@@Z@std@@@Z@QEBAJPEB_W1@Z`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const OLECHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140044c00`

## callees

- `0x140005240`
- `0x14000ca80`
- `0x14000e97c`
- `0x1400317a8`
- `0x140042bac`
- `0x140042dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140042bec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140042bec`

## string_xrefs

- `0x140042c01`: `onecoreuap\base\appmodel\search\searchprotocolhost\prothndlr.cxx`
- `0x140042c41`: `onecoreuap\base\appmodel\search\searchprotocolhost\prothndlr.cxx`

## pseudocode

```c
__int64 __fastcall `CProtocolHandlerStateRepositoryStore::Enumerate'::`4'::_lambda_1_::operator()(
        _QWORD *a1,
        __int64 a2,
        const OLECHAR *a3)
{
  HRESULT v5; // eax
  int v6; // eax
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-98h]
  GUID pclsid; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v10[96]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  pclsid = 0;
  v5 = CLSIDFromString(a3, &pclsid);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
        (const char *)(unsigned int)v5,
        v8);
    TLMString<32,32,1024>::TLMString<32,32,1024>(v10, a2);
    v6 = std::_Func_class<long,TLMString<32,32,1024> const &,_GUID &>::operator()(*a1, v10, &pclsid);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
        (const char *)(unsigned int)v6,
        v8);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v10);
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      272,
      "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx");
  }
  return result;
}

```

## disassembly

```asm
0x140042bac  mov     rax, rsp
0x140042baf  push    rdi
0x140042bb0  sub     rsp, 0B0h
0x140042bb7  mov     [rsp+0B8h+var_90], 0FFFFFFFFFFFFFFFEh
0x140042bc0  mov     [rax+20h], rbx
0x140042bc4  mov     rax, cs:__security_cookie
0x140042bcb  xor     rax, rsp
0x140042bce  mov     [rsp+0B8h+var_18], rax
0x140042bd6  mov     rbx, rdx
0x140042bd9  mov     rdi, rcx
0x140042bdc  xorps   xmm0, xmm0
0x140042bdf  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x140042be4  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x140042be9  mov     rcx, r8; lpsz
0x140042bec  call    cs:__imp_CLSIDFromString
0x140042bf2  mov     rcx, [rsp+0B8h]; this
0x140042bfa  test    eax, eax
0x140042bfc  jns     short loc_140042C12
0x140042bfe  mov     r9d, eax; char *
0x140042c01  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042c08  mov     edx, 110h; void *
0x140042c0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140042c12  mov     rdx, rbx
0x140042c15  lea     rcx, [rsp+0B8h+var_78]
0x140042c1a  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x140042c1f  nop
0x140042c20  lea     r8, [rsp+0B8h+pclsid]
0x140042c25  lea     rdx, [rsp+0B8h+var_78]
0x140042c2a  mov     rcx, [rdi]
0x140042c2d  call    ??R?$_Func_class@JAEBV?$TLMString@$0CA@$0CA@$0EAA@@@AEAU_GUID@@@std@@QEBAJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@AEAU_GUID@@@Z; std::_Func_class<long,TLMString<32,32,1024> const &,_GUID &>::operator()(TLMString<32,32,1024> const &,_GUID &)
0x140042c32  mov     rcx, [rsp+0B8h]; this
0x140042c3a  test    eax, eax
0x140042c3c  jns     short loc_140042C53
0x140042c3e  mov     r9d, eax; char *
0x140042c41  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042c48  mov     edx, 110h; void *
0x140042c4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140042c53  lea     rcx, [rsp+0B8h+var_78]
0x140042c58  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x140042c5d  nop
0x140042c5e  xor     eax, eax
0x140042c60  jmp     short loc_140042C66
0x140042c62  mov     eax, [rsp+0B8h+var_98]
0x140042c66  mov     rcx, [rsp+0B8h+var_18]
0x140042c6e  xor     rcx, rsp; StackCookie
0x140042c71  call    __security_check_cookie
0x140042c76  mov     rbx, [rsp+0B8h+arg_18]
0x140042c7e  add     rsp, 0B0h
0x140042c85  pop     rdi
0x140042c86  retn
```
