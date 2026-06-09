# CMetadataRDFReaderWriter::HrGenerateDOM(int)

- ea: `0x180020ae0`
- end: `0x180020c7a`
- name: `?HrGenerateDOM@CMetadataRDFReaderWriter@@MEAAJH@Z`
- size: `410`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180014334`
- `0x1800171c4`
- `0x180020ae0`
- `0x180020c80`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrGenerateDOM(CMetadataRDFReaderWriter *this, int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  _QWORD *v7; // r15
  __int64 v8; // rsi
  __int64 v10; // [rsp+20h] [rbp-48h]
  __int64 v11; // [rsp+80h] [rbp+18h] BYREF

  v11 = 0;
  v4 = CMetadataRDFReaderWriter::EnsureDOM(this);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = 0;
    if ( !*((_DWORD *)this + 58) )
      goto LABEL_25;
    v7 = (_QWORD *)((char *)this + 208);
    while ( 1 )
    {
      v8 = *(_QWORD *)(*v7 + 8 * v6);
      if ( (*(_BYTE *)(v8 + 8) & 2) != 0 )
      {
        if ( v8 )
          (**(void (__fastcall ***)(_QWORD, __int64))v8)(*(_QWORD *)(*v7 + 8 * v6), 1);
        v4 = CMILObjectArray<RDFItem *>::RemoveAt((char *)this + 208, (unsigned int)v6);
        v5 = v4;
        if ( v4 < 0 && g_doStackCaptures )
          goto LABEL_24;
        LODWORD(v6) = v6 - 1;
        if ( v4 < 0 )
          goto LABEL_25;
      }
      else
      {
        LODWORD(v10) = a2;
        v4 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, _QWORD, __int64 *, __int64))(*(_QWORD *)this + 328LL))(
               this,
               *(_QWORD *)(*v7 + 8 * v6),
               *((_QWORD *)this + 23),
               &v11,
               v10);
        v5 = v4;
        if ( v4 < 0 )
        {
          if ( g_doStackCaptures )
            goto LABEL_24;
          goto LABEL_25;
        }
        v4 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, __int64, _QWORD, __int64))(*(_QWORD *)this + 320LL))(
               this,
               *((_QWORD *)this + 23),
               v11,
               *((_QWORD *)this + 24),
               v8);
        v5 = v4;
        if ( v4 < 0 )
        {
          if ( g_doStackCaptures )
            goto LABEL_24;
          goto LABEL_25;
        }
        if ( a2 )
          *(_DWORD *)(v8 + 8) &= ~1u;
        if ( v11 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          v11 = 0;
        }
      }
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= *((_DWORD *)this + 58) )
        goto LABEL_25;
    }
  }
  if ( g_doStackCaptures )
LABEL_24:
    DoStackCapture(v4);
LABEL_25:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v5;
}

```

## disassembly

