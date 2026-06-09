# RegisterAppXPackageIfNecessary2

- ea: `0x180025e20`
- end: `0x180026083`
- name: `RegisterAppXPackageIfNecessary2`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008dda0`

## callees

- `0x18000b5c0`
- `0x1800174e0`
- `0x180025e20`
- `0x180026090`
- `0x180026580`
- `0x180027890`
- `0x1800367e4`
- `0x180043f90`
- `0x180056208`
- `0x18005e7cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002604f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002604f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026063`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x180025eac`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x180025eac`

## string_xrefs

- `0x180025e73`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x180025fd6`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18002600f`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegisterAppXPackageIfNecessary2(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        _DWORD *a5)
{
  char v9; // si
  int PackageFamilyAndPraid; // eax
  unsigned __int16 *v11; // rbx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  unsigned __int16 **v14; // r9
  int v15; // edi
  __int64 v16; // rdx
  const char *v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 result; // rax
  unsigned __int16 **v22; // [rsp+20h] [rbp-98h]
  __int64 v23; // [rsp+28h] [rbp-90h]
  bool v24[4]; // [rsp+50h] [rbp-68h] BYREF
  int v25; // [rsp+54h] [rbp-64h] BYREF
  int v26; // [rsp+58h] [rbp-60h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-58h] BYREF
  LPVOID v28; // [rsp+68h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v9 = 0;
  v27 = 0;
  v24[0] = 0;
  v26 = 0;
  pv = 0;
  v28 = 0;
  try
  {
    PackageFamilyAndPraid = GetPackageFamilyAndPraid(a2, (unsigned __int16 **)&v28, (unsigned __int16 **)&pv);
    if ( PackageFamilyAndPraid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
        (const char *)(unsigned int)PackageFamilyAndPraid,
        (int)v22);
    v11 = 0;
    v27 = 0;
    v25 = 0;
    v24[0] = 0;
    if ( (unsigned __int8)IsEnsurePackageRegisteredForMultiUserSessionPresent(retaddr) )
    {
      v12 = EnsurePackageRegisteredForMultiUserSession(a2, v28, a1);
      v15 = v12;
      if ( v12 < 0 )
      {
        v16 = 520;
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
          (const char *)(unsigned int)v12,
          (int)v22);
LABEL_19:
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16F,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
            (const char *)(unsigned int)v15,
            (int)v22);
        if ( a3 )
        {
          if ( a4 )
          {
            v20 = StringCchCopyW(a4, *a3, v11);
            if ( v20 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x173,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
                (const char *)(unsigned int)v20,
                (int)v22);
          }
        }
        *a5 = (v9 & 0x21) != 0;
        if ( pv )
          CoTaskMemFree(pv);
        if ( v11 )
          CoTaskMemFree(v11);
        if ( v28 )
          CoTaskMemFree(v28);
        return 0;
      }
      v18 = DevPlat::Shared::PraidAndPackageInfoFromAppId(a2, v13, &v27, v14, v22);
      v15 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x209,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
          (const char *)(unsigned int)v18,
          (int)v22);
        v11 = v27;
        goto LABEL_19;
      }
      v11 = v27;
      v12 = QuirkUseUAPForLegacyImmersiveApplication(a2, v27, v24);
      v15 = v12;
      if ( v12 < 0 )
      {
        v16 = 522;
        goto LABEL_7;
      }
      v9 = 2;
    }
    else
    {
      LODWORD(v23) = 0;
      LODWORD(v22) = 0;
      v19 = EnsurePackageRegistered(a2, v28, a1, L"Windows.Launch", (__int64)v22, v23, &v27, v24, (__int64)&v25, &v26);
      v15 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
          (const char *)(unsigned int)v19,
          (int)v22);
        v11 = v27;
        v9 = v25;
        goto LABEL_19;
      }
      v11 = v27;
      v9 = v25;
    }
    v12 = CheckAppPackageForRemediationBeforeActivate(v11);
    v15 = v12;
    if ( v12 >= 0 )
    {
      v15 = 0;
      goto LABEL_19;
    }
    v16 = 540;
    goto LABEL_7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x17A,
                           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\"
                                         "activationextensions.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x180025e20  mov     rax, rsp
0x180025e23  push    rbx
0x180025e24  push    rsi
0x180025e25  push    rdi
0x180025e26  push    r12
0x180025e28  push    r13
0x180025e2a  push    r14
0x180025e2c  sub     rsp, 88h
0x180025e33  mov     r12, r9
0x180025e36  mov     r13, r8
0x180025e39  mov     r14, rdx
0x180025e3c  mov     rdi, rcx
0x180025e3f  xor     esi, esi
0x180025e41  mov     [rax-58h], rsi
0x180025e45  mov     [rax-68h], sil
0x180025e49  mov     [rax-60h], esi
0x180025e4c  mov     [rax-48h], rsi
0x180025e50  mov     [rax-50h], rsi
0x180025e54  lea     r8, [rax-48h]; unsigned __int16 **
0x180025e58  lea     rdx, [rax-50h]; unsigned __int16 **
0x180025e5c  mov     rcx, r14; unsigned __int16 *
0x180025e5f  call    ?GetPackageFamilyAndPraid@@YAJPEBGPEAPEAG1@Z; GetPackageFamilyAndPraid(ushort const *,ushort * *,ushort * *)
0x180025e64  mov     rcx, [rsp+0B8h]; this
0x180025e6c  test    eax, eax
0x180025e6e  jns     short loc_180025E84
0x180025e70  mov     r9d, eax; char *
0x180025e73  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180025e7a  mov     edx, 163h; void *
0x180025e7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025e84  mov     rbx, rsi
0x180025e87  mov     [rsp+0B8h+var_58], rbx
0x180025e8c  mov     [rsp+0B8h+var_64], esi
0x180025e90  mov     [rsp+0B8h+var_68], bl
0x180025e94  call    IsEnsurePackageRegisteredForMultiUserSessionPresent
0x180025e99  mov     r8, rdi
0x180025e9c  mov     rdx, [rsp+0B8h+var_50]
0x180025ea1  mov     rcx, r14
0x180025ea4  test    al, al
0x180025ea6  jz      loc_180025F3B
0x180025eac  call    cs:__imp_EnsurePackageRegisteredForMultiUserSession
0x180025eb2  mov     edi, eax
0x180025eb4  test    eax, eax
0x180025eb6  jns     short loc_180025ED9
0x180025eb8  mov     edx, 208h; void *
0x180025ebd  mov     rcx, [rsp+0B8h]; this
0x180025ec5  mov     r9d, eax; char *
0x180025ec8  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180025ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ed4  jmp     loc_180025FC7
0x180025ed9  lea     r8, [rsp+0B8h+var_58]; unsigned __int16 **
0x180025ede  mov     rcx, r14; applicationUserModelId
0x180025ee1  call    ?PraidAndPackageInfoFromAppId@Shared@DevPlat@@YAJPEBGPEAPEAG11@Z; DevPlat::Shared::PraidAndPackageInfoFromAppId(ushort const *,ushort * *,ushort * *,ushort * *)
0x180025ee6  mov     edi, eax
0x180025ee8  test    eax, eax
0x180025eea  jns     short loc_180025F12
0x180025eec  mov     rcx, [rsp+0B8h]; this
0x180025ef4  mov     r9d, eax; char *
0x180025ef7  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180025efe  mov     edx, 209h; void *
0x180025f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f08  mov     rbx, [rsp+0B8h+var_58]
0x180025f0d  jmp     loc_180025FC7
0x180025f12  lea     r8, [rsp+0B8h+var_68]; bool *
0x180025f17  mov     rbx, [rsp+0B8h+var_58]
0x180025f1c  mov     rdx, rbx; unsigned __int16 *
0x180025f1f  mov     rcx, r14; unsigned __int16 *
0x180025f22  call    ?QuirkUseUAPForLegacyImmersiveApplication@@YAJPEBG0PEA_N@Z; QuirkUseUAPForLegacyImmersiveApplication(ushort const *,ushort const *,bool *)
0x180025f27  mov     edi, eax
0x180025f29  test    eax, eax
0x180025f2b  jns     short loc_180025F34
0x180025f2d  mov     edx, 20Ah
0x180025f32  jmp     short loc_180025EBD
0x180025f34  mov     esi, 2
0x180025f39  jmp     short loc_180025FAD
0x180025f3b  lea     rax, [rsp+0B8h+var_60]
0x180025f40  mov     [rsp+0B8h+var_70], rax
0x180025f45  lea     rax, [rsp+0B8h+var_64]
0x180025f4a  mov     [rsp+0B8h+var_78], rax
0x180025f4f  lea     rax, [rsp+0B8h+var_68]
0x180025f54  mov     [rsp+0B8h+var_80], rax
0x180025f59  lea     rax, [rsp+0B8h+var_58]
0x180025f5e  mov     [rsp+0B8h+var_88], rax
0x180025f63  mov     dword ptr [rsp+0B8h+var_90], ebx
0x180025f67  mov     dword ptr [rsp+0B8h+var_98], ebx; int
0x180025f6b  lea     r9, String2; "Windows.Launch"
0x180025f72  call    EnsurePackageRegistered
0x180025f77  mov     edi, eax
0x180025f79  test    eax, eax
0x180025f7b  jns     short loc_180025FA4
0x180025f7d  mov     rcx, [rsp+0B8h]; this
0x180025f85  mov     r9d, eax; char *
0x180025f88  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180025f8f  mov     edx, 219h; void *
0x180025f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f99  mov     rbx, [rsp+0B8h+var_58]
0x180025f9e  mov     esi, [rsp+0B8h+var_64]
0x180025fa2  jmp     short loc_180025FC7
0x180025fa4  mov     rbx, [rsp+0B8h+var_58]
0x180025fa9  mov     esi, [rsp+0B8h+var_64]
0x180025fad  mov     rcx, rbx; unsigned __int16 *
0x180025fb0  call    ?CheckAppPackageForRemediationBeforeActivate@@YAJPEBG@Z; CheckAppPackageForRemediationBeforeActivate(ushort const *)
0x180025fb5  mov     edi, eax
0x180025fb7  test    eax, eax
0x180025fb9  jns     short loc_180025FC5
0x180025fbb  mov     edx, 21Ch
0x180025fc0  jmp     loc_180025EBD
0x180025fc5  xor     edi, edi
0x180025fc7  mov     rcx, [rsp+0B8h]; this
0x180025fcf  test    edi, edi
0x180025fd1  jns     short loc_180025FE7
0x180025fd3  mov     r9d, edi; char *
0x180025fd6  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180025fdd  mov     edx, 16Fh; void *
0x180025fe2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025fe7  test    r13, r13
0x180025fea  jz      short loc_180026020
0x180025fec  test    r12, r12
0x180025fef  jz      short loc_180026020
0x180025ff1  mov     edx, [r13+0]; unsigned __int64
0x180025ff5  mov     r8, rbx; unsigned __int16 *
0x180025ff8  mov     rcx, r12; unsigned __int16 *
0x180025ffb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026000  mov     rcx, [rsp+0B8h]; this
0x180026008  test    eax, eax
0x18002600a  jns     short loc_180026020
0x18002600c  mov     r9d, eax; char *
0x18002600f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180026016  mov     edx, 173h; void *
0x18002601b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026020  test    sil, 21h
0x180026024  mov     ecx, 0
0x180026029  setnz   cl
0x18002602c  mov     rax, [rsp+0B8h+arg_20]
0x180026034  mov     [rax], ecx
0x180026036  mov     rcx, [rsp+0B8h+pv]; pv
0x18002603b  test    rcx, rcx
0x18002603e  jz      short loc_180026047
0x180026040  call    cs:__imp_CoTaskMemFree
0x180026046  nop
0x180026047  test    rbx, rbx
0x18002604a  jz      short loc_180026056
0x18002604c  mov     rcx, rbx; pv
0x18002604f  call    cs:__imp_CoTaskMemFree
0x180026055  nop
0x180026056  cmp     [rsp+0B8h+var_50], 0
0x18002605c  jz      short loc_180026069
0x18002605e  mov     rcx, [rsp+0B8h+var_50]; pv
0x180026063  call    cs:__imp_CoTaskMemFree
0x180026069  xor     eax, eax
0x18002606b  jmp     short loc_180026071
0x18002606d  mov     eax, [rsp+0B8h+var_60]
0x180026071  add     rsp, 88h
0x180026078  pop     r14
0x18002607a  pop     r13
0x18002607c  pop     r12
0x18002607e  pop     rdi
0x18002607f  pop     rsi
0x180026080  pop     rbx
0x180026081  retn
```
