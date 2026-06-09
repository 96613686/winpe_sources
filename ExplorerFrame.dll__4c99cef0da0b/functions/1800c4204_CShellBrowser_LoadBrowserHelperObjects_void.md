# CShellBrowser::_LoadBrowserHelperObjects(void)

- ea: `0x1800c4204`
- end: `0x1800c4452`
- name: `?_LoadBrowserHelperObjects@CShellBrowser@@AEAAHXZ`
- size: `590`
- prototype: `__int64 __fastcall(CShellBrowser *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180125924`

## callees

- `0x180052f80`
- `0x1800c4204`
- `0x1800c4458`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x1800c431b`
- `SHCORE!SHGetValueW` at `0x1800c431b`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800c434d`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800c434d`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800c433d`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800c433d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c43a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c43a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c42b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c42b3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c42f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c42f0`
- `USER32!GetSystemMetrics` at `0x1800c4278`
- `USER32!GetSystemMetrics` at `0x1800c4278`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c4431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c4431`
- `apphelp!ApphelpCheckShellObject` at `0x1800c4364`
- `apphelp!ApphelpCheckShellObject` at `0x1800c4364`
- `urlmon!__imp_CoInternetCreateExtension` at `0x1800c4392`
- `urlmon!__imp_CoInternetCreateExtension` at `0x1800c4392`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellBrowser::_LoadBrowserHelperObjects(
        CShellBrowser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned int v6; // ebx
  DWORD v7; // r14d
  DWORD i; // edx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, _QWORD, _QWORD *); // rbx
  _QWORD *v11; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG pullFlags; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  IID ObjectCLSID; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[64]; // [rsp+A0h] [rbp-60h] BYREF

  hKey = 0;
  if ( !(unsigned int)IERegGetBoolWithPoliciesW((const unsigned __int16 *)this, a2, a3, a4) || GetSystemMetrics(67) )
    return 1;
  v6 = 0;
  if ( *((_QWORD *)this + 44)
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Browser Helper Objects",
          0,
          8u,
          &hKey) )
  {
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchName = 64;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( SHGetValueW(hKey, Name, L"NoExplorer", 0, 0, 0) )
      {
        ObjectCLSID = 0;
        v14 = 0;
        pullFlags = 0;
        if ( (unsigned int)GUIDFromStringW(Name, &ObjectCLSID) )
        {
          if ( (SHGetObjectCompatFlags(0, &ObjectCLSID) & 4) == 0
            && ApphelpCheckShellObject(&ObjectCLSID, 1, &pullFlags)
            && (int)CoInternetCreateExtension(&ObjectCLSID, 0, 1, 3, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v14) >= 0 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, *((_QWORD *)this + 44));
            v15[0] = 13;
            v15[1] = v14;
            v9 = *((_QWORD *)this + 44);
            v10 = *(void (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v9 + 272LL);
            v11 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, Name);
            v15[2] = 0;
            v10(v9, *v11, v15);
            SysFreeString(bstrString);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            v6 = 1;
          }
        }
      }
      ++v7;
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x1800c4204  mov     [rsp-8+arg_8], rbx
0x1800c4209  mov     [rsp-8+arg_10], rdi
0x1800c420e  push    rbp
0x1800c420f  push    r12
0x1800c4211  push    r13
0x1800c4213  push    r14
0x1800c4215  push    r15
0x1800c4217  lea     rbp, [rsp-30h]
0x1800c421c  sub     rsp, 130h
0x1800c4223  mov     rax, cs:__security_cookie
0x1800c422a  xor     rax, rsp
0x1800c422d  mov     [rbp+50h+var_30], rax
0x1800c4231  mov     r15, rcx
0x1800c4234  xor     r13d, r13d
0x1800c4237  mov     [rsp+150h+hKey], r13
0x1800c423c  call    ?IERegGetBoolWithPoliciesW@@YAHPEBG00H@Z; IERegGetBoolWithPoliciesW(ushort const *,ushort const *,ushort const *,int)
0x1800c4241  test    eax, eax
0x1800c4243  jnz     short loc_1800C4273
0x1800c4245  mov     eax, 1
0x1800c424a  mov     rcx, [rbp+50h+var_30]
0x1800c424e  xor     rcx, rsp; StackCookie
0x1800c4251  call    __security_check_cookie
0x1800c4256  lea     r11, [rsp+150h+var_20]
0x1800c425e  mov     rbx, [r11+38h]
0x1800c4262  mov     rdi, [r11+40h]
0x1800c4266  mov     rsp, r11
0x1800c4269  pop     r15
0x1800c426b  pop     r14
0x1800c426d  pop     r13
0x1800c426f  pop     r12
0x1800c4271  pop     rbp
0x1800c4272  retn
0x1800c4273  mov     ecx, 43h ; 'C'; nIndex
0x1800c4278  call    cs:__imp_GetSystemMetrics
0x1800c427e  test    eax, eax
0x1800c4280  jnz     short loc_1800C4245
0x1800c4282  mov     ebx, r13d
0x1800c4285  cmp     [r15+160h], r13
0x1800c428c  jz      loc_1800C43AD
0x1800c4292  lea     rax, [rsp+150h+hKey]
0x1800c4297  mov     [rsp+150h+phkResult], rax; phkResult
0x1800c429c  mov     r9d, 8; samDesired
0x1800c42a2  xor     r8d, r8d; ulOptions
0x1800c42a5  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c42ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c42b3  call    cs:__imp_RegOpenKeyExW
0x1800c42b9  test    eax, eax
0x1800c42bb  jnz     loc_1800C43AD
0x1800c42c1  mov     r14d, r13d
0x1800c42c4  xor     edx, edx; dwIndex
0x1800c42c6  mov     [rsp+150h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800c42cb  mov     [rsp+150h+lpcchClass], r13; lpcchClass
0x1800c42d0  mov     [rsp+150h+lpClass], r13; lpClass
0x1800c42d5  mov     [rsp+150h+phkResult], r13; lpReserved
0x1800c42da  mov     [rsp+150h+cchName], 40h ; '@'
0x1800c42e2  lea     r9, [rsp+150h+cchName]; lpcchName
0x1800c42e7  lea     r8, [rbp+50h+Name]; lpName
0x1800c42eb  mov     rcx, [rsp+150h+hKey]; hKey
0x1800c42f0  call    cs:__imp_RegEnumKeyExW
0x1800c42f6  mov     rcx, [rsp+150h+hKey]; hKey
0x1800c42fb  test    eax, eax
0x1800c42fd  jnz     loc_1800C43A7
0x1800c4303  mov     [rsp+150h+lpClass], r13; pcbData
0x1800c4308  mov     [rsp+150h+phkResult], r13; pvData
0x1800c430d  xor     r9d, r9d; pdwType
0x1800c4310  lea     r8, aNoexplorer; "NoExplorer"
0x1800c4317  lea     rdx, [rbp+50h+Name]; pszSubKey
0x1800c431b  call    cs:__imp_SHGetValueW
0x1800c4321  test    eax, eax
0x1800c4323  jz      short loc_1800C439C
0x1800c4325  xorps   xmm0, xmm0
0x1800c4328  movups  xmmword ptr [rbp+50h+ObjectCLSID.Data1], xmm0
0x1800c432c  mov     [rsp+150h+var_100], r13
0x1800c4331  mov     [rbp+50h+pullFlags], r13
0x1800c4335  lea     rdx, [rbp+50h+ObjectCLSID]
0x1800c4339  lea     rcx, [rbp+50h+Name]
0x1800c433d  call    cs:__imp_GUIDFromStringW
0x1800c4343  test    eax, eax
0x1800c4345  jz      short loc_1800C439C
0x1800c4347  lea     rdx, [rbp+50h+ObjectCLSID]
0x1800c434b  xor     ecx, ecx
0x1800c434d  call    cs:__imp_SHGetObjectCompatFlags
0x1800c4353  test    al, 4
0x1800c4355  jnz     short loc_1800C439C
0x1800c4357  lea     r8, [rbp+50h+pullFlags]; pullFlags
0x1800c435b  mov     edx, 1; bShimIfNecessary
0x1800c4360  lea     rcx, [rbp+50h+ObjectCLSID]; ObjectCLSID
0x1800c4364  call    cs:__imp_ApphelpCheckShellObject
0x1800c436a  test    eax, eax
0x1800c436c  jz      short loc_1800C439C
0x1800c436e  lea     rax, [rsp+150h+var_100]
0x1800c4373  mov     [rsp+150h+lpClass], rax
0x1800c4378  lea     rax, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x1800c437f  mov     [rsp+150h+phkResult], rax
0x1800c4384  xor     edx, edx
0x1800c4386  lea     r9d, [rdx+3]
0x1800c438a  lea     r8d, [rdx+1]
0x1800c438e  lea     rcx, [rbp+50h+ObjectCLSID]
0x1800c4392  call    cs:__imp_CoInternetCreateExtension
0x1800c4398  test    eax, eax
0x1800c439a  jns     short loc_1800C43B4
0x1800c439c  inc     r14d
0x1800c439f  mov     edx, r14d
0x1800c43a2  jmp     loc_1800C42C6
0x1800c43a7  call    cs:__imp_RegCloseKey
0x1800c43ad  mov     eax, ebx
0x1800c43af  jmp     loc_1800C424A
0x1800c43b4  mov     rcx, [rsp+150h+var_100]
0x1800c43b9  mov     rax, [rcx]
0x1800c43bc  mov     rdx, [r15+160h]
0x1800c43c3  mov     rax, [rax+18h]
0x1800c43c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c43cc  xorps   xmm0, xmm0
0x1800c43cf  xor     r12d, r12d
0x1800c43d2  movups  [rsp+150h+var_F0], xmm0
0x1800c43d7  lea     eax, [r12+0Dh]
0x1800c43dc  mov     word ptr [rsp+150h+var_F0], ax
0x1800c43e1  mov     rax, [rsp+150h+var_100]
0x1800c43e6  mov     qword ptr [rsp+150h+var_F0+8], rax
0x1800c43eb  mov     rdi, [r15+160h]
0x1800c43f2  mov     rax, [rdi]
0x1800c43f5  mov     rbx, [rax+110h]
0x1800c43fc  lea     rdx, [rbp+50h+Name]; unsigned __int16 *
0x1800c4400  lea     rcx, [rbp+50h+bstrString]; this
0x1800c4404  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800c4409  nop
0x1800c440a  movups  xmm0, [rsp+150h+var_F0]
0x1800c440f  movaps  [rsp+150h+var_F0], xmm0
0x1800c4414  mov     [rsp+150h+var_E0], r12
0x1800c4419  lea     r8, [rsp+150h+var_F0]
0x1800c441e  mov     rdx, [rax]
0x1800c4421  mov     rcx, rdi
0x1800c4424  mov     rax, rbx
0x1800c4427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c442c  nop
0x1800c442d  mov     rcx, [rbp+50h+bstrString]; bstrString
0x1800c4431  call    cs:__imp_SysFreeString
0x1800c4437  mov     rcx, [rsp+150h+var_100]
0x1800c443c  mov     rax, [rcx]
0x1800c443f  mov     rax, [rax+10h]
0x1800c4443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4448  lea     ebx, [r12+1]
0x1800c444d  jmp     loc_1800C439C
```
