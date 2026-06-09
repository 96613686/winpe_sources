# SdbpReadTagData

- ea: `0x18000cf80`
- end: `0x18000d562`
- name: `SdbpReadTagData`
- size: `1506`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180009680`
- `0x18000bca0`
- `0x1800111b0`
- `0x180016590`
- `0x180026ca0`
- `0x18004c110`

## callees

- `0x18000cf80`
- `0x18000ef24`
- `0x18000f080`
- `0x18000f114`
- `0x18005915d`

## string_xrefs

- `0x18000d120`: `SdbpReadMappedData`
- `0x18000d163`: `SdbpReadMappedData`
- `0x18000d1af`: `SdbpReadMappedData`
- `0x18000d21f`: `SdbpReadMappedData`
- `0x18000d40e`: `SdbpReadMappedData`
- `0x18000d44c`: `SdbpReadMappedData`
- `0x18000d4c5`: `SdbpReadMappedData`
- `0x18000d542`: `SdbpReadMappedData`
- `0x18000d131`: `Error reading data`
- `0x18000d1e5`: `Error reading size data [%x]`
- `0x18000d230`: `Error reading size data [%x]`
- `0x18000d178`: `Error reading tag`
- `0x18000d1cd`: `SdbpReadTagData`
- `0x18000d377`: `SdbpReadTagData`
- `0x18000d1c0`: `Error reading tag data`
- `0x18000d0eb`: `Error reading size data`
- `0x18000d46c`: `Error reading size data`
- `0x18000d402`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000d43d`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000d4b9`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000d537`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpReadTagData(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 v4; // r15
  int v5; // r12d
  __int64 v8; // rbp
  unsigned __int16 v9; // ax
  int v10; // r14d
  unsigned int v11; // ebx
  unsigned int v12; // esi
  unsigned int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  _DWORD *v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // rdi
  int v19; // ebp
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // eax
  unsigned int v24; // [rsp+88h] [rbp+10h] BYREF
  void *v25; // [rsp+90h] [rbp+18h]

  v25 = a3;
  v4 = a2;
  v5 = 2;
  v8 = a2 + 2;
  if ( (unsigned int)v8 < 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
  }
  else
  {
    if ( *(_DWORD *)(a1 + 20) >= (unsigned int)v8 )
    {
      v9 = *(_WORD *)(a2 + *(_QWORD *)(a1 + 8));
      goto LABEL_4;
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
  v9 = 0;
LABEL_4:
  v10 = v9;
  v11 = v9 & 0xF000;
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    switch ( v11 )
    {
      case 0x1000u:
        v14 = 0;
LABEL_24:
        if ( v14 + (unsigned int)v4 < v14 || v14 + (unsigned int)v4 > *(_DWORD *)(a1 + 20) )
        {
          AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
          v14 = 0x20000000;
        }
        goto LABEL_12;
      case 0x2000u:
        v14 = 1;
        goto LABEL_24;
      case 0x3000u:
        v14 = 2;
        goto LABEL_24;
    }
    if ( v11 != 0x4000 )
    {
      if ( v11 == 20480 )
      {
        v14 = 8;
        goto LABEL_24;
      }
      if ( v11 != 24576 )
      {
        v24 = 0;
        if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)v8, &v24, 4) )
          AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
        v14 = v24;
        goto LABEL_24;
      }
    }
    v14 = 4;
    goto LABEL_24;
  }
  v12 = 0x20000000;
  if ( v11 == 36864 )
    goto LABEL_6;
  if ( v11 == 20480 )
  {
    v14 = 8;
    goto LABEL_9;
  }
  if ( v11 > 0x5000 )
  {
    if ( v11 == 24576 )
      goto LABEL_49;
    if ( v11 == 28672 || v11 == 0x8000 )
    {
LABEL_6:
      if ( (unsigned int)v8 >= 0xFFFFFFFC )
      {
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          855,
          "Offset and region size add up to cause an integer overflow or underflow");
      }
      else
      {
        v13 = *(_DWORD *)(a1 + 20);
        if ( v13 >= (int)v8 + 4 )
        {
          v14 = *(_DWORD *)(v8 + *(_QWORD *)(a1 + 8));
LABEL_9:
          v15 = v14;
LABEL_10:
          if ( v15 + (unsigned int)v4 < v15 || v15 + (unsigned int)v4 > *(_DWORD *)(a1 + 20) )
          {
            AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
            v14 = 0x20000000;
          }
LABEL_12:
          v12 = v14;
          goto LABEL_13;
        }
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          860,
          "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
          v8,
          4,
          v13);
      }
      v14 = 0x20000000;
      AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
      v15 = 0x20000000;
      goto LABEL_10;
    }
  }
  else
  {
    switch ( v11 )
    {
      case 0x1000u:
        v14 = 0;
        v15 = 0;
        goto LABEL_10;
      case 0x3000u:
        v14 = 2;
        v15 = 2;
        goto LABEL_10;
      case 0x2000u:
        v14 = 1;
        goto LABEL_9;
      case 0x4000u:
LABEL_49:
        v15 = 4;
        v14 = 4;
        goto LABEL_10;
    }
  }
  AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v10);
