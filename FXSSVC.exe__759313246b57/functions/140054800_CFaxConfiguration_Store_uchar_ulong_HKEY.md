# CFaxConfiguration::Store(uchar *,ulong,HKEY__ *)

- ea: `0x140054800`
- end: `0x140054c53`
- name: `?Store@CFaxConfiguration@@AEBAKPEAEKPEAUHKEY__@@@Z`
- size: `1107`
- prototype: `unsigned int(CFaxConfiguration *__hidden this, unsigned __int8 *, unsigned int, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140054728`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140054800`
- `0x140054d90`
- `0x14006998c`
- `0x14006a478`
- `0x140074004`
- `0x140075070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400548a3`
- `KERNEL32!GetLastError` at `0x14005495a`
- `KERNEL32!GetLastError` at `0x1400549b4`
- `KERNEL32!GetLastError` at `0x140054a0e`
- `KERNEL32!GetLastError` at `0x140054a68`
- `KERNEL32!GetLastError` at `0x140054ac2`
- `KERNEL32!GetLastError` at `0x140054bac`
- `KERNEL32!GetLastError` at `0x140054bf7`
- `KERNEL32!GetLastError` at `0x1400548a3`
- `KERNEL32!GetLastError` at `0x14005495a`
- `KERNEL32!GetLastError` at `0x1400549b4`
- `KERNEL32!GetLastError` at `0x140054a0e`
- `KERNEL32!GetLastError` at `0x140054a68`
- `KERNEL32!GetLastError` at `0x140054ac2`
- `KERNEL32!GetLastError` at `0x140054bac`
- `KERNEL32!GetLastError` at `0x140054bf7`

## string_xrefs

- `0x140054b99`: `AutoCreateAccountOnConnect`
- `0x140054bd7`: `AutoCreateAccountOnConnect`
- `0x140054be4`: `IncomingFaxesArePublic`
- `0x140054c22`: `IncomingFaxesArePublic`

## pseudocode

```c
__int64 __fastcall CFaxConfiguration::Store(CFaxConfiguration *this, unsigned __int8 *a2, unsigned int a3, HKEY a4)
{
  void *v7; // rbp
  CMapDeviceId *v8; // rcx
  unsigned int v9; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v11; // rcx
  int v12; // edx
  const WCHAR *v13; // r9
  const WCHAR *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // r9
  CFaxConfiguration *v17; // rcx
  unsigned int v18; // eax
  _DWORD v20[26]; // [rsp+30h] [rbp-68h] BYREF

  v7 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v8 + 2), 30, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, a3);
    v9 = 668;
    goto LABEL_65;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"UseArchive", *((_DWORD *)a2 + 1)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 20;
    v13 = L"UseArchive";
    goto LABEL_64;
  }
  v14 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( v14 )
  {
    v15 = ContractEnvironmentString(v14);
    v7 = (void *)v15;
    if ( !v15 )
    {
      v9 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
      }
      goto LABEL_65;
    }
    v16 = (const BYTE *)v15;
  }
  else
  {
    v16 = (const BYTE *)&Class;
  }
  if ( !(unsigned int)SetRegistryStringValue(a4, 1u, L"ArchiveFolder", v16) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 22;
    v13 = L"ArchiveFolder";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"SizeQuotaWarn", *((_DWORD *)a2 + 4)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 23;
    v13 = L"SizeQuotaWarn";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"HighWatermark", *((_DWORD *)a2 + 5)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 24;
    v13 = L"HighWatermark";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"LowWatermark", *((_DWORD *)a2 + 6)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 25;
    v13 = L"LowWatermark";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"ArchiveAgeLimit", *((_DWORD *)a2 + 7)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 26;
    v13 = L"ArchiveAgeLimit";
    goto LABEL_64;
  }
  v20[1] = *((_DWORD *)a2 + 17);
  v20[2] = *((_DWORD *)a2 + 13);
  v20[3] = *((_DWORD *)a2 + 11);
  v20[4] = *((_DWORD *)a2 + 12);
  v20[5] = *((_DWORD *)a2 + 14);
  v20[6] = *((_DWORD *)a2 + 15);
  v20[7] = *((_DWORD *)a2 + 10);
  v20[8] = *((_DWORD *)a2 + 16);
  v20[0] = 36;
  v18 = CFaxConfiguration::StoreOutboxSettings(v17, a4, (struct _FAX_OUTBOX_CONFIG *const)v20);
  v9 = v18;
  if ( !v18 )
  {
    if ( (unsigned int)SetRegistryDword(a4, L"AutoCreateAccountOnConnect", *((_DWORD *)a2 + 19)) )
    {
      if ( (unsigned int)SetRegistryDword(a4, L"IncomingFaxesArePublic", *((_DWORD *)a2 + 20)) )
        goto LABEL_65;
      LastError = GetLastError();
      v9 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v12 = 29;
      v13 = L"IncomingFaxesArePublic";
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v12 = 28;
      v13 = L"AutoCreateAccountOnConnect";
    }
LABEL_64:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids,
      (_DWORD)v13,
      LastError);
    goto LABEL_65;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, v18);
  }
