# CMPEG2Demultiplexer::InitPullModeStream(IAsyncReader *)

- ea: `0x180015260`
- end: `0x180015387`
- name: `?InitPullModeStream@CMPEG2Demultiplexer@@QEAAJPEAUIAsyncReader@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, struct IAsyncReader *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ac30`

## callees

- `0x180014564`
- `0x180015260`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::InitPullModeStream(CMPEG2Demultiplexer *this, struct IAsyncReader *a2)
{
  __int64 v2; // rsi
  __int64 v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  __int64 v7; // rdi
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 42);
  v9 = 0;
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IAsyncReader *))(*(_QWORD *)v2 + 8LL))(
         v2,
         *(_QWORD *)(v2 + 120),
         a2);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
LABEL_10:
    v7 = *((_QWORD *)this + 42);
    if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7);
    CMPEG2Demultiplexer::DeleteAllOutputPins_(this);
    return (unsigned int)v6;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, &v9, &v10);
      if ( v6 >= 0 )
      {
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 344LL) + 16LL) = v9;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 344LL) + 24LL) = v10;
        *(_DWORD *)(v2 + 176) = 1;
      }
    }
  }
  else
  {
    v6 = -2147467259;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 16LL))(v2, v5);
  if ( v6 < 0 )
    goto LABEL_10;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015260  mov     [rsp+arg_8], rbx
0x180015265  push    rbp
0x180015266  push    rsi
0x180015267  push    rdi
0x180015268  sub     rsp, 20h
0x18001526c  mov     rsi, [rcx+150h]
0x180015273  mov     rbp, rcx
0x180015276  mov     r8, rdx
0x180015279  mov     [rsp+38h+arg_0], 0
0x180015282  mov     rcx, rsi
0x180015285  mov     [rsp+38h+arg_10], 0
0x18001528e  mov     rax, [rsi]
0x180015291  mov     rdx, [rsi+78h]
0x180015295  mov     rax, [rax+8]
0x180015299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001529e  mov     rdi, rax
0x1800152a1  test    rax, rax
0x1800152a4  jz      loc_180015342
0x1800152aa  mov     rcx, [rax]
0x1800152ad  mov     rax, [rcx+8]
0x1800152b1  mov     rcx, rdi
0x1800152b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152b9  test    eax, eax
0x1800152bb  jz      short loc_180015325
0x1800152bd  mov     rcx, [rdi]
0x1800152c0  mov     rax, [rcx+10h]
0x1800152c4  mov     rcx, rdi
0x1800152c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152cc  mov     ebx, eax
0x1800152ce  test    eax, eax
0x1800152d0  js      short loc_18001532A
0x1800152d2  mov     rax, [rdi]
0x1800152d5  lea     r8, [rsp+38h+arg_10]
0x1800152da  lea     rdx, [rsp+38h+arg_0]
0x1800152df  mov     rcx, rdi
0x1800152e2  mov     rax, [rax+18h]
0x1800152e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152eb  mov     ebx, eax
0x1800152ed  test    eax, eax
0x1800152ef  js      short loc_18001532A
0x1800152f1  mov     rax, [rsi+78h]
0x1800152f5  mov     rcx, [rax+158h]
0x1800152fc  mov     rax, [rsp+38h+arg_0]
0x180015301  mov     [rcx+10h], rax
0x180015305  mov     rax, [rsi+78h]
0x180015309  mov     rcx, [rax+158h]
0x180015310  mov     rax, [rsp+38h+arg_10]
0x180015315  mov     [rcx+18h], rax
0x180015319  mov     dword ptr [rsi+0B0h], 1
0x180015323  jmp     short loc_18001532A
0x180015325  mov     ebx, 80004005h
0x18001532a  mov     rax, [rsi]
0x18001532d  mov     rdx, rdi
0x180015330  mov     rcx, rsi
0x180015333  mov     rax, [rax+10h]
0x180015337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001533c  test    ebx, ebx
0x18001533e  jns     short loc_180015378
0x180015340  jmp     short loc_180015347
0x180015342  mov     ebx, 8007000Eh
0x180015347  mov     rdi, [rbp+150h]
0x18001534e  mov     rcx, rdi
0x180015351  mov     rax, [rdi]
0x180015354  mov     rax, [rax+30h]
0x180015358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001535d  test    eax, eax
0x18001535f  js      short loc_180015370
0x180015361  mov     rdx, [rdi]
0x180015364  mov     rcx, rdi
0x180015367  mov     rax, [rdx+38h]
0x18001536b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015370  mov     rcx, rbp; this
0x180015373  call    ?DeleteAllOutputPins_@CMPEG2Demultiplexer@@AEAAJXZ; CMPEG2Demultiplexer::DeleteAllOutputPins_(void)
0x180015378  mov     eax, ebx
0x18001537a  mov     rbx, [rsp+38h+arg_8]
0x18001537f  add     rsp, 20h
0x180015383  pop     rdi
0x180015384  pop     rsi
0x180015385  pop     rbp
0x180015386  retn
```
