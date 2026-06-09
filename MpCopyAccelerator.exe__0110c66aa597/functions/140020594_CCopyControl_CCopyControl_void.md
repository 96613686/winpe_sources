# CCopyControl::~CCopyControl(void)

- ea: `0x140020594`
- end: `0x1400205fa`
- name: `??1CCopyControl@@AEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CCopyControl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400265b0`

## callees

- `0x140005c40`
- `0x140020594`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400205a9`
- `KERNEL32!CloseHandle` at `0x1400205a9`

## pseudocode

```c
void __fastcall CCopyControl::~CCopyControl(CCopyControl *this)
{
  void *v2; // rcx
  _QWORD **v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = *(void **)this;
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (_QWORD **)*((_QWORD *)this + 1);
  *v3[1] = 0;
  v4 = *v3;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      operator delete(v4);
      v4 = v5;
    }
    while ( v5 );
  }
  operator delete(*((void **)this + 1));
}

```

## disassembly

```asm
0x140020594  mov     [rsp+arg_8], rbx
0x140020599  push    rdi
0x14002059a  sub     rsp, 20h
0x14002059e  mov     rdi, rcx
0x1400205a1  mov     rcx, [rcx]; hObject
0x1400205a4  test    rcx, rcx
0x1400205a7  jz      short loc_1400205B6
0x1400205a9  call    cs:__imp_CloseHandle
0x1400205af  mov     qword ptr [rdi], 0
0x1400205b6  mov     rcx, [rdi+8]
0x1400205ba  mov     rax, [rcx+8]
0x1400205be  mov     qword ptr [rax], 0
0x1400205c5  mov     rcx, [rcx]; void *
0x1400205c8  test    rcx, rcx
0x1400205cb  jz      short loc_1400205E2
0x1400205cd  mov     rbx, [rcx]
0x1400205d0  mov     edx, 18h; unsigned __int64
0x1400205d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400205da  mov     rcx, rbx
0x1400205dd  test    rbx, rbx
0x1400205e0  jnz     short loc_1400205CD
0x1400205e2  mov     rcx, [rdi+8]; void *
0x1400205e6  mov     edx, 18h; unsigned __int64
0x1400205eb  mov     rbx, [rsp+28h+arg_8]
0x1400205f0  add     rsp, 20h
0x1400205f4  pop     rdi
0x1400205f5  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
