# ConfigValueStringList::~ConfigValueStringList(void)

- ea: `0x18000707c`
- end: `0x1800070e7`
- name: `??1ConfigValueStringList@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(ConfigValueStringList *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800070f0`
- `0x18000b0a0`
- `0x18000b0c0`
- `0x18000b0e0`
- `0x18000b100`

## callees

- `0x18000266c`
- `0x18000707c`

## pseudocode

```c
void __fastcall ConfigValueStringList::~ConfigValueStringList(ConfigValueStringList *this)
{
  char *v1; // rdi
  __int64 *v2; // rbx
  __int64 v3; // rax
  __int64 *v4; // rdx
  __int64 *v5; // rcx

  *(_QWORD *)this = &ConfigValueStringList::`vftable';
  v1 = (char *)this + 8;
  while ( 1 )
  {
    v2 = *(__int64 **)v1;
    if ( *(char **)v1 == v1 )
      break;
    v3 = *v2;
    v4 = (__int64 *)v2[1];
    *v4 = *v2;
    *(_QWORD *)(v3 + 8) = v4;
    v5 = (__int64 *)v2[2];
    if ( v5 != v2 + 4 )
      operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)v1 + 2) = 0;
}

```

## disassembly

```asm
0x18000707c  mov     [rsp+arg_8], rbx
0x180007081  push    rdi
0x180007082  sub     rsp, 20h
0x180007086  lea     rax, ??_7ConfigValueStringList@@6B@; const ConfigValueStringList::`vftable'
0x18000708d  mov     [rcx], rax
0x180007090  lea     rdi, [rcx+8]
0x180007094  mov     rbx, [rdi]
0x180007097  cmp     rbx, rdi
0x18000709a  jz      short loc_1800070D4
0x18000709c  mov     rax, [rbx]
0x18000709f  mov     rdx, [rbx+8]
0x1800070a3  mov     [rdx], rax
0x1800070a6  mov     [rax+8], rdx
0x1800070aa  lea     rax, [rbx+20h]
0x1800070ae  mov     rcx, [rbx+10h]; void *
0x1800070b2  cmp     rcx, rax
0x1800070b5  jz      short loc_1800070C3
0x1800070b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800070be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800070c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800070ca  mov     rcx, rbx; void *
0x1800070cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800070d2  jmp     short loc_180007094
0x1800070d4  mov     rbx, [rsp+28h+arg_8]
0x1800070d9  mov     qword ptr [rdi+10h], 0
0x1800070e1  add     rsp, 20h
0x1800070e5  pop     rdi
0x1800070e6  retn
```
