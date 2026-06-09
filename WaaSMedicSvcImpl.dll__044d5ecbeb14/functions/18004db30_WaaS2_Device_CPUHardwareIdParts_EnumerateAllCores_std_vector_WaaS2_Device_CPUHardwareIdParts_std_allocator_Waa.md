# WaaS2::Device::CPUHardwareIdParts::EnumerateAllCores(std::vector<WaaS2::Device::CPUHardwareIdParts,std::allocator<WaaS2::Device::CPUHardwareIdParts>> &)

- ea: `0x18004db30`
- end: `0x18004df40`
- name: `?EnumerateAllCores@CPUHardwareIdParts@Device@WaaS2@@SAJAEAV?$vector@VCPUHardwareIdParts@Device@WaaS2@@V?$allocator@VCPUHardwareIdParts@Device@WaaS2@@@std@@@std@@@Z`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18003c6e8`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005bbc`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000c638`
- `0x180041ab4`
- `0x180043b7c`
- `0x1800453a8`
- `0x180045908`
- `0x1800464d4`
- `0x1800473ec`
- `0x180048b98`
- `0x18004db30`
- `0x180052368`
- `0x1800540a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dbb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dbb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004dddd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004dddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dc1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dc1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaaS2::Device::CPUHardwareIdParts::EnumerateAllCores(__int64 a1)
{
  WaaS2::Device::DetectCPUHardwareIdParts *v2; // rsi
  WaaS2::Device::DetectCPUHardwareIdParts *v3; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  DWORD v9; // r14d
  DWORD i; // edx
  __int64 *v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rsi
  char v14; // al
  __int64 *v15; // rbx
  __int64 v16; // rcx
  __int64 **v17; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[28]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+7Ch] [rbp-84h]
  _BYTE v30[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[72]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v32[640]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v33[320]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR Name[8]; // [rsp+5E0h] [rbp+4E0h] BYREF
  __int128 v35; // [rsp+5F0h] [rbp+4F0h]
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+538h]

  v2 = *(WaaS2::Device::DetectCPUHardwareIdParts **)(a1 + 8);
  v3 = *(WaaS2::Device::DetectCPUHardwareIdParts **)a1;
  if ( *(WaaS2::Device::DetectCPUHardwareIdParts **)a1 != v2 )
  {
    do
    {
      WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(v3);
      v3 = (WaaS2::Device::DetectCPUHardwareIdParts *)((char *)v3 + 640);
    }
    while ( v3 != v2 );
    *(_QWORD *)(a1 + 8) = *(_QWORD *)a1;
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Hardware\\Description\\System\\CentralProcessor", 0, 0x20119u, &hKey) )
  {
    WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v33);
    v4 = WaaS2::Device::CPUHardwareIdParts::Init(
           (WaaS2::Device::CPUHardwareIdParts *)v33,
           L"Hardware\\Description\\System\\CentralProcessor\\0");
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B7,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v4,
        phkResult);
      WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v33);
