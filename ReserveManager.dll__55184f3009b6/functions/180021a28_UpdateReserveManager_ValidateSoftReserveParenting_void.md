# UpdateReserveManager::ValidateSoftReserveParenting(void)

- ea: `0x180021a28`
- end: `0x180021c30`
- name: `?ValidateSoftReserveParenting@UpdateReserveManager@@AEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800192e0`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180014e34`
- `0x180015034`
- `0x180015ad0`
- `0x180021a28`
- `0x180027414`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180021bdc`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180021bdc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180021b06`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180021b06`

## string_xrefs

- `0x180021a5c`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021b1f`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021be8`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021c08`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"SoftParentingValidated", ( 4ul ), &Value, sizeof(Value))`
- `0x180021a76`: `UpdateReserveManager::ValidateSoftReserveParenting`
- `0x180021b32`: `UpdateReserveManager::ValidateSoftReserveParenting`
- `0x180021bfd`: `UpdateReserveManager::ValidateSoftReserveParenting`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ValidateSoftReserveParenting(HKEY *this)
{
  __int64 result; // rax
  HKEY v3; // rcx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  const char *v7; // rax
  HKEY v8; // rcx
  __int64 v9; // r8
  HKEY v10; // rcx
  bool v11; // [rsp+30h] [rbp-40h] BYREF
  const char *v12; // [rsp+38h] [rbp-38h] BYREF
  const char *v13; // [rsp+40h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-28h]
  const char *v15; // [rsp+50h] [rbp-20h]
  int Data; // [rsp+58h] [rbp-18h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    if ( *((_BYTE *)this + 1176) )
    {
      v14 = 4583;
      v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v13 = "UpdateReserveManager::ValidateSoftReserveParenting";
      v15 = "static_cast<DWORD>(50L)";
      RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
      return 2147942450LL;
    }
    v11 = 0;
    result = UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport(this, &v11);
    if ( (int)result >= 0 )
    {
      if ( v11 )
        goto LABEL_14;
      v3 = this[14];
      v11 = 0;
      result = DoesRegDwordExist(v3, L"CurrentControlSet\\Control\\FileSystem", L"SuppressInheritanceSupport", &v11);
      if ( (int)result < 0 )
        return result;
      if ( v11 )
      {
LABEL_14:
        v8 = this[13];
        v11 = 0;
        result = DoesRegDwordExist(
                   v8,
                   L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                   L"SoftParentingValidated",
                   &v11);
        if ( (int)result < 0 )
          return result;
        if ( !v11 )
        {
          result = StorageReserveHelper::FixReserveAreaUntaggedParent(
                     (StorageReserveHelper *)(this + 82),
                     (const unsigned __int16 *)2,
                     v9);
          if ( (int)result < 0 )
            return result;
          v10 = this[13];
          Data = 1;
          v5 = RegSetKeyValueW(
                 v10,
                 L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                 L"SoftParentingValidated",
                 4u,
                 &Data,
                 4u);
          if ( v5 )
          {
            v14 = 4635;
            v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v6 = (int)v5 <= 0;
            v13 = "UpdateReserveManager::ValidateSoftReserveParenting";
            v7 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"Soft"
                 "ParentingValidated\", ( 4ul ), &Value, sizeof(Value))";
            goto LABEL_11;
          }
        }
      }
      else
      {
        v4 = RegDeleteKeyValueW(
               this[13],
               L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
               L"SoftParentingValidated");
        v5 = v4;
        if ( v4 != 2 )
        {
          v6 = v4 <= 0;
          if ( v4 )
          {
            v14 = 4609;
            v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v13 = "UpdateReserveManager::ValidateSoftReserveParenting";
            v7 = "RetValue";
LABEL_11:
            v15 = v7;
            if ( !v6 )
              v5 = (unsigned __int16)v5 | 0x80070000;
            RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v5);
            return v5;
          }
        }
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021a28  mov     [rsp-8+arg_8], rbx
0x180021a2d  push    rbp
0x180021a2e  mov     rbp, rsp
0x180021a31  sub     rsp, 70h
0x180021a35  mov     rax, cs:__security_cookie
0x180021a3c  xor     rax, rsp
0x180021a3f  mov     [rbp+var_10], rax
0x180021a43  mov     rbx, rcx
0x180021a46  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180021a4b  test    eax, eax
0x180021a4d  js      loc_180021C16
0x180021a53  cmp     byte ptr [rbx+498h], 0
0x180021a5a  jz      short loc_180021AA5
0x180021a5c  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021a63  mov     [rbp+var_28], 11E7h
0x180021a6b  mov     [rbp+var_38], rax
0x180021a6f  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180021a76  lea     rax, aUpdatereservem_32; "UpdateReserveManager::ValidateSoftReser"...
0x180021a7d  mov     r8d, 80070032h
0x180021a83  mov     [rbp+var_30], rax
0x180021a87  lea     rcx, [rbp+var_38]
0x180021a8b  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x180021a92  mov     [rbp+var_20], rax
0x180021a96  call    RtlReportErrorOrigination
0x180021a9b  mov     eax, 80070032h
0x180021aa0  jmp     loc_180021C16
0x180021aa5  lea     rdx, [rbp+var_40]; bool *
0x180021aa9  mov     [rbp+var_40], 0
0x180021aad  mov     rcx, rbx; this
0x180021ab0  call    ?DoesBuildHaveSuppressInheritanceSupport@UpdateReserveManager@@AEAAJPEA_N@Z; UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport(bool *)
0x180021ab5  test    eax, eax
0x180021ab7  js      loc_180021C16
0x180021abd  cmp     [rbp+var_40], 0
0x180021ac1  jnz     loc_180021B6D
0x180021ac7  mov     rcx, [rbx+70h]; HKEY
0x180021acb  lea     r9, [rbp+var_40]; bool *
0x180021acf  lea     r8, aSuppressinheri; "SuppressInheritanceSupport"
0x180021ad6  mov     [rbp+var_40], 0
0x180021ada  lea     rdx, aCurrentcontrol_0; "CurrentControlSet\\Control\\FileSystem"
0x180021ae1  call    ?DoesRegDwordExist@@YAJQEAUHKEY__@@QEB_W1PEA_N@Z; DoesRegDwordExist(HKEY__ * const,wchar_t const * const,wchar_t const * const,bool *)
0x180021ae6  test    eax, eax
0x180021ae8  js      loc_180021C16
0x180021aee  cmp     [rbp+var_40], 0
0x180021af2  jnz     short loc_180021B6D
0x180021af4  mov     rcx, [rbx+68h]; hKey
0x180021af8  lea     r8, aSoftparentingv; "SoftParentingValidated"
0x180021aff  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180021b06  call    cs:__imp_RegDeleteKeyValueW
0x180021b0c  mov     ebx, eax
0x180021b0e  cmp     eax, 2
0x180021b11  jz      loc_180021C14
0x180021b17  test    eax, eax
0x180021b19  jz      loc_180021C14
0x180021b1f  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021b26  mov     [rbp+var_28], 1201h
0x180021b2e  mov     [rbp+var_38], rax
0x180021b32  lea     rax, aUpdatereservem_32; "UpdateReserveManager::ValidateSoftReser"...
0x180021b39  mov     [rbp+var_30], rax
0x180021b3d  lea     rax, aRetvalue; "RetValue"
0x180021b44  mov     [rbp+var_20], rax
0x180021b48  jle     short loc_180021B53
0x180021b4a  movzx   ebx, bx
0x180021b4d  or      ebx, 80070000h
0x180021b53  mov     r8d, ebx
0x180021b56  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180021b5d  lea     rcx, [rbp+var_38]
0x180021b61  call    RtlReportErrorOrigination
0x180021b66  mov     eax, ebx
0x180021b68  jmp     loc_180021C16
0x180021b6d  mov     rcx, [rbx+68h]; HKEY
0x180021b71  lea     r9, [rbp+var_40]; bool *
0x180021b75  lea     r8, aSoftparentingv; "SoftParentingValidated"
0x180021b7c  mov     [rbp+var_40], 0
0x180021b80  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180021b87  call    ?DoesRegDwordExist@@YAJQEAUHKEY__@@QEB_W1PEA_N@Z; DoesRegDwordExist(HKEY__ * const,wchar_t const * const,wchar_t const * const,bool *)
0x180021b8c  test    eax, eax
0x180021b8e  js      loc_180021C16
0x180021b94  cmp     [rbp+var_40], 0
0x180021b98  jnz     short loc_180021C14
0x180021b9a  lea     rcx, [rbx+290h]; this
0x180021ba1  mov     edx, 2; unsigned __int16 *
0x180021ba6  call    ?FixReserveAreaUntaggedParent@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z; StorageReserveHelper::FixReserveAreaUntaggedParent(ushort const *,_STORAGE_RESERVE_ID)
0x180021bab  test    eax, eax
0x180021bad  js      short loc_180021C16
0x180021baf  mov     rcx, [rbx+68h]; hKey
0x180021bb3  lea     rax, [rbp+Data]
0x180021bb7  mov     r9d, 4; dwType
0x180021bbd  mov     [rbp+Data], 1
0x180021bc4  mov     [rsp+70h+cbData], r9d; cbData
0x180021bc9  lea     r8, aSoftparentingv; "SoftParentingValidated"
0x180021bd0  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180021bd7  mov     [rsp+70h+lpData], rax; lpData
0x180021bdc  call    cs:__imp_RegSetKeyValueW
0x180021be2  mov     ebx, eax
0x180021be4  test    eax, eax
0x180021be6  jz      short loc_180021C14
0x180021be8  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021bef  mov     [rbp+var_28], 121Bh
0x180021bf7  mov     [rbp+var_38], rax
0x180021bfb  test    ebx, ebx
0x180021bfd  lea     rax, aUpdatereservem_32; "UpdateReserveManager::ValidateSoftReser"...
0x180021c04  mov     [rbp+var_30], rax
0x180021c08  lea     rax, aRegsetkeyvalue_4; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180021c0f  jmp     loc_180021B44
0x180021c14  xor     eax, eax
0x180021c16  mov     rcx, [rbp+var_10]
0x180021c1a  xor     rcx, rsp; StackCookie
0x180021c1d  call    __security_check_cookie
0x180021c22  mov     rbx, [rsp+70h+arg_8]
0x180021c2a  add     rsp, 70h
0x180021c2e  pop     rbp
0x180021c2f  retn
```
