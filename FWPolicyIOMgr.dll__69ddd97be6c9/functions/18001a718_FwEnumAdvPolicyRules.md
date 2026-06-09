# FwEnumAdvPolicyRules

- ea: `0x18001a718`
- end: `0x18001aa2d`
- name: `FwEnumAdvPolicyRules`
- size: `789`
- prototype: `__int64 __usercall@<rax>(struct _tag_FW_RULE_MANIPULATOR *@<rcx>, struct _tag_FW_BLOB_RULE **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba5c`

## callees

- `0x1800042c4`
- `0x1800179e4`
- `0x18001a718`
- `0x18001ce10`
- `0x18001e9ac`
- `0x18001f650`
- `0x180031008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a959`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a959`
- `fwbase!FwRegOpenKey` at `0x18001a7a7`
- `fwbase!FwRegOpenKey` at `0x18001a7a7`
- `fwbase!FwRegCloseKey` at `0x18001a8eb`
- `fwbase!FwRegCloseKey` at `0x18001a8eb`

## pseudocode

```c
__int64 __fastcall FwEnumAdvPolicyRules(
        struct _tag_FW_RULE_MANIPULATOR *a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        struct _tag_FW_BLOB_RULE **a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v7; // edi
  int v11; // eax
  signed int v12; // ebx
  LPCOLESTR v13; // rcx
  __int64 v14; // rdx
  DWORD v16; // eax
  __int64 *v17; // r9
  __int64 v18; // rcx
  DWORD i; // esi
  LSTATUS v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v7 = 0;
  v25 = a4;
  v26 = a3;
  hKey = 0;
  v29 = 0;
  v24 = 0;
  cSubKeys = 0;
  cchName = 255;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = FwRegOpenKey(a2, a3, 9, &hKey, &v29);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( !v29 )
      return 0;
    v11 = FwAdvPolicyRegQueryNumKeys(hKey, &cSubKeys);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v16 = cSubKeys;
      if ( cSubKeys )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v16 )
            goto LABEL_20;
          v24 = 0;
          v20 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
          if ( v20 == 259 )
            goto LABEL_20;
          v12 = v20 > 0 ? (unsigned __int16)v20 | 0x80070000 : v20;
          if ( v12 < 0 )
            break;
          v21 = FwAdvPolicySubSectionLoadRules(a1, hKey, Name, a5, &v24, a6, a7);
          v12 = v21;
          if ( v21 < 0 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
              goto LABEL_27;
            if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v22 = 44;
              v23 = (unsigned int)v21;
LABEL_43:
              WPP_SF_d(*((_QWORD *)v13 + 2), v22, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v23);
              v13 = WPP_GLOBAL_Control;
              goto LABEL_22;
            }
            goto LABEL_22;
          }
          v7 += v24;
          v16 = cSubKeys;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_27;
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v22 = 43;
          v23 = (unsigned int)v12;
          goto LABEL_43;
        }
        goto LABEL_22;
      }
      v11 = FwAdvPolicySubSectionLoadRules(a1, hKey, 0, a5, &v24, a6, a7);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v7 = v24;
LABEL_20:
        *v25 = v7;
        if ( v12 >= 0 )
          goto LABEL_27;
        goto LABEL_21;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 42;
        goto LABEL_7;
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 41;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 37;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, (unsigned int)v11);
LABEL_21:
      v13 = WPP_GLOBAL_Control;
    }
  }
LABEL_22:
  if ( v13 != (LPCOLESTR)&WPP_GLOBAL_Control && (v13[14] & 4) != 0 )
  {
    v17 = &qword_18003DA20;
    v18 = *((_QWORD *)v13 + 2);
    if ( v26 )
      LODWORD(v17) = v26;
    WPP_SF_Sd(v18, 45, (unsigned int)WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, (_DWORD)v17, v12);
  }
LABEL_27:
  FwRegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001a718  push    rbp
