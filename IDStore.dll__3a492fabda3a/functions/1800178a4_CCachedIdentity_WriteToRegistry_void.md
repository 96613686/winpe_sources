# CCachedIdentity::WriteToRegistry(void)

- ea: `0x1800178a4`
- end: `0x180017e25`
- name: `?WriteToRegistry@CCachedIdentity@@QEAAJXZ`
- size: `1409`
- prototype: `__int64 __fastcall(struct _GUID *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008260`

## callees

- `0x18000a680`
- `0x18000dd90`
- `0x1800144b4`
- `0x180014540`
- `0x1800145a0`
- `0x180017674`
- `0x180017760`
- `0x1800178a4`
- `0x180017e2c`
- `0x1800193a8`
- `0x1800194dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001797d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001797d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001798b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001798b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001795c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001795c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017d54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017d54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017b43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017c07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017b43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017c07`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017c9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017c61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017c61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017a43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017a43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a9e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800179d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800179d8`

## string_xrefs

- `0x180017af1`: `IdentityCache`

## pseudocode

```c
__int64 __fastcall CCachedIdentity::WriteToRegistry(struct _GUID *this)
{
  const unsigned __int16 *v1; // rdx
  unsigned __int16 *v3; // rbx
  int UserSid; // edi
  __int64 v5; // rcx
  int v6; // eax
  void *v7; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  int v13; // eax
  bool v14; // cc
  const unsigned __int16 *v15; // rdx
  LSTATUS v16; // eax
  CIdentityProfileHandler *v17; // rcx
  int v18; // edx
  LSTATUS InfoKeyW; // eax
  int v20; // eax
  int v21; // edx
  int v22; // r8d
  const wchar_t *v23; // rax
  int v24; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-11h] BYREF
  PSID Sid; // [rsp+80h] [rbp-9h] BYREF
  LPVOID lpMem[3]; // [rsp+88h] [rbp-1h] BYREF
  int v30; // [rsp+A0h] [rbp+17h]
  int Data; // [rsp+F0h] [rbp+67h] BYREF
  DWORD dwDisposition; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD Type; // [rsp+100h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = *(const unsigned __int16 **)&this[9].Data1;
  lpMem[0] = 0;
  lpMem[1] = 0;
  v30 = 0;
  v3 = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  dwDisposition = 0;
  v24 = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  UserSid = CDynamicString::Assign((CDynamicString *)lpMem, v1);
  if ( UserSid < 0 )
    goto LABEL_7;
  UserSid = CDynamicString::Append((CDynamicString *)lpMem, L"\\");
  if ( UserSid < 0 )
    goto LABEL_7;
  v6 = SimpleCheckMembership(v5, &v24);
  UserSid = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
    {
LABEL_7:
      v7 = lpMem[0];
      goto LABEL_8;
    }
    UserSid = (unsigned __int16)v6;
LABEL_6:
    UserSid |= 0x80070000;
    goto LABEL_7;
  }
  if ( v24 )
  {
    v15 = L"GlobalStore";
    goto LABEL_39;
  }
  StringSid = 0;
  Sid = 0;
  UserSid = GetUserSid(&Sid);
  if ( UserSid )
  {
    v14 = UserSid < 0;
LABEL_36:
    if ( v14 )
      goto LABEL_7;
    UserSid = (unsigned __int16)UserSid;
    goto LABEL_6;
  }
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v10 = -1;
    do
      ++v10;
    while ( StringSid[v10] );
    v11 = (unsigned int)(v10 + 1);
    v12 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v11);
    v3 = v12;
    if ( v12 )
    {
      v13 = StringCchCopyW(v12, v11, StringSid);
      UserSid = v13;
      if ( v13 < 0 )
      {
        if ( (v13 & 0x1FFF0000) == 0x70000 )
        {
          UserSid = (unsigned __int16)v13;
          if ( !(_WORD)v13 )
            UserSid = 1359;
        }
      }
      else
      {
        UserSid = 0;
        v3[(unsigned int)(v11 - 1)] = 0;
      }
    }
    else
    {
      UserSid = 8;
    }
    LocalFree(StringSid);
  }
  else
  {
    UserSid = GetLastError();
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids,
        (unsigned int)UserSid);
    }
  }
  LocalFree(Sid);
  v14 = UserSid <= 0;
  if ( UserSid )
    goto LABEL_36;
  v15 = v3;
