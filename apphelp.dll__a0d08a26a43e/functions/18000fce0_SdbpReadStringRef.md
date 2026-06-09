# SdbpReadStringRef

- ea: `0x18000fce0`
- end: `0x1800103ba`
- name: `SdbpReadStringRef`
- size: `1754`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009680`

## callees

- `0x18000ef24`
- `0x18000efe0`
- `0x18000f080`
- `0x18000f114`
- `0x18000fce0`
- `0x18005915d`

## string_xrefs

- `0x18000fe6e`: `SdbpReadMappedData`
- `0x18000ff07`: `SdbpReadMappedData`
- `0x18000ff95`: `SdbpReadMappedData`
- `0x180010080`: `SdbpReadMappedData`
- `0x18001023d`: `SdbpReadMappedData`
- `0x180010272`: `SdbpReadMappedData`
- `0x1800102af`: `SdbpReadMappedData`
- `0x18001039a`: `SdbpReadMappedData`
- `0x18000fe89`: `Error reading data`
- `0x18000ff36`: `Error reading data`
- `0x180010091`: `Error reading data`
- `0x18000ff5b`: `Error reading size data [%x]`
- `0x18000ffa6`: `Error reading size data [%x]`
- `0x18000ff43`: `SdbpReadStringRef`
- `0x180010005`: `SdbpReadStringRef`
- `0x180010318`: `Error reading tag`
- `0x18000ff25`: `SdbpReadTagData`
- `0x18001016f`: `SdbpReadTagData`
- `0x18000ff18`: `Error reading tag data`
- `0x18000fed2`: `Error reading size data`
- `0x1800102cf`: `Error reading size data`
- `0x180010230`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x180010266`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x1800102a0`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18001038f`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpReadStringRef(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  _DWORD *v5; // r14
  _QWORD *v6; // r12
  unsigned int v7; // r15d
  int v8; // r13d
  int v9; // ebp
  unsigned int v10; // esi
  unsigned int v11; // ecx
  unsigned int v12; // eax
  unsigned __int16 v14; // ax
  int v15; // ecx
  unsigned int TagFromTagID; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+18h] BYREF

  v2 = (unsigned int)a2;
  v17 = 0;
  v4 = (unsigned int)(a2 + 2);
  if ( (unsigned int)a2 >= 0xFFFFFFFE )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
    v5 = (_DWORD *)(a1 + 20);
