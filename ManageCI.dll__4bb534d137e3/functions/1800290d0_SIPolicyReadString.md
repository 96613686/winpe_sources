# SIPolicyReadString

- ea: `0x1800290d0`
- end: `0x180029192`
- name: `SIPolicyReadString`
- size: `194`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025288`
- `0x180025b20`
- `0x18002612c`
- `0x18002644c`
- `0x180026938`
- `0x180026ac0`
- `0x180026b44`
- `0x180026d30`

## callees

- `0x180029038`
- `0x18002906c`
- `0x1800290d0`

## pseudocode

```c
__int64 __fastcall SIPolicyReadString(__int64 *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rcx
  int v6; // r11d
  unsigned __int64 v7; // rsi
  __int16 v8; // r11
  __int64 v9; // rcx
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+50h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v10[0] = 0;
  v11 = 0;
  result = SIPolicyReadPrimitive(a1, 4u, &v11);
  if ( (int)result >= 0 )
  {
    if ( v11 > 0xFFFE )
      return 3236495363LL;
    result = SIPolicyReadBytes(a1, v11, v10);
    if ( (int)result >= 0 )
    {
      v7 = (-v6 & 3) + 4LL;
      result = SIPolicyReadBytes(v5, v7, &v12);
      if ( (int)result >= 0 )
      {
        v9 = 0;
        while ( !*(_BYTE *)(v9 + v12) )
        {
          v9 = (unsigned int)(v9 + 1);
          if ( (unsigned int)v9 >= v7 )
          {
            *(_QWORD *)(a2 + 8) = v10[0];
            result = (unsigned int)result;
            *(_WORD *)a2 = v8;
            *(_WORD *)(a2 + 2) = v8;
            return result;
          }
        }
        return 3236495363LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800290d0  mov     rax, rsp
0x1800290d3  mov     [rax+8], rbx
0x1800290d7  mov     [rax+10h], rsi
0x1800290db  push    rdi
0x1800290dc  sub     rsp, 30h
0x1800290e0  mov     rbx, rdx
0x1800290e3  mov     qword ptr [rax+20h], 0
0x1800290eb  mov     edx, 4
0x1800290f0  mov     qword ptr [rax-18h], 0
0x1800290f8  lea     r8, [rax+18h]
0x1800290fc  mov     dword ptr [rax+18h], 0
0x180029103  mov     rdi, rcx
0x180029106  call    SIPolicyReadPrimitive
0x18002910b  test    eax, eax
0x18002910d  js      short loc_180029182
0x18002910f  mov     r11d, [rsp+38h+arg_10]
0x180029114  cmp     r11d, 0FFFEh
0x18002911b  ja      short loc_18002917D
0x18002911d  mov     edx, r11d
0x180029120  lea     r8, [rsp+38h+var_18]
0x180029125  mov     rcx, rdi
0x180029128  call    SIPolicyReadBytes
0x18002912d  test    eax, eax
0x18002912f  js      short loc_180029182
0x180029131  mov     esi, r11d
0x180029134  lea     r8, [rsp+38h+arg_18]
0x180029139  neg     esi
0x18002913b  and     esi, 3
0x18002913e  add     rsi, 4
0x180029142  mov     rdx, rsi
0x180029145  call    SIPolicyReadBytes
0x18002914a  mov     edx, eax
0x18002914c  test    eax, eax
0x18002914e  js      short loc_180029182
0x180029150  mov     r8, [rsp+38h+arg_18]
0x180029155  xor     ecx, ecx
0x180029157  cmp     byte ptr [rcx+r8], 0
0x18002915c  jnz     short loc_18002917D
0x18002915e  inc     ecx
0x180029160  mov     eax, ecx
0x180029162  cmp     rax, rsi
0x180029165  jb      short loc_180029157
0x180029167  mov     rax, [rsp+38h+var_18]
0x18002916c  mov     [rbx+8], rax
0x180029170  mov     eax, edx
0x180029172  mov     [rbx], r11w
0x180029176  mov     [rbx+2], r11w
0x18002917b  jmp     short loc_180029182
0x18002917d  mov     eax, 0C0E90003h
0x180029182  mov     rbx, [rsp+38h+arg_0]
0x180029187  mov     rsi, [rsp+38h+arg_8]
0x18002918c  add     rsp, 30h
0x180029190  pop     rdi
0x180029191  retn
```
