# CDPComAccountProvider::AccountProviderCallback::OnGetUserAccountCompleted(uint,uint,ICDPAccount *)

- ea: `0x180010dd0`
- end: `0x180010fdc`
- name: `?OnGetUserAccountCompleted@AccountProviderCallback@CDPComAccountProvider@@UEAAJIIPEAVICDPAccount@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(CDPComAccountProvider::AccountProviderCallback *__hidden this, unsigned int, unsigned int, struct ICDPAccount *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003678`
- `0x180010dd0`
- `0x180011250`
- `0x180020cc4`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180010f69`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180010f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f41`

## string_xrefs

- `0x180010ed0`: `..\cdpcomaccountprovider.cpp`
- `0x180010f8b`: `..\cdpcomaccountprovider.cpp`
- `0x180010fb0`: `..\cdpcomaccountprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComAccountProvider::AccountProviderCallback::OnGetUserAccountCompleted(
        CDPComAccountProvider::AccountProviderCallback *this,
        unsigned int a2,
        unsigned int a3,
        struct ICDPAccount *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  rsize_t v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  const char *v22; // rax
  unsigned int v23; // ebx
  int v24; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+38h] [rbp-28h] BYREF
  char ***v26; // [rsp+40h] [rbp-20h] BYREF
  char **v27; // [rsp+48h] [rbp-18h] BYREF
  char *Destination[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+20h] BYREF

  v25 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v9 = *((_QWORD *)this + 4);
  v25 = 0;
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v9 + 24LL))(
            v9,
            &GUID_a35b686f_455f_4848_b54c_056df7756c59,
            &v25);
    if ( v10 >= 0 )
    {
      *(_OWORD *)Destination = 0;
      if ( a4 )
      {
        *(_OWORD *)Destination = 0;
        LODWORD(Destination[1]) = (*(unsigned __int16 (__fastcall **)(struct ICDPAccount *))(*(_QWORD *)a4 + 24LL))(a4);
        v17 = (*(__int64 (__fastcall **)(struct ICDPAccount *))(*(_QWORD *)a4 + 32LL))(a4);
        v18 = -1;
        do
          ++v18;
        while ( *(_BYTE *)(v17 + v18) );
        v19 = v18 + 1;
        Destination[0] = (char *)CoTaskMemAlloc(v18 + 1);
        if ( !Destination[0] )
        {
          v29 = -2147024882;
          v24 = 297;
          Log<long &,char const (&)[40],int>(v21, v20, &v29, "..\\cdpcomaccountprovider.cpp", &v24);
          goto LABEL_18;
        }
        v22 = (const char *)(*(__int64 (__fastcall **)(struct ICDPAccount *))(*(_QWORD *)a4 + 32LL))(a4);
        strcpy_s(Destination[0], v19, v22);
      }
      v27 = Destination;
      v26 = &v27;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char **))(*(_QWORD *)v25 + 40LL))(
              v25,
              a2,
              a3,
              Destination);
      if ( v11 >= 0 )
      {
        ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___::_ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___(&v26);
        v14 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        return 0;
      }
      v29 = v11;
      v24 = 305;
      Log<long &,char const (&)[40],int>(v13, v12, &v29, "..\\cdpcomaccountprovider.cpp", &v24);
      ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___::_ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___(&v26);
LABEL_18:
      v23 = v29;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      return v23;
    }
  }
  else
  {
    v10 = -2147024809;
  }
  v29 = v10;
  v24 = 291;
  Log<long &,char const (&)[40],int>(v9, v8, &v29, "..\\cdpcomaccountprovider.cpp", &v24);
  v16 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return v29;
}

```

## disassembly

