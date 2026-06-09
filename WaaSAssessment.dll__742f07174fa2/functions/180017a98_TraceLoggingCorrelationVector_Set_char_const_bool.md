# TraceLoggingCorrelationVector::Set(char const *,bool)

- ea: `0x180017a98`
- end: `0x180017cdf`
- name: `?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `583`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *Source, bool)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800170c8`
- `0x180017244`
- `0x1800176a4`
- `0x1800177f0`

## callees

- `0x180002f58`
- `0x180016ce4`
- `0x180016d80`
- `0x180017a98`
- `0x180017da8`

## import_xrefs

- `msvcrt!_errno` at `0x180017c0e`
- `msvcrt!_errno` at `0x180017c0e`
- `msvcrt!strncpy_s` at `0x180017b63`
- `msvcrt!strncpy_s` at `0x180017c88`
- `msvcrt!strncpy_s` at `0x180017b63`
- `msvcrt!strncpy_s` at `0x180017c88`
- `msvcrt!_set_errno` at `0x180017be4`
- `msvcrt!_set_errno` at `0x180017be4`
- `msvcrt!strtol` at `0x180017bf3`
- `msvcrt!strtol` at `0x180017bf3`
- `msvcrt!strrchr` at `0x180017bcd`
- `msvcrt!strrchr` at `0x180017bcd`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Set(const char *Source, __int64 a2)
{
  unsigned __int8 v3; // al
  int v4; // esi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  void *v10; // rax
  unsigned __int64 v12; // rax
  char *v13; // rax
  char *v14; // rdi
  unsigned int v15; // eax
  __int64 v16; // r14
  void *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rsi
  void *v20; // rax
  rsize_t v21; // rdi

  LOBYTE(a2) = 1;
  v3 = TraceLoggingCorrelationVector::ValidateImpl(Source, a2);
  v4 = v3;
  if ( !v3 )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  if ( !v5 )
    goto LABEL_19;
  v6 = 64;
  if ( (_BYTE)v4 != 1 )
    v6 = 128;
  if ( v5 > v6 || Source[v5 - 1] != 33 )
  {
LABEL_19:
    v12 = 63;
    if ( (_BYTE)v4 != 1 )
      v12 = 127;
    if ( v5 > v12 )
      return 0;
    v13 = strrchr(Source, 46);
    if ( !v13 )
      return 0;
    v14 = v13 + 1;
    _set_errno(0);
    v15 = strtol(v14, 0, 10);
    v16 = v15;
    if ( !v15 && *v14 != 48 && v14[1] )
      return 0;
    if ( *_errno() == 34 )
      return 0;
    if ( v4 == 1 )
    {
      v20 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      if ( !v20 )
        return 0;
      v18 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v20);
    }
    else
    {
      if ( v4 != 2 )
        return 0;
      v17 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      if ( !v17 )
      {
        v19 = 0;
        goto LABEL_35;
      }
      v18 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v17);
    }
    v19 = v18;
LABEL_35:
    if ( v19 )
    {
      v21 = v14 - Source;
      strncpy_s((char *)v19, 0x81u, Source, v21);
      *(_BYTE *)(v19 + 129) = v21;
      *(_QWORD *)(v19 + 136) = v16 | ((v5 + 1) << 32);
      *(_QWORD *)(v19 + 136) &= ~0x8000000000000000uLL;
      *(_BYTE *)(*(unsigned __int8 *)(v19 + 129) + v19) = 0;
      return (struct TraceLoggingCorrelationVector *)v19;
    }
    return 0;
  }
  if ( v4 == 1 )
  {
    v10 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    if ( v10 )
    {
      v8 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v10);
      goto LABEL_16;
    }
  }
  else if ( v4 == 2 )
  {
    v7 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    if ( !v7 )
    {
      v9 = 0;
      goto LABEL_17;
    }
    v8 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v7);
LABEL_16:
    v9 = v8;
