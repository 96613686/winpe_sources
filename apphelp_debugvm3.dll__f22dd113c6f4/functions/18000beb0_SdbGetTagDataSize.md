# SdbGetTagDataSize

- ea: `0x18000beb0`
- end: `0x18000c158`
- name: `SdbGetTagDataSize`
- size: `680`
- prototype: ``
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b7f8`
- `0x18000d570`
- `0x18000ef54`
- `0x180011968`
- `0x180011d28`
- `0x18002d86c`
- `0x180036100`
- `0x180038978`
- `0x1800407e0`
- `0x180041adc`
- `0x180042b6c`
- `0x180042ee4`
- `0x180049c30`
- `0x18004c3a0`
- `0x18004cfa0`
- `0x18004e5d4`
- `0x1800504a4`

## callees

- `0x18000beb0`
- `0x18000ef24`
- `0x18000efe0`
- `0x18000f080`
- `0x18000f114`

## string_xrefs

- `0x18000bf78`: `SdbpReadMappedData`
- `0x18000c0ef`: `SdbpReadMappedData`
- `0x18000bf49`: `Error reading size data [%x]`
- `0x18000bf86`: `Error reading size data [%x]`
- `0x18000c020`: `Error reading size data`
- `0x18000c113`: `Error reading size data`
- `0x18000c0e4`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbGetTagDataSize(__int64 a1, __int64 a2)
{
  int v2; // r13d
  unsigned __int16 TagFromTagID; // ax
  int v5; // r15d
  int v6; // ebx
  __int64 v7; // rcx
  unsigned int v8; // r8d
  __int64 result; // rax
  __int64 v10; // [rsp+20h] [rbp-38h]
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF

  v2 = a2;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v5 = TagFromTagID;
  v6 = TagFromTagID & 0xF000;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v6 != 36864 )
    {
      switch ( v6 )
      {
        case 16384:
          goto LABEL_14;
        case 20480:
          result = 8;
          goto LABEL_6;
        case 4096:
          result = 0;
          goto LABEL_6;
        case 24576:
LABEL_14:
          result = 4;
          goto LABEL_6;
        case 12288:
          result = 2;
          goto LABEL_6;
        case 8192:
          result = 1;
          goto LABEL_6;
      }
      if ( v6 != 28672 && v6 != 0x8000 )
      {
        AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v5);
        return 0x20000000;
      }
    }
    v7 = (unsigned int)(v2 + 2);
    if ( (unsigned int)(v2 + 6) < 4 )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
    }
    else
    {
      v8 = *(_DWORD *)(a1 + 20);
      if ( v8 >= v2 + 6 )
      {
        result = *(unsigned int *)(v7 + *(_QWORD *)(a1 + 8));
        goto LABEL_6;
      }
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v7,
        4,
        v8);
    }
    AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
    result = 0x20000000;
LABEL_6:
    if ( (int)result + v2 >= (unsigned int)result && (unsigned int)(result + v2) <= *(_DWORD *)(a1 + 20) )
      return result;
    LODWORD(v10) = -1073741675;
    AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", v10);
    return 0x20000000;
  }
  switch ( v6 )
  {
    case 4096:
      result = 0;
      break;
    case 8192:
      result = 1;
      break;
    case 12288:
      result = 2;
      break;
    case 16384:
      goto LABEL_42;
    case 20480:
      result = 8;
      break;
    case 24576:
LABEL_42:
      result = 4;
      break;
    default:
      v11 = 0;
      if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)(v2 + 2), &v11, 4) )
        AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
      result = v11;
      break;
  }
  if ( (int)result + v2 < (unsigned int)result || (unsigned int)(result + v2) > *(_DWORD *)(a1 + 20) )
  {
    AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
    return 0x20000000;
  }
  return result;
}

```

## disassembly

