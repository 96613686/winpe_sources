# Dossier::GetAllKeyValuePairs(WOSCKeyValuePair *,ulong *)

- ea: `0x18000d300`
- end: `0x18000d67b`
- name: `?GetAllKeyValuePairs@Dossier@@EEAAJPEAUWOSCKeyValuePair@@PEAK@Z`
- size: `891`
- prototype: `int(Dossier *__hidden this, struct WOSCKeyValuePair *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006e28`
- `0x18000d300`
- `0x18000efec`
- `0x180012308`
- `0x180018948`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000d529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000d529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d497`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d45b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d45b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d647`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d647`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d414`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d414`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000d4de`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000d4de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetAllKeyValuePairs(Dossier *this, struct WOSCKeyValuePair *a2, unsigned int *a3)
{
  DWORD *lpcValues; // rbx
  Dossier *v5; // r15
  unsigned __int16 *v6; // rdi
  int AllKeyValuePairs; // ebx
  __int64 v8; // rdx
  signed int StateSeparationRegistryLocation; // esi
  unsigned __int16 *v11; // r15
  _QWORD *v12; // rdi
  void *v13; // r14
  DWORD LastError; // ebx
  LSTATUS InfoKeyW; // eax
  DWORD v16; // r14d
  WCHAR *v17; // rax
  WCHAR *v18; // rbx
  LSTATUS v19; // eax
  __int64 v20; // rax
  WCHAR *v21; // rax
  __int64 v22; // r12
  unsigned __int16 *v23; // rax
  _QWORD *v24; // r15
  void *v25; // r12
  DWORD v26; // edi
  LPVOID v27; // rax
  int phkResult; // [rsp+28h] [rbp-69h]
  DWORD cchValueName; // [rsp+68h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-19h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-11h] BYREF
  unsigned __int16 *v33; // [rsp+88h] [rbp-9h] BYREF
  __int64 v34; // [rsp+90h] [rbp-1h]
  void **p_lpSubKey; // [rsp+98h] [rbp+7h]
  unsigned __int16 *v36; // [rsp+A0h] [rbp+Fh] BYREF
  char v37; // [rsp+A8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  lpcValues = a3;
  v5 = this;
  v6 = 0;
  if ( !a3 )
  {
    AllKeyValuePairs = -2147467261;
    v8 = 226;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)AllKeyValuePairs,
      phkResult);
    return (unsigned int)AllKeyValuePairs;
  }
  if ( !*((_DWORD *)this + 4) )
  {
    AllKeyValuePairs = -2147418113;
    v8 = 227;
    goto LABEL_3;
  }
  if ( *((_DWORD *)this + 5) )
  {
    hKey = 0;
    lpSubKey = 0;
    p_lpSubKey = (void **)&lpSubKey;
    v36 = 0;
    v37 = 1;
    StateSeparationRegistryLocation = GetStateSeparationRegistryLocation(
                                        L"WaaSAssessment",
                                        L"Software\\Microsoft\\Windows\\CurrentVersion\\WaaSAssessment",
                                        &v36);
    if ( v37 )
    {
      v11 = v36;
      v12 = p_lpSubKey;
      v13 = *p_lpSubKey;
      if ( *p_lpSubKey )
      {
        LastError = GetLastError();
        CoTaskMemFree(v13);
        SetLastError(LastError);
        lpcValues = a3;
      }
      *v12 = v11;
      v5 = this;
      v6 = 0;
    }
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
    {
      if ( !a2 )
      {
        InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, lpcValues, 0, 0, 0, 0);
        if ( InfoKeyW )
        {
          if ( InfoKeyW > 0 )
            StateSeparationRegistryLocation = (unsigned __int16)InfoKeyW | 0x80070000;
          else
            StateSeparationRegistryLocation = InfoKeyW;
        }
      }
      v16 = 0;
LABEL_46:
      if ( StateSeparationRegistryLocation >= 0 && a2 )
      {
        while ( v16 < *lpcValues )
        {
          v17 = (WCHAR *)CoTaskMemAlloc(0x7FFEu);
          v18 = v17;
          if ( v17 )
            memset_0(v17, 0, 0x7FFEu);
          cchValueName = 0x3FFF;
          v19 = RegEnumValueW(hKey, v16, v18, &cchValueName, 0, 0, 0, 0);
          if ( v19 == 259 )
          {
            CoTaskMemFree(v18);
            break;
          }
          if ( v19 )
          {
            if ( v19 > 0 )
              StateSeparationRegistryLocation = (unsigned __int16)v19 | 0x80070000;
            else
              StateSeparationRegistryLocation = v19;
          }
          if ( StateSeparationRegistryLocation < 0 )
            goto LABEL_45;
          pv = 0;
          if ( v18 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v18[v20] );
            v21 = (WCHAR *)CoTaskMemRealloc(v18, 2LL * (unsigned int)(v20 + 1));
            v18 = v21;
            if ( v21 )
            {
              v33 = 0;
              CSpDynamicString::operator=(&v33, v21);
              v6 = v33;
              CoTaskMemFree(0);
            }
          }
          v22 = 16LL * (int)v16;
          v34 = v22;
          *(_QWORD *)((char *)a2 + v22) = v6;
          p_lpSubKey = &pv;
          v6 = 0;
          v36 = 0;
          v37 = 1;
          StateSeparationRegistryLocation = (**(__int64 (__fastcall ***)(Dossier *, WCHAR *, unsigned __int16 **))v5)(
                                              v5,
                                              v18,
                                              &v36);
          if ( v37 )
          {
            v23 = v36;
            v33 = v36;
            v24 = p_lpSubKey;
            v25 = *p_lpSubKey;
            if ( *p_lpSubKey )
            {
              v26 = GetLastError();
              CoTaskMemFree(v25);
              SetLastError(v26);
              v23 = v33;
              v6 = 0;
            }
            *v24 = v23;
            v5 = this;
            v22 = v34;
          }
          if ( StateSeparationRegistryLocation != -2147023266 )
          {
            v27 = pv;
            pv = 0;
            *(_QWORD *)((char *)a2 + v22 + 8) = v27;
            if ( pv )
              CoTaskMemFree(pv);
LABEL_45:
            CoTaskMemFree(v18);
            ++v16;
            lpcValues = a3;
            goto LABEL_46;
          }
          StateSeparationRegistryLocation = 0;
          if ( pv )
            CoTaskMemFree(pv);
          CoTaskMemFree(v18);
          ++v16;
          lpcValues = a3;
        }
      }
      RegCloseKey(hKey);
    }
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
  }
  else
  {
    AllKeyValuePairs = WOSCOneSettings::GetAllKeyValuePairs((Dossier *)((char *)this + 8), a2, a3);
    if ( AllKeyValuePairs < 0 )
    {
      v8 = 232;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d300  mov     rax, rsp
0x18000d303  mov     [rax+10h], rbx
0x18000d307  mov     [rax+18h], r8
0x18000d30b  mov     [rax+8], rcx
0x18000d30f  push    rbp
0x18000d310  push    rsi
0x18000d311  push    rdi
0x18000d312  push    r12
0x18000d314  push    r13
0x18000d316  push    r14
0x18000d318  push    r15
0x18000d31a  lea     rbp, [rax-5Fh]
0x18000d31e  sub     rsp, 0B0h
0x18000d325  mov     rbx, r8
0x18000d328  mov     r13, rdx
0x18000d32b  mov     r15, rcx
0x18000d32e  xor     edi, edi
0x18000d330  test    r8, r8
0x18000d333  jnz     short loc_18000D359
0x18000d335  mov     ebx, 80004003h
0x18000d33a  mov     edx, 0E2h; void *
0x18000d33f  mov     rcx, [rbp+5Fh]; this
0x18000d343  mov     r9d, ebx; char *
0x18000d346  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000d34d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d352  mov     eax, ebx
0x18000d354  jmp     loc_18000D660
0x18000d359  cmp     [rcx+10h], edi
0x18000d35c  jnz     short loc_18000D36A
0x18000d35e  mov     ebx, 8000FFFFh
0x18000d363  mov     edx, 0E3h; struct WOSCKeyValuePair *
0x18000d368  jmp     short loc_18000D33F
0x18000d36a  cmp     [rcx+14h], edi
0x18000d36d  jnz     short loc_18000D389
0x18000d36f  add     rcx, 8; this
0x18000d373  call    ?GetAllKeyValuePairs@WOSCOneSettings@@QEAAJPEAUWOSCKeyValuePair@@PEAK@Z; WOSCOneSettings::GetAllKeyValuePairs(WOSCKeyValuePair *,ulong *)
0x18000d378  mov     ebx, eax
0x18000d37a  test    eax, eax
0x18000d37c  jns     loc_18000D65E
0x18000d382  mov     edx, 0E8h
0x18000d387  jmp     short loc_18000D33F
0x18000d389  mov     [rbp+57h+hKey], rdi
0x18000d38d  mov     [rbp+57h+lpSubKey], rdi
0x18000d391  lea     rax, [rbp+57h+lpSubKey]
0x18000d395  mov     [rbp+57h+var_50], rax
0x18000d399  mov     [rbp+57h+var_48], rdi
0x18000d39d  mov     [rbp+57h+var_40], 1
0x18000d3a1  lea     r8, [rbp+57h+var_48]; unsigned __int16 **
0x18000d3a5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d3ac  lea     rcx, aWaasassessment_2; "WaaSAssessment"
0x18000d3b3  call    ?GetStateSeparationRegistryLocation@@YAJPEBG0PEAPEAG@Z; GetStateSeparationRegistryLocation(ushort const *,ushort const *,ushort * *)
0x18000d3b8  mov     esi, eax
0x18000d3ba  cmp     [rbp+57h+var_40], dil
0x18000d3be  jz      short loc_18000D3F7
0x18000d3c0  mov     r15, [rbp+57h+var_48]
0x18000d3c4  mov     rdi, [rbp+57h+var_50]
0x18000d3c8  mov     r14, [rdi]
0x18000d3cb  test    r14, r14
0x18000d3ce  jz      short loc_18000D3EE
0x18000d3d0  call    cs:__imp_GetLastError
0x18000d3d6  mov     ebx, eax
0x18000d3d8  mov     rcx, r14; pv
0x18000d3db  call    cs:__imp_CoTaskMemFree
0x18000d3e1  mov     ecx, ebx; dwErrCode
0x18000d3e3  call    cs:__imp_SetLastError
0x18000d3e9  nop
0x18000d3ea  mov     rbx, [rbp+57h+arg_10]
0x18000d3ee  mov     [rdi], r15
0x18000d3f1  mov     r15, [rbp+57h+arg_0]
0x18000d3f5  xor     edi, edi
0x18000d3f7  lea     rax, [rbp+57h+hKey]
0x18000d3fb  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000d400  mov     r9d, 20019h; samDesired
0x18000d406  xor     r8d, r8d; ulOptions
0x18000d409  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000d40d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d414  call    cs:__imp_RegOpenKeyExW
0x18000d41a  test    eax, eax
0x18000d41c  jnz     loc_18000D64E
0x18000d422  test    r13, r13
0x18000d425  jnz     short loc_18000D474
0x18000d427  mov     [rsp+58h], rdi; lpftLastWriteTime
0x18000d42c  mov     [rsp+0E0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18000d431  mov     [rsp+0E0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18000d436  mov     [rsp+0E0h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18000d43b  mov     [rsp+0E0h+lpcValues], rbx; lpcValues
0x18000d440  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18000d445  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18000d44a  mov     [rsp+0E0h+phkResult], rdi; lpcSubKeys
0x18000d44f  xor     r9d, r9d; lpReserved
0x18000d452  xor     r8d, r8d; lpcchClass
0x18000d455  xor     edx, edx; lpClass
0x18000d457  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d45b  call    cs:__imp_RegQueryInfoKeyW
0x18000d461  test    eax, eax
0x18000d463  jz      short loc_18000D474
0x18000d465  jg      short loc_18000D46B
0x18000d467  mov     esi, eax
0x18000d469  jmp     short loc_18000D474
0x18000d46b  movzx   esi, ax
0x18000d46e  or      esi, 80070000h
0x18000d474  mov     r14d, edi
0x18000d477  jmp     loc_18000D630
0x18000d47c  test    r13, r13
0x18000d47f  jz      loc_18000D643
0x18000d485  mov     [rbp+57h+arg_18], r14d
0x18000d489  cmp     r14d, [rbx]
0x18000d48c  jnb     loc_18000D643
0x18000d492  mov     ecx, 7FFEh; cb
0x18000d497  call    cs:__imp_CoTaskMemAlloc
0x18000d49d  mov     rbx, rax
0x18000d4a0  test    rax, rax
0x18000d4a3  jz      short loc_18000D4B5
0x18000d4a5  xor     edx, edx; Val
0x18000d4a7  mov     r8d, 7FFEh; Size
0x18000d4ad  mov     rcx, rax; void *
0x18000d4b0  call    memset_0
0x18000d4b5  mov     [rbp+57h+cchValueName], 3FFFh
0x18000d4bc  mov     [rsp+0E0h+lpcValues], rdi; lpcbData
0x18000d4c1  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpData
0x18000d4c6  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rdi; lpType
0x18000d4cb  mov     [rsp+0E0h+phkResult], rdi; lpReserved
0x18000d4d0  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18000d4d4  mov     r8, rbx; lpValueName
0x18000d4d7  mov     edx, r14d; dwIndex
0x18000d4da  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d4de  call    cs:__imp_RegEnumValueW
0x18000d4e4  cmp     eax, 103h
0x18000d4e9  jz      loc_18000D63A
0x18000d4ef  test    eax, eax
0x18000d4f1  jz      short loc_18000D502
0x18000d4f3  jg      short loc_18000D4F9
0x18000d4f5  mov     esi, eax
0x18000d4f7  jmp     short loc_18000D502
0x18000d4f9  movzx   esi, ax
0x18000d4fc  or      esi, 80070000h
0x18000d502  test    esi, esi
0x18000d504  js      loc_18000D620
0x18000d50a  mov     [rbp+57h+pv], rdi
0x18000d50e  test    rbx, rbx
0x18000d511  jz      short loc_18000D553
0x18000d513  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d517  inc     rax
0x18000d51a  cmp     [rbx+rax*2], di
0x18000d51e  jnz     short loc_18000D517
0x18000d520  lea     edx, [rax+1]
0x18000d523  add     rdx, rdx; cb
0x18000d526  mov     rcx, rbx; pv
0x18000d529  call    cs:__imp_CoTaskMemRealloc
0x18000d52f  mov     rbx, rax
0x18000d532  test    rax, rax
0x18000d535  jz      short loc_18000D553
0x18000d537  mov     [rbp+57h+var_60], rdi
0x18000d53b  mov     rdx, rax
0x18000d53e  lea     rcx, [rbp+57h+var_60]
0x18000d542  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18000d547  mov     rdi, [rbp+57h+var_60]
0x18000d54b  xor     ecx, ecx; pv
0x18000d54d  call    cs:__imp_CoTaskMemFree
0x18000d553  movsxd  r12, r14d
0x18000d556  shl     r12, 4
0x18000d55a  mov     [rbp+57h+var_58], r12
0x18000d55e  mov     [r12+r13], rdi
0x18000d562  lea     rax, [rbp+57h+pv]
0x18000d566  mov     [rbp+57h+var_50], rax
0x18000d56a  xor     edi, edi
0x18000d56c  mov     [rbp+57h+var_48], rdi
0x18000d570  mov     [rbp+57h+var_40], 1
0x18000d574  mov     rax, [r15]
0x18000d577  lea     r8, [rbp+57h+var_48]
0x18000d57b  mov     rdx, rbx
0x18000d57e  mov     rcx, r15
0x18000d581  mov     rax, [rax]
0x18000d584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d589  mov     esi, eax
0x18000d58b  cmp     [rbp+57h+var_40], dil
0x18000d58f  jz      short loc_18000D5D0
0x18000d591  mov     rax, [rbp+57h+var_48]
0x18000d595  mov     [rbp+57h+var_60], rax
0x18000d599  mov     r15, [rbp+57h+var_50]
0x18000d59d  mov     r12, [r15]
0x18000d5a0  test    r12, r12
0x18000d5a3  jz      short loc_18000D5C5
0x18000d5a5  call    cs:__imp_GetLastError
0x18000d5ab  mov     edi, eax
0x18000d5ad  mov     rcx, r12; pv
0x18000d5b0  call    cs:__imp_CoTaskMemFree
0x18000d5b6  mov     ecx, edi; dwErrCode
0x18000d5b8  call    cs:__imp_SetLastError
0x18000d5be  nop
0x18000d5bf  mov     rax, [rbp+57h+var_60]
0x18000d5c3  xor     edi, edi
0x18000d5c5  mov     [r15], rax
0x18000d5c8  mov     r15, [rbp+57h+arg_0]
0x18000d5cc  mov     r12, [rbp+57h+var_58]
0x18000d5d0  cmp     esi, 8007065Eh
0x18000d5d6  jnz     short loc_18000D603
0x18000d5d8  mov     esi, edi
0x18000d5da  mov     rcx, [rbp+57h+pv]; pv
0x18000d5de  test    rcx, rcx
0x18000d5e1  jz      short loc_18000D5EA
0x18000d5e3  call    cs:__imp_CoTaskMemFree
0x18000d5e9  nop
0x18000d5ea  mov     rcx, rbx; pv
0x18000d5ed  call    cs:__imp_CoTaskMemFree
0x18000d5f3  mov     r14d, [rbp+57h+arg_18]
0x18000d5f7  inc     r14d
0x18000d5fa  mov     rbx, [rbp+57h+arg_10]
0x18000d5fe  jmp     loc_18000D485
0x18000d603  mov     rax, [rbp+57h+pv]
0x18000d607  mov     [rbp+57h+pv], rdi
0x18000d60b  mov     [r12+r13+8], rax
0x18000d610  mov     rcx, [rbp+57h+pv]; pv
0x18000d614  test    rcx, rcx
0x18000d617  jz      short loc_18000D620
0x18000d619  call    cs:__imp_CoTaskMemFree
0x18000d61f  nop
0x18000d620  mov     rcx, rbx; pv
0x18000d623  call    cs:__imp_CoTaskMemFree
0x18000d629  inc     r14d
0x18000d62c  mov     rbx, [rbp+57h+arg_10]
0x18000d630  test    esi, esi
0x18000d632  jns     loc_18000D47C
0x18000d638  jmp     short loc_18000D643
0x18000d63a  mov     rcx, rbx; pv
0x18000d63d  call    cs:__imp_CoTaskMemFree
0x18000d643  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d647  call    cs:__imp_RegCloseKey
0x18000d64d  nop
0x18000d64e  mov     rcx, [rbp+57h+lpSubKey]; pv
0x18000d652  test    rcx, rcx
0x18000d655  jz      short loc_18000D65E
0x18000d657  call    cs:__imp_CoTaskMemFree
0x18000d65d  nop
0x18000d65e  xor     eax, eax
0x18000d660  mov     rbx, [rsp+0E0h+arg_8]
0x18000d668  add     rsp, 0B0h
0x18000d66f  pop     r15
0x18000d671  pop     r14
0x18000d673  pop     r13
0x18000d675  pop     r12
0x18000d677  pop     rdi
0x18000d678  pop     rsi
0x18000d679  pop     rbp
0x18000d67a  retn
```
