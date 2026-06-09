# SdbpGetRegistryMatchingAttributes

- ea: `0x18002d86c`
- end: `0x18002db9d`
- name: `SdbpGetRegistryMatchingAttributes`
- size: `817`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002d740`
- `0x18004e1e0`

## callees

- `0x18000beb0`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180011240`
- `0x180022b10`
- `0x180026ca0`
- `0x18002d86c`

## string_xrefs

- `0x18002d8ec`: `Failed to get key path tag`
- `0x18002db72`: `SdbpGetRegistryMatchingAttributes`
- `0x18002db65`: `Failed to read key path`
- `0x18002d980`: `Failed to read value type`
- `0x18002dae5`: `Failed to read value data`
- `0x18002db56`: `Failed to read value data`
- `0x18002d9c0`: `Unknown registry value type`
- `0x18002db0e`: `Failed to read value data size`

## pseudocode

```c
__int64 __fastcall SdbpGetRegistryMatchingAttributes(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        _DWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        __int64 *a8,
        __int64 *a9,
        _QWORD *a10)
{
  __int64 TagDataSize; // r14
  unsigned int v11; // edi
  unsigned int v13; // ebp
  unsigned int FirstTag; // eax
  _WORD *StringTagPtr; // rax
  _WORD *v16; // rsi
  int v17; // r15d
  __int64 v18; // r13
  __int64 BinaryTagData; // r12
  unsigned int v20; // eax
  unsigned int v21; // eax
  int DWORDTag; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // eax
  __int64 QWORDTag; // rax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // edi
  unsigned int v33; // eax
  int v35; // [rsp+20h] [rbp-58h]
  __int64 v36; // [rsp+30h] [rbp-48h]

  TagDataSize = 0;
  *a3 = 0;
  v11 = a2;
  *a4 = 0;
  v13 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( FirstTag )
  {
    StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, FirstTag);
    v16 = StringTagPtr;
    if ( !StringTagPtr || !*StringTagPtr )
    {
      AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1054, "Failed to read key path");
      return v13;
    }
    v36 = 0;
    v35 = 0;
    v17 = 0;
    v18 = 0;
    BinaryTagData = 0;
    v20 = SdbFindFirstTag(a1, v11, 24624);
    if ( v20 )
      v36 = SdbGetStringTagPtr(a1, v20);
    v21 = SdbFindFirstTag(a1, v11, 16465);
    if ( v21 )
    {
      DWORDTag = SdbReadDWORDTag(a1, v21, 0);
      v17 = DWORDTag;
      if ( !DWORDTag )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1073, "Failed to read value type", 0);
        return v13;
      }
      v23 = DWORDTag - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( !v25 )
          {
            v31 = SdbFindFirstTag(a1, v11, 36882);
            v32 = v31;
            if ( !v31 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1120,
                "Failed to get TAG_REG_VALUE_DATA_BINARY",
                0);
              return v13;
            }
            BinaryTagData = SdbGetBinaryTagData(a1, v31);
            if ( !BinaryTagData )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1126, "Failed to read value data", 0);
              return v13;
            }
            TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v32);
            if ( TagDataSize == 0x20000000 )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1132, "Failed to read value data size", 0);
              return v13;
            }
            goto LABEL_23;
          }
          v26 = v25 - 1;
          if ( !v26 )
          {
            v30 = SdbFindFirstTag(a1, v11, 16466);
            if ( !v30 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1100,
                "Failed to get TAG_REG_VALUE_DATA_DWORD",
                0);
              return v13;
            }
            v35 = SdbReadDWORDTag(a1, v30, 0);
            goto LABEL_23;
          }
          v27 = v26 - 3;
          if ( v27 )
          {
            if ( v27 != 4 )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1138, "Unknown registry value type", 0);
              return v13;
            }
            v28 = SdbFindFirstTag(a1, v11, 20507);
            if ( !v28 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1110,
                "Failed to get TAG_REG_VALUE_DATA_QWORD",
                0);
              return v13;
            }
            QWORDTag = SdbReadQWORDTag(a1, v28, 0);
LABEL_24:
            v13 = 1;
            *a3 = v16;
            *a4 = v36;
            *a5 = v17;
            *a6 = v18;
            *a7 = v35;
            *a8 = QWORDTag;
            *a9 = BinaryTagData;
            *a10 = TagDataSize;
            return v13;
          }
        }
      }
      v33 = SdbFindFirstTag(a1, v11, 24625);
      if ( !v33 )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1086, "Failed to get TAG_REG_VALUE_DATA_SZ", 0);
        return v13;
      }
      v18 = SdbGetStringTagPtr(a1, v33);
      if ( !v18 )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1092, "Failed to read value data", 0);
        return v13;
      }
    }
LABEL_23:
    QWORDTag = 0;
    goto LABEL_24;
  }
  AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1042, "Failed to get key path tag");
  return v13;
}

```

