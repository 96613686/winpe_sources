# CLogBlock::CLogBlock(char const *,long *)

- ea: `0x18000acb0`
- end: `0x18000acf8`
- name: `??0CLogBlock@@QEAA@PEBDPEAJ@Z`
- size: `72`
- prototype: `CLogBlock *__fastcall(CLogBlock *__hidden this, const char *, int *)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eb30`
- `0x180012b10`
- `0x1800130e0`
- `0x180013430`
- `0x180013b40`
- `0x1800140f0`
- `0x180014140`
- `0x1800146c0`
- `0x1800147a0`
- `0x180014de4`
- `0x180015184`
- `0x180015b30`
- `0x180015d10`
- `0x180016060`
- `0x180016400`
- `0x180016718`
- `0x180016bb8`
- `0x180016d1c`
- `0x180017328`
- `0x180018040`

## callees

- `0x18000acb0`
- `0x1800191ac`

## pseudocode

```c
CLogBlock *__fastcall CLogBlock::CLogBlock(CLogBlock *this, const char *a2, int *a3)
{
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = a3;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, a2);
  }
  return this;
}

```

## disassembly

```asm
0x18000acb0  push    rbx
0x18000acb2  sub     rsp, 20h
0x18000acb6  mov     r9, rdx
0x18000acb9  mov     [rcx+8], rdx
0x18000acbd  mov     rbx, rcx
0x18000acc0  mov     [rcx], r8
0x18000acc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acca  lea     rax, WPP_GLOBAL_Control
0x18000acd1  cmp     rcx, rax
0x18000acd4  jz      short loc_18000ACDF
0x18000acd6  test    dword ptr [rcx+1Ch], 400h
0x18000acdd  jnz     short loc_18000ACE8
0x18000acdf  mov     rax, rbx
0x18000ace2  add     rsp, 20h
0x18000ace6  pop     rbx
0x18000ace7  retn
0x18000ace8  mov     rcx, [rcx+10h]
0x18000acec  mov     edx, 0Ah
0x18000acf1  call    WPP_SF_s
0x18000acf6  jmp     short loc_18000ACDF
```
