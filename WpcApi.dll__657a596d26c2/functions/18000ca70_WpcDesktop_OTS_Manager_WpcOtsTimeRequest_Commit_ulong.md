# WpcDesktop::OTS::Manager::WpcOtsTimeRequest::Commit(ulong)

- ea: `0x18000ca70`
- end: `0x18000cb32`
- name: `?Commit@WpcOtsTimeRequest@Manager@OTS@WpcDesktop@@UEAAJK@Z`
- size: `194`
- prototype: `__int64 __fastcall(WpcDesktop::OTS::Manager::WpcOtsTimeRequest *this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005f9c`
- `0x18000ca70`
- `0x18001ff68`
- `0x18002c010`

## string_xrefs

- `0x18000cacc`: `WpcOtsTimeRequest::Commit`

## pseudocode

```c
__int64 __fastcall WpcDesktop::OTS::Manager::WpcOtsTimeRequest::Commit(
        WpcDesktop::OTS::Manager::WpcOtsTimeRequest *this,
        int a2)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rdx
  _OWORD v5[2]; // [rsp+20h] [rbp-19h] BYREF
  _QWORD v6[7]; // [rsp+40h] [rbp+7h] BYREF
  _QWORD *v7; // [rsp+78h] [rbp+3Fh]
  int v8; // [rsp+A8h] [rbp+6Fh] BYREF

  v8 = a2;
  v6[0] = &std::_Func_impl_no_alloc<_lambda_ef10df06da94fd38ac23154a0c4c1ccd_,void,>::`vftable';
  v6[1] = (char *)this - 32;
  v6[2] = &v8;
  v7 = v6;
  memset(v5, 0, sizeof(v5));
  std::wstring::_Construct<1,unsigned short const *>(v5, L"WpcOtsTimeRequest::Commit", 25);
  v2 = ApiBoundary::Catch(v5, v6);
  std::wstring::~wstring(v5);
  if ( v7 )
  {
    v3 = v6;
    LOBYTE(v3) = v7 != v6;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v7 + 32LL))(v7, v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ca70  mov     [rsp-8+arg_0], rbx
0x18000ca75  mov     [rsp-8+arg_8], edx
0x18000ca79  push    rbp
0x18000ca7a  lea     rbp, [rsp-57h]
0x18000ca7f  sub     rsp, 90h
0x18000ca86  mov     rax, cs:__security_cookie
0x18000ca8d  xor     rax, rsp
0x18000ca90  mov     [rbp+57h+var_10], rax
0x18000ca94  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ef10df06da94fd38ac23154a0c4c1ccd_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ef10df06da94fd38ac23154a0c4c1ccd_,void,>::`vftable'
0x18000ca9b  mov     [rbp+57h+var_50], rax
0x18000ca9f  lea     rax, [rcx-20h]
0x18000caa3  mov     [rbp+57h+var_48], rax
0x18000caa7  lea     rax, [rbp+57h+arg_8]
0x18000caab  mov     [rbp+57h+var_40], rax
0x18000caaf  lea     rax, [rbp+57h+var_50]
0x18000cab3  mov     [rbp+57h+var_18], rax
0x18000cab7  xorps   xmm0, xmm0
0x18000caba  movups  [rbp+57h+var_70], xmm0
0x18000cabe  xorps   xmm1, xmm1
0x18000cac1  movdqu  [rbp+57h+var_60], xmm1
0x18000cac6  mov     r8d, 19h
0x18000cacc  lea     rdx, aWpcotstimerequ; "WpcOtsTimeRequest::Commit"
0x18000cad3  lea     rcx, [rbp+57h+var_70]
0x18000cad7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cadc  lea     rdx, [rbp+57h+var_50]
0x18000cae0  lea     rcx, [rbp+57h+var_70]
0x18000cae4  call    ?Catch@ApiBoundary@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AXXZ@3@@Z; ApiBoundary::Catch(std::wstring const &,std::function<void (void)> const &)
0x18000cae9  mov     ebx, eax
0x18000caeb  lea     rcx, [rbp+57h+var_70]
0x18000caef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000caf4  mov     rcx, [rbp+57h+var_18]
0x18000caf8  test    rcx, rcx
0x18000cafb  jz      short loc_18000CB13
0x18000cafd  mov     rax, [rcx]
0x18000cb00  lea     rdx, [rbp+57h+var_50]
0x18000cb04  cmp     rcx, rdx
0x18000cb07  setnz   dl
0x18000cb0a  mov     rax, [rax+20h]
0x18000cb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb13  mov     eax, ebx
0x18000cb15  mov     rcx, [rbp+57h+var_10]
0x18000cb19  xor     rcx, rsp; StackCookie
0x18000cb1c  call    __security_check_cookie
0x18000cb21  mov     rbx, [rsp+90h+arg_0]
0x18000cb29  add     rsp, 90h
0x18000cb30  pop     rbp
0x18000cb31  retn
```
