# SIPolicyReadBinary

- ea: `0x180028f84`
- end: `0x180029030`
- name: `SIPolicyReadBinary`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025288`
- `0x18002612c`
- `0x18002644c`

## callees

- `0x180028f84`
- `0x180029038`
- `0x18002906c`

## pseudocode

```c
__int64 __fastcall SIPolicyReadBinary(__int64 *a1, _QWORD *a2, unsigned int *a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned int v8; // r11d
  unsigned int v9; // ecx
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v10[0] = 0;
  v11 = 0;
  result = SIPolicyReadPrimitive(a1, 4u, &v11);
  if ( (int)result >= 0 )
  {
    v7 = v11 + (-v11 & 3);
    if ( v7 < v11 )
    {
      return 3221225621LL;
    }
    else if ( v7 )
    {
      result = SIPolicyReadBytes(a1, v7, v10);
      if ( (int)result >= 0 )
      {
        v9 = v8;
        if ( v8 >= v7 )
        {
LABEL_9:
          *a2 = v10[0];
          result = (unsigned int)result;
          *a3 = v8;
        }
        else
        {
          while ( !*(_BYTE *)(v9 + v10[0]) )
          {
            if ( ++v9 >= v7 )
              goto LABEL_9;
          }
          return 3236495363LL;
        }
      }
    }
    else
    {
      *a2 = 0;
      result = 0;
      *a3 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028f84  push    rbx
0x180028f86  push    rbp
0x180028f87  push    rsi
0x180028f88  push    rdi
0x180028f89  sub     rsp, 38h
0x180028f8d  mov     rdi, r8
0x180028f90  mov     [rsp+58h+var_38], 0
0x180028f99  mov     rsi, rdx
0x180028f9c  mov     [rsp+58h+arg_18], 0
0x180028fa4  lea     r8, [rsp+58h+arg_18]
0x180028fa9  mov     edx, 4
0x180028fae  mov     rbp, rcx
0x180028fb1  call    SIPolicyReadPrimitive
0x180028fb6  test    eax, eax
0x180028fb8  js      short loc_180029027
0x180028fba  mov     r11d, [rsp+58h+arg_18]
0x180028fbf  mov     ebx, r11d
0x180028fc2  neg     ebx
0x180028fc4  and     ebx, 3
0x180028fc7  add     ebx, r11d
0x180028fca  cmp     ebx, r11d
0x180028fcd  jb      short loc_180029022
0x180028fcf  test    ebx, ebx
0x180028fd1  jnz     short loc_180028FE0
0x180028fd3  mov     qword ptr [rsi], 0
0x180028fda  xor     eax, eax
0x180028fdc  mov     [rdi], ebx
0x180028fde  jmp     short loc_180029027
0x180028fe0  mov     edx, ebx
0x180028fe2  lea     r8, [rsp+58h+var_38]
0x180028fe7  mov     rcx, rbp
0x180028fea  call    SIPolicyReadBytes
0x180028fef  mov     edx, eax
0x180028ff1  test    eax, eax
0x180028ff3  js      short loc_180029027
0x180028ff5  mov     r8, [rsp+58h+var_38]
0x180028ffa  mov     ecx, r11d
0x180028ffd  cmp     r11d, ebx
0x180029000  jnb     short loc_180029011
0x180029002  mov     eax, ecx
0x180029004  cmp     byte ptr [rax+r8], 0
0x180029009  jnz     short loc_18002901B
0x18002900b  inc     ecx
0x18002900d  cmp     ecx, ebx
0x18002900f  jb      short loc_180029002
0x180029011  mov     [rsi], r8
0x180029014  mov     eax, edx
0x180029016  mov     [rdi], r11d
0x180029019  jmp     short loc_180029027
0x18002901b  mov     eax, 0C0E90003h
0x180029020  jmp     short loc_180029027
0x180029022  mov     eax, 0C0000095h
0x180029027  add     rsp, 38h
0x18002902b  pop     rdi
0x18002902c  pop     rsi
0x18002902d  pop     rbp
0x18002902e  pop     rbx
0x18002902f  retn
```