## disassembly

```asm
0x18002d86c  mov     [rsp+arg_0], rbx
0x18002d871  mov     [rsp+arg_18], r9
0x18002d876  mov     [rsp+arg_10], r8
0x18002d87b  push    rbp
0x18002d87c  push    rsi
0x18002d87d  push    rdi
0x18002d87e  push    r12
0x18002d880  push    r13
0x18002d882  push    r14
0x18002d884  push    r15
0x18002d886  sub     rsp, 40h
0x18002d88a  mov     rax, [rsp+78h+arg_20]
0x18002d892  xor     r14d, r14d
0x18002d895  mov     [r8], r14
0x18002d898  mov     edi, edx
0x18002d89a  mov     r8d, 6001h
0x18002d8a0  mov     [r9], r14
0x18002d8a3  mov     rbx, rcx
0x18002d8a6  mov     ebp, r14d
0x18002d8a9  mov     [rax], r14d
0x18002d8ac  mov     rax, [rsp+78h+arg_28]
0x18002d8b4  mov     [rax], r14
0x18002d8b7  mov     rax, [rsp+78h+arg_30]
0x18002d8bf  mov     [rax], r14d
0x18002d8c2  mov     rax, [rsp+78h+arg_38]
0x18002d8ca  mov     [rax], r14
0x18002d8cd  mov     rax, [rsp+78h+arg_40]
0x18002d8d5  mov     [rax], r14
0x18002d8d8  mov     rax, [rsp+78h+arg_48]
0x18002d8e0  mov     [rax], r14
0x18002d8e3  call    SdbFindFirstTag
0x18002d8e8  test    eax, eax
0x18002d8ea  jnz     short loc_18002D8FE
0x18002d8ec  lea     r9, aFailedToGetKey; "Failed to get key path tag"
0x18002d8f3  mov     r8d, 412h
0x18002d8f9  jmp     loc_18002DB72
0x18002d8fe  mov     edx, eax
0x18002d900  mov     rcx, rbx
0x18002d903  call    SdbGetStringTagPtr
0x18002d908  mov     rsi, rax
0x18002d90b  test    rax, rax
0x18002d90e  jz      loc_18002DB65
0x18002d914  cmp     [rax], r14w
0x18002d918  jz      loc_18002DB65
0x18002d91e  mov     r8d, 6030h
0x18002d924  mov     [rsp+78h+var_48], r14
0x18002d929  mov     edx, edi
0x18002d92b  mov     [rsp+78h+var_58], r14d
0x18002d930  mov     rcx, rbx
0x18002d933  mov     r15d, r14d
0x18002d936  mov     r13, r14
0x18002d939  mov     r12, r14
0x18002d93c  call    SdbFindFirstTag
0x18002d941  test    eax, eax
0x18002d943  jz      short loc_18002D954
0x18002d945  mov     edx, eax
0x18002d947  mov     rcx, rbx
0x18002d94a  call    SdbGetStringTagPtr
0x18002d94f  mov     [rsp+78h+var_48], rax
0x18002d954  mov     r8d, 4051h
0x18002d95a  mov     edx, edi
0x18002d95c  mov     rcx, rbx
0x18002d95f  call    SdbFindFirstTag
0x18002d964  test    eax, eax
0x18002d966  jz      loc_18002DA3E
0x18002d96c  xor     r8d, r8d
0x18002d96f  mov     edx, eax
0x18002d971  mov     rcx, rbx
0x18002d974  call    SdbReadDWORDTag
0x18002d979  mov     r15d, eax
0x18002d97c  test    eax, eax
0x18002d97e  jnz     short loc_18002D992
0x18002d980  lea     r9, aFailedToReadVa_1; "Failed to read value type"
0x18002d987  mov     r8d, 431h
0x18002d98d  jmp     loc_18002DB72
0x18002d992  sub     eax, 1
0x18002d995  jz      loc_18002DB1D
0x18002d99b  sub     eax, 1
0x18002d99e  jz      loc_18002DB1D
0x18002d9a4  sub     eax, 1
0x18002d9a7  jz      loc_18002DAAB
0x18002d9ad  sub     eax, 1
0x18002d9b0  jz      short loc_18002DA07
0x18002d9b2  sub     eax, 3
0x18002d9b5  jz      loc_18002DB1D
0x18002d9bb  cmp     eax, 4
0x18002d9be  jz      short loc_18002D9D2
0x18002d9c0  lea     r9, aUnknownRegistr_0; "Unknown registry value type"
0x18002d9c7  mov     r8d, 472h
0x18002d9cd  jmp     loc_18002DB72
0x18002d9d2  mov     r8d, 501Bh
0x18002d9d8  mov     edx, edi
0x18002d9da  mov     rcx, rbx
0x18002d9dd  call    SdbFindFirstTag
0x18002d9e2  test    eax, eax
0x18002d9e4  jnz     short loc_18002D9F8
0x18002d9e6  lea     r9, aFailedToGetTag_2; "Failed to get TAG_REG_VALUE_DATA_QWORD"
0x18002d9ed  mov     r8d, 456h
0x18002d9f3  jmp     loc_18002DB72
0x18002d9f8  xor     r8d, r8d
0x18002d9fb  mov     edx, eax
0x18002d9fd  mov     rcx, rbx
0x18002da00  call    SdbReadQWORDTag
0x18002da05  jmp     short loc_18002DA41
0x18002da07  mov     r8d, 4052h
0x18002da0d  mov     edx, edi
0x18002da0f  mov     rcx, rbx
0x18002da12  call    SdbFindFirstTag
0x18002da17  test    eax, eax
0x18002da19  jnz     short loc_18002DA2D
0x18002da1b  lea     r9, aFailedToGetTag_5; "Failed to get TAG_REG_VALUE_DATA_DWORD"
0x18002da22  mov     r8d, 44Ch
0x18002da28  jmp     loc_18002DB72
0x18002da2d  xor     r8d, r8d
0x18002da30  mov     edx, eax
0x18002da32  mov     rcx, rbx
0x18002da35  call    SdbReadDWORDTag
0x18002da3a  mov     [rsp+78h+var_58], eax
0x18002da3e  mov     rax, rbp
0x18002da41  mov     rcx, [rsp+78h+arg_10]
0x18002da49  mov     ebp, 1
0x18002da4e  mov     rdx, [rsp+78h+arg_18]
0x18002da56  mov     [rcx], rsi
0x18002da59  mov     rcx, [rsp+78h+var_48]
0x18002da5e  mov     [rdx], rcx
0x18002da61  mov     rcx, [rsp+78h+arg_20]
0x18002da69  mov     rdx, [rsp+78h+arg_30]
0x18002da71  mov     [rcx], r15d
0x18002da74  mov     rcx, [rsp+78h+arg_28]
0x18002da7c  mov     [rcx], r13
0x18002da7f  mov     ecx, [rsp+78h+var_58]
0x18002da83  mov     [rdx], ecx
0x18002da85  mov     rcx, [rsp+78h+arg_38]
0x18002da8d  mov     [rcx], rax
0x18002da90  mov     rax, [rsp+78h+arg_40]
0x18002da98  mov     [rax], r12
0x18002da9b  mov     rax, [rsp+78h+arg_48]
0x18002daa3  mov     [rax], r14
0x18002daa6  jmp     loc_18002DB83
0x18002daab  mov     r8d, 9012h
0x18002dab1  mov     edx, edi
0x18002dab3  mov     rcx, rbx
0x18002dab6  call    SdbFindFirstTag
0x18002dabb  mov     edi, eax
0x18002dabd  test    eax, eax
0x18002dabf  jnz     short loc_18002DAD3
0x18002dac1  lea     r9, aFailedToGetTag; "Failed to get TAG_REG_VALUE_DATA_BINARY"
0x18002dac8  mov     r8d, 460h
0x18002dace  jmp     loc_18002DB72
0x18002dad3  mov     edx, edi
0x18002dad5  mov     rcx, rbx
0x18002dad8  call    SdbGetBinaryTagData
0x18002dadd  mov     r12, rax
0x18002dae0  test    rax, rax
0x18002dae3  jnz     short loc_18002DAF4
0x18002dae5  lea     r9, aFailedToReadVa_4; "Failed to read value data"
0x18002daec  mov     r8d, 466h
0x18002daf2  jmp     short loc_18002DB72
0x18002daf4  mov     edx, edi
0x18002daf6  mov     rcx, rbx
0x18002daf9  call    SdbGetTagDataSize
0x18002dafe  mov     r14d, eax
0x18002db01  cmp     r14, 20000000h
0x18002db08  jnz     loc_18002DA3E
0x18002db0e  lea     r9, aFailedToReadVa_3; "Failed to read value data size"
0x18002db15  mov     r8d, 46Ch
0x18002db1b  jmp     short loc_18002DB72
0x18002db1d  mov     r8d, 6031h
0x18002db23  mov     edx, edi
0x18002db25  mov     rcx, rbx
0x18002db28  call    SdbFindFirstTag
0x18002db2d  test    eax, eax
0x18002db2f  jnz     short loc_18002DB40
0x18002db31  lea     r9, aFailedToGetTag_6; "Failed to get TAG_REG_VALUE_DATA_SZ"
0x18002db38  mov     r8d, 43Eh
0x18002db3e  jmp     short loc_18002DB72
0x18002db40  mov     edx, eax
0x18002db42  mov     rcx, rbx
0x18002db45  call    SdbGetStringTagPtr
0x18002db4a  mov     r13, rax
0x18002db4d  test    rax, rax
0x18002db50  jnz     loc_18002DA3E
0x18002db56  lea     r9, aFailedToReadVa_4; "Failed to read value data"
0x18002db5d  mov     r8d, 444h
0x18002db63  jmp     short loc_18002DB72
0x18002db65  lea     r9, aFailedToReadKe; "Failed to read key path"
0x18002db6c  mov     r8d, 41Eh
0x18002db72  lea     rdx, aSdbpgetregistr; "SdbpGetRegistryMatchingAttributes"
0x18002db79  mov     ecx, 1
0x18002db7e  call    AslLogCallPrintf
0x18002db83  mov     rbx, [rsp+78h+arg_0]
0x18002db8b  mov     eax, ebp
0x18002db8d  add     rsp, 40h
0x18002db91  pop     r15
0x18002db93  pop     r14
0x18002db95  pop     r13
0x18002db97  pop     r12
0x18002db99  pop     rdi
0x18002db9a  pop     rsi
0x18002db9b  pop     rbp
0x18002db9c  retn
```
