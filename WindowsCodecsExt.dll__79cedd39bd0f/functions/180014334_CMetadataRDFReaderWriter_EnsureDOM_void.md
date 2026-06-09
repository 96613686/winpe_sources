# CMetadataRDFReaderWriter::EnsureDOM(void)

- ea: `0x180014334`
- end: `0x180014474`
- name: `?EnsureDOM@CMetadataRDFReaderWriter@@IEAAJXZ`
- size: `320`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180015c60`
- `0x18001d838`
- `0x180020ae0`

## callees

- `0x180014334`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::EnsureDOM(CMetadataRDFReaderWriter *this)
{
  unsigned int v1; // ebx
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v9 = 0;
  v10 = 0;
  if ( *((_QWORD *)this + 23) )
    return v1;
  v3 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64 *))(*(_QWORD *)this + 264LL))(this, &v9);
  v1 = v3;
  if ( v3 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_7;
  }
  v3 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64, __int64 *))(*(_QWORD *)this + 304LL))(
         this,
         v9,
         &v10);
  v1 = v3;
  if ( v3 >= 0 )
  {
    v4 = *((_QWORD *)this + 23);
    v5 = v9;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 23) = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = *((_QWORD *)this + 24);
    v7 = v10;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 24) = v7;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    goto LABEL_17;
  }
  if ( g_doStackCaptures )
LABEL_7:
    DoStackCapture(v3);
LABEL_17:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return v1;
}

```

## disassembly

```asm
0x180014334  mov     r11, rsp
0x180014337  mov     [r11+18h], rbx
0x18001433b  mov     [r11+20h], rsi
0x18001433f  push    rdi
0x180014340  sub     rsp, 20h
0x180014344  xor     ebx, ebx
0x180014346  mov     rdi, rcx
0x180014349  mov     [r11+8], rbx
0x18001434d  mov     [r11+10h], rbx
0x180014351  cmp     [rcx+0B8h], rbx
0x180014358  jnz     loc_180014462
0x18001435e  mov     rax, [rcx]
0x180014361  lea     rdx, [r11+8]
0x180014365  mov     rax, [rax+108h]
0x18001436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014371  mov     ebx, eax
0x180014373  test    eax, eax
0x180014375  jns     short loc_180014385
0x180014377  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001437e  jnz     short loc_1800143B0
0x180014380  jmp     loc_18001442D
0x180014385  mov     rax, [rdi]
0x180014388  lea     r8, [rsp+28h+arg_8]
0x18001438d  mov     rdx, [rsp+28h+arg_0]
0x180014392  mov     rcx, rdi
0x180014395  mov     rax, [rax+130h]
0x18001439c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a1  mov     ebx, eax
0x1800143a3  test    eax, eax
0x1800143a5  jns     short loc_1800143BD
0x1800143a7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800143ae  jz      short loc_1800143B9
0x1800143b0  mov     ecx, eax; int
0x1800143b2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800143b7  jmp     short loc_18001442D
0x1800143b9  test    eax, eax
0x1800143bb  js      short loc_18001442D
0x1800143bd  mov     rcx, [rdi+0B8h]
0x1800143c4  mov     rsi, [rsp+28h+arg_0]
0x1800143c9  test    rcx, rcx
0x1800143cc  jz      short loc_1800143DA
0x1800143ce  mov     rax, [rcx]
0x1800143d1  mov     rax, [rax+10h]
0x1800143d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143da  mov     [rdi+0B8h], rsi
0x1800143e1  test    rsi, rsi
0x1800143e4  jz      short loc_1800143F5
0x1800143e6  mov     rax, [rsi]
0x1800143e9  mov     rcx, rsi
0x1800143ec  mov     rax, [rax+8]
0x1800143f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f5  mov     rcx, [rdi+0C0h]
0x1800143fc  mov     rsi, [rsp+28h+arg_8]
0x180014401  test    rcx, rcx
0x180014404  jz      short loc_180014412
0x180014406  mov     rax, [rcx]
0x180014409  mov     rax, [rax+10h]
0x18001440d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014412  mov     [rdi+0C0h], rsi
0x180014419  test    rsi, rsi
0x18001441c  jz      short loc_18001442D
0x18001441e  mov     rax, [rsi]
0x180014421  mov     rcx, rsi
0x180014424  mov     rax, [rax+8]
0x180014428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001442d  mov     rcx, [rsp+28h+arg_0]
0x180014432  test    rcx, rcx
0x180014435  jz      short loc_18001444C
0x180014437  mov     rax, [rcx]
0x18001443a  mov     rax, [rax+10h]
0x18001443e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014443  mov     [rsp+28h+arg_0], 0
0x18001444c  mov     rcx, [rsp+28h+arg_8]
0x180014451  test    rcx, rcx
0x180014454  jz      short loc_180014462
0x180014456  mov     rdx, [rcx]
0x180014459  mov     rax, [rdx+10h]
0x18001445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014462  mov     rsi, [rsp+28h+arg_18]
0x180014467  mov     eax, ebx
0x180014469  mov     rbx, [rsp+28h+arg_10]
0x18001446e  add     rsp, 20h
0x180014472  pop     rdi
0x180014473  retn
```
