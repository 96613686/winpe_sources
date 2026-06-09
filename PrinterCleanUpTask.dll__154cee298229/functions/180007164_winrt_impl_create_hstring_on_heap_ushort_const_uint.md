# winrt::impl::create_hstring_on_heap(ushort const *,uint)

- ea: `0x180007164`
- end: `0x1800071d5`
- name: `?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z`
- size: `113`
- prototype: `struct winrt::impl::hstring_header *__fastcall(winrt::impl *this, winrt::impl *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006a54`
- `0x18000f4b4`

## callees

- `0x180002aea`
- `0x180002b78`
- `0x180003405`
- `0x180007164`
- `0x180007340`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800071b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800071b1`

## pseudocode

```c
struct winrt::impl::hstring_header *__fastcall winrt::impl::create_hstring_on_heap(winrt::impl *this, winrt::impl *a2)
{
  __int64 v2; // rbx
  struct winrt::impl::shared_hstring_header *v5; // rax
  __int64 v6; // rdx
  struct winrt::impl::shared_hstring_header *v7; // rdi
  size_t v8; // r8
  void *v9; // rcx

  v2 = (unsigned int)a2;
  if ( !(_DWORD)a2 )
    return 0;
  v5 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)a2, (unsigned int)a2);
  v7 = v5;
  v8 = 2 * v2;
  if ( 2 * v2 )
  {
    v9 = (char *)v5 + 28;
    if ( v5 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( this )
      {
        memcpy_0(v9, this, v8);
        return v7;
      }
      memset_0(v9, 0, v8);
    }
    *(_DWORD *)_o__errno(v9, v6, v8) = 22;
    invalid_parameter_noinfo();
  }
  return v7;
}

```

## disassembly

```asm
0x180007164  mov     [rsp+arg_0], rbx
0x180007169  mov     [rsp+arg_8], rsi
0x18000716e  push    rdi
0x18000716f  sub     rsp, 20h
0x180007173  mov     ebx, edx
0x180007175  mov     rsi, rcx
0x180007178  test    edx, edx
0x18000717a  jnz     short loc_180007180
0x18000717c  xor     eax, eax
0x18000717e  jmp     short loc_1800071C5
0x180007180  mov     ecx, ebx; this
0x180007182  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180007187  mov     r8, rbx
0x18000718a  mov     rdi, rax
0x18000718d  add     r8, r8; Size
0x180007190  jz      short loc_1800071C2
0x180007192  lea     rcx, [rax+1Ch]; void *
0x180007196  test    rcx, rcx
0x180007199  jz      short loc_1800071B1
0x18000719b  test    rsi, rsi
0x18000719e  jz      short loc_1800071AA
0x1800071a0  mov     rdx, rsi; Src
0x1800071a3  call    memcpy_0
0x1800071a8  jmp     short loc_1800071C2
0x1800071aa  xor     edx, edx; Val
0x1800071ac  call    memset_0
0x1800071b1  call    cs:__imp__o__errno
0x1800071b7  mov     dword ptr [rax], 16h
0x1800071bd  call    _invalid_parameter_noinfo
0x1800071c2  mov     rax, rdi
0x1800071c5  mov     rbx, [rsp+28h+arg_0]
0x1800071ca  mov     rsi, [rsp+28h+arg_8]
0x1800071cf  add     rsp, 20h
0x1800071d3  pop     rdi
0x1800071d4  retn
```
