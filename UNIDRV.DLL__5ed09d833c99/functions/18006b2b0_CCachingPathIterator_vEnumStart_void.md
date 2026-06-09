# CCachingPathIterator::vEnumStart(void)

- ea: `0x18006b2b0`
- end: `0x18006b308`
- name: `?vEnumStart@CCachingPathIterator@@UEAAXXZ`
- size: `88`
- prototype: `void __fastcall(CCachingPathIterator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18006ab14`
- `0x18006b2b0`

## import_xrefs

- `GDI32!PATHOBJ_vEnumStart` at `0x18006b2ee`
- `GDI32!PATHOBJ_vEnumStart` at `0x18006b2ee`

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
0x18006b2b0  mov     [rsp+arg_0], rbx
0x18006b2b5  push    rdi
0x18006b2b6  sub     rsp, 20h
0x18006b2ba  lea     rdi, [rcx+18h]
0x18006b2be  cmp     dword ptr [rdi+10h], 0
0x18006b2c2  lea     rbx, [rcx+10h]
0x18006b2c6  jz      short loc_18006B2D1
0x18006b2c8  mov     rax, [rdi]
0x18006b2cb  mov     [rcx+20h], rax
0x18006b2cf  jmp     short loc_18006B2FA
0x18006b2d1  cmp     dword ptr [rbx], 3
0x18006b2d4  mov     rcx, [rcx+8]; ppo
0x18006b2d8  jle     short loc_18006B2EE
0x18006b2da  mov     rdx, rcx; ppo
0x18006b2dd  mov     rcx, rdi; this
0x18006b2e0  call    ?CreateCache@CPathCache@@QEAAHPEAU_PATHOBJ@@@Z; CPathCache::CreateCache(_PATHOBJ *)
0x18006b2e5  mov     rax, [rdi]
0x18006b2e8  mov     [rdi+8], rax
0x18006b2ec  jmp     short loc_18006B2FA
0x18006b2ee  call    cs:__imp_PATHOBJ_vEnumStart
0x18006b2f5  nop     dword ptr [rax+rax+00h]
0x18006b2fa  inc     dword ptr [rbx]
0x18006b2fc  mov     rbx, [rsp+28h+arg_0]
0x18006b301  add     rsp, 20h
0x18006b305  pop     rdi
0x18006b306  retn
```
