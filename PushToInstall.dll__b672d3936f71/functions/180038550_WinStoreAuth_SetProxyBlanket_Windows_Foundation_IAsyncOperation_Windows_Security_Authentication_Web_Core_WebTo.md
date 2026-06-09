# WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)

- ea: `0x180038550`
- end: `0x18003868a`
- name: `??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(IUnknown *)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a9a8`
- `0x18003acdc`
- `0x18003b010`
- `0x18003c128`
- `0x18003c52c`
- `0x18003e414`
- `0x18003e828`
- `0x180043f90`

## callees

- `0x180010b84`
- `0x180038550`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180038587`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800385f2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180038587`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800385f2`

## pseudocode

```c
__int64 __fastcall WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
        IUnknown *a1)
{
  HRESULT v2; // ebx
  HRESULT v3; // eax
  unsigned int v4; // edi
  IUnknown *v5; // rcx
  IUnknown *v7; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IUnknown *pProxy; // [rsp+58h] [rbp+10h] BYREF

  v2 = CoSetProxyBlanket(a1, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v2 == -2147467262 )
    return 0;
  pProxy = 0;
  if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_00000000_0000_0000_c000_000000000046,
         &pProxy) < 0
    || (v3 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u),
        v4 = v3,
        v3 >= 0) )
  {
    v7 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
    }
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v2,
        dwAuthnLevel);
      return (unsigned int)v2;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF0,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)v3,
    dwAuthnLevel);
  v5 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180038550  mov     rax, rsp
0x180038553  mov     [rax+8], rbx
0x180038557  push    rdi
0x180038558  sub     rsp, 40h
0x18003855c  mov     rdi, rcx
0x18003855f  mov     dword ptr [rax-10h], 40h ; '@'
0x180038566  mov     qword ptr [rax-18h], 0
0x18003856e  mov     dword ptr [rax-20h], 3
0x180038575  mov     dword ptr [rax-28h], 0
0x18003857c  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180038580  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180038584  or      edx, r8d; dwAuthnSvc
0x180038587  call    cs:__imp_CoSetProxyBlanket
0x18003858d  mov     ebx, eax
0x18003858f  cmp     eax, 80004002h
0x180038594  jz      loc_18003867D
0x18003859a  mov     [rsp+48h+pProxy], 0
0x1800385a3  mov     rcx, [rdi]
0x1800385a6  mov     rax, [rcx]
0x1800385a9  lea     r8, [rsp+48h+pProxy]
0x1800385ae  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800385b5  mov     rcx, rdi
0x1800385b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385bd  test    eax, eax
0x1800385bf  js      short loc_18003863C
0x1800385c1  mov     [rsp+48h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800385c9  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x1800385d2  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x1800385da  mov     [rsp+48h+dwAuthnLevel], 0; int
0x1800385e2  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800385e6  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800385ea  or      edx, r8d; dwAuthnSvc
0x1800385ed  mov     rcx, [rsp+48h+pProxy]; pProxy
0x1800385f2  call    cs:__imp_CoSetProxyBlanket
0x1800385f8  mov     edi, eax
0x1800385fa  test    eax, eax
0x1800385fc  jns     short loc_18003863C
0x1800385fe  mov     rcx, [rsp+48h]; this
0x180038603  mov     r9d, eax; char *
0x180038606  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003860d  mov     edx, 0F0h; void *
0x180038612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038617  nop
0x180038618  mov     rcx, [rsp+48h+pProxy]
0x18003861d  test    rcx, rcx
0x180038620  jz      short loc_180038638
0x180038622  mov     [rsp+48h+pProxy], 0
0x18003862b  mov     rax, [rcx]
0x18003862e  mov     rax, [rax+10h]
0x180038632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038637  nop
0x180038638  mov     eax, edi
0x18003863a  jmp     short loc_18003867F
0x18003863c  mov     rcx, [rsp+48h+pProxy]
0x180038641  test    rcx, rcx
0x180038644  jz      short loc_18003865C
0x180038646  mov     [rsp+48h+pProxy], 0
0x18003864f  mov     rax, [rcx]
0x180038652  mov     rax, [rax+10h]
0x180038656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003865b  nop
0x18003865c  test    ebx, ebx
0x18003865e  jns     short loc_18003867D
0x180038660  mov     rcx, [rsp+48h]; this
0x180038665  mov     r9d, ebx; char *
0x180038668  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003866f  mov     edx, 0F3h; void *
0x180038674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038679  mov     eax, ebx
0x18003867b  jmp     short loc_18003867F
0x18003867d  xor     eax, eax
0x18003867f  mov     rbx, [rsp+48h+arg_0]
0x180038684  add     rsp, 40h
0x180038688  pop     rdi
0x180038689  retn
```
