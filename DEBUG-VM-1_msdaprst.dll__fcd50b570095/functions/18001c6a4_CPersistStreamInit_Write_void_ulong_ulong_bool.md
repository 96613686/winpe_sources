# CPersistStreamInit::Write(void *,ulong,ulong *,bool)

- ea: `0x18001c6a4`
- end: `0x18001c80f`
- name: `?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z`
- size: `363`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *Src@<rdx>, size_t Size@<r8>, unsigned int *@<r9>, bool)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ac00`
- `0x18001ba50`
- `0x18001c36c`
- `0x18001c818`
- `0x18001ce6c`
- `0x18001d168`
- `0x18001e000`
- `0x18001e7a4`
- `0x18001eb04`
- `0x18001ec64`
- `0x18001edac`
- `0x18001f470`

## callees

- `0x18001a6c8`
- `0x18001acb0`
- `0x18001b728`
- `0x18001c6a4`
- `0x18001f470`
- `0x18002e012`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::Write(
        CPersistStreamInit *this,
        _BYTE *Src,
        size_t Size,
        unsigned int *a4,
        bool a5)
{
  size_t v5; // rdi
  int v6; // esi
  bool v10; // zf
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // edx

  v5 = (unsigned int)Size;
  v6 = 0;
  *a4 = Size;
  if ( *((_BYTE *)this + 64) )
  {
    if ( (_DWORD)Size == 1 )
    {
      v10 = *Src == 10;
    }
    else
    {
      if ( (_DWORD)Size != 2 || *Src != 13 )
        goto LABEL_15;
      v10 = Src[1] == 10;
    }
  }
  else
  {
    if ( (_DWORD)Size != 2 )
    {
      if ( (_DWORD)Size != 4 || *(_WORD *)Src != 13 || *((_WORD *)Src + 1) != 10 )
        goto LABEL_15;
      goto LABEL_14;
    }
    v10 = *(_WORD *)Src == 10;
  }
  if ( v10 )
LABEL_14:
    *((_DWORD *)this + 13) = 0;
LABEL_15:
  v11 = *((_DWORD *)this + 13);
  if ( (v11 + (unsigned int)Size > 0x6E || v11 + (unsigned int)Size < v11) && a5 )
  {
    v6 = CPersistStreamInit::WriteTag(this, 0x28u, a4);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v6 = CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
    if ( v6 < 0 )
      return (unsigned int)v6;
    *((_DWORD *)this + 13) = 0;
  }
  v12 = *((_DWORD *)this + 2068);
  if ( v12 + (unsigned int)v5 <= 0x2000 && v12 + (unsigned int)v5 >= v12
    || (v6 = CPersistStreamInit::FlushBuffer(this), v6 >= 0) )
  {
    if ( (unsigned int)v5 <= 0x2000 )
    {
      memcpy_0((char *)this + *((unsigned int *)this + 2068) + 80, Src, v5);
      *((_DWORD *)this + 2068) += v5;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned int *))(**((_QWORD **)this + 3) + 32LL))(
             *((_QWORD *)this + 3),
             Src,
             (unsigned int)v5,
             a4);
    }
    v13 = *((_DWORD *)this + 13) + *a4;
    if ( v13 >= *((_DWORD *)this + 13) )
    {
      *((_DWORD *)this + 13) = v13;
    }
    else
    {
      v6 = -2147467259;
      if ( (bidGblFlags & 2) != 0 && off_180048B48[0] )
        bidTraceW(off_1800481F0[0], 3259392, off_180048B48[0], 2147500037LL, 3183);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c6a4  push    rbx
0x18001c6a6  push    rbp
0x18001c6a7  push    rsi
0x18001c6a8  push    rdi
0x18001c6a9  push    r14
0x18001c6ab  sub     rsp, 30h
0x18001c6af  mov     edi, r8d
0x18001c6b2  xor     esi, esi
0x18001c6b4  mov     [r9], edi
0x18001c6b7  mov     r14, r9
0x18001c6ba  mov     rbp, rdx
0x18001c6bd  mov     rbx, rcx
0x18001c6c0  cmp     [rcx+40h], sil
0x18001c6c4  jz      short loc_18001C6E2
0x18001c6c6  cmp     edi, 1
0x18001c6c9  jnz     short loc_18001C6D0
0x18001c6cb  cmp     byte ptr [rdx], 0Ah
0x18001c6ce  jmp     short loc_18001C6DE
0x18001c6d0  cmp     edi, 2
0x18001c6d3  jnz     short loc_18001C702
0x18001c6d5  cmp     byte ptr [rdx], 0Dh
0x18001c6d8  jnz     short loc_18001C702
0x18001c6da  cmp     byte ptr [rdx+1], 0Ah
0x18001c6de  jz      short loc_18001C6FF
0x18001c6e0  jmp     short loc_18001C702
0x18001c6e2  cmp     edi, 2
0x18001c6e5  jnz     short loc_18001C6ED
0x18001c6e7  cmp     word ptr [rdx], 0Ah
0x18001c6eb  jmp     short loc_18001C6DE
0x18001c6ed  cmp     edi, 4
0x18001c6f0  jnz     short loc_18001C702
0x18001c6f2  cmp     word ptr [rdx], 0Dh
0x18001c6f6  jnz     short loc_18001C702
0x18001c6f8  cmp     word ptr [rdx+2], 0Ah
0x18001c6fd  jnz     short loc_18001C702
0x18001c6ff  mov     [rcx+34h], esi
0x18001c702  mov     eax, [rcx+34h]
0x18001c705  lea     ecx, [rax+rdi]
0x18001c708  cmp     ecx, 6Eh ; 'n'
0x18001c70b  ja      short loc_18001C711
0x18001c70d  cmp     ecx, eax
0x18001c70f  jnb     short loc_18001C74E
0x18001c711  cmp     [rsp+58h+arg_20], sil
0x18001c719  jz      short loc_18001C74E
0x18001c71b  mov     r8, r14; unsigned int *
0x18001c71e  mov     dl, 28h ; '('; unsigned __int8
0x18001c720  mov     rcx, rbx; this
0x18001c723  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001c728  mov     esi, eax
0x18001c72a  test    eax, eax
0x18001c72c  js      loc_18001C802
0x18001c732  mov     edx, [rbx+30h]; unsigned int
0x18001c735  mov     rcx, rbx; this
0x18001c738  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001c73d  mov     esi, eax
0x18001c73f  test    eax, eax
0x18001c741  js      loc_18001C802
0x18001c747  mov     dword ptr [rbx+34h], 0
0x18001c74e  mov     eax, [rbx+2050h]
0x18001c754  lea     ecx, [rax+rdi]
0x18001c757  cmp     ecx, 2000h
0x18001c75d  ja      short loc_18001C763
0x18001c75f  cmp     ecx, eax
0x18001c761  jnb     short loc_18001C775
0x18001c763  mov     rcx, rbx; this
0x18001c766  call    ?FlushBuffer@CPersistStreamInit@@AEAAJXZ; CPersistStreamInit::FlushBuffer(void)
0x18001c76b  mov     esi, eax
0x18001c76d  test    eax, eax
0x18001c76f  js      loc_18001C802
0x18001c775  mov     rdx, rbp; Src
0x18001c778  cmp     edi, 2000h
0x18001c77e  jbe     short loc_18001C79A
0x18001c780  mov     rcx, [rbx+18h]
0x18001c784  mov     r9, r14
0x18001c787  mov     r8d, edi
0x18001c78a  mov     rax, [rcx]
0x18001c78d  mov     rax, [rax+20h]
0x18001c791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c796  mov     esi, eax
0x18001c798  jmp     short loc_18001C7B5
0x18001c79a  mov     ecx, [rbx+2050h]
0x18001c7a0  mov     r8, rdi; Size
0x18001c7a3  add     rcx, 50h ; 'P'
0x18001c7a7  add     rcx, rbx; void *
0x18001c7aa  call    memcpy_0
0x18001c7af  add     [rbx+2050h], edi
0x18001c7b5  mov     edx, [r14]
0x18001c7b8  add     edx, [rbx+34h]
0x18001c7bb  cmp     edx, [rbx+34h]
0x18001c7be  jnb     short loc_18001C7FF
0x18001c7c0  test    byte ptr cs:_bidGblFlags, 2
0x18001c7c7  mov     esi, 80004005h
0x18001c7cc  jz      short loc_18001C802
0x18001c7ce  mov     rax, cs:off_180048B48; "<CPersistStreamInit::Write|ADO|ERR>  HR"...
0x18001c7d5  test    rax, rax
0x18001c7d8  jz      short loc_18001C802
0x18001c7da  mov     r8, cs:off_180048B48; "<CPersistStreamInit::Write|ADO|ERR>  HR"...
0x18001c7e1  mov     r9d, esi
0x18001c7e4  mov     rcx, cs:off_1800481F0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001c7eb  mov     edx, 31BC00h
0x18001c7f0  mov     [rsp+58h+var_38], 0C6Fh
0x18001c7f8  call    _bidTraceW
0x18001c7fd  jmp     short loc_18001C802
0x18001c7ff  mov     [rbx+34h], edx
0x18001c802  mov     eax, esi
0x18001c804  add     rsp, 30h
0x18001c808  pop     r14
0x18001c80a  pop     rdi
0x18001c80b  pop     rsi
0x18001c80c  pop     rbp
0x18001c80d  pop     rbx
0x18001c80e  retn
```
