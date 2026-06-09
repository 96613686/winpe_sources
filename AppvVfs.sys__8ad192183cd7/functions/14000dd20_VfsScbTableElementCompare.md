# VfsScbTableElementCompare

- ea: `0x14000dd20`
- end: `0x14000ddd9`
- name: `VfsScbTableElementCompare`
- size: `185`
- prototype: `char __fastcall(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000dd20`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000dd41`
- `ntoskrnl!RtlCompareMemory` at `0x14000dda0`
- `ntoskrnl!RtlCompareMemory` at `0x14000dd41`
- `ntoskrnl!RtlCompareMemory` at `0x14000dda0`
- `ntoskrnl!RtlLengthSid` at `0x14000dd66`
- `ntoskrnl!RtlLengthSid` at `0x14000dd78`
- `ntoskrnl!RtlLengthSid` at `0x14000dd66`
- `ntoskrnl!RtlLengthSid` at `0x14000dd78`

## pseudocode

```c
char __fastcall VfsScbTableElementCompare(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)
{
  SIZE_T v5; // rax
  bool v6; // cf
  SIZE_T v7; // rbx
  ULONG v8; // eax
  SIZE_T v10; // rax

  v5 = RtlCompareMemory(FirstStruct, SecondStruct, 0x20u);
  if ( v5 == 32 )
  {
    v7 = RtlLengthSid(FirstStruct + 32);
    v8 = RtlLengthSid(SecondStruct + 32);
    if ( (unsigned int)v7 < v8 )
      return 0;
    if ( (unsigned int)v7 > v8 )
      return 1;
    v10 = RtlCompareMemory(FirstStruct + 32, SecondStruct + 32, v7);
    if ( v10 == v7 )
      return 2;
    v6 = (unsigned __int8)FirstStruct[v10 + 32] < (unsigned __int8)SecondStruct[v10 + 32];
  }
  else
  {
    v6 = (unsigned __int8)FirstStruct[v5] < (unsigned __int8)SecondStruct[v5];
  }
  return !v6;
}

```

## disassembly

```asm
0x14000dd20  mov     [rsp+arg_0], rbx
0x14000dd25  mov     [rsp+arg_8], rsi
0x14000dd2a  push    rdi
0x14000dd2b  sub     rsp, 20h
0x14000dd2f  mov     rdi, r8
0x14000dd32  mov     rsi, rdx
0x14000dd35  mov     rdx, rdi; Source2
0x14000dd38  mov     rcx, rsi; Source1
0x14000dd3b  mov     r8d, 20h ; ' '; Length
0x14000dd41  call    cs:__imp_RtlCompareMemory
0x14000dd48  nop     dword ptr [rax+rax+00h]
0x14000dd4d  mov     r9, rax
0x14000dd50  cmp     rax, 20h ; ' '
0x14000dd54  jz      short loc_14000DD62
0x14000dd56  mov     cl, [r9+rdi]
0x14000dd5a  xor     eax, eax
0x14000dd5c  cmp     [r9+rsi], cl
0x14000dd60  jmp     short loc_14000DDC5
0x14000dd62  lea     rcx, [rsi+20h]; Sid
0x14000dd66  call    cs:__imp_RtlLengthSid
0x14000dd6d  nop     dword ptr [rax+rax+00h]
0x14000dd72  lea     rcx, [rdi+20h]; Sid
0x14000dd76  mov     ebx, eax
0x14000dd78  call    cs:__imp_RtlLengthSid
0x14000dd7f  nop     dword ptr [rax+rax+00h]
0x14000dd84  cmp     ebx, eax
0x14000dd86  jnb     short loc_14000DD8C
0x14000dd88  xor     eax, eax
0x14000dd8a  jmp     short loc_14000DDC8
0x14000dd8c  jbe     short loc_14000DD95
0x14000dd8e  mov     eax, 1
0x14000dd93  jmp     short loc_14000DDC8
0x14000dd95  mov     r8, rbx; Length
0x14000dd98  lea     rdx, [rdi+20h]; Source2
0x14000dd9c  lea     rcx, [rsi+20h]; Source1
0x14000dda0  call    cs:__imp_RtlCompareMemory
0x14000dda7  nop     dword ptr [rax+rax+00h]
0x14000ddac  mov     rdx, rax
0x14000ddaf  cmp     rax, rbx
0x14000ddb2  jnz     short loc_14000DDBB
0x14000ddb4  mov     eax, 2
0x14000ddb9  jmp     short loc_14000DDC8
0x14000ddbb  mov     cl, [rdi+rdx+20h]
0x14000ddbf  xor     eax, eax
0x14000ddc1  cmp     [rsi+rdx+20h], cl
0x14000ddc5  setnb   al
0x14000ddc8  mov     rbx, [rsp+28h+arg_0]
0x14000ddcd  mov     rsi, [rsp+28h+arg_8]
0x14000ddd2  add     rsp, 20h
0x14000ddd6  pop     rdi
0x14000ddd7  retn
```
