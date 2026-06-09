# CMetadataXMPReaderWriter::ClearXMPFields(int)

- ea: `0x18000b1e4`
- end: `0x18000b290`
- name: `?ClearXMPFields@CMetadataXMPReaderWriter@@IEAAJH@Z`
- size: `172`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022a00`

## callees

- `0x180009990`
- `0x18000b1e4`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::ClearXMPFields(CMetadataXMPReaderWriter *this, int a2)
{
  unsigned int v2; // r14d
  char *v3; // rsi
  unsigned int v4; // edi
  __int64 i; // rbp
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  __int64 v9; // rcx
  int v11; // eax

  v2 = *((_DWORD *)this + 72);
  v3 = (char *)this + 264;
  v4 = 0;
  for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
  {
    v8 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)v3 + 8 * i);
    if ( v8 )
      (**v8)(v8, 1);
  }
  *((_DWORD *)v3 + 6) = 0;
  v9 = *((_QWORD *)this + 31);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 31) = 0;
  }
  *((_QWORD *)this + 32) = 0;
  if ( a2 )
  {
    v11 = CMetadataRDFReaderWriter::ClearFields(this);
    v4 = v11;
    if ( v11 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v11);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000b1e4  push    rbx
0x18000b1e6  push    rbp
0x18000b1e7  push    rsi
0x18000b1e8  push    rdi
0x18000b1e9  push    r14
0x18000b1eb  push    r15
0x18000b1ed  sub     rsp, 28h
0x18000b1f1  mov     r14d, [rcx+120h]
0x18000b1f8  lea     rsi, [rcx+108h]
0x18000b1ff  xor     edi, edi
0x18000b201  xor     ebp, ebp
0x18000b203  mov     r15d, edx
0x18000b206  mov     rbx, rcx
0x18000b209  test    r14d, r14d
0x18000b20c  jz      short loc_18000B231
0x18000b20e  mov     rax, [rsi]
0x18000b211  mov     rcx, [rax+rbp*8]
0x18000b215  test    rcx, rcx
0x18000b218  jz      short loc_18000B22A
0x18000b21a  mov     rax, [rcx]
0x18000b21d  mov     edx, 1
0x18000b222  mov     rax, [rax]
0x18000b225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b22a  inc     ebp
0x18000b22c  cmp     ebp, r14d
0x18000b22f  jb      short loc_18000B20E
0x18000b231  mov     [rsi+18h], edi
0x18000b234  mov     rcx, [rbx+0F8h]
0x18000b23b  test    rcx, rcx
0x18000b23e  jnz     short loc_18000B27B
0x18000b240  mov     [rbx+100h], rdi
0x18000b247  test    r15d, r15d
0x18000b24a  jnz     short loc_18000B25B
0x18000b24c  mov     eax, edi
0x18000b24e  add     rsp, 28h
0x18000b252  pop     r15
0x18000b254  pop     r14
0x18000b256  pop     rdi
0x18000b257  pop     rsi
0x18000b258  pop     rbp
0x18000b259  pop     rbx
0x18000b25a  retn
0x18000b25b  mov     rcx, rbx; this
0x18000b25e  call    ?ClearFields@CMetadataRDFReaderWriter@@MEAAJXZ; CMetadataRDFReaderWriter::ClearFields(void)
0x18000b263  mov     edi, eax
0x18000b265  test    eax, eax
0x18000b267  jns     short loc_18000B24C
0x18000b269  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000b270  jz      short loc_18000B24C
0x18000b272  mov     ecx, eax; int
0x18000b274  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000b279  jmp     short loc_18000B24C
0x18000b27b  mov     rax, [rcx]
0x18000b27e  mov     rax, [rax+10h]
0x18000b282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b287  mov     [rbx+0F8h], rdi
0x18000b28e  jmp     short loc_18000B240
```