```asm
0x18000beb0  mov     [rsp+arg_0], rbx
0x18000beb5  mov     [rsp+arg_10], rdi
0x18000beba  push    r13
0x18000bebc  push    r14
0x18000bebe  push    r15
0x18000bec0  sub     rsp, 40h
0x18000bec4  mov     r13d, edx
0x18000bec7  mov     r14, rcx
0x18000beca  call    SdbGetTagFromTagID
0x18000becf  movzx   r15d, ax
0x18000bed3  mov     ebx, r15d
0x18000bed6  and     ebx, 0F000h
0x18000bedc  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000bee1  mov     edi, 1
0x18000bee6  test    eax, eax
0x18000bee8  jz      loc_18000C004
0x18000beee  cmp     ebx, 9000h
0x18000bef4  jnz     loc_18000BFB3
0x18000befa  lea     ecx, [r13+2]
0x18000befe  mov     eax, 4
0x18000bf03  lea     edx, [rcx+4]
0x18000bf06  cmp     edx, eax
0x18000bf08  jb      short loc_18000BF6B
0x18000bf0a  mov     r8d, [r14+14h]
0x18000bf0e  cmp     r8d, edx
0x18000bf11  jb      loc_18000C0DF
0x18000bf17  mov     rax, [r14+8]
0x18000bf1b  mov     eax, [rcx+rax]
0x18000bf1e  lea     ecx, [rax+r13]
0x18000bf22  cmp     ecx, eax
0x18000bf24  jb      short loc_18000BF41
0x18000bf26  cmp     ecx, [r14+14h]
0x18000bf2a  ja      short loc_18000BF41
0x18000bf2c  mov     rbx, [rsp+58h+arg_0]
0x18000bf31  mov     rdi, [rsp+58h+arg_10]
0x18000bf36  add     rsp, 40h
0x18000bf3a  pop     r15
0x18000bf3c  pop     r14
0x18000bf3e  pop     r13
0x18000bf40  retn
0x18000bf41  mov     dword ptr [rsp+58h+var_38], 0C0000095h
0x18000bf49  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000bf50  mov     r8d, 149h
0x18000bf56  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000bf5d  mov     ecx, edi
0x18000bf5f  call    AslLogCallPrintf
0x18000bf64  mov     eax, 20000000h
0x18000bf69  jmp     short loc_18000BF2C
0x18000bf6b  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000bf72  mov     r8d, 357h
0x18000bf78  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000bf7f  mov     ecx, edi
0x18000bf81  call    AslLogCallPrintf
0x18000bf86  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x18000bf8d  mov     dword ptr [rsp+58h+var_38], 0C0000023h
0x18000bf95  mov     r8d, 137h
0x18000bf9b  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000bfa2  mov     ecx, edi
0x18000bfa4  call    AslLogCallPrintf
0x18000bfa9  mov     eax, 20000000h
0x18000bfae  jmp     loc_18000BF1E
0x18000bfb3  cmp     ebx, 4000h
0x18000bfb9  jnz     short loc_18000BFC5
0x18000bfbb  mov     eax, 4
0x18000bfc0  jmp     loc_18000BF1E
0x18000bfc5  cmp     ebx, 5000h
0x18000bfcb  jnz     short loc_18000BFD7
0x18000bfcd  mov     eax, 8
0x18000bfd2  jmp     loc_18000BF1E
0x18000bfd7  cmp     ebx, 1000h
0x18000bfdd  jz      short loc_18000BFFD
0x18000bfdf  cmp     ebx, 6000h
0x18000bfe5  jz      short loc_18000BFBB
0x18000bfe7  cmp     ebx, 3000h
0x18000bfed  jnz     loc_18000C0A8
0x18000bff3  mov     eax, 2
0x18000bff8  jmp     loc_18000BF1E
0x18000bffd  xor     eax, eax
0x18000bfff  jmp     loc_18000BF1E
0x18000c004  cmp     ebx, 1000h
0x18000c00a  jnz     short loc_18000C040
0x18000c00c  xor     eax, eax
0x18000c00e  lea     ecx, [rax+r13]
0x18000c012  cmp     ecx, eax
0x18000c014  jb      short loc_18000C020
0x18000c016  cmp     ecx, [r14+14h]
0x18000c01a  jbe     loc_18000BF2C
0x18000c020  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000c027  mov     r8d, 177h
0x18000c02d  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000c034  mov     ecx, edi
0x18000c036  call    AslLogCallPrintf
0x18000c03b  jmp     loc_18000BF64
0x18000c040  cmp     ebx, 2000h
0x18000c046  jz      loc_18000C151
0x18000c04c  cmp     ebx, 3000h
0x18000c052  jz      loc_18000C147
0x18000c058  cmp     ebx, 4000h
0x18000c05e  jz      loc_18000C13D
0x18000c064  cmp     ebx, 5000h
0x18000c06a  jz      loc_18000C133
0x18000c070  cmp     ebx, 6000h
0x18000c076  jz      loc_18000C13D
0x18000c07c  lea     edx, [r13+2]
0x18000c080  mov     [rsp+58h+arg_8], 0
0x18000c088  mov     r9d, 4
0x18000c08e  lea     r8, [rsp+58h+arg_8]
0x18000c093  mov     rcx, r14
0x18000c096  call    SdbpReadMappedData
0x18000c09b  test    eax, eax
0x18000c09d  jz      short loc_18000C113
0x18000c09f  mov     eax, [rsp+58h+arg_8]
0x18000c0a3  jmp     loc_18000C00E
0x18000c0a8  cmp     ebx, 2000h
0x18000c0ae  jz      short loc_18000C10C
0x18000c0b0  cmp     ebx, 7000h
0x18000c0b6  jz      loc_18000BEFA
0x18000c0bc  cmp     ebx, 8000h
0x18000c0c2  jz      loc_18000BEFA
0x18000c0c8  mov     dword ptr [rsp+58h+var_38], r15d
0x18000c0cd  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x18000c0d4  mov     r8d, 13Eh
0x18000c0da  jmp     loc_18000BF56
0x18000c0df  mov     [rsp+58h+var_28], r8d
0x18000c0e4  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x18000c0eb  mov     [rsp+58h+var_30], eax
0x18000c0ef  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000c0f6  mov     dword ptr [rsp+58h+var_38], ecx
0x18000c0fa  mov     r8d, 35Ch
0x18000c100  mov     ecx, edi
0x18000c102  call    AslLogCallPrintf
0x18000c107  jmp     loc_18000BF86
0x18000c10c  mov     eax, edi
0x18000c10e  jmp     loc_18000BF1E
0x18000c113  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x18000c11a  mov     r8d, 16Ch
0x18000c120  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x18000c127  mov     ecx, edi
0x18000c129  call    AslLogCallPrintf
0x18000c12e  jmp     loc_18000C09F
0x18000c133  mov     eax, 8
0x18000c138  jmp     loc_18000C00E
0x18000c13d  mov     eax, 4
0x18000c142  jmp     loc_18000C00E
0x18000c147  mov     eax, 2
0x18000c14c  jmp     loc_18000C00E
0x18000c151  mov     eax, edi
0x18000c153  jmp     loc_18000C00E
```
