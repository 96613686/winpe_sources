# GetTopViewAwareItemFromParentIDList(_ITEMIDLIST_ABSOLUTE const *,ITopViewAwareItem * *)

- ea: `0x1800879c4`
- end: `0x180087a7a`
- name: `?GetTopViewAwareItemFromParentIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUITopViewAwareItem@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, struct ITopViewAwareItem **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800867c0`

## callees

- `0x1800879c4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x180087a5b`
- `Windows.Storage!ILFree` at `0x180087a5b`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180087a13`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180087a13`
- `Windows.Storage!ILClone` at `0x1800879dd`
- `Windows.Storage!ILClone` at `0x1800879dd`
- `Windows.Storage!ILRemoveLastID` at `0x1800879ee`
- `Windows.Storage!ILRemoveLastID` at `0x1800879ee`

## pseudocode

```c
__int64 __fastcall GetTopViewAwareItemFromParentIDList(const ITEMIDLIST *a1, struct ITopViewAwareItem **a2)
{
  ITEMIDLIST *v3; // rax
  ITEMIDLIST *v4; // rdi
  HRESULT v5; // ebx
  void *ppv; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = ILClone(a1);
  v4 = v3;
  if ( v3 )
  {
    ILRemoveLastID(v3);
    *a2 = 0;
    ppv = 0;
    v5 = SHCreateItemFromIDList(v4, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, struct ITopViewAwareItem **))(*(_QWORD *)ppv + 24LL))(
             ppv,
             0,
             &BHID_SFViewObject,
             &GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb,
             a2);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ILFree(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800879c4  mov     [rsp+arg_0], rbx
0x1800879c9  mov     [rsp+arg_10], rsi
0x1800879ce  push    rdi
0x1800879cf  sub     rsp, 30h
0x1800879d3  mov     rsi, rdx
0x1800879d6  mov     qword ptr [rdx], 0
0x1800879dd  call    cs:__imp_ILClone
0x1800879e3  mov     rdi, rax
0x1800879e6  test    rax, rax
0x1800879e9  jz      short loc_180087A63
0x1800879eb  mov     rcx, rax; pidl
0x1800879ee  call    cs:__imp_ILRemoveLastID
0x1800879f4  lea     r8, [rsp+38h+ppv]; ppv
0x1800879f9  mov     qword ptr [rsi], 0
0x180087a00  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180087a07  mov     [rsp+38h+ppv], 0
0x180087a10  mov     rcx, rdi; pidl
0x180087a13  call    cs:__imp_SHCreateItemFromIDList
0x180087a19  mov     ebx, eax
0x180087a1b  test    eax, eax
0x180087a1d  js      short loc_180087A58
0x180087a1f  mov     rcx, [rsp+38h+ppv]
0x180087a24  lea     r9, _GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb
0x180087a2b  lea     r8, BHID_SFViewObject
0x180087a32  mov     [rsp+38h+var_18], rsi
0x180087a37  xor     edx, edx
0x180087a39  mov     rax, [rcx]
0x180087a3c  mov     rax, [rax+18h]
0x180087a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a45  mov     rcx, [rsp+38h+ppv]
0x180087a4a  mov     ebx, eax
0x180087a4c  mov     rax, [rcx]
0x180087a4f  mov     rax, [rax+10h]
0x180087a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a58  mov     rcx, rdi; pidl
0x180087a5b  call    cs:__imp_ILFree
0x180087a61  jmp     short loc_180087A68
0x180087a63  mov     ebx, 8007000Eh
0x180087a68  mov     rsi, [rsp+38h+arg_10]
0x180087a6d  mov     eax, ebx
0x180087a6f  mov     rbx, [rsp+38h+arg_0]
0x180087a74  add     rsp, 30h
0x180087a78  pop     rdi
0x180087a79  retn
```