0x18001a71a  push    rbx
0x18001a71b  push    rsi
0x18001a71c  push    rdi
0x18001a71d  push    r12
0x18001a71f  push    r13
0x18001a721  push    r14
0x18001a723  push    r15
0x18001a725  lea     rbp, [rsp-188h]
0x18001a72d  sub     rsp, 288h
0x18001a734  mov     rax, cs:__security_cookie
0x18001a73b  xor     rax, rsp
0x18001a73e  mov     [rbp+1C0h+var_50], rax
0x18001a745  mov     r13, [rbp+1C0h+arg_20]
0x18001a74c  xor     edi, edi
0x18001a74e  mov     [rsp+2C0h+var_278], r9
0x18001a753  mov     rsi, r8
0x18001a756  mov     [rsp+2C0h+var_270], r8
0x18001a75b  mov     rbx, rdx
0x18001a75e  mov     [rsp+2C0h+hKey], 0
0x18001a767  mov     r12, rcx
0x18001a76a  mov     [rsp+2C0h+var_25C], 0
0x18001a772  mov     [rsp+2C0h+var_280], edi
0x18001a776  mov     [rsp+2C0h+cSubKeys], edi
0x18001a77a  mov     [rsp+2C0h+cchName], 0FFh
0x18001a782  test    rdx, rdx
0x18001a785  jnz     short loc_18001A78C
0x18001a787  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a78c  lea     rax, [rsp+2C0h+var_25C]
0x18001a791  mov     r8d, 9
0x18001a797  lea     r9, [rsp+2C0h+hKey]
0x18001a79c  mov     [rsp+2C0h+lpReserved], rax
0x18001a7a1  mov     rdx, rsi
0x18001a7a4  mov     rcx, rbx
0x18001a7a7  call    cs:__imp_FwRegOpenKey
0x18001a7ad  lea     r14, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001a7b4  mov     ebx, eax
0x18001a7b6  lea     rsi, WPP_GLOBAL_Control
0x18001a7bd  test    eax, eax
0x18001a7bf  jns     short loc_18001A7F4
0x18001a7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7c8  cmp     rcx, rsi
0x18001a7cb  jz      loc_18001A8A8
0x18001a7d1  test    byte ptr [rcx+1Ch], 1
0x18001a7d5  jz      loc_18001A8A8
0x18001a7db  mov     edx, 25h ; '%'
0x18001a7e0  mov     rcx, [rcx+10h]
0x18001a7e4  mov     r9d, eax
0x18001a7e7  mov     r8, r14
0x18001a7ea  call    WPP_SF_d
0x18001a7ef  jmp     loc_18001A8A1
0x18001a7f4  cmp     [rsp+2C0h+var_25C], edi
0x18001a7f8  jnz     short loc_18001A801
0x18001a7fa  xor     eax, eax
0x18001a7fc  jmp     loc_18001A8F3
0x18001a801  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001a806  lea     rdx, [rsp+2C0h+cSubKeys]; lpcSubKeys
0x18001a80b  call    FwAdvPolicyRegQueryNumKeys
0x18001a810  mov     ebx, eax
0x18001a812  test    eax, eax
0x18001a814  jns     short loc_18001A833
0x18001a816  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a81d  cmp     rcx, rsi
0x18001a820  jz      loc_18001A8A8
0x18001a826  test    byte ptr [rcx+1Ch], 1
0x18001a82a  jz      short loc_18001A8A8
0x18001a82c  mov     edx, 29h ; ')'
0x18001a831  jmp     short loc_18001A7E0
0x18001a833  mov     eax, [rsp+2C0h+cSubKeys]
0x18001a837  test    eax, eax
0x18001a839  jnz     loc_18001A916
0x18001a83f  mov     eax, [rbp+1C0h+arg_30]
0x18001a845  mov     r9, r13; struct _tag_FW_BLOB_RULE **
0x18001a848  mov     rdx, [rsp+2C0h+hKey]; HKEY
0x18001a84d  xor     r8d, r8d; unsigned __int16 *
0x18001a850  mov     dword ptr [rsp+2C0h+lpcchClass], eax; unsigned int
0x18001a854  mov     rcx, r12; struct _tag_FW_RULE_MANIPULATOR *
0x18001a857  mov     eax, [rbp+1C0h+arg_28]
0x18001a85d  mov     dword ptr [rsp+2C0h+lpClass], eax; unsigned int
0x18001a861  lea     rax, [rsp+2C0h+var_280]
0x18001a866  mov     [rsp+2C0h+lpReserved], rax; unsigned int *
0x18001a86b  call    ?FwAdvPolicySubSectionLoadRules@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAUHKEY__@@PEBGPEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z; FwAdvPolicySubSectionLoadRules(_tag_FW_RULE_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)
0x18001a870  mov     ebx, eax
0x18001a872  test    eax, eax
0x18001a874  jns     short loc_18001A892
0x18001a876  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a87d  cmp     rcx, rsi
0x18001a880  jz      short loc_18001A8A8
0x18001a882  test    byte ptr [rcx+1Ch], 1
0x18001a886  jz      short loc_18001A8A8
0x18001a888  mov     edx, 2Ah ; '*'
0x18001a88d  jmp     loc_18001A7E0
0x18001a892  mov     edi, [rsp+2C0h+var_280]
0x18001a896  mov     rax, [rsp+2C0h+var_278]
0x18001a89b  mov     [rax], edi
0x18001a89d  test    ebx, ebx
0x18001a89f  jns     short loc_18001A8E6
0x18001a8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8a8  lea     rdi, WPP_GLOBAL_Control
0x18001a8af  cmp     rcx, rdi
0x18001a8b2  jz      short loc_18001A8E6
0x18001a8b4  test    byte ptr [rcx+1Ch], 4
0x18001a8b8  jz      short loc_18001A8E6
0x18001a8ba  mov     rax, [rsp+2C0h+var_270]
0x18001a8bf  lea     r9, qword_18003DA20
0x18001a8c6  mov     rcx, [rcx+10h]
0x18001a8ca  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001a8d1  test    rax, rax
0x18001a8d4  mov     dword ptr [rsp+2C0h+lpReserved], ebx
0x18001a8d8  mov     edx, 2Dh ; '-'
0x18001a8dd  cmovnz  r9, rax
0x18001a8e1  call    WPP_SF_Sd
0x18001a8e6  mov     rcx, [rsp+2C0h+hKey]
0x18001a8eb  call    cs:__imp_FwRegCloseKey
0x18001a8f1  mov     eax, ebx
0x18001a8f3  mov     rcx, [rbp+1C0h+var_50]
0x18001a8fa  xor     rcx, rsp; StackCookie
0x18001a8fd  call    __security_check_cookie
0x18001a902  add     rsp, 288h
0x18001a909  pop     r15
0x18001a90b  pop     r14
0x18001a90d  pop     r13
0x18001a90f  pop     r12
0x18001a911  pop     rdi
0x18001a912  pop     rsi
0x18001a913  pop     rbx
0x18001a914  pop     rbp
0x18001a915  retn
0x18001a916  mov     r14d, [rbp+1C0h+arg_30]
0x18001a91d  xor     esi, esi
0x18001a91f  mov     r15d, [rbp+1C0h+arg_28]
0x18001a926  cmp     esi, eax
0x18001a928  jnb     loc_18001A896
0x18001a92e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001a933  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x18001a938  xor     eax, eax
0x18001a93a  lea     r8, [rsp+2C0h+Name]; lpName
0x18001a93f  mov     [rsp+2C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001a944  mov     edx, esi; dwIndex
0x18001a946  mov     [rsp+2C0h+lpcchClass], rax; lpcchClass
0x18001a94b  mov     [rsp+2C0h+lpClass], rax; lpClass
0x18001a950  mov     [rsp+2C0h+lpReserved], rax; lpReserved
0x18001a955  mov     [rsp+2C0h+var_280], eax
0x18001a959  call    cs:__imp_RegEnumKeyExW
0x18001a95f  cmp     eax, 103h
0x18001a964  jz      loc_18001A896
0x18001a96a  test    eax, eax
0x18001a96c  jg      short loc_18001A972
0x18001a96e  mov     ebx, eax
0x18001a970  jmp     short loc_18001A97B
0x18001a972  movzx   ebx, ax
0x18001a975  or      ebx, 80070000h
0x18001a97b  test    ebx, ebx
0x18001a97d  js      short loc_18001A9E8
0x18001a97f  mov     rdx, [rsp+2C0h+hKey]; HKEY
0x18001a984  lea     rax, [rsp+2C0h+var_280]
0x18001a989  mov     dword ptr [rsp+2C0h+lpcchClass], r14d; unsigned int
0x18001a98e  lea     r8, [rsp+2C0h+Name]; unsigned __int16 *
0x18001a993  mov     dword ptr [rsp+2C0h+lpClass], r15d; unsigned int
0x18001a998  mov     r9, r13; struct _tag_FW_BLOB_RULE **
0x18001a99b  mov     rcx, r12; struct _tag_FW_RULE_MANIPULATOR *
0x18001a99e  mov     [rsp+2C0h+lpReserved], rax; unsigned int *
0x18001a9a3  call    ?FwAdvPolicySubSectionLoadRules@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAUHKEY__@@PEBGPEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z; FwAdvPolicySubSectionLoadRules(_tag_FW_RULE_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)
0x18001a9a8  mov     ebx, eax
0x18001a9aa  test    eax, eax
0x18001a9ac  js      short loc_18001A9BD
0x18001a9ae  add     edi, [rsp+2C0h+var_280]
0x18001a9b2  mov     eax, [rsp+2C0h+cSubKeys]
0x18001a9b6  inc     esi
0x18001a9b8  jmp     loc_18001A926
0x18001a9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9c4  lea     rdi, WPP_GLOBAL_Control
0x18001a9cb  cmp     rcx, rdi
0x18001a9ce  jz      loc_18001A8E6
0x18001a9d4  test    byte ptr [rcx+1Ch], 1
0x18001a9d8  jz      loc_18001A8AF
0x18001a9de  mov     edx, 2Ch ; ','
0x18001a9e3  mov     r9d, eax
0x18001a9e6  jmp     short loc_18001AA11
0x18001a9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9ef  lea     rdi, WPP_GLOBAL_Control
0x18001a9f6  cmp     rcx, rdi
0x18001a9f9  jz      loc_18001A8E6
0x18001a9ff  test    byte ptr [rcx+1Ch], 1
0x18001aa03  jz      loc_18001A8AF
0x18001aa09  mov     edx, 2Bh ; '+'
0x18001aa0e  mov     r9d, ebx
0x18001aa11  mov     rcx, [rcx+10h]
0x18001aa15  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001aa1c  call    WPP_SF_d
0x18001aa21  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa28  jmp     loc_18001A8AF
```
