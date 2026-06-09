# winrt::param::hstring::create_string_reference(ushort const * const,unsigned __int64)

- ea: `0x180012e7c`
- end: `0x180012eb8`
- name: `?create_string_reference@hstring@param@winrt@@AEAAXQEBG_K@Z`
- size: `60`
- prototype: `void __fastcall(winrt::param::hstring *this, const unsigned __int16 *const, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800109e8`
- `0x180010a0c`

## callees

- `0x180012e7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012e97`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012e97`

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
0x180012e7c  sub     rsp, 28h
0x180012e80  xor     r9d, r9d
0x180012e83  test    r8d, r8d
0x180012e86  jnz     short loc_180012E8D
0x180012e88  mov     [rcx], r9
0x180012e8b  jmp     short loc_180012EB3
0x180012e8d  mov     eax, r8d
0x180012e90  cmp     [rdx+rax*2], r9w
0x180012e95  jz      short loc_180012E9E
0x180012e97  call    cs:__imp_abort
0x180012e9e  lea     rax, [rcx+8]
0x180012ea2  mov     dword ptr [rax], 1
0x180012ea8  mov     [rax+4], r8d
0x180012eac  mov     [rax+10h], rdx
0x180012eb0  mov     [rcx], rax
0x180012eb3  add     rsp, 28h
0x180012eb7  retn
```
