# CreateUpdateDeploymentProvider

- ea: `0x180006710`
- end: `0x1800068f1`
- name: `CreateUpdateDeploymentProvider`
- size: `481`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x180006710`
- `0x180007b9c`
- `0x18000a1d4`
- `0x18000dce4`
- `0x180012f24`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800068c5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800068c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800067e0`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800067e0`

## string_xrefs

- `0x18000674a`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\UpdateDeploymentExportImpl.cpp`
- `0x180006858`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\UpdateDeploymentExportImpl.cpp`

## pseudocode

```c
__int64 __fastcall CreateUpdateDeploymentProvider(_QWORD *a1, unsigned int a2)
{
  struct CUpdateDeploymentProvider *v4; // rbx
  PSECURITY_DESCRIPTOR v5; // rdi
  HRESULT v6; // esi
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(struct CUpdateDeploymentProvider *, GUID *, __int64 *); // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-60h]
  int v12; // [rsp+50h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc; // [rsp+58h] [rbp-28h] BYREF
  struct CUpdateDeploymentProvider *v14; // [rsp+60h] [rbp-20h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\UpdateDeploymentExportImpl.cpp",
      (const char *)0x80004003LL,
      dwAuthnLevel);
    return 2147500035LL;
  }
  v12 = 0;
  v4 = 0;
  v14 = 0;
  v15 = 0;
  v5 = 0;
  pSecDesc = 0;
  v6 = CCoInit::Initialize((CCoInit *)&v12, a2, 1);
  if ( v6 >= 0 )
  {
    v6 = AllocAbsoluteSDFromString(L"O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x1013ffff;;;BA)", &pSecDesc);
    v5 = pSecDesc;
    if ( v6 >= 0 )
    {
      v6 = CoInitializeSecurity(pSecDesc, -1, 0, 0, 0, 2u, 0, 0x1000u, 0);
      if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147417831 )
      {
        v6 = CUpdateDeploymentProvider::CreateInstance(&v14);
        v4 = v14;
        if ( v6 >= 0 )
        {
          v8 = **(__int64 (__fastcall ***)(struct CUpdateDeploymentProvider *, GUID *, __int64 *))v14;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v6 = v8(v4, &GUID_5d54b8cc_f575_4c39_bc33_f6da35df78f0, &v15);
          if ( v6 >= 0 )
          {
            v10 = v15;
            v9 = 0;
            v15 = 0;
            *a1 = v10;
            v6 = 0;
            goto LABEL_18;
          }
          v7 = 79;
        }
        else
        {
          v7 = 77;
        }
      }
      else
      {
        v7 = 75;
      }
    }
    else
    {
      v7 = 64;
    }
  }
  else
  {
    v7 = 63;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\UpdateDeploymentExportImpl.cpp",
    (const char *)(unsigned int)v6,
    dwAuthnLevel);
  v9 = v15;
