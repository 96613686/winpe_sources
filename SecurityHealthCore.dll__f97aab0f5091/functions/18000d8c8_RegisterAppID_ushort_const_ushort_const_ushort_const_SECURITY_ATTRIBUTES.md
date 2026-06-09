# RegisterAppID(ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000d8c8`
- end: `0x18000db93`
- name: `?RegisterAppID@@YAJPEBG00PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d384`

## callees

- `0x180004ae0`
- `0x18000d7fc`
- `0x18000d8c8`
- `0x1800cee78`
- `0x1800dc038`
- `0x1800de124`
- `0x1800de258`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000dac0`
- `KERNEL32!GetLastError` at `0x18000dac0`
- `KERNEL32!LocalFree` at `0x18000db17`
- `KERNEL32!LocalFree` at `0x18000db67`
- `KERNEL32!LocalFree` at `0x18000db17`
- `KERNEL32!LocalFree` at `0x18000db67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d9b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d9b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dab6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dab6`

## string_xrefs

- `0x18000da07`: `SecurityHealthService`
- `0x18000d9cf`: `Windows Security Health Service`

## pseudocode

```c
__int64 __fastcall RegisterAppID(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  int v5; // eax
  struct _SECURITY_ATTRIBUTES *v6; // r8
  unsigned int v7; // ebx
  const struct std::nothrow_t *v8; // rdx
  ShieldProvider *v10; // rbx
  int v11; // edi
  const unsigned __int16 *v12; // r9
  _QWORD *v13; // rcx
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r9
  HKEY v18; // rdx
  const unsigned __int16 *v19; // r8
  signed int LastError; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  const void *v24; // [rsp+28h] [rbp-18h]
  ShieldProvider *v25; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+28h] BYREF
  const unsigned __int16 *SecurityDescriptorSize; // [rsp+70h] [rbp+30h] BYREF

  SecurityDescriptorSize = a3;
  hKey = (HKEY)a2;
  SecurityDescriptor = a1;
  v25 = 0;
  v5 = CommonUtil::NewSprintfW(
         (CommonUtil *)&v25,
         (unsigned __int16 **)L"AppID\\%ls",
         L"{2eb6d15c-5239-41cf-82fb-353d20b816cf}");
  v7 = v5;
  if ( v5 < 0 )
  {
    v8 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids,
        (unsigned int)v5);
    if ( v25 )
      operator delete(v25, v8);
    return v7;
  }
  v10 = v25;
  LOBYTE(v6) = (_BYTE)g_fDevMode;
  hKey = 0;
  v11 = ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(v25, (unsigned __int16 *)a4, v6, &hKey);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v15 = 19;
LABEL_12:
    WPP_SF_d(v13[2], v15, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids, (unsigned int)v11);
LABEL_13:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v10 )
      operator delete(v10, v14);
    return (unsigned int)v11;
  }
  v11 = CommonUtil::UtilRegSetValueString((CommonUtil *)hKey, 0, L"Windows Security Health Service", v12);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v15 = 20;
    goto LABEL_12;
  }
  v11 = CommonUtil::UtilRegSetValueString((CommonUtil *)hKey, (HKEY)&stru_1800F4C10, L"SecurityHealthService", v16);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v15 = 21;
    goto LABEL_12;
  }
  v11 = CommonUtil::UtilRegSetValueString((CommonUtil *)hKey, (HKEY)&stru_1800F4C30, &word_1800F4E78, v17);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v15 = 22;
    goto LABEL_12;
  }
  SecurityDescriptor = 0;
  LODWORD(SecurityDescriptorSize) = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;S-1-15-2-2"
           "743877165-1931364543-2468930561-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
          1u,
          &SecurityDescriptor,
          (PULONG)&SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 23;
LABEL_37:
        WPP_SF_d(v21[2], v22, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids, (unsigned int)v11);
        goto LABEL_38;
      }
      goto LABEL_38;
    }
  }
  v11 = CommonUtil::UtilRegSetValue(
          (CommonUtil *)hKey,
          v18,
          v19,
          (unsigned int)SecurityDescriptorSize,
          (unsigned __int64)SecurityDescriptor,
          v24);
  if ( v11 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 24;
      goto LABEL_37;
    }
LABEL_38:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_13;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    operator delete(v10, v23);
  return 0;
}

