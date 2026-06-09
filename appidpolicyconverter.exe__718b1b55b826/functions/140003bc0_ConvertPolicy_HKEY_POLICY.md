# ConvertPolicy(HKEY__ *,_POLICY *)

- ea: `0x140003bc0`
- end: `0x140004143`
- name: `?ConvertPolicy@@YAKPEAUHKEY__@@PEAU_POLICY@@@Z`
- size: `1411`
- prototype: `__int64 __fastcall(HKEY, struct _POLICY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x14000458c`

## callees

- `0x140002938`
- `0x140002a64`
- `0x140003bc0`
- `0x14000414c`
- `0x140007150`
- `0x1400071d8`
- `0x140007240`
- `0x1400073a8`
- `0x140007468`
- `0x14000753c`
- `0x140007c18`
- `0x140008d30`
- `0x140008ef4`
- `0x140013acf`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003cbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003cbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003c02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003c02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003fef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004061`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400040d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003fef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004061`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400040d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004123`

## string_xrefs

- `0x140003f76`: `ServiceEnforcementMode`
- `0x140003fac`: `ServiceEnforcementMode`

## pseudocode

```c
__int64 __fastcall ConvertPolicy(HKEY a1, struct _POLICY *a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // r8
  _QWORD *v6; // rcx
  int v7; // edx
  void *v8; // rax
  DWORD i; // r15d
  unsigned int SubKeyName; // eax
  int v11; // r8d
  unsigned __int16 *v12; // rbx
  unsigned __int64 v13; // rax
  _DWORD *v14; // r15
  LSTATUS v15; // eax
  int v16; // r8d
  _QWORD *v17; // rcx
  int v18; // edx
  const WCHAR *v19; // rax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int16 *v26; // [rsp+68h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C0h] [rbp+50h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+58h] BYREF

  hKey = 0;
  v3 = *(const WCHAR **)a2;
  v26 = 0;
  Type = 0;
  cbData = 0;
  v4 = RegOpenKeyExW(a1, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_85;
    v7 = 27;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v5, *(_QWORD *)a2);
  cSubKeys = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_85;
    v7 = 29;
LABEL_5:
    WPP_SF_dS(v6[2], v7, v5, v4, *(_QWORD *)a2);
    goto LABEL_85;
  }
  if ( cSubKeys > 0xFFFD )
    goto LABEL_14;
  if ( cSubKeys )
  {
    v8 = (void *)AiAlloc(40LL * (cSubKeys + 2));
    *((_QWORD *)a2 + 5) = v8;
    if ( !v8 )
    {
      v4 = 8;
      goto LABEL_85;
    }
    memset_0(v8, 0, 40LL * (cSubKeys + 2));
    for ( i = 0; ; ++i )
    {
      if ( v4 )
        goto LABEL_85;
      SubKeyName = GetSubKeyName(hKey, i, &v26);
      v4 = SubKeyName;
      if ( SubKeyName == 259 )
        break;
      if ( SubKeyName )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v11, SubKeyName, *(_QWORD *)a2, i);
        goto LABEL_85;
      }
      v12 = v26;
      v13 = -1;
      do
        ++v13;
      while ( v26[v13] );
      if ( v13 > 0x7FFF )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v11, *(_QWORD *)a2, (__int64)v26);
        AiFree(v12);
