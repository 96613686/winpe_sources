# _anonymous_namespace_::to_com_string_copy

- ea: `0x140034d34`
- end: `0x140034d8c`
- name: `_anonymous_namespace_::to_com_string_copy`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400334a0`
- `0x140036570`

## callees

- `0x1400313d8`
- `0x140034d34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140034d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140034d52`

## pseudocode

```c
_WORD *__fastcall anonymous_namespace_::to_com_string_copy(__int64 a1)
{
  __int64 v1; // rdi
  _WORD *result; // rax
  _WORD *v4; // rbx

  v1 = *(_QWORD *)(a1 + 8);
  result = CoTaskMemAlloc(2 * v1 + 2);
  v4 = result;
  if ( result )
  {
    if ( v1 )
      std::_Copy_memmove_n<wchar_t const *,wchar_t *>(*(void **)a1, v1, result);
    v4[v1] = 0;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x140034d34  mov     [rsp+arg_0], rbx
0x140034d39  mov     [rsp+arg_8], rsi
0x140034d3e  push    rdi
0x140034d3f  sub     rsp, 20h
0x140034d43  mov     rdi, [rcx+8]
0x140034d47  mov     rsi, rcx
0x140034d4a  lea     rcx, ds:2[rdi*2]; cb
0x140034d52  call    cs:__imp_CoTaskMemAlloc
0x140034d58  mov     rbx, rax
0x140034d5b  test    rax, rax
0x140034d5e  jz      short loc_140034D7C
0x140034d60  test    rdi, rdi
0x140034d63  jz      short loc_140034D73
0x140034d65  mov     rcx, [rsi]; Src
0x140034d68  mov     r8, rbx
0x140034d6b  mov     rdx, rdi
0x140034d6e  call    ??$_Copy_memmove_n@PEB_WPEA_W@std@@YAPEA_WPEB_W_KPEA_W@Z; std::_Copy_memmove_n<wchar_t const *,wchar_t *>(wchar_t const *,unsigned __int64,wchar_t *)
0x140034d73  xor     eax, eax
0x140034d75  mov     [rbx+rdi*2], ax
0x140034d79  mov     rax, rbx
0x140034d7c  mov     rbx, [rsp+28h+arg_0]
0x140034d81  mov     rsi, [rsp+28h+arg_8]
0x140034d86  add     rsp, 20h
0x140034d8a  pop     rdi
0x140034d8b  retn
```