LABEL_18:
  if ( v5 )
  {
    SusFree(v5);
    v9 = v15;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v15 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct CUpdateDeploymentProvider *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v12 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006710  mov     [rsp-18h+arg_8], rbx
0x180006715  mov     [rsp-18h+arg_10], rsi
0x18000671a  push    rbp
0x18000671b  push    rdi
0x18000671c  push    r14
0x18000671e  mov     rbp, rsp
0x180006721  sub     rsp, 80h
0x180006728  mov     rax, cs:__security_cookie
0x18000672f  xor     rax, rsp
0x180006732  mov     [rbp+var_10], rax
0x180006736  mov     r14, rcx
0x180006739  test    rcx, rcx
0x18000673c  jnz     short loc_180006761
0x18000673e  mov     rcx, [rbp+18h]; this
0x180006742  mov     ebx, 80004003h
0x180006747  mov     r9d, ebx; char *
0x18000674a  lea     r8, aCW1SSrcClientU_5; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180006751  lea     edx, [r14+38h]; void *
0x180006755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000675a  mov     eax, ebx
0x18000675c  jmp     loc_1800068CD
0x180006761  mov     [rbp+var_30], 0
0x180006768  xor     ebx, ebx
0x18000676a  mov     [rbp+var_20], rbx
0x18000676e  mov     [rbp+var_18], rbx
0x180006772  xor     edi, edi
0x180006774  mov     [rbp+pSecDesc], rdi
0x180006778  mov     r8b, 1; bool
0x18000677b  lea     rcx, [rbp+var_30]; this
0x18000677f  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x180006784  mov     esi, eax
0x180006786  test    eax, eax
0x180006788  jns     short loc_180006792
0x18000678a  lea     edx, [rbx+3Fh]
0x18000678d  jmp     loc_180006858
0x180006792  lea     rdx, [rbp+pSecDesc]
0x180006796  lea     rcx, aOBagBadA0x1013; "O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x101"...
0x18000679d  call    AllocAbsoluteSDFromString
0x1800067a2  mov     esi, eax
0x1800067a4  mov     rdi, [rbp+pSecDesc]
0x1800067a8  test    eax, eax
0x1800067aa  jns     short loc_1800067B6
0x1800067ac  mov     edx, 40h ; '@'
0x1800067b1  jmp     loc_180006858
0x1800067b6  mov     [rsp+80h+pReserved3], rbx; pReserved3
0x1800067bb  mov     [rsp+80h+dwCapabilities], 1000h; dwCapabilities
0x1800067c3  mov     [rsp+80h+pAuthList], rbx; pAuthList
0x1800067c8  mov     [rsp+80h+dwImpLevel], 2; dwImpLevel
0x1800067d0  mov     [rsp+80h+dwAuthnLevel], ebx; int
0x1800067d4  xor     r9d, r9d; pReserved1
0x1800067d7  xor     r8d, r8d; asAuthSvc
0x1800067da  or      edx, 0FFFFFFFFh; cAuthSvc
0x1800067dd  mov     rcx, rdi; pSecDesc
0x1800067e0  call    cs:__imp_CoInitializeSecurity
0x1800067e6  mov     esi, eax
0x1800067e8  mov     ecx, 80000000h
0x1800067ed  add     eax, ecx
0x1800067ef  test    ecx, eax
0x1800067f1  jnz     short loc_180006802
0x1800067f3  cmp     esi, 80010119h
0x1800067f9  jz      short loc_180006802
0x1800067fb  mov     edx, 4Bh ; 'K'
0x180006800  jmp     short loc_180006858
0x180006802  lea     rcx, [rbp+var_20]; struct CUpdateDeploymentProvider **
0x180006806  call    ?CreateInstance@CUpdateDeploymentProvider@@SAJPEAPEAV1@@Z; CUpdateDeploymentProvider::CreateInstance(CUpdateDeploymentProvider * *)
0x18000680b  mov     esi, eax
0x18000680d  mov     rbx, [rbp+var_20]
0x180006811  test    eax, eax
0x180006813  jns     short loc_18000681C
0x180006815  mov     edx, 4Dh ; 'M'
0x18000681a  jmp     short loc_180006858
0x18000681c  mov     rax, [rbx]
0x18000681f  mov     rsi, [rax]
0x180006822  mov     rcx, [rbp+var_18]
0x180006826  test    rcx, rcx
0x180006829  jz      short loc_180006837
0x18000682b  mov     rdx, [rcx]
0x18000682e  mov     rax, [rdx+10h]
0x180006832  call    _guard_dispatch_icall
0x180006837  lea     r8, [rbp+var_18]
0x18000683b  lea     rdx, _GUID_5d54b8cc_f575_4c39_bc33_f6da35df78f0
0x180006842  mov     rcx, rbx
0x180006845  mov     rax, rsi
0x180006848  call    _guard_dispatch_icall
0x18000684d  mov     esi, eax
0x18000684f  test    eax, eax
0x180006851  jns     short loc_180006871
0x180006853  mov     edx, 4Fh ; 'O'; void *
0x180006858  lea     r8, aCW1SSrcClientU_5; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18000685f  mov     rcx, [rbp+18h]; this
0x180006863  mov     r9d, esi; char *
0x180006866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000686b  mov     rcx, [rbp+var_18]
0x18000686f  jmp     short loc_180006880
0x180006871  mov     rax, [rbp+var_18]
0x180006875  xor     ecx, ecx
0x180006877  mov     [rbp+var_18], rcx
0x18000687b  mov     [r14], rax
0x18000687e  xor     esi, esi
0x180006880  test    rdi, rdi
0x180006883  jz      short loc_180006891
0x180006885  mov     rcx, rdi; lpMem
0x180006888  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000688d  mov     rcx, [rbp+var_18]
0x180006891  test    rcx, rcx
0x180006894  jz      short loc_1800068AA
0x180006896  mov     rax, [rcx]
0x180006899  mov     rax, [rax+10h]
0x18000689d  call    _guard_dispatch_icall
0x1800068a2  mov     [rbp+var_18], 0
0x1800068aa  test    rbx, rbx
0x1800068ad  jz      short loc_1800068BF
0x1800068af  mov     rcx, [rbx]
0x1800068b2  mov     rax, [rcx+10h]
0x1800068b6  mov     rcx, rbx
0x1800068b9  call    _guard_dispatch_icall
0x1800068be  nop
0x1800068bf  cmp     [rbp+var_30], 0
0x1800068c3  jz      short loc_1800068CB
0x1800068c5  call    cs:__imp_CoUninitialize
0x1800068cb  mov     eax, esi
0x1800068cd  mov     rcx, [rbp+var_10]
0x1800068d1  xor     rcx, rsp; StackCookie
0x1800068d4  call    __security_check_cookie
0x1800068d9  lea     r11, [rsp+80h+var_s0]
0x1800068e1  mov     rbx, [r11+28h]
0x1800068e5  mov     rsi, [r11+30h]
0x1800068e9  mov     rsp, r11
0x1800068ec  pop     r14
0x1800068ee  pop     rdi
0x1800068ef  pop     rbp
0x1800068f0  retn
```
