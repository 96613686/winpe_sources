# CMetadataRDFReaderWriter::SaveToStream(IStream *,int)

- ea: `0x180023c40`
- end: `0x180023cfc`
- name: `?SaveToStream@CMetadataRDFReaderWriter@@MEAAJPEAUIStream@@H@Z`
- size: `188`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800171c4`
- `0x180023c40`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::SaveToStream(
        CMetadataRDFReaderWriter *this,
        struct IStream *a2,
        unsigned int a3)
{
  __int64 v3; // rax
  int v6; // eax
  int v7; // ebx
  int v8; // ecx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+30h] [rbp-38h]

  v3 = *(_QWORD *)this;
  v12 = 0;
  if ( *((_QWORD *)this + 23) )
    v6 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(v3 + 352))(this, a3);
  else
    v6 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(v3 + 296))(this, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (__int64 *)*((_QWORD *)this + 23);
    *((_QWORD *)&v12 + 1) = a2;
    LOWORD(v12) = 13;
    v10 = *v9;
    v13 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v10 + 528))(v9, &v12);
    if ( v7 < 0 && g_doStackCaptures || v7 >= 1 && (v7 = -2147467259, g_doStackCaptures) )
    {
      v8 = v7;
      goto LABEL_12;
    }
  }
  else if ( g_doStackCaptures )
  {
    v8 = v6;
LABEL_12:
    DoStackCapture(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023c40  push    rbx
0x180023c42  push    rsi
0x180023c43  push    rdi
0x180023c44  push    r14
0x180023c46  sub     rsp, 48h
0x180023c4a  mov     rax, [rcx]
0x180023c4d  xor     r14d, r14d
0x180023c50  xorps   xmm0, xmm0
0x180023c53  mov     rsi, rdx
0x180023c56  mov     rdi, rcx
0x180023c59  mov     edx, r8d
0x180023c5c  movups  [rsp+68h+var_48], xmm0
0x180023c61  cmp     [rcx+0B8h], r14
0x180023c68  jz      short loc_180023C89
0x180023c6a  mov     rax, [rax+160h]
0x180023c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c76  mov     ebx, eax
0x180023c78  test    eax, eax
0x180023c7a  jns     short loc_180023C92
0x180023c7c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180023c83  jz      short loc_180023CF0
0x180023c85  mov     ecx, eax
0x180023c87  jmp     short loc_180023CEB
0x180023c89  mov     rax, [rax+128h]
0x180023c90  jmp     short loc_180023C71
0x180023c92  mov     rcx, [rdi+0B8h]
0x180023c99  lea     rdx, [rsp+68h+var_48]
0x180023c9e  mov     qword ptr [rsp+68h+var_48+8], rsi
0x180023ca3  mov     eax, 0Dh
0x180023ca8  mov     word ptr [rsp+68h+var_48], ax
0x180023cad  movups  xmm0, [rsp+68h+var_48]
0x180023cb2  mov     rax, [rcx]
0x180023cb5  mov     [rsp+68h+var_38], r14
0x180023cba  movaps  [rsp+68h+var_48], xmm0
0x180023cbf  mov     rax, [rax+210h]
0x180023cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ccb  mov     ebx, eax
0x180023ccd  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180023cd3  test    ebx, ebx
0x180023cd5  jns     short loc_180023CDB
0x180023cd7  test    eax, eax
0x180023cd9  jnz     short loc_180023CE9
0x180023cdb  cmp     ebx, 1
0x180023cde  jl      short loc_180023CF0
0x180023ce0  mov     ebx, 80004005h
0x180023ce5  test    eax, eax
0x180023ce7  jz      short loc_180023CF0
0x180023ce9  mov     ecx, ebx; int
0x180023ceb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023cf0  mov     eax, ebx
0x180023cf2  add     rsp, 48h
0x180023cf6  pop     r14
0x180023cf8  pop     rdi
0x180023cf9  pop     rsi
0x180023cfa  pop     rbx
0x180023cfb  retn
```