LABEL_39:
  UserSid = CDynamicString::Append((CDynamicString *)lpMem, v15);
  if ( UserSid < 0 )
    goto LABEL_7;
  UserSid = CDynamicString::Append((CDynamicString *)lpMem, L"\\");
  if ( UserSid < 0 )
    goto LABEL_7;
  UserSid = CDynamicString::Append((CDynamicString *)lpMem, L"IdentityCache");
  if ( UserSid < 0 )
    goto LABEL_7;
  v7 = lpMem[0];
  v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem[0], 0, 0, 0, 0x2011Fu, 0, &hKey, &dwDisposition);
  if ( v16 )
  {
    if ( v16 > 0 )
      UserSid = (unsigned __int16)v16 | 0x80070000;
    else
      UserSid = v16;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v18 = 10;
LABEL_49:
      WPP_SF_Sd(
        *((_QWORD *)v17 + 2),
        v18,
        (unsigned int)WPP_a5692e5375a637ab30c730d622955dd4_Traceguids,
        (_DWORD)v7,
        v16);
    }
  }
  else
  {
    UserSid = CDynamicString::Append((CDynamicString *)lpMem, L"\\");
    if ( UserSid < 0 )
      goto LABEL_7;
    UserSid = CDynamicString::Append((CDynamicString *)lpMem, *(const unsigned __int16 **)&this[7].Data1);
    if ( UserSid < 0 )
      goto LABEL_7;
    v7 = lpMem[0];
    v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem[0], 0, 0, 0, 0x2011Fu, 0, &phkResult, &dwDisposition);
    if ( v16 )
    {
      if ( v16 > 0 )
        UserSid = (unsigned __int16)v16 | 0x80070000;
      else
        UserSid = v16;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v18 = 11;
        goto LABEL_49;
      }
    }
    else
    {
      if ( dwDisposition == 2 )
      {
        Sid = 0;
        StringSid = 0;
        GetSystemTimeAsFileTime((LPFILETIME)&StringSid);
        InfoKeyW = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, (PFILETIME)&Sid);
        UserSid = InfoKeyW;
        if ( InfoKeyW )
        {
          if ( InfoKeyW > 0 )
            UserSid = (unsigned __int16)InfoKeyW | 0x80070000;
          goto LABEL_8;
        }
        if ( StringSid < (LPWSTR)((char *)Sid + 5000000) )
        {
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a5692e5375a637ab30c730d622955dd4_Traceguids, v7);
          }
          UserSid = 0;
          goto LABEL_8;
        }
      }
      UserSid = CCachedIdentity::WriteToRegistry(this, phkResult);
      if ( UserSid < 0 )
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_a5692e5375a637ab30c730d622955dd4_Traceguids,
            (_DWORD)v7,
            UserSid);
        }
      }
      else
      {
        if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          goto LABEL_10;
        Type = 4;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"Version", 0, &Type, (LPBYTE)&Data, &cbData) )
        {
          v20 = 0;
          if ( Data != -1 )
            v20 = Data + 1;
          Data = v20;
        }
        Type = 4;
        cbData = 4;
        RegSetValueExW(hKey, L"Version", 0, 4u, (const BYTE *)&Data, 4u);
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v23 = L"System";
          if ( !v24 )
            v23 = v3;
          WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, Data, (__int64)v23);
        }
      }
    }
  }
LABEL_8:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
LABEL_10:
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( v3 )
    LocalFree(v3);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x1800178a4  push    rbp
