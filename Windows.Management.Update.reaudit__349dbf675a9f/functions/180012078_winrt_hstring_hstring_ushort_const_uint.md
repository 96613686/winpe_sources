# winrt::hstring::hstring(ushort const *,uint)

- ea: `0x180012078`
- end: `0x18001210e`
- name: `??0hstring@winrt@@QEAA@PEBGI@Z`
- size: `150`
- prototype: `_QWORD(winrt::hstring *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `30`
- callee_count: `5`
- tags: ``

## callers

- `0x180011610`
- `0x180014b10`
- `0x180014b40`
- `0x180014b70`
- `0x180014ba0`
- `0x180014bd0`
- `0x180014c00`
- `0x180014c30`
- `0x180014c60`
- `0x180014c90`
- `0x180014cc0`
- `0x180014cf0`
- `0x180014d20`
- `0x180014d50`
- `0x180014d80`
- `0x180014db0`
- `0x180014de0`
- `0x180014e10`
- `0x180014e40`
- `0x180014e70`
- `0x180018b84`
- `0x18001e9d0`
- `0x180020230`
- `0x180020260`
- `0x180024600`
- `0x180025440`
- `0x180025470`
- `0x180026230`
- `0x180026400`
- `0x18002664c`

## callees

- `0x180003582`
- `0x1800035cc`
- `0x180008de5`
- `0x180012078`
- `0x1800172cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800120d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800120d2`

## pseudocode

```c
winrt::hstring *__fastcall winrt::hstring::hstring(winrt::hstring *this, const unsigned __int16 *a2, unsigned int a3)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx
  struct winrt::impl::shared_hstring_header *v7; // rax
  __int64 v8; // rdx
  struct winrt::impl::shared_hstring_header *v9; // r14
  void *v10; // rcx
  size_t v11; // r8
  winrt::hstring *result; // rax

  v3 = 0;
  if ( a3 )
  {
    v7 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)a3);
    v9 = v7;
    v10 = (char *)v7 + 28;
    v11 = 2LL * a3;
    if ( v11 )
    {
      if ( v7 != (struct winrt::impl::shared_hstring_header *)-28LL )
      {
        if ( a2 )
        {
          memcpy_0(v10, a2, v11);
          goto LABEL_8;
        }
        memset_0(v10, 0, v11);
      }
      *(_DWORD *)_o__errno(v10, v8, v11) = 22;
      invalid_parameter_noinfo();
    }
LABEL_8:
    v3 = v9;
  }
  result = this;
  *(_QWORD *)this = v3;
  return result;
}

```

## disassembly

```asm
0x180012078  mov     rax, rsp
0x18001207b  mov     [rax+8], rbx
0x18001207f  mov     [rax+10h], rbp
0x180012083  mov     [rax+18h], rsi
0x180012087  mov     [rax+20h], rdi
0x18001208b  push    r14
0x18001208d  sub     rsp, 20h
0x180012091  xor     ebx, ebx
0x180012093  mov     esi, r8d
0x180012096  mov     rbp, rdx
0x180012099  mov     rdi, rcx
0x18001209c  test    r8d, r8d
0x18001209f  jz      short loc_1800120EC
0x1800120a1  mov     ecx, esi; this
0x1800120a3  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800120a8  mov     r8d, esi
0x1800120ab  mov     r14, rax
0x1800120ae  lea     rcx, [rax+1Ch]; void *
0x1800120b2  add     r8, r8; Size
0x1800120b5  jz      short loc_1800120E9
0x1800120b7  test    rcx, rcx
0x1800120ba  jz      short loc_1800120D2
0x1800120bc  test    rbp, rbp
0x1800120bf  jz      short loc_1800120CB
0x1800120c1  mov     rdx, rbp; Src
0x1800120c4  call    memcpy_0
0x1800120c9  jmp     short loc_1800120E9
0x1800120cb  xor     edx, edx; Val
0x1800120cd  call    memset_0
0x1800120d2  call    cs:__imp__o__errno
0x1800120d9  nop     dword ptr [rax+rax+00h]
0x1800120de  mov     dword ptr [rax], 16h
0x1800120e4  call    _invalid_parameter_noinfo
0x1800120e9  mov     rbx, r14
0x1800120ec  mov     rbp, [rsp+28h+arg_8]
0x1800120f1  mov     rax, rdi
0x1800120f4  mov     rsi, [rsp+28h+arg_10]
0x1800120f9  mov     [rdi], rbx
0x1800120fc  mov     rbx, [rsp+28h+arg_0]
0x180012101  mov     rdi, [rsp+28h+arg_18]
0x180012106  add     rsp, 20h
0x18001210a  pop     r14
0x18001210c  retn
```
