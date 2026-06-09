# CDPComAccountProvider::AccountProviderCallback::OnGetAllUserAccountsCompleted(uint,uint,ICDPAccount * *,ushort)

- ea: `0x1800108b0`
- end: `0x180010c72`
- name: `?OnGetAllUserAccountsCompleted@AccountProviderCallback@CDPComAccountProvider@@UEAAJIIPEAPEAVICDPAccount@@G@Z`
- size: `962`
- prototype: `__int64 __fastcall(CDPComAccountProvider::AccountProviderCallback *__hidden this, unsigned int, unsigned int, struct ICDPAccount **, unsigned __int16)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003678`
- `0x18000e934`
- `0x1800108b0`
- `0x180011280`
- `0x1800112cc`
- `0x18001d0f4`
- `0x180020cc4`
- `0x18002ca90`
- `0x18002cacc`
- `0x18002d1c8`
- `0x1800439fc`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180010ba6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180010ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001099f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001099f`

## string_xrefs

- `0x1800109d4`: `..\cdpcomaccountprovider.cpp`
- `0x180010b54`: `..\cdpcomaccountprovider.cpp`
- `0x180010bdf`: `..\cdpcomaccountprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CDPComAccountProvider::AccountProviderCallback::OnGetAllUserAccountsCompleted(
        CDPComAccountProvider::AccountProviderCallback *this,
        unsigned int a2,
        unsigned int a3,
        struct ICDPAccount **a4,
        unsigned __int16 a5)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 v13; // r12
  struct ICDPAccount **v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  rsize_t v18; // r14
  char *v19; // rsi
  int v20; // eax
  _QWORD *v21; // rcx
  unsigned __int64 v23; // rdi
  void *v24; // rbx
  __int128 v25; // rax
  _QWORD *v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  _QWORD *v31; // rcx
  const char *v32; // rax
  int v33; // [rsp+30h] [rbp-78h] BYREF
  _QWORD *v34; // [rsp+38h] [rbp-70h] BYREF
  __int128 **v35; // [rsp+40h] [rbp-68h] BYREF
  __int128 *v36; // [rsp+48h] [rbp-60h] BYREF
  __int128 v37; // [rsp+50h] [rbp-58h] BYREF
  __int128 v38; // [rsp+60h] [rbp-48h] BYREF
  __int64 v39; // [rsp+70h] [rbp-38h]
  unsigned int v40; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v41; // [rsp+B8h] [rbp+10h]

  v41 = a2;
  v34 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v9 = *((_QWORD *)this + 4);
  if ( !v9 )
  {
    v34 = 0;
    v10 = -2147024809;
    goto LABEL_26;
  }
  v34 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD **))(*(_QWORD *)v9 + 24LL))(
          v9,
          &GUID_a35b686f_455f_4848_b54c_056df7756c59,
          &v34);
  if ( v10 < 0 )
  {
LABEL_26:
    v40 = v10;
    v33 = 253;
    Log<long &,char const (&)[40],int>(v9, v8, &v40, "..\\cdpcomaccountprovider.cpp", &v33);
    v31 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v31 + 16LL))(v31, *v31);
    }
    return v40;
  }
  std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(&v38);
  v36 = &v38;
  v35 = &v36;
  v13 = a5;
  v14 = &a4[a5];
  while ( a4 != v14 )
  {
    v15 = (__int64)*a4;
    if ( !*a4 )
    {
      v20 = -2147024809;
      goto LABEL_10;
    }
    v37 = 0;
    DWORD2(v37) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(v16 + v17) );
    v18 = v17 + 1;
    v19 = (char *)CoTaskMemAlloc(v17 + 1);
    *(_QWORD *)&v37 = v19;
    if ( !v19 )
    {
      v20 = -2147024882;
LABEL_10:
      v40 = v20;
      v33 = 269;
      Log<long &,char const (&)[40],int>(v12, v11, &v40, "..\\cdpcomaccountprovider.cpp", &v33);
      ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___::_ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___(&v35);
      if ( (_QWORD)v38 )
      {
        std::_Deallocate<16>((void *)v38, (v39 - v38) & 0xFFFFFFFFFFFFFFF0uLL);
        v38 = 0;
        v39 = 0;
      }
      v21 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
      }
      return v40;
    }
    v32 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    strcpy_s(v19, v18, v32);
    std::vector<CDPComAccount>::emplace_back<CDPComAccount &>((__int64)&v38, &v37);
    ++a4;
  }
  v23 = saturated_mul((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 4, 8u);
  v24 = operator new[](v23);
  memset_0(v24, 0, v23);
  *(_QWORD *)&v37 = v24;
  v25 = v38;
  v26 = v24;
  while ( (_QWORD)v25 != *((_QWORD *)&v25 + 1) )
  {
    *v26 = v25;
    *(_QWORD *)&v25 = v25 + 16;
    ++v26;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, void *, unsigned __int16))(*v34 + 24LL))(
          v34,
          v41,
          a3,
          v24,
          v13);
  if ( v27 < 0 )
  {
    v40 = v27;
    v33 = 281;
    Log<long &,char const (&)[40],int>(v29, v28, &v40, "..\\cdpcomaccountprovider.cpp", &v33);
    std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(&v37);
    ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___::_ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___(&v35);
    if ( (_QWORD)v38 )
    {
      std::_Deallocate<16>((void *)v38, (v39 - v38) & 0xFFFFFFFFFFFFFFF0uLL);
      v38 = 0;
      v39 = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    return v40;
  }
  else
  {
    if ( v24 )
      operator delete(v24);
    ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___::_ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___(&v35);
    if ( (_QWORD)v38 )
      std::_Deallocate<16>((void *)v38, (v39 - v38) & 0xFFFFFFFFFFFFFFF0uLL);
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800108b0  mov     rax, rsp
0x1800108b3  mov     [rax+18h], rbx
0x1800108b7  mov     [rax+20h], rsi
0x1800108bb  mov     [rax+10h], edx
0x1800108be  push    rdi
0x1800108bf  push    r12
0x1800108c1  push    r13
0x1800108c3  push    r14
0x1800108c5  push    r15
0x1800108c7  sub     rsp, 80h
0x1800108ce  mov     rdi, r9
0x1800108d1  mov     r13d, r8d
0x1800108d4  mov     rbx, rcx
0x1800108d7  xor     esi, esi
0x1800108d9  mov     [rax-70h], rsi
0x1800108dd  lea     rcx, [rax-70h]
0x1800108e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800108e6  mov     rcx, [rbx+20h]
0x1800108ea  test    rcx, rcx
0x1800108ed  jz      loc_180010B31
0x1800108f3  mov     [rsp+0A8h+var_70], rsi
0x1800108f8  mov     rax, [rcx]
0x1800108fb  lea     r8, [rsp+0A8h+var_70]
0x180010900  lea     rdx, _GUID_a35b686f_455f_4848_b54c_056df7756c59
0x180010907  mov     rax, [rax+18h]
0x18001090b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010910  nop
0x180010911  test    eax, eax
0x180010913  js      loc_180010B3B
0x180010919  lea     rcx, [rsp+0A8h+var_48]
0x18001091e  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x180010923  nop
0x180010924  lea     rax, [rsp+0A8h+var_48]
0x180010929  mov     [rsp+0A8h+var_60], rax
0x18001092e  lea     rax, [rsp+0A8h+var_60]
0x180010933  mov     [rsp+0A8h+var_68], rax
0x180010938  movzx   r12d, [rsp+0A8h+arg_20]
0x180010941  lea     r15, [rdi+r12*8]
0x180010945  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010949  cmp     rdi, r15
0x18001094c  jz      loc_180010A45
0x180010952  mov     rbx, [rdi]
0x180010955  test    rbx, rbx
0x180010958  jz      loc_180010C49
0x18001095e  xorps   xmm0, xmm0
0x180010961  movdqa  [rsp+0A8h+var_58], xmm0
0x180010967  mov     rax, [rbx]
0x18001096a  mov     rcx, rbx
0x18001096d  mov     rax, [rax+18h]
0x180010971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010976  movzx   eax, ax
0x180010979  mov     dword ptr [rsp+0A8h+var_58+8], eax
0x18001097d  mov     rax, [rbx]
0x180010980  mov     rcx, rbx
0x180010983  mov     rax, [rax+20h]
0x180010987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001098c  mov     rcx, r14
0x18001098f  inc     rcx
0x180010992  cmp     [rax+rcx], sil
0x180010996  jnz     short loc_18001098F
0x180010998  lea     r14, [rcx+1]
0x18001099c  mov     rcx, r14; cb
0x18001099f  call    cs:__imp_CoTaskMemAlloc
0x1800109a5  mov     rsi, rax
0x1800109a8  mov     qword ptr [rsp+0A8h+var_58], rax
0x1800109ad  test    rax, rax
0x1800109b0  jnz     loc_180010B8E
0x1800109b6  mov     eax, 8007000Eh
0x1800109bb  mov     [rsp+0A8h+arg_0], eax
0x1800109c2  mov     [rsp+0A8h+var_78], 10Dh
0x1800109ca  lea     rax, [rsp+0A8h+var_78]
0x1800109cf  mov     [rsp+0A8h+var_88], rax
0x1800109d4  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x1800109db  lea     r8, [rsp+0A8h+arg_0]
0x1800109e3  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800109e8  nop
0x1800109e9  lea     rcx, [rsp+0A8h+var_68]
0x1800109ee  call    ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8______ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___
0x1800109f3  nop
0x1800109f4  mov     rcx, qword ptr [rsp+0A8h+var_48]
0x1800109f9  test    rcx, rcx
0x1800109fc  jz      short loc_180010A1D
0x1800109fe  mov     rdx, [rsp+0A8h+var_38]
0x180010a03  sub     rdx, rcx
0x180010a06  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180010a0a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010a0f  xorps   xmm0, xmm0
0x180010a12  movdqu  [rsp+0A8h+var_48], xmm0
0x180010a18  mov     [rsp+0A8h+var_38], rsi
0x180010a1d  mov     rcx, [rsp+0A8h+var_70]
0x180010a22  test    rcx, rcx
0x180010a25  jz      short loc_180010A39
0x180010a27  mov     [rsp+0A8h+var_70], rsi
0x180010a2c  mov     rdx, [rcx]
0x180010a2f  mov     rax, [rdx+10h]
0x180010a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a38  nop
0x180010a39  mov     eax, [rsp+0A8h+arg_0]
0x180010a40  jmp     loc_180010B14
0x180010a45  mov     rcx, qword ptr [rsp+0A8h+var_48+8]
0x180010a4a  sub     rcx, qword ptr [rsp+0A8h+var_48]
0x180010a4f  sar     rcx, 4
0x180010a53  mov     eax, 8
0x180010a58  mul     rcx
0x180010a5b  mov     rdi, rax
0x180010a5e  cmovb   rdi, r14
0x180010a62  mov     rcx, rdi; unsigned __int64
0x180010a65  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010a6a  mov     rbx, rax
0x180010a6d  mov     r8, rdi; Size
0x180010a70  xor     edx, edx; Val
0x180010a72  mov     rcx, rax; void *
0x180010a75  call    memset_0
0x180010a7a  mov     qword ptr [rsp+0A8h+var_58], rbx
0x180010a7f  mov     rax, qword ptr [rsp+0A8h+var_48]
0x180010a84  mov     rdx, qword ptr [rsp+0A8h+var_48+8]
0x180010a89  mov     rcx, rbx
0x180010a8c  cmp     rax, rdx
0x180010a8f  jnz     loc_180010C53
0x180010a95  mov     rcx, [rsp+0A8h+var_70]
0x180010a9a  mov     rax, [rcx]
0x180010a9d  mov     word ptr [rsp+0A8h+var_88], r12w
0x180010aa3  mov     r9, rbx
0x180010aa6  mov     r8d, r13d
0x180010aa9  mov     edx, [rsp+0A8h+arg_8]
0x180010ab0  mov     rax, [rax+18h]
0x180010ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab9  test    eax, eax
0x180010abb  js      loc_180010BC6
0x180010ac1  test    rbx, rbx
0x180010ac4  jz      short loc_180010ACF
0x180010ac6  mov     rcx, rbx; Block
0x180010ac9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010ace  nop
0x180010acf  lea     rcx, [rsp+0A8h+var_68]
0x180010ad4  call    ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8______ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___
0x180010ad9  nop
0x180010ada  mov     rcx, qword ptr [rsp+0A8h+var_48]
0x180010adf  test    rcx, rcx
0x180010ae2  jz      short loc_180010AF6
0x180010ae4  mov     rdx, [rsp+0A8h+var_38]
0x180010ae9  sub     rdx, rcx
0x180010aec  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180010af0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010af5  nop
0x180010af6  mov     rcx, [rsp+0A8h+var_70]
0x180010afb  test    rcx, rcx
0x180010afe  jz      short loc_180010B12
0x180010b00  mov     [rsp+0A8h+var_70], rsi
0x180010b05  mov     rax, [rcx]
0x180010b08  mov     rax, [rax+10h]
0x180010b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b11  nop
0x180010b12  xor     eax, eax
0x180010b14  lea     r11, [rsp+0A8h+var_28]
0x180010b1c  mov     rbx, [r11+40h]
0x180010b20  mov     rsi, [r11+48h]
0x180010b24  mov     rsp, r11
0x180010b27  pop     r15
0x180010b29  pop     r14
0x180010b2b  pop     r13
0x180010b2d  pop     r12
0x180010b2f  pop     rdi
0x180010b30  retn
0x180010b31  mov     [rsp+0A8h+var_70], rsi
0x180010b36  mov     eax, 80070057h
0x180010b3b  mov     [rsp+0A8h+arg_0], eax
0x180010b42  mov     [rsp+0A8h+var_78], 0FDh
0x180010b4a  lea     rax, [rsp+0A8h+var_78]
0x180010b4f  mov     [rsp+0A8h+var_88], rax
0x180010b54  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180010b5b  lea     r8, [rsp+0A8h+arg_0]
0x180010b63  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180010b68  nop
0x180010b69  mov     rcx, [rsp+0A8h+var_70]
0x180010b6e  test    rcx, rcx
0x180010b71  jz      short loc_180010B85
0x180010b73  mov     [rsp+0A8h+var_70], rsi
0x180010b78  mov     rdx, [rcx]
0x180010b7b  mov     rax, [rdx+10h]
0x180010b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b84  nop
0x180010b85  mov     eax, [rsp+0A8h+arg_0]
0x180010b8c  jmp     short loc_180010B14
0x180010b8e  mov     rax, [rbx]
0x180010b91  mov     rcx, rbx
0x180010b94  mov     rax, [rax+20h]
0x180010b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b9d  mov     r8, rax; Source
0x180010ba0  mov     rdx, r14; SizeInBytes
0x180010ba3  mov     rcx, rsi; Destination
0x180010ba6  call    cs:__imp_strcpy_s
0x180010bac  lea     rdx, [rsp+0A8h+var_58]
0x180010bb1  lea     rcx, [rsp+0A8h+var_48]
0x180010bb6  call    ??$emplace_back@AEAUCDPComAccount@@@?$vector@UCDPComAccount@@V?$allocator@UCDPComAccount@@@std@@@std@@QEAAAEAUCDPComAccount@@AEAU2@@Z; std::vector<CDPComAccount>::emplace_back<CDPComAccount &>(CDPComAccount &)
0x180010bbb  add     rdi, 8
0x180010bbf  xor     esi, esi
0x180010bc1  jmp     loc_180010945
0x180010bc6  mov     [rsp+0A8h+arg_0], eax
0x180010bcd  mov     [rsp+0A8h+var_78], 119h
0x180010bd5  lea     rax, [rsp+0A8h+var_78]
0x180010bda  mov     [rsp+0A8h+var_88], rax
0x180010bdf  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180010be6  lea     r8, [rsp+0A8h+arg_0]
0x180010bee  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180010bf3  nop
0x180010bf4  lea     rcx, [rsp+0A8h+var_58]
0x180010bf9  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x180010bfe  nop
0x180010bff  lea     rcx, [rsp+0A8h+var_68]
0x180010c04  call    ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8______ScopeWarden__lambda_f16ae333d12fdad8ee03dbd9f59815d8___
0x180010c09  nop
0x180010c0a  mov     rcx, qword ptr [rsp+0A8h+var_48]
0x180010c0f  test    rcx, rcx
0x180010c12  jz      short loc_180010C33
0x180010c14  mov     rdx, [rsp+0A8h+var_38]
0x180010c19  sub     rdx, rcx
0x180010c1c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180010c20  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010c25  xorps   xmm0, xmm0
0x180010c28  movdqu  [rsp+0A8h+var_48], xmm0
0x180010c2e  mov     [rsp+0A8h+var_38], rsi
0x180010c33  lea     rcx, [rsp+0A8h+var_70]
0x180010c38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c3d  mov     eax, [rsp+0A8h+arg_0]
0x180010c44  jmp     loc_180010B14
0x180010c49  mov     eax, 80070057h
0x180010c4e  jmp     loc_1800109BB
0x180010c53  mov     [rcx], rax
0x180010c56  add     rax, 10h
0x180010c5a  lea     rcx, [rcx+8]
0x180010c5e  jmp     loc_180010A8C
0x180010c63  lea     rcx, [rsp+0A8h+var_70]
0x180010c68  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c6d  jmp     loc_180010B85
```
