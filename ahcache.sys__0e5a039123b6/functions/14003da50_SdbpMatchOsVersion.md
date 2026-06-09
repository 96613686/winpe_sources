# SdbpMatchOsVersion

- ea: `0x14003da50`
- end: `0x14003e14e`
- name: `SdbpMatchOsVersion`
- size: `1790`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14003bea8`

## callees

- `0x1400055d4`
- `0x1400079f0`
- `0x140007e40`
- `0x14003da50`
- `0x14003e154`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14003fc10`
- `0x14003fcb0`
- `0x140053c68`
- `0x140054300`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x14003daa6`
- `ntoskrnl!RtlGetVersion` at `0x14003daa6`

## string_xrefs

- `0x14003db93`: `Error reading data`
- `0x14003dc9f`: `Error reading data`
- `0x14003dd90`: `Error reading data`

## pseudocode

```c
_BOOL8 __fastcall SdbpMatchOsVersion(__int64 a1, unsigned int a2)
{
  BOOL v4; // ebp
  unsigned int v5; // r12d
  unsigned __int64 v6; // r13
  unsigned int NextTagId; // edi
  unsigned int v8; // eax
  unsigned int v9; // r14d
  unsigned int v10; // edi
  unsigned int v11; // ebp
  __int64 QWORDTag; // rax
  unsigned int v13; // edi
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // edi
  unsigned int v17; // ebp
  unsigned int v18; // edi
  unsigned int v19; // r14d
  unsigned int v20; // edi
  unsigned int v21; // ebp
  __int64 v23; // rax
  __int64 v24; // rax
  _WORD v25[2]; // [rsp+40h] [rbp-178h] BYREF
  int v26; // [rsp+44h] [rbp-174h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-168h] BYREF

  v4 = 1;
  v26 = 1;
  memset(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  RtlGetVersion(&VersionInformation);
  v5 = 12;
  v6 = (VersionInformation.dwBuildNumber
      | ((VersionInformation.dwMinorVersion | ((unsigned __int64)VersionInformation.dwMajorVersion << 16)) << 16)) << 16;
  if ( a2 )
  {
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
    {
      v9 = 0;
      goto LABEL_7;
    }
    NextTagId = SdbpGetNextTagId(a1, a2);
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && NextTagId > *(_DWORD *)(a1 + 20) )
    {
      AslLogCallPrintf(
        2,
        "SdbGetFirstChild",
        3141,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; pdb->dwSize=0x%X)",
        a2,
        *(_DWORD *)(a1 + 20));
      v9 = 0;
      goto LABEL_7;
    }
    v8 = a2 + 6;
  }
  else
  {
    NextTagId = *(_DWORD *)(a1 + 20);
    v8 = 12;
  }
  v9 = 0;
  if ( v8 < NextTagId )
    v9 = v8;
LABEL_7:
  while ( v9 )
  {
    v25[0] = 0;
    if ( (unsigned int)SdbpReadMappedData(a1, v9, v25, 2u) )
    {
      if ( v25[0] == 20509 )
      {
        QWORDTag = SdbReadQWORDTag(a1, v9, 0);
        v4 = SdbpCheckVersion(QWORDTag, v6) != 0;
        v26 = v4;
        break;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    }
    if ( !a2 )
    {
      v10 = *(_DWORD *)(a1 + 20);
      goto LABEL_12;
    }
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
    {
      v10 = SdbpGetNextTagId(a1, a2);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        && v10 > *(_DWORD *)(a1 + 20) )
      {
        AslLogCallPrintf(
          2,
          "SdbGetNextChild",
          3196,
          "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
          a2,
          v9,
          *(_DWORD *)(a1 + 20));
        v9 = 0;
      }
      else
      {
LABEL_12:
        v11 = SdbpGetNextTagId(a1, v9);
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( v11 < v10 )
            goto LABEL_15;
LABEL_14:
          v11 = 0;
          goto LABEL_15;
        }
        if ( v11 >= v10 || v11 <= v9 )
          goto LABEL_14;
LABEL_15:
        v9 = v11;
        v4 = v26;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v9 = 0;
    }
  }
  if ( a2 )
  {
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
    {
      v15 = 0;
      goto LABEL_24;
    }
    v13 = SdbpGetNextTagId(a1, a2);
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && v13 > *(_DWORD *)(a1 + 20) )
    {
      AslLogCallPrintf(
        2,
        "SdbGetFirstChild",
        3141,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; pdb->dwSize=0x%X)",
        a2,
        *(_DWORD *)(a1 + 20));
      v15 = 0;
      goto LABEL_24;
    }
    v14 = a2 + 6;
  }
  else
  {
    v13 = *(_DWORD *)(a1 + 20);
    v14 = 12;
  }
  v15 = 0;
  if ( v14 < v13 )
    v15 = v14;
