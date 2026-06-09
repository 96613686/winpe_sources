# winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)

- ea: `0x1800157c0`
- end: `0x180015859`
- name: `?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z`
- size: `153`
- prototype: `struct winrt::impl::hstring_header *__fastcall(winrt::impl *__hidden this, struct winrt::impl::hstring_header *)`
- caller_count: `31`
- callee_count: `4`
- tags: ``

## callers

- `0x180001dc0`
- `0x180004e40`
- `0x1800052e0`
- `0x1800058e0`
- `0x180006110`
- `0x180006b70`
- `0x180007150`
- `0x180007a20`
- `0x180008c60`
- `0x18000ac40`
- `0x18000ac80`
- `0x18000d1f0`
- `0x18000d4e0`
- `0x18000d7a0`
- `0x18000e040`
- `0x18000ef70`
- `0x180013a90`
- `0x180015860`
- `0x18001c9d0`
- `0x18001eb00`
- `0x1800216e0`
- `0x1800247c0`
- `0x180024840`
- `0x180026450`
- `0x1800266a0`
- `0x180026720`
- `0x180026f60`
- `0x1800273b0`
- `0x180028d10`
- `0x18003a020`
- `0x18003b980`

## callees

- `0x180004350`
- `0x1800157c0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015830`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015830`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001583c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001583c`

## pseudocode

```c
struct winrt::impl::hstring_header *__fastcall winrt::impl::duplicate_hstring(
        winrt::impl *this,
        struct winrt::impl::hstring_header *a2)
{
  const void *v3; // rsi
  __int64 v4; // rdi
  struct winrt::impl::shared_hstring_header *v5; // rbx
  struct winrt::impl::shared_hstring_header *v6; // rax
  void *v7; // rcx
  size_t v8; // r8

  if ( !this )
    return 0;
  if ( (*(_BYTE *)this & 1) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 6);
    return this;
  }
  v3 = (const void *)*((_QWORD *)this + 2);
  v4 = *((unsigned int *)this + 1);
  if ( !(_DWORD)v4 )
    return 0;
  v6 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v4, (unsigned int)a2);
  v5 = v6;
  v7 = (char *)v6 + 28;
  v8 = 2 * v4;
  if ( 2 * v4 )
  {
    if ( v6 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v3 )
      {
        memmove(v7, v3, v8);
        return v5;
      }
      memset(v7, 0, v8);
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  return v5;
}

```

## disassembly

```asm
0x1800157c0  sub     rsp, 28h
0x1800157c4  test    rcx, rcx
0x1800157c7  jnz     short loc_1800157D0
0x1800157c9  xor     eax, eax
0x1800157cb  add     rsp, 28h
0x1800157cf  retn
0x1800157d0  test    byte ptr [rcx], 1
0x1800157d3  jnz     short loc_1800157E1
0x1800157d5  lock inc dword ptr [rcx+18h]
0x1800157d9  mov     rax, rcx
0x1800157dc  add     rsp, 28h
0x1800157e0  retn
0x1800157e1  mov     [rsp+28h+arg_0], rbx
0x1800157e6  mov     [rsp+28h+arg_8], rsi
0x1800157eb  mov     rsi, [rcx+10h]
0x1800157ef  mov     [rsp+28h+var_8], rdi
0x1800157f4  mov     edi, [rcx+4]
0x1800157f7  test    edi, edi
0x1800157f9  jnz     short loc_1800157FF
0x1800157fb  xor     ebx, ebx
0x1800157fd  jmp     short loc_180015842
0x1800157ff  mov     ecx, edi; this
0x180015801  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180015806  mov     r8, rdi
0x180015809  mov     rbx, rax
0x18001580c  lea     rcx, [rax+1Ch]; void *
0x180015810  add     r8, r8; Size
0x180015813  jz      short loc_180015842
0x180015815  test    rcx, rcx
0x180015818  jz      short loc_180015830
0x18001581a  test    rsi, rsi
0x18001581d  jz      short loc_180015829
0x18001581f  mov     rdx, rsi; Src
0x180015822  call    memmove
0x180015827  jmp     short loc_180015842
0x180015829  xor     edx, edx; Val
0x18001582b  call    memset
0x180015830  call    cs:__imp__errno
0x180015836  mov     dword ptr [rax], 16h
0x18001583c  call    cs:__imp__invalid_parameter_noinfo
0x180015842  mov     rdi, [rsp+28h+var_8]
0x180015847  mov     rax, rbx
0x18001584a  mov     rbx, [rsp+28h+arg_0]
0x18001584f  mov     rsi, [rsp+28h+arg_8]
0x180015854  add     rsp, 28h
0x180015858  retn
```
