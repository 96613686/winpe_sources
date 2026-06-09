# CDPComAccountProvider::GetUserAccountPropertyAsync(CDPComAccount *,char const *,ICDPComAccountProviderCallback *,uint *)

- ea: `0x1800209c0`
- end: `0x180020b81`
- name: `?GetUserAccountPropertyAsync@CDPComAccountProvider@@UEAAJPEAUCDPComAccount@@PEBDPEAUICDPComAccountProviderCallback@@PEAI@Z`
- size: `449`
- prototype: `__int64 __fastcall(CDPComAccountProvider *__hidden this, struct CDPComAccount *, const char *, struct ICDPComAccountProviderCallback *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003678`
- `0x180004eb0`
- `0x1800097d0`
- `0x180009ae0`
- `0x18000a2c0`
- `0x1800209c0`
- `0x180020cc4`
- `0x180064010`

## import_xrefs

- `cdp!CDPCreateAccountInternalForUser` at `0x180020a9d`
- `cdp!CDPCreateAccountInternalForUser` at `0x180020a9d`

## string_xrefs

- `0x1800209ff`: `..\cdpcomaccountprovider.cpp`
- `0x180020aba`: `..\cdpcomaccountprovider.cpp`
- `0x180020aff`: `..\cdpcomaccountprovider.cpp`

## pseudocode

```c
__int64 __fastcall CDPComAccountProvider::GetUserAccountPropertyAsync(
        CDPComAccountProvider *this,
        struct CDPComAccount *a2,
        const char *a3,
        struct ICDPComAccountProviderCallback *a4,
        unsigned int *a5)
{
  int v9; // eax
  int CurrentUserContextToken; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  std::_Ref_count_base *v22; // [rsp+50h] [rbp-10h]
  unsigned int v23; // [rsp+88h] [rbp+28h] BYREF
  struct ICDPComAccountProviderCallback *v24; // [rsp+98h] [rbp+38h] BYREF

  v24 = a4;
  if ( !a2 )
  {
    v18 = 163;
LABEL_3:
    v23 = -2147024809;
LABEL_4:
    Log<long &,char const (&)[40],int>((__int64)this, (__int64)a2, &v23, "..\\cdpcomaccountprovider.cpp", &v18);
    return v23;
  }
  if ( !a3 )
  {
    v18 = 164;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v18 = 165;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v23 = -2147467261;
    v18 = 166;
    goto LABEL_4;
  }
  v9 = CDPComAccountProvider::EnsureAccountProviderInitialized(this);
  if ( v9 < 0 )
  {
    v23 = v9;
    v18 = 168;
    goto LABEL_4;
  }
  CurrentUserContextToken = cdp::GetCurrentUserContextToken((cdp *)&v20, (unsigned __int64 *)a2);
  if ( CurrentUserContextToken < 0 )
  {
    v23 = CurrentUserContextToken;
    v18 = 173;
    goto LABEL_4;
  }
  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v11 = CDPCreateAccountInternalForUser(*(_QWORD *)a2, *((unsigned __int16 *)a2 + 4), v20, &v19);
  if ( v11 >= 0 )
  {
    cdp::MakeSharedNoThrow<CDPComAccountProvider::AccountProviderCallback,ICDPComAccountProviderCallback * &>(
      &v21,
      (__int64 *)&v24);
    if ( v21 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)this + 19) + 88LL))(
              *((_QWORD *)this + 19),
              v19,
              a3);
      if ( v17 >= 0 )
      {
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        v14 = 0;
        goto LABEL_26;
      }
      v23 = v17;
      v18 = 181;
    }
    else
    {
      v23 = -2147024882;
      v18 = 180;
    }
    Log<long &,char const (&)[40],int>(v16, v15, &v23, "..\\cdpcomaccountprovider.cpp", &v18);
    v14 = v23;
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
  else
  {
    v23 = v11;
    v18 = 177;
    Log<long &,char const (&)[40],int>(v13, v12, &v23, "..\\cdpcomaccountprovider.cpp", &v18);
    v14 = v23;
  }
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  return v14;
}

```

## disassembly

