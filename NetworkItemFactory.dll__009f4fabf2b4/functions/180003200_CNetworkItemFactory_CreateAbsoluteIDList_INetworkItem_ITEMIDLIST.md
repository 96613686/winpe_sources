# CNetworkItemFactory::CreateAbsoluteIDList(INetworkItem *,_ITEMIDLIST * *)

- ea: `0x180003200`
- end: `0x180003278`
- name: `?CreateAbsoluteIDList@CNetworkItemFactory@@UEAAJPEAUINetworkItem@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, struct INetworkItem *, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003200`
- `0x18000b010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180003244`
- `SHELL32!__imp_ILCombine` at `0x180003244`
- `SHELL32!__imp_ILFree` at `0x180003260`
- `SHELL32!__imp_ILFree` at `0x180003260`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::CreateAbsoluteIDList(
        LPCITEMIDLIST *this,
        struct INetworkItem *a2,
        struct _ITEMIDLIST **a3)
{
  LPCITEMIDLIST v4; // rax
  int v6; // ebx
  struct _ITEMIDLIST *v7; // rax
  LPCITEMIDLIST pidl2; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v4 = *this;
  pidl2 = 0;
  v6 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, struct INetworkItem *, LPCITEMIDLIST *))v4[34].mkid.abID)(
         this,
         a2,
         &pidl2);
  if ( v6 >= 0 )
  {
    v7 = ILCombine(this[9], pidl2);
    if ( v7 )
    {
      v6 = 0;
      *a3 = v7;
    }
    else
    {
      v6 = -2147024882;
    }
    ILFree((LPITEMIDLIST)pidl2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003200  mov     r11, rsp
0x180003203  mov     [r11+10h], rbx
0x180003207  mov     [r11+18h], rsi
0x18000320b  push    rdi
0x18000320c  sub     rsp, 20h
0x180003210  mov     qword ptr [r8], 0
0x180003217  mov     rsi, r8
0x18000321a  mov     rax, [rcx]
0x18000321d  lea     r8, [r11+8]
0x180003221  mov     rdi, rcx
0x180003224  mov     qword ptr [r11+8], 0
0x18000322c  mov     rax, [rax+68h]
0x180003230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003235  mov     ebx, eax
0x180003237  test    eax, eax
0x180003239  js      short loc_180003266
0x18000323b  mov     rdx, [rsp+28h+pidl2]; pidl2
0x180003240  mov     rcx, [rdi+48h]; pidl1
0x180003244  call    cs:__imp_ILCombine
0x18000324a  test    rax, rax
0x18000324d  jz      short loc_180003256
0x18000324f  xor     ebx, ebx
0x180003251  mov     [rsi], rax
0x180003254  jmp     short loc_18000325B
0x180003256  mov     ebx, 8007000Eh
0x18000325b  mov     rcx, [rsp+28h+pidl2]; pidl
0x180003260  call    cs:__imp_ILFree
0x180003266  mov     rsi, [rsp+28h+arg_10]
0x18000326b  mov     eax, ebx
0x18000326d  mov     rbx, [rsp+28h+arg_8]
0x180003272  add     rsp, 20h
0x180003276  pop     rdi
0x180003277  retn
```
