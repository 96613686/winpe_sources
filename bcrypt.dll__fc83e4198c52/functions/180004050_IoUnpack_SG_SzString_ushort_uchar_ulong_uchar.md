# IoUnpack_SG_SzString(ushort * *,uchar *,ulong,uchar *)

- ea: `0x180004050`
- end: `0x180004112`
- name: `?IoUnpack_SG_SzString@@YAKPEAPEAGPEAEK1@Z`
- size: `194`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019d0`
- `0x18000223c`
- `0x1800027ac`

## callees

- `0x180004050`
- `0x180004120`

## pseudocode

```c
__int64 __fastcall IoUnpack_SG_SzString(
        unsigned __int16 **a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v6; // rsi
  char *v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned int v10; // r8d
  __int64 result; // rax
  unsigned __int8 *v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  v4 = (unsigned __int64)*a1;
  v6 = a3;
  if ( *a1 == (unsigned __int16 *)-1LL )
  {
    v9 = 0;
  }
  else
  {
    if ( v4 >= a3 )
      return 1359;
    LODWORD(v12) = 0;
    if ( a3 - (_DWORD)v4 == 1 )
      return 1359;
    if ( (unsigned int)SzString_CchLength(
                         (const unsigned __int16 *)&a2[v4],
                         (unsigned int *)&v12,
                         (a3 - (unsigned int)v4) >> 1) )
      return 1359;
    v8 = (char *)*a1 + (unsigned int)(2 * (_DWORD)v12) + 2;
    if ( v8 < (char *)*a1 || (unsigned __int64)v8 > v6 )
      return 1359;
    v9 = (unsigned __int16 *)((char *)*a1 + (_QWORD)a2);
  }
  *a1 = v9;
  if ( !v9 )
    return 0;
  v10 = (_DWORD)a2 - (_DWORD)v9 + v6;
  if ( v10 == 1 )
    return 122;
  result = SzString_CchLength(v9, (unsigned int *)&v12, v10 >> 1);
  if ( !(_DWORD)result )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180004050  mov     [rsp+arg_18], r9
0x180004055  push    rbx
0x180004056  push    rbp
0x180004057  push    rsi
0x180004058  push    rdi
0x180004059  sub     rsp, 28h
0x18000405d  mov     rax, [rcx]
0x180004060  mov     rdi, rdx
0x180004063  mov     esi, r8d
0x180004066  mov     rbx, rcx
0x180004069  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000406d  jz      loc_18000410E
0x180004073  cmp     rax, rsi
0x180004076  jnb     short loc_1800040EC
0x180004078  xor     ecx, ecx
0x18000407a  mov     r8d, esi
0x18000407d  sub     r8d, eax
0x180004080  mov     dword ptr [rsp+48h+arg_18], ecx
0x180004084  cmp     r8d, 1
0x180004088  jz      short loc_1800040EC
0x18000408a  lea     rcx, [rax+rdx]; unsigned __int16 *
0x18000408e  shr     r8d, 1; unsigned int
0x180004091  lea     rdx, [rsp+48h+arg_18]; unsigned int *
0x180004096  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x18000409b  test    eax, eax
0x18000409d  jnz     short loc_1800040EC
0x18000409f  mov     rcx, [rbx]
0x1800040a2  mov     eax, dword ptr [rsp+48h+arg_18]
0x1800040a6  lea     edx, [rax+rax]
0x1800040a9  add     rdx, 2
0x1800040ad  add     rdx, rcx
0x1800040b0  cmp     rdx, rcx
0x1800040b3  jb      short loc_1800040EC
0x1800040b5  cmp     rdx, rsi
0x1800040b8  ja      short loc_1800040EC
0x1800040ba  add     rcx, rdi; unsigned __int16 *
0x1800040bd  mov     [rbx], rcx
0x1800040c0  test    rcx, rcx
0x1800040c3  jz      short loc_1800040F3
0x1800040c5  sub     edi, ecx
0x1800040c7  lea     r8d, [rdi+rsi]
0x1800040cb  cmp     r8d, 1
0x1800040cf  jz      short loc_1800040FF
0x1800040d1  shr     r8d, 1; unsigned int
0x1800040d4  lea     rdx, [rsp+48h+arg_18]; unsigned int *
0x1800040d9  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x1800040de  test    eax, eax
0x1800040e0  jz      short loc_1800040F3
0x1800040e2  add     rsp, 28h
0x1800040e6  pop     rdi
0x1800040e7  pop     rsi
0x1800040e8  pop     rbp
0x1800040e9  pop     rbx
0x1800040ea  retn
0x1800040ec  mov     eax, 54Fh
0x1800040f1  jmp     short loc_1800040E2
0x1800040f3  xor     eax, eax
0x1800040f5  add     rsp, 28h
0x1800040f9  pop     rdi
0x1800040fa  pop     rsi
0x1800040fb  pop     rbp
0x1800040fc  pop     rbx
0x1800040fd  retn
0x1800040ff  mov     eax, 7Ah ; 'z'
0x180004104  add     rsp, 28h
0x180004108  pop     rdi
0x180004109  pop     rsi
0x18000410a  pop     rbp
0x18000410b  pop     rbx
0x18000410c  retn
0x18000410e  xor     ecx, ecx
0x180004110  jmp     short loc_1800040BD
```