LABEL_14:
        v4 = 87;
        goto LABEL_85;
      }
      if ( i >= cSubKeys )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v11, *(_QWORD *)a2, *((_DWORD *)a2 + 9) - 1);
        AiFree(v12);
        v4 = 1018;
        goto LABEL_85;
      }
      *(_QWORD *)(*((_QWORD *)a2 + 5) + 40LL * i) = v26;
      v4 = ConvertRule(hKey, (LPCWSTR *)(*((_QWORD *)a2 + 5) + 40LL * i), (unsigned int *)a2 + 8);
    }
    *((_DWORD *)a2 + 9) = i;
    if ( i )
    {
      *((_DWORD *)a2 + 9) = i + 2;
      v4 = AddLowboxAceToPolicy((struct _POLICY_RULE *)(*((_QWORD *)a2 + 5) + 40LL * i));
      if ( v4 )
        goto LABEL_85;
      v4 = AddLpacAceToPolicy((struct _POLICY_RULE *)(*((_QWORD *)a2 + 5)
                                                    + 40LL * (unsigned int)(*((_DWORD *)a2 + 9) - 1)));
      if ( v4 )
        goto LABEL_85;
    }
    v14 = (_DWORD *)((char *)a2 + 8);
    cbData = 4;
    v15 = RegQueryValueExW(hKey, L"EnforcementMode", 0, &Type, (LPBYTE)a2 + 8, &cbData);
    v4 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
          goto LABEL_85;
        v18 = 33;
        v19 = L"EnforcementMode";
        goto LABEL_46;
      }
    }
    else if ( Type == 4 && cbData == 4 )
    {
LABEL_50:
      if ( !*v14 )
        *((_DWORD *)a2 + 8) |= 0x19u;
      cbData = 4;
      v20 = RegQueryValueExW(hKey, L"ServiceEnforcementMode", 0, &Type, (LPBYTE)a2 + 12, &cbData);
      v4 = v20;
      if ( v20 )
      {
        if ( v20 != 2 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
          {
            goto LABEL_85;
          }
          v18 = 34;
          v19 = L"ServiceEnforcementMode";
          goto LABEL_46;
        }
      }
      else if ( Type == 4 && cbData == 4 )
      {
LABEL_60:
        cbData = 4;
        v21 = RegQueryValueExW(hKey, L"AllowWindows", 0, &Type, (LPBYTE)a2 + 16, &cbData);
        v4 = v21;
        if ( v21 )
        {
          if ( v21 != 2 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
            {
              goto LABEL_85;
            }
            v18 = 35;
            v19 = L"AllowWindows";
            goto LABEL_46;
          }
        }
        else if ( Type == 4 && cbData == 4 )
        {
LABEL_68:
          cbData = 4;
          v22 = RegQueryValueExW(hKey, L"CurrentOriginDataId", 0, &Type, (LPBYTE)a2 + 20, &cbData);
          v4 = v22;
          if ( v22 )
          {
            if ( v22 != 2 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
              {
                goto LABEL_85;
              }
              v18 = 36;
              v19 = L"CurrentOriginDataId";
              goto LABEL_46;
            }
          }
          else if ( Type == 4 && cbData == 4 )
          {
LABEL_76:
            cbData = 4;
            v23 = RegQueryValueExW(hKey, L"TrustedOriginDataId", 0, &Type, (LPBYTE)a2 + 24, &cbData);
            v4 = v23;
            if ( v23 )
            {
              if ( v23 != 2 )
              {
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
                {
                  goto LABEL_85;
                }
                v18 = 37;
                v19 = L"TrustedOriginDataId";
LABEL_46:
                WPP_SF_dSS(v17[2], v18, v16, v4, *(_QWORD *)a2, (__int64)v19);
                goto LABEL_85;
              }
              v4 = 0;
            }
            else if ( Type == 4 && cbData == 4 )
            {
              goto LABEL_85;
            }
            *((_DWORD *)a2 + 6) = 0;
            goto LABEL_85;
          }
          *((_DWORD *)a2 + 5) = 0;
          goto LABEL_76;
        }
        *((_DWORD *)a2 + 4) = 0;
        goto LABEL_68;
      }
      *((_DWORD *)a2 + 3) = 0;
      goto LABEL_60;
    }
    *v14 = 1;
    goto LABEL_50;
  }
