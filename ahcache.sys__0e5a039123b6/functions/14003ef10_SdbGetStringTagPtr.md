# SdbGetStringTagPtr

- ea: `0x14003ef10`
- end: `0x14003f274`
- name: `SdbGetStringTagPtr`
- size: `868`
- prototype: ``
- caller_count: `24`
- callee_count: `8`
- tags: ``

## callers

- `0x140005f1c`
- `0x140024994`
- `0x1400255d0`
- `0x14002ebc0`
- `0x14002ed10`
- `0x14002ef40`
- `0x14002f050`
- `0x14002f430`
- `0x14002f980`
- `0x14002fd64`
- `0x140038a88`
- `0x140038bd8`
- `0x140039400`
- `0x140039b18`
- `0x14003af10`
- `0x14003b2f0`
- `0x14003b694`
- `0x14003c010`
- `0x14003c364`
- `0x14003fe74`
- `0x140049ec0`
- `0x14004a1ac`
- `0x14004b4ac`
- `0x14005289c`

## callees

- `0x1400055d4`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14003ef10`
- `0x14003f280`
- `0x14003fcf8`
- `0x14004007c`

## string_xrefs

- `0x14003efd4`: `Error reading data`
- `0x14003f0d3`: `Error reading data`
- `0x14003f1a7`: `Error reading data`
- `0x14003f109`: `SdbpReadStringRef`
- `0x14003f1b4`: `SdbpReadStringRef`
- `0x14003f196`: `SdbpReadTagData`
- `0x14003f1f2`: `SdbpReadTagData`
- `0x14003f189`: `Error reading tag data`
- `0x14003f205`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbGetStringTagPtr(PVOID Parameter, __int64 a2)
{
  unsigned int v2; // edi
  int v4; // esi
  __int64 v5; // rcx
  unsigned int TagDataSize; // eax
  unsigned int v8; // ebp
  int v9; // ecx
  unsigned int v11; // eax
  unsigned __int16 TagFromTagID; // ax
  unsigned __int16 v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  if ( !Parameter )
  {
    AslLogCallPrintf(1, "SdbGetStringTagPtr", 722, "Invalid pdb");
    return 0;
  }
  v4 = 2;
  v13 = 0;
  if ( !(unsigned int)SdbpReadMappedData(Parameter, a2, &v13, 2) )
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    return 0;
  }
  if ( (v13 & 0xF000) == 0x8000 )
    return SdbpGetMappedTagData(Parameter, v2);
  v5 = 0;
  if ( (v13 & 0xF000) == 0x6000 )
  {
    v14 = 0;
    v13 = 0;
    if ( (unsigned int)SdbpReadMappedData(Parameter, v2, &v13, 2) )
    {
      if ( (v13 & 0xF000) == 0x6000 )
      {
        TagDataSize = SdbGetTagDataSize(Parameter, v2);
        v8 = TagDataSize;
        if ( TagDataSize > 4 )
        {
          AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, TagDataSize);
          goto LABEL_34;
        }
        v13 = 0;
        if ( !(unsigned int)SdbpReadMappedData(Parameter, v2, &v13, 2) )
        {
          AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
          v4 = 0;
          goto LABEL_17;
        }
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          v9 = 6;
          if ( (v13 & 0xF000u) < 0x7000 )
            v9 = 2;
          v4 = v9;
          goto LABEL_17;
        }
        v11 = v13 & 0xF000;
        if ( v11 == 36864 )
          goto LABEL_22;
        if ( v11 == 24576 )
          goto LABEL_17;
        if ( v11 > 0x4000 )
        {
          if ( v11 == 20480 )
            goto LABEL_17;
          if ( v11 == 28672 || v11 == 0x8000 )
          {
LABEL_22:
            v4 = 6;
LABEL_17:
            if ( (unsigned int)SdbpReadMappedData(Parameter, v4 + v2, &v14, v8) )
            {
              if ( v14 )
                return SdbpGetMappedStringFromTable(Parameter);
LABEL_25:
              AslLogCallPrintf(1, "SdbGetStringTagPtr", 742, "Error getting StringRef");
              return 0;
            }
            AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
LABEL_34:
            AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
            goto LABEL_25;
          }
        }
        else if ( v11 == 0x4000 || v11 == 4096 || v11 == 0x2000 || v11 == 12288 )
        {
          goto LABEL_17;
        }
        AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v13);
        v4 = 0;
        goto LABEL_17;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    }
    TagFromTagID = SdbGetTagFromTagID(Parameter, v2);
    AslLogCallPrintf(1, "SdbpReadStringRef", 634, "TagID 0x%08X, Tag %04X not STRINGREF type", v2, TagFromTagID);
    goto LABEL_25;
  }
  return v5;
}

```

## disassembly

