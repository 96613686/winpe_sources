# BiIsLinkedToFirmwareVariable

- ea: `0x14001c6e4`
- end: `0x14001c78d`
- name: `BiIsLinkedToFirmwareVariable`
- size: `169`
- prototype: `char __fastcall(__int64, _DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140013b9c`
- `0x140018b54`
- `0x140019990`
- `0x140021c10`

## callees

- `0x140014574`
- `0x14001c3a8`
- `0x14001c6e4`

## pseudocode

```c
char __fastcall BiIsLinkedToFirmwareVariable(__int64 a1, _DWORD *a2)
{
  char v4; // bl
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned int)BiGetFirmwareType(0) != 2 )
    return 0;
  v4 = 0;
  v6 = 0;
  if ( (int)BiGetObjectDescription(a1, &v6) >= 0
    && (HIDWORD(v6) & 0xF0000000) == 0x10000000
    && (HIDWORD(v6) & 0xF00000) == 0x100000
    && ((HIDWORD(v6) & 0xFFFFF) != 2
     || !a2
     || *a2 == 285212673
     || *a2 == 301989890
     || *a2 == 301989892
     || *a2 == 369098882) )
  {
    return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x14001c6e4  mov     [rsp+arg_0], rbx
0x14001c6e9  mov     [rsp+arg_8], rsi
0x14001c6ee  push    rdi
0x14001c6ef  sub     rsp, 20h
0x14001c6f3  mov     rsi, rcx
0x14001c6f6  mov     rdi, rdx
0x14001c6f9  xor     ecx, ecx
0x14001c6fb  call    BiGetFirmwareType
0x14001c700  sub     eax, 1
0x14001c703  jz      short loc_14001C779
0x14001c705  cmp     eax, 1
0x14001c708  jnz     short loc_14001C779
0x14001c70a  xor     ebx, ebx
0x14001c70c  lea     rdx, [rsp+28h+arg_10]
0x14001c711  mov     rcx, rsi
0x14001c714  mov     [rsp+28h+arg_10], rbx
0x14001c719  call    BiGetObjectDescription
0x14001c71e  test    eax, eax
0x14001c720  js      short loc_14001C77B
0x14001c722  mov     eax, dword ptr [rsp+28h+arg_10+4]
0x14001c726  mov     ecx, eax
0x14001c728  and     ecx, 0F0000000h
0x14001c72e  cmp     ecx, 10000000h
0x14001c734  jnz     short loc_14001C77B
0x14001c736  mov     ecx, eax
0x14001c738  and     ecx, 0F00000h
0x14001c73e  cmp     ecx, 100000h
0x14001c744  jnz     short loc_14001C77B
0x14001c746  and     eax, 0FFFFFh
0x14001c74b  cmp     eax, 2
0x14001c74e  jnz     short loc_14001C775
0x14001c750  test    rdi, rdi
0x14001c753  jz      short loc_14001C775
0x14001c755  cmp     dword ptr [rdi], 11000001h
0x14001c75b  jz      short loc_14001C775
0x14001c75d  cmp     dword ptr [rdi], 12000002h
0x14001c763  jz      short loc_14001C775
0x14001c765  cmp     dword ptr [rdi], 12000004h
0x14001c76b  jz      short loc_14001C775
0x14001c76d  cmp     dword ptr [rdi], 16000082h
0x14001c773  jnz     short loc_14001C77B
0x14001c775  mov     bl, 1
0x14001c777  jmp     short loc_14001C77B
0x14001c779  xor     ebx, ebx
0x14001c77b  mov     rsi, [rsp+28h+arg_8]
0x14001c780  mov     al, bl
0x14001c782  mov     rbx, [rsp+28h+arg_0]
0x14001c787  add     rsp, 20h
0x14001c78b  pop     rdi
0x14001c78c  retn
```
