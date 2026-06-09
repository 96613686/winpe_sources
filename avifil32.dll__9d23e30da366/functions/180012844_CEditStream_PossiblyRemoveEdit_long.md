# CEditStream::PossiblyRemoveEdit(long)

- ea: `0x180012844`
- end: `0x1800128d4`
- name: `?PossiblyRemoveEdit@CEditStream@@AEAAJJ@Z`
- size: `144`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011594`
- `0x180012224`

## callees

- `0x180012844`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CEditStream::PossiblyRemoveEdit(CEditStream *this, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rcx
  int v7; // eax

  v4 = *((_QWORD *)this + 29);
  v5 = 56LL * a2;
  if ( *(int *)(v4 + v5 + 12) <= 0 )
  {
    v6 = *(_QWORD *)(v4 + 56LL * a2);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v7 = --*((_DWORD *)this + 54);
    if ( a2 + 1 < (unsigned int)a2 )
      return 2147942934LL;
    if ( a2 >= 0 && a2 < v7 )
      memmove_0(
        (void *)(v5 + *((_QWORD *)this + 29)),
        (const void *)(*((_QWORD *)this + 29) + 56LL * (unsigned int)(a2 + 1)),
        56LL * (v7 - a2));
  }
  return 0;
}

```

## disassembly

```asm
0x180012844  mov     [rsp+arg_0], rbx
0x180012849  mov     [rsp+arg_8], rsi
0x18001284e  push    rdi
0x18001284f  sub     rsp, 20h
0x180012853  movsxd  rbx, edx
0x180012856  mov     rdi, rcx
0x180012859  mov     rcx, [rcx+0E8h]
0x180012860  imul    rsi, rbx, 38h ; '8'
0x180012864  cmp     dword ptr [rcx+rsi+0Ch], 0
0x180012869  jg      short loc_1800128C2
0x18001286b  mov     rcx, [rcx+rsi]
0x18001286f  test    rcx, rcx
0x180012872  jz      short loc_180012880
0x180012874  mov     rax, [rcx]
0x180012877  mov     rax, [rax+10h]
0x18001287b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012880  dec     dword ptr [rdi+0D8h]
0x180012886  lea     edx, [rbx+1]
0x180012889  mov     eax, [rdi+0D8h]
0x18001288f  cmp     edx, ebx
0x180012891  jnb     short loc_18001289A
0x180012893  mov     eax, 80070216h
0x180012898  jmp     short loc_1800128C4
0x18001289a  test    ebx, ebx
0x18001289c  js      short loc_1800128C2
0x18001289e  cmp     ebx, eax
0x1800128a0  jge     short loc_1800128C2
0x1800128a2  mov     rcx, [rdi+0E8h]
0x1800128a9  sub     eax, ebx
0x1800128ab  cdqe
0x1800128ad  imul    r8, rax, 38h ; '8'; Size
0x1800128b1  mov     eax, edx
0x1800128b3  imul    rdx, rax, 38h ; '8'
0x1800128b7  add     rdx, rcx; Src
0x1800128ba  add     rcx, rsi; void *
0x1800128bd  call    memmove_0
0x1800128c2  xor     eax, eax
0x1800128c4  mov     rbx, [rsp+28h+arg_0]
0x1800128c9  mov     rsi, [rsp+28h+arg_8]
0x1800128ce  add     rsp, 20h
0x1800128d2  pop     rdi
0x1800128d3  retn
```