```asm
0x1800209c0  mov     [rsp-18h+arg_0], rbx
0x1800209c5  mov     [rsp-18h+arg_10], rsi
0x1800209ca  mov     [rsp-18h+arg_18], r9
0x1800209cf  push    rbp
0x1800209d0  push    rdi
0x1800209d1  push    r14
0x1800209d3  mov     rbp, rsp
0x1800209d6  sub     rsp, 60h
0x1800209da  mov     rsi, r8
0x1800209dd  mov     rbx, rdx
0x1800209e0  mov     r14, rcx
0x1800209e3  test    rdx, rdx
0x1800209e6  jnz     short loc_180020A17
0x1800209e8  mov     [rbp+var_30], 0A3h
0x1800209ef  mov     [rbp+arg_8], 80070057h
0x1800209f6  lea     rax, [rbp+var_30]
0x1800209fa  mov     [rsp+60h+var_40], rax
0x1800209ff  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180020a06  lea     r8, [rbp+arg_8]
0x180020a0a  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180020a0f  mov     eax, [rbp+arg_8]
0x180020a12  jmp     loc_180020B6C
0x180020a17  test    rsi, rsi
0x180020a1a  jnz     short loc_180020A25
0x180020a1c  mov     [rbp+var_30], 0A4h
0x180020a23  jmp     short loc_1800209EF
0x180020a25  test    r9, r9
0x180020a28  jnz     short loc_180020A33
0x180020a2a  mov     [rbp+var_30], 0A5h
0x180020a31  jmp     short loc_1800209EF
0x180020a33  mov     rdi, [rbp+arg_20]
0x180020a37  test    rdi, rdi
0x180020a3a  jnz     short loc_180020A4C
0x180020a3c  mov     [rbp+arg_8], 80004003h
0x180020a43  mov     [rbp+var_30], 0A6h
0x180020a4a  jmp     short loc_1800209F6
0x180020a4c  call    ?EnsureAccountProviderInitialized@CDPComAccountProvider@@AEAAJXZ; CDPComAccountProvider::EnsureAccountProviderInitialized(void)
0x180020a51  test    eax, eax
0x180020a53  jns     short loc_180020A61
0x180020a55  mov     [rbp+arg_8], eax
0x180020a58  mov     [rbp+var_30], 0A8h
0x180020a5f  jmp     short loc_1800209F6
0x180020a61  lea     rcx, [rbp+var_20]; this
0x180020a65  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x180020a6a  test    eax, eax
0x180020a6c  jns     short loc_180020A7D
0x180020a6e  mov     [rbp+arg_8], eax
0x180020a71  mov     [rbp+var_30], 0ADh
0x180020a78  jmp     loc_1800209F6
0x180020a7d  mov     [rbp+var_28], 0
0x180020a85  lea     rcx, [rbp+var_28]
0x180020a89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020a8e  lea     r9, [rbp+var_28]
0x180020a92  mov     r8, [rbp+var_20]
0x180020a96  movzx   edx, word ptr [rbx+8]
0x180020a9a  mov     rcx, [rbx]
0x180020a9d  call    cs:__imp_CDPCreateAccountInternalForUser
0x180020aa3  test    eax, eax
0x180020aa5  jns     short loc_180020AD2
0x180020aa7  mov     [rbp+arg_8], eax
0x180020aaa  mov     [rbp+var_30], 0B1h
0x180020ab1  lea     rax, [rbp+var_30]
0x180020ab5  mov     [rsp+60h+var_40], rax
0x180020aba  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180020ac1  lea     r8, [rbp+arg_8]
0x180020ac5  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180020aca  mov     ebx, [rbp+arg_8]
0x180020acd  jmp     loc_180020B61
0x180020ad2  lea     rdx, [rbp+arg_18]
0x180020ad6  lea     rcx, [rbp+var_18]
0x180020ada  call    ??$MakeSharedNoThrow@VAccountProviderCallback@CDPComAccountProvider@@AEAPEAUICDPComAccountProviderCallback@@@cdp@@YA?AV?$shared_ptr@VAccountProviderCallback@CDPComAccountProvider@@@std@@AEAPEAUICDPComAccountProviderCallback@@@Z; cdp::MakeSharedNoThrow<CDPComAccountProvider::AccountProviderCallback,ICDPComAccountProviderCallback * &>(ICDPComAccountProviderCallback * &)
0x180020adf  mov     r9, [rbp+var_18]
0x180020ae3  test    r9, r9
0x180020ae6  jnz     short loc_180020B22
0x180020ae8  mov     [rbp+arg_8], 8007000Eh
0x180020aef  mov     [rbp+var_30], 0B4h
0x180020af6  lea     rax, [rbp+var_30]
0x180020afa  mov     [rsp+60h+var_40], rax
0x180020aff  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180020b06  lea     r8, [rbp+arg_8]
0x180020b0a  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180020b0f  mov     ebx, [rbp+arg_8]
0x180020b12  mov     rcx, [rbp+var_10]; this
0x180020b16  test    rcx, rcx
0x180020b19  jz      short loc_180020B61
0x180020b1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020b20  jmp     short loc_180020B61
0x180020b22  mov     rcx, [r14+98h]
0x180020b29  mov     rax, [rcx]
0x180020b2c  mov     [rsp+60h+var_40], rdi
0x180020b31  mov     r8, rsi
0x180020b34  mov     rdx, [rbp+var_28]
0x180020b38  mov     rax, [rax+58h]
0x180020b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b41  test    eax, eax
0x180020b43  jns     short loc_180020B51
0x180020b45  mov     [rbp+arg_8], eax
0x180020b48  mov     [rbp+var_30], 0B5h
0x180020b4f  jmp     short loc_180020AF6
0x180020b51  mov     rcx, [rbp+var_10]; this
0x180020b55  test    rcx, rcx
0x180020b58  jz      short loc_180020B5F
0x180020b5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020b5f  xor     ebx, ebx
0x180020b61  lea     rcx, [rbp+var_28]
0x180020b65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020b6a  mov     eax, ebx
0x180020b6c  lea     r11, [rsp+60h+var_s0]
0x180020b71  mov     rbx, [r11+20h]
0x180020b75  mov     rsi, [r11+30h]
0x180020b79  mov     rsp, r11
0x180020b7c  pop     r14
0x180020b7e  pop     rdi
0x180020b7f  pop     rbp
0x180020b80  retn
```
