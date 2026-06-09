# CopyIISToIISSynId(ulong,ulong,uchar *,_iistype *)

- ea: `0x180018150`
- end: `0x1800182b5`
- name: `?CopyIISToIISSynId@@YAPEAEKKPEAEPEAU_iistype@@@Z`
- size: `357`
- prototype: `unsigned __int8 *(unsigned int, unsigned int, unsigned __int8 *, struct _iistype *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110bc`

## callees

- `0x180018150`
- `0x18001d652`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180018231`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018231`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800181c0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800181fb`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018274`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800181c0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800181fb`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018274`

## pseudocode

```c
const WCHAR *__fastcall CopyIISToIISSynId(unsigned int a1, DWORD a2, const WCHAR *a3, struct _iistype *a4)
{
  size_t v4; // r15
  unsigned int v7; // eax
  const WCHAR *v8; // rbp
  unsigned int v9; // r12d
  void *v10; // rax
  void *v11; // rbx
  const WCHAR *v12; // rbp
  unsigned int v13; // r12d

  v4 = a2;
  if ( a1 <= 6 )
  {
    if ( a1 != 6 )
    {
      if ( a1 != 1 )
      {
        if ( a1 == 2 )
        {
          *(_DWORD *)a4 = 2;
        }
        else
        {
          if ( a1 != 3 )
          {
            v7 = a1 - 4;
            if ( a1 != 4 )
              goto LABEL_7;
            v8 = a3;
            v9 = 0;
            if ( a2 )
            {
              do
              {
                *((_DWORD *)a4 + 6 * v9) = 4;
                *((_QWORD *)a4 + 3 * v9 + 1) = AllocADsStr(v8);
                while ( *v8 )
                  ++v8;
                ++v8;
                ++v9;
              }
              while ( v9 < (unsigned int)v4 );
            }
            return a3;
          }
          *(_DWORD *)a4 = 3;
        }
        *((_QWORD *)a4 + 1) = AllocADsStr(a3);
        return a3;
      }
      *(_DWORD *)a4 = 1;
LABEL_31:
      *((_DWORD *)a4 + 2) = *(_DWORD *)a3;
      return a3;
    }
LABEL_30:
    *(_DWORD *)a4 = a1;
    goto LABEL_31;
  }
  if ( a1 == 7 )
    goto LABEL_30;
  if ( a1 != 8 )
  {
    v7 = a1 - 9;
    if ( a1 == 9 )
    {
LABEL_22:
      *(_DWORD *)a4 = a1;
      v10 = AllocADsMem(a2);
      v11 = v10;
      if ( v10 )
      {
        memcpy_0(v10, a3, v4);
        *((_QWORD *)a4 + 2) = v11;
        *((_DWORD *)a4 + 2) = v4;
      }
      return a3;
    }
LABEL_7:
    if ( v7 != 1 )
      return a3;
    goto LABEL_22;
  }
  v12 = a3;
  v13 = 0;
  if ( a2 )
  {
    do
    {
      *((_DWORD *)a4 + 6 * v13) = 8;
      *((_QWORD *)a4 + 3 * v13 + 1) = AllocADsStr(v12);
      while ( *v12 )
        ++v12;
      ++v12;
      ++v13;
    }
    while ( v13 < (unsigned int)v4 );
  }
  return a3;
}

```

## disassembly

