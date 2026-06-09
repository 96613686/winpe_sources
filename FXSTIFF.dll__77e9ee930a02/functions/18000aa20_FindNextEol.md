# FindNextEol

- ea: `0x18000aa20`
- end: `0x18000ab57`
- name: `FindNextEol`
- size: `311`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, unsigned __int64, unsigned __int64 *, _BYTE *, int, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b120`
- `0x18000bb50`
- `0x18000cc10`
- `0x18000d060`

## callees

- `0x18000aa20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindNextEol(
        __int64 a1,
        unsigned __int8 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        _BYTE *a5,
        int a6,
        _DWORD *a7)
{
  __int64 v8; // r10
  unsigned __int8 v9; // dl
  int v10; // esi
  unsigned __int64 v11; // r8
  unsigned __int8 v12; // r10
  _DWORD *v13; // rax
  int v14; // edx
  __int64 v15; // rax

  v8 = a2 >> 3;
  *a7 = 0;
  v9 = a2 - 8 * (a2 >> 3);
  v10 = v8 + a1;
  v11 = v8 + a1 + 1;
  v12 = *((_BYTE *)qword_18001BD00 + *(unsigned __int8 *)(v8 + a1));
  if ( v12 <= v9 )
  {
    v12 = v9;
  }
  else if ( a6 == 1 )
  {
    *a7 = 1;
  }
  while ( 1 )
  {
    if ( !*(_BYTE *)v11 )
    {
      while ( (v11 & 3) != 0 )
      {
        if ( *(_BYTE *)v11 )
          goto LABEL_15;
        if ( ++v11 >= a3 )
          return 0;
      }
      v13 = (_DWORD *)v11;
      while ( !*v13 )
      {
        if ( (unsigned __int64)++v13 >= a3 )
          return 0;
      }
      v11 = (unsigned __int64)v13;
      if ( !*(_BYTE *)v13 )
      {
        do
          ++v11;
        while ( !*(_BYTE *)v11 );
      }
    }
LABEL_15:
    if ( v11 >= a3 )
      return 0;
    v14 = *((unsigned __int8 *)qword_180043E20 + *(unsigned __int8 *)v11);
    *a5 = v14;
    if ( v14 + 8 * ((_DWORD)v11 - v10) - (unsigned int)v12 >= 0xB )
      break;
    if ( a6 == 1 )
      *a7 = 1;
    v15 = *(unsigned __int8 *)v11;
    v10 = v11++;
    if ( v11 >= a3 )
      return 0;
    v12 = *((_BYTE *)qword_18001BD00 + v15);
  }
  *a4 = v11 & 0xFFFFFFFFFFFFFFFCuLL;
  *a5 += ((8 * v11) & 0x18) + 1;
  if ( *a5 > 0x1Fu )
  {
    *a5 -= 32;
    *a4 += 4LL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000aa20  push    rbx
0x18000aa22  push    rsi
0x18000aa23  push    rdi
0x18000aa24  push    r15
0x18000aa26  mov     rdi, [rsp+20h+arg_30]
0x18000aa2b  lea     r15, cs:180000000h
0x18000aa32  mov     al, dl
0x18000aa34  mov     r11, r8
0x18000aa37  shr     al, 3
0x18000aa3a  mov     rbx, r9
0x18000aa3d  movzx   r10d, al
0x18000aa41  mov     al, r10b
0x18000aa44  mov     dword ptr [rdi], 0
0x18000aa4a  shl     al, 3
0x18000aa4d  sub     dl, al
0x18000aa4f  lea     rsi, [r10+rcx]
0x18000aa53  movzx   eax, byte ptr [rsi]
0x18000aa56  lea     r8, [rsi+1]
0x18000aa5a  mov     r10b, [rax+r15+1BD00h]
0x18000aa62  cmp     r10b, dl
0x18000aa65  jbe     short loc_18000AA76
0x18000aa67  cmp     [rsp+20h+arg_28], 1
0x18000aa6c  jnz     short loc_18000AA79
0x18000aa6e  mov     dword ptr [rdi], 1
0x18000aa74  jmp     short loc_18000AA79
0x18000aa76  mov     r10b, dl
0x18000aa79  mov     r9, [rsp+20h+arg_20]
0x18000aa7e  cmp     byte ptr [r8], 0
0x18000aa82  jnz     short loc_18000AACA
0x18000aa84  jmp     short loc_18000AA98
0x18000aa86  cmp     byte ptr [r8], 0
0x18000aa8a  jnz     short loc_18000AACA
0x18000aa8c  inc     r8
0x18000aa8f  cmp     r8, r11
0x18000aa92  jnb     loc_18000AB4E
0x18000aa98  test    r8b, 3
0x18000aa9c  jnz     short loc_18000AA86
0x18000aa9e  cmp     dword ptr [r8], 0
0x18000aaa2  mov     rax, r8
0x18000aaa5  jnz     short loc_18000AAB9
0x18000aaa7  add     rax, 4
0x18000aaab  cmp     rax, r11
0x18000aaae  jnb     loc_18000AB4E
0x18000aab4  cmp     dword ptr [rax], 0
0x18000aab7  jz      short loc_18000AAA7
0x18000aab9  cmp     byte ptr [rax], 0
0x18000aabc  mov     r8, rax
0x18000aabf  jnz     short loc_18000AACA
0x18000aac1  inc     r8
0x18000aac4  cmp     byte ptr [r8], 0
0x18000aac8  jz      short loc_18000AAC1
0x18000aaca  cmp     r8, r11
0x18000aacd  jnb     short loc_18000AB4E
0x18000aacf  movzx   eax, byte ptr [r8]
0x18000aad3  mov     ecx, r8d
0x18000aad6  sub     ecx, esi
0x18000aad8  shl     ecx, 3
0x18000aadb  movzx   edx, byte ptr [rax+r15+43E20h]
0x18000aae4  movzx   eax, r10b
0x18000aae8  sub     ecx, eax
0x18000aaea  mov     [r9], dl
0x18000aaed  add     ecx, edx
0x18000aaef  cmp     ecx, 0Bh
0x18000aaf2  jnb     short loc_18000AB1D
0x18000aaf4  cmp     [rsp+20h+arg_28], 1
0x18000aaf9  jnz     short loc_18000AB01
0x18000aafb  mov     dword ptr [rdi], 1
0x18000ab01  movzx   eax, byte ptr [r8]
0x18000ab05  mov     rsi, r8
0x18000ab08  inc     r8
0x18000ab0b  cmp     r8, r11
0x18000ab0e  jnb     short loc_18000AB4E
0x18000ab10  mov     r10b, [rax+r15+1BD00h]
0x18000ab18  jmp     loc_18000AA7E
0x18000ab1d  mov     rax, r8
0x18000ab20  shl     r8b, 3
0x18000ab24  and     r8b, 18h
0x18000ab28  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000ab2c  inc     r8b
0x18000ab2f  mov     [rbx], rax
0x18000ab32  add     [r9], r8b
0x18000ab35  mov     cl, [r9]
0x18000ab38  cmp     cl, 1Fh
0x18000ab3b  jbe     short loc_18000AB47
0x18000ab3d  sub     cl, 20h ; ' '
0x18000ab40  mov     [r9], cl
0x18000ab43  add     qword ptr [rbx], 4
0x18000ab47  mov     eax, 1
0x18000ab4c  jmp     short loc_18000AB50
0x18000ab4e  xor     eax, eax
0x18000ab50  pop     r15
0x18000ab52  pop     rdi
0x18000ab53  pop     rsi
0x18000ab54  pop     rbx
0x18000ab55  retn
```
