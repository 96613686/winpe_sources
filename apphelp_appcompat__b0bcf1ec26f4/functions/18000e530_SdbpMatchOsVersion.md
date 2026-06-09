# SdbpMatchOsVersion

- ea: `0x18000e530`
- end: `0x18000ecad`
- name: `SdbpMatchOsVersion`
- size: `1917`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000c43c`
- `0x180010700`

## callees

- `0x18000e530`
- `0x18000ef24`
- `0x18000ef54`
- `0x18000efe0`
- `0x18000f114`
- `0x180026ca0`
- `0x18002e38c`
- `0x18002e590`
- `0x18004ac2c`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x18000e583`
- `ntdll!RtlGetVersion` at `0x18000e583`

## string_xrefs

- `0x18000e729`: `SdbpReadMappedData`
- `0x18000e7e1`: `SdbpReadMappedData`
- `0x18000e944`: `SdbpReadMappedData`
- `0x18000eb73`: `SdbpReadMappedData`
- `0x18000ebdc`: `SdbpReadMappedData`
- `0x18000ec4f`: `SdbpReadMappedData`
- `0x18000e73c`: `Error reading data`
- `0x18000e7f2`: `Error reading data`
- `0x18000e955`: `Error reading data`
- `0x18000eb64`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000ebcd`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000ec40`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
_BOOL8 __fastcall SdbpMatchOsVersion(__int64 a1, unsigned int a2)
{
  BOOL v4; // r13d
  unsigned int v5; // r15d
  unsigned __int64 v6; // r12
  unsigned int NextTagId; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // ecx
  unsigned int *v11; // rsi
  __int64 QWORDTag; // rax
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // esi
  unsigned int v19; // r14d
  unsigned int v20; // esi
  unsigned int v21; // r14d
  unsigned int v22; // esi
  unsigned int v23; // edi
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned int v27; // r14d
  unsigned int v28; // esi
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-168h] BYREF

  v4 = 1;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
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
      goto LABEL_9;
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
      goto LABEL_9;
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
LABEL_9:
  while ( v9 )
  {
    if ( v9 >= 0xFFFFFFFE )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
      v11 = (unsigned int *)(a1 + 20);
LABEL_32:
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
      goto LABEL_33;
    }
    v10 = *(_DWORD *)(a1 + 20);
    v11 = (unsigned int *)(a1 + 20);
    if ( v10 < v9 + 2 )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v9,
        2,
        v10);
      goto LABEL_32;
    }
    if ( *(_WORD *)(v9 + *(_QWORD *)(a1 + 8)) == 20509 )
    {
      QWORDTag = SdbReadQWORDTag(a1, v9, 0);
      v4 = SdbpCheckVersion(QWORDTag, v6) != 0;
      break;
    }
LABEL_33:
    if ( !a2 )
    {
      v19 = *v11;
      goto LABEL_37;
    }
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
    {
      v19 = SdbpGetNextTagId(a1, a2);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() && v19 > *v11 )
      {
        AslLogCallPrintf(
          2,
          "SdbGetNextChild",
          3196,
          "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
          a2,
          v9,
          *v11);
        v9 = 0;
      }
      else
      {
LABEL_37:
        v20 = SdbpGetNextTagId(a1, v9);
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( v20 < v19 )
            goto LABEL_40;
LABEL_82:
          v20 = 0;
          goto LABEL_40;
        }
        if ( v20 >= v19 || v20 <= v9 )
          goto LABEL_82;
LABEL_40:
        v9 = v20;
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
      goto LABEL_22;
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
      goto LABEL_22;
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
LABEL_22:
  while ( v15 )
  {
    if ( v15 >= 0xFFFFFFFE )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
LABEL_42:
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
      goto LABEL_43;
    }
    v16 = *(_DWORD *)(a1 + 20);
    if ( v16 < v15 + 2 )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v15,
        2,
        v16);
      goto LABEL_42;
    }
    if ( *(_WORD *)(v15 + *(_QWORD *)(a1 + 8)) == 20511 )
    {
      v17 = SdbReadQWORDTag(a1, v15, 0);
      v4 = v4 && (unsigned int)SdbpCheckFromVersion(v17, v6);
      break;
    }
