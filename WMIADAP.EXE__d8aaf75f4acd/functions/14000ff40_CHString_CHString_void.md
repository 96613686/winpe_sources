# CHString::~CHString(void)

- ea: `0x14000ff40`
- end: `0x14000ff8c`
- name: `??1CHString@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(const unsigned __int16 **this)`
- caller_count: `35`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f91c`
- `0x14001057c`
- `0x140011cc0`
- `0x140011cf0`
- `0x140011ee0`
- `0x140012d30`
- `0x140012f60`
- `0x140013440`
- `0x140013510`
- `0x140013860`
- `0x140014060`
- `0x140015f5f`
- `0x140015f95`
- `0x140015fa7`
- `0x14001609a`
- `0x1400160c6`
- `0x140016116`
- `0x140016142`
- `0x14001617c`
- `0x14001618e`
- `0x1400161a0`
- `0x1400161b2`
- `0x1400161c4`
- `0x140016276`
- `0x140016288`
- `0x1400162ac`
- `0x1400162e4`
- `0x1400162f6`
- `0x140016308`
- `0x14001632c`
- `0x14001633e`
- `0x140016350`
- `0x140016362`
- `0x140016374`
- `0x140016386`

## callees

- `0x14000ff40`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ff80`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ff80`

## pseudocode

```c
void __fastcall CHString::~CHString(const unsigned __int16 **this)
{
  const unsigned __int16 *v2; // rax
  char *v3; // rcx

  v2 = *this;
  if ( *this != afxPchNil )
  {
    v3 = byte_140024890;
    if ( v2 - 6 != (const unsigned __int16 *)byte_140024890
      && _InterlockedExchangeAdd((volatile signed __int32 *)v2 - 3, 0xFFFFFFFF) <= 1 )
    {
      if ( *this != afxPchNil )
        v3 = (char *)(*this - 6);
      CWin32DefaultArena::WbemMemFree(v3);
    }
  }
}

```

## disassembly

```asm
0x14000ff40  sub     rsp, 28h
0x14000ff44  mov     rdx, rcx
0x14000ff47  mov     rax, [rcx]
0x14000ff4a  cmp     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x14000ff51  jz      short loc_14000FF87
0x14000ff53  lea     r8, [rax-0Ch]
0x14000ff57  lea     rcx, byte_140024890
0x14000ff5e  cmp     r8, rcx
0x14000ff61  jz      short loc_14000FF87
0x14000ff63  or      eax, 0FFFFFFFFh
0x14000ff66  lock xadd [r8], eax
0x14000ff6b  sub     eax, 1
0x14000ff6e  jg      short loc_14000FF87
0x14000ff70  mov     rax, [rdx]
0x14000ff73  cmp     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x14000ff7a  jz      short loc_14000FF80
0x14000ff7c  lea     rcx, [rax-0Ch]
0x14000ff80  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000ff86  nop
0x14000ff87  add     rsp, 28h
0x14000ff8b  retn
```
