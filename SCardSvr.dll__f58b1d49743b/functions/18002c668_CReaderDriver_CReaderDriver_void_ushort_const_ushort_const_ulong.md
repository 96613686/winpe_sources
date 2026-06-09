# CReaderDriver::CReaderDriver(void *,ushort const *,ushort const *,ulong)

- ea: `0x18002c668`
- end: `0x18002c7d3`
- name: `??0CReaderDriver@@QEAA@PEAXPEBG1K@Z`
- size: `363`
- prototype: `CReaderDriver *__fastcall(CReaderDriver *this, char *, const unsigned __int8 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c850`

## callees

- `0x1800016c0`
- `0x180010670`
- `0x1800136a0`
- `0x180014180`
- `0x18002c668`
- `0x18002d394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c78a`

## pseudocode

```c
CReaderDriver *__fastcall CReaderDriver::CReaderDriver(
        CReaderDriver *this,
        char *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  __int64 v9; // rdi
  __int64 v10; // r8
  DWORD LastError; // eax

  CReader::CReader(this, (unsigned int)a2);
  *(_QWORD *)this = &CReaderDriver::`vftable';
  *((_QWORD *)this + 95) = 0;
  *((_DWORD *)this + 192) = 0;
  *((_QWORD *)this + 98) = &CBuffer::`vftable';
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = &CBuffer::`vftable';
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_DWORD *)this + 210) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_DWORD *)this + 224) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_DWORD *)this + 228) = 0;
  if ( !(unsigned int)CReader::InitFailed(this) )
  {
    *((_QWORD *)this + 106) = 0;
    *((_DWORD *)this + 194) = 0;
    *((_DWORD *)this + 200) = 0;
    *((_DWORD *)this + 206) = 0;
    *(_OWORD *)((char *)this + 856) = 0;
    *(_OWORD *)((char *)this + 872) = 0;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    CBuffer::Set((CReaderDriver *)((char *)this + 784), a3, 2 * v10 + 2);
    do
      ++v9;
    while ( *(_WORD *)&a4[2 * v9] );
    CBuffer::Set((CReaderDriver *)((char *)this + 808), a4, 2 * v9 + 2);
    if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      LastError = GetLastError();
    else
      LastError = 0;
    *((_DWORD *)this + 210) = LastError;
    if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 832)) )
      CHandleObject::Close((CReaderDriver *)((char *)this + 832));
    *((_QWORD *)this + 104) = a2;
    *((_DWORD *)this + 8) = 0;
    *((_DWORD *)this + 184) = 0;
    *((_DWORD *)this + 9) |= a5;
  }
  return this;
}

```

## disassembly

```asm
0x18002c668  mov     [rsp+arg_0], rcx
0x18002c66d  push    rbx
0x18002c66e  push    rbp
0x18002c66f  push    rsi
0x18002c670  push    rdi
0x18002c671  push    r12
0x18002c673  push    r13
0x18002c675  push    r14
0x18002c677  push    r15
0x18002c679  sub     rsp, 28h
0x18002c67d  mov     r14, r9
0x18002c680  mov     r12, r8
0x18002c683  mov     rbp, rdx
0x18002c686  mov     rbx, rcx
0x18002c689  call    ??0CReader@@QEAA@XZ; CReader::CReader(void)
0x18002c68e  nop
0x18002c68f  lea     rax, ??_7CReaderDriver@@6B@; const CReaderDriver::`vftable'
0x18002c696  mov     [rbx], rax
0x18002c699  xor     edi, edi
0x18002c69b  mov     [rbx+2F8h], rdi
0x18002c6a2  mov     [rbx+300h], edi
0x18002c6a8  lea     r15, [rbx+310h]
0x18002c6af  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002c6b6  mov     [r15], rax
0x18002c6b9  mov     [r15+8], rdi
0x18002c6bd  mov     [r15+10h], rdi
0x18002c6c1  lea     r13, [rbx+328h]
0x18002c6c8  mov     [r13+0], rax
0x18002c6cc  mov     [r13+8], rdi
0x18002c6d0  mov     [r13+10h], rdi
0x18002c6d4  lea     rsi, [rbx+340h]
0x18002c6db  mov     [rsi], rdi
0x18002c6de  mov     [rsi+8], edi
0x18002c6e1  mov     [rbx+378h], rdi
0x18002c6e8  mov     [rbx+380h], edi
0x18002c6ee  mov     [rbx+388h], rdi
0x18002c6f5  mov     [rbx+390h], edi
0x18002c6fb  mov     rcx, rbx; this
0x18002c6fe  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18002c703  test    eax, eax
0x18002c705  jnz     loc_18002C7BF
0x18002c70b  mov     [rbx+350h], rdi
0x18002c712  mov     [rbx+308h], edi
0x18002c718  mov     [rbx+320h], edi
0x18002c71e  mov     [rbx+338h], edi
0x18002c724  xorps   xmm0, xmm0
0x18002c727  movups  xmmword ptr [rbx+358h], xmm0
0x18002c72e  movups  xmmword ptr [rbx+368h], xmm0
0x18002c735  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c739  mov     r8, rdi
0x18002c73c  xor     eax, eax
0x18002c73e  inc     r8
0x18002c741  cmp     [r12+r8*2], ax
0x18002c746  jnz     short loc_18002C73E
0x18002c748  lea     r8d, ds:2[r8*2]; unsigned int
0x18002c750  mov     rdx, r12; unsigned __int8 *
0x18002c753  mov     rcx, r15; this
0x18002c756  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18002c75b  xor     r15d, r15d
0x18002c75e  inc     rdi
0x18002c761  cmp     [r14+rdi*2], r15w
0x18002c766  jnz     short loc_18002C75E
0x18002c768  lea     r8d, ds:2[rdi*2]; unsigned int
0x18002c770  mov     rdx, r14; unsigned __int8 *
0x18002c773  mov     rcx, r13; this
0x18002c776  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18002c77b  lea     rax, [rbp-1]
0x18002c77f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c783  ja      short loc_18002C78A
0x18002c785  mov     eax, r15d
0x18002c788  jmp     short loc_18002C790
0x18002c78a  call    cs:__imp_GetLastError
0x18002c790  mov     [rsi+8], eax
0x18002c793  mov     rcx, rsi; this
0x18002c796  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002c79b  test    eax, eax
0x18002c79d  jz      short loc_18002C7A7
0x18002c79f  mov     rcx, rsi; this
0x18002c7a2  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002c7a7  mov     [rsi], rbp
0x18002c7aa  mov     [rbx+20h], r15d
0x18002c7ae  mov     [rbx+2E0h], r15d
0x18002c7b5  mov     eax, [rsp+68h+arg_20]
0x18002c7bc  or      [rbx+24h], eax
0x18002c7bf  mov     rax, rbx
0x18002c7c2  add     rsp, 28h
0x18002c7c6  pop     r15
0x18002c7c8  pop     r14
0x18002c7ca  pop     r13
0x18002c7cc  pop     r12
0x18002c7ce  pop     rdi
0x18002c7cf  pop     rsi
0x18002c7d0  pop     rbp
0x18002c7d1  pop     rbx
0x18002c7d2  retn
```
