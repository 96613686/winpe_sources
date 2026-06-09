# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x180109fac`
- end: `0x18010a2ae`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `770`
- prototype: `__int64 __fastcall(const struct Common::StateSeparationRedirectionMapping *, const unsigned __int16 **, unsigned __int16 *, unsigned __int16 *, bool, HKEY *phkResult)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180104754`

## callees

- `0x180003430`
- `0x1800eabf4`
- `0x18010968c`
- `0x1801098c0`
- `0x180109dcc`
- `0x180109fac`
- `0x18010a720`
- `0x18010a834`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010a0a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010a0a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a19a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a1e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a19a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010a1e2`

## string_xrefs

- `0x18010a1ab`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180109fe2`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18010a030`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18010a137`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18010a1c4`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18010a23f`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetRegKeyContainingValue(
        const struct Common::StateSeparationRedirectionMapping *a1,
        const unsigned __int16 **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5,
        HKEY *phkResult)
{
  int IsStateSeparationEnabled; // eax
  HKEY v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // r9d
  int v11; // ebx
  int PersistedRegKeyPath; // eax
  HKEY v14; // rdx
  unsigned int v15; // r9d
  unsigned int v16; // edi
  unsigned __int16 *v17; // rbx
  int v18; // eax
  HKEY v19; // rcx
  LSTATUS Value; // eax
  __int64 v21; // rdx
  int v22; // eax
  unsigned __int16 *v23; // rdx
  unsigned int v24; // r9d
  unsigned __int16 *v25; // rcx
  HKEY v26; // rdi
  HKEY v27; // rcx
  HKEY *v28; // rsi
  unsigned __int16 *v29; // rcx
  __int64 i; // rbx
  int appended; // eax
  int v32; // eax
  unsigned int v33; // ecx
  int lpData; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v35[2]; // [rsp+30h] [rbp-30h] BYREF
  int v36; // [rsp+40h] [rbp-20h]
  _QWORD v37[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int16 *v39; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  hKey = (HKEY)a4;
  v39 = a3;
  a5 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&a5);
  v11 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      lpData);
    return (unsigned int)v11;
  }
  if ( a5 )
  {
    v39 = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                            (Common **)&Common::StateSeparation::AppxRoot,
                            a2,
                            v9,
                            &v39);
    v16 = PersistedRegKeyPath;
    v17 = v39;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        lpData);
      goto LABEL_36;
    }
    hKey = 0;
    v18 = Common::RegistryKey::Open(&hKey, v14, v39, v15);
    v16 = v18;
    if ( v18 <= -2147024895 || (unsigned int)(v18 + 2147024892) <= 0x7FF8FFFB )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)(unsigned int)v18,
        lpData);
      v21 = 146;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)v16,
        lpData);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      goto LABEL_36;
    }
    v19 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      Value = RegQueryValueExW(hKey, L"PackageRepositoryRoot", 0, 0, 0, 0);
      v16 = Value;
      if ( !Value || Value == 234 )
      {
        v26 = hKey;
        v27 = 0;
        hKey = 0;
        v28 = phkResult;
        if ( *phkResult != v26 )
        {
          if ( (unsigned __int64)*phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(*phkResult);
            v27 = hKey;
          }
          *v28 = v26;
        }
        if ( (unsigned __int64)v27 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(v27);
        v16 = 0;
LABEL_36:
        v29 = v17;
LABEL_37:
        operator delete(v29);
        return v16;
      }
      if ( (unsigned int)(Value - 2) > 1 )
      {
        if ( Value > 0 )
          v16 = (unsigned __int16)Value | 0x80070000;
        if ( (v16 & 0x80000000) != 0 )
        {
          v21 = 150;
          goto LABEL_34;
        }
      }
      v19 = hKey;
    }
    if ( (unsigned __int64)v19 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(v19);
    operator delete(v17);
  }
  if ( a2 )
  {
    *(_OWORD *)v35 = 0;
    v36 = 0;
    v22 = Common::StringBuffer::SetValueFromString(
            (Common::StringBuffer *)v35,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx");
    v11 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v22,
        lpData);
      v25 = v35[1];
LABEL_24:
      if ( v25 )
        operator delete(v25);
      return (unsigned int)v11;
    }
    for ( i = 0; !i; i = 1 )
    {
      v23 = (unsigned __int16 *)*a2;
      if ( !*a2 )
        break;
      v37[1] = v35;
      v37[0] = &Common::StringBufferBuilder::`vftable';
      v37[2] = v35;
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBufferBuilder *)v37, v23);
      v16 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          lpData);
        v29 = v35[1];
        if ( !v35[1] )
          return v16;
        goto LABEL_37;
      }
    }
    v11 = Common::RegistryKey::Open(phkResult, (HKEY)v23, v35[1], v24);
    v25 = v35[1];
    if ( v11 < 0 )
      goto LABEL_24;
    if ( v35[1] )
      operator delete(v35[1]);
    return 0;
  }
  else
  {
    v32 = Common::RegistryKey::Open(phkResult, v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx", v10);
    v33 = 0;
    if ( v32 < 0 )
      return (unsigned int)v32;
    return v33;
  }
}

```

## disassembly

```asm
0x180109fac  mov     [rsp-18h+arg_0], rbx
0x180109fb1  mov     [rsp-18h+hKey], r9
0x180109fb6  mov     [rsp-18h+arg_10], r8
0x180109fbb  push    rbp
0x180109fbc  push    rsi
0x180109fbd  push    rdi
0x180109fbe  mov     rbp, rsp
0x180109fc1  sub     rsp, 60h
0x180109fc5  mov     rsi, rdx
0x180109fc8  mov     [rbp+arg_20], 0
0x180109fcc  lea     rcx, [rbp+arg_20]; bool *
0x180109fd0  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180109fd5  mov     ebx, eax
0x180109fd7  test    eax, eax
0x180109fd9  jns     short loc_180109FFA
0x180109fdb  mov     rcx, [rbp+18h]; this
0x180109fdf  mov     r9d, eax; char *
0x180109fe2  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109fe9  mov     edx, 8Ah; void *
0x180109fee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ff3  mov     eax, ebx
0x180109ff5  jmp     loc_18010A29E
0x180109ffa  cmp     [rbp+arg_20], 0
0x180109ffe  jz      loc_18010A101
0x18010a004  mov     [rbp+arg_10], 0
0x18010a00c  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x18010a010  mov     rdx, rsi; unsigned __int16 **
0x18010a013  lea     rcx, ?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18010a01a  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x18010a01f  mov     edi, eax
0x18010a021  mov     rbx, [rbp+arg_10]
0x18010a025  test    eax, eax
0x18010a027  jns     short loc_18010A046
0x18010a029  mov     rcx, [rbp+18h]; this
0x18010a02d  mov     r9d, eax; char *
0x18010a030  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x18010a037  mov     edx, 90h; void *
0x18010a03c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a041  jmp     loc_18010A1E9
0x18010a046  mov     [rbp+hKey], 0
0x18010a04e  mov     r8, rbx; unsigned __int16 *
0x18010a051  lea     rcx, [rbp+hKey]; phkResult
0x18010a055  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18010a05a  mov     edi, eax
0x18010a05c  cmp     eax, 80070001h
0x18010a061  jle     loc_18010A1A4
0x18010a067  lea     ecx, [rax+7FF8FFFCh]
0x18010a06d  cmp     ecx, 7FF8FFFBh
0x18010a073  jbe     loc_18010A1A4
0x18010a079  mov     rcx, [rbp+hKey]; hKey
0x18010a07d  lea     rax, [rcx-1]
0x18010a081  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010a085  ja      short loc_18010A0E8
0x18010a087  mov     [rsp+60h+lpcbData], 0; lpcbData
0x18010a090  mov     [rsp+60h+lpData], 0; int
0x18010a099  xor     r9d, r9d; lpType
0x18010a09c  xor     r8d, r8d; lpReserved
0x18010a09f  lea     rdx, ?appRepositoryPath@StateRepository@@3QB_WB; "PackageRepositoryRoot"
0x18010a0a6  call    cs:__imp_RegQueryValueExW
0x18010a0ac  mov     edi, eax
0x18010a0ae  test    eax, eax
0x18010a0b0  jz      loc_18010A160
0x18010a0b6  cmp     eax, 0EAh
0x18010a0bb  jz      loc_18010A160
0x18010a0c1  lea     ecx, [rax-2]
0x18010a0c4  cmp     ecx, 1
0x18010a0c7  jbe     short loc_18010A0E4
0x18010a0c9  test    eax, eax
0x18010a0cb  jle     short loc_18010A0D6
0x18010a0cd  movzx   edi, ax
0x18010a0d0  or      edi, 80070000h
0x18010a0d6  test    edi, edi
0x18010a0d8  jns     short loc_18010A0E4
0x18010a0da  mov     edx, 96h
0x18010a0df  jmp     loc_18010A1C1
0x18010a0e4  mov     rcx, [rbp+hKey]; hKey
0x18010a0e8  lea     rax, [rcx-1]
0x18010a0ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010a0f0  ja      short loc_18010A0F9
0x18010a0f2  call    cs:__imp_RegCloseKey
0x18010a0f8  nop
0x18010a0f9  mov     rcx, rbx; void *
0x18010a0fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a101  test    rsi, rsi
0x18010a104  jz      loc_18010A285
0x18010a10a  xor     eax, eax
0x18010a10c  xorps   xmm0, xmm0
0x18010a10f  movups  xmmword ptr [rbp+var_30], xmm0
0x18010a113  mov     [rbp+var_20], eax
0x18010a116  mov     rdx, cs:off_1801159E0; Src
0x18010a11d  lea     rcx, [rbp+var_30]; this
0x18010a121  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18010a126  mov     ebx, eax
0x18010a128  test    eax, eax
0x18010a12a  jns     loc_18010A1F8
0x18010a130  mov     rcx, [rbp+18h]; this
0x18010a134  mov     r9d, eax; char *
0x18010a137  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x18010a13e  mov     edx, 0A7h; void *
0x18010a143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a148  nop
0x18010a149  mov     rcx, [rbp+var_30+8]; void *
0x18010a14d  test    rcx, rcx
0x18010a150  jz      loc_180109FF3
0x18010a156  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a15b  jmp     loc_180109FF3
0x18010a160  mov     rdi, [rbp+hKey]
0x18010a164  xor     ecx, ecx
0x18010a166  mov     [rbp+hKey], rcx
0x18010a16a  mov     rsi, [rbp+phkResult]
0x18010a16e  mov     rdx, [rsi]
0x18010a171  cmp     rdx, rdi
0x18010a174  jz      short loc_18010A190
0x18010a176  lea     rax, [rdx-1]
0x18010a17a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010a17e  ja      short loc_18010A18D
0x18010a180  mov     rcx, rdx; hKey
0x18010a183  call    cs:__imp_RegCloseKey
0x18010a189  mov     rcx, [rbp+hKey]; hKey
0x18010a18d  mov     [rsi], rdi
0x18010a190  lea     rax, [rcx-1]
0x18010a194  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010a198  ja      short loc_18010A1A0
0x18010a19a  call    cs:__imp_RegCloseKey
0x18010a1a0  xor     edi, edi
0x18010a1a2  jmp     short loc_18010A1E9
0x18010a1a4  mov     rcx, [rbp+18h]; this
0x18010a1a8  mov     r9d, edi; char *
0x18010a1ab  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\common\\regist"...
0x18010a1b2  mov     edx, 5Ah ; 'Z'; void *
0x18010a1b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a1bc  mov     edx, 92h; void *
0x18010a1c1  mov     r9d, edi; char *
0x18010a1c4  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x18010a1cb  mov     rcx, [rbp+18h]; this
0x18010a1cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a1d4  mov     rcx, [rbp+hKey]; hKey
0x18010a1d8  lea     rax, [rcx-1]
0x18010a1dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010a1e0  ja      short loc_18010A1E9
0x18010a1e2  call    cs:__imp_RegCloseKey
0x18010a1e8  nop
0x18010a1e9  mov     rcx, rbx; void *
0x18010a1ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a1f1  mov     eax, edi
0x18010a1f3  jmp     loc_18010A29E
0x18010a1f8  xor     ebx, ebx
0x18010a1fa  cmp     rbx, 1
0x18010a1fe  jnb     short loc_18010A25C
0x18010a200  mov     rdx, [rsi+rbx*8]; unsigned __int16 *
0x18010a204  test    rdx, rdx
0x18010a207  jz      short loc_18010A25C
0x18010a209  lea     rax, [rbp+var_30]
0x18010a20d  mov     [rbp+var_10], rax
0x18010a211  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18010a218  mov     [rbp+var_18], rax
0x18010a21c  lea     rax, [rbp+var_30]
0x18010a220  mov     [rbp+var_8], rax
0x18010a224  lea     rcx, [rbp+var_18]; struct Common::StringBufferBuilder *
0x18010a228  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBufferBuilder *,ushort const *)
0x18010a22d  mov     edi, eax
0x18010a22f  test    eax, eax
0x18010a231  js      short loc_18010A238
0x18010a233  inc     rbx
0x18010a236  jmp     short loc_18010A1FA
0x18010a238  mov     rcx, [rbp+18h]; this
0x18010a23c  mov     r9d, edi; char *
0x18010a23f  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x18010a246  mov     edx, 0AAh; void *
0x18010a24b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a250  nop
0x18010a251  mov     rcx, [rbp+var_30+8]
0x18010a255  test    rcx, rcx
0x18010a258  jz      short loc_18010A1F1
0x18010a25a  jmp     short loc_18010A1EC
0x18010a25c  mov     r8, [rbp+var_30+8]; unsigned __int16 *
0x18010a260  mov     rcx, [rbp+phkResult]; phkResult
0x18010a264  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18010a269  mov     ebx, eax
0x18010a26b  mov     rcx, [rbp+var_30+8]; void *
0x18010a26f  test    eax, eax
0x18010a271  js      loc_18010A14D
0x18010a277  test    rcx, rcx
0x18010a27a  jz      short loc_18010A281
0x18010a27c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a281  xor     eax, eax
0x18010a283  jmp     short loc_18010A29E
0x18010a285  mov     r8, cs:off_1801159E0; unsigned __int16 *
0x18010a28c  mov     rcx, [rbp+phkResult]; phkResult
0x18010a290  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18010a295  xor     ecx, ecx
0x18010a297  test    eax, eax
0x18010a299  cmovs   ecx, eax
0x18010a29c  mov     eax, ecx
0x18010a29e  mov     rbx, [rsp+60h+arg_0]
0x18010a2a6  add     rsp, 60h
0x18010a2aa  pop     rdi
0x18010a2ab  pop     rsi
0x18010a2ac  pop     rbp
0x18010a2ad  retn
```
