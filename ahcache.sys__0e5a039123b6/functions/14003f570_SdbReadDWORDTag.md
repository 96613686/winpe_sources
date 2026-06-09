# SdbReadDWORDTag

- ea: `0x14003f570`
- end: `0x14003f7e6`
- name: `SdbReadDWORDTag`
- size: `630`
- prototype: ``
- caller_count: `16`
- callee_count: `6`
- tags: ``

## callers

- `0x140002d38`
- `0x140005f1c`
- `0x14002e064`
- `0x14002ebc0`
- `0x14002f900`
- `0x14002fd64`
- `0x140039898`
- `0x140039b18`
- `0x14003af10`
- `0x14003c710`
- `0x140040c08`
- `0x1400413ec`
- `0x140042680`
- `0x14004a1ac`
- `0x14004b664`
- `0x14005289c`

## callees

- `0x1400055d4`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14003f570`
- `0x14004007c`

## string_xrefs

- `0x14003f67c`: `Error reading data`
- `0x14003f6b2`: `SdbReadDWORDTag`
- `0x14003f730`: `SdbpReadTagData`
- `0x14003f762`: `SdbpReadTagData`
- `0x14003f723`: `Error reading tag data`
- `0x14003f775`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbReadDWORDTag(__int64 a1, __int64 a2, unsigned int a3)
{
  int v4; // esi
  unsigned int v5; // ebx
  unsigned int TagDataSize; // eax
  unsigned int v8; // ebp
  int v9; // ecx
  unsigned int v11; // eax
  unsigned __int16 TagFromTagID; // ax
  unsigned __int16 v13; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = a3;
  v4 = 2;
  v13 = 0;
  v5 = a2;
  if ( !(unsigned int)SdbpReadMappedData(a1, a2, &v13, 2) )
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_15;
  }
  if ( (v13 & 0xF000) != 0x4000 )
  {
LABEL_15:
    TagFromTagID = SdbGetTagFromTagID(a1, v5);
    AslLogCallPrintf(1, "SdbReadDWORDTag", 179, "TagID 0x%X, Tag 0x%X not of the expected type", v5, TagFromTagID);
    return a3;
  }
  TagDataSize = SdbGetTagDataSize(a1, v5);
  v8 = TagDataSize;
  if ( TagDataSize > 4 )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, TagDataSize);
    return a3;
  }
  v13 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, v5, &v13, 2) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v4 = 0;
    goto LABEL_9;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v11 = v13 & 0xF000;
    if ( v11 == 36864 )
      goto LABEL_13;
    if ( v11 == 24576 )
      goto LABEL_9;
    if ( v11 > 0x4000 )
    {
      if ( v11 == 20480 )
        goto LABEL_9;
      if ( v11 == 28672 || v11 == 0x8000 )
      {
LABEL_13:
        v4 = 6;
        goto LABEL_9;
      }
    }
    else if ( v11 == 0x4000 || v11 == 4096 || v11 == 0x2000 || v11 == 12288 )
    {
      goto LABEL_9;
    }
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v13);
    v4 = 0;
    goto LABEL_9;
  }
  v9 = 6;
  if ( (v13 & 0xF000u) < 0x7000 )
    v9 = 2;
  v4 = v9;
LABEL_9:
  if ( !(unsigned int)SdbpReadMappedData(a1, v4 + v5, &v14, v8) )
  {
    AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
    return a3;
  }
  return v14;
}

```

## disassembly

