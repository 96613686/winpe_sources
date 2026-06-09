# com::string_copy_and_release(char const *)

- ea: `0x1400eb834`
- end: `0x1400eb8ab`
- name: `?string_copy_and_release@com@@YA@PEBD@Z`
- size: `119`
- prototype: `__int64 __fastcall(com *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e9e50`
- `0x1400ede6c`
- `0x1400f00e4`

## callees

- `0x1400eb834`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400eb861`
- `ole32!CoTaskMemAlloc` at `0x1400eb861`

## pseudocode

```c
void *__fastcall com::string_copy_and_release(com *this, const char *a2)
{
  size_t v3; // rdi
  void *v4; // rax
  void *v5; // rbx

  if ( !this )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( *((_BYTE *)this + v3) );
  v4 = CoTaskMemAlloc(v3 + 1);
  v5 = v4;
  if ( v4 )
    memset(v4, 0, v3 + 1);
  else
    v5 = 0;
  memmove(v5, this, v3);
  return v5;
}

```

## disassembly

```asm
0x1400eb834  mov     [rsp+arg_8], rbx
0x1400eb839  mov     [rsp+arg_10], rbp
0x1400eb83e  mov     [rsp+arg_18], rsi
0x1400eb843  push    rdi
0x1400eb844  sub     rsp, 20h
0x1400eb848  mov     rsi, rcx
0x1400eb84b  test    rcx, rcx
0x1400eb84e  jz      short loc_1400EB891
0x1400eb850  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400eb854  inc     rdi
0x1400eb857  cmp     byte ptr [rcx+rdi], 0
0x1400eb85b  jnz     short loc_1400EB854
0x1400eb85d  lea     rcx, [rdi+1]; cb
0x1400eb861  call    cs:__imp_CoTaskMemAlloc
0x1400eb867  mov     rbx, rax
0x1400eb86a  test    rax, rax
0x1400eb86d  jz      short loc_1400EB87F
0x1400eb86f  lea     r8, [rdi+1]; Size
0x1400eb873  xor     edx, edx; Val
0x1400eb875  mov     rcx, rax; void *
0x1400eb878  call    memset
0x1400eb87d  jmp     short loc_1400EB881
0x1400eb87f  xor     ebx, ebx
0x1400eb881  mov     r8, rdi; Size
0x1400eb884  mov     rdx, rsi; Src
0x1400eb887  mov     rcx, rbx; void *
0x1400eb88a  call    memmove
0x1400eb88f  jmp     short loc_1400EB893
0x1400eb891  xor     ebx, ebx
0x1400eb893  mov     rbp, [rsp+28h+arg_10]
0x1400eb898  mov     rax, rbx
0x1400eb89b  mov     rbx, [rsp+28h+arg_8]
0x1400eb8a0  mov     rsi, [rsp+28h+arg_18]
0x1400eb8a5  add     rsp, 20h
0x1400eb8a9  pop     rdi
0x1400eb8aa  retn
```