LABEL_43:
    if ( !a2 )
    {
      v21 = *(_DWORD *)(a1 + 20);
LABEL_47:
      v22 = SdbpGetNextTagId(a1, v15);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( v22 < v21 && v22 > v15 )
          goto LABEL_50;
LABEL_84:
        v22 = 0;
      }
      else if ( v22 >= v21 )
      {
        goto LABEL_84;
      }
LABEL_50:
      v15 = v22;
      continue;
    }
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
    {
      v21 = SdbpGetNextTagId(a1, a2);
      if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        || v21 <= *(_DWORD *)(a1 + 20) )
      {
        goto LABEL_47;
      }
      AslLogCallPrintf(
        2,
        "SdbGetNextChild",
        3196,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
        a2,
        v15,
        *(_DWORD *)(a1 + 20));
      v15 = 0;
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v15 = 0;
    }
  }
  if ( a2 )
  {
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
    {
      v23 = 0;
      goto LABEL_57;
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
      v23 = 0;
      goto LABEL_57;
    }
    v5 = a2 + 6;
  }
  else
  {
    v18 = *(_DWORD *)(a1 + 20);
  }
  v23 = 0;
  if ( v5 < v18 )
    v23 = v5;
  while ( 1 )
  {
LABEL_57:
    if ( !v23 )
      return v4;
    if ( v23 < 0xFFFFFFFE )
      break;
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_65:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
LABEL_66:
    if ( !a2 )
    {
      v27 = *(_DWORD *)(a1 + 20);
LABEL_70:
      v28 = SdbpGetNextTagId(a1, v23);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( v28 < v27 && v28 > v23 )
          goto LABEL_73;
LABEL_86:
        v28 = 0;
      }
      else if ( v28 >= v27 )
      {
        goto LABEL_86;
      }
LABEL_73:
      v23 = v28;
      continue;
    }
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x7000 )
    {
      v27 = SdbpGetNextTagId(a1, a2);
      if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        || v27 <= *(_DWORD *)(a1 + 20) )
      {
        goto LABEL_70;
      }
      AslLogCallPrintf(
        2,
        "SdbGetNextChild",
        3196,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
        a2,
        v23,
        *(_DWORD *)(a1 + 20));
      v23 = 0;
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v23 = 0;
    }
  }
  v24 = *(_DWORD *)(a1 + 20);
  if ( v24 < v23 + 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v23,
      2,
      v24);
    goto LABEL_65;
  }
  if ( *(_WORD *)(v23 + *(_QWORD *)(a1 + 8)) != 20510 )
    goto LABEL_66;
  v25 = SdbReadQWORDTag(a1, v23, 0);
  return v4 && (unsigned int)SdbpCheckUptoVersion(v25, v6);
}

