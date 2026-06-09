# SdbGetStringTagPtr

- ea: `0x18000f150`
- end: `0x18000fac6`
- name: `SdbGetStringTagPtr`
- size: `2422`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `55`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005f14`
- `0x18000607c`
- `0x180006c20`
- `0x180007e94`
- `0x180008474`
- `0x180008a80`
- `0x180009468`
- `0x18000a23c`
- `0x18000b42c`
- `0x18000b7f8`
- `0x18000c160`
- `0x18000c43c`
- `0x18001108c`
- `0x180011be0`
- `0x180011e74`
- `0x18001e198`
- `0x18001ebc8`
- `0x18001f7f8`
- `0x180026180`
- `0x1800264d0`
- `0x180026790`
- `0x18002d86c`
- `0x18002eb8c`
- `0x180035800`
- `0x180036308`
- `0x180038240`
- `0x180038978`
- `0x18003acf4`
- `0x18004034c`
- `0x180040650`
- `0x180041adc`
- `0x180042b6c`
- `0x180042ee4`
- `0x1800449e0`
- `0x180044b60`
- `0x1800455b8`
- `0x1800458f4`
- `0x18004609c`
- `0x180046364`
- `0x180046400`
- `0x1800478c0`
- `0x180048000`
- `0x180049140`
- `0x180049c30`
- `0x18004adf0`
- `0x18004cfa0`
- `0x18004d730`
- `0x18004da50`
- `0x18004db50`
- `0x18004dc10`

## callees

- `0x18000ef24`
- `0x18000efe0`
- `0x18000f080`
- `0x18000f114`
- `0x18000f150`
- `0x180010db0`
- `0x18005915d`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18000f330`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000f330`

## string_xrefs

- `0x18000f376`: `SdbpReadMappedData`
- `0x18000f3d2`: `SdbpReadMappedData`
- `0x18000f4d5`: `SdbpReadMappedData`
- `0x18000f5e7`: `SdbpReadMappedData`
- `0x18000f63f`: `SdbpReadMappedData`
- `0x18000f87c`: `SdbpReadMappedData`
- `0x18000f8be`: `SdbpReadMappedData`
- `0x18000f916`: `SdbpReadMappedData`
- `0x18000f956`: `SdbpReadMappedData`
- `0x18000fa76`: `SdbpReadMappedData`
- `0x18000faa5`: `SdbpReadMappedData`
- `0x18000f387`: `Error reading data`
- `0x18000f3e3`: `Error reading data`
- `0x18000f504`: `Error reading data`
- `0x18000f650`: `Error reading data`
- `0x18000f8d9`: `Error reading data`
- `0x18000f585`: `Error reading size data [%x]`
- `0x18000f5f8`: `Error reading size data [%x]`
- `0x18000f511`: `SdbpReadStringRef`
- `0x18000f545`: `SdbpReadStringRef`
- `0x18000f9c5`: `Error reading tag`
- `0x18000f4f3`: `SdbpReadTagData`
- `0x18000f778`: `SdbpReadTagData`
- `0x18000f4e6`: `Error reading tag data`
- `0x18000f49f`: `Error reading size data`
- `0x18000f976`: `Error reading size data`
- `0x18000f86d`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000f8af`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000f907`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000f947`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000fa6a`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000fa9a`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbGetStringTagPtr(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int16 v5; // dx
  __int64 v6; // rbx
  unsigned int v7; // eax
  _QWORD *v8; // r13
  __int64 v9; // rdx
  unsigned int v10; // r12d
  int v11; // r15d
  unsigned int v12; // ecx
  unsigned int v13; // r12d
  unsigned int v14; // ecx
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // edx
  int v19; // esi
  int v20; // eax
  __int64 v21; // r8
  unsigned int v22; // ecx
  _DWORD *v24; // [rsp+80h] [rbp+8h] BYREF
  int v25; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  v3 = a1;
  if ( a1 )
  {
    v4 = a2 + 2;
    if ( a2 >= 0xFFFFFFFE )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
    }
    else
    {
      if ( *(_DWORD *)(a1 + 20) >= (unsigned int)v4 )
      {
        v5 = *(_WORD *)(a2 + *(_QWORD *)(a1 + 8)) & 0xF000;
        if ( v5 == (__int16)0x8000 )
          return SdbpGetMappedTagData(a1, (unsigned int)v2);
        v6 = 0;
        if ( v5 == 24576 )
        {
          v7 = *(_DWORD *)(a1 + 20);
          v25 = 0;
          if ( v7 < (unsigned int)v4 )
          {
            AslLogCallPrintf(
              1,
              "SdbpReadMappedData",
              860,
              "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
              v2,
              2,
              v7);
            AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
            v9 = v2;
            v8 = (_QWORD *)(v3 + 8);
          }
          else
          {
            v8 = (_QWORD *)(a1 + 8);
            v9 = (unsigned int)v2;
            if ( (*(_WORD *)(v2 + *(_QWORD *)(a1 + 8)) & 0xF000) == 0x6000 )
            {
              LODWORD(v24) = (unsigned __int16)SdbGetTagFromTagID(a1, (unsigned int)v2);
              v10 = (unsigned __int16)v24 & 0xF000;
              if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
              {
                v11 = 0x20000000;
                if ( v10 == 36864 )
                  goto LABEL_10;
                if ( v10 == 20480 )
                {
                  v13 = 8;
                  goto LABEL_13;
                }
                if ( v10 > 0x5000 )
                {
                  if ( v10 == 24576 )
                  {
LABEL_69:
                    v14 = 4;
                    v13 = 4;
                    goto LABEL_14;
                  }
                  if ( v10 == 28672 || v10 == 0x8000 )
                  {
LABEL_10:
                    if ( (unsigned int)v4 >= 0xFFFFFFFC )
                    {
                      AslLogCallPrintf(
                        1,
                        "SdbpReadMappedData",
                        855,
                        "Offset and region size add up to cause an integer overflow or underflow");
                    }
                    else
                    {
                      v12 = *(_DWORD *)(v3 + 20);
                      if ( v12 >= (int)v2 + 6 )
                      {
                        v13 = *(_DWORD *)(v4 + *v8);
LABEL_13:
                        v14 = v13;
LABEL_14:
                        if ( v14 + (unsigned int)v2 < v14 || v14 + (unsigned int)v2 > *(_DWORD *)(v3 + 20) )
                        {
                          AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
                          v13 = 0x20000000;
                        }
                        goto LABEL_16;
                      }
                      AslLogCallPrintf(
                        1,
                        "SdbpReadMappedData",
                        860,
                        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
                        v2 + 2,
                        4,
                        v12);
                    }
                    v13 = 0x20000000;
                    AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
                    v14 = 0x20000000;
                    goto LABEL_14;
                  }
                }
                else
                {
                  switch ( v10 )
                  {
                    case 0x1000u:
                      v13 = 0;
                      v14 = 0;
                      goto LABEL_14;
                    case 0x3000u:
                      v14 = 2;
                      v13 = 2;
                      goto LABEL_14;
                    case 0x2000u:
                      v14 = 1;
                      v13 = 1;
                      goto LABEL_14;
                    case 0x4000u:
                      goto LABEL_69;
                  }
                }
                AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", (_DWORD)v24);
                goto LABEL_77;
              }
              switch ( v10 )
              {
                case 0x1000u:
                  v13 = 0;
LABEL_43:
                  if ( v13 + (unsigned int)v2 < v13 || v13 + (unsigned int)v2 > *(_DWORD *)(v3 + 20) )
                  {
                    AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
                    v13 = 0x20000000;
                  }
LABEL_16:
                  v11 = v13;
                  if ( v13 <= 4 )
                  {
                    LOWORD(v24) = 0;
                    if ( !(unsigned int)SdbpReadMappedData(v3, (unsigned int)v2, &v24, 2) )
                    {
                      AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
                      v16 = 0;
                      goto LABEL_21;
                    }
                    if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
                    {
                      v16 = 6;
                      if ( ((unsigned __int16)v24 & 0xF000u) < 0x7000 )
                        v16 = 2;
                      goto LABEL_21;
                    }
                    v15 = (unsigned __int16)v24 & 0xF000;
                    if ( v15 == 36864 )
                      goto LABEL_20;
                    if ( v15 == 24576 )
                    {
LABEL_61:
                      v16 = 2;
                      goto LABEL_21;
                    }
                    if ( v15 > 0x4000 )
                    {
                      if ( v15 == 20480 )
                        goto LABEL_61;
                      if ( v15 == 28672 || v15 == 0x8000 )
                      {
LABEL_20:
                        v16 = 6;
LABEL_21:
                        v17 = v2 + v16;
                        if ( v17 + v13 < v13 )
                        {
                          AslLogCallPrintf(
                            1,
                            "SdbpReadMappedData",
                            855,
                            "Offset and region size add up to cause an integer overflow or underflow");
                        }
                        else
                        {
                          v18 = *(_DWORD *)(v3 + 20);
                          if ( v18 >= v17 + v13 )
                          {
                            memcpy_0(&v25, (const void *)(*v8 + v17), v13);
                            v19 = v25;
                            if ( v25 )
                            {
                              v24 = 0;
                              if ( *(_DWORD *)(v3 + 16) )
                              {
                                v3 = *(_QWORD *)(v3 + 2640);
                                if ( !v3 )
                                {
                                  AslLogCallPrintf(
                                    1,
                                    "SdbpGetStringTableItemFromStringRef",
                                    838,
                                    "No stringtable in DB");
                                  goto LABEL_39;
                                }
                                v21 = (unsigned int)(v25 + 6);
                              }
                              else
                              {
                                v20 = RtlRunOnceExecuteOnce(v3 + 2624, InitOnceGetStringTableOffset, v3, &v24);
                                if ( v20 < 0 )
                                {
                                  AslLogCallPrintf(
                                    1,
                                    "SdbpGetStringTableItemFromStringRef",
                                    858,
                                    "RtlRunOnceExecuteOnce failed for InitOnceGetStringTableOffset [%x]",
                                    v20);
                                  goto LABEL_39;
                                }
                                if ( !v24 || !*v24 )
                                {
                                  AslLogCallPrintf(
                                    1,
                                    "SdbpGetStringTableItemFromStringRef",
                                    874,
                                    "InitOnceGetStringTableOffset succeeded but failed to find string table");
                                  goto LABEL_39;
                                }
                                v21 = (unsigned int)(*v24 + v19);
                              }
                              if ( (unsigned int)(v21 + 2) >= 2 )
                              {
                                v22 = *(_DWORD *)(v3 + 20);
                                if ( v22 >= (int)v21 + 2 )
                                {
                                  if ( *(_WORD *)(v21 + *(_QWORD *)(v3 + 8)) == 0x8801 )
                                  {
                                    if ( (_DWORD)v21 && v3 )
                                      return SdbpGetMappedTagData(v3, (unsigned int)v21);
                                    goto LABEL_39;
                                  }
                                  goto LABEL_32;
                                }
                                AslLogCallPrintf(
                                  1,
                                  "SdbpReadMappedData",
                                  860,
                                  "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
                                  v21,
                                  2,
                                  v22);
                              }
                              else
                              {
                                AslLogCallPrintf(
                                  1,
                                  "SdbpReadMappedData",
                                  855,
                                  "Offset and region size add up to cause an integer overflow or underflow");
                              }
                              AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
LABEL_32:
                              AslLogCallPrintf(
                                1,
                                "SdbpGetStringTableItemFromStringRef",
                                888,
                                "Pulled out a non-stringtable item");
LABEL_39:
                              AslLogCallPrintf(
                                1,
                                "SdbpGetMappedStringFromTable",
                                977,
                                "SdbpGetStringTableItemFromStringRef failed to get tagid for string ref");
                              return v6;
                            }
                            goto LABEL_52;
                          }
                          AslLogCallPrintf(
                            1,
                            "SdbpReadMappedData",
                            860,
                            "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
                            v17,
                            v13,
                            v18);
                        }
                        AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
                        goto LABEL_48;
                      }
                    }
                    else if ( v15 == 0x4000 || v15 == 4096 || v15 == 0x2000 || v15 == 12288 )
                    {
                      goto LABEL_61;
                    }
                    AslLogCallPrintf(
                      1,
                      "SdbpGetTagHeadSize",
                      121,
                      "Invalid TAG_TYPE encountered. TAG: [%x]",
                      (unsigned __int16)v24);
                    v16 = 0;
                    goto LABEL_21;
                  }
LABEL_77:
                  AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, v11);
LABEL_48:
                  AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
LABEL_52:
                  AslLogCallPrintf(1, "SdbGetStringTagPtr", 742, "Error getting StringRef");
                  return 0;
                case 0x2000u:
                  v13 = 1;
                  goto LABEL_43;
                case 0x3000u:
                  v13 = 2;
                  goto LABEL_43;
              }
              if ( v10 != 0x4000 )
              {
                if ( v10 == 20480 )
                {
                  v13 = 8;
                  goto LABEL_43;
                }
                if ( v10 != 24576 )
                {
                  LODWORD(v24) = 0;
                  if ( !(unsigned int)SdbpReadMappedData(v3, (unsigned int)v4, &v24, 4) )
                    AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
                  v13 = (unsigned int)v24;
                  goto LABEL_43;
                }
              }
              v13 = 4;
              goto LABEL_43;
            }
          }
          if ( (unsigned int)v4 >= 2 )
          {
            if ( *(_DWORD *)(v3 + 20) >= (unsigned int)v4 )
            {
              LOWORD(v6) = *(_WORD *)(v9 + *v8);
LABEL_51:
              AslLogCallPrintf(
                1,
                "SdbpReadStringRef",
                634,
                "TagID 0x%08X, Tag %04X not STRINGREF type",
                v2,
                (unsigned __int16)v6);
              goto LABEL_52;
            }
            AslLogCallPrintf(
              1,
              "SdbpReadMappedData",
              860,
              "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
              v2,
              2,
              *(_DWORD *)(v3 + 20));
          }
          else
          {
            AslLogCallPrintf(
              1,
              "SdbpReadMappedData",
              855,
              "Offset and region size add up to cause an integer overflow or underflow");
          }
          AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
          goto LABEL_51;
        }
        return v6;
      }
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        a2,
        2,
        *(_DWORD *)(a1 + 20));
    }
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    return 0;
  }
  AslLogCallPrintf(1, "SdbGetStringTagPtr", 722, "Invalid pdb");
  return 0;
}