LABEL_24:
  while ( v15 )
  {
    v25[0] = 0;
    if ( (unsigned int)SdbpReadMappedData(a1, v15, v25, 2u) )
    {
      if ( v25[0] == 20511 )
      {
        v23 = SdbReadQWORDTag(a1, v15, 0);
        if ( v4 && (unsigned int)SdbpCheckFromVersion(v23, v6) )
        {
          v4 = 1;
          v26 = 1;
        }
        else
        {
          v4 = 0;
          v26 = 0;
        }
        break;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    }
    if ( !a2 )
    {
      v16 = *(_DWORD *)(a1 + 20);
      goto LABEL_29;
    }
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
    {
      v16 = SdbpGetNextTagId(a1, a2);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        && v16 > *(_DWORD *)(a1 + 20) )
      {
        AslLogCallPrintf(
          2,
          "SdbGetNextChild",
          3196,
          "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
          a2,
          v15,
          *(_DWORD *)(a1 + 20));
        v15 = 0;
        goto LABEL_32;
      }
LABEL_29:
      v17 = SdbpGetNextTagId(a1, v15);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( v17 < v16 && v17 > v15 )
          goto LABEL_31;
      }
      else if ( v17 < v16 )
      {
LABEL_31:
        v15 = v17;
LABEL_32:
        v4 = v26;
        continue;
      }
      v17 = 0;
      goto LABEL_31;
    }
    AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
    v4 = v26;
    v15 = 0;
  }
  if ( a2 )
  {
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
    {
      v19 = 0;
      goto LABEL_40;
    }
    v18 = SdbpGetNextTagId(a1, a2);
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && v18 > *(_DWORD *)(a1 + 20) )
    {
      AslLogCallPrintf(
        2,
        "SdbGetFirstChild",
        3141,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; pdb->dwSize=0x%X)",
        a2,
        *(_DWORD *)(a1 + 20));
      v19 = 0;
      goto LABEL_40;
    }
    v5 = a2 + 6;
  }
  else
  {
    v18 = *(_DWORD *)(a1 + 20);
  }
  v19 = 0;
  if ( v5 < v18 )
    v19 = v5;
LABEL_40:
  while ( 2 )
  {
    if ( !v19 )
      return v4;
    v25[0] = 0;
    if ( !(unsigned int)SdbpReadMappedData(a1, v19, v25, 2u) )
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
      goto LABEL_43;
    }
    if ( v25[0] != 20510 )
    {
LABEL_43:
      if ( !a2 )
      {
        v20 = *(_DWORD *)(a1 + 20);
        goto LABEL_45;
      }
      if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
      {
        v20 = SdbpGetNextTagId(a1, a2);
        if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
          && v20 > *(_DWORD *)(a1 + 20) )
        {
          AslLogCallPrintf(
            2,
            "SdbGetNextChild",
            3196,
            "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
            a2,
            v19,
            *(_DWORD *)(a1 + 20));
          v19 = 0;
          goto LABEL_48;
        }
LABEL_45:
        v21 = SdbpGetNextTagId(a1, v19);
        if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( v21 < v20 && v21 > v19 )
            goto LABEL_47;
        }
        else if ( v21 < v20 )
        {
LABEL_47:
          v19 = v21;
LABEL_48:
          v4 = v26;
          continue;
        }
        v21 = 0;
        goto LABEL_47;
      }
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v4 = v26;
      v19 = 0;
      continue;
    }
    break;
  }
  v24 = SdbReadQWORDTag(a1, v19, 0);
  return v4 && (unsigned int)SdbpCheckUptoVersion(v24, v6);
}

