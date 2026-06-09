# WpcDesktop::OTS::Manager::WpcOtsRequestManager::CreateTimeRequest(ushort *,IWpcOtsTimeRequest * *)

- ea: `0x18000cb40`
- end: `0x18000cc0f`
- name: `?CreateTimeRequest@WpcOtsRequestManager@Manager@OTS@WpcDesktop@@UEAAJPEAGPEAPEAUIWpcOtsTimeRequest@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(WpcDesktop::OTS::Manager::WpcOtsRequestManager *__hidden this, unsigned __int16 *, struct IWpcOtsTimeRequest **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005f9c`
- `0x18000cb40`
- `0x18001ff68`
- `0x18002c010`

## string_xrefs

- `0x18000cba9`: `WpcOtsRequestManager::CreateTimeRequest`

## pseudocode

```c
__int64 __fastcall WpcDesktop::OTS::Manager::WpcOtsRequestManager::CreateTimeRequest(
        WpcDesktop::OTS::Manager::WpcOtsRequestManager *this,
        unsigned __int16 *a2,
        struct IWpcOtsTimeRequest **a3)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rdx
  _OWORD v6[2]; // [rsp+28h] [rbp-19h] BYREF
  _QWORD v7[7]; // [rsp+48h] [rbp+7h] BYREF
  _QWORD *v8; // [rsp+80h] [rbp+3Fh]
  unsigned __int16 *v9; // [rsp+B0h] [rbp+6Fh] BYREF
  struct IWpcOtsTimeRequest **v10; // [rsp+B8h] [rbp+77h] BYREF

  v10 = a3;
  v9 = a2;
  v7[0] = &std::_Func_impl_no_alloc<_lambda_b02109554609c394510eb354a049fda6_,void,>::`vftable';
  v7[1] = &v9;
  v7[2] = (char *)this - 32;
  v7[3] = &v10;
  v8 = v7;
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,unsigned short const *>(v6, L"WpcOtsRequestManager::CreateTimeRequest", 39);
  v3 = ApiBoundary::Catch(v6, v7);
  std::wstring::~wstring(v6);
  if ( v8 )
  {
    v4 = v7;
    LOBYTE(v4) = v8 != v7;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18000cb40  mov     rax, rsp
0x18000cb43  mov     [rax+8], rbx
0x18000cb47  mov     [rax+18h], r8
0x18000cb4b  mov     [rax+10h], rdx
0x18000cb4f  push    rbp
0x18000cb50  lea     rbp, [rax-5Fh]
0x18000cb54  sub     rsp, 90h
0x18000cb5b  mov     rax, cs:__security_cookie
0x18000cb62  xor     rax, rsp
0x18000cb65  mov     [rbp+57h+var_10], rax
0x18000cb69  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_b02109554609c394510eb354a049fda6_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_b02109554609c394510eb354a049fda6_,void,>::`vftable'
0x18000cb70  mov     [rbp+57h+var_50], rax
0x18000cb74  lea     rax, [rbp+57h+arg_8]
0x18000cb78  mov     [rbp+57h+var_48], rax
0x18000cb7c  lea     rax, [rcx-20h]
0x18000cb80  mov     [rbp+57h+var_40], rax
0x18000cb84  lea     rax, [rbp+57h+arg_10]
0x18000cb88  mov     [rbp+57h+var_38], rax
0x18000cb8c  lea     rax, [rbp+57h+var_50]
0x18000cb90  mov     [rbp+57h+var_18], rax
0x18000cb94  xorps   xmm0, xmm0
0x18000cb97  movups  [rbp+57h+var_70], xmm0
0x18000cb9b  xorps   xmm1, xmm1
0x18000cb9e  movdqu  [rbp+57h+var_60], xmm1
0x18000cba3  mov     r8d, 27h ; '''
0x18000cba9  lea     rdx, aWpcotsrequestm; "WpcOtsRequestManager::CreateTimeRequest"
0x18000cbb0  lea     rcx, [rbp+57h+var_70]
0x18000cbb4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cbb9  lea     rdx, [rbp+57h+var_50]
0x18000cbbd  lea     rcx, [rbp+57h+var_70]
0x18000cbc1  call    ?Catch@ApiBoundary@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AXXZ@3@@Z; ApiBoundary::Catch(std::wstring const &,std::function<void (void)> const &)
0x18000cbc6  mov     ebx, eax
0x18000cbc8  lea     rcx, [rbp+57h+var_70]
0x18000cbcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbd1  mov     rcx, [rbp+57h+var_18]
0x18000cbd5  test    rcx, rcx
0x18000cbd8  jz      short loc_18000CBF0
0x18000cbda  mov     rax, [rcx]
0x18000cbdd  lea     rdx, [rbp+57h+var_50]
0x18000cbe1  cmp     rcx, rdx
0x18000cbe4  setnz   dl
0x18000cbe7  mov     rax, [rax+20h]
0x18000cbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbf0  mov     eax, ebx
0x18000cbf2  mov     rcx, [rbp+57h+var_10]
0x18000cbf6  xor     rcx, rsp; StackCookie
0x18000cbf9  call    __security_check_cookie
0x18000cbfe  mov     rbx, [rsp+90h+arg_0]
0x18000cc06  add     rsp, 90h
0x18000cc0d  pop     rbp
0x18000cc0e  retn
```