```asm
0x180020ae0  mov     rax, rsp
0x180020ae3  push    rbx
0x180020ae4  push    rbp
0x180020ae5  push    rsi
0x180020ae6  push    rdi
0x180020ae7  push    r14
0x180020ae9  push    r15
0x180020aeb  sub     rsp, 38h
0x180020aef  mov     ebp, edx
0x180020af1  mov     qword ptr [rax+18h], 0
0x180020af9  mov     r14, rcx
0x180020afc  call    ?EnsureDOM@CMetadataRDFReaderWriter@@IEAAJXZ; CMetadataRDFReaderWriter::EnsureDOM(void)
0x180020b01  mov     ebx, eax
0x180020b03  test    eax, eax
0x180020b05  jns     short loc_180020B1C
0x180020b07  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020b0e  jnz     loc_180020C48
0x180020b14  test    eax, eax
0x180020b16  js      loc_180020C4F
0x180020b1c  xor     edi, edi
0x180020b1e  cmp     [r14+0E8h], edi
0x180020b25  jbe     loc_180020C4F
0x180020b2b  lea     r15, [r14+0D0h]
0x180020b32  mov     rax, [r15]
0x180020b35  mov     rsi, [rax+rdi*8]
0x180020b39  test    byte ptr [rsi+8], 2
0x180020b3d  jnz     loc_180020C00
0x180020b43  mov     rax, [r14]
0x180020b46  lea     r9, [rsp+68h+arg_10]
0x180020b4e  mov     r8, [r14+0B8h]
0x180020b55  mov     rdx, rsi
0x180020b58  mov     rcx, r14
0x180020b5b  mov     dword ptr [rsp+68h+var_48], ebp
0x180020b5f  mov     rax, [rax+148h]
0x180020b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6b  mov     ebx, eax
0x180020b6d  test    eax, eax
0x180020b6f  jns     short loc_180020B86
0x180020b71  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020b78  jnz     loc_180020C48
0x180020b7e  test    eax, eax
0x180020b80  js      loc_180020C4F
0x180020b86  mov     rax, [r14]
0x180020b89  mov     rcx, r14
0x180020b8c  mov     r9, [r14+0C0h]
0x180020b93  mov     r8, [rsp+68h+arg_10]
0x180020b9b  mov     rdx, [r14+0B8h]
0x180020ba2  mov     rax, [rax+140h]
0x180020ba9  mov     [rsp+68h+var_48], rsi
0x180020bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb3  mov     ebx, eax
0x180020bb5  test    eax, eax
0x180020bb7  jns     short loc_180020BCE
0x180020bb9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020bc0  jnz     loc_180020C48
0x180020bc6  test    eax, eax
0x180020bc8  js      loc_180020C4F
0x180020bce  test    ebp, ebp
0x180020bd0  jz      short loc_180020BD6
0x180020bd2  and     dword ptr [rsi+8], 0FFFFFFFEh
0x180020bd6  mov     rdx, [rsp+68h+arg_10]
0x180020bde  test    rdx, rdx
0x180020be1  jz      short loc_180020C37
0x180020be3  mov     rax, [rdx]
0x180020be6  mov     rcx, rdx
0x180020be9  mov     rax, [rax+10h]
0x180020bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf2  mov     [rsp+68h+arg_10], 0
0x180020bfe  jmp     short loc_180020C37
0x180020c00  test    rsi, rsi
0x180020c03  jz      short loc_180020C18
0x180020c05  mov     rax, [rsi]
0x180020c08  mov     edx, 1
0x180020c0d  mov     rcx, rsi
0x180020c10  mov     rax, [rax]
0x180020c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c18  mov     edx, edi
0x180020c1a  mov     rcx, r15
0x180020c1d  call    ?RemoveAt@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJI@Z; CMILObjectArray<RDFItem *>::RemoveAt(uint)
0x180020c22  mov     ebx, eax
0x180020c24  test    eax, eax
0x180020c26  jns     short loc_180020C31
0x180020c28  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020c2f  jnz     short loc_180020C48
0x180020c31  dec     edi
0x180020c33  test    eax, eax
0x180020c35  js      short loc_180020C4F
0x180020c37  inc     edi
0x180020c39  cmp     edi, [r14+0E8h]
0x180020c40  jb      loc_180020B32
0x180020c46  jmp     short loc_180020C4F
0x180020c48  mov     ecx, eax; int
0x180020c4a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020c4f  mov     rdx, [rsp+68h+arg_10]
0x180020c57  test    rdx, rdx
0x180020c5a  jz      short loc_180020C6B
0x180020c5c  mov     rcx, [rdx]
0x180020c5f  mov     rax, [rcx+10h]
0x180020c63  mov     rcx, rdx
0x180020c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c6b  mov     eax, ebx
0x180020c6d  add     rsp, 38h
0x180020c71  pop     r15
0x180020c73  pop     r14
0x180020c75  pop     rdi
0x180020c76  pop     rsi
0x180020c77  pop     rbp
0x180020c78  pop     rbx
0x180020c79  retn
```
