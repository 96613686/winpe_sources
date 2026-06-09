# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18006faf0`
- end: `0x18006fb9f`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006fbb0`

## callees

- `0x18006cf6c`
- `0x18006faf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fb87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fb87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fb06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fb06`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fb6e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fb6e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetItem(
        __int64 a1,
        __int64 a2,
        const PROPVARIANT *a3)
{
  PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( *(_WORD *)a3 == 5
    || *(_WORD *)a3 == 13
    || *(_WORD *)a3 == 19
    || *(_WORD *)a3 == 21
    || *(_WORD *)a3 == 31
    || *(_WORD *)a3 == 72
    || *(_WORD *)a3 == 4113
    || *(_WORD *)a3 == 4127 )
  {
    if ( Item )
    {
      v7 = PropVariantCopy(Item, a3);
      *(_DWORD *)(a1 + 64) = 1;
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -1072875843;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18006faf0  push    rbx
0x18006faf2  push    rbp
0x18006faf3  push    rsi
0x18006faf4  push    rdi
0x18006faf5  sub     rsp, 28h
0x18006faf9  mov     rdi, rcx
0x18006fafc  mov     rbp, r8
0x18006faff  add     rcx, 8; lpCriticalSection
0x18006fb03  mov     rbx, rdx
0x18006fb06  call    cs:__imp_EnterCriticalSection
0x18006fb0d  nop     dword ptr [rax+rax+00h]
0x18006fb12  mov     rdx, rbx
0x18006fb15  mov     rcx, rdi
0x18006fb18  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18006fb1d  movzx   r9d, word ptr [rbp+0]
0x18006fb22  sub     r9d, 5
0x18006fb26  jz      short loc_18006FB5C
0x18006fb28  sub     r9d, 8
0x18006fb2c  jz      short loc_18006FB5C
0x18006fb2e  sub     r9d, 6
0x18006fb32  jz      short loc_18006FB5C
0x18006fb34  sub     r9d, 2
0x18006fb38  jz      short loc_18006FB5C
0x18006fb3a  sub     r9d, 0Ah
0x18006fb3e  jz      short loc_18006FB5C
0x18006fb40  sub     r9d, 29h ; ')'
0x18006fb44  jz      short loc_18006FB5C
0x18006fb46  sub     r9d, 0FC9h
0x18006fb4d  jz      short loc_18006FB5C
0x18006fb4f  cmp     r9d, 0Eh
0x18006fb53  jz      short loc_18006FB5C
0x18006fb55  mov     ebx, 0C00D36BDh
0x18006fb5a  jmp     short loc_18006FB83
0x18006fb5c  test    rax, rax
0x18006fb5f  jnz     short loc_18006FB68
0x18006fb61  mov     ebx, 8007000Eh
0x18006fb66  jmp     short loc_18006FB83
0x18006fb68  mov     rdx, rbp; pvarSrc
0x18006fb6b  mov     rcx, rax; pvarDest
0x18006fb6e  call    cs:__imp_PropVariantCopy
0x18006fb75  nop     dword ptr [rax+rax+00h]
0x18006fb7a  mov     ebx, eax
0x18006fb7c  mov     dword ptr [rdi+40h], 1
0x18006fb83  lea     rcx, [rdi+8]; lpCriticalSection
0x18006fb87  call    cs:__imp_LeaveCriticalSection
0x18006fb8e  nop     dword ptr [rax+rax+00h]
0x18006fb93  mov     eax, ebx
0x18006fb95  add     rsp, 28h
0x18006fb99  pop     rdi
0x18006fb9a  pop     rsi
0x18006fb9b  pop     rbp
0x18006fb9c  pop     rbx
0x18006fb9d  retn
```
