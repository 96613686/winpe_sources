# SdbpValidateAndApplyCompatFlags

- ea: `0x14002e3b8`
- end: `0x14002e4c3`
- name: `SdbpValidateAndApplyCompatFlags`
- size: `267`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002e118`
- `0x140042ad4`

## callees

- `0x1400055d4`
- `0x14002e3b8`
- `0x14002e4cc`
- `0x14003d820`
- `0x14003e364`
- `0x140040730`

## string_xrefs

- `0x14002e3fe`: `SdbpValidateAndApplyCompatFlags`
- `0x14002e44c`: `SdbpValidateAndApplyCompatFlags`
- `0x14002e47c`: `SdbpValidateAndApplyCompatFlags`

## pseudocode

```c
__int64 __fastcall SdbpValidateAndApplyCompatFlags(__int64 a1, _DWORD *a2, char a3)
{
  unsigned int v4; // edi
  int v6; // eax

  v4 = 0;
  if ( *a2 == 1 )
  {
    *(_DWORD *)(a1 + 2608) |= 1u;
    goto LABEL_7;
  }
  if ( *a2 == 2 )
  {
LABEL_7:
    *(_DWORD *)(a1 + 2608) |= 2u;
    goto LABEL_8;
  }
  if ( *a2 != 3 && (a3 & 1) == 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpValidateAndApplyCompatFlags",
      981,
      "MajorVersion mismatch, MajorVersion [0x%lx] Expected 0x%lx",
      *a2,
      3);
    return v4;
  }
LABEL_8:
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && (v6 = SdbpValidateRootTagSizes(a1), v6 < 0) )
  {
    AslLogCallPrintf(
      1,
      "SdbpValidateAndApplyCompatFlags",
      992,
      "SdbpValidateRootTagSizes failed to validate SDB [%x]",
      v6);
  }
  else
  {
    if ( (unsigned int)SdbGetDatabaseID(a1, a1 + 28) )
      return 1;
    AslLogCallPrintf(1, "SdbpValidateAndApplyCompatFlags", 1005, "Failed to get the database ID");
    if ( (a3 & 8) == 0 && ((a3 & 4) == 0 || (unsigned int)SdbFindFirstTag(a1, 0, 28673)) )
      return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x14002e3b8  mov     [rsp+arg_0], rbx
0x14002e3bd  mov     [rsp+arg_8], rsi
0x14002e3c2  push    rdi
0x14002e3c3  sub     rsp, 30h
0x14002e3c7  mov     esi, r8d
0x14002e3ca  xor     edi, edi
0x14002e3cc  mov     r8d, [rdx]
0x14002e3cf  mov     rbx, rcx
0x14002e3d2  mov     eax, r8d
0x14002e3d5  sub     eax, 1
0x14002e3d8  jz      short loc_14002E418
0x14002e3da  sub     eax, 1
0x14002e3dd  jz      short loc_14002E41F
0x14002e3df  cmp     eax, 1
0x14002e3e2  jz      short loc_14002E426
0x14002e3e4  test    sil, 1
0x14002e3e8  jnz     short loc_14002E426
0x14002e3ea  mov     [rsp+38h+var_10], 3
0x14002e3f2  lea     r9, aMajorversionMi; "MajorVersion mismatch, MajorVersion [0x"...
0x14002e3f9  mov     [rsp+38h+var_18], r8d
0x14002e3fe  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x14002e405  mov     r8d, 3D5h
0x14002e40b  lea     ecx, [rdi+1]
0x14002e40e  call    AslLogCallPrintf
0x14002e413  jmp     loc_14002E4B0
0x14002e418  or      dword ptr [rcx+0A30h], 1
0x14002e41f  or      dword ptr [rcx+0A30h], 2
0x14002e426  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14002e42b  test    eax, eax
0x14002e42d  jz      short loc_14002E45F
0x14002e42f  mov     rcx, rbx
0x14002e432  call    SdbpValidateRootTagSizes
0x14002e437  test    eax, eax
0x14002e439  jns     short loc_14002E45F
0x14002e43b  lea     r9, aSdbpvalidatero; "SdbpValidateRootTagSizes failed to vali"...
0x14002e442  mov     [rsp+38h+var_18], eax
0x14002e446  mov     r8d, 3E0h
0x14002e44c  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x14002e453  mov     ecx, 1
0x14002e458  call    AslLogCallPrintf
0x14002e45d  jmp     short loc_14002E4B0
0x14002e45f  lea     rdx, [rbx+1Ch]
0x14002e463  mov     rcx, rbx
0x14002e466  call    SdbGetDatabaseID
0x14002e46b  test    eax, eax
0x14002e46d  jnz     short loc_14002E4AB
0x14002e46f  lea     r9, aFailedToGetThe; "Failed to get the database ID"
0x14002e476  mov     r8d, 3EDh
0x14002e47c  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x14002e483  lea     ecx, [rax+1]
0x14002e486  call    AslLogCallPrintf
0x14002e48b  test    sil, 8
0x14002e48f  jnz     short loc_14002E4B0
0x14002e491  test    sil, 4
0x14002e495  jz      short loc_14002E4AB
0x14002e497  xor     edx, edx
0x14002e499  mov     r8d, 7001h
0x14002e49f  mov     rcx, rbx
0x14002e4a2  call    SdbFindFirstTag
0x14002e4a7  test    eax, eax
0x14002e4a9  jz      short loc_14002E4B0
0x14002e4ab  mov     edi, 1
0x14002e4b0  mov     rbx, [rsp+38h+arg_0]
0x14002e4b5  mov     eax, edi
0x14002e4b7  mov     rsi, [rsp+38h+arg_8]
0x14002e4bc  add     rsp, 30h
0x14002e4c0  pop     rdi
0x14002e4c1  retn
```