LABEL_7:
      if ( hKey )
        RegCloseKey(hKey);
      return v5;
    }
    v7 = *(_QWORD *)(a1 + 8);
    if ( v7 == *(_QWORD *)(a1 + 16) )
    {
      std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(
        a1,
        *(_QWORD *)(a1 + 8),
        v33);
    }
    else
    {
      WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(v7, v33);
      *(_QWORD *)(a1 + 8) += 640LL;
    }
    WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v33);
  }
  else
  {
    v26 = 0;
    v27 = 0;
    v8 = operator new(0x2E8u);
    *v8 = v8;
    v8[1] = v8;
    v8[2] = v8;
    *((_WORD *)v8 + 12) = 257;
    v26 = v8;
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      *(_OWORD *)Name = 0;
      v35 = 0;
      cchName = 16;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      memset_0(v33, 0, 0x200u);
      if ( (int)StringCchPrintfW(v33, 0x100u, L"%s\\%s", L"Hardware\\Description\\System\\CentralProcessor", Name) >= 0 )
      {
        WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v32);
        if ( WaaS2::Device::CPUHardwareIdParts::Init((WaaS2::Device::CPUHardwareIdParts *)v32, v33) >= 0 )
        {
          WaaS2::Device::CPUIdentityKey::FromParts(v30, v32);
          v12 = v26;
          v13 = v26[1];
          v29 = 0;
          while ( !*(_BYTE *)(v13 + 25) )
          {
            v14 = std::less<WaaS2::Device::CPUIdentityKey>::operator()(v11, v13 + 32, v30);
            if ( !v14 )
              v12 = (_QWORD *)v13;
            v11 = (__int64 *)(v13 + 16);
            if ( !v14 )
              v11 = (__int64 *)v13;
            v13 = *v11;
          }
          if ( *((_BYTE *)v12 + 25)
            || (unsigned __int8)std::less<WaaS2::Device::CPUIdentityKey>::operator()(v11, v30, v12 + 4) )
          {
            v12 = v26;
          }
          if ( v12 == v26 )
            std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::emplace<WaaS2::Device::CPUIdentityKey &,WaaS2::Device::CPUHardwareIdParts>(
              &v26,
              v28,
              v30,
              v32);
          std::wstring::~wstring(v31);
        }
        WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v32);
      }
      ++v9;
    }
    if ( v27 )
    {
      v15 = (__int64 *)*v26;
      while ( !*((_BYTE *)v15 + 25) )
      {
        v16 = *(_QWORD *)(a1 + 8);
        if ( v16 == *(_QWORD *)(a1 + 16) )
        {
          std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(
            a1,
            *(_QWORD *)(a1 + 8),
            v15 + 13);
        }
        else
        {
          WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(v16, v15 + 13);
          *(_QWORD *)(a1 + 8) += 640LL;
        }
        v17 = (__int64 **)v15[2];
        if ( *((_BYTE *)v17 + 25) )
        {
          for ( j = (__int64 *)v15[1]; !*((_BYTE *)j + 25) && v15 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v15 = j;
          v15 = j;
        }
        else
        {
          v15 = (__int64 *)v15[2];
          for ( k = *v17; !*((_BYTE *)k + 25); k = (__int64 *)*k )
            v15 = k;
        }
      }
    }
    else
    {
      WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v32);
      v20 = WaaS2::Device::CPUHardwareIdParts::Init(
              (WaaS2::Device::CPUHardwareIdParts *)v32,
              L"Hardware\\Description\\System\\CentralProcessor\\0");
      v5 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E0,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v20,
          phkResulta);
        WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v32);
        std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::~_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>(&v26);
        goto LABEL_7;
      }
      v21 = *(_QWORD *)(a1 + 8);
      if ( v21 == *(_QWORD *)(a1 + 16) )
      {
        std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(
          a1,
          *(_QWORD *)(a1 + 8),
          v32);
      }
      else
      {
        WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(v21, v32);
        *(_QWORD *)(a1 + 8) += 640LL;
      }
      WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts((WaaS2::Device::DetectCPUHardwareIdParts *)v32);
    }
    std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::~_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>(&v26);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18004db30  mov     [rsp-8+arg_8], rbx
