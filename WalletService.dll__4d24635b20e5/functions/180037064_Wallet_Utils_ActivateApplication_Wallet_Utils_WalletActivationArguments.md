# Wallet::Utils::ActivateApplication(Wallet::Utils::WalletActivationArguments &)

- ea: `0x180037064`
- end: `0x1800371cd`
- name: `?ActivateApplication@Utils@Wallet@@YAJAEAUWalletActivationArguments@12@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Wallet::Utils *__hidden this, struct Wallet::Utils::WalletActivationArguments *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027bd0`

## callees

- `0x18000acac`
- `0x18000d8d8`
- `0x180013f78`
- `0x18001400c`
- `0x18002d048`
- `0x180037064`
- `0x1800397cc`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800370ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800370ed`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::ActivateApplication(
        Wallet::Utils *this,
        struct Wallet::Utils::WalletActivationArguments *a2)
{
  unsigned int v3; // ebx
  const unsigned __int16 *v4; // rdx
  HRESULT v5; // ecx
  int v6; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v10; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v12[264]; // [rsp+60h] [rbp-A0h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  memset_0(v12, 0, 0x208u);
  v10 = 0;
  LODWORD(v9) = 0;
  if ( g_fUnitTestContext )
  {
    v3 = g_activateAppReturnValue;
  }
  else
  {
    v5 = CoCreateInstance(&CLSID_ApplicationActivationClient, 0, 1u, &GUID_2e941141_7f97_4756_ba1d_9decde894a3d, &v10);
    if ( v5 >= 0 )
    {
      if ( Wallet::Utils::IsPhoneProductId(*((LPCOLESTR *)this + 10), v4) )
      {
        v5 = -2147023728;
      }
      else if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   v11,
                                   *((_QWORD *)this + 10)) )
      {
        LODWORD(ppv) = *((_DWORD *)this + 10);
        v5 = StringCchPrintfW(v12, 0x104u, L"\"%s\" %d %s", *((_QWORD *)this + 1), ppv, *((_QWORD *)this + 6), v9);
        if ( v5 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v10 + 24LL))(
                 v10,
                 v11[0],
                 0,
                 0,
                 &v9);
          v5 = 0;
          if ( v6 < 0 )
            v5 = v6;
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    v3 = v5;
  }
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v10);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  return v3;
}

```

## disassembly

```asm
0x180037064  mov     [rsp-8+arg_8], rbx
0x180037069  push    rbp
0x18003706a  lea     rbp, [rsp-180h]
0x180037072  sub     rsp, 280h
0x180037079  mov     rax, cs:__security_cookie
0x180037080  xor     rax, rsp
0x180037083  mov     [rbp+180h+var_10], rax
0x18003708a  mov     rbx, rcx
0x18003708d  lea     rcx, [rsp+280h+var_240]
0x180037092  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180037097  nop
0x180037098  xor     edx, edx; Val
0x18003709a  mov     r8d, 208h; Size
0x1800370a0  lea     rcx, [rsp+280h+var_220]; void *
0x1800370a5  call    memset_0
0x1800370aa  mov     [rsp+280h+var_248], 0
0x1800370b3  mov     dword ptr [rsp+280h+var_250], 0
0x1800370bb  cmp     cs:?g_fUnitTestContext@@3HA, 0; int g_fUnitTestContext
0x1800370c2  jz      short loc_1800370CF
0x1800370c4  mov     ebx, cs:?g_activateAppReturnValue@@3JA; long g_activateAppReturnValue
0x1800370ca  jmp     loc_180037196
0x1800370cf  lea     rax, [rsp+280h+var_248]
0x1800370d4  mov     [rsp+280h+ppv], rax; ppv
0x1800370d9  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x1800370e0  xor     edx, edx; pUnkOuter
0x1800370e2  lea     r8d, [rdx+1]; dwClsContext
0x1800370e6  lea     rcx, CLSID_ApplicationActivationClient; rclsid
0x1800370ed  call    cs:__imp_CoCreateInstance
0x1800370f3  mov     ecx, eax
0x1800370f5  test    eax, eax
0x1800370f7  js      loc_180037194
0x1800370fd  mov     rcx, [rbx+50h]; lpsz
0x180037101  call    ?IsPhoneProductId@Utils@Wallet@@YA_NPEBG@Z; Wallet::Utils::IsPhoneProductId(ushort const *)
0x180037106  test    al, al
0x180037108  jz      short loc_180037114
0x18003710a  mov     ecx, 80070490h
0x18003710f  jmp     loc_180037194
0x180037114  mov     rdx, [rbx+50h]
0x180037118  mov     r8, [rbx+58h]
0x18003711c  sub     r8, rdx
0x18003711f  sar     r8, 1
0x180037122  lea     rcx, [rsp+280h+var_240]
0x180037127  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003712c  test    al, al
0x18003712e  jnz     short loc_180037137
0x180037130  mov     ecx, 8007000Eh
0x180037135  jmp     short loc_180037194
0x180037137  mov     rax, [rbx+30h]
0x18003713b  mov     [rsp+280h+var_258], rax
0x180037140  mov     eax, [rbx+28h]
0x180037143  mov     dword ptr [rsp+280h+ppv], eax
0x180037147  mov     r9, [rbx+8]
0x18003714b  lea     r8, aSDS; "\"%s\" %d %s"
0x180037152  mov     edx, 104h; unsigned __int64
0x180037157  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18003715c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037161  mov     ecx, eax
0x180037163  test    eax, eax
0x180037165  js      short loc_180037194
0x180037167  mov     rcx, [rsp+280h+var_248]
0x18003716c  mov     rax, [rcx]
0x18003716f  lea     rdx, [rsp+280h+var_250]
0x180037174  mov     [rsp+280h+ppv], rdx
0x180037179  xor     r9d, r9d
0x18003717c  xor     r8d, r8d
0x18003717f  mov     rdx, [rsp+280h+var_240]
0x180037184  mov     rax, [rax+18h]
0x180037188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003718d  xor     ecx, ecx
0x18003718f  test    eax, eax
0x180037191  cmovs   ecx, eax
0x180037194  mov     ebx, ecx
0x180037196  lea     rcx, [rsp+280h+var_248]
0x18003719b  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x1800371a0  nop
0x1800371a1  lea     rcx, [rsp+280h+var_240]
0x1800371a6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800371ab  mov     eax, ebx
0x1800371ad  mov     rcx, [rbp+180h+var_10]
0x1800371b4  xor     rcx, rsp; StackCookie
0x1800371b7  call    __security_check_cookie
0x1800371bc  mov     rbx, [rsp+280h+arg_8]
0x1800371c4  add     rsp, 280h
0x1800371cb  pop     rbp
0x1800371cc  retn
```
