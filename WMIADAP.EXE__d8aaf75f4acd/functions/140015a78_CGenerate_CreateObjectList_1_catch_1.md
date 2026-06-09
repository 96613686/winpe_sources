# _CGenerate::CreateObjectList_::_1_::catch$1

- ea: `0x140015a78`
- end: `0x140015abe`
- name: `_CGenerate::CreateObjectList_::_1_::catch$1`
- size: `70`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140015a78`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140015a8e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140015a9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140015a8e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140015a9d`

## pseudocode

```c
__int64 __fastcall CGenerate::CreateObjectList_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx

  v3 = *(void **)(a2 + 64);
  if ( v3 )
    CWin32DefaultArena::WbemMemFree(v3);
  v4 = *(void **)(a2 + 56);
  if ( v4 )
    CWin32DefaultArena::WbemMemFree(v4);
  *(_DWORD *)(a2 + 200) = -2147418113;
  return 0;
}

```

## disassembly

```asm
0x140015a78  mov     [rsp+arg_8], rdx
0x140015a7d  push    rbp
0x140015a7e  sub     rsp, 30h
0x140015a82  mov     rbp, rdx
0x140015a85  mov     rcx, [rbp+40h]
0x140015a89  test    rcx, rcx
0x140015a8c  jz      short loc_140015A94
0x140015a8e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140015a94  mov     rcx, [rbp+38h]
0x140015a98  test    rcx, rcx
0x140015a9b  jz      short loc_140015AA3
0x140015a9d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140015aa3  mov     dword ptr [rbp+0C8h], 8000FFFFh
0x140015aad  mov     rax, 0
0x140015ab7  add     rsp, 30h
0x140015abb  pop     rbp
0x140015abc  retn
```
