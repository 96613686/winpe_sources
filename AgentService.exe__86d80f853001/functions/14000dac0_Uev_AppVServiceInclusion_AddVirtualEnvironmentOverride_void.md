# Uev::AppVServiceInclusion::AddVirtualEnvironmentOverride(void)

- ea: `0x14000dac0`
- end: `0x14000de78`
- name: `?AddVirtualEnvironmentOverride@AppVServiceInclusion@Uev@@MEAAJXZ`
- size: `952`
- prototype: `__int64 __fastcall(Uev::AppVServiceInclusion *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1400039f0`
- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c078`
- `0x14000c124`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000c4c8`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x14000dac0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000db63`
- `ADVAPI32!RegGetValueW` at `0x14000dbc9`
- `ADVAPI32!RegGetValueW` at `0x14000db63`
- `ADVAPI32!RegGetValueW` at `0x14000dbc9`
- `ADVAPI32!RegOpenKeyExW` at `0x14000db0b`
- `ADVAPI32!RegOpenKeyExW` at `0x14000db0b`
- `ADVAPI32!RegSetValueExW` at `0x14000dd58`
- `ADVAPI32!RegSetValueExW` at `0x14000dd58`

## string_xrefs

- `0x14000ddad`: `An unexpected error occurred opening the App-V 4.x product registry key (error code 0x%X)`
- `0x14000dd66`: `Unable to add an entry for the UE-V agent service to the App-V 4.x override registry key (error code 0x%X)`
- `0x14000dd8a`: `Unable to read App-V 4.x virtual environment override entry. (error code 0x%X)`
- `0x14000dde5`: `Attempting to use an invalid handle.`
- `0x14000de16`: `Attempting to use an invalid handle.`
- `0x14000de47`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Uev::AppVServiceInclusion::AddVirtualEnvironmentOverride(Uev::AppVServiceInclusion *this)
{
  LSTATUS v2; // eax
  unsigned int ValueW; // esi
  void *pvData; // rdi
  void *v5; // rbx
  unsigned __int64 v6; // r8
  _WORD *v7; // rdx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
  __int128 *v10; // rdx
  __int128 *v11; // rax
  unsigned __int64 v12; // rcx
  BYTE **v13; // r15
  char *v14; // rdi
  __int64 v15; // rax
  __int128 *v16; // rdx
  unsigned __int64 v17; // rdx
  BYTE **v18; // rcx
  unsigned __int64 v19; // rdx
  BYTE **v20; // rcx
  const BYTE *v21; // rdx
  _QWORD v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+D0h] [rbp-30h] BYREF
  BYTE *lpData[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v28; // [rsp+F0h] [rbp-10h]
  HKEY hkey; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v30; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v31; // [rsp+110h] [rbp+10h]
  unsigned __int64 v32; // [rsp+118h] [rbp+18h]

  hkey = 0;
  v2 = RegOpenKeyExW(*((HKEY *)this + 1), *((LPCWSTR *)this + 7), 0, 0x2001Fu, &hkey);
  ValueW = v2;
  if ( !v2 )
  {
    pvData = operator new[](0x800u);
    v5 = pvData;
    pcbData = 2048;
    if ( !hkey )
    {
      std::wstring::wstring(v23, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v23);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    ValueW = RegGetValueW(hkey, 0, *((LPCWSTR *)this + 4), 0x20u, 0, pvData, &pcbData);
    if ( ValueW == 234 )
    {
      v5 = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
      operator delete(pvData);
      if ( !hkey )
      {
        std::wstring::wstring(&v30, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(v23, &v30);
        throw (Uev::SmartHandleException *)v23;
      }
      ValueW = RegGetValueW(hkey, 0, *((LPCWSTR *)this + 4), 0x20u, 0, v5, &pcbData);
    }
    if ( ValueW )
    {
      DbgTraceFrmt<3,long>((wchar_t *)L"Unable to read App-V 4.x virtual environment override entry. (error code 0x%X)");
LABEL_40:
      if ( v5 )
        operator delete(v5);
      goto LABEL_44;
    }
    *(_OWORD *)lpData = 0;
    v27 = 0;
    v28 = 0;
    v6 = 0;
    if ( pcbData >> 1 != 2 )
      v6 = (pcbData >> 1) - 1;
    std::wstring::_Construct<1,wchar_t *>(lpData, v5, v6);
    v7 = (_WORD *)*((_QWORD *)this + 5);
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    std::wstring::_Construct<1,wchar_t *>(&v30, v7, v8);
    v9 = v31;
    v10 = &v30;
    v11 = (__int128 *)v30;
    v12 = v32;
    if ( v32 > 7 )
      v10 = (__int128 *)v30;
    v13 = lpData;
    if ( v28 > 7 )
      v13 = (BYTE **)lpData[0];
    if ( v31 <= v27 )
    {
      if ( !v31
        || (v14 = (char *)v13 + 2 * v27, v15 = _std_search_2(v13, v14, v10, v31), (char *)v15 != v14)
        && (v15 - (__int64)v13) >> 1 != -1 )
      {
        DbgTraceFrmt<3,int>();
LABEL_38:
        std::wstring::_Tidy_deallocate(&v30);
        std::wstring::_Tidy_deallocate(lpData);
        goto LABEL_40;
      }
      v12 = v32;
      v9 = v31;
      v11 = (__int128 *)v30;
    }
    v16 = &v30;
    if ( v12 > 7 )
      v16 = v11;
    std::wstring::_Append<wchar_t>(lpData, v16, v9);
    v17 = v27;
    v18 = lpData;
    if ( v27 >= v28 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(lpData);
    }
    else
    {
      ++v27;
      if ( v28 > 7 )
        v18 = (BYTE **)lpData[0];
      *(_DWORD *)((char *)v18 + 2 * v17) = 0;
    }
    v19 = v27;
    v20 = lpData;
    if ( v27 >= v28 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(lpData);
    }
    else
    {
      ++v27;
      if ( v28 > 7 )
        v20 = (BYTE **)lpData[0];
      *(_DWORD *)((char *)v20 + 2 * v19) = 0;
    }
    v21 = (const BYTE *)lpData;
    if ( v28 > 7 )
      v21 = lpData[0];
    if ( !hkey )
    {
      std::wstring::wstring(v23, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v23);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    ValueW = RegSetValueExW(hkey, *((LPCWSTR *)this + 4), 0, 7u, v21, 2 * v27);
    if ( ValueW )
      DbgTraceFrmt<3,long>((wchar_t *)L"Unable to add an entry for the UE-V agent service to the App-V 4.x override regist"
                                       "ry key (error code 0x%X)");
    goto LABEL_38;
  }
  if ( v2 != 2 )
    DbgTraceFrmt<3,long>((wchar_t *)L"An unexpected error occurred opening the App-V 4.x product registry key (error code 0x%X)");
LABEL_44:
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hkey);
  return ValueW;
}

```

