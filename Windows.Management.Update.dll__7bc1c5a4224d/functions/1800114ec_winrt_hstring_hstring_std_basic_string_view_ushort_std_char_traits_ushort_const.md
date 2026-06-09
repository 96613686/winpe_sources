# winrt::hstring::hstring(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x1800114ec`
- end: `0x180011557`
- name: `??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `107`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(struct winrt::impl::shared_hstring_header **, __int64)`
- caller_count: `29`
- callee_count: `5`
- tags: ``

## callers

- `0x180010acc`
- `0x180013e50`
- `0x180013e90`
- `0x180013ed0`
- `0x180013f10`
- `0x180013f50`
- `0x180013f90`
- `0x180013fd0`
- `0x180014010`
- `0x180014050`
- `0x180014090`
- `0x1800140d0`
- `0x180014110`
- `0x180014150`
- `0x180014190`
- `0x1800141d0`
- `0x180014210`
- `0x180014250`
- `0x180014290`
- `0x1800142d0`
- `0x18001d738`
- `0x18001ef60`
- `0x18001efa0`
- `0x18002333c`
- `0x180024180`
- `0x1800241c0`
- `0x180024e64`
- `0x180025030`
- `0x180025290`

## callees

- `0x180003392`
- `0x1800033e8`
- `0x180008833`
- `0x1800114ec`
- `0x1800166a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011537`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011537`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::hstring::hstring(
        struct winrt::impl::shared_hstring_header **a1,
        __int64 a2)
{
  __int64 v2; // rsi
  struct winrt::impl::shared_hstring_header *v4; // rdi
  const void *v5; // rbp
  struct winrt::impl::shared_hstring_header *v6; // rax
  __int64 v7; // rdx
  size_t v8; // r8
  void *v9; // rcx

  v2 = *(unsigned int *)(a2 + 8);
  if ( (_DWORD)v2 )
  {
    v5 = *(const void **)a2;
    v6 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v2, a2);
    v4 = v6;
    v8 = 2 * v2;
    if ( 2 * v2 )
    {
      v9 = (char *)v6 + 28;
      if ( v6 != (struct winrt::impl::shared_hstring_header *)-28LL )
      {
        if ( v5 )
        {
          memcpy_0(v9, v5, v8);
          goto LABEL_9;
        }
        memset_0(v9, 0, v8);
      }
      *(_DWORD *)_o__errno(v9, v7, v8) = 22;
      invalid_parameter_noinfo();
    }
  }
  else
  {
    v4 = 0;
  }
LABEL_9:
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x1800114ec  push    rbx
0x1800114ee  push    rbp
0x1800114ef  push    rsi
0x1800114f0  push    rdi
0x1800114f1  sub     rsp, 28h
0x1800114f5  mov     esi, [rdx+8]
0x1800114f8  mov     rbx, rcx
0x1800114fb  test    esi, esi
0x1800114fd  jnz     short loc_180011503
0x1800114ff  xor     edi, edi
0x180011501  jmp     short loc_180011548
0x180011503  mov     rbp, [rdx]
0x180011506  mov     ecx, esi; this
0x180011508  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001150d  mov     r8, rsi
0x180011510  mov     rdi, rax
0x180011513  add     r8, r8; Size
0x180011516  jz      short loc_180011548
0x180011518  lea     rcx, [rax+1Ch]; void *
0x18001151c  test    rcx, rcx
0x18001151f  jz      short loc_180011537
0x180011521  test    rbp, rbp
0x180011524  jz      short loc_180011530
0x180011526  mov     rdx, rbp; Src
0x180011529  call    memcpy_0
0x18001152e  jmp     short loc_180011548
0x180011530  xor     edx, edx; Val
0x180011532  call    memset_0
0x180011537  call    cs:__imp__o__errno
0x18001153d  mov     dword ptr [rax], 16h
0x180011543  call    _invalid_parameter_noinfo
0x180011548  mov     [rbx], rdi
0x18001154b  mov     rax, rbx
0x18001154e  add     rsp, 28h
0x180011552  pop     rdi
0x180011553  pop     rsi
0x180011554  pop     rbp
0x180011555  pop     rbx
0x180011556  retn
```
