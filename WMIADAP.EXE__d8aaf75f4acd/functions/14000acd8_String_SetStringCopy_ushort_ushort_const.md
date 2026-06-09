# __String::SetStringCopy(ushort * &,ushort const * &)

- ea: `0x14000acd8`
- end: `0x14000ad47`
- name: `?SetStringCopy@__String@@SAXAEAPEAGAEAPEBG@Z`
- size: `111`
- prototype: `void __fastcall(unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ab90`
- `0x14000db08`

## callees

- `0x140006284`
- `0x14000acd8`

## import_xrefs

- `msvcrt!wcslen` at `0x14000acfa`
- `msvcrt!wcslen` at `0x14000acfa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000ad19`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000ad19`

## pseudocode

```c
void __fastcall __String::SetStringCopy(unsigned __int16 **a1, const unsigned __int16 **a2)
{
  unsigned int v4; // esi
  unsigned __int64 v5; // rax
  unsigned __int16 *v6; // rax

  if ( *a2 )
  {
    v4 = wcslen(*a2) + 1;
    v5 = 2LL * v4;
    if ( !is_mul_ok(v4, 2u) )
      v5 = -1;
    try
    {
      v6 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v5);
      *a1 = v6;
      if ( v6 )
        StringCchCopyW(v6, v4, *a2);
    }
    catch ( ... )
    {
      if ( *a1 )
      {
        CWin32DefaultArena::WbemMemFree(*a1);
        *a1 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x14000acd8  mov     [rsp+arg_8], rbx
0x14000acdd  mov     [rsp+arg_10], rsi
0x14000ace2  mov     [rsp+arg_0], rcx
0x14000ace7  push    rdi
0x14000ace8  sub     rsp, 20h
0x14000acec  mov     rdi, rdx
0x14000acef  mov     rbx, rcx
0x14000acf2  mov     rcx, [rdx]; String
0x14000acf5  test    rcx, rcx
0x14000acf8  jz      short loc_14000AD37
0x14000acfa  call    cs:__imp_wcslen
0x14000ad00  lea     esi, [rax+1]
0x14000ad03  mov     eax, 2
0x14000ad08  mul     rsi
0x14000ad0b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000ad12  cmovb   rax, rcx
0x14000ad16  mov     rcx, rax
0x14000ad19  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000ad1f  mov     [rbx], rax
0x14000ad22  test    rax, rax
0x14000ad25  jz      short loc_14000AD35
0x14000ad27  mov     r8, [rdi]; unsigned __int16 *
0x14000ad2a  mov     edx, esi; unsigned __int64
0x14000ad2c  mov     rcx, rax; unsigned __int16 *
0x14000ad2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ad34  nop
0x14000ad35  jmp     short $+2
0x14000ad37  mov     rbx, [rsp+28h+arg_8]
0x14000ad3c  mov     rsi, [rsp+28h+arg_10]
0x14000ad41  add     rsp, 20h
0x14000ad45  pop     rdi
0x14000ad46  retn
```
