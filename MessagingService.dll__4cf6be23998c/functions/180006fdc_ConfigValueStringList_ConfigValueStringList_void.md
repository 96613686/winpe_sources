# ConfigValueStringList::ConfigValueStringList(void)

- ea: `0x180006fdc`
- end: `0x180007075`
- name: `??0ConfigValueStringList@@QEAA@XZ`
- size: `153`
- prototype: `ConfigValueStringList *__fastcall(ConfigValueStringList *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800015d0`
- `0x180001600`
- `0x180001630`
- `0x180001660`

## callees

- `0x18000266c`
- `0x180006fdc`

## pseudocode

```c
ConfigValueStringList *__fastcall ConfigValueStringList::ConfigValueStringList(ConfigValueStringList *this)
{
  char *v1; // rbx
  __int64 *v3; // rdi
  __int64 v4; // rax
  __int64 *v5; // rdx
  __int64 *v6; // rcx
  ConfigValueStringList *result; // rax

  v1 = (char *)this + 8;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = (char *)this + 8;
  *(_QWORD *)this = &ConfigValueStringList::`vftable';
  *((_QWORD *)this + 2) = (char *)this + 8;
  *((_QWORD *)this + 3) = 0;
  while ( 1 )
  {
    v3 = *(__int64 **)v1;
    if ( *(char **)v1 == v1 )
      break;
    v4 = *v3;
    v5 = (__int64 *)v3[1];
    *v5 = *v3;
    *(_QWORD *)(v4 + 8) = v5;
    v6 = (__int64 *)v3[2];
    if ( v6 != v3 + 4 )
      operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)v1 + 2) = 0;
  result = this;
  *((_DWORD *)this + 10) = 0;
  return result;
}

```

## disassembly

```asm
0x180006fdc  mov     [rsp+arg_8], rbx
0x180006fe1  mov     [rsp+arg_10], rsi
0x180006fe6  push    rdi
0x180006fe7  sub     rsp, 20h
0x180006feb  lea     rbx, [rcx+8]
0x180006fef  mov     qword ptr [rcx+20h], 0
0x180006ff7  lea     rax, ??_7ConfigValueStringList@@6B@; const ConfigValueStringList::`vftable'
0x180006ffe  mov     [rbx], rbx
0x180007001  mov     [rcx], rax
0x180007004  mov     rsi, rcx
0x180007007  mov     [rbx+8], rbx
0x18000700b  mov     qword ptr [rbx+10h], 0
0x180007013  mov     rdi, [rbx]
0x180007016  cmp     rdi, rbx
0x180007019  jz      short loc_180007053
0x18000701b  mov     rax, [rdi]
0x18000701e  mov     rdx, [rdi+8]
0x180007022  mov     [rdx], rax
0x180007025  mov     [rax+8], rdx
0x180007029  lea     rax, [rdi+20h]
0x18000702d  mov     rcx, [rdi+10h]; void *
0x180007031  cmp     rcx, rax
0x180007034  jz      short loc_180007042
0x180007036  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000703d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007042  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007049  mov     rcx, rdi; void *
0x18000704c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007051  jmp     short loc_180007013
0x180007053  mov     qword ptr [rbx+10h], 0
0x18000705b  mov     rax, rsi
0x18000705e  mov     rbx, [rsp+28h+arg_8]
0x180007063  mov     dword ptr [rsi+28h], 0
0x18000706a  mov     rsi, [rsp+28h+arg_10]
0x18000706f  add     rsp, 20h
0x180007073  pop     rdi
0x180007074  retn
```
