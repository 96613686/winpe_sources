# SdbReadDWORDTag

- ea: `0x180022b10`
- end: `0x180023095`
- name: `SdbReadDWORDTag`
- size: `1413`
- prototype: ``
- caller_count: `27`
- callee_count: `6`
- tags: ``

## callers

- `0x18000607c`
- `0x180006c20`
- `0x180007020`
- `0x18000b7f8`
- `0x180016348`
- `0x18001e198`
- `0x180022640`
- `0x1800227b0`
- `0x1800228a0`
- `0x180026790`
- `0x18002d86c`
- `0x180038978`
- `0x180042b6c`
- `0x180042ee4`
- `0x1800449e0`
- `0x180044b60`
- `0x1800455b8`
- `0x180045f90`
- `0x180046254`
- `0x180047ca8`
- `0x18004961c`
- `0x180049d1c`
- `0x18004cfa0`
- `0x18004d730`
- `0x18004da50`
- `0x18004e3e0`
- `0x18004e5d4`

## callees

- `0x18000ef24`
- `0x18000efe0`
- `0x18000f080`
- `0x18000f114`
- `0x180022b10`
- `0x18005921d`

## string_xrefs

- `0x180022ccd`: `SdbpReadMappedData`
- `0x180022d3c`: `SdbpReadMappedData`
- `0x180022da8`: `SdbpReadMappedData`
- `0x180022f80`: `SdbpReadMappedData`
- `0x180022fb3`: `SdbpReadMappedData`
- `0x180023078`: `SdbpReadMappedData`
- `0x180022cdb`: `Error reading data`
- `0x180022d71`: `Error reading size data [%x]`
- `0x180022db6`: `Error reading size data [%x]`
- `0x180023011`: `Error reading tag`
- `0x180022d57`: `SdbpReadTagData`
- `0x180022f5e`: `SdbpReadTagData`
- `0x180022d4a`: `Error reading tag data`
- `0x180022e6b`: `Error reading size data`
- `0x180022fd2`: `Error reading size data`
- `0x180022d0f`: `SdbReadDWORDTag`
- `0x180022f75`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x180022fa2`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18002306d`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbReadDWORDTag(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // r14
  int v7; // esi
  int v8; // r12d
  int v9; // edi
  size_t v10; // rbp
  unsigned int v11; // ecx
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // ecx
  unsigned __int16 TagFromTagID; // ax
  unsigned int v17; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+18h]
  unsigned int v19; // [rsp+98h] [rbp+20h] BYREF

  v18 = a3;
  v19 = a3;
  v6 = a2 + 2;
  v7 = 2;
  if ( a2 >= 0xFFFFFFFE )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_26:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_27;
  }
  if ( *(_DWORD *)(a1 + 20) < (unsigned int)v6 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      a2,
      2,
      *(_DWORD *)(a1 + 20));
    goto LABEL_26;
  }
  if ( (*(_WORD *)(a2 + *(_QWORD *)(a1 + 8)) & 0xF000) != 0x4000 )
  {
LABEL_27:
    TagFromTagID = SdbGetTagFromTagID(a1, a2);
    AslLogCallPrintf(1, "SdbReadDWORDTag", 179, "TagID 0x%X, Tag 0x%X not of the expected type", a2, TagFromTagID);
    return a3;
  }
  v8 = (unsigned __int16)SdbGetTagFromTagID(a1, a2);
  v9 = v8 & 0xF000;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    LODWORD(v10) = 0x20000000;
    if ( v9 != 36864 )
    {
      switch ( v9 )
      {
        case 16384:
          goto LABEL_35;
        case 20480:
          v12 = 8;
          goto LABEL_9;
        case 4096:
          v12 = 0;
          goto LABEL_9;
        case 24576:
LABEL_35:
          v12 = 4;
          goto LABEL_9;
        case 12288:
          v12 = 2;
          goto LABEL_9;
        case 8192:
          v12 = 1;
          goto LABEL_9;
      }
      if ( v9 != 28672 && v9 != 0x8000 )
      {
        AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v8);
        goto LABEL_61;
      }
    }
    if ( (unsigned int)(v6 + 4) < 4 )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
    }
    else
    {
      v11 = *(_DWORD *)(a1 + 20);
      if ( v11 >= (int)v6 + 4 )
      {
        v12 = *(_DWORD *)(v6 + *(_QWORD *)(a1 + 8));
LABEL_9:
        if ( v12 + a2 < v12 || v12 + a2 > *(_DWORD *)(a1 + 20) )
        {
          AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
          v12 = 0x20000000;
        }
        goto LABEL_11;
      }
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v6,
        4,
        v11);
    }
    AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
    v12 = 0x20000000;
    goto LABEL_9;
  }
  if ( v9 != 4096 )
  {
    if ( v9 == 0x2000 )
    {
      v12 = 1;
      goto LABEL_46;
    }
    if ( v9 == 12288 )
    {
      v12 = 2;
      goto LABEL_46;
    }
    if ( v9 != 0x4000 )
    {
      if ( v9 == 20480 )
      {
        v12 = 8;
        goto LABEL_46;
      }
      if ( v9 != 24576 )
      {
        v17 = 0;
        if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)v6, &v17, 4) )
          AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
        v12 = v17;
        goto LABEL_46;
      }
    }
    v12 = 4;
    goto LABEL_46;
  }
  v12 = 0;