LABEL_21:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    a2 = v2;
    v6 = (_QWORD *)(a1 + 8);
    goto LABEL_33;
  }
  v5 = (_DWORD *)(a1 + 20);
  if ( *(_DWORD *)(a1 + 20) < (unsigned int)v4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      a2,
      2,
      *(_DWORD *)(a1 + 20));
    goto LABEL_21;
  }
  v6 = (_QWORD *)(a1 + 8);
  a2 = (unsigned int)a2;
  if ( (*(_WORD *)((unsigned int)a2 + *(_QWORD *)(a1 + 8)) & 0xF000) == 0x6000 )
  {
    TagFromTagID = (unsigned __int16)SdbGetTagFromTagID(a1, (unsigned int)a2);
    v7 = TagFromTagID & 0xF000;
    v8 = 2;
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
    {
      v9 = 0x20000000;
      if ( v7 == 36864 )
        goto LABEL_6;
      if ( v7 == 20480 )
      {
        v10 = 8;
        goto LABEL_9;
      }
      if ( v7 > 0x5000 )
      {
        if ( v7 == 24576 )
        {
LABEL_52:
          v10 = 4;
          goto LABEL_9;
        }
        if ( v7 == 28672 || v7 == 0x8000 )
        {
LABEL_6:
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
            if ( *v5 >= (unsigned int)(v4 + 4) )
            {
              v10 = *(_DWORD *)(v4 + *v6);
LABEL_9:
              v11 = v10;
LABEL_10:
              if ( v11 + (unsigned int)v2 < v11 || v11 + (unsigned int)v2 > *v5 )
              {
                AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
                v10 = 0x20000000;
              }
              goto LABEL_12;
            }
            AslLogCallPrintf(
              1,
              "SdbpReadMappedData",
              860,
              "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
              v4,
              4,
              *v5);
          }
          v10 = 0x20000000;
          AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
          v11 = 0x20000000;
          goto LABEL_10;
        }
      }
      else
      {
        switch ( v7 )
        {
          case 0x1000u:
            v10 = 0;
            v11 = 0;
            goto LABEL_10;
          case 0x3000u:
            v10 = 2;
            v11 = 2;
            goto LABEL_10;
          case 0x2000u:
            v10 = 1;
            goto LABEL_9;
          case 0x4000u:
            goto LABEL_52;
        }
      }
      AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", TagFromTagID);
      goto LABEL_59;
    }
    switch ( v7 )
    {
      case 0x1000u:
        v10 = 0;
LABEL_24:
        if ( v10 + (unsigned int)v2 < v10 || v10 + (unsigned int)v2 > *v5 )
        {
          AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
          v10 = 0x20000000;
        }
LABEL_12:
        v9 = v10;
        if ( v10 <= 4 )
        {
          LOWORD(TagFromTagID) = 0;
          if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)v2, &TagFromTagID, 2) )
          {
            AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
            v8 = 0;
            goto LABEL_17;
          }
          if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
          {
            v15 = 6;
            if ( (TagFromTagID & 0xF000) < 0x7000 )
              v15 = 2;
            v8 = v15;
            goto LABEL_17;
          }
          v12 = TagFromTagID & 0xF000;
          if ( v12 == 36864 )
            goto LABEL_16;
          if ( v12 == 24576 )
            goto LABEL_17;
          if ( v12 > 0x4000 )
          {
            if ( v12 == 20480 )
              goto LABEL_17;
            if ( v12 == 28672 || v12 == 0x8000 )
            {
LABEL_16:
              v8 = 6;
LABEL_17:
              if ( (_DWORD)v2 + v8 + v10 < v10 )
              {
                AslLogCallPrintf(
                  1,
                  "SdbpReadMappedData",
                  855,
                  "Offset and region size add up to cause an integer overflow or underflow");
              }
              else
              {
                if ( *v5 >= (_DWORD)v2 + v8 + v10 )
                {
                  memcpy_0(&v17, (const void *)(*v6 + (unsigned int)(v2 + v8)), v10);
                  return v17;
                }
                AslLogCallPrintf(
                  1,
                  "SdbpReadMappedData",
                  860,
                  "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
                  v2 + v8,
                  v10,
                  *v5);
              }
              AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
              goto LABEL_29;
            }
          }
          else if ( v12 == 0x4000 || v12 == 4096 || v12 == 0x2000 || v12 == 12288 )
          {
            goto LABEL_17;
          }
          AslLogCallPrintf(
            1,
            "SdbpGetTagHeadSize",
            121,
            "Invalid TAG_TYPE encountered. TAG: [%x]",
            (unsigned __int16)TagFromTagID);
          v8 = 0;
          goto LABEL_17;
        }
LABEL_59:
        AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, v9);
LABEL_29:
        AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
        return 0;
      case 0x2000u:
        v10 = 1;
        goto LABEL_24;
      case 0x3000u:
        v10 = 2;
        goto LABEL_24;
    }
    if ( v7 != 0x4000 )
    {
      if ( v7 == 20480 )
      {
        v10 = 8;
        goto LABEL_24;
      }
      if ( v7 != 24576 )
      {
        TagFromTagID = 0;
        if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)v4, &TagFromTagID, 4) )
          AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
        v10 = TagFromTagID;
        goto LABEL_24;
      }
    }
    v10 = 4;
    goto LABEL_24;
  }
LABEL_33:
  if ( (unsigned int)v4 < 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_45:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    v14 = 0;
    goto LABEL_36;
  }
  if ( *v5 < (unsigned int)v4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v2,
      2,
      *v5);
    goto LABEL_45;
  }
  v14 = *(_WORD *)(a2 + *v6);
LABEL_36:
  AslLogCallPrintf(1, "SdbpReadStringRef", 634, "TagID 0x%08X, Tag %04X not STRINGREF type", v2, v14);
  return 0;
}

