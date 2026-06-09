# CStreamBase::HrCopyRangesToIStream(IStream *)

- ea: `0x180013d70`
- end: `0x180013ea0`
- name: `?HrCopyRangesToIStream@CStreamBase@@UEAAJPEAUIStream@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(CStreamBase *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008c50`

## callees

- `0x180013d70`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CStreamBase::HrCopyRangesToIStream(CStreamBase *this, struct IStream *a2)
{
  char *v2; // rbx
  unsigned int v5; // esi
  __int64 v6; // r9
  __int64 v7; // rdi
  __int64 i; // rbp
  int v10; // eax
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = (char *)this + 16;
  v5 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  v11 = 0;
  if ( a2 )
  {
    if ( (**(int (__fastcall ***)(struct IStream *, GUID *, __int64 *))a2)(a2, &IID_IMILCStreamBase, &v11) >= 0 )
    {
      v6 = v11;
      if ( v11 )
      {
        v7 = v11 + 16;
        if ( v11 != -16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 112LL))(v11 + 16);
          v6 = v11;
        }
      }
      else
      {
        v7 = 0;
      }
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 12); i = (unsigned int)(i + 1) )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 48LL))(
                v6,
                *(unsigned int *)(*((_QWORD *)this + 3) + 4 * i));
        v5 = v10;
        if ( v10 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v10);
          if ( !v7 )
            goto LABEL_10;
LABEL_9:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7);
          goto LABEL_10;
        }
        v6 = v11;
      }
      if ( !v7 )
        goto LABEL_11;
      goto LABEL_9;
    }
LABEL_10:
    v6 = v11;
LABEL_11:
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v11 = 0;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  return v5;
}

```

## disassembly

```asm
0x180013d70  mov     [rsp+arg_8], rbx
0x180013d75  mov     [rsp+arg_10], rbp
0x180013d7a  push    rsi
0x180013d7b  push    rdi
0x180013d7c  push    r14
0x180013d7e  sub     rsp, 20h
0x180013d82  lea     rbx, [rcx+10h]
0x180013d86  mov     r14, rcx
0x180013d89  mov     rax, [rbx]
0x180013d8c  mov     rcx, rbx
0x180013d8f  mov     rdi, rdx
0x180013d92  xor     esi, esi
0x180013d94  mov     rax, [rax+70h]
0x180013d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d9d  mov     [rsp+38h+arg_0], rsi
0x180013da2  test    rdi, rdi
0x180013da5  jz      short loc_180013E16
0x180013da7  mov     rax, [rdi]
0x180013daa  lea     r8, [rsp+38h+arg_0]
0x180013daf  lea     rdx, IID_IMILCStreamBase
0x180013db6  mov     rcx, rdi
0x180013db9  mov     rax, [rax]
0x180013dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc1  test    eax, eax
0x180013dc3  js      short loc_180013E0C
0x180013dc5  mov     r9, [rsp+38h+arg_0]
0x180013dca  test    r9, r9
0x180013dcd  jz      loc_180013E6A
0x180013dd3  lea     rdi, [r9+10h]
0x180013dd7  test    rdi, rdi
0x180013dda  jz      short loc_180013DF0
0x180013ddc  mov     rax, [rdi]
0x180013ddf  mov     rcx, rdi
0x180013de2  mov     rax, [rax+70h]
0x180013de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013deb  mov     r9, [rsp+38h+arg_0]
0x180013df0  xor     ebp, ebp
0x180013df2  cmp     ebp, [r14+30h]
0x180013df6  jb      short loc_180013E3A
0x180013df8  test    rdi, rdi
0x180013dfb  jz      short loc_180013E11
0x180013dfd  mov     rax, [rdi]
0x180013e00  mov     rcx, rdi
0x180013e03  mov     rax, [rax+78h]
0x180013e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0c  mov     r9, [rsp+38h+arg_0]
0x180013e11  test    r9, r9
0x180013e14  jnz     short loc_180013E83
0x180013e16  mov     rcx, [rbx]
0x180013e19  mov     rax, [rcx+78h]
0x180013e1d  mov     rcx, rbx
0x180013e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e25  mov     rbx, [rsp+38h+arg_8]
0x180013e2a  mov     eax, esi
0x180013e2c  mov     rbp, [rsp+38h+arg_10]
0x180013e31  add     rsp, 20h
0x180013e35  pop     r14
0x180013e37  pop     rdi
0x180013e38  pop     rsi
0x180013e39  retn
0x180013e3a  mov     rax, [r9]
0x180013e3d  mov     rcx, r9
0x180013e40  mov     rdx, [r14+18h]
0x180013e44  mov     rax, [rax+30h]
0x180013e48  mov     edx, [rdx+rbp*4]
0x180013e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e50  mov     esi, eax
0x180013e52  test    eax, eax
0x180013e54  jns     short loc_180013E6E
0x180013e56  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180013e5d  jnz     short loc_180013E7A
0x180013e5f  test    eax, eax
0x180013e61  jns     short loc_180013E6E
0x180013e63  test    rdi, rdi
0x180013e66  jnz     short loc_180013DFD
0x180013e68  jmp     short loc_180013E0C
0x180013e6a  xor     edi, edi
0x180013e6c  jmp     short loc_180013DF0
0x180013e6e  mov     r9, [rsp+38h+arg_0]
0x180013e73  inc     ebp
0x180013e75  jmp     loc_180013DF2
0x180013e7a  mov     ecx, eax; int
0x180013e7c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180013e81  jmp     short loc_180013E63
0x180013e83  mov     rcx, [r9]
0x180013e86  mov     rax, [rcx+10h]
0x180013e8a  mov     rcx, r9
0x180013e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e92  mov     [rsp+38h+arg_0], 0
0x180013e9b  jmp     loc_180013E16
```