```asm
0x14003f570  mov     [rsp+arg_8], rbx
0x14003f575  push    rsi
0x14003f576  push    rdi
0x14003f577  push    r12
0x14003f579  push    r14
0x14003f57b  push    r15
0x14003f57d  sub     rsp, 30h
0x14003f581  mov     r14d, r8d
0x14003f584  mov     [rsp+58h+arg_18], r8d
0x14003f589  xor     eax, eax
0x14003f58b  lea     r8, [rsp+58h+arg_10]
0x14003f590  mov     esi, 2
0x14003f595  mov     [rsp+58h+arg_10], ax
0x14003f59a  mov     r9d, esi
0x14003f59d  mov     ebx, edx
0x14003f59f  mov     rdi, rcx
0x14003f5a2  call    SdbpReadMappedData
0x14003f5a7  test    eax, eax
0x14003f5a9  jz      loc_14003F67C
0x14003f5af  movzx   eax, [rsp+58h+arg_10]
0x14003f5b4  mov     r15d, 0F000h
0x14003f5ba  and     ax, r15w
0x14003f5be  mov     r12d, 4000h
0x14003f5c4  cmp     ax, r12w
0x14003f5c8  jnz     loc_14003F69A
0x14003f5ce  mov     edx, ebx
0x14003f5d0  mov     [rsp+58h+arg_0], rbp
0x14003f5d5  mov     rcx, rdi
0x14003f5d8  call    SdbGetTagDataSize
0x14003f5dd  mov     ebp, eax
0x14003f5df  cmp     eax, 4
0x14003f5e2  ja      loc_14003F749
0x14003f5e8  xor     eax, eax
0x14003f5ea  lea     r8, [rsp+58h+arg_10]
0x14003f5ef  mov     r9d, esi
0x14003f5f2  mov     [rsp+58h+arg_10], ax
0x14003f5f7  mov     edx, ebx
0x14003f5f9  mov     rcx, rdi
0x14003f5fc  call    SdbpReadMappedData
0x14003f601  test    eax, eax
0x14003f603  jz      loc_14003F775
0x14003f609  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003f60e  test    eax, eax
0x14003f610  jnz     short loc_14003F664
0x14003f612  movzx   eax, [rsp+58h+arg_10]
0x14003f617  mov     edx, 7000h
0x14003f61c  and     ax, r15w
0x14003f620  mov     ecx, 6
0x14003f625  cmp     ax, dx
0x14003f628  cmovb   ecx, esi
0x14003f62b  mov     esi, ecx
0x14003f62d  lea     edx, [rsi+rbx]
0x14003f630  mov     r9d, ebp
0x14003f633  lea     r8, [rsp+58h+arg_18]
0x14003f638  mov     rcx, rdi
0x14003f63b  call    SdbpReadMappedData
0x14003f640  test    eax, eax
0x14003f642  jz      loc_14003F723
0x14003f648  mov     eax, [rsp+58h+arg_18]
0x14003f64c  mov     rbp, [rsp+58h+arg_0]
0x14003f651  mov     rbx, [rsp+58h+arg_8]
0x14003f656  add     rsp, 30h
0x14003f65a  pop     r15
0x14003f65c  pop     r14
0x14003f65e  pop     r12
0x14003f660  pop     rdi
0x14003f661  pop     rsi
0x14003f662  retn
0x14003f664  movzx   ecx, [rsp+58h+arg_10]
0x14003f669  mov     eax, ecx
0x14003f66b  and     eax, r15d
0x14003f66e  cmp     eax, 9000h
0x14003f673  jnz     short loc_14003F6E3
0x14003f675  mov     esi, 6
0x14003f67a  jmp     short loc_14003F62D
0x14003f67c  lea     r9, aErrorReadingDa; "Error reading data"
0x14003f683  mov     r8d, 0BDFh
0x14003f689  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003f690  mov     ecx, 1
0x14003f695  call    AslLogCallPrintf
0x14003f69a  mov     edx, ebx
0x14003f69c  mov     rcx, rdi
0x14003f69f  call    SdbGetTagFromTagID
0x14003f6a4  movzx   eax, ax
0x14003f6a7  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x14003f6ae  mov     [rsp+58h+var_30], eax
0x14003f6b2  lea     rdx, aSdbreaddwordta; "SdbReadDWORDTag"
0x14003f6b9  mov     r8d, 0B3h
0x14003f6bf  mov     [rsp+58h+var_38], ebx
0x14003f6c3  mov     ecx, 1
0x14003f6c8  call    AslLogCallPrintf
0x14003f6cd  mov     rbx, [rsp+58h+arg_8]
0x14003f6d2  mov     eax, r14d
0x14003f6d5  add     rsp, 30h
0x14003f6d9  pop     r15
0x14003f6db  pop     r14
0x14003f6dd  pop     r12
0x14003f6df  pop     rdi
0x14003f6e0  pop     rsi
0x14003f6e1  retn
0x14003f6e3  cmp     eax, 6000h
0x14003f6e8  jz      loc_14003F62D
0x14003f6ee  cmp     eax, r12d
0x14003f6f1  ja      loc_14003F79A
0x14003f6f7  jz      loc_14003F62D
0x14003f6fd  cmp     eax, 1000h
0x14003f702  jz      loc_14003F62D
0x14003f708  cmp     eax, 2000h
0x14003f70d  jz      loc_14003F62D
0x14003f713  cmp     eax, 3000h
0x14003f718  jz      loc_14003F62D
0x14003f71e  jmp     loc_14003F7BD
0x14003f723  lea     r9, aErrorReadingTa; "Error reading tag data"
0x14003f72a  mov     r8d, 1BEh
0x14003f730  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003f737  mov     ecx, 1
0x14003f73c  call    AslLogCallPrintf
0x14003f741  mov     eax, r14d
0x14003f744  jmp     loc_14003F64C
0x14003f749  mov     [rsp+58h+var_30], ebp
0x14003f74d  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14003f754  mov     r8d, 1B7h
0x14003f75a  mov     [rsp+58h+var_38], 4
0x14003f762  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14003f769  mov     ecx, 1
0x14003f76e  call    AslLogCallPrintf
0x14003f773  jmp     short loc_14003F741
0x14003f775  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003f77c  mov     r8d, 64h ; 'd'
0x14003f782  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f789  mov     ecx, 1
0x14003f78e  call    AslLogCallPrintf
0x14003f793  xor     esi, esi
0x14003f795  jmp     loc_14003F62D
0x14003f79a  cmp     eax, 5000h
0x14003f79f  jz      loc_14003F62D
0x14003f7a5  mov     edx, 7000h
0x14003f7aa  cmp     eax, edx
0x14003f7ac  jz      loc_14003F675
0x14003f7b2  cmp     eax, 8000h
0x14003f7b7  jz      loc_14003F675
0x14003f7bd  mov     [rsp+58h+var_38], ecx
0x14003f7c1  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003f7c8  mov     ecx, 1
0x14003f7cd  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f7d4  mov     r8d, 79h ; 'y'
0x14003f7da  call    AslLogCallPrintf
0x14003f7df  xor     esi, esi
0x14003f7e1  jmp     loc_14003F62D
```
