# CEdpMethods::CreateHostName(ushort const *,Windows::Networking::IHostName * *)

- ea: `0x1800bc894`
- end: `0x1800bca68`
- name: `?CreateHostName@CEdpMethods@@AEAAJPEBGPEAPEAUIHostName@Networking@Windows@@@Z`
- size: `468`
- prototype: `int(CEdpMethods *__hidden this, const unsigned __int16 *, struct Windows::Networking::IHostName **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bcee0`

## callees

- `0x180007e10`
- `0x180011314`
- `0x1800bc144`
- `0x1800bc894`
- `0x1800bd244`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bca31`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bca31`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bc92f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bc92f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bca24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bca24`

## string_xrefs

- `0x1800bc904`: `CEdpMethods::CreateHostName`

## pseudocode

```c
__int64 __fastcall CEdpMethods::CreateHostName(
        CEdpMethods *this,
        const unsigned __int16 *a2,
        struct Windows::Networking::IHostName **a3)
{
  _BYTE *v5; // rax
  char v6; // cl
  int v7; // ebx
  __int16 v8; // ax
  HSTRING v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, HSTRING, struct Windows::Networking::IHostName **); // rdi
  unsigned int v13; // edi
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  int v16; // [rsp+28h] [rbp-28h] BYREF
  int v17; // [rsp+2Ch] [rbp-24h]
  char v18; // [rsp+30h] [rbp-20h]
  const char *v19; // [rsp+38h] [rbp-18h]
  __int64 v20; // [rsp+40h] [rbp-10h]
  struct Windows::Networking::IHostName *v21; // [rsp+80h] [rbp+30h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v21 = this;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (v5[68] & 0x20) == 0 || (v6 = 1, v5[65] < 6u) )
    v6 = 0;
  v18 = v6;
  v19 = "CEdpMethods::CreateHostName";
  v17 = 100;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  string = 0;
  v7 = RoInitialize(1);
  v16 = v7;
  v8 = 109;
  if ( v7 < 0 )
    goto LABEL_9;
  LOWORD(v17) = 109;
  if ( a3 )
    *a3 = 0;
  v8 = 112;
  if ( !a2 || (LOWORD(v17) = 112, v8 = 113, !a3) )
  {
    v16 = -2147024809;
LABEL_9:
    HIWORD(v17) = v8;
    goto LABEL_21;
  }
  LOWORD(v17) = 113;
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  v16 = GetActivationFactory<Windows::Networking::IHostNameFactory>(v9, &v22);
  v8 = 116;
  if ( v16 < 0 )
    goto LABEL_9;
  LOWORD(v17) = 116;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v16 = WindowsCreateString(a2, v10, &string);
  v8 = 118;
  if ( v16 < 0 )
    goto LABEL_9;
  v11 = v22;
  LOWORD(v17) = 118;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Networking::IHostName **))(*(_QWORD *)v22 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v21);
  v16 = v12(v11, string, &v21);
  v8 = 120;
  if ( v16 < 0 )
    goto LABEL_9;
  LOWORD(v17) = 120;
  *a3 = v21;
  v21 = 0;
LABEL_21:
  WindowsDeleteString(string);
  WindowsDeleteString(0);
  v13 = v16;
  if ( v7 >= 0 )
    RoUninitialize();
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v16);
  return v13;
}

