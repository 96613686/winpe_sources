# SdbpReadStringRef

- ea: `0x14003f9b4`
- end: `0x14003fc07`
- name: `SdbpReadStringRef`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400425d8`

## callees

- `0x1400055d4`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14003f9b4`
- `0x14004007c`

## string_xrefs

- `0x14003fae8`: `Error reading data`
- `0x14003fb5e`: `Error reading data`
- `0x14003fb1e`: `SdbpReadStringRef`
- `0x14003fb6b`: `SdbpReadStringRef`
- `0x14003fb4d`: `SdbpReadTagData`
- `0x14003fb98`: `SdbpReadTagData`
- `0x14003fb40`: `Error reading tag data`
- `0x14003fbb1`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbpReadStringRef(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  int v4; // edi
  unsigned int TagDataSize; // eax
  unsigned int v6; // r14d
  int v8; // eax
  unsigned __int16 TagFromTagID; // ax
  unsigned __int16 v10; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  v10 = 0;
  v2 = a2;
  v4 = 2;
  if ( (unsigned int)SdbpReadMappedData(a1, a2, &v10, 2) )
  {
    if ( (v10 & 0xF000) == 0x6000 )
    {
      TagDataSize = SdbGetTagDataSize(a1, v2);
      v6 = TagDataSize;
      if ( TagDataSize > 4 )
      {
        AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, TagDataSize);
LABEL_21:
        AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
        return 0;
      }
      v10 = 0;
      if ( (unsigned int)SdbpReadMappedData(a1, v2, &v10, 2) )
      {
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          v4 = (v10 & 0xF000u) < 0x7000 ? 2 : 6;
LABEL_7:
          if ( (unsigned int)SdbpReadMappedData(a1, v4 + v2, &v11, v6) )
            return v11;
          AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
          goto LABEL_21;
        }
        v8 = v10 & 0xF000;
        if ( v8 == 24576 || v8 == 4096 || v8 == 0x2000 || v8 == 12288 || v8 == 0x4000 || v8 == 20480 )
          goto LABEL_7;
        if ( v8 == 36864 || v8 == 28672 || v8 == 0x8000 )
        {
          v4 = 6;
          goto LABEL_7;
        }
        AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v10);
      }
      else
      {
        AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
      }
      v4 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
  }
  TagFromTagID = SdbGetTagFromTagID(a1, v2);
  AslLogCallPrintf(1, "SdbpReadStringRef", 634, "TagID 0x%08X, Tag %04X not STRINGREF type", v2, TagFromTagID);
  return 0;
}