```

## disassembly

```asm
0x14003da50  mov     [rsp+arg_10], rbx
0x14003da55  push    rbp
0x14003da56  push    rsi
0x14003da57  push    rdi
0x14003da58  push    r12
0x14003da5a  push    r13
0x14003da5c  push    r14
0x14003da5e  push    r15
0x14003da60  sub     rsp, 180h
0x14003da67  mov     rax, cs:__security_cookie
0x14003da6e  xor     rax, rsp
0x14003da71  mov     [rsp+1B8h+var_48], rax
0x14003da79  mov     esi, edx
0x14003da7b  mov     rbx, rcx
0x14003da7e  mov     ebp, 1
0x14003da83  lea     rcx, [rsp+1B8h+VersionInformation.dwMajorVersion]; void *
0x14003da88  xor     edx, edx; Val
0x14003da8a  mov     [rsp+1B8h+var_174], ebp
0x14003da8e  mov     r8d, 118h; Size
0x14003da94  call    memset
0x14003da99  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x14003da9e  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14003daa6  call    cs:__imp_RtlGetVersion
0x14003daad  nop     dword ptr [rax+rax+00h]
0x14003dab2  mov     eax, [rsp+1B8h+VersionInformation.dwMinorVersion]
0x14003dab6  mov     edi, 0F000h
0x14003dabb  mov     r13d, [rsp+1B8h+VersionInformation.dwMajorVersion]
0x14003dac0  mov     r12d, 0Ch
0x14003dac6  shl     r13, 10h
0x14003daca  mov     r14d, 7000h
0x14003dad0  or      r13, rax
0x14003dad3  mov     eax, [rsp+1B8h+VersionInformation.dwBuildNumber]
0x14003dad7  shl     r13, 10h
0x14003dadb  or      r13, rax
0x14003dade  shl     r13, 10h
0x14003dae2  test    esi, esi
0x14003dae4  jz      loc_14003DDDE
0x14003daea  mov     edx, esi
0x14003daec  mov     rcx, rbx
0x14003daef  call    SdbGetTagFromTagID
0x14003daf4  and     ax, di
0x14003daf7  cmp     ax, r14w
0x14003dafb  jnz     loc_14003DFD6
0x14003db01  mov     edx, esi
0x14003db03  mov     rcx, rbx
0x14003db06  call    SdbpGetNextTagId
0x14003db0b  mov     edi, eax
0x14003db0d  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003db12  test    eax, eax
0x14003db14  jnz     loc_14003DFE1
0x14003db1a  lea     eax, [rsi+6]
0x14003db1d  xor     r15d, r15d
0x14003db20  cmp     eax, edi
0x14003db22  mov     r14d, r15d
0x14003db25  cmovb   r14d, eax
0x14003db29  mov     edi, 501Dh
0x14003db2e  test    r14d, r14d
0x14003db31  jz      loc_14003DBD9
0x14003db37  mov     r9d, 2
0x14003db3d  mov     [rsp+1B8h+var_178], r15w
0x14003db43  lea     r8, [rsp+1B8h+var_178]
0x14003db48  mov     edx, r14d
0x14003db4b  mov     rcx, rbx
0x14003db4e  call    SdbpReadMappedData
0x14003db53  test    eax, eax
0x14003db55  jz      short loc_14003DB93
0x14003db57  cmp     [rsp+1B8h+var_178], di
0x14003db5c  jz      short loc_14003DBB3
0x14003db5e  test    esi, esi
0x14003db60  jnz     loc_14003DF01
0x14003db66  mov     edi, [rbx+14h]
0x14003db69  mov     edx, r14d
0x14003db6c  mov     rcx, rbx
0x14003db6f  call    SdbpGetNextTagId
0x14003db74  mov     ebp, eax
0x14003db76  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003db7b  test    eax, eax
0x14003db7d  jnz     loc_14003E01D
0x14003db83  cmp     ebp, edi
0x14003db85  jb      short loc_14003DB8A
0x14003db87  mov     ebp, r15d
0x14003db8a  mov     r14d, ebp
0x14003db8d  mov     ebp, [rsp+1B8h+var_174]
0x14003db91  jmp     short loc_14003DB29
0x14003db93  lea     r9, aErrorReadingDa; "Error reading data"
0x14003db9a  mov     r8d, 0BDFh
0x14003dba0  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003dba7  mov     ecx, 1
0x14003dbac  call    AslLogCallPrintf
0x14003dbb1  jmp     short loc_14003DB5E
0x14003dbb3  xor     r8d, r8d
0x14003dbb6  mov     edx, r14d
0x14003dbb9  mov     rcx, rbx
0x14003dbbc  call    SdbReadQWORDTag
0x14003dbc1  mov     rcx, rax
0x14003dbc4  mov     rdx, r13
0x14003dbc7  call    SdbpCheckVersion
0x14003dbcc  mov     ebp, r15d
0x14003dbcf  test    eax, eax
0x14003dbd1  setnz   bpl
0x14003dbd5  mov     [rsp+1B8h+var_174], ebp
0x14003dbd9  test    esi, esi
0x14003dbdb  jz      loc_14003DDE9
0x14003dbe1  mov     edx, esi
0x14003dbe3  mov     rcx, rbx
0x14003dbe6  call    SdbGetTagFromTagID
0x14003dbeb  mov     ecx, 0F000h
0x14003dbf0  and     ax, cx
0x14003dbf3  mov     ecx, 7000h
0x14003dbf8  cmp     ax, cx
0x14003dbfb  jnz     loc_14003E033
0x14003dc01  mov     edx, esi
0x14003dc03  mov     rcx, rbx
0x14003dc06  call    SdbpGetNextTagId
0x14003dc0b  mov     edi, eax
0x14003dc0d  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003dc12  test    eax, eax
0x14003dc14  jnz     loc_14003E03B
0x14003dc1a  lea     eax, [rsi+6]
0x14003dc1d  cmp     eax, edi
0x14003dc1f  mov     r14d, r15d
0x14003dc22  cmovb   r14d, eax
0x14003dc26  mov     edi, 501Fh
0x14003dc2b  nop     dword ptr [rax+rax+00h]
0x14003dc30  test    r14d, r14d
0x14003dc33  jz      loc_14003DCBF
0x14003dc39  mov     r9d, 2
0x14003dc3f  mov     [rsp+1B8h+var_178], r15w
0x14003dc45  lea     r8, [rsp+1B8h+var_178]
0x14003dc4a  mov     edx, r14d
0x14003dc4d  mov     rcx, rbx
0x14003dc50  call    SdbpReadMappedData
0x14003dc55  test    eax, eax
0x14003dc57  jz      short loc_14003DC9F
0x14003dc59  cmp     [rsp+1B8h+var_178], di
0x14003dc5e  jz      loc_14003E089
0x14003dc64  test    esi, esi
0x14003dc66  jnz     loc_14003DF47
0x14003dc6c  mov     edi, [rbx+14h]
0x14003dc6f  mov     edx, r14d
0x14003dc72  mov     rcx, rbx
0x14003dc75  call    SdbpGetNextTagId
0x14003dc7a  mov     ebp, eax
0x14003dc7c  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003dc81  test    eax, eax
0x14003dc83  jnz     loc_14003E074
0x14003dc89  cmp     ebp, edi
0x14003dc8b  jnb     loc_14003E081
0x14003dc91  mov     r14d, ebp
0x14003dc94  mov     ebp, [rsp+1B8h+var_174]
0x14003dc98  mov     edi, 501Fh
0x14003dc9d  jmp     short loc_14003DC30
0x14003dc9f  lea     r9, aErrorReadingDa; "Error reading data"
0x14003dca6  mov     r8d, 0BDFh
0x14003dcac  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003dcb3  mov     ecx, 1
0x14003dcb8  call    AslLogCallPrintf
0x14003dcbd  jmp     short loc_14003DC64
0x14003dcbf  test    esi, esi
0x14003dcc1  jz      loc_14003DDF4
0x14003dcc7  mov     edx, esi
0x14003dcc9  mov     rcx, rbx
0x14003dccc  call    SdbGetTagFromTagID
0x14003dcd1  mov     edi, 0F000h
0x14003dcd6  mov     ecx, 7000h
0x14003dcdb  and     ax, di
0x14003dcde  cmp     ax, cx
0x14003dce1  jnz     loc_14003E0C5
0x14003dce7  mov     edx, esi
0x14003dce9  mov     rcx, rbx
0x14003dcec  call    SdbpGetNextTagId
0x14003dcf1  mov     edi, eax
0x14003dcf3  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003dcf8  test    eax, eax
0x14003dcfa  jnz     loc_14003E0CD
0x14003dd00  lea     r12d, [rsi+6]
0x14003dd04  cmp     r12d, edi
0x14003dd07  mov     r14d, r15d
0x14003dd0a  cmovb   r14d, r12d
0x14003dd0e  mov     edi, 0F000h
0x14003dd13  mov     r12d, 501Eh
0x14003dd19  nop     dword ptr [rax+00000000h]
0x14003dd20  test    r14d, r14d
0x14003dd23  jz      loc_14003DDB0
0x14003dd29  mov     r9d, 2
0x14003dd2f  mov     [rsp+1B8h+var_178], r15w
0x14003dd35  lea     r8, [rsp+1B8h+var_178]
0x14003dd3a  mov     edx, r14d
0x14003dd3d  mov     rcx, rbx
0x14003dd40  call    SdbpReadMappedData
0x14003dd45  test    eax, eax
0x14003dd47  jz      short loc_14003DD90
0x14003dd49  cmp     [rsp+1B8h+var_178], r12w
0x14003dd4f  jz      loc_14003E11B
0x14003dd55  test    esi, esi
0x14003dd57  jnz     loc_14003DF91
0x14003dd5d  mov     edi, [rbx+14h]
0x14003dd60  mov     edx, r14d
0x14003dd63  mov     rcx, rbx
0x14003dd66  call    SdbpGetNextTagId
0x14003dd6b  mov     ebp, eax
0x14003dd6d  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003dd72  test    eax, eax
0x14003dd74  jnz     loc_14003E106
0x14003dd7a  cmp     ebp, edi
0x14003dd7c  jnb     loc_14003E113
0x14003dd82  mov     r14d, ebp
0x14003dd85  mov     ebp, [rsp+1B8h+var_174]
0x14003dd89  mov     edi, 0F000h
0x14003dd8e  jmp     short loc_14003DD20
0x14003dd90  lea     r9, aErrorReadingDa; "Error reading data"
0x14003dd97  mov     r8d, 0BDFh
0x14003dd9d  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003dda4  mov     ecx, 1
0x14003dda9  call    AslLogCallPrintf
0x14003ddae  jmp     short loc_14003DD55
0x14003ddb0  mov     eax, ebp
0x14003ddb2  mov     rcx, [rsp+1B8h+var_48]
0x14003ddba  xor     rcx, rsp; StackCookie
0x14003ddbd  call    __security_check_cookie
0x14003ddc2  mov     rbx, [rsp+1B8h+arg_10]
0x14003ddca  add     rsp, 180h
0x14003ddd1  pop     r15
0x14003ddd3  pop     r14
0x14003ddd5  pop     r13
0x14003ddd7  pop     r12
0x14003ddd9  pop     rdi
0x14003ddda  pop     rsi
0x14003dddb  pop     rbp
0x14003dddc  retn
0x14003ddde  mov     edi, [rbx+14h]
0x14003dde1  mov     eax, r12d
0x14003dde4  jmp     loc_14003DB1D
0x14003dde9  mov     edi, [rbx+14h]
0x14003ddec  mov     eax, r12d
0x14003ddef  jmp     loc_14003DC1D
0x14003ddf4  mov     edi, [rbx+14h]
0x14003ddf7  jmp     loc_14003DD04
0x14003ddfc  mov     edx, esi
0x14003ddfe  mov     rcx, rbx
0x14003de01  call    SdbpGetNextTagId
0x14003de06  mov     edi, eax
0x14003de08  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003de0d  test    eax, eax
0x14003de0f  jz      loc_14003DB69
0x14003de15  mov     eax, [rbx+14h]
0x14003de18  cmp     edi, eax
0x14003de1a  jbe     loc_14003DB69
0x14003de20  mov     [rsp+1B8h+var_188], eax
0x14003de24  lea     r9, aSdbpgetnexttag; "SdbpGetNextTagId returned value larger "...
0x14003de2b  mov     [rsp+1B8h+var_190], r14d
0x14003de30  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x14003de37  mov     r8d, 0C7Ch
0x14003de3d  mov     [rsp+1B8h+var_198], esi
0x14003de41  mov     ecx, 2
0x14003de46  call    AslLogCallPrintf
0x14003de4b  mov     r14d, r15d
0x14003de4e  jmp     loc_14003DB29
0x14003de53  mov     edx, esi
0x14003de55  mov     rcx, rbx
0x14003de58  call    SdbpGetNextTagId
0x14003de5d  mov     edi, eax
0x14003de5f  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003de64  test    eax, eax
0x14003de66  jz      loc_14003DC6F
0x14003de6c  mov     eax, [rbx+14h]
0x14003de6f  cmp     edi, eax
0x14003de71  jbe     loc_14003DC6F
0x14003de77  mov     [rsp+1B8h+var_188], eax
0x14003de7b  lea     r9, aSdbpgetnexttag; "SdbpGetNextTagId returned value larger "...
0x14003de82  mov     [rsp+1B8h+var_190], r14d
0x14003de87  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x14003de8e  mov     r8d, 0C7Ch
0x14003de94  mov     [rsp+1B8h+var_198], esi
0x14003de98  mov     ecx, 2
0x14003de9d  call    AslLogCallPrintf
0x14003dea2  mov     r14d, r15d
0x14003dea5  jmp     loc_14003DC94
0x14003deaa  mov     edx, esi
0x14003deac  mov     rcx, rbx
0x14003deaf  call    SdbpGetNextTagId
0x14003deb4  mov     edi, eax
0x14003deb6  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003debb  test    eax, eax
0x14003debd  jz      loc_14003DD60
0x14003dec3  mov     eax, [rbx+14h]
0x14003dec6  cmp     edi, eax
0x14003dec8  jbe     loc_14003DD60
0x14003dece  mov     [rsp+1B8h+var_188], eax
0x14003ded2  lea     r9, aSdbpgetnexttag; "SdbpGetNextTagId returned value larger "...
0x14003ded9  mov     [rsp+1B8h+var_190], r14d
0x14003dede  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x14003dee5  mov     r8d, 0C7Ch
0x14003deeb  mov     [rsp+1B8h+var_198], esi
0x14003deef  mov     ecx, 2
0x14003def4  call    AslLogCallPrintf
0x14003def9  mov     r14d, r15d
0x14003defc  jmp     loc_14003DD85
0x14003df01  mov     edx, esi
0x14003df03  mov     rcx, rbx
  ... truncated ...
```