LABEL_46:
  if ( v12 + a2 < v12 || v12 + a2 > *(_DWORD *)(a1 + 20) )
  {
    AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
    v12 = 0x20000000;
  }
LABEL_11:
  v10 = v12;
  if ( v12 <= 4 )
  {
    LOWORD(v17) = 0;
    if ( (unsigned int)SdbpReadMappedData(a1, a2, &v17, 2) )
    {
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
      {
        v13 = v17 & 0xF000;
        if ( v13 == 24576 || v13 == 4096 || v13 == 0x2000 || v13 == 12288 || v13 == 0x4000 || v13 == 20480 )
          goto LABEL_22;
        if ( v13 != 36864 && v13 != 28672 && v13 != 0x8000 )
        {
          AslLogCallPrintf(
            1,
            "SdbpGetTagHeadSize",
            121,
            "Invalid TAG_TYPE encountered. TAG: [%x]",
            (unsigned __int16)v17);
          goto LABEL_70;
        }
        v7 = 6;
      }
      else
      {
        v7 = (v17 & 0xF000) < 0x7000 ? 2 : 6;
      }
LABEL_22:
      if ( v7 + a2 + (unsigned int)v10 < (unsigned int)v10 )
      {
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          855,
          "Offset and region size add up to cause an integer overflow or underflow");
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 20);
        if ( v14 >= v7 + a2 + (unsigned int)v10 )
        {
          memcpy_0(&v19, (const void *)(*(_QWORD *)(a1 + 8) + v7 + a2), v10);
          return v19;
        }
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          860,
          "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
          v7 + a2,
          v10,
          v14);
      }
      AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
      return v18;
    }
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
LABEL_70:
    v7 = 0;
    goto LABEL_22;
  }
LABEL_61:
  AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, v10);
  return v18;
}

