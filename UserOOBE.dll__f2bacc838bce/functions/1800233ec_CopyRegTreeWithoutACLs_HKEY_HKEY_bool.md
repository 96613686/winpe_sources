# CopyRegTreeWithoutACLs(HKEY__ *,HKEY__ *,bool)

- ea: `0x1800233ec`
- end: `0x1800236b5`
- name: `?CopyRegTreeWithoutACLs@@YAJPEAUHKEY__@@0_N@Z`
- size: `713`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029260`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000e580`
- `0x180018c98`
- `0x18001f6c4`
- `0x180022a38`
- `0x180022f50`
- `0x1800233ec`
- `0x180023c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002347a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002347a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002356e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002356e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023515`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023515`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235b3`

## string_xrefs

- `0x180023429`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x18002348b`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x1800234d2`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x1800235fc`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x18002362c`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x180023651`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x180023676`: `shell\OOBE\common\inc\CopyRegTree.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall CopyRegTreeWithoutACLs(HKEY hKey, HKEY a2, char a3)
{
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // eax
  __int64 v9; // rcx
  int v10; // eax
  DWORD v11; // edi
  WCHAR *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // esi
  int v16; // eax
  int v17; // esi
  int lpcSubKeys; // [rsp+28h] [rbp-39h]
  unsigned int lpcSubKeysa; // [rsp+28h] [rbp-39h]
  unsigned int lpcSubKeysb; // [rsp+28h] [rbp-39h]
  unsigned int lpcSubKeysc; // [rsp+28h] [rbp-39h]
  unsigned int lpcSubKeysd; // [rsp+28h] [rbp-39h]
  HKEY v23; // [rsp+68h] [rbp+7h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp+Fh] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp+17h] BYREF
  HKEY *p_hKeya; // [rsp+80h] [rbp+1Fh] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+27h] BYREF
  char v28; // [rsp+90h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+E0h] [rbp+7Fh] BYREF

  LOBYTE(cbMaxSubKeyLen) = a3;
  v5 = DuplicateKeyValues(hKey, a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x2E,
               (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
               (const char *)v7,
               lpcSubKeysa);
    lpName = 0;
    ++cbMaxSubKeyLen;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpName,
      0);
    v10 = _AllocArray<unsigned short,CTCoAllocPolicy>(v9, 1, cbMaxSubKeyLen, &lpName);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v11 = 0;
      v12 = lpName;
      while ( 1 )
      {
        cchName = cbMaxSubKeyLen;
        v13 = RegEnumKeyExW(hKey, v11, v12, &cchName, 0, 0, 0, 0);
        if ( v13 == 259 )
          break;
        if ( v13 )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x3D,
                 (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
                 (const char *)v13,
                 lpcSubKeysb);
          goto LABEL_20;
        }
        v23 = 0;
        p_hKeya = &v23;
        phkResult = 0;
        v28 = 1;
        v14 = RegCreateKeyExW(a2, v12, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKeya);
        if ( v14 )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x40,
                 (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
                 (const char *)v14,
                 lpcSubKeysc);
          goto LABEL_17;
        }
        hKeya = 0;
        p_hKeya = &hKeya;
        phkResult = 0;
        v28 = 1;
        v15 = RegOpenKeyExW(hKey, v12, 0, 0x20019u, &phkResult);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKeya);
        if ( v15 )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x42,
                 (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
                 (const char *)v15,
                 lpcSubKeysd);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
LABEL_17:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
          goto LABEL_20;
        }
        v16 = DuplicateKeyValues(hKeya, v23);
        v17 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x43,
            (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
            (const char *)(unsigned int)v16,
            lpcSubKeysd);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
          v6 = v17;
          goto LABEL_20;
        }
        ++v11;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
      }
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
        (const char *)(unsigned int)v10,
        lpcSubKeysa);
    }
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpName);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
      (const char *)(unsigned int)v5,
      lpcSubKeys);
  }
  return v6;
}

```

## disassembly