```asm
0x14003ef10  push    rbx
0x14003ef12  push    rdi
0x14003ef13  sub     rsp, 48h
0x14003ef17  mov     edi, edx
0x14003ef19  mov     rbx, rcx
0x14003ef1c  test    rcx, rcx
0x14003ef1f  jz      loc_14003EFAC
0x14003ef25  mov     [rsp+58h+arg_8], rbp
0x14003ef2a  lea     r8, [rsp+58h+arg_0]
0x14003ef2f  mov     [rsp+58h+arg_18], rsi
0x14003ef34  xor     eax, eax
0x14003ef36  mov     [rsp+58h+var_18], r12
0x14003ef3b  mov     esi, 2
0x14003ef40  mov     r9d, esi
0x14003ef43  mov     [rsp+58h+var_20], r14
0x14003ef48  mov     [rsp+58h+var_28], r15
0x14003ef4d  mov     [rsp+58h+arg_0], ax
0x14003ef52  call    SdbpReadMappedData
0x14003ef57  test    eax, eax
0x14003ef59  jz      short loc_14003EFD4
0x14003ef5b  movzx   eax, [rsp+58h+arg_0]
0x14003ef60  mov     r15d, 0F000h
0x14003ef66  and     ax, r15w
0x14003ef6a  mov     r12d, 8000h
0x14003ef70  cmp     ax, r12w
0x14003ef74  jz      loc_14003F1CA
0x14003ef7a  xor     ecx, ecx
0x14003ef7c  mov     r14d, 6000h
0x14003ef82  cmp     ax, r14w
0x14003ef86  jz      short loc_14003EFF6
0x14003ef88  mov     rax, rcx
0x14003ef8b  mov     r14, [rsp+58h+var_20]
0x14003ef90  mov     r12, [rsp+58h+var_18]
0x14003ef95  mov     rsi, [rsp+58h+arg_18]
0x14003ef9a  mov     rbp, [rsp+58h+arg_8]
0x14003ef9f  mov     r15, [rsp+58h+var_28]
0x14003efa4  add     rsp, 48h
0x14003efa8  pop     rdi
0x14003efa9  pop     rbx
0x14003efaa  retn
0x14003efac  lea     r9, aInvalidPdb; "Invalid pdb"
0x14003efb3  mov     r8d, 2D2h
0x14003efb9  lea     rdx, aSdbgetstringta; "SdbGetStringTagPtr"
0x14003efc0  mov     ecx, 1
0x14003efc5  call    AslLogCallPrintf
0x14003efca  xor     eax, eax
0x14003efcc  add     rsp, 48h
0x14003efd0  pop     rdi
0x14003efd1  pop     rbx
0x14003efd2  retn
0x14003efd4  lea     r9, aErrorReadingDa; "Error reading data"
0x14003efdb  mov     r8d, 0BDFh
0x14003efe1  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003efe8  mov     ecx, 1
0x14003efed  call    AslLogCallPrintf
0x14003eff2  xor     ecx, ecx
0x14003eff4  jmp     short loc_14003EF88
0x14003eff6  mov     [rsp+58h+arg_10], ecx
0x14003effa  lea     r8, [rsp+58h+arg_0]
0x14003efff  xor     eax, eax
0x14003f001  mov     rcx, rbx
0x14003f004  mov     r9d, esi
0x14003f007  mov     [rsp+58h+arg_0], ax
0x14003f00c  mov     edx, edi
0x14003f00e  call    SdbpReadMappedData
0x14003f013  test    eax, eax
0x14003f015  jz      loc_14003F0D3
0x14003f01b  movzx   eax, [rsp+58h+arg_0]
0x14003f020  and     ax, r15w
0x14003f024  cmp     ax, r14w
0x14003f028  jnz     loc_14003F0F1
0x14003f02e  mov     edx, edi
0x14003f030  mov     rcx, rbx
0x14003f033  call    SdbGetTagDataSize
0x14003f038  mov     ebp, eax
0x14003f03a  cmp     eax, 4
0x14003f03d  ja      loc_14003F1D9
0x14003f043  xor     eax, eax
0x14003f045  lea     r8, [rsp+58h+arg_0]
0x14003f04a  mov     r9d, esi
0x14003f04d  mov     [rsp+58h+arg_0], ax
0x14003f052  mov     edx, edi
0x14003f054  mov     rcx, rbx
0x14003f057  call    SdbpReadMappedData
0x14003f05c  test    eax, eax
0x14003f05e  jz      loc_14003F205
0x14003f064  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003f069  test    eax, eax
0x14003f06b  jnz     short loc_14003F0BB
0x14003f06d  movzx   eax, [rsp+58h+arg_0]
0x14003f072  mov     edx, 7000h
0x14003f077  and     ax, r15w
0x14003f07b  mov     ecx, 6
0x14003f080  cmp     ax, dx
0x14003f083  cmovb   ecx, esi
0x14003f086  mov     esi, ecx
0x14003f088  lea     edx, [rsi+rdi]
0x14003f08b  mov     r9d, ebp
0x14003f08e  lea     r8, [rsp+58h+arg_10]
0x14003f093  mov     rcx, rbx
0x14003f096  call    SdbpReadMappedData
0x14003f09b  test    eax, eax
0x14003f09d  jz      loc_14003F189
0x14003f0a3  mov     edx, [rsp+58h+arg_10]
0x14003f0a7  test    edx, edx
0x14003f0a9  jz      short loc_14003F124
0x14003f0ab  mov     rcx, rbx; Parameter
0x14003f0ae  call    SdbpGetMappedStringFromTable
0x14003f0b3  mov     rcx, rax
0x14003f0b6  jmp     loc_14003EF88
0x14003f0bb  movzx   ecx, [rsp+58h+arg_0]
0x14003f0c0  mov     eax, ecx
0x14003f0c2  and     eax, r15d
0x14003f0c5  cmp     eax, 9000h
0x14003f0ca  jnz     short loc_14003F149
0x14003f0cc  mov     esi, 6
0x14003f0d1  jmp     short loc_14003F088
0x14003f0d3  lea     r9, aErrorReadingDa; "Error reading data"
0x14003f0da  mov     r8d, 0BDFh
0x14003f0e0  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003f0e7  mov     ecx, 1
0x14003f0ec  call    AslLogCallPrintf
0x14003f0f1  mov     edx, edi
0x14003f0f3  mov     rcx, rbx
0x14003f0f6  call    SdbGetTagFromTagID
0x14003f0fb  movzx   eax, ax
0x14003f0fe  lea     r9, aTagid0x08xTag0; "TagID 0x%08X, Tag %04X not STRINGREF ty"...
0x14003f105  mov     [rsp+58h+var_30], eax
0x14003f109  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x14003f110  mov     r8d, 27Ah
0x14003f116  mov     [rsp+58h+var_38], edi
0x14003f11a  mov     ecx, 1
0x14003f11f  call    AslLogCallPrintf
0x14003f124  lea     r9, aErrorGettingSt; "Error getting StringRef"
0x14003f12b  mov     r8d, 2E6h
0x14003f131  lea     rdx, aSdbgetstringta; "SdbGetStringTagPtr"
0x14003f138  mov     ecx, 1
0x14003f13d  call    AslLogCallPrintf
0x14003f142  xor     eax, eax
0x14003f144  jmp     loc_14003EF8B
0x14003f149  cmp     eax, r14d
0x14003f14c  jz      loc_14003F088
0x14003f152  cmp     eax, 4000h
0x14003f157  ja      loc_14003F22A
0x14003f15d  jz      loc_14003F088
0x14003f163  cmp     eax, 1000h
0x14003f168  jz      loc_14003F088
0x14003f16e  cmp     eax, 2000h
0x14003f173  jz      loc_14003F088
0x14003f179  cmp     eax, 3000h
0x14003f17e  jz      loc_14003F088
0x14003f184  jmp     loc_14003F24B
0x14003f189  lea     r9, aErrorReadingTa; "Error reading tag data"
0x14003f190  mov     r8d, 1BEh
0x14003f196  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003f19d  mov     ecx, 1
0x14003f1a2  call    AslLogCallPrintf
0x14003f1a7  lea     r9, aErrorReadingDa; "Error reading data"
0x14003f1ae  mov     r8d, 27Fh
0x14003f1b4  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x14003f1bb  mov     ecx, 1
0x14003f1c0  call    AslLogCallPrintf
0x14003f1c5  jmp     loc_14003F124
0x14003f1ca  mov     edx, edi
0x14003f1cc  mov     rcx, rbx
0x14003f1cf  call    SdbpGetMappedTagData
0x14003f1d4  jmp     loc_14003F0B3
0x14003f1d9  mov     [rsp+58h+var_30], ebp
0x14003f1dd  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14003f1e4  mov     r8d, 1B7h
0x14003f1ea  mov     [rsp+58h+var_38], 4
0x14003f1f2  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003f1f9  mov     ecx, 1
0x14003f1fe  call    AslLogCallPrintf
0x14003f203  jmp     short loc_14003F1A7
0x14003f205  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003f20c  mov     r8d, 64h ; 'd'
0x14003f212  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f219  mov     ecx, 1
0x14003f21e  call    AslLogCallPrintf
0x14003f223  xor     esi, esi
0x14003f225  jmp     loc_14003F088
0x14003f22a  cmp     eax, 5000h
0x14003f22f  jz      loc_14003F088
0x14003f235  mov     edx, 7000h
0x14003f23a  cmp     eax, edx
0x14003f23c  jz      loc_14003F0CC
0x14003f242  cmp     eax, r12d
0x14003f245  jz      loc_14003F0CC
0x14003f24b  mov     [rsp+58h+var_38], ecx
0x14003f24f  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003f256  mov     ecx, 1
0x14003f25b  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f262  mov     r8d, 79h ; 'y'
0x14003f268  call    AslLogCallPrintf
0x14003f26d  xor     esi, esi
0x14003f26f  jmp     loc_14003F088
```