LABEL_85:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140003bc0  mov     [rsp-38h+arg_0], rbx
0x140003bc5  push    rbp
0x140003bc6  push    rsi
0x140003bc7  push    rdi
0x140003bc8  push    r12
0x140003bca  push    r13
0x140003bcc  push    r14
0x140003bce  push    r15
0x140003bd0  mov     rbp, rsp
0x140003bd3  sub     rsp, 70h
0x140003bd7  xor     r12d, r12d
0x140003bda  lea     rax, [rbp+hKey]
0x140003bde  mov     rdi, rdx
0x140003be1  mov     [rbp+hKey], r12
0x140003be5  mov     rdx, [rdx]; lpSubKey
0x140003be8  mov     r9d, 20019h; samDesired
0x140003bee  xor     r8d, r8d; ulOptions
0x140003bf1  mov     [rbp+var_8], r12
0x140003bf5  mov     [rbp+Type], r12d
0x140003bf9  mov     [rbp+cbData], r12d
0x140003bfd  mov     [rsp+70h+phkResult], rax; phkResult
0x140003c02  call    cs:__imp_RegOpenKeyExW
0x140003c08  mov     ebx, eax
0x140003c0a  test    eax, eax
0x140003c0c  jz      short loc_140003C51
0x140003c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c15  lea     r14, WPP_GLOBAL_Control
0x140003c1c  cmp     rcx, r14
0x140003c1f  jz      loc_14000411A
0x140003c25  mov     esi, 800h
0x140003c2a  test    [rcx+1Ch], esi
0x140003c2d  jz      loc_14000411A
0x140003c33  lea     edx, [r12+1Bh]
0x140003c38  mov     rax, [rdi]
0x140003c3b  mov     r9d, ebx
0x140003c3e  mov     rcx, [rcx+10h]
0x140003c42  mov     [rsp+70h+phkResult], rax
0x140003c47  call    WPP_SF_dS
0x140003c4c  jmp     loc_14000411A
0x140003c51  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c58  lea     r14, WPP_GLOBAL_Control
0x140003c5f  mov     esi, 800h
0x140003c64  cmp     rcx, r14
0x140003c67  jz      short loc_140003C7F
0x140003c69  test    [rcx+1Ch], esi
0x140003c6c  jz      short loc_140003C7F
0x140003c6e  mov     r9, [rdi]
0x140003c71  mov     edx, 1Ch
0x140003c76  mov     rcx, [rcx+10h]
0x140003c7a  call    WPP_SF_S
0x140003c7f  mov     rcx, [rbp+hKey]; hKey
0x140003c83  lea     rax, [rbp+cSubKeys]
0x140003c87  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x140003c8c  xor     r9d, r9d; lpReserved
0x140003c8f  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x140003c94  xor     r8d, r8d; lpcchClass
0x140003c97  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x140003c9c  xor     edx, edx; lpClass
0x140003c9e  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x140003ca3  mov     [rsp+70h+lpcValues], r12; lpcValues
0x140003ca8  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x140003cad  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x140003cb2  mov     [rsp+70h+phkResult], rax; lpcSubKeys
0x140003cb7  mov     [rbp+cSubKeys], r12d
0x140003cbb  call    cs:__imp_RegQueryInfoKeyW
0x140003cc1  mov     ebx, eax
0x140003cc3  test    eax, eax
0x140003cc5  jz      short loc_140003CEA
0x140003cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cce  cmp     rcx, r14
0x140003cd1  jz      loc_14000411A
0x140003cd7  test    [rcx+1Ch], esi
0x140003cda  jz      loc_14000411A
0x140003ce0  mov     edx, 1Dh
0x140003ce5  jmp     loc_140003C38
0x140003cea  mov     eax, [rbp+cSubKeys]
0x140003ced  cmp     eax, 0FFFDh
0x140003cf2  jbe     short loc_140003CFE
0x140003cf4  mov     ebx, 57h ; 'W'
0x140003cf9  jmp     loc_14000411A
0x140003cfe  test    eax, eax
0x140003d00  jz      loc_14000411A
0x140003d06  add     eax, 2
0x140003d09  lea     rcx, [rax+rax*4]
0x140003d0d  shl     rcx, 3
0x140003d11  call    AiAlloc
0x140003d16  mov     [rdi+28h], rax
0x140003d1a  mov     r9, rax
0x140003d1d  test    rax, rax
0x140003d20  jnz     short loc_140003D2A
0x140003d22  lea     ebx, [rax+8]
0x140003d25  jmp     loc_14000411A
0x140003d2a  mov     eax, [rbp+cSubKeys]
0x140003d2d  xor     edx, edx; Val
0x140003d2f  add     eax, 2
0x140003d32  mov     rcx, r9; void *
0x140003d35  lea     r8, [rax+rax*4]
0x140003d39  shl     r8, 3; Size
0x140003d3d  call    memset_0
0x140003d42  mov     r15d, r12d
0x140003d45  test    ebx, ebx
0x140003d47  jnz     loc_14000411A
0x140003d4d  mov     rcx, [rbp+hKey]; hKey
0x140003d51  lea     r8, [rbp+var_8]; unsigned __int16 **
0x140003d55  mov     edx, r15d; dwIndex
0x140003d58  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x140003d5d  mov     ebx, eax
0x140003d5f  cmp     eax, 103h
0x140003d64  jz      loc_140003E6A
0x140003d6a  test    eax, eax
0x140003d6c  jnz     loc_140003E2E
0x140003d72  mov     rbx, [rbp+var_8]
0x140003d76  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003d7a  inc     rax
0x140003d7d  cmp     [rbx+rax*2], r12w
0x140003d82  jnz     short loc_140003D7A
0x140003d84  cmp     rax, 7FFFh
0x140003d8a  ja      short loc_140003DFA
0x140003d8c  cmp     r15d, [rbp+cSubKeys]
0x140003d90  jnb     short loc_140003DBD
0x140003d92  mov     eax, r15d
0x140003d95  lea     r8, [rdi+20h]; unsigned int *
0x140003d99  lea     rcx, [rax+rax*4]
0x140003d9d  mov     rax, [rdi+28h]
0x140003da1  mov     [rax+rcx*8], rbx
0x140003da5  mov     rax, [rdi+28h]
0x140003da9  lea     rdx, [rax+rcx*8]; struct _POLICY_RULE *
0x140003dad  mov     rcx, [rbp+hKey]; HKEY
0x140003db1  call    ?ConvertRule@@YAKPEAUHKEY__@@PEAU_POLICY_RULE@@PEAK@Z; ConvertRule(HKEY__ *,_POLICY_RULE *,ulong *)
0x140003db6  mov     ebx, eax
0x140003db8  inc     r15d
0x140003dbb  jmp     short loc_140003D45
0x140003dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dc4  cmp     rcx, r14
0x140003dc7  jz      short loc_140003DE8
0x140003dc9  test    [rcx+1Ch], esi
0x140003dcc  jz      short loc_140003DE8
0x140003dce  mov     eax, [rdi+24h]
0x140003dd1  mov     edx, 20h ; ' '
0x140003dd6  mov     r9, [rdi]
0x140003dd9  dec     eax
0x140003ddb  mov     rcx, [rcx+10h]
0x140003ddf  mov     dword ptr [rsp+70h+phkResult], eax
0x140003de3  call    WPP_SF_Sd
0x140003de8  mov     rcx, rbx
0x140003deb  call    AiFree
0x140003df0  mov     ebx, 3FAh
0x140003df5  jmp     loc_14000411A
0x140003dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e01  cmp     rcx, r14
0x140003e04  jz      short loc_140003E21
0x140003e06  test    [rcx+1Ch], esi
0x140003e09  jz      short loc_140003E21
0x140003e0b  mov     r9, [rdi]
0x140003e0e  mov     edx, 1Fh
0x140003e13  mov     rcx, [rcx+10h]
0x140003e17  mov     [rsp+70h+phkResult], rbx
0x140003e1c  call    WPP_SF_SS
0x140003e21  mov     rcx, rbx
0x140003e24  call    AiFree
0x140003e29  jmp     loc_140003CF4
0x140003e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e35  cmp     rcx, r14
0x140003e38  jz      loc_14000411A
0x140003e3e  test    [rcx+1Ch], esi
0x140003e41  jz      loc_14000411A
0x140003e47  mov     rax, [rdi]
0x140003e4a  mov     edx, 1Eh
0x140003e4f  mov     rcx, [rcx+10h]
0x140003e53  mov     r9d, ebx
0x140003e56  mov     dword ptr [rsp+70h+lpcbMaxSubKeyLen], r15d
0x140003e5b  mov     [rsp+70h+phkResult], rax
0x140003e60  call    WPP_SF_dSd
0x140003e65  jmp     loc_14000411A
0x140003e6a  mov     [rdi+24h], r15d
0x140003e6e  test    r15d, r15d
0x140003e71  jz      short loc_140003EB8
0x140003e73  lea     eax, [r15+2]
0x140003e77  mov     [rdi+24h], eax
0x140003e7a  mov     eax, r15d
0x140003e7d  lea     rcx, [rax+rax*4]
0x140003e81  mov     rax, [rdi+28h]
0x140003e85  lea     rcx, [rax+rcx*8]; struct _POLICY_RULE *
0x140003e89  call    ?AddLowboxAceToPolicy@@YAKPEAU_POLICY_RULE@@@Z; AddLowboxAceToPolicy(_POLICY_RULE *)
0x140003e8e  mov     ebx, eax
0x140003e90  test    eax, eax
0x140003e92  jnz     loc_14000411A
0x140003e98  mov     eax, [rdi+24h]
0x140003e9b  dec     eax
0x140003e9d  lea     rcx, [rax+rax*4]
0x140003ea1  mov     rax, [rdi+28h]
0x140003ea5  lea     rcx, [rax+rcx*8]; struct _POLICY_RULE *
0x140003ea9  call    ?AddLpacAceToPolicy@@YAKPEAU_POLICY_RULE@@@Z; AddLpacAceToPolicy(_POLICY_RULE *)
0x140003eae  mov     ebx, eax
0x140003eb0  test    eax, eax
0x140003eb2  jnz     loc_14000411A
0x140003eb8  mov     rcx, [rbp+hKey]; hKey
0x140003ebc  lea     rax, [rbp+cbData]
0x140003ec0  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbData
0x140003ec5  lea     r15, [rdi+8]
0x140003ec9  mov     r13d, 4
0x140003ecf  mov     [rsp+70h+phkResult], r15; lpData
0x140003ed4  lea     r9, [rbp+Type]; lpType
0x140003ed8  mov     [rbp+cbData], r13d
0x140003edc  xor     r8d, r8d; lpReserved
0x140003edf  lea     rdx, aEnforcementmod; "EnforcementMode"
0x140003ee6  call    cs:__imp_RegQueryValueExW
0x140003eec  mov     ebx, eax
0x140003eee  test    eax, eax
0x140003ef0  jz      short loc_140003F39
0x140003ef2  cmp     eax, 2
0x140003ef5  jz      short loc_140003F45
0x140003ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003efe  cmp     rcx, r14
0x140003f01  jz      loc_14000411A
0x140003f07  test    [rcx+1Ch], esi
0x140003f0a  jz      loc_14000411A
0x140003f10  lea     edx, [r13+1Dh]
0x140003f14  lea     rax, aEnforcementmod; "EnforcementMode"
0x140003f1b  mov     rcx, [rcx+10h]
0x140003f1f  mov     r9d, ebx
0x140003f22  mov     [rsp+70h+lpcbMaxSubKeyLen], rax
0x140003f27  mov     rax, [rdi]
0x140003f2a  mov     [rsp+70h+phkResult], rax
0x140003f2f  call    WPP_SF_dSS
0x140003f34  jmp     loc_14000411A
0x140003f39  cmp     [rbp+Type], r13d
0x140003f3d  jnz     short loc_140003F45
0x140003f3f  cmp     [rbp+cbData], r13d
0x140003f43  jz      short loc_140003F4C
0x140003f45  mov     dword ptr [r15], 1
0x140003f4c  cmp     [r15], r12d
0x140003f4f  jnz     short loc_140003F55
0x140003f51  or      dword ptr [rdi+20h], 19h
0x140003f55  mov     rcx, [rbp+hKey]; hKey
0x140003f59  lea     rax, [rbp+cbData]
0x140003f5d  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbData
0x140003f62  lea     r15, [rdi+0Ch]
0x140003f66  lea     r9, [rbp+Type]; lpType
0x140003f6a  mov     [rsp+70h+phkResult], r15; lpData
0x140003f6f  xor     r8d, r8d; lpReserved
0x140003f72  mov     [rbp+cbData], r13d
0x140003f76  lea     rdx, aServiceenforce; "ServiceEnforcementMode"
0x140003f7d  call    cs:__imp_RegQueryValueExW
0x140003f83  mov     ebx, eax
0x140003f85  test    eax, eax
0x140003f87  jz      short loc_140003FB8
0x140003f89  cmp     eax, 2
0x140003f8c  jz      short loc_140003FC4
0x140003f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f95  cmp     rcx, r14
0x140003f98  jz      loc_14000411A
0x140003f9e  test    [rcx+1Ch], esi
0x140003fa1  jz      loc_14000411A
0x140003fa7  mov     edx, 22h ; '"'
0x140003fac  lea     rax, aServiceenforce; "ServiceEnforcementMode"
0x140003fb3  jmp     loc_140003F1B
0x140003fb8  cmp     [rbp+Type], r13d
0x140003fbc  jnz     short loc_140003FC4
0x140003fbe  cmp     [rbp+cbData], r13d
0x140003fc2  jz      short loc_140003FC7
0x140003fc4  mov     [r15], r12d
0x140003fc7  mov     rcx, [rbp+hKey]; hKey
0x140003fcb  lea     rax, [rbp+cbData]
0x140003fcf  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbData
0x140003fd4  lea     r15, [rdi+10h]
0x140003fd8  lea     r9, [rbp+Type]; lpType
0x140003fdc  mov     [rsp+70h+phkResult], r15; lpData
0x140003fe1  xor     r8d, r8d; lpReserved
0x140003fe4  mov     [rbp+cbData], r13d
0x140003fe8  lea     rdx, aAllowwindows; "AllowWindows"
0x140003fef  call    cs:__imp_RegQueryValueExW
0x140003ff5  mov     ebx, eax
0x140003ff7  test    eax, eax
0x140003ff9  jz      short loc_14000402A
0x140003ffb  cmp     eax, 2
0x140003ffe  jz      short loc_140004036
0x140004000  mov     rcx, cs:WPP_GLOBAL_Control
0x140004007  cmp     rcx, r14
0x14000400a  jz      loc_14000411A
0x140004010  test    [rcx+1Ch], esi
0x140004013  jz      loc_14000411A
0x140004019  mov     edx, 23h ; '#'
0x14000401e  lea     rax, aAllowwindows; "AllowWindows"
0x140004025  jmp     loc_140003F1B
0x14000402a  cmp     [rbp+Type], r13d
0x14000402e  jnz     short loc_140004036
0x140004030  cmp     [rbp+cbData], r13d
0x140004034  jz      short loc_140004039
0x140004036  mov     [r15], r12d
0x140004039  mov     rcx, [rbp+hKey]; hKey
0x14000403d  lea     rax, [rbp+cbData]
0x140004041  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbData
0x140004046  lea     r15, [rdi+14h]
0x14000404a  lea     r9, [rbp+Type]; lpType
0x14000404e  mov     [rsp+70h+phkResult], r15; lpData
0x140004053  xor     r8d, r8d; lpReserved
0x140004056  mov     [rbp+cbData], r13d
0x14000405a  lea     rdx, aCurrentorigind; "CurrentOriginDataId"
0x140004061  call    cs:__imp_RegQueryValueExW
  ... truncated ...
```
