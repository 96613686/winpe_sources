# GenerateCorrelationVector(char *)

- ea: `0x180016fd0`
- end: `0x1800170bf`
- name: `?GenerateCorrelationVector@@YAJPEAD@Z`
- size: `239`
- prototype: `__int64 __fastcall(char *Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180018234`

## callees

- `0x180002f58`
- `0x180016b60`
- `0x180016fd0`
- `0x180017ce8`
- `0x18001972e`
- `0x180019760`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180017098`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017098`
- `RPCRT4!UuidCreate` at `0x18001702c`
- `RPCRT4!UuidCreate` at `0x18001702c`

## pseudocode

```c
__int64 __fastcall GenerateCorrelationVector(char *Destination)
{
  _BYTE *v3; // rax
  _BYTE *v4; // rdi
  unsigned int v5; // ebx
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  if ( !Destination )
    return 2147500035LL;
  v3 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 2147942414LL;
  v3[130] = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  v4[129] = 17;
  *((_QWORD *)v4 + 17) = 0x1300000000LL;
  memset_0(v4, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, v4);
  *((_WORD *)v4 + 8) = 46;
  if ( TraceLoggingCorrelationVector::ToString((TraceLoggingCorrelationVector *)v4, Destination) )
    v5 = 0;
  else
    v5 = -2147024882;
  operator delete(v4);
  return v5;
}

```

## disassembly

```asm
0x180016fd0  mov     [rsp+arg_8], rbx
0x180016fd5  push    rdi
0x180016fd6  sub     rsp, 40h
0x180016fda  mov     rax, cs:__security_cookie
0x180016fe1  xor     rax, rsp
0x180016fe4  mov     [rsp+48h+var_18], rax
0x180016fe9  mov     rbx, rcx
0x180016fec  test    rcx, rcx
0x180016fef  jnz     short loc_180016FFB
0x180016ff1  mov     eax, 80004003h
0x180016ff6  jmp     loc_1800170A7
0x180016ffb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017002  mov     ecx, 90h; unsigned __int64
0x180017007  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001700c  mov     rdi, rax
0x18001700f  test    rax, rax
0x180017012  jz      loc_1800170A2
0x180017018  xorps   xmm0, xmm0
0x18001701b  mov     byte ptr [rax+82h], 41h ; 'A'
0x180017022  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180017027  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001702c  call    cs:__imp_UuidCreate
0x180017032  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180017037  mov     rax, 1300000000h
0x180017041  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180017047  xor     edx, edx; Val
0x180017049  mov     byte ptr [rdi+81h], 11h
0x180017050  mov     r8d, 81h; Size
0x180017056  mov     rcx, rdi; void *
0x180017059  mov     [rdi+88h], rax
0x180017060  call    memset_0
0x180017065  mov     r8, rdi
0x180017068  lea     rcx, [rsp+48h+Uuid]
0x18001706d  mov     edx, 0Ch
0x180017072  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180017077  mov     rdx, rbx; Destination
0x18001707a  mov     word ptr [rdi+10h], 2Eh ; '.'
0x180017080  mov     rcx, rdi; this
0x180017083  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180017088  test    al, al
0x18001708a  jnz     short loc_180017093
0x18001708c  mov     ebx, 8007000Eh
0x180017091  jmp     short loc_180017095
0x180017093  xor     ebx, ebx
0x180017095  mov     rcx, rdi
0x180017098  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001709e  mov     eax, ebx
0x1800170a0  jmp     short loc_1800170A7
0x1800170a2  mov     eax, 8007000Eh
0x1800170a7  mov     rcx, [rsp+48h+var_18]
0x1800170ac  xor     rcx, rsp; StackCookie
0x1800170af  call    __security_check_cookie
0x1800170b4  mov     rbx, [rsp+48h+arg_8]
0x1800170b9  add     rsp, 40h
0x1800170bd  pop     rdi
0x1800170be  retn
```
