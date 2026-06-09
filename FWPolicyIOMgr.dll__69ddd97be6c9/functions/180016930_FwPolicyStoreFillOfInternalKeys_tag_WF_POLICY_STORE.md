# FwPolicyStoreFillOfInternalKeys(_tag_WF_POLICY_STORE *)

- ea: `0x180016930`
- end: `0x180016b11`
- name: `?FwPolicyStoreFillOfInternalKeys@@YAJPEAU_tag_WF_POLICY_STORE@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct _tag_WF_POLICY_STORE *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016790`
- `0x18001c140`
- `0x18001e670`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180016930`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016a12`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016a12`
- `fwbase!FwRegOpenKey` at `0x1800169bd`
- `fwbase!FwRegOpenKey` at `0x180016a6c`
- `fwbase!FwRegOpenKey` at `0x1800169bd`
- `fwbase!FwRegOpenKey` at `0x180016a6c`
- `fwbase!FwLicensingIsXbox` at `0x1800169f4`
- `fwbase!FwLicensingIsXbox` at `0x180016a98`
- `fwbase!FwLicensingIsXbox` at `0x1800169f4`
- `fwbase!FwLicensingIsXbox` at `0x180016a98`
- `fwbase!FwRegCreateKey` at `0x180016a33`
- `fwbase!FwRegCreateKey` at `0x180016ab9`
- `fwbase!FwRegCreateKey` at `0x180016a33`
- `fwbase!FwRegCreateKey` at `0x180016ab9`

## string_xrefs

- `0x180016a04`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x180016a0b`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwPolicyStoreFillOfInternalKeys(struct _tag_WF_POLICY_STORE *a1)
{
  bool v2; // zf
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int Key; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v2 = *((_DWORD *)a1 + 2) == 6;
  v17 = 0;
  if ( v2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = FwRegOpenKey(
         -2147483646,
         *((_QWORD *)a1 + 2),
         *((unsigned int *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
         (char *)a1 + 40,
         &v17);
  Key = v3;
  if ( v3 >= 0 )
  {
    if ( !v17 )
    {
      if ( (unsigned int)FwLicensingIsXbox(v5, v4, v6, v7)
        || !(unsigned int)_o__wcsnicmp(
                            g_FwPersistentStoreRootKey,
                            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                            73) )
      {
        Key = -2147024894;
      }
      else
      {
        Key = FwRegCreateKey(
                -2147483646,
                *((_QWORD *)a1 + 2),
                *((unsigned int *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
                (char *)a1 + 40);
      }
    }
    v11 = *((_QWORD *)a1 + 4);
    if ( v11 )
    {
      v3 = FwRegOpenKey(
             -2147483646,
             v11,
             *((unsigned int *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
             (char *)a1 + 48,
             &v17);
      Key = v3;
      if ( v3 >= 0 )
      {
        if ( !v17 && !(unsigned int)FwLicensingIsXbox(v13, v12, v14, v15) )
        {
          v3 = FwRegCreateKey(
                 -2147483646,
                 *((_QWORD *)a1 + 4),
                 *((unsigned int *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
                 (char *)a1 + 48);
          Key = v3;
          if ( v3 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v10 = 197;
              goto LABEL_26;
            }
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 196;
          goto LABEL_26;
        }
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 195;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v3);
    }
  }
  return Key;
}

```

## disassembly

```asm
0x180016930  mov     [rsp+arg_8], rbx
0x180016935  mov     [rsp+arg_10], rbp
0x18001693a  push    rsi
0x18001693b  push    rdi
0x18001693c  push    r14
0x18001693e  sub     rsp, 40h
0x180016942  mov     rax, cs:__security_cookie
0x180016949  xor     rax, rsp
0x18001694c  mov     [rsp+58h+var_20], rax
0x180016951  mov     rdi, rcx
0x180016954  mov     rcx, cs:WPP_GLOBAL_Control
0x18001695b  lea     rbp, WPP_GLOBAL_Control
0x180016962  cmp     rcx, rbp
0x180016965  jz      short loc_180016982
0x180016967  test    byte ptr [rcx+1Ch], 8
0x18001696b  jz      short loc_180016982
0x18001696d  mov     rcx, [rcx+10h]
0x180016971  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180016978  mov     edx, 0C2h
0x18001697d  call    WPP_SF_
0x180016982  cmp     dword ptr [rdi+8], 6
0x180016986  mov     [rsp+58h+var_28], 0
0x18001698e  jnz     short loc_180016995
0x180016990  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016995  movsxd  r8, dword ptr [rdi+0Ch]
0x180016999  lea     rax, [rsp+58h+var_28]
0x18001699e  mov     rdx, [rdi+10h]
0x1800169a2  lea     r14, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x1800169a9  lea     r9, [rdi+28h]
0x1800169ad  mov     [rsp+58h+var_38], rax
0x1800169b2  mov     rcx, 0FFFFFFFF80000002h
0x1800169b9  mov     r8d, [r14+r8*4]
0x1800169bd  call    cs:__imp_FwRegOpenKey
0x1800169c3  mov     ebx, eax
0x1800169c5  test    eax, eax
0x1800169c7  jns     short loc_1800169ED
0x1800169c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169d0  cmp     rcx, rbp
0x1800169d3  jz      loc_180016AEF
0x1800169d9  test    byte ptr [rcx+1Ch], 1
0x1800169dd  jz      loc_180016AEF
0x1800169e3  mov     edx, 0C3h
0x1800169e8  jmp     loc_180016ADC
0x1800169ed  cmp     [rsp+58h+var_28], 0
0x1800169f2  jnz     short loc_180016A42
0x1800169f4  call    cs:__imp_FwLicensingIsXbox
0x1800169fa  test    eax, eax
0x1800169fc  jnz     short loc_180016A3D
0x1800169fe  mov     r8d, 49h ; 'I'
0x180016a04  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180016a0b  lea     rcx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180016a12  call    cs:__imp__o__wcsnicmp
0x180016a18  test    eax, eax
0x180016a1a  jz      short loc_180016A3D
0x180016a1c  movsxd  r8, dword ptr [rdi+0Ch]
0x180016a20  lea     r9, [rdi+28h]
0x180016a24  mov     rdx, [rdi+10h]
0x180016a28  mov     rcx, 0FFFFFFFF80000002h
0x180016a2f  mov     r8d, [r14+r8*4]
0x180016a33  call    cs:__imp_FwRegCreateKey
0x180016a39  mov     ebx, eax
0x180016a3b  jmp     short loc_180016A42
0x180016a3d  mov     ebx, 80070002h
0x180016a42  mov     rdx, [rdi+20h]
0x180016a46  test    rdx, rdx
0x180016a49  jz      loc_180016AEF
0x180016a4f  movsxd  r8, dword ptr [rdi+0Ch]
0x180016a53  lea     rax, [rsp+58h+var_28]
0x180016a58  lea     r9, [rdi+30h]
0x180016a5c  mov     [rsp+58h+var_38], rax
0x180016a61  mov     rcx, 0FFFFFFFF80000002h
0x180016a68  mov     r8d, [r14+r8*4]
0x180016a6c  call    cs:__imp_FwRegOpenKey
0x180016a72  mov     ebx, eax
0x180016a74  test    eax, eax
0x180016a76  jns     short loc_180016A91
0x180016a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a7f  cmp     rcx, rbp
0x180016a82  jz      short loc_180016AEF
0x180016a84  test    byte ptr [rcx+1Ch], 1
0x180016a88  jz      short loc_180016AEF
0x180016a8a  mov     edx, 0C4h
0x180016a8f  jmp     short loc_180016ADC
0x180016a91  cmp     [rsp+58h+var_28], 0
0x180016a96  jnz     short loc_180016AEF
0x180016a98  call    cs:__imp_FwLicensingIsXbox
0x180016a9e  test    eax, eax
0x180016aa0  jnz     short loc_180016AEF
0x180016aa2  movsxd  r8, dword ptr [rdi+0Ch]
0x180016aa6  lea     r9, [rdi+30h]
0x180016aaa  mov     rdx, [rdi+20h]
0x180016aae  mov     rcx, 0FFFFFFFF80000002h
0x180016ab5  mov     r8d, [r14+r8*4]
0x180016ab9  call    cs:__imp_FwRegCreateKey
0x180016abf  mov     ebx, eax
0x180016ac1  test    eax, eax
0x180016ac3  jns     short loc_180016AEF
0x180016ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016acc  cmp     rcx, rbp
0x180016acf  jz      short loc_180016AEF
0x180016ad1  test    byte ptr [rcx+1Ch], 1
0x180016ad5  jz      short loc_180016AEF
0x180016ad7  mov     edx, 0C5h
0x180016adc  mov     rcx, [rcx+10h]
0x180016ae0  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180016ae7  mov     r9d, eax
0x180016aea  call    WPP_SF_d
0x180016aef  mov     eax, ebx
0x180016af1  mov     rcx, [rsp+58h+var_20]
0x180016af6  xor     rcx, rsp; StackCookie
0x180016af9  call    __security_check_cookie
0x180016afe  mov     rbx, [rsp+58h+arg_8]
0x180016b03  mov     rbp, [rsp+58h+arg_10]
0x180016b08  add     rsp, 40h
0x180016b0c  pop     r14
0x180016b0e  pop     rdi
0x180016b0f  pop     rsi
0x180016b10  retn
```
