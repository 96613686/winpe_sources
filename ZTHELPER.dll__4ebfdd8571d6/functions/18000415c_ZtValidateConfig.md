# ZtValidateConfig

- ea: `0x18000415c`
- end: `0x18000420f`
- name: `ZtValidateConfig`
- size: `179`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004f98`

## callees

- `0x18000415c`
- `0x180015008`

## pseudocode

```c
__int64 __fastcall ZtValidateConfig(__int64 a1)
{
  unsigned int v1; // ebx
  USHORT v2; // dx

  v1 = 0;
  if ( !a1 )
    return 87;
  if ( *(_DWORD *)a1 != 1 )
  {
    v1 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v1;
    v2 = 32;
    goto LABEL_17;
  }
  if ( (*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFE00uLL) != 0 )
  {
    v1 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v1;
    v2 = 33;
    goto LABEL_17;
  }
  if ( *(_DWORD *)(a1 + 16) > 2u )
  {
    v1 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v1;
    v2 = 34;
LABEL_17:
    WPP_SF_d(1026, v2, (ULONGLONG)WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, 87);
    return v1;
  }
  if ( g_fVelocityFixForwarder )
  {
    if ( *(_DWORD *)(a1 + 36) )
    {
      if ( *(_DWORD *)(a1 + 24) )
      {
        v1 = 87;
        if ( (xmmword_18001F260 & 4) != 0 )
        {
          v2 = 35;
          goto LABEL_17;
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000415c  push    rbx
0x18000415e  sub     rsp, 20h
0x180004162  xor     ebx, ebx
0x180004164  test    rcx, rcx
0x180004167  jnz     short loc_180004171
0x180004169  lea     ebx, [rcx+57h]
0x18000416c  jmp     loc_180004207
0x180004171  cmp     dword ptr [rcx], 1
0x180004174  jnz     short loc_1800041E0
0x180004176  test    qword ptr [rcx+8], 0FFFFFFFFFFFFFE00h
0x18000417e  jnz     short loc_1800041C8
0x180004180  cmp     dword ptr [rcx+10h], 2
0x180004184  jbe     short loc_18000419E
0x180004186  mov     r9d, 57h ; 'W'
0x18000418c  mov     ebx, r9d
0x18000418f  test    byte ptr cs:xmmword_18001F260, 4
0x180004196  jz      short loc_180004207
0x180004198  lea     edx, [r9-35h]
0x18000419c  jmp     short loc_1800041F6
0x18000419e  cmp     cs:g_fVelocityFixForwarder, ebx
0x1800041a4  jz      short loc_180004207
0x1800041a6  cmp     [rcx+24h], ebx
0x1800041a9  jz      short loc_180004207
0x1800041ab  cmp     [rcx+18h], ebx
0x1800041ae  jz      short loc_180004207
0x1800041b0  mov     r9d, 57h ; 'W'
0x1800041b6  mov     ebx, r9d
0x1800041b9  test    byte ptr cs:xmmword_18001F260, 4
0x1800041c0  jz      short loc_180004207
0x1800041c2  lea     edx, [r9-34h]
0x1800041c6  jmp     short loc_1800041F6
0x1800041c8  mov     r9d, 57h ; 'W'
0x1800041ce  mov     ebx, r9d
0x1800041d1  test    byte ptr cs:xmmword_18001F260, 4
0x1800041d8  jz      short loc_180004207
0x1800041da  lea     edx, [r9-36h]
0x1800041de  jmp     short loc_1800041F6
0x1800041e0  mov     r9d, 57h ; 'W'
0x1800041e6  mov     ebx, r9d
0x1800041e9  test    byte ptr cs:xmmword_18001F260, 4
0x1800041f0  jz      short loc_180004207
0x1800041f2  lea     edx, [r9-37h]
0x1800041f6  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x1800041fd  mov     ecx, 402h
0x180004202  call    WPP_SF_d
0x180004207  mov     eax, ebx
0x180004209  add     rsp, 20h
0x18000420d  pop     rbx
0x18000420e  retn
```
