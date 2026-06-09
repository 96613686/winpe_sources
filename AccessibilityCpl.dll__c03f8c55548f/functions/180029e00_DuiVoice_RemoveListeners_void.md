# DuiVoice::RemoveListeners(void)

- ea: `0x180029e00`
- end: `0x180029e80`
- name: `?RemoveListeners@DuiVoice@@AEAAXXZ`
- size: `128`
- prototype: `void __fastcall(DuiVoice *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180029950`
- `0x180029c04`

## callees

- `0x1800299a0`
- `0x180029e00`

## import_xrefs

- `msvcrt!free` at `0x180029e53`
- `msvcrt!free` at `0x180029e53`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180029e3b`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180029e3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DuiVoice::RemoveListeners(DuiVoice *this)
{
  unsigned int v2; // esi
  char *v3; // rbx
  DirectUI::Element *v4; // rcx

  if ( *((_QWORD *)this + 2) )
  {
    v2 = 0;
    v3 = (char *)this + 8;
    do
    {
      v4 = *(DirectUI::Element **)ATL::CAtlArray<DirectUI::Element *,ATL::CElementTraits<DirectUI::Element *>>::operator[](
                                    v3,
                                    v2);
      if ( v4 )
        DirectUI::Element::RemoveListener(v4, this);
      ++v2;
    }
    while ( (unsigned __int64)v2 < *((_QWORD *)this + 2) );
    if ( *(_QWORD *)v3 )
    {
      free(*(void **)v3);
      *(_QWORD *)v3 = 0;
    }
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
  }
}

```

## disassembly

```asm
0x180029e00  mov     [rsp+arg_0], rbx
0x180029e05  mov     [rsp+arg_8], rsi
0x180029e0a  push    rdi
0x180029e0b  sub     rsp, 20h
0x180029e0f  mov     rdi, rcx
0x180029e12  mov     rax, [rcx+10h]
0x180029e16  test    rax, rax
0x180029e19  jz      short loc_180029E70
0x180029e1b  xor     esi, esi
0x180029e1d  lea     rbx, [rcx+8]
0x180029e21  test    rax, rax
0x180029e24  jz      short loc_180029E4B
0x180029e26  mov     edx, esi
0x180029e28  mov     rcx, rbx
0x180029e2b  call    ??A?$CAtlArray@PEAVElement@DirectUI@@V?$CElementTraits@PEAVElement@DirectUI@@@ATL@@@ATL@@QEAAAEAPEAVElement@DirectUI@@_K@Z; ATL::CAtlArray<DirectUI::Element *,ATL::CElementTraits<DirectUI::Element *>>::operator[](unsigned __int64)
0x180029e30  mov     rcx, [rax]
0x180029e33  test    rcx, rcx
0x180029e36  jz      short loc_180029E41
0x180029e38  mov     rdx, rdi
0x180029e3b  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180029e41  inc     esi
0x180029e43  mov     eax, esi
0x180029e45  cmp     rax, [rdi+10h]
0x180029e49  jb      short loc_180029E26
0x180029e4b  mov     rcx, [rbx]; Block
0x180029e4e  test    rcx, rcx
0x180029e51  jz      short loc_180029E60
0x180029e53  call    cs:__imp_free
0x180029e59  mov     qword ptr [rbx], 0
0x180029e60  mov     qword ptr [rbx+8], 0
0x180029e68  mov     qword ptr [rbx+10h], 0
0x180029e70  mov     rbx, [rsp+28h+arg_0]
0x180029e75  mov     rsi, [rsp+28h+arg_8]
0x180029e7a  add     rsp, 20h
0x180029e7e  pop     rdi
0x180029e7f  retn
```