0x1800178a6  push    rbx
0x1800178a7  push    rsi
0x1800178a8  push    rdi
0x1800178a9  push    r12
0x1800178ab  push    r13
0x1800178ad  push    r14
0x1800178af  lea     rbp, [rsp-27h]
0x1800178b4  sub     rsp, 0B0h
0x1800178bb  mov     rdx, [rcx+90h]; unsigned __int16 *
0x1800178c2  xor     r12d, r12d
0x1800178c5  mov     r14, rcx
0x1800178c8  mov     [rbp+57h+lpMem], r12
0x1800178cc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800178d0  mov     [rbp+57h+var_50], r12
0x1800178d4  lea     rcx, [rbp+57h+lpMem]; this
0x1800178d8  mov     [rbp+57h+var_40], r12d
0x1800178dc  mov     ebx, r12d
0x1800178df  mov     [rbp+57h+var_70], rsi
0x1800178e3  mov     [rbp+57h+hKey], rsi
0x1800178e7  mov     [rbp+57h+dwDisposition], r12d
0x1800178eb  mov     [rbp+57h+var_80], r12d
0x1800178ef  mov     [rbp+57h+Data], r12d
0x1800178f3  mov     [rbp+57h+cbData], r12d
0x1800178f7  mov     [rbp+57h+Type], r12d
0x1800178fb  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x180017900  mov     edi, eax
0x180017902  test    eax, eax
0x180017904  js      short loc_180017936
0x180017906  lea     rdx, asc_18001F5AC; "\\"
0x18001790d  lea     rcx, [rbp+57h+lpMem]; this
0x180017911  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017916  mov     edi, eax
0x180017918  test    eax, eax
0x18001791a  js      short loc_180017936
0x18001791c  lea     rdx, [rbp+57h+var_80]; int *
0x180017920  call    ?SimpleCheckMembership@@YAKKPEAH@Z; SimpleCheckMembership(ulong,int *)
0x180017925  mov     edi, eax
0x180017927  test    eax, eax
0x180017929  jz      short loc_1800179A5
0x18001792b  jle     short loc_180017936
0x18001792d  movzx   edi, ax
0x180017930  or      edi, 80070000h
0x180017936  mov     rsi, [rbp+57h+lpMem]
0x18001793a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001793e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017942  jz      short loc_180017952
0x180017944  call    cs:__imp_RegCloseKey
0x18001794a  mov     [rbp+57h+hKey], 0FFFFFFFFFFFFFFFFh
0x180017952  mov     rcx, [rbp+57h+var_70]; hKey
0x180017956  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001795a  jz      short loc_18001796A
0x18001795c  call    cs:__imp_RegCloseKey
0x180017962  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x18001796a  test    rbx, rbx
0x18001796d  jz      short loc_180017978
0x18001796f  mov     rcx, rbx; hMem
0x180017972  call    cs:__imp_LocalFree
0x180017978  test    rsi, rsi
0x18001797b  jz      short loc_180017991
0x18001797d  call    cs:__imp_GetProcessHeap
0x180017983  mov     r8, rsi; lpMem
0x180017986  xor     edx, edx; dwFlags
0x180017988  mov     rcx, rax; hHeap
0x18001798b  call    cs:__imp_HeapFree
0x180017991  mov     eax, edi
0x180017993  add     rsp, 0B0h
0x18001799a  pop     r14
0x18001799c  pop     r13
0x18001799e  pop     r12
0x1800179a0  pop     rdi
0x1800179a1  pop     rsi
0x1800179a2  pop     rbx
0x1800179a3  pop     rbp
0x1800179a4  retn
0x1800179a5  mov     r13d, 4
0x1800179ab  cmp     [rbp+57h+var_80], r12d
0x1800179af  jnz     loc_180017ABD
0x1800179b5  lea     rcx, [rbp+57h+Sid]; void **
0x1800179b9  mov     [rbp+57h+StringSid], r12
0x1800179bd  mov     [rbp+57h+Sid], r12
0x1800179c1  call    ?GetUserSid@@YAKPEAPEAX@Z; GetUserSid(void * *)
0x1800179c6  mov     edi, eax
0x1800179c8  test    eax, eax
0x1800179ca  jnz     loc_180017AAD
0x1800179d0  mov     rcx, [rbp+57h+Sid]; Sid
0x1800179d4  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800179d8  call    cs:__imp_ConvertSidToStringSidW
0x1800179de  test    eax, eax
0x1800179e0  jnz     short loc_180017A24
0x1800179e2  call    cs:__imp_GetLastError
0x1800179e8  mov     edi, eax
0x1800179ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179f1  lea     rax, WPP_GLOBAL_Control
0x1800179f8  cmp     rcx, rax
0x1800179fb  jz      loc_180017A9A
0x180017a01  test    [rcx+1Ch], r13b
0x180017a05  jz      loc_180017A9A
0x180017a0b  mov     rcx, [rcx+10h]
0x180017a0f  lea     edx, [r13+0Ah]
0x180017a13  mov     r9d, edi
0x180017a16  lea     r8, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids
0x180017a1d  call    WPP_SF_d
0x180017a22  jmp     short loc_180017A9A
0x180017a24  mov     rcx, [rbp+57h+StringSid]
0x180017a28  mov     rax, rsi
0x180017a2b  inc     rax
0x180017a2e  cmp     [rcx+rax*2], r12w
0x180017a33  jnz     short loc_180017A2B
0x180017a35  lea     esi, [rax+1]
0x180017a38  mov     ecx, 40h ; '@'; uFlags
0x180017a3d  lea     rdx, [rsi+rsi]; uBytes
0x180017a41  mov     edi, esi
0x180017a43  call    cs:__imp_LocalAlloc
0x180017a49  mov     rbx, rax
0x180017a4c  test    rax, rax
0x180017a4f  jnz     short loc_180017A56
0x180017a51  lea     edi, [rax+8]
0x180017a54  jmp     short loc_180017A90
0x180017a56  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180017a5a  mov     rdx, rdi; unsigned __int64
0x180017a5d  mov     rcx, rbx; unsigned __int16 *
0x180017a60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a65  mov     edi, eax
0x180017a67  test    eax, eax
0x180017a69  js      short loc_180017A78
0x180017a6b  lea     eax, [rsi-1]
0x180017a6e  mov     edi, r12d
0x180017a71  mov     [rbx+rax*2], r12w
0x180017a76  jmp     short loc_180017A90
0x180017a78  and     eax, 1FFF0000h
0x180017a7d  cmp     eax, 70000h
0x180017a82  jnz     short loc_180017A90
0x180017a84  movzx   edi, di
0x180017a87  test    edi, edi
0x180017a89  jnz     short loc_180017A90
0x180017a8b  mov     edi, 54Fh
0x180017a90  mov     rcx, [rbp+57h+StringSid]; hMem
0x180017a94  call    cs:__imp_LocalFree
0x180017a9a  mov     rcx, [rbp+57h+Sid]; hMem
0x180017a9e  call    cs:__imp_LocalFree
0x180017aa4  test    edi, edi
0x180017aa6  jnz     short loc_180017AAF
0x180017aa8  mov     rdx, rbx
0x180017aab  jmp     short loc_180017AC4
0x180017aad  test    edi, edi
0x180017aaf  jle     loc_180017936
0x180017ab5  movzx   edi, di
0x180017ab8  jmp     loc_180017930
0x180017abd  lea     rdx, aGlobalstore; "GlobalStore"
0x180017ac4  lea     rcx, [rbp+57h+lpMem]; this
0x180017ac8  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017acd  mov     edi, eax
0x180017acf  test    eax, eax
0x180017ad1  js      loc_180017936
0x180017ad7  lea     rdx, asc_18001F5AC; "\\"
0x180017ade  lea     rcx, [rbp+57h+lpMem]; this
0x180017ae2  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017ae7  mov     edi, eax
0x180017ae9  test    eax, eax
0x180017aeb  js      loc_180017936
0x180017af1  lea     rdx, aIdentitycache; "IdentityCache"
0x180017af8  lea     rcx, [rbp+57h+lpMem]; this
0x180017afc  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017b01  mov     edi, eax
0x180017b03  test    eax, eax
0x180017b05  js      loc_180017936
0x180017b0b  mov     rsi, [rbp+57h+lpMem]
0x180017b0f  lea     rax, [rbp+57h+dwDisposition]
0x180017b13  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x180017b18  xor     r9d, r9d; lpClass
0x180017b1b  lea     rax, [rbp+57h+hKey]
0x180017b1f  xor     r8d, r8d; Reserved
0x180017b22  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180017b27  mov     rdx, rsi; lpSubKey
0x180017b2a  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180017b2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017b36  mov     [rsp+0E0h+samDesired], 2011Fh; samDesired
0x180017b3e  mov     [rsp+0E0h+dwOptions], r12d; dwOptions
0x180017b43  call    cs:__imp_RegCreateKeyExW
0x180017b49  test    eax, eax
0x180017b4b  jz      short loc_180017B9E
0x180017b4d  jg      short loc_180017B53
0x180017b4f  mov     edi, eax
0x180017b51  jmp     short loc_180017B5C
0x180017b53  movzx   edi, ax
0x180017b56  or      edi, 80070000h
0x180017b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b63  lea     rdx, WPP_GLOBAL_Control
0x180017b6a  cmp     rcx, rdx
0x180017b6d  jz      loc_18001793A
0x180017b73  test    [rcx+1Ch], r13b
0x180017b77  jz      loc_18001793A
0x180017b7d  mov     edx, 0Ah
0x180017b82  mov     rcx, [rcx+10h]
0x180017b86  lea     r8, WPP_a5692e5375a637ab30c730d622955dd4_Traceguids
0x180017b8d  mov     r9, rsi
0x180017b90  mov     [rsp+0E0h+dwOptions], eax
0x180017b94  call    WPP_SF_Sd
0x180017b99  jmp     loc_18001793A
0x180017b9e  lea     rdx, asc_18001F5AC; "\\"
0x180017ba5  lea     rcx, [rbp+57h+lpMem]; this
0x180017ba9  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017bae  mov     edi, eax
0x180017bb0  test    eax, eax
0x180017bb2  js      loc_180017936
0x180017bb8  mov     rdx, [r14+70h]; unsigned __int16 *
0x180017bbc  lea     rcx, [rbp+57h+lpMem]; this
0x180017bc0  call    ?Append@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Append(ushort const *)
0x180017bc5  mov     edi, eax
0x180017bc7  test    eax, eax
0x180017bc9  js      loc_180017936
0x180017bcf  mov     rsi, [rbp+57h+lpMem]
0x180017bd3  lea     rax, [rbp+57h+dwDisposition]
0x180017bd7  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x180017bdc  xor     r9d, r9d; lpClass
0x180017bdf  lea     rax, [rbp+57h+var_70]
0x180017be3  xor     r8d, r8d; Reserved
0x180017be6  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180017beb  mov     rdx, rsi; lpSubKey
0x180017bee  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180017bf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017bfa  mov     [rsp+0E0h+samDesired], 2011Fh; samDesired
0x180017c02  mov     [rsp+0E0h+dwOptions], r12d; dwOptions
0x180017c07  call    cs:__imp_RegCreateKeyExW
0x180017c0d  test    eax, eax
0x180017c0f  jz      short loc_180017C4B
0x180017c11  jg      short loc_180017C17
0x180017c13  mov     edi, eax
0x180017c15  jmp     short loc_180017C20
0x180017c17  movzx   edi, ax
0x180017c1a  or      edi, 80070000h
0x180017c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c27  lea     rdx, WPP_GLOBAL_Control
0x180017c2e  cmp     rcx, rdx
0x180017c31  jz      loc_18001793A
0x180017c37  test    [rcx+1Ch], r13b
0x180017c3b  jz      loc_18001793A
0x180017c41  mov     edx, 0Bh
0x180017c46  jmp     loc_180017B82
0x180017c4b  cmp     [rbp+57h+dwDisposition], 2
0x180017c4f  jnz     loc_180017D08
0x180017c55  lea     rcx, [rbp+57h+StringSid]; lpSystemTimeAsFileTime
0x180017c59  mov     [rbp+57h+Sid], r12
0x180017c5d  mov     [rbp+57h+StringSid], r12
0x180017c61  call    cs:__imp_GetSystemTimeAsFileTime
0x180017c67  mov     rcx, [rbp+57h+var_70]; hKey
0x180017c6b  lea     rax, [rbp+57h+Sid]
0x180017c6f  mov     [rsp+0E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180017c74  xor     r9d, r9d; lpReserved
0x180017c77  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180017c7c  xor     r8d, r8d; lpcchClass
0x180017c7f  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180017c84  xor     edx, edx; lpClass
0x180017c86  mov     [rsp+0E0h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x180017c8b  mov     [rsp+0E0h+phkResult], r12; lpcValues
0x180017c90  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x180017c95  mov     qword ptr [rsp+0E0h+samDesired], r12; lpcbMaxSubKeyLen
0x180017c9a  mov     qword ptr [rsp+0E0h+dwOptions], r12; lpcSubKeys
0x180017c9f  call    cs:__imp_RegQueryInfoKeyW
0x180017ca5  mov     edi, eax
0x180017ca7  test    eax, eax
0x180017ca9  jz      short loc_180017CBF
0x180017cab  jle     loc_18001793A
0x180017cb1  movzx   edi, ax
0x180017cb4  or      edi, 80070000h
0x180017cba  jmp     loc_18001793A
0x180017cbf  mov     rax, [rbp+57h+Sid]
0x180017cc3  add     rax, 4C4B40h
0x180017cc9  cmp     [rbp+57h+StringSid], rax
0x180017ccd  jnb     short loc_180017D08
0x180017ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cd6  lea     rax, WPP_GLOBAL_Control
0x180017cdd  cmp     rcx, rax
0x180017ce0  jz      short loc_180017D00
0x180017ce2  test    byte ptr [rcx+1Ch], 8
0x180017ce6  jz      short loc_180017D00
0x180017ce8  mov     rcx, [rcx+10h]
0x180017cec  lea     r8, WPP_a5692e5375a637ab30c730d622955dd4_Traceguids
0x180017cf3  mov     edx, 0Ch
0x180017cf8  mov     r9, rsi
0x180017cfb  call    WPP_SF_S
0x180017d00  mov     edi, r12d
0x180017d03  jmp     loc_18001793A
0x180017d08  mov     rdx, [rbp+57h+var_70]; HKEY
0x180017d0c  mov     rcx, r14; this
0x180017d0f  call    ?WriteToRegistry@CCachedIdentity@@QEAAJPEAUHKEY__@@@Z; CCachedIdentity::WriteToRegistry(HKEY__ *)
0x180017d14  mov     edi, eax
0x180017d16  test    eax, eax
0x180017d18  js      loc_180017DE3
0x180017d1e  mov     rcx, [rbp+57h+hKey]; hKey
0x180017d22  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017d26  jz      loc_180017952
0x180017d2c  lea     rax, [rbp+57h+cbData]
0x180017d30  mov     [rbp+57h+Type], r13d
0x180017d34  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x180017d39  lea     r9, [rbp+57h+Type]; lpType
0x180017d3d  lea     rax, [rbp+57h+Data]
0x180017d41  mov     [rbp+57h+cbData], r13d
0x180017d45  xor     r8d, r8d; lpReserved
  ... truncated ...
```