```asm
0x1800233ec  mov     rax, rsp
0x1800233ef  mov     [rax+8], rbx
0x1800233f3  mov     [rax+10h], rsi
0x1800233f7  mov     [rax+18h], r8b
0x1800233fb  push    rbp
0x1800233fc  push    rdi
0x1800233fd  push    r12
0x1800233ff  push    r14
0x180023401  push    r15
0x180023403  lea     rbp, [rax-5Fh]
0x180023407  sub     rsp, 90h
0x18002340e  mov     r15, rdx
0x180023411  mov     r14, rcx
0x180023414  call    ?DuplicateKeyValues@@YAJPEAUHKEY__@@0@Z; DuplicateKeyValues(HKEY__ *,HKEY__ *)
0x180023419  mov     ebx, eax
0x18002341b  xor     r12d, r12d
0x18002341e  test    eax, eax
0x180023420  jns     short loc_18002343F
0x180023422  mov     rcx, [rbp+5Fh]; this
0x180023426  mov     r9d, eax; char *
0x180023429  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023430  lea     edx, [r12+2Ah]; void *
0x180023435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002343a  jmp     loc_180023697
0x18002343f  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180023443  mov     [rsp+0B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180023448  mov     [rsp+0B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18002344d  mov     [rsp+0B0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180023452  mov     [rsp+0B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180023457  mov     [rsp+0B0h+lpcValues], r12; lpcValues
0x18002345c  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180023461  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180023465  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002346a  mov     [rsp+0B0h+lpcSubKeys], r12; int
0x18002346f  xor     r9d, r9d; lpReserved
0x180023472  xor     r8d, r8d; lpcchClass
0x180023475  xor     edx, edx; lpClass
0x180023477  mov     rcx, r14; hKey
0x18002347a  call    cs:__imp_RegQueryInfoKeyW
0x180023480  test    eax, eax
0x180023482  jz      short loc_1800234A1
0x180023484  mov     rcx, [rbp+5Fh]; this
0x180023488  mov     r9d, eax; char *
0x18002348b  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023492  mov     edx, 2Eh ; '.'; void *
0x180023497  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002349c  jmp     loc_180023699
0x1800234a1  mov     [rbp+57h+lpName], r12
0x1800234a5  inc     [rbp+57h+cbMaxSubKeyLen]
0x1800234a8  xor     edx, edx
0x1800234aa  lea     rcx, [rbp+57h+lpName]
0x1800234ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800234b3  mov     r8d, [rbp+57h+cbMaxSubKeyLen]
0x1800234b7  lea     r9, [rbp+57h+lpName]
0x1800234bb  mov     edx, 1
0x1800234c0  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800234c5  mov     ebx, eax
0x1800234c7  test    eax, eax
0x1800234c9  jns     short loc_1800234E8
0x1800234cb  mov     rcx, [rbp+5Fh]; this
0x1800234cf  mov     r9d, eax; char *
0x1800234d2  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x1800234d9  mov     edx, 34h ; '4'; void *
0x1800234de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234e3  jmp     loc_18002368E
0x1800234e8  mov     edi, r12d
0x1800234eb  mov     rbx, [rbp+57h+lpName]
0x1800234ef  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800234f2  mov     [rbp+57h+cchName], eax
0x1800234f5  mov     [rsp+0B0h+lpcValues], r12; lpftLastWriteTime
0x1800234fa  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcchClass
0x1800234ff  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r12; lpClass
0x180023504  mov     [rsp+0B0h+lpcSubKeys], r12; unsigned int
0x180023509  lea     r9, [rbp+57h+cchName]; lpcchName
0x18002350d  mov     r8, rbx; lpName
0x180023510  mov     edx, edi; dwIndex
0x180023512  mov     rcx, r14; hKey
0x180023515  call    cs:__imp_RegEnumKeyExW
0x18002351b  cmp     eax, 103h
0x180023520  jz      loc_18002368B
0x180023526  test    eax, eax
0x180023528  jnz     loc_18002366F
0x18002352e  mov     [rbp+57h+var_50], r12
0x180023532  lea     rax, [rbp+57h+var_50]
0x180023536  mov     [rbp+57h+var_38], rax
0x18002353a  mov     [rbp+57h+phkResult], r12
0x18002353e  mov     [rbp+57h+var_28], 1
0x180023542  mov     [rsp+0B0h+lpcbMaxValueNameLen], r12; lpdwDisposition
0x180023547  lea     rax, [rbp+57h+phkResult]
0x18002354b  mov     [rsp+0B0h+lpcValues], rax; phkResult
0x180023550  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpSecurityAttributes
0x180023555  mov     dword ptr [rsp+0B0h+lpcbMaxSubKeyLen], 0F003Fh; samDesired
0x18002355d  mov     dword ptr [rsp+0B0h+lpcSubKeys], r12d; unsigned int
0x180023562  xor     r9d, r9d; lpClass
0x180023565  xor     r8d, r8d; Reserved
0x180023568  mov     rdx, rbx; lpSubKey
0x18002356b  mov     rcx, r15; hKey
0x18002356e  call    cs:__imp_RegCreateKeyExW
0x180023574  mov     esi, eax
0x180023576  lea     rcx, [rbp+57h+var_38]
0x18002357a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002357f  test    esi, esi
0x180023581  jnz     loc_18002364A
0x180023587  mov     [rbp+57h+hKey], r12
0x18002358b  lea     rax, [rbp+57h+hKey]
0x18002358f  mov     [rbp+57h+var_38], rax
0x180023593  mov     [rbp+57h+phkResult], r12
0x180023597  mov     [rbp+57h+var_28], 1
0x18002359b  lea     rax, [rbp+57h+phkResult]
0x18002359f  mov     [rsp+0B0h+lpcSubKeys], rax; unsigned int
0x1800235a4  mov     r9d, 20019h; samDesired
0x1800235aa  xor     r8d, r8d; ulOptions
0x1800235ad  mov     rdx, rbx; lpSubKey
0x1800235b0  mov     rcx, r14; hKey
0x1800235b3  call    cs:__imp_RegOpenKeyExW
0x1800235b9  mov     esi, eax
0x1800235bb  lea     rcx, [rbp+57h+var_38]
0x1800235bf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800235c4  test    esi, esi
0x1800235c6  jnz     short loc_180023625
0x1800235c8  mov     rdx, [rbp+57h+var_50]; HKEY
0x1800235cc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800235d0  call    ?DuplicateKeyValues@@YAJPEAUHKEY__@@0@Z; DuplicateKeyValues(HKEY__ *,HKEY__ *)
0x1800235d5  mov     esi, eax
0x1800235d7  test    eax, eax
0x1800235d9  js      short loc_1800235F5
0x1800235db  inc     edi
0x1800235dd  lea     rcx, [rbp+57h+hKey]
0x1800235e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800235e6  nop
0x1800235e7  lea     rcx, [rbp+57h+var_50]
0x1800235eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800235f0  jmp     loc_1800234EF
0x1800235f5  mov     rcx, [rbp+5Fh]; this
0x1800235f9  mov     r9d, esi; char *
0x1800235fc  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023603  mov     edx, 43h ; 'C'; void *
0x180023608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002360d  nop
0x18002360e  lea     rcx, [rbp+57h+hKey]
0x180023612  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023617  nop
0x180023618  lea     rcx, [rbp+57h+var_50]
0x18002361c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023621  mov     ebx, esi
0x180023623  jmp     short loc_18002368E
0x180023625  mov     rcx, [rbp+5Fh]; this
0x180023629  mov     r9d, esi; char *
0x18002362c  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023633  mov     edx, 42h ; 'B'; void *
0x180023638  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002363d  mov     ebx, eax
0x18002363f  lea     rcx, [rbp+57h+hKey]
0x180023643  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023648  jmp     short loc_180023664
0x18002364a  mov     rcx, [rbp+5Fh]; this
0x18002364e  mov     r9d, esi; char *
0x180023651  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023658  mov     edx, 40h ; '@'; void *
0x18002365d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023662  mov     ebx, eax
0x180023664  lea     rcx, [rbp+57h+var_50]
0x180023668  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002366d  jmp     short loc_18002368E
0x18002366f  mov     rcx, [rbp+5Fh]; this
0x180023673  mov     r9d, eax; char *
0x180023676  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x18002367d  mov     edx, 3Dh ; '='; void *
0x180023682  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023687  mov     ebx, eax
0x180023689  jmp     short loc_18002368E
0x18002368b  mov     ebx, r12d
0x18002368e  lea     rcx, [rbp+57h+lpName]
0x180023692  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023697  mov     eax, ebx
0x180023699  lea     r11, [rsp+0B0h+var_20]
0x1800236a1  mov     rbx, [r11+30h]
0x1800236a5  mov     rsi, [r11+38h]
0x1800236a9  mov     rsp, r11
0x1800236ac  pop     r15
0x1800236ae  pop     r14
0x1800236b0  pop     r12
0x1800236b2  pop     rdi
0x1800236b3  pop     rbp
0x1800236b4  retn
```