```

## disassembly

```asm
0x14003f9b4  mov     [rsp+arg_0], rbp
0x14003f9b9  push    rsi
0x14003f9ba  push    rdi
0x14003f9bb  push    r12
0x14003f9bd  push    r14
0x14003f9bf  push    r15
0x14003f9c1  sub     rsp, 30h
0x14003f9c5  xor     eax, eax
0x14003f9c7  mov     [rsp+58h+arg_18], 0
0x14003f9cf  lea     r8, [rsp+58h+arg_10]
0x14003f9d4  mov     [rsp+58h+arg_10], ax
0x14003f9d9  mov     esi, edx
0x14003f9db  mov     rbp, rcx
0x14003f9de  lea     edi, [rax+2]
0x14003f9e1  mov     r9d, edi
0x14003f9e4  call    SdbpReadMappedData
0x14003f9e9  test    eax, eax
0x14003f9eb  jz      loc_14003FAE8
0x14003f9f1  movzx   eax, [rsp+58h+arg_10]
0x14003f9f6  mov     r15d, 0F000h
0x14003f9fc  and     ax, r15w
0x14003fa00  mov     r12d, 6000h
0x14003fa06  cmp     ax, r12w
0x14003fa0a  jnz     loc_14003FB06
0x14003fa10  mov     edx, esi
0x14003fa12  mov     rcx, rbp
0x14003fa15  call    SdbGetTagDataSize
0x14003fa1a  mov     r14d, eax
0x14003fa1d  cmp     eax, 4
0x14003fa20  ja      loc_14003FB7E
0x14003fa26  xor     eax, eax
0x14003fa28  lea     r8, [rsp+58h+arg_10]
0x14003fa2d  mov     r9d, edi
0x14003fa30  mov     [rsp+58h+arg_10], ax
0x14003fa35  mov     edx, esi
0x14003fa37  mov     rcx, rbp
0x14003fa3a  call    SdbpReadMappedData
0x14003fa3f  test    eax, eax
0x14003fa41  jz      loc_14003FBAB
0x14003fa47  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003fa4c  test    eax, eax
0x14003fa4e  jnz     short loc_14003FA9F
0x14003fa50  movzx   eax, [rsp+58h+arg_10]
0x14003fa55  mov     ecx, 7000h
0x14003fa5a  and     ax, r15w
0x14003fa5e  mov     edi, 6
0x14003fa63  cmp     ax, cx
0x14003fa66  sbb     eax, eax
0x14003fa68  and     eax, 0FFFFFFFCh
0x14003fa6b  add     edi, eax
0x14003fa6d  lea     edx, [rdi+rsi]
0x14003fa70  mov     r9d, r14d
0x14003fa73  lea     r8, [rsp+58h+arg_18]
0x14003fa78  mov     rcx, rbp
0x14003fa7b  call    SdbpReadMappedData
0x14003fa80  test    eax, eax
0x14003fa82  jz      loc_14003FB40
0x14003fa88  mov     eax, [rsp+58h+arg_18]
0x14003fa8c  mov     rbp, [rsp+58h+arg_0]
0x14003fa91  add     rsp, 30h
0x14003fa95  pop     r15
0x14003fa97  pop     r14
0x14003fa99  pop     r12
0x14003fa9b  pop     rdi
0x14003fa9c  pop     rsi
0x14003fa9d  retn
0x14003fa9f  movzx   edx, [rsp+58h+arg_10]
0x14003faa4  mov     eax, edx
0x14003faa6  and     eax, r15d
0x14003faa9  cmp     eax, r12d
0x14003faac  jz      short loc_14003FA6D
0x14003faae  cmp     eax, 1000h
0x14003fab3  jz      short loc_14003FA6D
0x14003fab5  cmp     eax, 2000h
0x14003faba  jz      short loc_14003FA6D
0x14003fabc  cmp     eax, 3000h
0x14003fac1  jz      short loc_14003FA6D
0x14003fac3  cmp     eax, 4000h
0x14003fac8  jz      short loc_14003FA6D
0x14003faca  cmp     eax, 5000h
0x14003facf  jz      short loc_14003FA6D
0x14003fad1  mov     ecx, 7000h
0x14003fad6  cmp     eax, 9000h
0x14003fadb  jnz     loc_14003FBF2
0x14003fae1  mov     edi, 6
0x14003fae6  jmp     short loc_14003FA6D
0x14003fae8  lea     r9, aErrorReadingDa; "Error reading data"
0x14003faef  mov     r8d, 0BDFh
0x14003faf5  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003fafc  mov     ecx, 1
0x14003fb01  call    AslLogCallPrintf
0x14003fb06  mov     edx, esi
0x14003fb08  mov     rcx, rbp
0x14003fb0b  call    SdbGetTagFromTagID
0x14003fb10  movzx   eax, ax
0x14003fb13  lea     r9, aTagid0x08xTag0; "TagID 0x%08X, Tag %04X not STRINGREF ty"...
0x14003fb1a  mov     [rsp+58h+var_30], eax
0x14003fb1e  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x14003fb25  mov     r8d, 27Ah
0x14003fb2b  mov     [rsp+58h+var_38], esi
0x14003fb2f  mov     ecx, 1
0x14003fb34  call    AslLogCallPrintf
0x14003fb39  xor     eax, eax
0x14003fb3b  jmp     loc_14003FA8C
0x14003fb40  lea     r9, aErrorReadingTa; "Error reading tag data"
0x14003fb47  mov     r8d, 1BEh
0x14003fb4d  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003fb54  mov     ecx, 1
0x14003fb59  call    AslLogCallPrintf
0x14003fb5e  lea     r9, aErrorReadingDa; "Error reading data"
0x14003fb65  mov     r8d, 27Fh
0x14003fb6b  lea     rdx, aSdbpreadstring; "SdbpReadStringRef"
0x14003fb72  mov     ecx, 1
0x14003fb77  call    AslLogCallPrintf
0x14003fb7c  jmp     short loc_14003FB39
0x14003fb7e  mov     [rsp+58h+var_30], r14d
0x14003fb83  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14003fb8a  mov     r8d, 1B7h
0x14003fb90  mov     [rsp+58h+var_38], 4
0x14003fb98  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003fb9f  mov     ecx, 1
0x14003fba4  call    AslLogCallPrintf
0x14003fba9  jmp     short loc_14003FB5E
0x14003fbab  mov     r8d, 64h ; 'd'
0x14003fbb1  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003fbb8  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003fbbf  lea     ecx, [r8-63h]
0x14003fbc3  call    AslLogCallPrintf
0x14003fbc8  jmp     short loc_14003FBEB
0x14003fbca  mov     r8d, 79h ; 'y'
0x14003fbd0  mov     [rsp+58h+var_38], edx
0x14003fbd4  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003fbdb  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003fbe2  lea     ecx, [r8-78h]
0x14003fbe6  call    AslLogCallPrintf
0x14003fbeb  xor     edi, edi
0x14003fbed  jmp     loc_14003FA6D
0x14003fbf2  cmp     eax, ecx
0x14003fbf4  jz      loc_14003FAE1
0x14003fbfa  cmp     eax, 8000h
0x14003fbff  jz      loc_14003FAE1
0x14003fc05  jmp     short loc_14003FBCA
```