```

## disassembly

```asm
0x18000e530  mov     [rsp+arg_10], rbx
0x18000e535  push    rbp
0x18000e536  push    rsi
0x18000e537  push    rdi
0x18000e538  push    r12
0x18000e53a  push    r13
0x18000e53c  push    r14
0x18000e53e  push    r15
0x18000e540  sub     rsp, 170h
0x18000e547  mov     rax, cs:__security_cookie
0x18000e54e  xor     rax, rsp
0x18000e551  mov     [rsp+1A8h+var_48], rax
0x18000e559  mov     ebp, edx
0x18000e55b  mov     rbx, rcx
0x18000e55e  xor     edx, edx; Val
0x18000e560  lea     rcx, [rsp+1A8h+VersionInformation.dwMajorVersion]; void *
0x18000e565  mov     r8d, 118h; Size
0x18000e56b  mov     r13d, 1
0x18000e571  call    memset_0
0x18000e576  lea     rcx, [rsp+1A8h+VersionInformation]; lpVersionInformation
0x18000e57b  mov     [rsp+1A8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000e583  call    cs:__imp_RtlGetVersion
0x18000e589  mov     eax, [rsp+1A8h+VersionInformation.dwMinorVersion]
0x18000e58d  mov     edi, 7000h
0x18000e592  mov     r12d, [rsp+1A8h+VersionInformation.dwMajorVersion]
0x18000e597  mov     r15d, 0Ch
0x18000e59d  shl     r12, 10h
0x18000e5a1  mov     r14d, 0F000h
0x18000e5a7  or      r12, rax
0x18000e5aa  mov     eax, [rsp+1A8h+VersionInformation.dwBuildNumber]
0x18000e5ae  shl     r12, 10h
0x18000e5b2  or      r12, rax
0x18000e5b5  shl     r12, 10h
0x18000e5b9  test    ebp, ebp
0x18000e5bb  jnz     short loc_18000E5C5
0x18000e5bd  mov     esi, [rbx+14h]
0x18000e5c0  mov     eax, r15d
0x18000e5c3  jmp     short loc_18000E5FF
0x18000e5c5  mov     edx, ebp
0x18000e5c7  mov     rcx, rbx
0x18000e5ca  call    SdbGetTagFromTagID
0x18000e5cf  and     ax, r14w
0x18000e5d3  cmp     ax, di
0x18000e5d6  jnz     loc_18000EB59
0x18000e5dc  mov     edx, ebp
0x18000e5de  mov     rcx, rbx
0x18000e5e1  call    SdbpGetNextTagId
0x18000e5e6  mov     esi, eax
0x18000e5e8  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e5ed  test    eax, eax
0x18000e5ef  jz      short loc_18000E5FC
0x18000e5f1  mov     eax, [rbx+14h]
0x18000e5f4  cmp     esi, eax
0x18000e5f6  ja      loc_18000EA35
0x18000e5fc  lea     eax, [rbp+6]
0x18000e5ff  xor     edi, edi
0x18000e601  cmp     eax, esi
0x18000e603  cmovb   edi, eax
0x18000e606  mov     edx, 501Dh
0x18000e60b  test    edi, edi
0x18000e60d  jz      short loc_18000E65B
0x18000e60f  lea     eax, [rdi+2]
0x18000e612  cmp     eax, 2
0x18000e615  jb      loc_18000E71C
0x18000e61b  mov     ecx, [rbx+14h]
0x18000e61e  lea     rsi, [rbx+14h]
0x18000e622  cmp     ecx, eax
0x18000e624  jb      loc_18000EB60
0x18000e62a  mov     rax, [rbx+8]
0x18000e62e  mov     ecx, edi
0x18000e630  cmp     [rcx+rax], dx
0x18000e634  jnz     loc_18000E758
0x18000e63a  xor     r8d, r8d
0x18000e63d  mov     edx, edi
0x18000e63f  mov     rcx, rbx
0x18000e642  call    SdbReadQWORDTag
0x18000e647  mov     rcx, rax
0x18000e64a  mov     rdx, r12
0x18000e64d  call    SdbpCheckVersion
0x18000e652  xor     r13d, r13d
0x18000e655  test    eax, eax
0x18000e657  setnz   r13b
0x18000e65b  test    ebp, ebp
0x18000e65d  jnz     short loc_18000E667
0x18000e65f  mov     esi, [rbx+14h]
0x18000e662  mov     eax, r15d
0x18000e665  jmp     short loc_18000E6A6
0x18000e667  mov     edx, ebp
0x18000e669  mov     rcx, rbx
0x18000e66c  call    SdbGetTagFromTagID
0x18000e671  and     ax, r14w
0x18000e675  mov     ecx, 7000h
0x18000e67a  cmp     ax, cx
0x18000e67d  jnz     loc_18000EBC2
0x18000e683  mov     edx, ebp
0x18000e685  mov     rcx, rbx
0x18000e688  call    SdbpGetNextTagId
0x18000e68d  mov     esi, eax
0x18000e68f  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e694  test    eax, eax
0x18000e696  jz      short loc_18000E6A3
0x18000e698  mov     eax, [rbx+14h]
0x18000e69b  cmp     esi, eax
0x18000e69d  ja      loc_18000EA62
0x18000e6a3  lea     eax, [rbp+6]
0x18000e6a6  xor     edi, edi
0x18000e6a8  cmp     eax, esi
0x18000e6aa  cmovb   edi, eax
0x18000e6ad  mov     edx, 501Fh
0x18000e6b2  test    edi, edi
0x18000e6b4  jz      short loc_18000E70C
0x18000e6b6  lea     eax, [rdi+2]
0x18000e6b9  cmp     eax, 2
0x18000e6bc  jb      loc_18000E7D4
0x18000e6c2  mov     ecx, [rbx+14h]
0x18000e6c5  cmp     ecx, eax
0x18000e6c7  jb      loc_18000EBC9
0x18000e6cd  mov     rax, [rbx+8]
0x18000e6d1  mov     ecx, edi
0x18000e6d3  cmp     [rcx+rax], dx
0x18000e6d7  jnz     loc_18000E810
0x18000e6dd  xor     r8d, r8d
0x18000e6e0  mov     edx, edi
0x18000e6e2  mov     rcx, rbx
0x18000e6e5  call    SdbReadQWORDTag
0x18000e6ea  test    r13d, r13d
0x18000e6ed  jz      loc_18000EC2D
0x18000e6f3  mov     rdx, r12
0x18000e6f6  mov     rcx, rax
0x18000e6f9  call    SdbpCheckFromVersion
0x18000e6fe  test    eax, eax
0x18000e700  jz      loc_18000EC2D
0x18000e706  mov     r13d, 1
0x18000e70c  test    ebp, ebp
0x18000e70e  jnz     loc_18000E88D
0x18000e714  mov     esi, [rbx+14h]
0x18000e717  jmp     loc_18000E8CD
0x18000e71c  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000e723  mov     r8d, 357h
0x18000e729  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000e730  mov     ecx, r13d
0x18000e733  call    AslLogCallPrintf
0x18000e738  lea     rsi, [rbx+14h]
0x18000e73c  lea     r9, aErrorReadingDa; "Error reading data"
0x18000e743  mov     r8d, 0BDFh
0x18000e749  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000e750  mov     ecx, r13d
0x18000e753  call    AslLogCallPrintf
0x18000e758  test    ebp, ebp
0x18000e75a  jz      loc_18000EA1E
0x18000e760  mov     edx, ebp
0x18000e762  mov     rcx, rbx
0x18000e765  call    SdbGetTagFromTagID
0x18000e76a  and     ax, r14w
0x18000e76e  mov     ecx, 7000h
0x18000e773  cmp     ax, cx
0x18000e776  jnz     loc_18000EAEC
0x18000e77c  mov     edx, ebp
0x18000e77e  mov     rcx, rbx
0x18000e781  call    SdbpGetNextTagId
0x18000e786  mov     r14d, eax
0x18000e789  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e78e  test    eax, eax
0x18000e790  jz      short loc_18000E79D
0x18000e792  mov     eax, [rsi]
0x18000e794  cmp     r14d, eax
0x18000e797  ja      loc_18000EB91
0x18000e79d  mov     edx, edi
0x18000e79f  mov     rcx, rbx
0x18000e7a2  call    SdbpGetNextTagId
0x18000e7a7  mov     esi, eax
0x18000e7a9  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e7ae  test    eax, eax
0x18000e7b0  jz      loc_18000EABC
0x18000e7b6  cmp     esi, r14d
0x18000e7b9  jnb     loc_18000EAC5
0x18000e7bf  cmp     esi, edi
0x18000e7c1  jbe     loc_18000EAC5
0x18000e7c7  mov     edi, esi
0x18000e7c9  mov     r14d, 0F000h
0x18000e7cf  jmp     loc_18000E606
0x18000e7d4  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000e7db  mov     r8d, 357h
0x18000e7e1  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000e7e8  mov     ecx, 1
0x18000e7ed  call    AslLogCallPrintf
0x18000e7f2  lea     r9, aErrorReadingDa; "Error reading data"
0x18000e7f9  mov     r8d, 0BDFh
0x18000e7ff  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000e806  mov     ecx, 1
0x18000e80b  call    AslLogCallPrintf
0x18000e810  test    ebp, ebp
0x18000e812  jz      loc_18000EA26
0x18000e818  mov     edx, ebp
0x18000e81a  mov     rcx, rbx
0x18000e81d  call    SdbGetTagFromTagID
0x18000e822  and     ax, r14w
0x18000e826  mov     ecx, 7000h
0x18000e82b  cmp     ax, cx
0x18000e82e  jnz     loc_18000EB0F
0x18000e834  mov     edx, ebp
0x18000e836  mov     rcx, rbx
0x18000e839  call    SdbpGetNextTagId
0x18000e83e  mov     r14d, eax
0x18000e841  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e846  test    eax, eax
0x18000e848  jz      short loc_18000E856
0x18000e84a  mov     eax, [rbx+14h]
0x18000e84d  cmp     r14d, eax
0x18000e850  ja      loc_18000EBFC
0x18000e856  mov     edx, edi
0x18000e858  mov     rcx, rbx
0x18000e85b  call    SdbpGetNextTagId
0x18000e860  mov     esi, eax
0x18000e862  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e867  test    eax, eax
0x18000e869  jz      loc_18000EACC
0x18000e86f  cmp     esi, r14d
0x18000e872  jnb     loc_18000EAD5
0x18000e878  cmp     esi, edi
0x18000e87a  jbe     loc_18000EAD5
0x18000e880  mov     edi, esi
0x18000e882  mov     r14d, 0F000h
0x18000e888  jmp     loc_18000E6AD
0x18000e88d  mov     edx, ebp
0x18000e88f  mov     rcx, rbx
0x18000e892  call    SdbGetTagFromTagID
0x18000e897  and     ax, r14w
0x18000e89b  mov     ecx, 7000h
0x18000e8a0  cmp     ax, cx
0x18000e8a3  jnz     loc_18000EC35
0x18000e8a9  mov     edx, ebp
0x18000e8ab  mov     rcx, rbx
0x18000e8ae  call    SdbpGetNextTagId
0x18000e8b3  mov     esi, eax
0x18000e8b5  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e8ba  test    eax, eax
0x18000e8bc  jz      short loc_18000E8C9
0x18000e8be  mov     eax, [rbx+14h]
0x18000e8c1  cmp     esi, eax
0x18000e8c3  ja      loc_18000EA8F
0x18000e8c9  lea     r15d, [rbp+6]
0x18000e8cd  xor     edi, edi
0x18000e8cf  cmp     r15d, esi
0x18000e8d2  cmovb   edi, r15d
0x18000e8d6  mov     r15d, 501Eh
0x18000e8dc  test    edi, edi
0x18000e8de  jz      loc_18000E9F0
0x18000e8e4  lea     eax, [rdi+2]
0x18000e8e7  cmp     eax, 2
0x18000e8ea  jb      short loc_18000E937
0x18000e8ec  mov     ecx, [rbx+14h]
0x18000e8ef  cmp     ecx, eax
0x18000e8f1  jb      loc_18000EC3C
0x18000e8f7  mov     rax, [rbx+8]
0x18000e8fb  mov     ecx, edi
0x18000e8fd  cmp     [rcx+rax], r15w
0x18000e902  jnz     short loc_18000E973
0x18000e904  xor     r8d, r8d
0x18000e907  mov     edx, edi
0x18000e909  mov     rcx, rbx
0x18000e90c  call    SdbReadQWORDTag
0x18000e911  test    r13d, r13d
0x18000e914  jz      loc_18000ECA6
0x18000e91a  mov     rdx, r12
0x18000e91d  mov     rcx, rax
0x18000e920  call    SdbpCheckUptoVersion
0x18000e925  test    eax, eax
0x18000e927  jz      loc_18000ECA6
0x18000e92d  mov     eax, 1
0x18000e932  jmp     loc_18000E9F3
0x18000e937  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000e93e  mov     r8d, 357h
0x18000e944  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000e94b  mov     ecx, 1
0x18000e950  call    AslLogCallPrintf
0x18000e955  lea     r9, aErrorReadingDa; "Error reading data"
0x18000e95c  mov     r8d, 0BDFh
0x18000e962  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000e969  mov     ecx, 1
0x18000e96e  call    AslLogCallPrintf
0x18000e973  test    ebp, ebp
0x18000e975  jz      loc_18000EA2F
0x18000e97b  mov     edx, ebp
0x18000e97d  mov     rcx, rbx
0x18000e980  call    SdbGetTagFromTagID
0x18000e985  and     ax, r14w
0x18000e989  mov     ecx, 7000h
0x18000e98e  cmp     ax, cx
0x18000e991  jnz     loc_18000EB34
0x18000e997  mov     edx, ebp
0x18000e999  mov     rcx, rbx
0x18000e99c  call    SdbpGetNextTagId
0x18000e9a1  mov     r14d, eax
0x18000e9a4  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000e9a9  test    eax, eax
0x18000e9ab  jz      short loc_18000E9B9
0x18000e9ad  mov     eax, [rbx+14h]
0x18000e9b0  cmp     r14d, eax
0x18000e9b3  ja      loc_18000EC6F
  ... truncated ...
```