```

## disassembly

```asm
0x18000fce0  mov     r11, rsp
0x18000fce3  push    rbx
0x18000fce4  push    rbp
0x18000fce5  push    rsi
0x18000fce6  push    rdi
0x18000fce7  push    r12
0x18000fce9  push    r13
0x18000fceb  push    r14
0x18000fced  sub     rsp, 40h
0x18000fcf1  mov     ebx, edx
0x18000fcf3  mov     rdi, rcx
0x18000fcf6  mov     dword ptr [r11+18h], 0
0x18000fcfe  lea     esi, [rbx+2]
0x18000fd01  cmp     esi, 2
0x18000fd04  jb      loc_18000FE61
0x18000fd0a  mov     eax, [rcx+14h]
0x18000fd0d  lea     r14, [rcx+14h]
0x18000fd11  cmp     eax, esi
0x18000fd13  jb      loc_18001022C
0x18000fd19  mov     rax, [rcx+8]
0x18000fd1d  lea     r12, [rcx+8]
0x18000fd21  mov     ebp, 0F000h
0x18000fd26  mov     edx, ebx
0x18000fd28  movzx   ecx, word ptr [rbx+rax]
0x18000fd2c  mov     eax, 6000h
0x18000fd31  and     cx, bp
0x18000fd34  cmp     cx, ax
0x18000fd37  jnz     loc_18000FFD5
0x18000fd3d  mov     rcx, rdi
0x18000fd40  mov     [r11+8], r15
0x18000fd44  call    SdbGetTagFromTagID
0x18000fd49  movzx   eax, ax
0x18000fd4c  mov     r15d, eax
0x18000fd4f  mov     [rsp+78h+arg_8], eax
0x18000fd56  and     r15d, ebp
0x18000fd59  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000fd5e  mov     r13d, 2
0x18000fd64  test    eax, eax
0x18000fd66  jz      loc_18000FEB3
0x18000fd6c  mov     ebp, 20000000h
0x18000fd71  cmp     r15d, 9000h
0x18000fd78  jnz     loc_1800100B6
0x18000fd7e  lea     eax, [rsi+4]
0x18000fd81  cmp     eax, 4
0x18000fd84  jb      loc_18000FF88
0x18000fd8a  mov     ecx, [r14]
0x18000fd8d  cmp     ecx, eax
0x18000fd8f  jb      loc_18001029C
0x18000fd95  mov     rax, [r12]
0x18000fd99  mov     esi, [rsi+rax]
0x18000fd9c  mov     ecx, esi
0x18000fd9e  lea     eax, [rcx+rbx]
0x18000fda1  cmp     eax, ecx
0x18000fda3  jb      loc_18000FF5B
0x18000fda9  cmp     eax, [r14]
0x18000fdac  ja      loc_18000FF5B
0x18000fdb2  mov     ebp, esi
0x18000fdb4  cmp     esi, 4
0x18000fdb7  ja      loc_180010156
0x18000fdbd  xor     eax, eax
0x18000fdbf  lea     r8, [rsp+78h+arg_8]
0x18000fdc7  mov     r9d, r13d
0x18000fdca  mov     word ptr [rsp+78h+arg_8], ax
0x18000fdd2  mov     edx, ebx
0x18000fdd4  mov     rcx, rdi
0x18000fdd7  call    SdbpReadMappedData
0x18000fddc  test    eax, eax
0x18000fdde  jz      loc_180010318
0x18000fde4  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000fde9  mov     edx, 0F000h
0x18000fdee  test    eax, eax
0x18000fdf0  jz      loc_180010185
0x18000fdf6  movzx   ecx, word ptr [rsp+78h+arg_8]
0x18000fdfe  mov     eax, ecx
0x18000fe00  and     eax, edx
0x18000fe02  cmp     eax, 9000h
0x18000fe07  jnz     loc_180010031
0x18000fe0d  mov     r13d, 6
0x18000fe13  lea     eax, [rbx+r13]
0x18000fe17  lea     ecx, [rax+rbp]
0x18000fe1a  cmp     ecx, ebp
0x18000fe1c  jb      loc_18000FEFA
0x18000fe22  mov     edx, [r14]
0x18000fe25  cmp     edx, ecx
0x18000fe27  jb      loc_18001038B
0x18000fe2d  mov     edx, eax
0x18000fe2f  lea     rcx, [rsp+78h+arg_10]; void *
0x18000fe37  add     rdx, [r12]; Src
0x18000fe3b  mov     r8, rbp; Size
0x18000fe3e  call    memcpy_0
0x18000fe43  mov     eax, [rsp+78h+arg_10]
0x18000fe4a  mov     r15, [rsp+78h+arg_0]
0x18000fe52  add     rsp, 40h
0x18000fe56  pop     r14
0x18000fe58  pop     r13
0x18000fe5a  pop     r12
0x18000fe5c  pop     rdi
0x18000fe5d  pop     rsi
0x18000fe5e  pop     rbp
0x18000fe5f  pop     rbx
0x18000fe60  retn
0x18000fe61  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000fe68  mov     r8d, 357h
0x18000fe6e  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000fe75  mov     ecx, 1
0x18000fe7a  call    AslLogCallPrintf
0x18000fe7f  lea     r14, [rdi+14h]
0x18000fe83  mov     r13d, 2
0x18000fe89  lea     r9, aErrorReadingDa; "Error reading data"
0x18000fe90  mov     r8d, 0BDFh
0x18000fe96  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000fe9d  mov     ecx, 1
0x18000fea2  call    AslLogCallPrintf
0x18000fea7  mov     rdx, rbx
0x18000feaa  lea     r12, [rdi+8]
0x18000feae  jmp     loc_18000FFDB
0x18000feb3  cmp     r15d, 1000h
0x18000feba  jnz     loc_1800101B4
0x18000fec0  xor     esi, esi
0x18000fec2  lea     eax, [rsi+rbx]
0x18000fec5  cmp     eax, esi
0x18000fec7  jb      short loc_18000FED2
0x18000fec9  cmp     eax, [r14]
0x18000fecc  jbe     loc_18000FDB2
0x18000fed2  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000fed9  mov     r8d, 177h
0x18000fedf  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000fee6  mov     ecx, 1
0x18000feeb  call    AslLogCallPrintf
0x18000fef0  mov     esi, 20000000h
0x18000fef5  jmp     loc_18000FDB2
0x18000fefa  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000ff01  mov     r8d, 357h
0x18000ff07  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000ff0e  mov     ecx, 1
0x18000ff13  call    AslLogCallPrintf
0x18000ff18  lea     r9, aErrorReadingTa; "Error reading tag data"
0x18000ff1f  mov     r8d, 1BEh
0x18000ff25  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x18000ff2c  mov     ecx, 1
0x18000ff31  call    AslLogCallPrintf
0x18000ff36  lea     r9, aErrorReadingDa; "Error reading data"
0x18000ff3d  mov     r8d, 27Fh
0x18000ff43  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x18000ff4a  mov     ecx, 1
0x18000ff4f  call    AslLogCallPrintf
0x18000ff54  xor     eax, eax
0x18000ff56  jmp     loc_18000FE4A
0x18000ff5b  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000ff62  mov     [rsp+78h+var_58], 0C0000095h
0x18000ff6a  mov     r8d, 149h
0x18000ff70  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000ff77  mov     ecx, 1
0x18000ff7c  call    AslLogCallPrintf
0x18000ff81  mov     esi, ebp
0x18000ff83  jmp     loc_18000FDB2
0x18000ff88  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000ff8f  mov     r8d, 357h
0x18000ff95  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000ff9c  mov     ecx, 1
0x18000ffa1  call    AslLogCallPrintf
0x18000ffa6  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000ffad  mov     [rsp+78h+var_58], 0C0000023h
0x18000ffb5  mov     r8d, 137h
0x18000ffbb  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000ffc2  mov     ecx, 1
0x18000ffc7  mov     esi, ebp
0x18000ffc9  call    AslLogCallPrintf
0x18000ffce  mov     ecx, ebp
0x18000ffd0  jmp     loc_18000FD9E
0x18000ffd5  mov     r13d, 2
0x18000ffdb  cmp     esi, 2
0x18000ffde  jb      loc_180010073
0x18000ffe4  mov     eax, [r14]
0x18000ffe7  cmp     eax, esi
0x18000ffe9  jb      loc_180010262
0x18000ffef  mov     rax, [r12]
0x18000fff3  movzx   eax, word ptr [rdx+rax]
0x18000fff7  movzx   eax, ax
0x18000fffa  lea     r9, aTagid0x08xTag0; "TagID 0x%08X, Tag %04X not STRINGREF ty"...
0x180010001  mov     [rsp+78h+var_50], eax
0x180010005  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x18001000c  mov     r8d, 27Ah
0x180010012  mov     [rsp+78h+var_58], ebx
0x180010016  mov     ecx, 1
0x18001001b  call    AslLogCallPrintf
0x180010020  xor     eax, eax
0x180010022  add     rsp, 40h
0x180010026  pop     r14
0x180010028  pop     r13
0x18001002a  pop     r12
0x18001002c  pop     rdi
0x18001002d  pop     rsi
0x18001002e  pop     rbp
0x18001002f  pop     rbx
0x180010030  retn
0x180010031  cmp     eax, 6000h
0x180010036  jz      loc_18000FE13
0x18001003c  cmp     eax, 4000h
0x180010041  ja      loc_18001033E
0x180010047  jz      loc_18000FE13
0x18001004d  cmp     eax, 1000h
0x180010052  jz      loc_18000FE13
0x180010058  cmp     eax, 2000h
0x18001005d  jz      loc_18000FE13
0x180010063  cmp     eax, 3000h
0x180010068  jz      loc_18000FE13
0x18001006e  jmp     loc_180010361
0x180010073  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18001007a  mov     r8d, 357h
0x180010080  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180010087  mov     ecx, 1
0x18001008c  call    AslLogCallPrintf
0x180010091  lea     r9, aErrorReadingDa; "Error reading data"
0x180010098  mov     r8d, 0BDFh
0x18001009e  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x1800100a5  mov     ecx, 1
0x1800100aa  call    AslLogCallPrintf
0x1800100af  xor     eax, eax
0x1800100b1  jmp     loc_18000FFF7
0x1800100b6  cmp     r15d, 5000h
0x1800100bd  jz      short loc_1800100F7
0x1800100bf  ja      short loc_18001010A
0x1800100c1  cmp     r15d, 1000h
0x1800100c8  jz      short loc_180010101
0x1800100ca  cmp     r15d, 3000h
0x1800100d1  jz      loc_1800101A9
0x1800100d7  cmp     r15d, 2000h
0x1800100de  jz      loc_180010292
0x1800100e4  cmp     r15d, 4000h
0x1800100eb  jnz     short loc_18001012D
0x1800100ed  mov     esi, 4
0x1800100f2  jmp     loc_18000FD9C
0x1800100f7  mov     esi, 8
0x1800100fc  jmp     loc_18000FD9C
0x180010101  xor     esi, esi
0x180010103  xor     ecx, ecx
0x180010105  jmp     loc_18000FD9E
0x18001010a  cmp     r15d, 6000h
0x180010111  jz      short loc_1800100ED
0x180010113  cmp     r15d, 7000h
0x18001011a  jz      loc_18000FD7E
0x180010120  cmp     r15d, 8000h
0x180010127  jz      loc_18000FD7E
0x18001012d  mov     eax, [rsp+78h+arg_8]
0x180010134  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x18001013b  mov     r8d, 13Eh
0x180010141  mov     [rsp+78h+var_58], eax
0x180010145  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18001014c  mov     ecx, 1
0x180010151  call    AslLogCallPrintf
0x180010156  mov     [rsp+78h+var_50], ebp
0x18001015a  lea     r9, aBufferTooSmall_1; "Buffer too small. Avail: %d, Need: %d"
0x180010161  mov     r8d, 1B7h
0x180010167  mov     [rsp+78h+var_58], 4
0x18001016f  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x180010176  mov     ecx, 1
0x18001017b  call    AslLogCallPrintf
0x180010180  jmp     loc_18000FF36
0x180010185  movzx   eax, word ptr [rsp+78h+arg_8]
0x18001018d  mov     ecx, 6
0x180010192  and     ax, dx
0x180010195  mov     edx, 7000h
0x18001019a  cmp     ax, dx
0x18001019d  cmovb   ecx, r13d
0x1800101a1  mov     r13d, ecx
0x1800101a4  jmp     loc_18000FE13
0x1800101a9  mov     esi, r13d
0x1800101ac  mov     ecx, r13d
0x1800101af  jmp     loc_18000FD9E
0x1800101b4  cmp     r15d, 2000h
0x1800101bb  jz      loc_18001030E
0x1800101c1  cmp     r15d, 3000h
0x1800101c8  jz      loc_180010306
0x1800101ce  cmp     r15d, 4000h
0x1800101d5  jz      loc_1800102FC
0x1800101db  cmp     r15d, 5000h
0x1800101e2  jz      loc_1800102F2
0x1800101e8  cmp     r15d, 6000h
0x1800101ef  jz      loc_1800102FC
0x1800101f5  mov     r9d, 4
0x1800101fb  mov     [rsp+78h+arg_8], 0
0x180010206  lea     r8, [rsp+78h+arg_8]
0x18001020e  mov     edx, esi
0x180010210  mov     rcx, rdi
0x180010213  call    SdbpReadMappedData
0x180010218  test    eax, eax
0x18001021a  jz      loc_1800102CF
0x180010220  mov     esi, [rsp+78h+arg_8]
0x180010227  jmp     loc_18000FEC2
0x18001022c  mov     [rsp+78h+var_48], eax
0x180010230  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x180010237  mov     r13d, 2
0x18001023d  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180010244  mov     [rsp+78h+var_50], r13d
0x180010249  mov     r8d, 35Ch
0x18001024f  mov     ecx, 1
0x180010254  mov     [rsp+78h+var_58], ebx
0x180010258  call    AslLogCallPrintf
0x18001025d  jmp     loc_18000FE89
  ... truncated ...
```
