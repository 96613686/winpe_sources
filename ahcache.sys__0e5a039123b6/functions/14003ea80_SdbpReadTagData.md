# SdbpReadTagData

- ea: `0x14003ea80`
- end: `0x14003ef04`
- name: `SdbpReadTagData`
- size: `1156`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14003c62c`
- `0x14003fc10`
- `0x140040820`
- `0x140040f90`
- `0x1400425d8`

## callees

- `0x1400055d4`
- `0x14003e248`
- `0x14003e364`
- `0x14003ea80`

## string_xrefs

- `0x14003ec57`: `Error reading data`
- `0x14003ec7c`: `Error reading size data [%x]`
- `0x14003edf2`: `Error reading size data [%x]`
- `0x14003eb60`: `Error reading size data`
- `0x14003ee20`: `Error reading size data`
- `0x14003edc2`: `SdbpReadTagData`
- `0x14003ee7b`: `SdbpReadTagData`
- `0x14003edb5`: `Error reading tag data`
- `0x14003ee93`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbpReadTagData(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v5; // esi
  unsigned int v6; // r15d
  unsigned __int16 v8; // ax
  int v9; // r14d
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edi
  int v13; // ecx
  unsigned int v15; // eax
  unsigned __int16 v16; // [rsp+78h] [rbp+48h] BYREF
  __int64 v17; // [rsp+80h] [rbp+50h]
  int v18; // [rsp+88h] [rbp+58h] BYREF

  v17 = a3;
  v5 = 2;
  v18 = 0;
  v6 = a2;
  v16 = 0;
  if ( (unsigned int)SdbpReadMappedData(a1, a2, &v16, 2) )
  {
    v8 = v16;
  }
  else
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    v8 = 0;
  }
  v9 = v8;
  v10 = v8 & 0xF000;
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v10 != 0x4000 )
    {
      switch ( v10 )
      {
        case 0x1000u:
          v11 = 0;
          goto LABEL_56;
        case 0x2000u:
          v11 = 1;
          goto LABEL_56;
        case 0x3000u:
          v11 = 2;
          goto LABEL_56;
        case 0x5000u:
          v11 = 8;
          goto LABEL_56;
      }
      if ( v10 != 24576 )
      {
        v18 = 0;
        if ( !(unsigned int)SdbpReadMappedData(a1, v6 + 2, &v18, 4) )
          AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
        v11 = v18;
        goto LABEL_13;
      }
    }
    v11 = 4;
LABEL_56:
    v18 = v11;
LABEL_13:
    if ( v11 + v6 < v11 || v11 + v6 > *(_DWORD *)(a1 + 20) )
    {
      AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
      v11 = 0x20000000;
    }
LABEL_21:
    v12 = v11;
    goto LABEL_22;
  }
  v12 = 0x20000000;
  if ( v10 == 0x4000 )
    goto LABEL_17;
  if ( v10 <= 0x6000 )
  {
    switch ( v10 )
    {
      case 0x6000u:
LABEL_17:
        v11 = 4;
LABEL_18:
        v18 = v11;
LABEL_19:
        if ( v11 + v6 < v11 || v11 + v6 > *(_DWORD *)(a1 + 20) )
        {
          AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
          v11 = 0x20000000;
        }
        goto LABEL_21;
      case 0x1000u:
        v11 = 0;
        goto LABEL_18;
      case 0x2000u:
        v11 = 1;
        goto LABEL_18;
      case 0x3000u:
        v11 = 2;
        goto LABEL_18;
      case 0x5000u:
        v11 = 8;
        goto LABEL_18;
    }
  }
  else if ( v10 == 36864 || v10 == 28672 || v10 == 0x8000 )
  {
    v18 = 0;
    if ( !(unsigned int)SdbpReadMappedData(a1, v6 + 2, &v18, 4) )
    {
      v18 = 0x20000000;
      AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
    }
    v11 = v18;
    goto LABEL_19;
  }
  AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v9);
LABEL_22:
  if ( v12 > a4 )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", a4, v12);
    return 0;
  }
  v16 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, v6, &v16, 2) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v5 = 0;
    goto LABEL_28;
  }
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v13 = 6;
    if ( (v16 & 0xF000u) < 0x7000 )
      v13 = 2;
    v5 = v13;
    goto LABEL_28;
  }
  v15 = v16 & 0xF000;
  if ( v15 == 36864 )
    goto LABEL_31;
  if ( v15 != 24576 )
  {
    if ( v15 > 0x4000 )
    {
      if ( v15 == 20480 )
        goto LABEL_28;
      if ( v15 == 28672 || v15 == 0x8000 )
      {
LABEL_31:
        v5 = 6;
        goto LABEL_28;
      }
    }
    else if ( v15 == 0x4000 || v15 == 4096 || v15 == 0x2000 || v15 == 12288 )
    {
      goto LABEL_28;
    }
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v16);
    v5 = 0;
  }
LABEL_28:
  if ( (unsigned int)SdbpReadMappedData(a1, v5 + v6, v17, v12) )
    return 1;
  AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
  return 0;
}

```

