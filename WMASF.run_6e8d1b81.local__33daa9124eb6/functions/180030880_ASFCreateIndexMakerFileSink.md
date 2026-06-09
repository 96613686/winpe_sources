# ASFCreateIndexMakerFileSink

- ea: `0x180030880`
- end: `0x18003094f`
- name: `ASFCreateIndexMakerFileSink`
- size: `207`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001174`
- `0x1800011cc`
- `0x18000ff88`
- `0x180030880`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall ASFCreateIndexMakerFileSink(unsigned __int16 *a1, __int64 a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  unsigned int v9; // ebx

  v4 = operator new(0x20u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[2] = 0;
  *v4 = &CASFIndexMakerFileSink::`vftable';
  *((_DWORD *)v4 + 2) = 1;
  if ( a1 )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v7 + 1, 2u));
    v5[2] = v8;
    if ( v8 )
    {
      do
        ++v6;
      while ( a1[v6] );
      StringCchCopyW(v8, v6 + 1, a1);
    }
  }
  v5[3] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64))*v5)(v5, &IID_IASFIndexMakerSink, a2);
  (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  return v9;
}

```

## disassembly

```asm
0x180030880  push    rbx
0x180030882  push    rbp
0x180030883  push    rsi
0x180030884  push    rdi
0x180030885  push    r14
0x180030887  sub     rsp, 20h
0x18003088b  mov     rsi, rcx
0x18003088e  mov     rbp, rdx
0x180030891  mov     ecx, 20h ; ' '; Size
0x180030896  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003089b  xor     r14d, r14d
0x18003089e  mov     rdi, rax
0x1800308a1  test    rax, rax
0x1800308a4  jz      loc_18003093F
0x1800308aa  mov     [rdi+10h], r14
0x1800308ae  lea     rax, ??_7CASFIndexMakerFileSink@@6B@; const CASFIndexMakerFileSink::`vftable'
0x1800308b5  mov     [rdi], rax
0x1800308b8  mov     dword ptr [rdi+8], 1
0x1800308bf  test    rsi, rsi
0x1800308c2  jz      short loc_18003090E
0x1800308c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800308c8  mov     rcx, rbx
0x1800308cb  inc     rcx
0x1800308ce  cmp     [rsi+rcx*2], r14w
0x1800308d3  jnz     short loc_1800308CB
0x1800308d5  inc     rcx
0x1800308d8  mov     eax, 2
0x1800308dd  mul     rcx
0x1800308e0  cmovb   rax, rbx
0x1800308e4  mov     rcx, rax; unsigned __int64
0x1800308e7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800308ec  mov     [rdi+10h], rax
0x1800308f0  test    rax, rax
0x1800308f3  jz      short loc_18003090E
0x1800308f5  inc     rbx
0x1800308f8  cmp     [rsi+rbx*2], r14w
0x1800308fd  jnz     short loc_1800308F5
0x1800308ff  lea     rdx, [rbx+1]; unsigned __int64
0x180030903  mov     r8, rsi; unsigned __int16 *
0x180030906  mov     rcx, rax; unsigned __int16 *
0x180030909  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003090e  mov     [rdi+18h], r14
0x180030912  lea     rdx, IID_IASFIndexMakerSink
0x180030919  mov     rax, [rdi]
0x18003091c  mov     r8, rbp
0x18003091f  mov     rcx, rdi
0x180030922  mov     rax, [rax]
0x180030925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003092a  mov     rcx, [rdi]
0x18003092d  mov     ebx, eax
0x18003092f  mov     rax, [rcx+10h]
0x180030933  mov     rcx, rdi
0x180030936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003093b  mov     eax, ebx
0x18003093d  jmp     short loc_180030944
0x18003093f  mov     eax, 8007000Eh
0x180030944  add     rsp, 20h
0x180030948  pop     r14
0x18003094a  pop     rdi
0x18003094b  pop     rsi
0x18003094c  pop     rbp
0x18003094d  pop     rbx
0x18003094e  retn
```
