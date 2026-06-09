# IoUnpack_SG_SzStringArray(ushort * * *,ulong,uchar *,ulong,uchar *)

- ea: `0x1800027ac`
- end: `0x180002834`
- name: `?IoUnpack_SG_SzStringArray@@YAKPEAPEAPEAGKPEAEK1@Z`
- size: `136`
- prototype: `unsigned int(unsigned __int16 ***, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180001af0`
- `0x180001b84`
- `0x180002370`
- `0x180012f40`
- `0x180018b80`
- `0x180018d90`

## callees

- `0x1800027ac`
- `0x180004050`

## pseudocode

```c
unsigned int __fastcall IoUnpack_SG_SzStringArray(
        unsigned __int16 ***a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  unsigned __int64 v4; // r10
  unsigned int v6; // ebp
  unsigned __int8 *v9; // rax
  unsigned __int64 v10; // rdx
  __int64 i; // rbx
  unsigned int result; // eax

  v4 = (unsigned __int64)*a1;
  v6 = (unsigned int)a4;
  if ( *a1 != (unsigned __int16 **)-1LL )
  {
    if ( a2 )
    {
      if ( v4 < (unsigned int)a4 )
      {
        v10 = v4 + 8LL * a2;
        if ( v10 <= (unsigned int)a4 && v10 >= v4 )
        {
          v9 = &a3[v4];
          *a1 = (unsigned __int16 **)&a3[v4];
          goto LABEL_8;
        }
      }
    }
    return 1359;
  }
  *a1 = 0;
  if ( a2 )
    return 1359;
  v9 = 0;
LABEL_8:
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      result = IoUnpack_SG_SzString(&(*a1)[i], a3, v6, a4);
      if ( result )
        return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800027ac  push    rbx
0x1800027ae  push    rbp
0x1800027af  push    rsi
0x1800027b0  push    rdi
0x1800027b1  push    r14
0x1800027b3  sub     rsp, 20h
0x1800027b7  mov     r10, [rcx]
0x1800027ba  mov     r14, r8
0x1800027bd  mov     ebp, r9d
0x1800027c0  mov     rsi, rcx
0x1800027c3  mov     edi, edx
0x1800027c5  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x1800027c9  jnz     short loc_18000282E
0x1800027cb  mov     qword ptr [rcx], 0
0x1800027d2  test    edx, edx
0x1800027d4  jnz     short loc_180002827
0x1800027d6  xor     eax, eax
0x1800027d8  jmp     short loc_1800027F4
0x1800027da  cmp     r10, rbp
0x1800027dd  jnb     short loc_180002827
0x1800027df  lea     rdx, [r10+rdi*8]
0x1800027e3  cmp     rdx, rbp
0x1800027e6  ja      short loc_180002827
0x1800027e8  cmp     rdx, r10
0x1800027eb  jb      short loc_180002827
0x1800027ed  lea     rax, [r10+r8]
0x1800027f1  mov     [rcx], rax
0x1800027f4  test    rax, rax
0x1800027f7  jz      short loc_180002819
0x1800027f9  xor     ebx, ebx
0x1800027fb  cmp     ebx, edi
0x1800027fd  jnb     short loc_180002819
0x1800027ff  mov     rax, [rsi]
0x180002802  mov     r8d, ebp; unsigned int
0x180002805  mov     rdx, r14; unsigned __int8 *
0x180002808  lea     rcx, [rax+rbx*8]; unsigned __int16 **
0x18000280c  call    ?IoUnpack_SG_SzString@@YAKPEAPEAGPEAEK1@Z; IoUnpack_SG_SzString(ushort * *,uchar *,ulong,uchar *)
0x180002811  test    eax, eax
0x180002813  jnz     short loc_18000281B
0x180002815  inc     ebx
0x180002817  jmp     short loc_1800027FB
0x180002819  xor     eax, eax
0x18000281b  add     rsp, 20h
0x18000281f  pop     r14
0x180002821  pop     rdi
0x180002822  pop     rsi
0x180002823  pop     rbp
0x180002824  pop     rbx
0x180002825  retn
0x180002827  mov     eax, 54Fh
0x18000282c  jmp     short loc_18000281B
0x18000282e  test    edx, edx
0x180002830  jz      short loc_180002827
0x180002832  jmp     short loc_1800027DA
```
