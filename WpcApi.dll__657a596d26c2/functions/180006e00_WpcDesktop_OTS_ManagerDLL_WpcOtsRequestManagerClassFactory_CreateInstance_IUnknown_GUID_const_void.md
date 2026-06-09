# WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006e00`
- end: `0x180006ecb`
- name: `?CreateInstance@WpcOtsRequestManagerClassFactory@ManagerDLL@OTS@WpcDesktop@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005f9c`
- `0x180006e00`
- `0x18001ff68`
- `0x18002c010`

## string_xrefs

- `0x180006e38`: `WpcOtsRequestManagerClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory::CreateInstance(
        WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rdx
  _OWORD v7[2]; // [rsp+28h] [rbp-19h] BYREF
  _QWORD v8[7]; // [rsp+48h] [rbp+7h] BYREF
  _QWORD *v9; // [rsp+80h] [rbp+3Fh]
  struct IUnknown *v10; // [rsp+B0h] [rbp+6Fh] BYREF
  void **v11; // [rsp+C0h] [rbp+7Fh] BYREF

  v11 = a4;
  v10 = a2;
  v8[3] = a3;
  v8[0] = &std::_Func_impl_no_alloc<_lambda_1474688f9344c4b55f9222d418d9063b_,void,>::`vftable';
  v8[1] = &v11;
  v8[2] = &v10;
  v9 = v8;
  memset(v7, 0, sizeof(v7));
  std::wstring::_Construct<1,unsigned short const *>(v7, L"WpcOtsRequestManagerClassFactory::CreateInstance", 48);
  v4 = ApiBoundary::Catch(v7, v8);
  std::wstring::~wstring(v7);
  if ( v9 )
  {
    v5 = v8;
    LOBYTE(v5) = v9 != v8;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180006e00  mov     rax, rsp
0x180006e03  mov     [rax+8], rbx
0x180006e07  mov     [rax+20h], r9
0x180006e0b  mov     [rax+10h], rdx
0x180006e0f  push    rbp
0x180006e10  lea     rbp, [rax-5Fh]
0x180006e14  sub     rsp, 90h
0x180006e1b  mov     rax, cs:__security_cookie
0x180006e22  xor     rax, rsp
0x180006e25  mov     [rbp+57h+var_10], rax
0x180006e29  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1474688f9344c4b55f9222d418d9063b_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1474688f9344c4b55f9222d418d9063b_,void,>::`vftable'
0x180006e30  mov     [rbp+57h+var_38], r8
0x180006e34  mov     [rbp+57h+var_50], rax
0x180006e38  lea     rdx, aWpcotsrequestm_0; "WpcOtsRequestManagerClassFactory::Creat"...
0x180006e3f  lea     rax, [rbp+57h+arg_18]
0x180006e43  xorps   xmm0, xmm0
0x180006e46  mov     [rbp+57h+var_48], rax
0x180006e4a  lea     rcx, [rbp+57h+var_70]
0x180006e4e  lea     rax, [rbp+57h+arg_8]
0x180006e52  xorps   xmm1, xmm1
0x180006e55  mov     [rbp+57h+var_40], rax
0x180006e59  mov     r8d, 30h ; '0'
0x180006e5f  lea     rax, [rbp+57h+var_50]
0x180006e63  mov     [rbp+57h+var_18], rax
0x180006e67  movups  [rbp+57h+var_70], xmm0
0x180006e6b  movdqu  [rbp+57h+var_60], xmm1
0x180006e70  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180006e75  lea     rdx, [rbp+57h+var_50]
0x180006e79  lea     rcx, [rbp+57h+var_70]
0x180006e7d  call    ?Catch@ApiBoundary@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AXXZ@3@@Z; ApiBoundary::Catch(std::wstring const &,std::function<void (void)> const &)
0x180006e82  lea     rcx, [rbp+57h+var_70]
0x180006e86  mov     ebx, eax
0x180006e88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006e8d  mov     rcx, [rbp+57h+var_18]
0x180006e91  test    rcx, rcx
0x180006e94  jz      short loc_180006EAC
0x180006e96  mov     rax, [rcx]
0x180006e99  lea     rdx, [rbp+57h+var_50]
0x180006e9d  cmp     rcx, rdx
0x180006ea0  setnz   dl
0x180006ea3  mov     rax, [rax+20h]
0x180006ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eac  mov     eax, ebx
0x180006eae  mov     rcx, [rbp+57h+var_10]
0x180006eb2  xor     rcx, rsp; StackCookie
0x180006eb5  call    __security_check_cookie
0x180006eba  mov     rbx, [rsp+90h+arg_0]
0x180006ec2  add     rsp, 90h
0x180006ec9  pop     rbp
0x180006eca  retn
```
