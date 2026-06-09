# std::experimental::generator<std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char>>::promise_type::_Rethrow_if_exception(void)

- ea: `0x1800105b0`
- end: `0x1800105fa`
- name: `?_Rethrow_if_exception@promise_type@?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAAXXZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e01c`

## callees

- `0x1800105b0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800105d8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800105d8`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800105bd`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800105bd`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800105ed`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800105ed`

## pseudocode

```c
void __fastcall std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::promise_type::_Rethrow_if_exception(
        __int64 a1)
{
  const void *v1; // rbx
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  v1 = (const void *)(a1 + 8);
  if ( __ExceptionPtrToBool((const void *)(a1 + 8)) )
  {
    v2 = 0;
    __ExceptionPtrCopy(&v2, v1);
    __ExceptionPtrRethrow(&v2);
  }
}

```

## disassembly

```asm
0x1800105b0  push    rbx
0x1800105b2  sub     rsp, 30h
0x1800105b6  lea     rbx, [rcx+8]
0x1800105ba  mov     rcx, rbx
0x1800105bd  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800105c3  test    al, al
0x1800105c5  jz      short loc_1800105F4
0x1800105c7  xorps   xmm0, xmm0
0x1800105ca  movdqu  [rsp+38h+var_18], xmm0
0x1800105d0  mov     rdx, rbx
0x1800105d3  lea     rcx, [rsp+38h+var_18]
0x1800105d8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800105de  lea     rax, [rsp+38h+var_18]
0x1800105e3  mov     [rsp+38h+arg_0], rax
0x1800105e8  lea     rcx, [rsp+38h+var_18]
0x1800105ed  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800105f3  nop
0x1800105f4  add     rsp, 30h
0x1800105f8  pop     rbx
0x1800105f9  retn
```
