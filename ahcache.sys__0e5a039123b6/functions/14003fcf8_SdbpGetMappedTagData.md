# SdbpGetMappedTagData

- ea: `0x14003fcf8`
- end: `0x14003fe6b`
- name: `SdbpGetMappedTagData`
- size: `371`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x140024994`
- `0x140024fc0`
- `0x14002de90`
- `0x14003ada0`
- `0x14003af10`
- `0x14003c19c`
- `0x14003ef10`

## callees

- `0x1400055d4`
- `0x14003e248`
- `0x14003e364`
- `0x14003fcf8`

## string_xrefs

- `0x14003fe24`: `Trying to read mapped data past the end of the database offset 0x%x size 0x%x`
- `0x14003fdd2`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbpGetMappedTagData(__int64 a1, unsigned int a2)
{
  int v4; // ebx
  unsigned int v5; // ecx
  __int64 v6; // rbx
  int v8; // eax
  unsigned __int16 v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = 0;
  v4 = 2;
  if ( !(unsigned int)SdbpReadMappedData(a1, a2, &v9, 2u) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
LABEL_16:
    v4 = 0;
    goto LABEL_4;
  }
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v4 = (v9 & 0xF000u) < 0x7000 ? 2 : 6;
    goto LABEL_4;
  }
  v8 = v9 & 0xF000;
  if ( v8 != 24576 && v8 != 4096 && v8 != 0x2000 && v8 != 12288 && v8 != 0x4000 && v8 != 20480 )
  {
    if ( v8 == 36864 || v8 == 28672 || v8 == 0x8000 )
    {
      v4 = 6;
      goto LABEL_4;
    }
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v9);
    goto LABEL_16;
  }
LABEL_4:
  v5 = *(_DWORD *)(a1 + 20);
  if ( v4 + a2 >= v5 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetMappedData",
      915,
      "Trying to read mapped data past the end of the database offset 0x%x size 0x%x",
      v4 + a2,
      v5);
    v6 = 0;
    goto LABEL_21;
  }
  v6 = v4 + a2 + *(_QWORD *)(a1 + 8);
  if ( !v6 )
LABEL_21:
    AslLogCallPrintf(1, "SdbpGetMappedTagData", 550, "Error getting ptr to tag data");
  return v6;
}

```

## disassembly

```asm
0x14003fcf8  mov     [rsp+arg_0], rbx
0x14003fcfd  mov     [rsp+arg_10], rsi
0x14003fd02  push    rdi
0x14003fd03  sub     rsp, 30h
0x14003fd07  xor     eax, eax
0x14003fd09  lea     r8, [rsp+38h+arg_8]
0x14003fd0e  mov     esi, edx
0x14003fd10  mov     [rsp+38h+arg_8], ax
0x14003fd15  mov     rdi, rcx
0x14003fd18  lea     ebx, [rax+2]
0x14003fd1b  mov     r9d, ebx
0x14003fd1e  call    SdbpReadMappedData
0x14003fd23  test    eax, eax
0x14003fd25  jz      loc_14003FDCC
0x14003fd2b  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003fd30  mov     ecx, 0F000h
0x14003fd35  test    eax, eax
0x14003fd37  jnz     short loc_14003FD86
0x14003fd39  movzx   eax, [rsp+38h+arg_8]
0x14003fd3e  mov     ebx, 6
0x14003fd43  and     ax, cx
0x14003fd46  mov     ecx, 7000h
0x14003fd4b  cmp     ax, cx
0x14003fd4e  sbb     eax, eax
0x14003fd50  and     eax, 0FFFFFFFCh
0x14003fd53  add     ebx, eax
0x14003fd55  mov     ecx, [rdi+14h]
0x14003fd58  lea     eax, [rbx+rsi]
0x14003fd5b  cmp     eax, ecx
0x14003fd5d  jnb     loc_14003FE20
0x14003fd63  mov     rbx, [rdi+8]
0x14003fd67  mov     edx, eax
0x14003fd69  add     rbx, rdx
0x14003fd6c  jz      loc_14003FE48
0x14003fd72  mov     rsi, [rsp+38h+arg_10]
0x14003fd77  mov     rax, rbx
0x14003fd7a  mov     rbx, [rsp+38h+arg_0]
0x14003fd7f  add     rsp, 30h
0x14003fd83  pop     rdi
0x14003fd84  retn
0x14003fd86  movzx   edx, [rsp+38h+arg_8]
0x14003fd8b  mov     eax, edx
0x14003fd8d  and     eax, ecx
0x14003fd8f  cmp     eax, 6000h
0x14003fd94  jz      short loc_14003FD55
0x14003fd96  cmp     eax, 1000h
0x14003fd9b  jz      short loc_14003FD55
0x14003fd9d  cmp     eax, 2000h
0x14003fda2  jz      short loc_14003FD55
0x14003fda4  cmp     eax, 3000h
0x14003fda9  jz      short loc_14003FD55
0x14003fdab  cmp     eax, 4000h
0x14003fdb0  jz      short loc_14003FD55
0x14003fdb2  cmp     eax, 5000h
0x14003fdb7  jz      short loc_14003FD55
0x14003fdb9  mov     ecx, 7000h
0x14003fdbe  cmp     eax, 9000h
0x14003fdc3  jnz     short loc_14003FE13
0x14003fdc5  mov     ebx, 6
0x14003fdca  jmp     short loc_14003FD55
0x14003fdcc  mov     r8d, 64h ; 'd'
0x14003fdd2  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003fdd9  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003fde0  lea     ecx, [r8-63h]
0x14003fde4  call    AslLogCallPrintf
0x14003fde9  jmp     short loc_14003FE0C
0x14003fdeb  mov     r8d, 79h ; 'y'
0x14003fdf1  mov     [rsp+38h+var_18], edx
0x14003fdf5  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003fdfc  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003fe03  lea     ecx, [r8-78h]
0x14003fe07  call    AslLogCallPrintf
0x14003fe0c  xor     ebx, ebx
0x14003fe0e  jmp     loc_14003FD55
0x14003fe13  cmp     eax, ecx
0x14003fe15  jz      short loc_14003FDC5
0x14003fe17  cmp     eax, 8000h
0x14003fe1c  jz      short loc_14003FDC5
0x14003fe1e  jmp     short loc_14003FDEB
0x14003fe20  mov     [rsp+38h+var_10], ecx
0x14003fe24  lea     r9, aTryingToReadMa; "Trying to read mapped data past the end"...
0x14003fe2b  mov     ecx, 1
0x14003fe30  mov     [rsp+38h+var_18], eax
0x14003fe34  mov     r8d, 393h
0x14003fe3a  lea     rdx, aSdbpgetmappedd; "SdbpGetMappedData"
0x14003fe41  call    AslLogCallPrintf
0x14003fe46  xor     ebx, ebx
0x14003fe48  lea     r9, aErrorGettingPt; "Error getting ptr to tag data"
0x14003fe4f  mov     r8d, 226h
0x14003fe55  lea     rdx, aSdbpgetmappedt_0; "SdbpGetMappedTagData"
0x14003fe5c  mov     ecx, 1
0x14003fe61  call    AslLogCallPrintf
0x14003fe66  jmp     loc_14003FD72
```
