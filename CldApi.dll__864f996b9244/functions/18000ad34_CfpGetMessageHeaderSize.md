# CfpGetMessageHeaderSize

- ea: `0x18000ad34`
- end: `0x18000ad62`
- name: `CfpGetMessageHeaderSize`
- size: `46`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f88`
- `0x18000a0d0`
- `0x18000a234`
- `0x18000a4c8`
- `0x18000a608`
- `0x18000a794`
- `0x18000a8f4`
- `0x18000aa48`

## callees

- `0x18000ad34`

## pseudocode

```c
__int64 __fastcall CfpGetMessageHeaderSize(__int64 a1)
{
  __int64 result; // rax
  _DWORD *v2; // rdx

  result = 232;
  if ( *(_DWORD *)a1 >= 0x20u && *(_QWORD *)(a1 + 24) )
    result = 362;
  if ( *(_DWORD *)a1 >= 0x28u )
  {
    v2 = *(_DWORD **)(a1 + 32);
    if ( v2 )
      return *v2 + (((_DWORD)result + 3) & 0xFFFFFFFC);
  }
  return result;
}

```

## disassembly

```asm
0x18000ad34  cmp     dword ptr [rcx], 20h ; ' '
0x18000ad37  mov     eax, 0E8h
0x18000ad3c  jb      short loc_18000AD4B
0x18000ad3e  cmp     qword ptr [rcx+18h], 0
0x18000ad43  mov     edx, 16Ah
0x18000ad48  cmovnz  eax, edx
0x18000ad4b  cmp     dword ptr [rcx], 28h ; '('
0x18000ad4e  jb      short locret_18000AD61
0x18000ad50  mov     rdx, [rcx+20h]
0x18000ad54  test    rdx, rdx
0x18000ad57  jz      short locret_18000AD61
0x18000ad59  add     eax, 3
0x18000ad5c  and     eax, 0FFFFFFFCh
0x18000ad5f  add     eax, [rdx]
0x18000ad61  retn
```
