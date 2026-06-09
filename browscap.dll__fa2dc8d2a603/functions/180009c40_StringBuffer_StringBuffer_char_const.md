# StringBuffer::StringBuffer(char const *)

- ea: `0x180009c40`
- end: `0x180009cea`
- name: `??0StringBuffer@@QEAA@PEBD@Z`
- size: `170`
- prototype: `StringBuffer *__fastcall(StringBuffer *__hidden this, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a70`
- `0x180008e40`
- `0x180009ab4`
- `0x180009b10`

## callees

- `0x1800099f8`
- `0x180009c40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
StringBuffer *__fastcall StringBuffer::StringBuffer(StringBuffer *this, const char *a2)
{
  const char *v2; // rdi
  __int64 v4; // rcx
  unsigned __int64 v5; // rcx
  _BYTE *v6; // rax
  _BYTE *v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // rax

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 3) = v4;
  v5 = v4 + 1;
  *((_QWORD *)this + 2) = v5;
  v6 = operator new(v5);
  *((_QWORD *)this + 4) = v6;
  v7 = v6;
  if ( v6 )
  {
    if ( !v2 )
    {
LABEL_16:
      *v6 = 0;
      goto LABEL_17;
    }
    v8 = *((_QWORD *)this + 2);
    if ( v8 )
    {
      if ( v8 <= 0x7FFFFFFF )
      {
        v9 = 2147483646;
        do
        {
          if ( !v9 )
            break;
          if ( !*v2 )
            break;
          *v7++ = *v2++;
          --v9;
          --v8;
        }
        while ( v8 );
        v6 = v7 - 1;
        if ( v8 )
          v6 = v7;
      }
      goto LABEL_16;
    }
  }
LABEL_17:
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &StringBuffer::`vftable';
  return this;
}

```

## disassembly

```asm
0x180009c40  mov     [rsp+arg_0], rbx
0x180009c45  push    rdi
0x180009c46  sub     rsp, 20h
0x180009c4a  mov     rdi, rdx
0x180009c4d  mov     rbx, rcx
0x180009c50  test    rdx, rdx
0x180009c53  jz      short loc_180009C64
0x180009c55  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009c59  inc     rcx
0x180009c5c  cmp     byte ptr [rdx+rcx], 0
0x180009c60  jnz     short loc_180009C59
0x180009c62  jmp     short loc_180009C66
0x180009c64  xor     ecx, ecx
0x180009c66  mov     [rbx+18h], rcx
0x180009c6a  inc     rcx; unsigned __int64
0x180009c6d  mov     [rbx+10h], rcx
0x180009c71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c76  mov     [rbx+20h], rax
0x180009c7a  mov     rcx, rax
0x180009c7d  test    rax, rax
0x180009c80  jz      short loc_180009CCB
0x180009c82  test    rdi, rdi
0x180009c85  jz      short loc_180009CC8
0x180009c87  mov     rdx, [rbx+10h]
0x180009c8b  test    rdx, rdx
0x180009c8e  jz      short loc_180009CCB
0x180009c90  cmp     rdx, 7FFFFFFFh
0x180009c97  ja      short loc_180009CC8
0x180009c99  mov     eax, 7FFFFFFEh
0x180009c9e  test    rax, rax
0x180009ca1  jz      short loc_180009CBD
0x180009ca3  mov     r8b, [rdi]
0x180009ca6  test    r8b, r8b
0x180009ca9  jz      short loc_180009CBD
0x180009cab  mov     [rcx], r8b
0x180009cae  inc     rdi
0x180009cb1  inc     rcx
0x180009cb4  dec     rax
0x180009cb7  sub     rdx, 1
0x180009cbb  jnz     short loc_180009C9E
0x180009cbd  test    rdx, rdx
0x180009cc0  lea     rax, [rcx-1]
0x180009cc4  cmovnz  rax, rcx
0x180009cc8  mov     byte ptr [rax], 0
0x180009ccb  lea     rax, ??_7StringBuffer@@6B@; const StringBuffer::`vftable'
0x180009cd2  mov     dword ptr [rbx+8], 0
0x180009cd9  mov     [rbx], rax
0x180009cdc  mov     rax, rbx
0x180009cdf  mov     rbx, [rsp+28h+arg_0]
0x180009ce4  add     rsp, 20h
0x180009ce8  pop     rdi
0x180009ce9  retn
```
