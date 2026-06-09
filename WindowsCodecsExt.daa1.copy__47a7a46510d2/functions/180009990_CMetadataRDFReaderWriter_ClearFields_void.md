# CMetadataRDFReaderWriter::ClearFields(void)

- ea: `0x180009990`
- end: `0x180009a53`
- name: `?ClearFields@CMetadataRDFReaderWriter@@MEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009868`
- `0x18000a3b0`
- `0x18000b1e4`
- `0x18000b3f0`
- `0x18000b590`

## callees

- `0x180009990`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::ClearFields(CMetadataRDFReaderWriter *this)
{
  unsigned int v1; // ebp
  char *v2; // rdi
  __int64 i; // rsi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 58);
  v2 = (char *)this + 208;
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
  {
    v5 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)v2 + 8 * i);
    if ( v5 )
      (**v5)(v5, 1);
  }
  *((_DWORD *)this + 36) = 2;
  *((_DWORD *)this + 43) = 0;
  *((_QWORD *)this + 22) = 0;
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 24) = 0;
  }
  v7 = *((_QWORD *)this + 23);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 23) = 0;
  }
  *((_DWORD *)v2 + 6) = 0;
  result = 0;
  *((_QWORD *)this + 30) = 0;
  return result;
}

```

## disassembly

```asm
0x180009990  push    rbx
0x180009992  push    rbp
0x180009993  push    rsi
0x180009994  push    rdi
0x180009995  sub     rsp, 28h
0x180009999  mov     ebp, [rcx+0E8h]
0x18000999f  lea     rdi, [rcx+0D0h]
0x1800099a6  xor     esi, esi
0x1800099a8  mov     rbx, rcx
0x1800099ab  test    ebp, ebp
0x1800099ad  jz      short loc_1800099D1
0x1800099af  mov     rax, [rdi]
0x1800099b2  mov     rcx, [rax+rsi*8]
0x1800099b6  test    rcx, rcx
0x1800099b9  jz      short loc_1800099CB
0x1800099bb  mov     rax, [rcx]
0x1800099be  mov     edx, 1
0x1800099c3  mov     rax, [rax]
0x1800099c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cb  inc     esi
0x1800099cd  cmp     esi, ebp
0x1800099cf  jb      short loc_1800099AF
0x1800099d1  mov     dword ptr [rbx+90h], 2
0x1800099db  mov     dword ptr [rbx+0ACh], 0
0x1800099e5  mov     qword ptr [rbx+0B0h], 0
0x1800099f0  mov     rcx, [rbx+0C0h]
0x1800099f7  test    rcx, rcx
0x1800099fa  jz      short loc_180009A13
0x1800099fc  mov     rax, [rcx]
0x1800099ff  mov     rax, [rax+10h]
0x180009a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a08  mov     qword ptr [rbx+0C0h], 0
0x180009a13  mov     rcx, [rbx+0B8h]
0x180009a1a  test    rcx, rcx
0x180009a1d  jz      short loc_180009A36
0x180009a1f  mov     rax, [rcx]
0x180009a22  mov     rax, [rax+10h]
0x180009a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a2b  mov     qword ptr [rbx+0B8h], 0
0x180009a36  mov     dword ptr [rdi+18h], 0
0x180009a3d  xor     eax, eax
0x180009a3f  mov     qword ptr [rbx+0F0h], 0
0x180009a4a  add     rsp, 28h
0x180009a4e  pop     rdi
0x180009a4f  pop     rsi
0x180009a50  pop     rbp
0x180009a51  pop     rbx
0x180009a52  retn
```
