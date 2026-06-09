# winrt::param::hstring::create_string_reference(ushort const * const,unsigned __int64)

- ea: `0x18000f44c`
- end: `0x18000f488`
- name: `?create_string_reference@hstring@param@winrt@@AEAAXQEBG_K@Z`
- size: `60`
- prototype: `void __fastcall(winrt::param::hstring *this, const unsigned __int16 *const, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a280`
- `0x18000a2b0`
- `0x18000a2d4`

## callees

- `0x18000f44c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f467`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f467`

## pseudocode

```c
void __fastcall winrt::param::hstring::create_string_reference(
        winrt::param::hstring *this,
        const unsigned __int16 *const a2,
        int a3)
{
  if ( a3 )
  {
    if ( a2[a3] )
      abort();
    *((_DWORD *)this + 2) = 1;
    *((_DWORD *)this + 3) = a3;
    *((_QWORD *)this + 3) = a2;
    *(_QWORD *)this = (char *)this + 8;
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000f44c  sub     rsp, 28h
0x18000f450  xor     r9d, r9d
0x18000f453  test    r8d, r8d
0x18000f456  jnz     short loc_18000F45D
0x18000f458  mov     [rcx], r9
0x18000f45b  jmp     short loc_18000F483
0x18000f45d  mov     eax, r8d
0x18000f460  cmp     [rdx+rax*2], r9w
0x18000f465  jz      short loc_18000F46E
0x18000f467  call    cs:__imp_abort
0x18000f46e  lea     rax, [rcx+8]
0x18000f472  mov     dword ptr [rax], 1
0x18000f478  mov     [rax+4], r8d
0x18000f47c  mov     [rax+10h], rdx
0x18000f480  mov     [rcx], rax
0x18000f483  add     rsp, 28h
0x18000f487  retn
```