```

## disassembly

```asm
0x180022b10  mov     rax, rsp
0x180022b13  mov     [rax+8], rbx
0x180022b17  mov     [rax+18h], r8d
0x180022b1b  push    rbp
0x180022b1c  push    rsi
0x180022b1d  push    rdi
0x180022b1e  push    r12
0x180022b20  push    r13
0x180022b22  push    r14
0x180022b24  push    r15
0x180022b26  sub     rsp, 40h
0x180022b2a  mov     r13d, edx
0x180022b2d  mov     ebx, 1
0x180022b32  mov     edi, r8d
0x180022b35  mov     [rax+20h], r8d
0x180022b39  mov     r15, rcx
0x180022b3c  lea     r14d, [r13+2]
0x180022b40  lea     esi, [rbx+1]
0x180022b43  cmp     r14d, esi
0x180022b46  jb      loc_180022CC0
0x180022b4c  mov     eax, [rcx+14h]
0x180022b4f  cmp     eax, r14d
0x180022b52  jb      loc_180022F71
0x180022b58  mov     rax, [rcx+8]
0x180022b5c  mov     ebp, 0F000h
0x180022b61  movzx   edx, word ptr [r13+rax+0]
0x180022b67  mov     eax, 4000h
0x180022b6c  and     dx, bp
0x180022b6f  cmp     dx, ax
0x180022b72  jnz     loc_180022CF6
0x180022b78  mov     edx, r13d
0x180022b7b  call    SdbGetTagFromTagID
0x180022b80  movzx   r12d, ax
0x180022b84  mov     edi, r12d
0x180022b87  and     edi, ebp
0x180022b89  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x180022b8e  lea     edx, [rbx+3]
0x180022b91  test    eax, eax
0x180022b93  jz      loc_180022E4F
0x180022b99  mov     ebp, 20000000h
0x180022b9e  cmp     edi, 9000h
0x180022ba4  jnz     loc_180022DE0
0x180022baa  lea     eax, [r14+4]
0x180022bae  cmp     eax, edx
0x180022bb0  jb      loc_180022D9B
0x180022bb6  mov     ecx, [r15+14h]
0x180022bba  cmp     ecx, eax
0x180022bbc  jb      loc_180022F9E
0x180022bc2  mov     rax, [r15+8]
0x180022bc6  mov     eax, [r14+rax]
0x180022bca  lea     ecx, [rax+r13]
0x180022bce  cmp     ecx, eax
0x180022bd0  jb      loc_180022D71
0x180022bd6  cmp     ecx, [r15+14h]
0x180022bda  ja      loc_180022D71
0x180022be0  mov     ebp, eax
0x180022be2  cmp     eax, 4
0x180022be5  ja      loc_180022F45
0x180022beb  xor     eax, eax
0x180022bed  lea     r8, [rsp+78h+arg_8]
0x180022bf5  mov     r9d, esi
0x180022bf8  mov     word ptr [rsp+78h+arg_8], ax
0x180022c00  mov     edx, r13d
0x180022c03  mov     rcx, r15
0x180022c06  call    SdbpReadMappedData
0x180022c0b  test    eax, eax
0x180022c0d  jz      loc_180023011
0x180022c13  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x180022c18  mov     edx, 0F000h
0x180022c1d  test    eax, eax
0x180022c1f  jz      loc_180022E2B
0x180022c25  movzx   ecx, word ptr [rsp+78h+arg_8]
0x180022c2d  mov     eax, ecx
0x180022c2f  and     eax, edx
0x180022c31  cmp     eax, 6000h
0x180022c36  jz      short loc_180022C70
0x180022c38  cmp     eax, 1000h
0x180022c3d  jz      short loc_180022C70
0x180022c3f  cmp     eax, 2000h
0x180022c44  jz      short loc_180022C70
0x180022c46  cmp     eax, 3000h
0x180022c4b  jz      short loc_180022C70
0x180022c4d  cmp     eax, 4000h
0x180022c52  jz      short loc_180022C70
0x180022c54  cmp     eax, 5000h
0x180022c59  jz      short loc_180022C70
0x180022c5b  mov     edx, 7000h
0x180022c60  cmp     eax, 9000h
0x180022c65  jnz     loc_180023054
0x180022c6b  mov     esi, 6
0x180022c70  lea     eax, [rsi+r13]
0x180022c74  lea     edx, [rax+rbp]
0x180022c77  cmp     edx, ebp
0x180022c79  jb      loc_180022D2F
0x180022c7f  mov     ecx, [r15+14h]
0x180022c83  cmp     ecx, edx
0x180022c85  jb      loc_180023069
0x180022c8b  mov     edx, eax
0x180022c8d  lea     rcx, [rsp+78h+arg_18]; void *
0x180022c95  add     rdx, [r15+8]; Src
0x180022c99  mov     r8, rbp; Size
0x180022c9c  call    memcpy_0
0x180022ca1  mov     eax, [rsp+78h+arg_18]
0x180022ca8  mov     rbx, [rsp+78h+arg_0]
0x180022cb0  add     rsp, 40h
0x180022cb4  pop     r15
0x180022cb6  pop     r14
0x180022cb8  pop     r13
0x180022cba  pop     r12
0x180022cbc  pop     rdi
0x180022cbd  pop     rsi
0x180022cbe  pop     rbp
0x180022cbf  retn
0x180022cc0  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x180022cc7  mov     r8d, 357h
0x180022ccd  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180022cd4  mov     ecx, ebx
0x180022cd6  call    AslLogCallPrintf
0x180022cdb  lea     r9, aErrorReadingDa; "Error reading data"
0x180022ce2  mov     r8d, 0BDFh
0x180022ce8  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x180022cef  mov     ecx, ebx
0x180022cf1  call    AslLogCallPrintf
0x180022cf6  mov     edx, r13d
0x180022cf9  mov     rcx, r15
0x180022cfc  call    SdbGetTagFromTagID
0x180022d01  movzx   eax, ax
0x180022d04  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x180022d0b  mov     [rsp+78h+var_50], eax
0x180022d0f  lea     rdx, aSdbreaddwordta_2; "SdbReadDWORDTag"
0x180022d16  mov     r8d, 0B3h
0x180022d1c  mov     [rsp+78h+var_58], r13d
0x180022d21  mov     ecx, ebx
0x180022d23  call    AslLogCallPrintf
0x180022d28  mov     eax, edi
0x180022d2a  jmp     loc_180022CA8
0x180022d2f  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x180022d36  mov     r8d, 357h
0x180022d3c  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180022d43  mov     ecx, ebx
0x180022d45  call    AslLogCallPrintf
0x180022d4a  lea     r9, aErrorReadingTa; "Error reading tag data"
0x180022d51  mov     r8d, 1BEh
0x180022d57  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x180022d5e  mov     ecx, ebx
0x180022d60  call    AslLogCallPrintf
0x180022d65  mov     eax, [rsp+78h+arg_10]
0x180022d6c  jmp     loc_180022CA8
0x180022d71  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x180022d78  mov     [rsp+78h+var_58], 0C0000095h
0x180022d80  mov     r8d, 149h
0x180022d86  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x180022d8d  mov     ecx, ebx
0x180022d8f  call    AslLogCallPrintf
0x180022d94  mov     eax, ebp
0x180022d96  jmp     loc_180022BE0
0x180022d9b  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x180022da2  mov     r8d, 357h
0x180022da8  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180022daf  mov     ecx, ebx
0x180022db1  call    AslLogCallPrintf
0x180022db6  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x180022dbd  mov     [rsp+78h+var_58], 0C0000023h
0x180022dc5  mov     r8d, 137h
0x180022dcb  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x180022dd2  mov     ecx, ebx
0x180022dd4  call    AslLogCallPrintf
0x180022dd9  mov     eax, ebp
0x180022ddb  jmp     loc_180022BCA
0x180022de0  cmp     edi, 4000h
0x180022de6  jnz     short loc_180022DEF
0x180022de8  mov     eax, edx
0x180022dea  jmp     loc_180022BCA
0x180022def  cmp     edi, 5000h
0x180022df5  jnz     short loc_180022E01
0x180022df7  mov     eax, 8
0x180022dfc  jmp     loc_180022BCA
0x180022e01  cmp     edi, 1000h
0x180022e07  jnz     short loc_180022E10
0x180022e09  xor     eax, eax
0x180022e0b  jmp     loc_180022BCA
0x180022e10  cmp     edi, 6000h
0x180022e16  jz      short loc_180022DE8
0x180022e18  cmp     edi, 3000h
0x180022e1e  jnz     loc_180022F01
0x180022e24  mov     eax, esi
0x180022e26  jmp     loc_180022BCA
0x180022e2b  movzx   eax, word ptr [rsp+78h+arg_8]
0x180022e33  mov     esi, 6
0x180022e38  and     ax, dx
0x180022e3b  mov     edx, 7000h
0x180022e40  cmp     ax, dx
0x180022e43  sbb     eax, eax
0x180022e45  and     eax, 0FFFFFFFCh
0x180022e48  add     esi, eax
0x180022e4a  jmp     loc_180022C70
0x180022e4f  cmp     edi, 1000h
0x180022e55  jnz     short loc_180022E90
0x180022e57  xor     eax, eax
0x180022e59  lea     ecx, [rax+r13]
0x180022e5d  cmp     ecx, eax
0x180022e5f  jb      short loc_180022E6B
0x180022e61  cmp     ecx, [r15+14h]
0x180022e65  jbe     loc_180022BE0
0x180022e6b  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x180022e72  mov     r8d, 177h
0x180022e78  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x180022e7f  mov     ecx, ebx
0x180022e81  call    AslLogCallPrintf
0x180022e86  mov     eax, 20000000h
0x180022e8b  jmp     loc_180022BE0
0x180022e90  cmp     edi, 2000h
0x180022e96  jz      loc_18002300A
0x180022e9c  cmp     edi, 3000h
0x180022ea2  jz      loc_180023003
0x180022ea8  cmp     edi, 4000h
0x180022eae  jz      loc_180022FFC
0x180022eb4  cmp     edi, 5000h
0x180022eba  jz      loc_180022FF2
0x180022ec0  cmp     edi, 6000h
0x180022ec6  jz      loc_180022FFC
0x180022ecc  mov     r9d, edx
0x180022ecf  mov     [rsp+78h+arg_8], 0
0x180022eda  mov     edx, r14d
0x180022edd  lea     r8, [rsp+78h+arg_8]
0x180022ee5  mov     rcx, r15
0x180022ee8  call    SdbpReadMappedData
0x180022eed  test    eax, eax
0x180022eef  jz      loc_180022FD2
0x180022ef5  mov     eax, [rsp+78h+arg_8]
0x180022efc  jmp     loc_180022E59
0x180022f01  cmp     edi, 2000h
0x180022f07  jz      loc_180022FCB
0x180022f0d  cmp     edi, 7000h
0x180022f13  jz      loc_180022BAA
0x180022f19  cmp     edi, 8000h
0x180022f1f  jz      loc_180022BAA
0x180022f25  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x180022f2c  mov     [rsp+78h+var_58], r12d
0x180022f31  mov     r8d, 13Eh
0x180022f37  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x180022f3e  mov     ecx, ebx
0x180022f40  call    AslLogCallPrintf
0x180022f45  mov     [rsp+78h+var_50], ebp
0x180022f49  lea     r9, aBufferTooSmall_1; "Buffer too small. Avail: %d, Need: %d"
0x180022f50  mov     r8d, 1B7h
0x180022f56  mov     [rsp+78h+var_58], 4
0x180022f5e  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x180022f65  mov     ecx, ebx
0x180022f67  call    AslLogCallPrintf
0x180022f6c  jmp     loc_180022D65
0x180022f71  mov     [rsp+78h+var_48], eax
0x180022f75  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x180022f7c  mov     [rsp+78h+var_50], esi
0x180022f80  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180022f87  mov     r8d, 35Ch
0x180022f8d  mov     [rsp+78h+var_58], r13d
0x180022f92  mov     ecx, ebx
0x180022f94  call    AslLogCallPrintf
0x180022f99  jmp     loc_180022CDB
0x180022f9e  mov     [rsp+78h+var_48], ecx
0x180022fa2  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x180022fa9  mov     [rsp+78h+var_50], edx
0x180022fad  mov     r8d, 35Ch
0x180022fb3  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180022fba  mov     [rsp+78h+var_58], r14d
0x180022fbf  mov     ecx, ebx
0x180022fc1  call    AslLogCallPrintf
0x180022fc6  jmp     loc_180022DB6
0x180022fcb  mov     eax, ebx
0x180022fcd  jmp     loc_180022BCA
0x180022fd2  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x180022fd9  mov     r8d, 16Ch
0x180022fdf  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x180022fe6  mov     ecx, ebx
0x180022fe8  call    AslLogCallPrintf
0x180022fed  jmp     loc_180022EF5
0x180022ff2  mov     eax, 8
0x180022ff7  jmp     loc_180022E59
0x180022ffc  mov     eax, edx
0x180022ffe  jmp     loc_180022E59
0x180023003  mov     eax, esi
0x180023005  jmp     loc_180022E59
0x18002300a  mov     eax, ebx
0x18002300c  jmp     loc_180022E59
0x180023011  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x180023018  mov     r8d, 64h ; 'd'
0x18002301e  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x180023025  mov     ecx, ebx
0x180023027  call    AslLogCallPrintf
0x18002302c  jmp     short loc_18002304D
0x18002302e  mov     [rsp+78h+var_58], ecx
0x180023032  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x180023039  mov     ecx, ebx
0x18002303b  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x180023042  mov     r8d, 79h ; 'y'
0x180023048  call    AslLogCallPrintf
0x18002304d  xor     esi, esi
0x18002304f  jmp     loc_180022C70
0x180023054  cmp     eax, edx
  ... truncated ...
```