```

## disassembly

```asm
0x18000f150  mov     r11, rsp
0x18000f153  push    rsi
0x18000f154  push    rdi
0x18000f155  sub     rsp, 68h
0x18000f159  mov     esi, edx
0x18000f15b  mov     rdi, rcx
0x18000f15e  test    rcx, rcx
0x18000f161  jz      loc_18000F6E1
0x18000f167  mov     [r11+10h], rbx
0x18000f16b  mov     [r11-18h], rbp
0x18000f16f  lea     ebp, [rsi+2]
0x18000f172  mov     [r11-20h], r12
0x18000f176  mov     [r11-28h], r13
0x18000f17a  mov     [r11-30h], r14
0x18000f17e  mov     [r11-38h], r15
0x18000f182  cmp     ebp, 2
0x18000f185  jb      loc_18000F3C5
0x18000f18b  mov     eax, [rcx+14h]
0x18000f18e  cmp     eax, ebp
0x18000f190  jb      loc_18000F869
0x18000f196  mov     rax, [rcx+8]
0x18000f19a  mov     r15d, 0F000h
0x18000f1a0  movzx   edx, word ptr [rsi+rax]
0x18000f1a4  mov     eax, 8000h
0x18000f1a9  and     dx, r15w
0x18000f1ad  cmp     dx, ax
0x18000f1b0  jz      loc_18000F89C
0x18000f1b6  xor     ebx, ebx
0x18000f1b8  mov     r8d, 6000h
0x18000f1be  cmp     dx, r8w
0x18000f1c2  jnz     loc_18000F452
0x18000f1c8  mov     eax, [rcx+14h]
0x18000f1cb  mov     [r11+18h], ebx
0x18000f1cf  cmp     eax, ebp
0x18000f1d1  jb      loc_18000F8AB
0x18000f1d7  mov     rax, [rcx+8]
0x18000f1db  lea     r13, [rcx+8]
0x18000f1df  mov     edx, esi
0x18000f1e1  movzx   ecx, word ptr [rsi+rax]
0x18000f1e5  and     cx, r15w
0x18000f1e9  cmp     cx, r8w
0x18000f1ed  jnz     loc_18000F629
0x18000f1f3  mov     rcx, rdi
0x18000f1f6  call    SdbGetTagFromTagID
0x18000f1fb  movzx   eax, ax
0x18000f1fe  mov     r12d, eax
0x18000f201  mov     dword ptr [rsp+78h+arg_0], eax
0x18000f208  and     r12d, r15d
0x18000f20b  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000f210  test    eax, eax
0x18000f212  jz      loc_18000F47D
0x18000f218  mov     r15d, 20000000h
0x18000f21e  cmp     r12d, 9000h
0x18000f225  jnz     loc_18000F692
0x18000f22b  lea     eax, [rbp+4]
0x18000f22e  cmp     eax, 4
0x18000f231  jb      loc_18000F5DA
0x18000f237  mov     ecx, [rdi+14h]
0x18000f23a  cmp     ecx, eax
0x18000f23c  jb      loc_18000F943
0x18000f242  mov     rax, [r13+0]
0x18000f246  mov     r12d, [rbp+rax+0]
0x18000f24b  mov     ecx, r12d
0x18000f24e  lea     eax, [rcx+rsi]
0x18000f251  cmp     eax, ecx
0x18000f253  jb      loc_18000F585
0x18000f259  cmp     eax, [rdi+14h]
0x18000f25c  ja      loc_18000F585
0x18000f262  mov     r15d, r12d
0x18000f265  cmp     r12d, 4
0x18000f269  ja      loc_18000F75E
0x18000f26f  mov     ebp, 2
0x18000f274  mov     word ptr [rsp+78h+arg_0], bx
0x18000f27c  mov     r9d, ebp
0x18000f27f  lea     r8, [rsp+78h+arg_0]
0x18000f287  mov     edx, esi
0x18000f289  mov     rcx, rdi
0x18000f28c  call    SdbpReadMappedData
0x18000f291  test    eax, eax
0x18000f293  jz      loc_18000F9C5
0x18000f299  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000f29e  mov     edx, 0F000h
0x18000f2a3  test    eax, eax
0x18000f2a5  jz      loc_18000F78E
0x18000f2ab  movzx   ecx, word ptr [rsp+78h+arg_0]
0x18000f2b3  mov     eax, ecx
0x18000f2b5  and     eax, edx
0x18000f2b7  cmp     eax, 9000h
0x18000f2bc  jnz     loc_18000F673
0x18000f2c2  mov     ecx, 6
0x18000f2c7  add     ecx, esi
0x18000f2c9  lea     eax, [rcx+r15]
0x18000f2cd  cmp     eax, r15d
0x18000f2d0  jb      loc_18000F4C8
0x18000f2d6  mov     edx, [rdi+14h]
0x18000f2d9  cmp     edx, eax
0x18000f2db  jb      loc_18000FA66
0x18000f2e1  mov     edx, ecx
0x18000f2e3  mov     r8, r15; Size
0x18000f2e6  add     rdx, [r13+0]; Src
0x18000f2ea  lea     rcx, [rsp+78h+arg_10]; void *
0x18000f2f2  call    memcpy_0
0x18000f2f7  mov     esi, [rsp+78h+arg_10]
0x18000f2fe  test    esi, esi
0x18000f300  jz      loc_18000F560
0x18000f306  mov     [rsp+78h+arg_0], rbx
0x18000f30e  cmp     [rdi+10h], ebx
0x18000f311  jnz     loc_18000F842
0x18000f317  lea     rcx, [rdi+0A40h]
0x18000f31e  mov     r8, rdi
0x18000f321  lea     r9, [rsp+78h+arg_0]
0x18000f329  lea     rdx, InitOnceGetStringTableOffset
0x18000f330  call    cs:__imp_RtlRunOnceExecuteOnce
0x18000f336  test    eax, eax
0x18000f338  js      loc_18000F5B3
0x18000f33e  mov     rax, [rsp+78h+arg_0]
0x18000f346  test    rax, rax
0x18000f349  jz      loc_18000F7BB
0x18000f34f  mov     ecx, [rax]
0x18000f351  test    ecx, ecx
0x18000f353  jz      loc_18000F7BB
0x18000f359  lea     r8d, [rcx+rsi]
0x18000f35d  lea     eax, [r8+2]
0x18000f361  cmp     eax, ebp
0x18000f363  jnb     loc_18000F405
0x18000f369  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000f370  mov     r8d, 357h
0x18000f376  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000f37d  mov     ecx, 1
0x18000f382  call    AslLogCallPrintf
0x18000f387  lea     r9, aErrorReadingDa; "Error reading data"
0x18000f38e  mov     r8d, 0BDFh
0x18000f394  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000f39b  mov     ecx, 1
0x18000f3a0  call    AslLogCallPrintf
0x18000f3a5  lea     r9, aPulledOutANonS; "Pulled out a non-stringtable item"
0x18000f3ac  mov     r8d, 378h
0x18000f3b2  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x18000f3b9  mov     ecx, 1
0x18000f3be  call    AslLogCallPrintf
0x18000f3c3  jmp     short loc_18000F434
0x18000f3c5  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000f3cc  mov     r8d, 357h
0x18000f3d2  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000f3d9  mov     ecx, 1
0x18000f3de  call    AslLogCallPrintf
0x18000f3e3  lea     r9, aErrorReadingDa; "Error reading data"
0x18000f3ea  mov     r8d, 0BDFh
0x18000f3f0  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000f3f7  mov     ecx, 1
0x18000f3fc  call    AslLogCallPrintf
0x18000f401  xor     ebx, ebx
0x18000f403  jmp     short loc_18000F452
0x18000f405  mov     ecx, [rdi+14h]
0x18000f408  cmp     ecx, eax
0x18000f40a  jb      loc_18000FA96
0x18000f410  mov     rax, [rdi+8]
0x18000f414  mov     edx, 8801h
0x18000f419  cmp     [r8+rax], dx
0x18000f41e  jnz     short loc_18000F3A5
0x18000f420  mov     rcx, rdi
0x18000f423  mov     edx, r8d
0x18000f426  test    r8d, r8d
0x18000f429  jz      short loc_18000F434
0x18000f42b  test    rcx, rcx
0x18000f42e  jnz     loc_18000F685
0x18000f434  lea     r9, aSdbpgetstringt; "SdbpGetStringTableItemFromStringRef fai"...
0x18000f43b  mov     r8d, 3D1h
0x18000f441  lea     rdx, aSdbpgetmappeds; "SdbpGetMappedStringFromTable"
0x18000f448  mov     ecx, 1
0x18000f44d  call    AslLogCallPrintf
0x18000f452  mov     rax, rbx
0x18000f455  mov     r14, [rsp+78h+var_30]
0x18000f45a  mov     r13, [rsp+78h+var_28]
0x18000f45f  mov     r12, [rsp+78h+var_20]
0x18000f464  mov     rbp, [rsp+78h+var_18]
0x18000f469  mov     rbx, [rsp+78h+arg_8]
0x18000f471  mov     r15, [rsp+78h+var_38]
0x18000f476  add     rsp, 68h
0x18000f47a  pop     rdi
0x18000f47b  pop     rsi
0x18000f47c  retn
0x18000f47d  cmp     r12d, 1000h
0x18000f484  jnz     loc_18000F7CD
0x18000f48a  mov     r12d, ebx
0x18000f48d  lea     eax, [r12+rsi]
0x18000f491  cmp     eax, r12d
0x18000f494  jb      short loc_18000F49F
0x18000f496  cmp     eax, [rdi+14h]
0x18000f499  jbe     loc_18000F262
0x18000f49f  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000f4a6  mov     r8d, 177h
0x18000f4ac  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000f4b3  mov     ecx, 1
0x18000f4b8  call    AslLogCallPrintf
0x18000f4bd  mov     r12d, 20000000h
0x18000f4c3  jmp     loc_18000F262
0x18000f4c8  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000f4cf  mov     r8d, 357h
0x18000f4d5  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000f4dc  mov     ecx, 1
0x18000f4e1  call    AslLogCallPrintf
0x18000f4e6  lea     r9, aErrorReadingTa; "Error reading tag data"
0x18000f4ed  mov     r8d, 1BEh
0x18000f4f3  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x18000f4fa  mov     ecx, 1
0x18000f4ff  call    AslLogCallPrintf
0x18000f504  lea     r9, aErrorReadingDa; "Error reading data"
0x18000f50b  mov     r8d, 27Fh
0x18000f511  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x18000f518  mov     ecx, 1
0x18000f51d  call    AslLogCallPrintf
0x18000f522  jmp     short loc_18000F560
0x18000f524  mov     eax, [rdi+14h]
0x18000f527  cmp     eax, ebp
0x18000f529  jb      loc_18000F903
0x18000f52f  mov     rax, [r13+0]
0x18000f533  movzx   ebx, word ptr [rdx+rax]
0x18000f537  movzx   eax, bx
0x18000f53a  lea     r9, aTagid0x08xTag0; "TagID 0x%08X, Tag %04X not STRINGREF ty"...
0x18000f541  mov     [rsp+78h+var_50], eax
0x18000f545  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x18000f54c  mov     r8d, 27Ah
0x18000f552  mov     [rsp+78h+var_58], esi
0x18000f556  mov     ecx, 1
0x18000f55b  call    AslLogCallPrintf
0x18000f560  lea     r9, aErrorGettingSt; "Error getting StringRef"
0x18000f567  mov     r8d, 2E6h
0x18000f56d  lea     rdx, aSdbgetstringta_0; "SdbGetStringTagPtr"
0x18000f574  mov     ecx, 1
0x18000f579  call    AslLogCallPrintf
0x18000f57e  xor     eax, eax
0x18000f580  jmp     loc_18000F455
0x18000f585  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000f58c  mov     [rsp+78h+var_58], 0C0000095h
0x18000f594  mov     r8d, 149h
0x18000f59a  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000f5a1  mov     ecx, 1
0x18000f5a6  call    AslLogCallPrintf
0x18000f5ab  mov     r12d, r15d
0x18000f5ae  jmp     loc_18000F262
0x18000f5b3  lea     r9, aRtlrunonceexec_0; "RtlRunOnceExecuteOnce failed for InitOn"...
0x18000f5ba  mov     [rsp+78h+var_58], eax
0x18000f5be  mov     r8d, 35Ah
0x18000f5c4  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x18000f5cb  mov     ecx, 1
0x18000f5d0  call    AslLogCallPrintf
0x18000f5d5  jmp     loc_18000F434
0x18000f5da  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000f5e1  mov     r8d, 357h
0x18000f5e7  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000f5ee  mov     ecx, 1
0x18000f5f3  call    AslLogCallPrintf
0x18000f5f8  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000f5ff  mov     [rsp+78h+var_58], 0C0000023h
0x18000f607  mov     r8d, 137h
0x18000f60d  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000f614  mov     ecx, 1
0x18000f619  mov     r12d, r15d
0x18000f61c  call    AslLogCallPrintf
0x18000f621  mov     ecx, r15d
0x18000f624  jmp     loc_18000F24E
0x18000f629  cmp     ebp, 2
0x18000f62c  jnb     loc_18000F524
0x18000f632  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000f639  mov     r8d, 357h
0x18000f63f  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000f646  mov     ecx, 1
0x18000f64b  call    AslLogCallPrintf
0x18000f650  lea     r9, aErrorReadingDa; "Error reading data"
0x18000f657  mov     r8d, 0BDFh
0x18000f65d  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000f664  mov     ecx, 1
0x18000f669  call    AslLogCallPrintf
0x18000f66e  jmp     loc_18000F537
0x18000f673  cmp     eax, 6000h
0x18000f678  jnz     loc_18000F9EA
0x18000f67e  mov     ecx, ebp
0x18000f680  jmp     loc_18000F2C7
0x18000f685  call    SdbpGetMappedTagData
0x18000f68a  mov     rbx, rax
0x18000f68d  jmp     loc_18000F452
0x18000f692  cmp     r12d, 5000h
0x18000f699  jz      short loc_18000F6D6
0x18000f69b  ja      short loc_18000F712
0x18000f69d  cmp     r12d, 1000h
0x18000f6a4  jz      short loc_18000F708
0x18000f6a6  cmp     r12d, 3000h
0x18000f6ad  jz      loc_18000F7AE
0x18000f6b3  cmp     r12d, 2000h
0x18000f6ba  jz      loc_18000F936
0x18000f6c0  cmp     r12d, 4000h
0x18000f6c7  jnz     short loc_18000F735
0x18000f6c9  mov     ecx, 4
0x18000f6ce  mov     r12d, ecx
0x18000f6d1  jmp     loc_18000F24E
0x18000f6d6  mov     r12d, 8
0x18000f6dc  jmp     loc_18000F24B
0x18000f6e1  lea     r9, aInvalidPdb; "Invalid pdb"
0x18000f6e8  mov     r8d, 2D2h
  ... truncated ...
```