```

## disassembly

```asm
0x18000d8c8  mov     [rsp-18h+SecurityDescriptorSize], r8
0x18000d8cd  mov     [rsp-18h+hKey], rdx
0x18000d8d2  mov     [rsp-18h+SecurityDescriptor], rcx
0x18000d8d7  push    rbp
0x18000d8d8  push    rbx
0x18000d8d9  push    rdi
0x18000d8da  mov     rbp, rsp
0x18000d8dd  sub     rsp, 40h
0x18000d8e1  lea     r8, a2eb6d15c523941; "{2eb6d15c-5239-41cf-82fb-353d20b816cf}"
0x18000d8e8  mov     [rbp+var_10], 0
0x18000d8f0  lea     rdx, aAppidLs; "AppID\\%ls"
0x18000d8f7  mov     rdi, r9
0x18000d8fa  lea     rcx, [rbp+var_10]; this
0x18000d8fe  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18000d903  mov     ebx, eax
0x18000d905  test    eax, eax
0x18000d907  jns     short loc_18000D94F
0x18000d909  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d910  lea     rdx, WPP_GLOBAL_Control
0x18000d917  cmp     rcx, rdx
0x18000d91a  jz      short loc_18000D93A
0x18000d91c  test    byte ptr [rcx+1Ch], 1
0x18000d920  jz      short loc_18000D93A
0x18000d922  mov     rcx, [rcx+10h]
0x18000d926  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000d92d  mov     edx, 12h
0x18000d932  mov     r9d, eax
0x18000d935  call    WPP_SF_d
0x18000d93a  mov     rcx, [rbp+var_10]; void *
0x18000d93e  test    rcx, rcx
0x18000d941  jz      short loc_18000D948
0x18000d943  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d948  mov     eax, ebx
0x18000d94a  jmp     loc_18000DB8B
0x18000d94f  mov     rbx, [rbp+var_10]
0x18000d953  lea     r9, [rbp+hKey]; bool
0x18000d957  mov     r8b, cs:?g_fDevMode@@3_NA; struct _SECURITY_ATTRIBUTES *
0x18000d95e  mov     rcx, rbx; this
0x18000d961  mov     rdx, rdi; unsigned __int16 *
0x18000d964  mov     [rbp+hKey], 0
0x18000d96c  call    ?GetRegKeyUnderClassesReAcledForWrite@ShieldProvider@@YAJPEAGPEAU_SECURITY_ATTRIBUTES@@_NPEAPEAUHKEY__@@@Z; ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(ushort *,_SECURITY_ATTRIBUTES *,bool,HKEY__ * *)
0x18000d971  mov     edi, eax
0x18000d973  test    eax, eax
0x18000d975  jns     short loc_18000D9CB
0x18000d977  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d97e  lea     rdx, WPP_GLOBAL_Control
0x18000d985  cmp     rcx, rdx
0x18000d988  jz      short loc_18000D9A8
0x18000d98a  test    byte ptr [rcx+1Ch], 1
0x18000d98e  jz      short loc_18000D9A8
0x18000d990  mov     edx, 13h
0x18000d995  mov     rcx, [rcx+10h]
0x18000d999  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000d9a0  mov     r9d, edi
0x18000d9a3  call    WPP_SF_d
0x18000d9a8  mov     rcx, [rbp+hKey]; hKey
0x18000d9ac  test    rcx, rcx
0x18000d9af  jz      short loc_18000D9B7
0x18000d9b1  call    cs:__imp_RegCloseKey
0x18000d9b7  test    rbx, rbx
0x18000d9ba  jz      short loc_18000D9C4
0x18000d9bc  mov     rcx, rbx; void *
0x18000d9bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d9c4  mov     eax, edi
0x18000d9c6  jmp     loc_18000DB8B
0x18000d9cb  mov     rcx, [rbp+hKey]; this
0x18000d9cf  lea     r8, aWindowsSecurit; "Windows Security Health Service"
0x18000d9d6  xor     edx, edx; HKEY
0x18000d9d8  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000d9dd  mov     edi, eax
0x18000d9df  test    eax, eax
0x18000d9e1  jns     short loc_18000DA03
0x18000d9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ea  lea     rdx, WPP_GLOBAL_Control
0x18000d9f1  cmp     rcx, rdx
0x18000d9f4  jz      short loc_18000D9A8
0x18000d9f6  test    byte ptr [rcx+1Ch], 1
0x18000d9fa  jz      short loc_18000D9A8
0x18000d9fc  mov     edx, 14h
0x18000da01  jmp     short loc_18000D995
0x18000da03  mov     rcx, [rbp+hKey]; this
0x18000da07  lea     r8, aSecurityhealth_10; "SecurityHealthService"
0x18000da0e  lea     rdx, stru_1800F4C10; HKEY
0x18000da15  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000da1a  mov     edi, eax
0x18000da1c  test    eax, eax
0x18000da1e  jns     short loc_18000DA4B
0x18000da20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da27  lea     rdx, WPP_GLOBAL_Control
0x18000da2e  cmp     rcx, rdx
0x18000da31  jz      loc_18000D9A8
0x18000da37  test    byte ptr [rcx+1Ch], 1
0x18000da3b  jz      loc_18000D9A8
0x18000da41  mov     edx, 15h
0x18000da46  jmp     loc_18000D995
0x18000da4b  mov     rcx, [rbp+hKey]; this
0x18000da4f  lea     r8, word_1800F4E78; unsigned __int16 *
0x18000da56  lea     rdx, stru_1800F4C30; HKEY
0x18000da5d  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000da62  mov     edi, eax
0x18000da64  test    eax, eax
0x18000da66  jns     short loc_18000DA93
0x18000da68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da6f  lea     rdx, WPP_GLOBAL_Control
0x18000da76  cmp     rcx, rdx
0x18000da79  jz      loc_18000D9A8
0x18000da7f  test    byte ptr [rcx+1Ch], 1
0x18000da83  jz      loc_18000D9A8
0x18000da89  mov     edx, 16h
0x18000da8e  jmp     loc_18000D995
0x18000da93  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000da97  mov     [rbp+SecurityDescriptor], 0
0x18000da9f  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000daa3  mov     dword ptr [rbp+SecurityDescriptorSize], 0
0x18000daaa  mov     edx, 1; StringSDRevision
0x18000daaf  lea     rcx, aOBagBadACcdclc_0; "O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCL"...
0x18000dab6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000dabc  test    eax, eax
0x18000dabe  jnz     short loc_18000DB22
0x18000dac0  call    cs:__imp_GetLastError
0x18000dac6  mov     edi, eax
0x18000dac8  test    eax, eax
0x18000daca  jle     short loc_18000DAD5
0x18000dacc  movzx   edi, ax
0x18000dacf  or      edi, 80070000h
0x18000dad5  test    edi, edi
0x18000dad7  jns     short loc_18000DB22
0x18000dad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dae0  lea     rdx, WPP_GLOBAL_Control
0x18000dae7  cmp     rcx, rdx
0x18000daea  jz      short loc_18000DB0A
0x18000daec  test    byte ptr [rcx+1Ch], 1
0x18000daf0  jz      short loc_18000DB0A
0x18000daf2  mov     edx, 17h
0x18000daf7  mov     rcx, [rcx+10h]
0x18000dafb  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000db02  mov     r9d, edi
0x18000db05  call    WPP_SF_d
0x18000db0a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000db0e  test    rcx, rcx
0x18000db11  jz      loc_18000D9A8
0x18000db17  call    cs:__imp_LocalFree
0x18000db1d  jmp     loc_18000D9A8
0x18000db22  mov     rax, [rbp+SecurityDescriptor]
0x18000db26  mov     r9d, dword ptr [rbp+SecurityDescriptorSize]; unsigned int
0x18000db2a  mov     rcx, [rbp+hKey]; this
0x18000db2e  mov     [rsp+40h+var_20], rax; unsigned __int64
0x18000db33  call    ?UtilRegSetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValue(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x18000db38  mov     edi, eax
0x18000db3a  test    eax, eax
0x18000db3c  jns     short loc_18000DB5E
0x18000db3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db45  lea     rdx, WPP_GLOBAL_Control
0x18000db4c  cmp     rcx, rdx
0x18000db4f  jz      short loc_18000DB0A
0x18000db51  test    byte ptr [rcx+1Ch], 1
0x18000db55  jz      short loc_18000DB0A
0x18000db57  mov     edx, 18h
0x18000db5c  jmp     short loc_18000DAF7
0x18000db5e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000db62  test    rcx, rcx
0x18000db65  jz      short loc_18000DB6D
0x18000db67  call    cs:__imp_LocalFree
0x18000db6d  mov     rcx, [rbp+hKey]; hKey
0x18000db71  test    rcx, rcx
0x18000db74  jz      short loc_18000DB7C
0x18000db76  call    cs:__imp_RegCloseKey
0x18000db7c  test    rbx, rbx
0x18000db7f  jz      short loc_18000DB89
0x18000db81  mov     rcx, rbx; void *
0x18000db84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000db89  xor     eax, eax
0x18000db8b  add     rsp, 40h
0x18000db8f  pop     rdi
0x18000db90  pop     rbx
0x18000db91  pop     rbp
0x18000db92  retn
```
