# D2D1RenderTarget::InitDraw(void)

- ea: `0x18003c8c0`
- end: `0x18003c993`
- name: `?InitDraw@D2D1RenderTarget@@UEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(D2D1RenderTarget *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003ae4`
- `0x18003c8c0`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003c8f6`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003c8f6`

## pseudocode

```c
__int64 __fastcall D2D1RenderTarget::InitDraw(D2D1RenderTarget *this)
{
  HRESULT Factory; // ebx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *ppIFactory[2]; // [rsp+30h] [rbp-28h] BYREF

  ppIFactory[0] = 0;
  Factory = D2D1CreateFactory(
              D2D1_FACTORY_TYPE_SINGLE_THREADED,
              &GUID_06152247_6f50_465a_9245_118bfd3b6007,
              0,
              ppIFactory);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)ppIFactory);
  if ( Factory >= 0 )
  {
    v3 = *((_QWORD *)this + 2);
    *(__m128i *)ppIFactory = _mm_load_si128((const __m128i *)&_xmm);
    Factory = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, char *))(*(_QWORD *)v3 + 64LL))(
                v3,
                ppIFactory,
                0,
                (char *)this + 32);
    if ( Factory >= 0 )
    {
      v4 = *((_QWORD *)this + 2);
      *(__m128i *)ppIFactory = _mm_load_si128((const __m128i *)&_xmm);
      Factory = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, char *))(*(_QWORD *)v4 + 64LL))(
                  v4,
                  ppIFactory,
                  0,
                  (char *)this + 24);
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 384LL))(*((_QWORD *)this + 2));
  return (unsigned int)Factory;
}

```

## disassembly

```asm
0x18003c8c0  mov     [rsp+arg_8], rbx
0x18003c8c5  push    rdi
0x18003c8c6  sub     rsp, 50h
0x18003c8ca  mov     rax, cs:__security_cookie
0x18003c8d1  xor     rax, rsp
0x18003c8d4  mov     [rsp+58h+var_18], rax
0x18003c8d9  mov     rdi, rcx
0x18003c8dc  mov     [rsp+58h+ppIFactory], 0
0x18003c8e5  xor     ecx, ecx; factoryType
0x18003c8e7  lea     r9, [rsp+58h+ppIFactory]; ppIFactory
0x18003c8ec  xor     r8d, r8d; pFactoryOptions
0x18003c8ef  lea     rdx, _GUID_06152247_6f50_465a_9245_118bfd3b6007; riid
0x18003c8f6  call    cs:__imp_D2D1CreateFactory
0x18003c8fc  lea     rcx, [rsp+58h+ppIFactory]
0x18003c901  mov     ebx, eax
0x18003c903  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c908  test    ebx, ebx
0x18003c90a  js      short loc_18003C966
0x18003c90c  mov     rcx, [rdi+10h]
0x18003c910  lea     r9, [rdi+20h]
0x18003c914  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x18003c91c  lea     rdx, [rsp+58h+ppIFactory]
0x18003c921  movups  xmmword ptr [rsp+58h+ppIFactory], xmm0
0x18003c926  xor     r8d, r8d
0x18003c929  mov     rax, [rcx]
0x18003c92c  mov     rax, [rax+40h]
0x18003c930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c935  mov     ebx, eax
0x18003c937  test    eax, eax
0x18003c939  js      short loc_18003C966
0x18003c93b  mov     rcx, [rdi+10h]
0x18003c93f  lea     r9, [rdi+18h]
0x18003c943  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x18003c94b  lea     rdx, [rsp+58h+ppIFactory]
0x18003c950  movups  xmmword ptr [rsp+58h+ppIFactory], xmm0
0x18003c955  xor     r8d, r8d
0x18003c958  mov     rax, [rcx]
0x18003c95b  mov     rax, [rax+40h]
0x18003c95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c964  mov     ebx, eax
0x18003c966  mov     rcx, [rdi+10h]
0x18003c96a  mov     rax, [rcx]
0x18003c96d  mov     rax, [rax+180h]
0x18003c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c979  mov     eax, ebx
0x18003c97b  mov     rcx, [rsp+58h+var_18]
0x18003c980  xor     rcx, rsp; StackCookie
0x18003c983  call    __security_check_cookie
0x18003c988  mov     rbx, [rsp+58h+arg_8]
0x18003c98d  add     rsp, 50h
0x18003c991  pop     rdi
0x18003c992  retn
```
