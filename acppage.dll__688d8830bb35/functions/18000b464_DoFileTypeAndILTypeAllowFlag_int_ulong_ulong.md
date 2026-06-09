# DoFileTypeAndILTypeAllowFlag(int,ulong,ulong)

- ea: `0x18000b464`
- end: `0x18000b4c9`
- name: `?DoFileTypeAndILTypeAllowFlag@@YAHHKK@Z`
- size: `101`
- prototype: `__int64 __fastcall(int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b654`
- `0x18000f0dc`
- `0x18000f130`

## callees

- `0x18000b464`

## pseudocode

```c
__int64 __fastcall DoFileTypeAndILTypeAllowFlag(int a1, int a2, int a3)
{
  unsigned int v3; // r10d
  unsigned int v5; // r9d
  __int64 v6; // rcx
  int v7; // ecx

  v3 = 0;
  v5 = 1;
  while ( 1 )
  {
    v6 = 54LL * v3;
    if ( *(_DWORD *)&a640x480[v6 + 50] == a1 )
      break;
    if ( ++v3 >= 0xD )
      return 0;
  }
  v7 = *(_DWORD *)&a640x480[v6 + 52];
  if ( (v7 & a2) == 0 && (!a3 || ((a3 & 2) == 0 || (v7 & 1) == 0) && ((a3 & 0x20001) == 0 || (v7 & 3) == 0)) )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x18000b464  mov     [rsp+arg_0], rbx
0x18000b469  xor     r10d, r10d
0x18000b46c  lea     rbx, a640x480; "640X480"
0x18000b473  mov     r11d, ecx
0x18000b476  lea     r9d, [r10+1]
0x18000b47a  mov     eax, r10d
0x18000b47d  imul    rcx, rax, 6Ch ; 'l'
0x18000b481  cmp     [rcx+rbx+64h], r11d
0x18000b486  jz      short loc_18000B493
0x18000b488  add     r10d, r9d
0x18000b48b  cmp     r10d, 0Dh
0x18000b48f  jb      short loc_18000B47A
0x18000b491  jmp     short loc_18000B4BD
0x18000b493  mov     ecx, [rcx+rbx+68h]
0x18000b497  test    edx, ecx
0x18000b499  jnz     short loc_18000B4C0
0x18000b49b  test    r8d, r8d
0x18000b49e  jz      short loc_18000B4BD
0x18000b4a0  test    r8b, 2
0x18000b4a4  jz      short loc_18000B4AF
0x18000b4a6  mov     eax, ecx
0x18000b4a8  and     eax, r9d
0x18000b4ab  test    al, al
0x18000b4ad  jnz     short loc_18000B4C0
0x18000b4af  test    r8d, 20001h
0x18000b4b6  jz      short loc_18000B4BD
0x18000b4b8  test    cl, 3
0x18000b4bb  jnz     short loc_18000B4C0
0x18000b4bd  xor     r9d, r9d
0x18000b4c0  mov     rbx, [rsp+arg_0]
0x18000b4c5  mov     eax, r9d
0x18000b4c8  retn
```