```asm
0x180018150  push    rbx
0x180018152  push    rbp
0x180018153  push    rsi
0x180018154  push    rdi
0x180018155  push    r12
0x180018157  push    r14
0x180018159  push    r15
0x18001815b  sub     rsp, 20h
0x18001815f  mov     r15d, edx
0x180018162  mov     rdi, r9
0x180018165  mov     r14, r8
0x180018168  cmp     ecx, 6
0x18001816b  ja      loc_180018216
0x180018171  jz      loc_180018299
0x180018177  mov     eax, ecx
0x180018179  sub     eax, 1
0x18001817c  jz      loc_18001820A
0x180018182  sub     eax, 1
0x180018185  jz      short loc_1800181F1
0x180018187  sub     eax, 1
0x18001818a  jz      short loc_1800181E8
0x18001818c  sub     eax, 1
0x18001818f  jz      short loc_18001819F
0x180018191  cmp     eax, 1
0x180018194  jz      loc_18001822B
0x18001819a  jmp     loc_1800182A3
0x18001819f  xor     esi, esi
0x1800181a1  mov     rbp, r14
0x1800181a4  mov     r12d, esi
0x1800181a7  test    edx, edx
0x1800181a9  jz      loc_1800182A3
0x1800181af  mov     eax, r12d
0x1800181b2  mov     rcx, rbp; pStr
0x1800181b5  lea     rbx, [rax+rax*2]
0x1800181b9  mov     dword ptr [rdi+rbx*8], 4
0x1800181c0  call    cs:__imp_AllocADsStr
0x1800181c6  mov     [rdi+rbx*8+8], rax
0x1800181cb  jmp     short loc_1800181D1
0x1800181cd  add     rbp, 2
0x1800181d1  cmp     [rbp+0], si
0x1800181d5  jnz     short loc_1800181CD
0x1800181d7  add     rbp, 2
0x1800181db  inc     r12d
0x1800181de  cmp     r12d, r15d
0x1800181e1  jb      short loc_1800181AF
0x1800181e3  jmp     loc_1800182A3
0x1800181e8  mov     dword ptr [r9], 3
0x1800181ef  jmp     short loc_1800181F8
0x1800181f1  mov     dword ptr [r9], 2
0x1800181f8  mov     rcx, r14; pStr
0x1800181fb  call    cs:__imp_AllocADsStr
0x180018201  mov     [rdi+8], rax
0x180018205  jmp     loc_1800182A3
0x18001820a  mov     dword ptr [r9], 1
0x180018211  jmp     loc_18001829C
0x180018216  mov     eax, ecx
0x180018218  sub     eax, 7
0x18001821b  jz      short loc_180018299
0x18001821d  sub     eax, 1
0x180018220  jz      short loc_180018257
0x180018222  sub     eax, 1
0x180018225  jnz     loc_180018191
0x18001822b  mov     [r9], ecx
0x18001822e  mov     ecx, r15d; cb
0x180018231  call    cs:__imp_AllocADsMem
0x180018237  mov     rbx, rax
0x18001823a  test    rax, rax
0x18001823d  jz      short loc_1800182A3
0x18001823f  mov     r8, r15; Size
0x180018242  mov     rdx, r14; Src
0x180018245  mov     rcx, rax; void *
0x180018248  call    memcpy_0
0x18001824d  mov     [rdi+10h], rbx
0x180018251  mov     [rdi+8], r15d
0x180018255  jmp     short loc_1800182A3
0x180018257  xor     esi, esi
0x180018259  mov     rbp, r14
0x18001825c  mov     r12d, esi
0x18001825f  test    edx, edx
0x180018261  jz      short loc_1800182A3
0x180018263  mov     eax, r12d
0x180018266  mov     rcx, rbp; pStr
0x180018269  lea     rbx, [rax+rax*2]
0x18001826d  mov     dword ptr [rdi+rbx*8], 8
0x180018274  call    cs:__imp_AllocADsStr
0x18001827a  mov     [rdi+rbx*8+8], rax
0x18001827f  jmp     short loc_180018285
0x180018281  add     rbp, 2
0x180018285  cmp     [rbp+0], si
0x180018289  jnz     short loc_180018281
0x18001828b  add     rbp, 2
0x18001828f  inc     r12d
0x180018292  cmp     r12d, r15d
0x180018295  jb      short loc_180018263
0x180018297  jmp     short loc_1800182A3
0x180018299  mov     [r9], ecx
0x18001829c  mov     eax, [r8]
0x18001829f  mov     [r9+8], eax
0x1800182a3  mov     rax, r14
0x1800182a6  add     rsp, 20h
0x1800182aa  pop     r15
0x1800182ac  pop     r14
0x1800182ae  pop     r12
0x1800182b0  pop     rdi
0x1800182b1  pop     rsi
0x1800182b2  pop     rbp
0x1800182b3  pop     rbx
0x1800182b4  retn
```