```

## disassembly

```asm
0x1800bc894  mov     [rsp-28h+arg_8], rbx
0x1800bc899  mov     [rsp-28h+arg_0], rcx
0x1800bc89e  push    rbp
0x1800bc89f  push    rsi
0x1800bc8a0  push    rdi
0x1800bc8a1  push    r14
0x1800bc8a3  push    r15
0x1800bc8a5  mov     rbp, rsp
0x1800bc8a8  sub     rsp, 50h
0x1800bc8ac  mov     r14, r8
0x1800bc8af  mov     rdi, rdx
0x1800bc8b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc8b9  lea     rcx, WPP_GLOBAL_Control
0x1800bc8c0  cmp     rax, rcx
0x1800bc8c3  jz      short loc_1800BC8ED
0x1800bc8c5  test    byte ptr [rax+44h], 20h
0x1800bc8c9  jz      short loc_1800BC8ED
0x1800bc8cb  cmp     byte ptr [rax+41h], 6
0x1800bc8cf  jb      short loc_1800BC8ED
0x1800bc8d1  mov     rcx, [rax+38h]
0x1800bc8d5  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bc8dc  mov     edx, 0Ch
0x1800bc8e1  call    WPP_SF_
0x1800bc8e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc8ed  xor     r15d, r15d
0x1800bc8f0  test    byte ptr [rax+44h], 20h
0x1800bc8f4  jz      short loc_1800BC8FE
0x1800bc8f6  cmp     byte ptr [rax+41h], 6
0x1800bc8fa  mov     cl, 1
0x1800bc8fc  jnb     short loc_1800BC901
0x1800bc8fe  mov     cl, r15b
0x1800bc901  mov     [rbp+var_20], cl
0x1800bc904  lea     rax, aCedpmethodsCre; "CEdpMethods::CreateHostName"
0x1800bc90b  mov     ecx, 1
0x1800bc910  mov     [rbp+var_18], rax
0x1800bc914  mov     [rbp+var_28], r15d
0x1800bc918  mov     [rbp+var_24], 64h ; 'd'
0x1800bc91f  mov     [rbp+var_10], r15
0x1800bc923  mov     [rbp+arg_18], r15
0x1800bc927  mov     [rbp+arg_0], r15
0x1800bc92b  mov     [rbp+string], r15
0x1800bc92f  call    cs:__imp_RoInitialize
0x1800bc935  mov     ebx, eax
0x1800bc937  mov     [rbp+var_28], eax
0x1800bc93a  test    eax, eax
0x1800bc93c  mov     eax, 6Dh ; 'm'
0x1800bc941  jns     short loc_1800BC94C
0x1800bc943  mov     word ptr [rbp+var_24+2], ax
0x1800bc947  jmp     loc_1800BCA18
0x1800bc94c  mov     word ptr [rbp+var_24], ax
0x1800bc950  test    r14, r14
0x1800bc953  jz      short loc_1800BC958
0x1800bc955  mov     [r14], r15
0x1800bc958  mov     eax, 70h ; 'p'
0x1800bc95d  test    rdi, rdi
0x1800bc960  jnz     short loc_1800BC96B
0x1800bc962  mov     [rbp+var_28], 80070057h
0x1800bc969  jmp     short loc_1800BC943
0x1800bc96b  mov     word ptr [rbp+var_24], ax
0x1800bc96f  mov     eax, 71h ; 'q'
0x1800bc974  test    r14, r14
0x1800bc977  jz      short loc_1800BC962
0x1800bc979  lea     rcx, [rbp+arg_18]
0x1800bc97d  mov     [rbp+var_28], r15d
0x1800bc981  mov     word ptr [rbp+var_24], ax
0x1800bc985  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bc98a  lea     rdx, [rbp+arg_18]
0x1800bc98e  call    ??$GetActivationFactory@UIHostNameFactory@Networking@Windows@@@@YAJPEBGPEAPEAUIHostNameFactory@Networking@Windows@@@Z; GetActivationFactory<Windows::Networking::IHostNameFactory>(ushort const *,Windows::Networking::IHostNameFactory * *)
0x1800bc993  mov     [rbp+var_28], eax
0x1800bc996  test    eax, eax
0x1800bc998  mov     eax, 74h ; 't'
0x1800bc99d  js      short loc_1800BC943
0x1800bc99f  mov     word ptr [rbp+var_24], ax
0x1800bc9a3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc9a7  inc     rdx; length
0x1800bc9aa  cmp     [rdi+rdx*2], r15w
0x1800bc9af  jnz     short loc_1800BC9A7
0x1800bc9b1  lea     r8, [rbp+string]; string
0x1800bc9b5  mov     rcx, rdi; sourceString
0x1800bc9b8  call    cs:__imp_WindowsCreateString
0x1800bc9be  mov     [rbp+var_28], eax
0x1800bc9c1  test    eax, eax
0x1800bc9c3  mov     eax, 76h ; 'v'
0x1800bc9c8  js      loc_1800BC943
0x1800bc9ce  mov     rsi, [rbp+arg_18]
0x1800bc9d2  lea     rcx, [rbp+arg_0]
0x1800bc9d6  mov     word ptr [rbp+var_24], ax
0x1800bc9da  mov     rax, [rsi]
0x1800bc9dd  mov     rdi, [rax+30h]
0x1800bc9e1  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bc9e6  mov     rdx, [rbp+string]
0x1800bc9ea  lea     r8, [rbp+arg_0]
0x1800bc9ee  mov     rcx, rsi
0x1800bc9f1  mov     rax, rdi
0x1800bc9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc9f9  mov     [rbp+var_28], eax
0x1800bc9fc  test    eax, eax
0x1800bc9fe  mov     eax, 78h ; 'x'
0x1800bca03  js      loc_1800BC943
0x1800bca09  mov     word ptr [rbp+var_24], ax
0x1800bca0d  mov     rax, [rbp+arg_0]
0x1800bca11  mov     [r14], rax
0x1800bca14  mov     [rbp+arg_0], r15
0x1800bca18  mov     rcx, [rbp+string]; string
0x1800bca1c  call    cs:__imp_WindowsDeleteString
0x1800bca22  xor     ecx, ecx; string
0x1800bca24  call    cs:__imp_WindowsDeleteString
0x1800bca2a  mov     edi, [rbp+var_28]
0x1800bca2d  test    ebx, ebx
0x1800bca2f  js      short loc_1800BCA37
0x1800bca31  call    cs:__imp_RoUninitialize
0x1800bca37  lea     rcx, [rbp+arg_0]
0x1800bca3b  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bca40  lea     rcx, [rbp+arg_18]
0x1800bca44  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bca49  lea     rcx, [rbp+var_28]; this
0x1800bca4d  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bca52  mov     rbx, [rsp+50h+arg_8]
0x1800bca5a  mov     eax, edi
0x1800bca5c  add     rsp, 50h
0x1800bca60  pop     r15
0x1800bca62  pop     r14
0x1800bca64  pop     rdi
0x1800bca65  pop     rsi
0x1800bca66  pop     rbp
0x1800bca67  retn
```