## disassembly

```asm
0x14000dac0  push    rbp
0x14000dac2  push    rbx
0x14000dac3  push    rsi
0x14000dac4  push    rdi
0x14000dac5  push    r12
0x14000dac7  push    r13
0x14000dac9  push    r14
0x14000dacb  push    r15
0x14000dacd  lea     rbp, [rsp-38h]
0x14000dad2  sub     rsp, 138h
0x14000dad9  mov     rax, cs:__security_cookie
0x14000dae0  xor     rax, rsp
0x14000dae3  mov     [rbp+70h+var_50], rax
0x14000dae7  mov     r14, rcx
0x14000daea  xor     r12d, r12d
0x14000daed  mov     [rbp+70h+hkey], r12
0x14000daf1  lea     rax, [rbp+70h+hkey]
0x14000daf5  mov     [rsp+170h+phkResult], rax; phkResult
0x14000dafa  mov     r9d, 2001Fh; samDesired
0x14000db00  xor     r8d, r8d; ulOptions
0x14000db03  mov     rdx, [rcx+38h]; lpSubKey
0x14000db07  mov     rcx, [rcx+8]; hKey
0x14000db0b  call    cs:__imp_RegOpenKeyExW
0x14000db11  mov     esi, eax
0x14000db13  test    eax, eax
0x14000db15  jnz     loc_14000DDA6
0x14000db1b  mov     esi, 800h
0x14000db20  mov     ecx, esi; unsigned __int64
0x14000db22  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000db27  mov     rdi, rax
0x14000db2a  mov     rbx, rax
0x14000db2d  mov     [rsp+170h+var_130], rax
0x14000db32  mov     [rbp+70h+var_A0], esi
0x14000db35  mov     rcx, [rbp+70h+hkey]; hkey
0x14000db39  test    rcx, rcx
0x14000db3c  jz      loc_14000DDE5
0x14000db42  lea     rax, [rbp+70h+var_A0]
0x14000db46  mov     [rsp+170h+pcbData], rax; pcbData
0x14000db4b  mov     [rsp+170h+pvData], rbx; pvData
0x14000db50  mov     [rsp+170h+phkResult], r12; pdwType
0x14000db55  lea     r15d, [r12+20h]
0x14000db5a  mov     r9d, r15d; dwFlags
0x14000db5d  mov     r8, [r14+20h]; lpValue
0x14000db61  xor     edx, edx; lpSubKey
0x14000db63  call    cs:__imp_RegGetValueW
0x14000db69  mov     esi, eax
0x14000db6b  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000db6f  cmp     eax, 0EAh
0x14000db74  jnz     short loc_14000DBD1
0x14000db76  mov     ecx, [rbp+70h+var_A0]
0x14000db79  shr     rcx, 1
0x14000db7c  lea     eax, [r12+2]
0x14000db81  mul     rcx
0x14000db84  cmovb   rax, r13
0x14000db88  mov     rcx, rax; unsigned __int64
0x14000db8b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000db90  mov     rbx, rax
0x14000db93  mov     [rsp+170h+var_130], rax
0x14000db98  mov     rcx, rdi; Block
0x14000db9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dba0  mov     rcx, [rbp+70h+hkey]; hkey
0x14000dba4  test    rcx, rcx
0x14000dba7  jz      loc_14000DE16
0x14000dbad  lea     rax, [rbp+70h+var_A0]
0x14000dbb1  mov     [rsp+170h+pcbData], rax; pcbData
0x14000dbb6  mov     [rsp+170h+pvData], rbx; pvData
0x14000dbbb  mov     [rsp+170h+phkResult], r12; pdwType
0x14000dbc0  mov     r9d, r15d; dwFlags
0x14000dbc3  mov     r8, [r14+20h]; lpValue
0x14000dbc7  xor     edx, edx; lpSubKey
0x14000dbc9  call    cs:__imp_RegGetValueW
0x14000dbcf  mov     esi, eax
0x14000dbd1  test    esi, esi
0x14000dbd3  jnz     loc_14000DD88
0x14000dbd9  mov     edx, [rbp+70h+var_A0]
0x14000dbdc  shr     edx, 1
0x14000dbde  xorps   xmm0, xmm0
0x14000dbe1  movups  xmmword ptr [rbp+70h+lpData], xmm0
0x14000dbe5  mov     [rbp+70h+var_88], r12
0x14000dbe9  mov     [rbp+70h+var_80], r12
0x14000dbed  lea     eax, [rdx-1]
0x14000dbf0  mov     r8d, r12d
0x14000dbf3  cmp     edx, 2
0x14000dbf6  cmovnz  r8d, eax
0x14000dbfa  mov     rdx, rbx
0x14000dbfd  lea     rcx, [rbp+70h+lpData]
0x14000dc01  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14000dc06  nop
0x14000dc07  mov     rdx, [r14+28h]
0x14000dc0b  xorps   xmm0, xmm0
0x14000dc0e  movups  [rbp+70h+var_70], xmm0
0x14000dc12  mov     [rbp+70h+var_60], r12
0x14000dc16  mov     [rbp+70h+var_58], r12
0x14000dc1a  mov     r8, r13
0x14000dc1d  inc     r8
0x14000dc20  cmp     [rdx+r8*2], r12w
0x14000dc25  jnz     short loc_14000DC1D
0x14000dc27  lea     rcx, [rbp+70h+var_70]
0x14000dc2b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14000dc30  nop
0x14000dc31  mov     r8, [rbp+70h+var_60]
0x14000dc35  lea     rdx, [rbp+70h+var_70]
0x14000dc39  mov     rax, qword ptr [rbp+70h+var_70]
0x14000dc3d  mov     rcx, [rbp+70h+var_58]
0x14000dc41  cmp     rcx, 7
0x14000dc45  cmova   rdx, rax
0x14000dc49  mov     r9, [rbp+70h+var_88]
0x14000dc4d  lea     r15, [rbp+70h+lpData]
0x14000dc51  cmp     [rbp+70h+var_80], 7
0x14000dc56  cmova   r15, [rbp+70h+lpData]
0x14000dc5b  cmp     r8, r9
0x14000dc5e  ja      short loc_14000DC96
0x14000dc60  test    r8, r8
0x14000dc63  jz      short loc_14000DCD6
0x14000dc65  lea     rdi, [r15+r9*2]
0x14000dc69  mov     r9, r8
0x14000dc6c  mov     r8, rdx
0x14000dc6f  mov     rdx, rdi
0x14000dc72  mov     rcx, r15
0x14000dc75  call    __std_search_2
0x14000dc7a  cmp     rax, rdi
0x14000dc7d  jz      short loc_14000DC8A
0x14000dc7f  sub     rax, r15
0x14000dc82  sar     rax, 1
0x14000dc85  cmp     rax, r13
0x14000dc88  jnz     short loc_14000DCD6
0x14000dc8a  mov     rcx, [rbp+70h+var_58]
0x14000dc8e  mov     r8, [rbp+70h+var_60]
0x14000dc92  mov     rax, qword ptr [rbp+70h+var_70]
0x14000dc96  lea     rdx, [rbp+70h+var_70]
0x14000dc9a  cmp     rcx, 7
0x14000dc9e  cmova   rdx, rax
0x14000dca2  lea     rcx, [rbp+70h+lpData]; Src
0x14000dca6  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000dcab  mov     rdx, [rbp+70h+var_88]
0x14000dcaf  mov     edi, 1
0x14000dcb4  lea     rcx, [rbp+70h+lpData]; Src
0x14000dcb8  cmp     rdx, [rbp+70h+var_80]
0x14000dcbc  jnb     short loc_14000DCE0
0x14000dcbe  lea     rax, [rdx+1]
0x14000dcc2  mov     [rbp+70h+var_88], rax
0x14000dcc6  cmp     [rbp+70h+var_80], 7
0x14000dccb  cmova   rcx, [rbp+70h+lpData]
0x14000dcd0  mov     [rcx+rdx*2], r12d
0x14000dcd4  jmp     short loc_14000DCEE
0x14000dcd6  call    ??$DbgTraceFrmt@$02H@@YAXPEB_WH@Z; DbgTraceFrmt<3,int>(wchar_t const *,int)
0x14000dcdb  jmp     loc_14000DD73
0x14000dce0  mov     r8b, r12b
0x14000dce3  xor     r9d, r9d
0x14000dce6  mov     rdx, rdi
0x14000dce9  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x14000dcee  mov     rdx, [rbp+70h+var_88]
0x14000dcf2  lea     rcx, [rbp+70h+lpData]; Src
0x14000dcf6  cmp     rdx, [rbp+70h+var_80]
0x14000dcfa  jnb     short loc_14000DD14
0x14000dcfc  lea     rax, [rdx+1]
0x14000dd00  mov     [rbp+70h+var_88], rax
0x14000dd04  cmp     [rbp+70h+var_80], 7
0x14000dd09  cmova   rcx, [rbp+70h+lpData]
0x14000dd0e  mov     [rcx+rdx*2], r12d
0x14000dd12  jmp     short loc_14000DD22
0x14000dd14  mov     r8b, r12b
0x14000dd17  xor     r9d, r9d
0x14000dd1a  mov     rdx, rdi
0x14000dd1d  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x14000dd22  lea     rdx, [rbp+70h+lpData]
0x14000dd26  cmp     [rbp+70h+var_80], 7
0x14000dd2b  cmova   rdx, [rbp+70h+lpData]
0x14000dd30  mov     rcx, [rbp+70h+hkey]; hKey
0x14000dd34  test    rcx, rcx
0x14000dd37  jz      loc_14000DE47
0x14000dd3d  mov     eax, dword ptr [rbp+70h+var_88]
0x14000dd40  add     eax, eax
0x14000dd42  mov     dword ptr [rsp+170h+pvData], eax; cbData
0x14000dd46  mov     [rsp+170h+phkResult], rdx; lpData
0x14000dd4b  mov     r9d, 7; dwType
0x14000dd51  xor     r8d, r8d; Reserved
0x14000dd54  mov     rdx, [r14+20h]; lpValueName
0x14000dd58  call    cs:__imp_RegSetValueExW
0x14000dd5e  mov     esi, eax
0x14000dd60  test    eax, eax
0x14000dd62  jz      short loc_14000DD73
0x14000dd64  mov     edx, eax
0x14000dd66  lea     rcx, aUnableToAddAnE_0; "Unable to add an entry for the UE-V age"...
0x14000dd6d  call    ??$DbgTraceFrmt@$02J@@YAXPEB_WJ@Z; DbgTraceFrmt<3,long>(wchar_t const *,long)
0x14000dd72  nop
0x14000dd73  lea     rcx, [rbp+70h+var_70]
0x14000dd77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000dd7c  nop
0x14000dd7d  lea     rcx, [rbp+70h+lpData]
0x14000dd81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000dd86  jmp     short loc_14000DD97
0x14000dd88  mov     edx, esi
0x14000dd8a  lea     rcx, aUnableToReadAp; "Unable to read App-V 4.x virtual enviro"...
0x14000dd91  call    ??$DbgTraceFrmt@$02J@@YAXPEB_WJ@Z; DbgTraceFrmt<3,long>(wchar_t const *,long)
0x14000dd96  nop
0x14000dd97  test    rbx, rbx
0x14000dd9a  jz      short loc_14000DDBA
0x14000dd9c  mov     rcx, rbx; Block
0x14000dd9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dda4  jmp     short loc_14000DDBA
0x14000dda6  cmp     eax, 2
0x14000dda9  jz      short loc_14000DDBA
0x14000ddab  mov     edx, eax
0x14000ddad  lea     rcx, aAnUnexpectedEr; "An unexpected error occurred opening th"...
0x14000ddb4  call    ??$DbgTraceFrmt@$02J@@YAXPEB_WJ@Z; DbgTraceFrmt<3,long>(wchar_t const *,long)
0x14000ddb9  nop
0x14000ddba  lea     rcx, [rbp+70h+hkey]
0x14000ddbe  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14000ddc3  mov     eax, esi
0x14000ddc5  mov     rcx, [rbp+70h+var_50]
0x14000ddc9  xor     rcx, rsp; StackCookie
0x14000ddcc  call    __security_check_cookie
0x14000ddd1  add     rsp, 138h
0x14000ddd8  pop     r15
0x14000ddda  pop     r14
0x14000dddc  pop     r13
0x14000ddde  pop     r12
0x14000dde0  pop     rdi
0x14000dde1  pop     rsi
0x14000dde2  pop     rbx
0x14000dde3  pop     rbp
0x14000dde4  retn
0x14000dde5  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14000ddec  lea     rcx, [rsp+170h+var_120]
0x14000ddf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000ddf6  nop
0x14000ddf7  lea     rdx, [rsp+170h+var_120]
0x14000ddfc  lea     rcx, [rbp+70h+pExceptionObject]
0x14000de00  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14000de05  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14000de0c  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14000de10  call    _CxxThrowException_0
0x14000de16  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14000de1d  lea     rcx, [rbp+70h+var_70]
0x14000de21  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000de26  nop
0x14000de27  lea     rdx, [rbp+70h+var_70]
0x14000de2b  lea     rcx, [rsp+170h+var_120]
0x14000de30  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14000de35  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14000de3c  lea     rcx, [rsp+170h+var_120]; pExceptionObject
0x14000de41  call    _CxxThrowException_0
0x14000de47  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14000de4e  lea     rcx, [rsp+170h+var_120]
0x14000de53  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000de58  nop
0x14000de59  lea     rdx, [rsp+170h+var_120]
0x14000de5e  lea     rcx, [rbp+70h+pExceptionObject]
0x14000de62  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14000de67  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14000de6e  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14000de72  call    _CxxThrowException_0
```