0x18004db35  mov     [rsp-8+arg_10], rsi
0x18004db3a  push    rbp
0x18004db3b  push    rdi
0x18004db3c  push    r12
0x18004db3e  push    r14
0x18004db40  push    r15
0x18004db42  lea     rbp, [rsp-510h]
0x18004db4a  sub     rsp, 610h
0x18004db51  mov     rax, cs:__security_cookie
0x18004db58  xor     rax, rsp
0x18004db5b  mov     [rbp+530h+var_30], rax
0x18004db62  mov     rdi, rcx
0x18004db65  mov     rsi, [rcx+8]
0x18004db69  mov     rbx, [rcx]
0x18004db6c  mov     r12d, 280h
0x18004db72  cmp     rbx, rsi
0x18004db75  jz      short loc_18004DB8E
0x18004db77  mov     rcx, rbx; this
0x18004db7a  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004db7f  add     rbx, r12
0x18004db82  cmp     rbx, rsi
0x18004db85  jnz     short loc_18004DB77
0x18004db87  mov     rax, [rdi]
0x18004db8a  mov     [rdi+8], rax
0x18004db8e  xor     r15d, r15d
0x18004db91  mov     [rsp+630h+hKey], r15
0x18004db96  lea     rax, [rsp+630h+hKey]
0x18004db9b  mov     [rsp+630h+phkResult], rax; int
0x18004dba0  mov     r9d, 20119h; samDesired
0x18004dba6  xor     r8d, r8d; ulOptions
0x18004dba9  lea     rdx, SubKey; "Hardware\\Description\\System\\CentralP"...
0x18004dbb0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004dbb7  call    cs:__imp_RegOpenKeyExW
0x18004dbbd  test    eax, eax
0x18004dbbf  jz      loc_18004DC6B
0x18004dbc5  lea     rcx, [rbp+530h+var_2D0]; this
0x18004dbcc  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(void)
0x18004dbd1  nop
0x18004dbd2  lea     rdx, aHardwareDescri_0; "Hardware\\Description\\System\\CentralP"...
0x18004dbd9  lea     rcx, [rbp+530h+var_2D0]; this
0x18004dbe0  call    ?Init@CPUHardwareIdParts@Device@WaaS2@@QEAAJPEBG@Z; WaaS2::Device::CPUHardwareIdParts::Init(ushort const *)
0x18004dbe5  mov     ebx, eax
0x18004dbe7  test    eax, eax
0x18004dbe9  jns     short loc_18004DC2B
0x18004dbeb  mov     rcx, [rbp+538h]; this
0x18004dbf2  mov     r9d, eax; char *
0x18004dbf5  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004dbfc  mov     edx, 3B7h; void *
0x18004dc01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dc06  nop
0x18004dc07  lea     rcx, [rbp+530h+var_2D0]; this
0x18004dc0e  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004dc13  nop
0x18004dc14  mov     rcx, [rsp+630h+hKey]; hKey
0x18004dc19  test    rcx, rcx
0x18004dc1c  jz      short loc_18004DC24
0x18004dc1e  call    cs:__imp_RegCloseKey
0x18004dc24  mov     eax, ebx
0x18004dc26  jmp     loc_18004DF15
0x18004dc2b  mov     rcx, [rdi+8]
0x18004dc2f  cmp     rcx, [rdi+10h]
0x18004dc33  jz      short loc_18004DC47
0x18004dc35  lea     rdx, [rbp+530h+var_2D0]
0x18004dc3c  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@$$QEAV012@@Z; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(WaaS2::Device::DetectCPUHardwareIdParts &&)
0x18004dc41  add     [rdi+8], r12
0x18004dc45  jmp     short loc_18004DC5A
0x18004dc47  lea     r8, [rbp+530h+var_2D0]
0x18004dc4e  mov     rdx, rcx
0x18004dc51  mov     rcx, rdi
0x18004dc54  call    ??$_Emplace_reallocate@VCPUHardwareIdParts@Device@WaaS2@@@?$vector@VCPUHardwareIdParts@Device@WaaS2@@V?$allocator@VCPUHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAPEAVCPUHardwareIdParts@Device@WaaS2@@QEAV234@$$QEAV234@@Z; std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(WaaS2::Device::CPUHardwareIdParts * const,WaaS2::Device::CPUHardwareIdParts &&)
0x18004dc59  nop
0x18004dc5a  lea     rcx, [rbp+530h+var_2D0]; this
0x18004dc61  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004dc66  jmp     loc_18004DF03
0x18004dc6b  mov     [rsp+630h+var_5E0], r15
0x18004dc70  mov     [rsp+630h+var_5D8], r15
0x18004dc75  mov     ecx, 2E8h; Size
0x18004dc7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004dc7f  mov     [rax], rax
0x18004dc82  mov     [rax+8], rax
0x18004dc86  mov     [rax+10h], rax
0x18004dc8a  mov     word ptr [rax+18h], 101h
0x18004dc90  mov     [rsp+630h+var_5E0], rax
0x18004dc95  mov     r14d, r15d
0x18004dc98  xor     edx, edx
0x18004dc9a  jmp     loc_18004DD9F
0x18004dc9f  xor     edx, edx; Val
0x18004dca1  mov     r8d, 200h; Size
0x18004dca7  lea     rcx, [rbp+530h+var_2D0]; void *
0x18004dcae  call    memset_0
0x18004dcb3  lea     rax, [rbp+530h+Name]
0x18004dcba  mov     [rsp+630h+phkResult], rax
0x18004dcbf  lea     r9, SubKey; "Hardware\\Description\\System\\CentralP"...
0x18004dcc6  lea     r8, aSS; "%s\\%s"
0x18004dccd  mov     edx, 100h; unsigned __int64
0x18004dcd2  lea     rcx, [rbp+530h+var_2D0]; unsigned __int16 *
0x18004dcd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004dcde  test    eax, eax
0x18004dce0  js      loc_18004DD99
0x18004dce6  lea     rcx, [rbp+530h+var_550]; this
0x18004dcea  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(void)
0x18004dcef  nop
0x18004dcf0  lea     rdx, [rbp+530h+var_2D0]; unsigned __int16 *
0x18004dcf7  lea     rcx, [rbp+530h+var_550]; this
0x18004dcfb  call    ?Init@CPUHardwareIdParts@Device@WaaS2@@QEAAJPEBG@Z; WaaS2::Device::CPUHardwareIdParts::Init(ushort const *)
0x18004dd00  test    eax, eax
0x18004dd02  js      loc_18004DD90
0x18004dd08  lea     rdx, [rbp+530h+var_550]
0x18004dd0c  lea     rcx, [rbp+530h+var_5A0]
0x18004dd10  call    ?FromParts@CPUIdentityKey@Device@WaaS2@@SA?AU123@AEBVDetectCPUHardwareIdParts@23@@Z; WaaS2::Device::CPUIdentityKey::FromParts(WaaS2::Device::DetectCPUHardwareIdParts const &)
0x18004dd15  nop
0x18004dd16  mov     rbx, [rsp+630h+var_5E0]
0x18004dd1b  mov     rsi, [rbx+8]
0x18004dd1f  xor     eax, eax
0x18004dd21  mov     [rsp+630h+var_5B4], eax
0x18004dd25  jmp     short loc_18004DD45
0x18004dd27  lea     rdx, [rsi+20h]
0x18004dd2b  lea     r8, [rbp+530h+var_5A0]
0x18004dd2f  call    ??R?$less@UCPUIdentityKey@Device@WaaS2@@@std@@QEBA_NAEBUCPUIdentityKey@Device@WaaS2@@0@Z; std::less<WaaS2::Device::CPUIdentityKey>::operator()(WaaS2::Device::CPUIdentityKey const &,WaaS2::Device::CPUIdentityKey const &)
0x18004dd34  test    al, al
0x18004dd36  cmovz   rbx, rsi
0x18004dd3a  lea     rcx, [rsi+10h]
0x18004dd3e  cmovz   rcx, rsi
0x18004dd42  mov     rsi, [rcx]
0x18004dd45  cmp     [rsi+19h], r15b
0x18004dd49  jz      short loc_18004DD27
0x18004dd4b  cmp     [rbx+19h], r15b
0x18004dd4f  jnz     short loc_18004DD62
0x18004dd51  lea     r8, [rbx+20h]
0x18004dd55  lea     rdx, [rbp+530h+var_5A0]
0x18004dd59  call    ??R?$less@UCPUIdentityKey@Device@WaaS2@@@std@@QEBA_NAEBUCPUIdentityKey@Device@WaaS2@@0@Z; std::less<WaaS2::Device::CPUIdentityKey>::operator()(WaaS2::Device::CPUIdentityKey const &,WaaS2::Device::CPUIdentityKey const &)
0x18004dd5e  test    al, al
0x18004dd60  jz      short loc_18004DD67
0x18004dd62  mov     rbx, [rsp+630h+var_5E0]
0x18004dd67  cmp     rbx, [rsp+630h+var_5E0]
0x18004dd6c  jnz     short loc_18004DD86
0x18004dd6e  lea     r9, [rbp+530h+var_550]
0x18004dd72  lea     r8, [rbp+530h+var_5A0]
0x18004dd76  lea     rdx, [rsp+630h+var_5D0]
0x18004dd7b  lea     rcx, [rsp+630h+var_5E0]
0x18004dd80  call    ??$emplace@AEAUCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@@?$_Tree@V?$_Tmap_traits@UCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@U?$less@UCPUIdentityKey@Device@WaaS2@@@std@@V?$allocator@U?$pair@$$CBUCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@@std@@@std@@@std@@@std@@_N@1@AEAUCPUIdentityKey@Device@WaaS2@@$$QEAVCPUHardwareIdParts@45@@Z; std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::emplace<WaaS2::Device::CPUIdentityKey &,WaaS2::Device::CPUHardwareIdParts>(WaaS2::Device::CPUIdentityKey &,WaaS2::Device::CPUHardwareIdParts &&)
0x18004dd85  nop
0x18004dd86  lea     rcx, [rbp+530h+var_598]; void *
0x18004dd8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004dd8f  nop
0x18004dd90  lea     rcx, [rbp+530h+var_550]; this
0x18004dd94  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004dd99  inc     r14d
0x18004dd9c  mov     edx, r14d; dwIndex
0x18004dd9f  mov     [rsp+630h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18004dda4  mov     [rsp+630h+lpcchClass], r15; lpcchClass
0x18004dda9  mov     [rsp+630h+lpClass], r15; lpClass
0x18004ddae  xorps   xmm0, xmm0
0x18004ddb1  mov     [rsp+630h+phkResult], r15; int
0x18004ddb6  movups  xmmword ptr [rbp+530h+Name], xmm0
0x18004ddbd  movups  [rbp+530h+var_40], xmm0
0x18004ddc4  mov     [rsp+630h+cchName], 10h
0x18004ddcc  lea     r9, [rsp+630h+cchName]; lpcchName
0x18004ddd1  lea     r8, [rbp+530h+Name]; lpName
0x18004ddd8  mov     rcx, [rsp+630h+hKey]; hKey
0x18004dddd  call    cs:__imp_RegEnumKeyExW
0x18004dde3  test    eax, eax
0x18004dde5  jz      loc_18004DC9F
0x18004ddeb  cmp     [rsp+630h+var_5D8], r15
0x18004ddf0  jz      short loc_18004DE70
0x18004ddf2  mov     rbx, [rsp+630h+var_5E0]
0x18004ddf7  mov     rbx, [rbx]
0x18004ddfa  cmp     [rbx+19h], r15b
0x18004ddfe  jnz     loc_18004DEF8
0x18004de04  lea     rdx, [rbx+68h]
0x18004de08  mov     rcx, [rdi+8]
0x18004de0c  cmp     rcx, [rdi+10h]
0x18004de10  jz      short loc_18004DE1D
0x18004de12  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@$$QEAV012@@Z; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(WaaS2::Device::DetectCPUHardwareIdParts &&)
0x18004de17  add     [rdi+8], r12
0x18004de1b  jmp     short loc_18004DE2B
0x18004de1d  mov     r8, rdx
0x18004de20  mov     rdx, rcx
0x18004de23  mov     rcx, rdi
0x18004de26  call    ??$_Emplace_reallocate@VCPUHardwareIdParts@Device@WaaS2@@@?$vector@VCPUHardwareIdParts@Device@WaaS2@@V?$allocator@VCPUHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAPEAVCPUHardwareIdParts@Device@WaaS2@@QEAV234@$$QEAV234@@Z; std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(WaaS2::Device::CPUHardwareIdParts * const,WaaS2::Device::CPUHardwareIdParts &&)
0x18004de2b  mov     rcx, [rbx+10h]
0x18004de2f  cmp     [rcx+19h], r15b
0x18004de33  jz      short loc_18004DE53
0x18004de35  mov     rax, [rbx+8]
0x18004de39  jmp     short loc_18004DE48
0x18004de3b  cmp     rbx, [rax+10h]
0x18004de3f  jnz     short loc_18004DE4E
0x18004de41  mov     rbx, rax
0x18004de44  mov     rax, [rax+8]
0x18004de48  cmp     [rax+19h], r15b
0x18004de4c  jz      short loc_18004DE3B
0x18004de4e  mov     rbx, rax
0x18004de51  jmp     short loc_18004DDFA
0x18004de53  mov     rbx, rcx
0x18004de56  mov     rcx, [rcx]
0x18004de59  cmp     [rcx+19h], r15b
0x18004de5d  jnz     short loc_18004DDFA
0x18004de5f  mov     rbx, rcx
0x18004de62  mov     rax, [rcx]
0x18004de65  mov     rcx, rax
0x18004de68  cmp     [rax+19h], r15b
0x18004de6c  jz      short loc_18004DE5F
0x18004de6e  jmp     short loc_18004DDFA
0x18004de70  lea     rcx, [rbp+530h+var_550]; this
0x18004de74  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(void)
0x18004de79  nop
0x18004de7a  lea     rdx, aHardwareDescri_0; "Hardware\\Description\\System\\CentralP"...
0x18004de81  lea     rcx, [rbp+530h+var_550]; this
0x18004de85  call    ?Init@CPUHardwareIdParts@Device@WaaS2@@QEAAJPEBG@Z; WaaS2::Device::CPUHardwareIdParts::Init(ushort const *)
0x18004de8a  mov     ebx, eax
0x18004de8c  test    eax, eax
0x18004de8e  jns     short loc_18004DEC5
0x18004de90  mov     rcx, [rbp+538h]; this
0x18004de97  mov     r9d, eax; char *
0x18004de9a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004dea1  mov     edx, 3E0h; void *
0x18004dea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004deab  nop
0x18004deac  lea     rcx, [rbp+530h+var_550]; this
0x18004deb0  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004deb5  nop
0x18004deb6  lea     rcx, [rsp+630h+var_5E0]
0x18004debb  call    ??1?$_Tree@V?$_Tmap_traits@UCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@U?$less@UCPUIdentityKey@Device@WaaS2@@@std@@V?$allocator@U?$pair@$$CBUCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::~_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>(void)
0x18004dec0  jmp     loc_18004DC14
0x18004dec5  mov     rcx, [rdi+8]
0x18004dec9  cmp     rcx, [rdi+10h]
0x18004decd  jz      short loc_18004DEDE
0x18004decf  lea     rdx, [rbp+530h+var_550]
0x18004ded3  call    ??0DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@$$QEAV012@@Z; WaaS2::Device::DetectCPUHardwareIdParts::DetectCPUHardwareIdParts(WaaS2::Device::DetectCPUHardwareIdParts &&)
0x18004ded8  add     [rdi+8], r12
0x18004dedc  jmp     short loc_18004DEEE
0x18004dede  lea     r8, [rbp+530h+var_550]
0x18004dee2  mov     rdx, rcx
0x18004dee5  mov     rcx, rdi
0x18004dee8  call    ??$_Emplace_reallocate@VCPUHardwareIdParts@Device@WaaS2@@@?$vector@VCPUHardwareIdParts@Device@WaaS2@@V?$allocator@VCPUHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAPEAVCPUHardwareIdParts@Device@WaaS2@@QEAV234@$$QEAV234@@Z; std::vector<WaaS2::Device::CPUHardwareIdParts>::_Emplace_reallocate<WaaS2::Device::CPUHardwareIdParts>(WaaS2::Device::CPUHardwareIdParts * const,WaaS2::Device::CPUHardwareIdParts &&)
0x18004deed  nop
0x18004deee  lea     rcx, [rbp+530h+var_550]; this
0x18004def2  call    ??1DetectCPUHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectCPUHardwareIdParts::~DetectCPUHardwareIdParts(void)
0x18004def7  nop
0x18004def8  lea     rcx, [rsp+630h+var_5E0]
0x18004defd  call    ??1?$_Tree@V?$_Tmap_traits@UCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@U?$less@UCPUIdentityKey@Device@WaaS2@@@std@@V?$allocator@U?$pair@$$CBUCPUIdentityKey@Device@WaaS2@@VCPUHardwareIdParts@23@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>::~_Tree<std::_Tmap_traits<WaaS2::Device::CPUIdentityKey,WaaS2::Device::CPUHardwareIdParts,std::less<WaaS2::Device::CPUIdentityKey>,std::allocator<std::pair<WaaS2::Device::CPUIdentityKey const,WaaS2::Device::CPUHardwareIdParts>>,0>>(void)
0x18004df02  nop
0x18004df03  mov     rcx, [rsp+630h+hKey]; hKey
0x18004df08  test    rcx, rcx
0x18004df0b  jz      short loc_18004DF13
0x18004df0d  call    cs:__imp_RegCloseKey
0x18004df13  xor     eax, eax
0x18004df15  mov     rcx, [rbp+530h+var_30]
0x18004df1c  xor     rcx, rsp; StackCookie
0x18004df1f  call    __security_check_cookie
0x18004df24  lea     r11, [rsp+630h+var_20]
0x18004df2c  mov     rbx, [r11+38h]
0x18004df30  mov     rsi, [r11+40h]
0x18004df34  mov     rsp, r11
0x18004df37  pop     r15
0x18004df39  pop     r14
0x18004df3b  pop     r12
0x18004df3d  pop     rdi
0x18004df3e  pop     rbp
0x18004df3f  retn
```
