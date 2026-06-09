# CHookThreadItem::~CHookThreadItem(void)

- ea: `0x18000b098`
- end: `0x18000b0c3`
- name: `??1CHookThreadItem@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CHookThreadItem *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ef5e`
- `0x18000f0df`

## callees

- `0x18000b098`
- `0x18000ce0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHookThreadItem::~CHookThreadItem(CHookThreadItem *this)
{
  char *v1; // rax
  char *v2; // rcx

  v1 = (char *)this + 24;
  v2 = (char *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    if ( v2 != v1 )
      operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000b098  mov     [rsp+arg_0], rcx
0x18000b09d  sub     rsp, 28h
0x18000b0a1  lea     rax, [rcx+18h]
0x18000b0a5  mov     rcx, [rax+10h]; Block
0x18000b0a9  test    rcx, rcx
0x18000b0ac  jz      short loc_18000B0BE
0x18000b0ae  cmp     rcx, rax
0x18000b0b1  jz      short loc_18000B0BE
0x18000b0b3  mov     edx, 8
0x18000b0b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b0bd  nop
0x18000b0be  add     rsp, 28h
0x18000b0c2  retn
```