```asm
0x180010dd0  mov     [rsp-18h+arg_8], rbx
0x180010dd5  mov     [rsp-18h+arg_10], rsi
0x180010dda  push    rbp
0x180010ddb  push    rdi
0x180010ddc  push    r14
0x180010dde  mov     rbp, rsp
0x180010de1  sub     rsp, 60h
0x180010de5  mov     rdi, r9
0x180010de8  mov     esi, r8d
0x180010deb  mov     r14d, edx
0x180010dee  mov     rbx, rcx
0x180010df1  mov     [rbp+var_28], 0
0x180010df9  lea     rcx, [rbp+var_28]
0x180010dfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010e02  mov     rcx, [rbx+20h]
0x180010e06  mov     [rbp+var_28], 0
0x180010e0e  test    rcx, rcx
0x180010e11  jz      loc_180010EB8
0x180010e17  mov     rax, [rcx]
0x180010e1a  lea     r8, [rbp+var_28]
0x180010e1e  lea     rdx, _GUID_a35b686f_455f_4848_b54c_056df7756c59
0x180010e25  mov     rax, [rax+18h]
0x180010e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2e  nop
0x180010e2f  test    eax, eax
0x180010e31  js      loc_180010EBD
0x180010e37  xorps   xmm0, xmm0
0x180010e3a  movups  xmmword ptr [rbp+Destination], xmm0
0x180010e3e  test    rdi, rdi
0x180010e41  jnz     loc_180010F04
0x180010e47  lea     rax, [rbp+Destination]
0x180010e4b  mov     [rbp+var_18], rax
0x180010e4f  lea     rax, [rbp+var_18]
0x180010e53  mov     [rbp+var_20], rax
0x180010e57  mov     rcx, [rbp+var_28]
0x180010e5b  mov     rax, [rcx]
0x180010e5e  lea     r9, [rbp+Destination]
0x180010e62  mov     r8d, esi
0x180010e65  mov     edx, r14d
0x180010e68  mov     rax, [rax+28h]
0x180010e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e71  test    eax, eax
0x180010e73  js      loc_180010F9D
0x180010e79  lea     rcx, [rbp+var_20]
0x180010e7d  call    ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7______ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___
0x180010e82  nop
0x180010e83  mov     rcx, [rbp+var_28]
0x180010e87  test    rcx, rcx
0x180010e8a  jz      short loc_180010EA1
0x180010e8c  mov     [rbp+var_28], 0
0x180010e94  mov     rax, [rcx]
0x180010e97  mov     rax, [rax+10h]
0x180010e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea0  nop
0x180010ea1  xor     eax, eax
0x180010ea3  lea     r11, [rsp+60h+var_s0]
0x180010ea8  mov     rbx, [r11+28h]
0x180010eac  mov     rsi, [r11+30h]
0x180010eb0  mov     rsp, r11
0x180010eb3  pop     r14
0x180010eb5  pop     rdi
0x180010eb6  pop     rbp
0x180010eb7  retn
0x180010eb8  mov     eax, 80070057h
0x180010ebd  mov     [rbp+arg_0], eax
0x180010ec0  mov     [rbp+var_30], 123h
0x180010ec7  lea     rax, [rbp+var_30]
0x180010ecb  mov     [rsp+60h+var_40], rax
0x180010ed0  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180010ed7  lea     r8, [rbp+arg_0]
0x180010edb  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180010ee0  nop
0x180010ee1  mov     rcx, [rbp+var_28]
0x180010ee5  test    rcx, rcx
0x180010ee8  jz      short loc_180010EFF
0x180010eea  mov     [rbp+var_28], 0
0x180010ef2  mov     rdx, [rcx]
0x180010ef5  mov     rax, [rdx+10h]
0x180010ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efe  nop
0x180010eff  mov     eax, [rbp+arg_0]
0x180010f02  jmp     short loc_180010EA3
0x180010f04  movdqa  xmmword ptr [rbp+Destination], xmm0
0x180010f09  mov     rax, [rdi]
0x180010f0c  mov     rcx, rdi
0x180010f0f  mov     rax, [rax+18h]
0x180010f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f18  movzx   eax, ax
0x180010f1b  mov     dword ptr [rbp+Destination+8], eax
0x180010f1e  mov     rax, [rdi]
0x180010f21  mov     rcx, rdi
0x180010f24  mov     rax, [rax+20h]
0x180010f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010f31  inc     rcx
0x180010f34  cmp     byte ptr [rax+rcx], 0
0x180010f38  jnz     short loc_180010F31
0x180010f3a  lea     rbx, [rcx+1]
0x180010f3e  mov     rcx, rbx; cb
0x180010f41  call    cs:__imp_CoTaskMemAlloc
0x180010f47  mov     [rbp+Destination], rax
0x180010f4b  test    rax, rax
0x180010f4e  jz      short loc_180010F74
0x180010f50  mov     rax, [rdi]
0x180010f53  mov     rcx, rdi
0x180010f56  mov     rax, [rax+20h]
0x180010f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5f  mov     r8, rax; Source
0x180010f62  mov     rdx, rbx; SizeInBytes
0x180010f65  mov     rcx, [rbp+Destination]; Destination
0x180010f69  call    cs:__imp_strcpy_s
0x180010f6f  jmp     loc_180010E47
0x180010f74  mov     [rbp+arg_0], 8007000Eh
0x180010f7b  mov     [rbp+var_30], 129h
0x180010f82  lea     rax, [rbp+var_30]
0x180010f86  mov     [rsp+60h+var_40], rax
0x180010f8b  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180010f92  lea     r8, [rbp+arg_0]
0x180010f96  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180010f9b  jmp     short loc_180010FC9
0x180010f9d  mov     [rbp+arg_0], eax
0x180010fa0  mov     [rbp+var_30], 131h
0x180010fa7  lea     rax, [rbp+var_30]
0x180010fab  mov     [rsp+60h+var_40], rax
0x180010fb0  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x180010fb7  lea     r8, [rbp+arg_0]
0x180010fbb  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180010fc0  lea     rcx, [rbp+var_20]
0x180010fc4  call    ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7______ScopeWarden__lambda_0e2d1e4bdc5c2a9e699a352b8e07a2e7___
0x180010fc9  mov     ebx, [rbp+arg_0]
0x180010fcc  lea     rcx, [rbp+var_28]
0x180010fd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010fd5  mov     eax, ebx
0x180010fd7  jmp     loc_180010EA3
```
