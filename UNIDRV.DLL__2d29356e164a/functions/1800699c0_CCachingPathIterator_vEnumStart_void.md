# CCachingPathIterator::vEnumStart(void)

- ea: `0x1800699c0`
- end: `0x180069a11`
- name: `?vEnumStart@CCachingPathIterator@@UEAAXXZ`
- size: `81`
- prototype: `void __fastcall(CCachingPathIterator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180069264`
- `0x1800699c0`

## import_xrefs

- `GDI32!PATHOBJ_vEnumStart` at `0x1800699fe`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800699fe`

## pseudocode

```c
void __fastcall CCachingPathIterator::vEnumStart(CCachingPathIterator *this)
{
  CPathCache *v1; // rdi
  int *v2; // rbx
  PATHOBJ *v3; // rcx

  v1 = (CCachingPathIterator *)((char *)this + 24);
  v2 = (int *)((char *)this + 16);
  if ( *((_DWORD *)this + 10) )
  {
    *((_QWORD *)this + 4) = *(_QWORD *)v1;
  }
  else
  {
    v3 = (PATHOBJ *)*((_QWORD *)this + 1);
    if ( *v2 <= 3 )
    {
      PATHOBJ_vEnumStart(v3);
    }
    else
    {
      CPathCache::CreateCache(v1, v3);
      *((_QWORD *)v1 + 1) = *(_QWORD *)v1;
    }
  }
  ++*v2;
}

```

## disassembly

```asm
0x1800699c0  mov     [rsp+arg_0], rbx
0x1800699c5  push    rdi
0x1800699c6  sub     rsp, 20h
0x1800699ca  lea     rdi, [rcx+18h]
0x1800699ce  cmp     dword ptr [rdi+10h], 0
0x1800699d2  lea     rbx, [rcx+10h]
0x1800699d6  jz      short loc_1800699E1
0x1800699d8  mov     rax, [rdi]
0x1800699db  mov     [rcx+20h], rax
0x1800699df  jmp     short loc_180069A04
0x1800699e1  cmp     dword ptr [rbx], 3
0x1800699e4  mov     rcx, [rcx+8]; ppo
0x1800699e8  jle     short loc_1800699FE
0x1800699ea  mov     rdx, rcx; ppo
0x1800699ed  mov     rcx, rdi; this
0x1800699f0  call    ?CreateCache@CPathCache@@QEAAHPEAU_PATHOBJ@@@Z; CPathCache::CreateCache(_PATHOBJ *)
0x1800699f5  mov     rax, [rdi]
0x1800699f8  mov     [rdi+8], rax
0x1800699fc  jmp     short loc_180069A04
0x1800699fe  call    cs:__imp_PATHOBJ_vEnumStart
0x180069a04  inc     dword ptr [rbx]
0x180069a06  mov     rbx, [rsp+28h+arg_0]
0x180069a0b  add     rsp, 20h
0x180069a0f  pop     rdi
0x180069a10  retn
```