LABEL_17:
    if ( v9 )
    {
      strncpy_s((char *)v9, 0x81u, Source, v5 - 1);
      *(_BYTE *)(v9 + 129) = v5 - 1;
      *(_QWORD *)(v9 + 136) = (v5 + 1) << 32;
      *(_QWORD *)(v9 + 136) |= 0x8000000000000000uLL;
      *(_BYTE *)(*(unsigned __int8 *)(v9 + 129) + v9) = 0;
      return (struct TraceLoggingCorrelationVector *)v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017a98  push    rbx
0x180017a9a  push    rbp
0x180017a9b  push    rsi
0x180017a9c  push    rdi
0x180017a9d  push    r14
0x180017a9f  sub     rsp, 20h
0x180017aa3  mov     dl, 1
0x180017aa5  mov     rbp, rcx
0x180017aa8  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x180017aad  movzx   esi, al
0x180017ab0  test    al, al
0x180017ab2  jz      loc_180017CD2
0x180017ab8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017abc  inc     rbx
0x180017abf  cmp     byte ptr [rbx+rbp], 0
0x180017ac3  jnz     short loc_180017ABC
0x180017ac5  cmp     rbx, 1
0x180017ac9  jb      loc_180017BAF
0x180017acf  mov     eax, 40h ; '@'
0x180017ad4  cmp     sil, 1
0x180017ad8  lea     ecx, [rax+40h]
0x180017adb  cmovnz  eax, ecx
0x180017ade  cmp     rbx, rax
0x180017ae1  ja      loc_180017BAF
0x180017ae7  cmp     byte ptr [rbx+rbp-1], 21h ; '!'
0x180017aec  jnz     loc_180017BAF
0x180017af2  mov     ecx, esi
0x180017af4  sub     ecx, 1
0x180017af7  jz      short loc_180017B26
0x180017af9  cmp     ecx, 1
0x180017afc  jnz     loc_180017CD2
0x180017b02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017b09  mov     ecx, 90h; unsigned __int64
0x180017b0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017b13  test    rax, rax
0x180017b16  jz      short loc_180017B22
0x180017b18  mov     rcx, rax
0x180017b1b  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180017b20  jmp     short loc_180017B48
0x180017b22  xor     edi, edi
0x180017b24  jmp     short loc_180017B4B
0x180017b26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017b2d  mov     ecx, 90h; unsigned __int64
0x180017b32  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017b37  test    rax, rax
0x180017b3a  jz      loc_180017CD2
0x180017b40  mov     rcx, rax
0x180017b43  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)
0x180017b48  mov     rdi, rax
0x180017b4b  test    rdi, rdi
0x180017b4e  jz      loc_180017CD2
0x180017b54  lea     r9, [rbx-1]; MaxCount
0x180017b58  mov     r8, rbp; Source
0x180017b5b  mov     edx, 81h; SizeInBytes
0x180017b60  mov     rcx, rdi; Destination
0x180017b63  call    cs:__imp_strncpy_s
0x180017b69  lea     eax, [rbx-1]
0x180017b6c  mov     rcx, 8000000000000000h
0x180017b76  mov     [rdi+81h], al
0x180017b7c  lea     rax, [rbx+1]
0x180017b80  shl     rax, 20h
0x180017b84  mov     [rdi+88h], rax
0x180017b8b  mov     rax, [rdi+88h]
0x180017b92  or      rax, rcx
0x180017b95  mov     [rdi+88h], rax
0x180017b9c  movzx   eax, byte ptr [rdi+81h]
0x180017ba3  mov     byte ptr [rax+rdi], 0
0x180017ba7  mov     rax, rdi
0x180017baa  jmp     loc_180017CD4
0x180017baf  mov     eax, 3Fh ; '?'
0x180017bb4  cmp     sil, 1
0x180017bb8  lea     ecx, [rax+40h]
0x180017bbb  cmovnz  eax, ecx
0x180017bbe  cmp     rbx, rax
0x180017bc1  ja      loc_180017CD2
0x180017bc7  lea     edx, [rcx-51h]; Ch
0x180017bca  mov     rcx, rbp; Str
0x180017bcd  call    cs:__imp_strrchr
0x180017bd3  mov     rdi, rax
0x180017bd6  test    rax, rax
0x180017bd9  jz      loc_180017CD2
0x180017bdf  xor     ecx, ecx; Value
0x180017be1  inc     rdi
0x180017be4  call    cs:__imp__set_errno
0x180017bea  xor     edx, edx; EndPtr
0x180017bec  mov     rcx, rdi; String
0x180017bef  lea     r8d, [rdx+0Ah]; Radix
0x180017bf3  call    cs:__imp_strtol
0x180017bf9  mov     r14d, eax
0x180017bfc  test    eax, eax
0x180017bfe  jnz     short loc_180017C0E
0x180017c00  cmp     byte ptr [rdi], 30h ; '0'
0x180017c03  jz      short loc_180017C0E
0x180017c05  cmp     [rdi+1], al
0x180017c08  jnz     loc_180017CD2
0x180017c0e  call    cs:__imp__errno
0x180017c14  cmp     dword ptr [rax], 22h ; '"'
0x180017c17  jz      loc_180017CD2
0x180017c1d  mov     ecx, esi
0x180017c1f  sub     ecx, 1
0x180017c22  jz      short loc_180017C51
0x180017c24  cmp     ecx, 1
0x180017c27  jnz     loc_180017CD2
0x180017c2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017c34  mov     ecx, 90h; unsigned __int64
0x180017c39  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017c3e  test    rax, rax
0x180017c41  jz      short loc_180017C4D
0x180017c43  mov     rcx, rax
0x180017c46  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180017c4b  jmp     short loc_180017C6F
0x180017c4d  xor     esi, esi
0x180017c4f  jmp     short loc_180017C72
0x180017c51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017c58  mov     ecx, 90h; unsigned __int64
0x180017c5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017c62  test    rax, rax
0x180017c65  jz      short loc_180017CD2
0x180017c67  mov     rcx, rax
0x180017c6a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)
0x180017c6f  mov     rsi, rax
0x180017c72  test    rsi, rsi
0x180017c75  jz      short loc_180017CD2
0x180017c77  sub     rdi, rbp
0x180017c7a  mov     r8, rbp; Source
0x180017c7d  mov     r9, rdi; MaxCount
0x180017c80  mov     edx, 81h; SizeInBytes
0x180017c85  mov     rcx, rsi; Destination
0x180017c88  call    cs:__imp_strncpy_s
0x180017c8e  mov     [rsi+81h], dil
0x180017c95  lea     rcx, [rbx+1]
0x180017c99  shl     rcx, 20h
0x180017c9d  or      rcx, r14
0x180017ca0  mov     [rsi+88h], rcx
0x180017ca7  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180017cb1  mov     rax, [rsi+88h]
0x180017cb8  and     rax, rcx
0x180017cbb  mov     [rsi+88h], rax
0x180017cc2  movzx   eax, byte ptr [rsi+81h]
0x180017cc9  mov     byte ptr [rax+rsi], 0
0x180017ccd  mov     rax, rsi
0x180017cd0  jmp     short loc_180017CD4
0x180017cd2  xor     eax, eax
0x180017cd4  add     rsp, 20h
0x180017cd8  pop     r14
0x180017cda  pop     rdi
0x180017cdb  pop     rsi
0x180017cdc  pop     rbp
0x180017cdd  pop     rbx
0x180017cde  retn
```