LABEL_13:
  if ( v12 > a4 )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", a4, v12);
    return 0;
  }
  if ( (unsigned int)v8 < 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
    v16 = (_DWORD *)(a1 + 20);
LABEL_30:
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v5 = 0;
    v18 = (_QWORD *)(a1 + 8);
    goto LABEL_19;
  }
  v16 = (_DWORD *)(a1 + 20);
  if ( *(_DWORD *)(a1 + 20) < (unsigned int)v8 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v4,
      2,
      *(_DWORD *)(a1 + 20));
    goto LABEL_30;
  }
  v17 = *(_QWORD *)(a1 + 8);
  v18 = (_QWORD *)(a1 + 8);
  v19 = *(unsigned __int16 *)(v4 + v17);
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v23 = 6;
    if ( (v19 & 0xF000u) < 0x7000 )
      v23 = 2;
    v5 = v23;
    goto LABEL_19;
  }
  v20 = v19 & 0xF000;
  if ( v20 != 36864 )
  {
    if ( v20 == 24576 )
      goto LABEL_19;
    if ( v20 > 0x4000 )
    {
      if ( v20 == 20480 )
        goto LABEL_19;
      if ( v20 == 28672 || v20 == 0x8000 )
        goto LABEL_18;
    }
    else if ( v20 == 0x4000 || v20 == 4096 || v20 == 0x2000 || v20 == 12288 )
    {
      goto LABEL_19;
    }
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v19);
    v5 = 0;
    goto LABEL_19;
  }
LABEL_18:
  v5 = 6;
