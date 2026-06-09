# LKRhash::CLKRLinearHashTable::_AllocateSegment(void)

- ea: `0x1800086f0`
- end: `0x180008824`
- name: `?_AllocateSegment@CLKRLinearHashTable@LKRhash@@AEBAQEAVCSegment@2@XZ`
- size: `308`
- prototype: `struct LKRhash::CSegment *__fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009574`
- `0x18000a330`

## callees

- `0x180007a08`
- `0x1800086f0`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct LKRhash::CSegment *__fastcall LKRhash::CLKRLinearHashTable::_AllocateSegment(LKRhash::CLKRLinearHashTable *this)
{
  LKRhash::CBucket *v1; // rax
  LKRhash::CBucket *v2; // rbx
  LKRhash::CBucket *v3; // rdi
  __int64 v4; // rsi
  LKRhash::CBucket *v5; // rax
  LKRhash::CBucket *v6; // rdi
  __int64 v7; // rsi
  LKRhash::CBucket *v8; // rax
  LKRhash::CBucket *v9; // rdi
  __int64 v10; // rsi

  if ( *((_DWORD *)this + 16) == 1 )
  {
    v8 = (LKRhash::CBucket *)(***((__int64 (__fastcall ****)(_QWORD, __int64, _QWORD))this + 18))(
                               *((_QWORD *)this + 18),
                               512,
                               0);
    v2 = v8;
    if ( v8 )
    {
      LKRhash::CBucket::CBucket(v8);
      v9 = (LKRhash::CBucket *)((char *)v2 + 64);
      v10 = 7;
      do
      {
        LKRhash::CBucket::CBucket(v9);
        v9 = (LKRhash::CBucket *)((char *)v9 + 64);
        --v10;
      }
      while ( v10 );
    }
    else
    {
      return 0;
    }
  }
  else if ( *((_DWORD *)this + 16) == 3 )
  {
    v1 = (LKRhash::CBucket *)(***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 18))(
                               *((_QWORD *)this + 18),
                               0x8000,
                               2);
    v2 = v1;
    if ( v1 )
    {
      LKRhash::CBucket::CBucket(v1);
      v3 = (LKRhash::CBucket *)((char *)v2 + 64);
      v4 = 511;
      do
      {
        LKRhash::CBucket::CBucket(v3);
        v3 = (LKRhash::CBucket *)((char *)v3 + 64);
        --v4;
      }
      while ( v4 );
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v5 = (LKRhash::CBucket *)(***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 18))(
                               *((_QWORD *)this + 18),
                               4096,
                               1);
    v2 = v5;
    if ( v5 )
    {
      LKRhash::CBucket::CBucket(v5);
      v6 = (LKRhash::CBucket *)((char *)v2 + 64);
      v7 = 63;
      do
      {
        LKRhash::CBucket::CBucket(v6);
        v6 = (LKRhash::CBucket *)((char *)v6 + 64);
        --v7;
      }
      while ( v7 );
    }
    else
    {
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800086f0  mov     [rsp+arg_10], rbx
0x1800086f5  mov     [rsp+arg_18], rsi
0x1800086fa  mov     [rsp+arg_0], rcx
0x1800086ff  push    rdi
0x180008700  sub     rsp, 20h
0x180008704  mov     edx, [rcx+40h]
0x180008707  sub     edx, 1
0x18000870a  jz      loc_1800087C3
0x180008710  sub     edx, 1
0x180008713  jz      short loc_180008770
0x180008715  cmp     edx, 1
0x180008718  jnz     short loc_180008770
0x18000871a  mov     rcx, [rcx+90h]
0x180008721  mov     rax, [rcx]
0x180008724  mov     edx, 8000h
0x180008729  mov     r8d, 2
0x18000872f  mov     rax, [rax]
0x180008732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008737  mov     rbx, rax
0x18000873a  mov     [rsp+28h+arg_8], rax
0x18000873f  test    rax, rax
0x180008742  jz      short loc_180008769
0x180008744  mov     rcx, rax; this
0x180008747  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x18000874c  lea     rdi, [rbx+40h]
0x180008750  mov     esi, 1FFh
0x180008755  mov     rcx, rdi; this
0x180008758  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x18000875d  add     rdi, 40h ; '@'
0x180008761  sub     rsi, 1
0x180008765  jnz     short loc_180008755
0x180008767  jmp     short loc_18000876B
0x180008769  xor     ebx, ebx
0x18000876b  jmp     loc_180008811
0x180008770  mov     rcx, [rcx+90h]
0x180008777  mov     rax, [rcx]
0x18000877a  mov     edx, 1000h
0x18000877f  mov     r8d, 1
0x180008785  mov     rax, [rax]
0x180008788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878d  mov     rbx, rax
0x180008790  mov     [rsp+28h+arg_8], rax
0x180008795  test    rax, rax
0x180008798  jz      short loc_1800087BF
0x18000879a  mov     rcx, rax; this
0x18000879d  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x1800087a2  lea     rdi, [rbx+40h]
0x1800087a6  mov     esi, 3Fh ; '?'
0x1800087ab  mov     rcx, rdi; this
0x1800087ae  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x1800087b3  add     rdi, 40h ; '@'
0x1800087b7  sub     rsi, 1
0x1800087bb  jnz     short loc_1800087AB
0x1800087bd  jmp     short loc_1800087C1
0x1800087bf  xor     ebx, ebx
0x1800087c1  jmp     short loc_180008811
0x1800087c3  mov     rcx, [rcx+90h]
0x1800087ca  mov     rax, [rcx]
0x1800087cd  xor     r8d, r8d
0x1800087d0  mov     edx, 200h
0x1800087d5  mov     rax, [rax]
0x1800087d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087dd  mov     rbx, rax
0x1800087e0  mov     [rsp+28h+arg_8], rax
0x1800087e5  test    rax, rax
0x1800087e8  jz      short loc_18000880F
0x1800087ea  mov     rcx, rax; this
0x1800087ed  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x1800087f2  lea     rdi, [rbx+40h]
0x1800087f6  mov     esi, 7
0x1800087fb  mov     rcx, rdi; this
0x1800087fe  call    ??0CBucket@LKRhash@@QEAA@XZ; LKRhash::CBucket::CBucket(void)
0x180008803  add     rdi, 40h ; '@'
0x180008807  sub     rsi, 1
0x18000880b  jnz     short loc_1800087FB
0x18000880d  jmp     short loc_180008811
0x18000880f  xor     ebx, ebx
0x180008811  mov     rax, rbx
0x180008814  mov     rbx, [rsp+28h+arg_10]
0x180008819  mov     rsi, [rsp+28h+arg_18]
0x18000881e  add     rsp, 20h
0x180008822  pop     rdi
0x180008823  retn
```
