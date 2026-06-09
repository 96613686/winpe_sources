# CMPEG2Parser::CreateDefaultStream(uchar,ushort const *,CMediaType *,int,int,int)

- ea: `0x180007b40`
- end: `0x180007cb9`
- name: `?CreateDefaultStream@CMPEG2Parser@@AEAAJEPEBGPEAVCMediaType@@HHH@Z`
- size: `377`
- prototype: `__int64 __fastcall(CMPEG2Parser *__hidden this, unsigned __int8, const unsigned __int16 *, struct CMediaType *, int, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bb8`
- `0x180008d84`
- `0x180008ea0`
- `0x180009348`

## callees

- `0x180001008`
- `0x180007b40`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2Parser::CreateDefaultStream(
        CMPEG2Parser *this,
        unsigned __int8 a2,
        const unsigned __int16 *a3,
        struct CMediaType *a4,
        int a5,
        int a6,
        char a7)
{
  __int64 v11; // rsi
  __int64 i; // rax
  char *v13; // rax
  char *v14; // rbx
  _QWORD *v15; // r14
  int v16; // r15d

  v11 = 2LL * a2;
  for ( i = *((_QWORD *)this + 2 * a2 - 369); i; i = *(_QWORD *)(i + 40) )
  {
    if ( !*(_DWORD *)(i + 12) || *(_BYTE *)(i + 9) == a7 )
      return 1;
  }
  v13 = (char *)operator new(0x30u);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  *(_QWORD *)v13 = &CMPEG2Parser::CStream::`vftable';
  v13[9] = a7;
  v15 = v13 + 32;
  v13[8] = a2;
  *((_DWORD *)v13 + 3) = a6;
  *((_DWORD *)v13 + 6) = 0;
  *((_QWORD *)v13 + 4) = 0;
  *((_QWORD *)v13 + 5) = 0;
  v16 = (***((__int64 (__fastcall ****)(_QWORD, const unsigned __int16 *, __int64))this + 1))(
          *((_QWORD *)this + 1),
          a3,
          (__int64)(v13 + 32));
  if ( v16 >= 0 )
  {
    *((_QWORD *)v14 + 5) = *((_QWORD *)this + v11 - 369);
    *((_QWORD *)this + v11 - 369) = v14;
    (*(void (__fastcall **)(_QWORD, struct CMediaType *))(*(_QWORD *)*v15 + 16LL))(*v15, a4);
    if ( *(_QWORD *)a4 != *(_QWORD *)&MEDIATYPE_MPEG2_PES.Data1
      || *((_QWORD *)a4 + 1) != *(_QWORD *)MEDIATYPE_MPEG2_PES.Data4 )
    {
      *(GUID *)a4 = MEDIATYPE_MPEG2_PES;
      (*(void (__fastcall **)(_QWORD, struct CMediaType *))(*(_QWORD *)*v15 + 16LL))(*v15, a4);
    }
    *(GUID *)a4 = MEDIATYPE_MPEG2_PACK;
    (*(void (__fastcall **)(_QWORD, struct CMediaType *))(*(_QWORD *)*v15 + 16LL))(*v15, a4);
    return 0;
  }
  else
  {
    (**(void (__fastcall ***)(char *, __int64))v14)(v14, 1);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x180007b40  push    rbx
0x180007b42  push    rbp
0x180007b43  push    rsi
0x180007b44  push    rdi
0x180007b45  push    r12
0x180007b47  push    r14
0x180007b49  push    r15
0x180007b4b  sub     rsp, 20h
0x180007b4f  mov     r14d, [rsp+58h+arg_30]
0x180007b57  mov     rdi, r9
0x180007b5a  movzx   r15d, dl
0x180007b5e  mov     r12, r8
0x180007b61  mov     esi, r15d
0x180007b64  mov     rbp, rcx
0x180007b67  add     rsi, rsi
0x180007b6a  mov     rax, [rcx+rsi*8-0B88h]
0x180007b72  jmp     short loc_180007B8C
0x180007b74  cmp     dword ptr [rax+0Ch], 0
0x180007b78  jz      loc_180007C15
0x180007b7e  cmp     [rax+9], r14b
0x180007b82  jz      loc_180007C15
0x180007b88  mov     rax, [rax+28h]
0x180007b8c  test    rax, rax
0x180007b8f  jnz     short loc_180007B74
0x180007b91  mov     ecx, 30h ; '0'; Size
0x180007b96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b9b  mov     rbx, rax
0x180007b9e  test    rax, rax
0x180007ba1  jz      loc_180007CA5
0x180007ba7  mov     ecx, [rsp+58h+arg_28]
0x180007bae  lea     rax, ??_7CStream@CMPEG2Parser@@6B@; const CMPEG2Parser::CStream::`vftable'
0x180007bb5  mov     [rbx], rax
0x180007bb8  mov     rdx, r12
0x180007bbb  mov     [rbx+9], r14b
0x180007bbf  lea     r14, [rbx+20h]
0x180007bc3  mov     [rbx+8], r15b
0x180007bc7  mov     r8, r14
0x180007bca  mov     [rbx+0Ch], ecx
0x180007bcd  mov     dword ptr [rbx+18h], 0
0x180007bd4  mov     qword ptr [rbx+20h], 0
0x180007bdc  mov     qword ptr [rbx+28h], 0
0x180007be4  mov     rcx, [rbp+8]
0x180007be8  mov     rax, [rcx]
0x180007beb  mov     rax, [rax]
0x180007bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf3  mov     r15d, eax
0x180007bf6  test    eax, eax
0x180007bf8  jns     short loc_180007C28
0x180007bfa  mov     rcx, [rbx]
0x180007bfd  mov     edx, 1
0x180007c02  mov     rax, [rcx]
0x180007c05  mov     rcx, rbx
0x180007c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c0d  mov     eax, r15d
0x180007c10  jmp     loc_180007CAA
0x180007c15  test    rax, rax
0x180007c18  jz      loc_180007B91
0x180007c1e  mov     eax, 1
0x180007c23  jmp     loc_180007CAA
0x180007c28  mov     rax, [rbp+rsi*8-0B88h]
0x180007c30  mov     rdx, rdi
0x180007c33  mov     [rbx+28h], rax
0x180007c37  mov     [rbp+rsi*8-0B88h], rbx
0x180007c3f  mov     rcx, [r14]
0x180007c42  mov     rax, [rcx]
0x180007c45  mov     rax, [rax+10h]
0x180007c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4e  mov     rax, [rdi]
0x180007c51  cmp     rax, qword ptr cs:MEDIATYPE_MPEG2_PES.Data1
0x180007c58  jnz     short loc_180007C67
0x180007c5a  mov     rax, [rdi+8]
0x180007c5e  cmp     rax, qword ptr cs:MEDIATYPE_MPEG2_PES.Data4
0x180007c65  jz      short loc_180007C84
0x180007c67  movups  xmm0, xmmword ptr cs:MEDIATYPE_MPEG2_PES.Data1
0x180007c6e  mov     rdx, rdi
0x180007c71  movdqu  xmmword ptr [rdi], xmm0
0x180007c75  mov     rcx, [r14]
0x180007c78  mov     rax, [rcx]
0x180007c7b  mov     rax, [rax+10h]
0x180007c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c84  movups  xmm0, xmmword ptr cs:MEDIATYPE_MPEG2_PACK.Data1
0x180007c8b  mov     rdx, rdi
0x180007c8e  movdqu  xmmword ptr [rdi], xmm0
0x180007c92  mov     rcx, [r14]
0x180007c95  mov     rax, [rcx]
0x180007c98  mov     rax, [rax+10h]
0x180007c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca1  xor     eax, eax
0x180007ca3  jmp     short loc_180007CAA
0x180007ca5  mov     eax, 8007000Eh
0x180007caa  add     rsp, 20h
0x180007cae  pop     r15
0x180007cb0  pop     r14
0x180007cb2  pop     r12
0x180007cb4  pop     rdi
0x180007cb5  pop     rsi
0x180007cb6  pop     rbp
0x180007cb7  pop     rbx
0x180007cb8  retn
```