## disassembly

```asm
0x14003ea80  mov     [rsp-38h+arg_0], rbx
0x14003ea85  mov     [rsp-38h+arg_10], r8
0x14003ea8a  push    rbp
0x14003ea8b  push    rsi
0x14003ea8c  push    rdi
0x14003ea8d  push    r12
0x14003ea8f  push    r13
0x14003ea91  push    r14
0x14003ea93  push    r15
0x14003ea95  mov     rbp, rsp
0x14003ea98  sub     rsp, 30h
0x14003ea9c  mov     r13d, r9d
0x14003ea9f  lea     r8, [rbp+arg_8]
0x14003eaa3  xor     edi, edi
0x14003eaa5  mov     esi, 2
0x14003eaaa  mov     r9d, esi
0x14003eaad  mov     [rbp+arg_18], edi
0x14003eab0  mov     r15d, edx
0x14003eab3  mov     [rbp+arg_8], di
0x14003eab7  mov     r12, rcx
0x14003eaba  call    SdbpReadMappedData
0x14003eabf  test    eax, eax
0x14003eac1  jz      loc_14003EC57
0x14003eac7  movzx   eax, [rbp+arg_8]
0x14003eacb  movzx   r14d, ax
0x14003eacf  mov     ebx, r14d
0x14003ead2  and     ebx, 0F000h
0x14003ead8  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003eadd  test    eax, eax
0x14003eadf  jnz     loc_14003EB85
0x14003eae5  cmp     ebx, 4000h
0x14003eaeb  jz      loc_14003EDA8
0x14003eaf1  cmp     ebx, 1000h
0x14003eaf7  jz      loc_14003EE5E
0x14003eafd  cmp     ebx, 2000h
0x14003eb03  jz      loc_14003EE54
0x14003eb09  cmp     ebx, 3000h
0x14003eb0f  jz      loc_14003EE4D
0x14003eb15  cmp     ebx, 5000h
0x14003eb1b  jz      loc_14003EE43
0x14003eb21  cmp     ebx, 6000h
0x14003eb27  jz      loc_14003EDA8
0x14003eb2d  lea     edx, [r15+2]
0x14003eb31  mov     [rbp+arg_18], edi
0x14003eb34  mov     r9d, 4
0x14003eb3a  lea     r8, [rbp+arg_18]
0x14003eb3e  mov     rcx, r12
0x14003eb41  call    SdbpReadMappedData
0x14003eb46  test    eax, eax
0x14003eb48  jz      loc_14003EE20
0x14003eb4e  mov     eax, [rbp+arg_18]
0x14003eb51  lea     ecx, [rax+r15]
0x14003eb55  cmp     ecx, eax
0x14003eb57  jb      short loc_14003EB60
0x14003eb59  cmp     ecx, [r12+14h]
0x14003eb5e  jbe     short loc_14003EBB5
0x14003eb60  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x14003eb67  mov     r8d, 177h
0x14003eb6d  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14003eb74  mov     ecx, 1
0x14003eb79  call    AslLogCallPrintf
0x14003eb7e  mov     eax, 20000000h
0x14003eb83  jmp     short loc_14003EBB5
0x14003eb85  mov     edi, 20000000h
0x14003eb8a  cmp     ebx, 4000h
0x14003eb90  jnz     loc_14003ECA9
0x14003eb96  mov     eax, 4
0x14003eb9b  mov     [rbp+arg_18], eax
0x14003eb9e  lea     ecx, [rax+r15]
0x14003eba2  cmp     ecx, eax
0x14003eba4  jb      loc_14003EC7C
0x14003ebaa  cmp     ecx, [r12+14h]
0x14003ebaf  ja      loc_14003EC7C
0x14003ebb5  mov     edi, eax
0x14003ebb7  cmp     edi, r13d
0x14003ebba  ja      loc_14003EE65
0x14003ebc0  xor     eax, eax
0x14003ebc2  lea     r8, [rbp+arg_8]
0x14003ebc6  mov     r9d, esi
0x14003ebc9  mov     [rbp+arg_8], ax
0x14003ebcd  mov     edx, r15d
0x14003ebd0  mov     rcx, r12
0x14003ebd3  call    SdbpReadMappedData
0x14003ebd8  test    eax, eax
0x14003ebda  jz      loc_14003EE93
0x14003ebe0  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003ebe5  mov     edx, 0F000h
0x14003ebea  test    eax, eax
0x14003ebec  jnz     short loc_14003EC3D
0x14003ebee  movzx   eax, [rbp+arg_8]
0x14003ebf2  mov     ecx, 6
0x14003ebf7  and     ax, dx
0x14003ebfa  mov     edx, 7000h
0x14003ebff  cmp     ax, dx
0x14003ec02  cmovb   ecx, esi
0x14003ec05  mov     esi, ecx
0x14003ec07  mov     r8, [rbp+arg_10]
0x14003ec0b  lea     edx, [rsi+r15]
0x14003ec0f  mov     r9d, edi
0x14003ec12  mov     rcx, r12
0x14003ec15  call    SdbpReadMappedData
0x14003ec1a  test    eax, eax
0x14003ec1c  jz      loc_14003EDB5
0x14003ec22  mov     eax, 1
0x14003ec27  mov     rbx, [rsp+30h+arg_0]
0x14003ec2c  add     rsp, 30h
0x14003ec30  pop     r15
0x14003ec32  pop     r14
0x14003ec34  pop     r13
0x14003ec36  pop     r12
0x14003ec38  pop     rdi
0x14003ec39  pop     rsi
0x14003ec3a  pop     rbp
0x14003ec3b  retn
0x14003ec3d  movzx   ecx, [rbp+arg_8]
0x14003ec41  mov     eax, ecx
0x14003ec43  and     eax, edx
0x14003ec45  cmp     eax, 9000h
0x14003ec4a  jnz     loc_14003ECEA
0x14003ec50  mov     esi, 6
0x14003ec55  jmp     short loc_14003EC07
0x14003ec57  lea     r9, aErrorReadingDa; "Error reading data"
0x14003ec5e  mov     r8d, 0BDFh
0x14003ec64  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003ec6b  mov     ecx, 1
0x14003ec70  call    AslLogCallPrintf
0x14003ec75  mov     eax, edi
0x14003ec77  jmp     loc_14003EACB
0x14003ec7c  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x14003ec83  mov     [rsp+30h+var_10], 0C0000095h
0x14003ec8b  mov     r8d, 149h
0x14003ec91  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14003ec98  mov     ecx, 1
0x14003ec9d  call    AslLogCallPrintf
0x14003eca2  mov     eax, edi
0x14003eca4  jmp     loc_14003EBB5
0x14003eca9  cmp     ebx, 6000h
0x14003ecaf  jbe     short loc_14003ED2C
0x14003ecb1  cmp     ebx, 9000h
0x14003ecb7  jnz     loc_14003ED68
0x14003ecbd  lea     edx, [r15+2]
0x14003ecc1  mov     [rbp+arg_18], 0
0x14003ecc8  mov     r9d, 4
0x14003ecce  lea     r8, [rbp+arg_18]
0x14003ecd2  mov     rcx, r12
0x14003ecd5  call    SdbpReadMappedData
0x14003ecda  test    eax, eax
0x14003ecdc  jz      loc_14003EDF2
0x14003ece2  mov     eax, [rbp+arg_18]
0x14003ece5  jmp     loc_14003EB9E
0x14003ecea  cmp     eax, 6000h
0x14003ecef  jz      loc_14003EC07
0x14003ecf5  cmp     eax, 4000h
0x14003ecfa  ja      loc_14003EEB8
0x14003ed00  jz      loc_14003EC07
0x14003ed06  cmp     eax, 1000h
0x14003ed0b  jz      loc_14003EC07
0x14003ed11  cmp     eax, 2000h
0x14003ed16  jz      loc_14003EC07
0x14003ed1c  cmp     eax, 3000h
0x14003ed21  jz      loc_14003EC07
0x14003ed27  jmp     loc_14003EEDB
0x14003ed2c  jz      loc_14003EB96
0x14003ed32  cmp     ebx, 1000h
0x14003ed38  jz      loc_14003EDEB
0x14003ed3e  cmp     ebx, 2000h
0x14003ed44  jz      loc_14003EDE1
0x14003ed4a  cmp     ebx, 3000h
0x14003ed50  jz      loc_14003EDDA
0x14003ed56  cmp     ebx, 5000h
0x14003ed5c  jnz     short loc_14003ED80
0x14003ed5e  mov     eax, 8
0x14003ed63  jmp     loc_14003EB9B
0x14003ed68  cmp     ebx, 7000h
0x14003ed6e  jz      loc_14003ECBD
0x14003ed74  cmp     ebx, 8000h
0x14003ed7a  jz      loc_14003ECBD
0x14003ed80  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x14003ed87  mov     [rsp+30h+var_10], r14d
0x14003ed8c  mov     r8d, 13Eh
0x14003ed92  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14003ed99  mov     ecx, 1
0x14003ed9e  call    AslLogCallPrintf
0x14003eda3  jmp     loc_14003EBB7
0x14003eda8  mov     eax, 4
0x14003edad  mov     [rbp+arg_18], eax
0x14003edb0  jmp     loc_14003EB51
0x14003edb5  lea     r9, aErrorReadingTa; "Error reading tag data"
0x14003edbc  mov     r8d, 1BEh
0x14003edc2  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003edc9  mov     ecx, 1
0x14003edce  call    AslLogCallPrintf
0x14003edd3  xor     eax, eax
0x14003edd5  jmp     loc_14003EC27
0x14003edda  mov     eax, esi
0x14003eddc  jmp     loc_14003EB9B
0x14003ede1  mov     eax, 1
0x14003ede6  jmp     loc_14003EB9B
0x14003edeb  xor     eax, eax
0x14003eded  jmp     loc_14003EB9B
0x14003edf2  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x14003edf9  mov     [rbp+arg_18], edi
0x14003edfc  mov     r8d, 137h
0x14003ee02  mov     [rsp+30h+var_10], 0C0000023h
0x14003ee0a  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14003ee11  mov     ecx, 1
0x14003ee16  call    AslLogCallPrintf
0x14003ee1b  jmp     loc_14003ECE2
0x14003ee20  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x14003ee27  mov     r8d, 16Ch
0x14003ee2d  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14003ee34  mov     ecx, 1
0x14003ee39  call    AslLogCallPrintf
0x14003ee3e  jmp     loc_14003EB4E
0x14003ee43  mov     eax, 8
0x14003ee48  jmp     loc_14003EDAD
0x14003ee4d  mov     eax, esi
0x14003ee4f  jmp     loc_14003EDAD
0x14003ee54  mov     eax, 1
0x14003ee59  jmp     loc_14003EDAD
0x14003ee5e  mov     eax, edi
0x14003ee60  jmp     loc_14003EDAD
0x14003ee65  mov     [rsp+30h+var_8], edi
0x14003ee69  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14003ee70  mov     r8d, 1B7h
0x14003ee76  mov     [rsp+30h+var_10], r13d
0x14003ee7b  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003ee82  mov     ecx, 1
0x14003ee87  call    AslLogCallPrintf
0x14003ee8c  xor     eax, eax
0x14003ee8e  jmp     loc_14003EC27
0x14003ee93  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003ee9a  mov     r8d, 64h ; 'd'
0x14003eea0  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003eea7  mov     ecx, 1
0x14003eeac  call    AslLogCallPrintf
0x14003eeb1  xor     esi, esi
0x14003eeb3  jmp     loc_14003EC07
0x14003eeb8  cmp     eax, 5000h
0x14003eebd  jz      loc_14003EC07
0x14003eec3  mov     edx, 7000h
0x14003eec8  cmp     eax, edx
0x14003eeca  jz      loc_14003EC50
0x14003eed0  cmp     eax, 8000h
0x14003eed5  jz      loc_14003EC50
0x14003eedb  mov     [rsp+30h+var_10], ecx
0x14003eedf  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003eee6  mov     ecx, 1
0x14003eeeb  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003eef2  mov     r8d, 79h ; 'y'
0x14003eef8  call    AslLogCallPrintf
0x14003eefd  xor     esi, esi
0x14003eeff  jmp     loc_14003EC07
```