LABEL_65:
  pMemFree(v7);
  return v9;
}

```

## disassembly

```asm
0x140054800  push    rbx
0x140054802  push    rbp
0x140054803  push    rsi
0x140054804  push    rdi
0x140054805  push    r12
0x140054807  push    r14
0x140054809  push    r15
0x14005480b  sub     rsp, 60h
0x14005480f  mov     rsi, r9
0x140054812  mov     ebx, r8d
0x140054815  mov     rdi, rdx
0x140054818  xor     ebp, ebp
0x14005481a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054821  lea     r15, WPP_GLOBAL_Control
0x140054828  lea     r12, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x14005482f  mov     r14b, 4
0x140054832  cmp     rcx, r15
0x140054835  jz      short loc_140054859
0x140054837  test    [rcx+1Ch], r14b
0x14005483b  jz      short loc_140054859
0x14005483d  cmp     byte ptr [rcx+19h], 5
0x140054841  jb      short loc_140054859
0x140054843  mov     rcx, [rcx+10h]
0x140054847  lea     edx, [rbp+13h]
0x14005484a  mov     r8, r12
0x14005484d  call    WPP_SF_
0x140054852  mov     rcx, cs:WPP_GLOBAL_Control
0x140054859  test    ebx, ebx
0x14005485b  jz      short loc_14005488C
0x14005485d  cmp     rcx, r15
0x140054860  jz      short loc_140054882
0x140054862  test    [rcx+1Ch], r14b
0x140054866  jz      short loc_140054882
0x140054868  cmp     byte ptr [rcx+19h], 2
0x14005486c  jb      short loc_140054882
0x14005486e  mov     rcx, [rcx+10h]
0x140054872  mov     edx, 1Eh
0x140054877  mov     r9d, ebx
0x14005487a  mov     r8, r12
0x14005487d  call    WPP_SF_d
0x140054882  mov     ebx, 29Ch
0x140054887  jmp     loc_140054C39
0x14005488c  mov     r8d, [rdi+4]
0x140054890  lea     rdx, aUsearchive; "UseArchive"
0x140054897  mov     rcx, rsi
0x14005489a  call    SetRegistryDword
0x14005489f  test    eax, eax
0x1400548a1  jnz     short loc_1400548E6
0x1400548a3  call    cs:__imp_GetLastError
0x1400548aa  nop     dword ptr [rax+rax+00h]
0x1400548af  mov     ebx, eax
0x1400548b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548b8  cmp     rcx, r15
0x1400548bb  jz      loc_140054C39
0x1400548c1  test    [rcx+1Ch], r14b
0x1400548c5  jz      loc_140054C39
0x1400548cb  cmp     byte ptr [rcx+19h], 2
0x1400548cf  jb      loc_140054C39
0x1400548d5  mov     edx, 14h
0x1400548da  lea     r9, aUsearchive; "UseArchive"
0x1400548e1  jmp     loc_140054C29
0x1400548e6  mov     rcx, [rdi+8]; lpString2
0x1400548ea  test    rcx, rcx
0x1400548ed  jz      short loc_14005493B
0x1400548ef  call    ContractEnvironmentString
0x1400548f4  mov     rbp, rax
0x1400548f7  test    rax, rax
0x1400548fa  jnz     short loc_140054936
0x1400548fc  xor     ebx, ebx
0x1400548fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140054905  cmp     rcx, r15
0x140054908  jz      loc_140054C39
0x14005490e  test    [rcx+1Ch], r14b
0x140054912  jz      loc_140054C39
0x140054918  cmp     byte ptr [rcx+19h], 2
0x14005491c  jb      loc_140054C39
0x140054922  mov     rcx, [rcx+10h]
0x140054926  lea     edx, [rax+15h]
0x140054929  mov     r8, r12
0x14005492c  call    WPP_SF_
0x140054931  jmp     loc_140054C39
0x140054936  mov     r9, rax
0x140054939  jmp     short loc_140054942
0x14005493b  lea     r9, Class; unsigned __int16 *
0x140054942  lea     r8, aArchivefolder; "ArchiveFolder"
0x140054949  mov     edx, 1; unsigned int
0x14005494e  mov     rcx, rsi; HKEY
0x140054951  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140054956  test    eax, eax
0x140054958  jnz     short loc_14005499D
0x14005495a  call    cs:__imp_GetLastError
0x140054961  nop     dword ptr [rax+rax+00h]
0x140054966  mov     ebx, eax
0x140054968  mov     rcx, cs:WPP_GLOBAL_Control
0x14005496f  cmp     rcx, r15
0x140054972  jz      loc_140054C39
0x140054978  test    [rcx+1Ch], r14b
0x14005497c  jz      loc_140054C39
0x140054982  cmp     byte ptr [rcx+19h], 2
0x140054986  jb      loc_140054C39
0x14005498c  mov     edx, 16h
0x140054991  lea     r9, aArchivefolder; "ArchiveFolder"
0x140054998  jmp     loc_140054C29
0x14005499d  mov     r8d, [rdi+10h]
0x1400549a1  lea     rdx, aSizequotawarn; "SizeQuotaWarn"
0x1400549a8  mov     rcx, rsi
0x1400549ab  call    SetRegistryDword
0x1400549b0  test    eax, eax
0x1400549b2  jnz     short loc_1400549F7
0x1400549b4  call    cs:__imp_GetLastError
0x1400549bb  nop     dword ptr [rax+rax+00h]
0x1400549c0  mov     ebx, eax
0x1400549c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400549c9  cmp     rcx, r15
0x1400549cc  jz      loc_140054C39
0x1400549d2  test    [rcx+1Ch], r14b
0x1400549d6  jz      loc_140054C39
0x1400549dc  cmp     byte ptr [rcx+19h], 2
0x1400549e0  jb      loc_140054C39
0x1400549e6  mov     edx, 17h
0x1400549eb  lea     r9, aSizequotawarn; "SizeQuotaWarn"
0x1400549f2  jmp     loc_140054C29
0x1400549f7  mov     r8d, [rdi+14h]
0x1400549fb  lea     rdx, aHighwatermark; "HighWatermark"
0x140054a02  mov     rcx, rsi
0x140054a05  call    SetRegistryDword
0x140054a0a  test    eax, eax
0x140054a0c  jnz     short loc_140054A51
0x140054a0e  call    cs:__imp_GetLastError
0x140054a15  nop     dword ptr [rax+rax+00h]
0x140054a1a  mov     ebx, eax
0x140054a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a23  cmp     rcx, r15
0x140054a26  jz      loc_140054C39
0x140054a2c  test    [rcx+1Ch], r14b
0x140054a30  jz      loc_140054C39
0x140054a36  cmp     byte ptr [rcx+19h], 2
0x140054a3a  jb      loc_140054C39
0x140054a40  mov     edx, 18h
0x140054a45  lea     r9, aHighwatermark; "HighWatermark"
0x140054a4c  jmp     loc_140054C29
0x140054a51  mov     r8d, [rdi+18h]
0x140054a55  lea     rdx, aLowwatermark; "LowWatermark"
0x140054a5c  mov     rcx, rsi
0x140054a5f  call    SetRegistryDword
0x140054a64  test    eax, eax
0x140054a66  jnz     short loc_140054AAB
0x140054a68  call    cs:__imp_GetLastError
0x140054a6f  nop     dword ptr [rax+rax+00h]
0x140054a74  mov     ebx, eax
0x140054a76  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a7d  cmp     rcx, r15
0x140054a80  jz      loc_140054C39
0x140054a86  test    [rcx+1Ch], r14b
0x140054a8a  jz      loc_140054C39
0x140054a90  cmp     byte ptr [rcx+19h], 2
0x140054a94  jb      loc_140054C39
0x140054a9a  mov     edx, 19h
0x140054a9f  lea     r9, aLowwatermark; "LowWatermark"
0x140054aa6  jmp     loc_140054C29
0x140054aab  mov     r8d, [rdi+1Ch]
0x140054aaf  lea     rdx, aArchiveagelimi; "ArchiveAgeLimit"
0x140054ab6  mov     rcx, rsi
0x140054ab9  call    SetRegistryDword
0x140054abe  test    eax, eax
0x140054ac0  jnz     short loc_140054B05
0x140054ac2  call    cs:__imp_GetLastError
0x140054ac9  nop     dword ptr [rax+rax+00h]
0x140054ace  mov     ebx, eax
0x140054ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x140054ad7  cmp     rcx, r15
0x140054ada  jz      loc_140054C39
0x140054ae0  test    [rcx+1Ch], r14b
0x140054ae4  jz      loc_140054C39
0x140054aea  cmp     byte ptr [rcx+19h], 2
0x140054aee  jb      loc_140054C39
0x140054af4  mov     edx, 1Ah
0x140054af9  lea     r9, aArchiveagelimi; "ArchiveAgeLimit"
0x140054b00  jmp     loc_140054C29
0x140054b05  mov     eax, [rdi+44h]
0x140054b08  lea     r8, [rsp+98h+var_68]; struct _FAX_OUTBOX_CONFIG *
0x140054b0d  mov     [rsp+98h+var_64], eax
0x140054b11  mov     rdx, rsi; HKEY
0x140054b14  mov     eax, [rdi+34h]
0x140054b17  mov     [rsp+98h+var_60], eax
0x140054b1b  mov     eax, [rdi+2Ch]
0x140054b1e  mov     [rsp+98h+var_5C], eax
0x140054b22  mov     eax, [rdi+30h]
0x140054b25  mov     [rsp+98h+var_58], eax
0x140054b29  mov     eax, [rdi+38h]
0x140054b2c  mov     [rsp+98h+var_54], eax
0x140054b30  mov     eax, [rdi+3Ch]
0x140054b33  mov     [rsp+98h+var_50], eax
0x140054b37  mov     eax, [rdi+28h]
0x140054b3a  mov     [rsp+98h+var_4C], eax
0x140054b3e  mov     eax, [rdi+40h]
0x140054b41  mov     [rsp+98h+var_48], eax
0x140054b45  mov     [rsp+98h+var_68], 24h ; '$'
0x140054b4d  call    ?StoreOutboxSettings@CFaxConfiguration@@AEBAKPEAUHKEY__@@QEAU_FAX_OUTBOX_CONFIG@@@Z; CFaxConfiguration::StoreOutboxSettings(HKEY__ *,_FAX_OUTBOX_CONFIG * const)
0x140054b52  mov     ebx, eax
0x140054b54  test    eax, eax
0x140054b56  jz      short loc_140054B95
0x140054b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b5f  cmp     rcx, r15
0x140054b62  jz      loc_140054C39
0x140054b68  test    [rcx+1Ch], r14b
0x140054b6c  jz      loc_140054C39
0x140054b72  cmp     byte ptr [rcx+19h], 2
0x140054b76  jb      loc_140054C39
0x140054b7c  mov     rcx, [rcx+10h]
0x140054b80  mov     edx, 1Bh
0x140054b85  mov     r9d, eax
0x140054b88  mov     r8, r12
0x140054b8b  call    WPP_SF_d
0x140054b90  jmp     loc_140054C39
0x140054b95  mov     r8d, [rdi+4Ch]
0x140054b99  lea     rdx, aAutocreateacco; "AutoCreateAccountOnConnect"
0x140054ba0  mov     rcx, rsi
0x140054ba3  call    SetRegistryDword
0x140054ba8  test    eax, eax
0x140054baa  jnz     short loc_140054BE0
0x140054bac  call    cs:__imp_GetLastError
0x140054bb3  nop     dword ptr [rax+rax+00h]
0x140054bb8  mov     ebx, eax
0x140054bba  mov     rcx, cs:WPP_GLOBAL_Control
0x140054bc1  cmp     rcx, r15
0x140054bc4  jz      short loc_140054C39
0x140054bc6  test    [rcx+1Ch], r14b
0x140054bca  jz      short loc_140054C39
0x140054bcc  cmp     byte ptr [rcx+19h], 2
0x140054bd0  jb      short loc_140054C39
0x140054bd2  mov     edx, 1Ch
0x140054bd7  lea     r9, aAutocreateacco; "AutoCreateAccountOnConnect"
0x140054bde  jmp     short loc_140054C29
0x140054be0  mov     r8d, [rdi+50h]
0x140054be4  lea     rdx, aIncomingfaxesa; "IncomingFaxesArePublic"
0x140054beb  mov     rcx, rsi
0x140054bee  call    SetRegistryDword
0x140054bf3  test    eax, eax
0x140054bf5  jnz     short loc_140054C39
0x140054bf7  call    cs:__imp_GetLastError
0x140054bfe  nop     dword ptr [rax+rax+00h]
0x140054c03  mov     ebx, eax
0x140054c05  mov     rcx, cs:WPP_GLOBAL_Control
0x140054c0c  cmp     rcx, r15
0x140054c0f  jz      short loc_140054C39
0x140054c11  test    [rcx+1Ch], r14b
0x140054c15  jz      short loc_140054C39
0x140054c17  cmp     byte ptr [rcx+19h], 2
0x140054c1b  jb      short loc_140054C39
0x140054c1d  mov     edx, 1Dh
0x140054c22  lea     r9, aIncomingfaxesa; "IncomingFaxesArePublic"
0x140054c29  mov     rcx, [rcx+10h]
0x140054c2d  mov     r8, r12
0x140054c30  mov     [rsp+98h+var_78], eax
0x140054c34  call    WPP_SF_Sd
0x140054c39  mov     rcx, rbp; lpMem
0x140054c3c  call    pMemFree
0x140054c41  mov     eax, ebx
0x140054c43  add     rsp, 60h
0x140054c47  pop     r15
0x140054c49  pop     r14
0x140054c4b  pop     r12
0x140054c4d  pop     rdi
0x140054c4e  pop     rsi
0x140054c4f  pop     rbp
0x140054c50  pop     rbx
0x140054c51  retn
```
