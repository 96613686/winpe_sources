# SdbGetTagDataSize

- ea: `0x14004007c`
- end: `0x140040307`
- name: `SdbGetTagDataSize`
- size: `651`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x140024994`
- `0x140024fc0`
- `0x14002db98`
- `0x14002dd74`
- `0x14002fd64`
- `0x14003ada0`
- `0x14003af10`
- `0x14003c19c`
- `0x14003e154`
- `0x14003ef10`
- `0x14003f570`
- `0x14003f9b4`
- `0x14005289c`

## callees

- `0x1400055d4`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14004007c`

## string_xrefs

- `0x1400400f8`: `Error reading size data [%x]`
- `0x140040275`: `Error reading size data [%x]`
- `0x140040215`: `Error reading size data`
- `0x1400402bf`: `Error reading size data`

## pseudocode

```c
__int64 __fastcall SdbGetTagDataSize(__int64 a1, __int64 a2)
{
  int v2; // r14d
  unsigned __int16 TagFromTagID; // ax
  int v5; // r15d
  int v6; // ebx
  __int64 result; // rax
  __int64 v8; // [rsp+20h] [rbp-10h]
  unsigned int v9; // [rsp+58h] [rbp+28h] BYREF

  v2 = a2;
  v9 = 0;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v5 = TagFromTagID;
  v6 = TagFromTagID & 0xF000;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v6 == 0x4000 )
      goto LABEL_3;
    if ( v6 != 36864 )
    {
      switch ( v6 )
      {
        case 20480:
          result = 8;
          goto LABEL_4;
        case 4096:
          result = 0;
          goto LABEL_4;
        case 8192:
          result = 1;
          goto LABEL_4;
        case 12288:
          result = 2;
          goto LABEL_4;
        case 24576:
LABEL_3:
          result = 4;
LABEL_4:
          v9 = result;
LABEL_5:
          if ( (int)result + v2 >= (unsigned int)result && (unsigned int)(result + v2) <= *(_DWORD *)(a1 + 20) )
            return result;
          LODWORD(v8) = -1073741675;
          AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", v8);
          return 0x20000000;
      }
      if ( v6 != 28672 && v6 != 0x8000 )
      {
        AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v5);
        return 0x20000000;
      }
    }
    v9 = 0;
    if ( !(unsigned int)SdbpReadMappedData(a1, v2 + 2, &v9, 4u) )
    {
      v9 = 0x20000000;
      AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
    }
    result = v9;
    goto LABEL_5;
  }
  switch ( v6 )
  {
    case 16384:
      goto LABEL_34;
    case 4096:
      result = 0;
      goto LABEL_35;
    case 8192:
      result = 1;
      goto LABEL_35;
    case 12288:
      result = 2;
      goto LABEL_35;
    case 20480:
      result = 8;
      goto LABEL_35;
    case 24576:
LABEL_34:
      result = 4;
LABEL_35:
      v9 = result;
      goto LABEL_28;
  }
  v9 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, v2 + 2, &v9, 4u) )
    AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
  result = v9;
LABEL_28:
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
0x14004007c  mov     [rsp-18h+arg_0], rbx
0x140040081  mov     [rsp-18h+arg_10], rsi
0x140040086  push    rbp
0x140040087  push    r14
0x140040089  push    r15
0x14004008b  mov     rbp, rsp
0x14004008e  sub     rsp, 30h
0x140040092  mov     r14d, edx
0x140040095  mov     [rbp+arg_8], 0
0x14004009c  mov     rsi, rcx
0x14004009f  call    SdbGetTagFromTagID
0x1400400a4  movzx   r15d, ax
0x1400400a8  mov     ebx, r15d
0x1400400ab  and     ebx, 0F000h
0x1400400b1  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1400400b6  test    eax, eax
0x1400400b8  jz      loc_140040194
0x1400400be  cmp     ebx, 4000h
0x1400400c4  jnz     short loc_14004011D
0x1400400c6  mov     eax, 4
0x1400400cb  mov     [rbp+arg_8], eax
0x1400400ce  lea     ecx, [rax+r14]
0x1400400d2  cmp     ecx, eax
0x1400400d4  jb      short loc_1400400F0
0x1400400d6  cmp     ecx, [rsi+14h]
0x1400400d9  ja      short loc_1400400F0
0x1400400db  mov     rbx, [rsp+30h+arg_0]
0x1400400e0  mov     rsi, [rsp+30h+arg_10]
0x1400400e5  add     rsp, 30h
0x1400400e9  pop     r15
0x1400400eb  pop     r14
0x1400400ed  pop     rbp
0x1400400ee  retn
0x1400400f0  mov     [rsp+30h+var_10], 0C0000095h
0x1400400f8  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x1400400ff  mov     r8d, 149h
0x140040105  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x14004010c  mov     ecx, 1
0x140040111  call    AslLogCallPrintf
0x140040116  mov     eax, 20000000h
0x14004011b  jmp     short loc_1400400DB
0x14004011d  cmp     ebx, 9000h
0x140040123  jz      loc_140040238
0x140040129  cmp     ebx, 5000h
0x14004012f  jz      loc_14004026B
0x140040135  cmp     ebx, 1000h
0x14004013b  jz      loc_1400402B8
0x140040141  cmp     ebx, 2000h
0x140040147  jz      loc_1400402AE
0x14004014d  cmp     ebx, 3000h
0x140040153  jz      loc_1400402A4
0x140040159  cmp     ebx, 6000h
0x14004015f  jz      loc_1400400C6
0x140040165  cmp     ebx, 7000h
0x14004016b  jz      loc_140040238
0x140040171  cmp     ebx, 8000h
0x140040177  jz      loc_140040238
0x14004017d  mov     [rsp+30h+var_10], r15d
0x140040182  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x140040189  mov     r8d, 13Eh
0x14004018f  jmp     loc_140040105
0x140040194  cmp     ebx, 4000h
0x14004019a  jz      loc_140040261
0x1400401a0  cmp     ebx, 1000h
0x1400401a6  jz      loc_140040300
0x1400401ac  cmp     ebx, 2000h
0x1400401b2  jz      loc_1400402F6
0x1400401b8  cmp     ebx, 3000h
0x1400401be  jz      loc_1400402EC
0x1400401c4  cmp     ebx, 5000h
0x1400401ca  jz      loc_1400402E2
0x1400401d0  cmp     ebx, 6000h
0x1400401d6  jz      loc_140040261
0x1400401dc  lea     edx, [r14+2]
0x1400401e0  mov     [rbp+arg_8], 0
0x1400401e7  mov     r9d, 4
0x1400401ed  lea     r8, [rbp+arg_8]
0x1400401f1  mov     rcx, rsi
0x1400401f4  call    SdbpReadMappedData
0x1400401f9  test    eax, eax
0x1400401fb  jz      loc_1400402BF
0x140040201  mov     eax, [rbp+arg_8]
0x140040204  lea     ecx, [rax+r14]
0x140040208  cmp     ecx, eax
0x14004020a  jb      short loc_140040215
0x14004020c  cmp     ecx, [rsi+14h]
0x14004020f  jbe     loc_1400400DB
0x140040215  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x14004021c  mov     r8d, 177h
0x140040222  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x140040229  mov     ecx, 1
0x14004022e  call    AslLogCallPrintf
0x140040233  jmp     loc_140040116
0x140040238  lea     edx, [r14+2]
0x14004023c  mov     [rbp+arg_8], 0
0x140040243  mov     r9d, 4
0x140040249  lea     r8, [rbp+arg_8]
0x14004024d  mov     rcx, rsi
0x140040250  call    SdbpReadMappedData
0x140040255  test    eax, eax
0x140040257  jz      short loc_140040275
0x140040259  mov     eax, [rbp+arg_8]
0x14004025c  jmp     loc_1400400CE
0x140040261  mov     eax, 4
0x140040266  mov     [rbp+arg_8], eax
0x140040269  jmp     short loc_140040204
0x14004026b  mov     eax, 8
0x140040270  jmp     loc_1400400CB
0x140040275  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x14004027c  mov     [rbp+arg_8], 20000000h
0x140040283  mov     r8d, 137h
0x140040289  mov     [rsp+30h+var_10], 0C0000023h
0x140040291  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x140040298  mov     ecx, 1
0x14004029d  call    AslLogCallPrintf
0x1400402a2  jmp     short loc_140040259
0x1400402a4  mov     eax, 2
0x1400402a9  jmp     loc_1400400CB
0x1400402ae  mov     eax, 1
0x1400402b3  jmp     loc_1400400CB
0x1400402b8  xor     eax, eax
0x1400402ba  jmp     loc_1400400CB
0x1400402bf  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x1400402c6  mov     r8d, 16Ch
0x1400402cc  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x1400402d3  mov     ecx, 1
0x1400402d8  call    AslLogCallPrintf
0x1400402dd  jmp     loc_140040201
0x1400402e2  mov     eax, 8
0x1400402e7  jmp     loc_140040266
0x1400402ec  mov     eax, 2
0x1400402f1  jmp     loc_140040266
0x1400402f6  mov     eax, 1
0x1400402fb  jmp     loc_140040266
0x140040300  xor     eax, eax
0x140040302  jmp     loc_140040266
```