LABEL_19:
  v21 = v5 + v4;
  if ( v5 + (_DWORD)v4 + v12 < v12 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
  }
  else
  {
    if ( *v16 >= v21 + v12 )
    {
      memcpy_0(v25, (const void *)(*v18 + v21), v12);
      return 1;
    }
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v5 + v4,
      v12,
      *v16);
  }
  AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
  return 0;
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp+arg_0], rbx
0x18000cf85  mov     [rsp+arg_10], r8
0x18000cf8a  push    rbp
0x18000cf8b  push    rsi
0x18000cf8c  push    rdi
0x18000cf8d  push    r12
0x18000cf8f  push    r13
0x18000cf91  push    r14
0x18000cf93  push    r15
0x18000cf95  sub     rsp, 40h
0x18000cf99  mov     r15d, edx
0x18000cf9c  mov     r12d, 2
0x18000cfa2  mov     r13d, r9d
0x18000cfa5  mov     rdi, rcx
0x18000cfa8  lea     ebp, [r15+2]
0x18000cfac  cmp     ebp, r12d
0x18000cfaf  jb      loc_18000D113
0x18000cfb5  mov     eax, [rcx+14h]
0x18000cfb8  cmp     eax, ebp
0x18000cfba  jb      loc_18000D3FE
0x18000cfc0  mov     rax, [rcx+8]
0x18000cfc4  movzx   eax, word ptr [r15+rax]
0x18000cfc9  movzx   r14d, ax
0x18000cfcd  mov     ebx, r14d
0x18000cfd0  and     ebx, 0F000h
0x18000cfd6  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000cfdb  test    eax, eax
0x18000cfdd  jz      loc_18000D0CC
0x18000cfe3  mov     esi, 20000000h
0x18000cfe8  cmp     ebx, 9000h
0x18000cfee  jnz     loc_18000D2A1
0x18000cff4  lea     eax, [rbp+4]
0x18000cff7  cmp     eax, 4
0x18000cffa  jb      loc_18000D212
0x18000d000  mov     ecx, [rdi+14h]
0x18000d003  cmp     ecx, eax
0x18000d005  jb      loc_18000D439
0x18000d00b  mov     rax, [rdi+8]
0x18000d00f  mov     ebx, [rbp+rax+0]
0x18000d013  mov     eax, ebx
0x18000d015  lea     ecx, [rax+r15]
0x18000d019  cmp     ecx, eax
0x18000d01b  jb      loc_18000D1E5
0x18000d021  cmp     ecx, [rdi+14h]
0x18000d024  ja      loc_18000D1E5
0x18000d02a  mov     esi, ebx
0x18000d02c  cmp     esi, r13d
0x18000d02f  ja      loc_18000D361
0x18000d035  cmp     ebp, r12d
0x18000d038  jb      loc_18000D156
0x18000d03e  mov     eax, [rdi+14h]
0x18000d041  lea     rbx, [rdi+14h]
0x18000d045  cmp     eax, ebp
0x18000d047  jb      loc_18000D4B5
0x18000d04d  mov     rax, [rdi+8]
0x18000d051  add     rdi, 8
0x18000d055  movzx   ebp, word ptr [r15+rax]
0x18000d05a  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000d05f  mov     edx, 0F000h
0x18000d064  test    eax, eax
0x18000d066  jz      loc_18000D33A
0x18000d06c  mov     eax, ebp
0x18000d06e  and     eax, edx
0x18000d070  cmp     eax, 9000h
0x18000d075  jnz     loc_18000D25F
0x18000d07b  mov     r12d, 6
0x18000d081  lea     eax, [r12+r15]
0x18000d085  lea     ecx, [rax+rsi]
0x18000d088  cmp     ecx, esi
0x18000d08a  jb      loc_18000D1A2
0x18000d090  mov     edx, [rbx]
0x18000d092  cmp     edx, ecx
0x18000d094  jb      loc_18000D533
0x18000d09a  mov     rcx, [rsp+78h+arg_10]; void *
0x18000d0a2  mov     edx, eax
0x18000d0a4  add     rdx, [rdi]; Src
0x18000d0a7  mov     r8d, esi; Size
0x18000d0aa  call    memcpy_0
0x18000d0af  mov     eax, 1
0x18000d0b4  mov     rbx, [rsp+78h+arg_0]
0x18000d0bc  add     rsp, 40h
0x18000d0c0  pop     r15
0x18000d0c2  pop     r14
0x18000d0c4  pop     r13
0x18000d0c6  pop     r12
0x18000d0c8  pop     rdi
0x18000d0c9  pop     rsi
0x18000d0ca  pop     rbp
0x18000d0cb  retn
0x18000d0cc  cmp     ebx, 1000h
0x18000d0d2  jnz     loc_18000D38F
0x18000d0d8  xor     ebx, ebx
0x18000d0da  lea     eax, [rbx+r15]
0x18000d0de  cmp     eax, ebx
0x18000d0e0  jb      short loc_18000D0EB
0x18000d0e2  cmp     eax, [rdi+14h]
0x18000d0e5  jbe     loc_18000D02A
0x18000d0eb  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000d0f2  mov     r8d, 177h
0x18000d0f8  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000d0ff  mov     ecx, 1
0x18000d104  call    AslLogCallPrintf
0x18000d109  mov     ebx, 20000000h
0x18000d10e  jmp     loc_18000D02A
0x18000d113  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000d11a  mov     r8d, 357h
0x18000d120  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d127  mov     ecx, 1
0x18000d12c  call    AslLogCallPrintf
0x18000d131  lea     r9, aErrorReadingDa; "Error reading data"
0x18000d138  mov     r8d, 0BDFh
0x18000d13e  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000d145  mov     ecx, 1
0x18000d14a  call    AslLogCallPrintf
0x18000d14f  xor     eax, eax
0x18000d151  jmp     loc_18000CFC9
0x18000d156  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000d15d  mov     r8d, 357h
0x18000d163  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d16a  mov     ecx, 1
0x18000d16f  call    AslLogCallPrintf
0x18000d174  lea     rbx, [rdi+14h]
0x18000d178  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x18000d17f  mov     r8d, 64h ; 'd'
0x18000d185  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x18000d18c  mov     ecx, 1
0x18000d191  call    AslLogCallPrintf
0x18000d196  xor     r12d, r12d
0x18000d199  add     rdi, 8
0x18000d19d  jmp     loc_18000D081
0x18000d1a2  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000d1a9  mov     r8d, 357h
0x18000d1af  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d1b6  mov     ecx, 1
0x18000d1bb  call    AslLogCallPrintf
0x18000d1c0  lea     r9, aErrorReadingTa; "Error reading tag data"
0x18000d1c7  mov     r8d, 1BEh
0x18000d1cd  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x18000d1d4  mov     ecx, 1
0x18000d1d9  call    AslLogCallPrintf
0x18000d1de  xor     eax, eax
0x18000d1e0  jmp     loc_18000D0B4
0x18000d1e5  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000d1ec  mov     [rsp+78h+var_58], 0C0000095h
0x18000d1f4  mov     r8d, 149h
0x18000d1fa  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000d201  mov     ecx, 1
0x18000d206  call    AslLogCallPrintf
0x18000d20b  mov     ebx, esi
0x18000d20d  jmp     loc_18000D02A
0x18000d212  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000d219  mov     r8d, 357h
0x18000d21f  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d226  mov     ecx, 1
0x18000d22b  call    AslLogCallPrintf
0x18000d230  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000d237  mov     [rsp+78h+var_58], 0C0000023h
0x18000d23f  mov     r8d, 137h
0x18000d245  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000d24c  mov     ecx, 1
0x18000d251  mov     ebx, esi
0x18000d253  call    AslLogCallPrintf
0x18000d258  mov     eax, esi
0x18000d25a  jmp     loc_18000D015
0x18000d25f  cmp     eax, 6000h
0x18000d264  jz      loc_18000D081
0x18000d26a  cmp     eax, 4000h
0x18000d26f  ja      loc_18000D4E6
0x18000d275  jz      loc_18000D081
0x18000d27b  cmp     eax, 1000h
0x18000d280  jz      loc_18000D081
0x18000d286  cmp     eax, 2000h
0x18000d28b  jz      loc_18000D081
0x18000d291  cmp     eax, 3000h
0x18000d296  jz      loc_18000D081
0x18000d29c  jmp     loc_18000D509
0x18000d2a1  cmp     ebx, 5000h
0x18000d2a7  jz      short loc_18000D2DF
0x18000d2a9  ja      short loc_18000D2F2
0x18000d2ab  cmp     ebx, 1000h
0x18000d2b1  jz      short loc_18000D2E9
0x18000d2b3  cmp     ebx, 3000h
0x18000d2b9  jz      loc_18000D356
0x18000d2bf  cmp     ebx, 2000h
0x18000d2c5  jz      loc_18000D42F
0x18000d2cb  cmp     ebx, 4000h
0x18000d2d1  jnz     short loc_18000D312
0x18000d2d3  mov     eax, 4
0x18000d2d8  mov     ebx, eax
0x18000d2da  jmp     loc_18000D015
0x18000d2df  mov     ebx, 8
0x18000d2e4  jmp     loc_18000D013
0x18000d2e9  xor     ebx, ebx
0x18000d2eb  xor     eax, eax
0x18000d2ed  jmp     loc_18000D015
0x18000d2f2  cmp     ebx, 6000h
0x18000d2f8  jz      short loc_18000D2D3
0x18000d2fa  cmp     ebx, 7000h
0x18000d300  jz      loc_18000CFF4
0x18000d306  cmp     ebx, 8000h
0x18000d30c  jz      loc_18000CFF4
0x18000d312  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x18000d319  mov     [rsp+78h+var_58], r14d
0x18000d31e  mov     r8d, 13Eh
0x18000d324  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000d32b  mov     ecx, 1
0x18000d330  call    AslLogCallPrintf
0x18000d335  jmp     loc_18000D02C
0x18000d33a  and     bp, dx
0x18000d33d  mov     eax, 6
0x18000d342  mov     edx, 7000h
0x18000d347  cmp     bp, dx
0x18000d34a  cmovb   eax, r12d
0x18000d34e  mov     r12d, eax
0x18000d351  jmp     loc_18000D081
0x18000d356  mov     ebx, r12d
0x18000d359  mov     eax, r12d
0x18000d35c  jmp     loc_18000D015
0x18000d361  mov     [rsp+78h+var_50], esi
0x18000d365  lea     r9, aBufferTooSmall_1; "Buffer too small. Avail: %d, Need: %d"
0x18000d36c  mov     r8d, 1B7h
0x18000d372  mov     [rsp+78h+var_58], r13d
0x18000d377  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x18000d37e  mov     ecx, 1
0x18000d383  call    AslLogCallPrintf
0x18000d388  xor     eax, eax
0x18000d38a  jmp     loc_18000D0B4
0x18000d38f  cmp     ebx, 2000h
0x18000d395  jz      loc_18000D4AB
0x18000d39b  cmp     ebx, 3000h
0x18000d3a1  jz      loc_18000D4A3
0x18000d3a7  cmp     ebx, 4000h
0x18000d3ad  jz      loc_18000D499
0x18000d3b3  cmp     ebx, 5000h
0x18000d3b9  jz      loc_18000D48F
0x18000d3bf  cmp     ebx, 6000h
0x18000d3c5  jz      loc_18000D499
0x18000d3cb  mov     r9d, 4
0x18000d3d1  mov     [rsp+78h+arg_8], 0
0x18000d3dc  lea     r8, [rsp+78h+arg_8]
0x18000d3e4  mov     edx, ebp
0x18000d3e6  mov     rcx, rdi
0x18000d3e9  call    SdbpReadMappedData
0x18000d3ee  test    eax, eax
0x18000d3f0  jz      short loc_18000D46C
0x18000d3f2  mov     ebx, [rsp+78h+arg_8]
0x18000d3f9  jmp     loc_18000D0DA
0x18000d3fe  mov     [rsp+78h+var_48], eax
0x18000d402  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x18000d409  mov     [rsp+78h+var_50], r12d
0x18000d40e  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d415  mov     r8d, 35Ch
0x18000d41b  mov     [rsp+78h+var_58], r15d
0x18000d420  mov     ecx, 1
0x18000d425  call    AslLogCallPrintf
0x18000d42a  jmp     loc_18000D131
0x18000d42f  mov     ebx, 1
0x18000d434  jmp     loc_18000D013
0x18000d439  mov     [rsp+78h+var_48], ecx
0x18000d43d  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x18000d444  mov     [rsp+78h+var_50], 4
0x18000d44c  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d453  mov     ecx, 1
0x18000d458  mov     [rsp+78h+var_58], ebp
0x18000d45c  mov     r8d, 35Ch
0x18000d462  call    AslLogCallPrintf
0x18000d467  jmp     loc_18000D230
0x18000d46c  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000d473  mov     r8d, 16Ch
0x18000d479  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000d480  mov     ecx, 1
0x18000d485  call    AslLogCallPrintf
0x18000d48a  jmp     loc_18000D3F2
0x18000d48f  mov     ebx, 8
0x18000d494  jmp     loc_18000D0DA
0x18000d499  mov     ebx, 4
0x18000d49e  jmp     loc_18000D0DA
0x18000d4a3  mov     ebx, r12d
0x18000d4a6  jmp     loc_18000D0DA
0x18000d4ab  mov     ebx, 1
0x18000d4b0  jmp     loc_18000D0DA
0x18000d4b5  mov     [rsp+78h+var_48], eax
0x18000d4b9  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x18000d4c0  mov     [rsp+78h+var_50], r12d
0x18000d4c5  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d4cc  mov     r8d, 35Ch
0x18000d4d2  mov     [rsp+78h+var_58], r15d
0x18000d4d7  mov     ecx, 1
0x18000d4dc  call    AslLogCallPrintf
0x18000d4e1  jmp     loc_18000D178
0x18000d4e6  cmp     eax, 5000h
0x18000d4eb  jz      loc_18000D081
0x18000d4f1  mov     edx, 7000h
0x18000d4f6  cmp     eax, edx
0x18000d4f8  jz      loc_18000D07B
0x18000d4fe  cmp     eax, 8000h
0x18000d503  jz      loc_18000D07B
0x18000d509  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x18000d510  mov     [rsp+78h+var_58], ebp
0x18000d514  mov     r8d, 79h ; 'y'
  ... truncated ...
```
