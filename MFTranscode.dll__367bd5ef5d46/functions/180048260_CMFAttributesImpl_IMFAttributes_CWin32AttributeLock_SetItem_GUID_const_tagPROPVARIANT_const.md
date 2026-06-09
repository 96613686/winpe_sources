# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x180048260`
- end: `0x1800482fc`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007130`
- `0x180048260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800482eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800482eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048276`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048276`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800482d8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800482d8`

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
  if ( a3->vt == 5
    || a3->vt == 13
    || a3->vt == 19
    || a3->vt == 21
    || a3->vt == 31
    || a3->vt == 72
    || a3->vt == 4113
    || a3->vt == 4127 )
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
0x180048260  push    rbx
0x180048262  push    rbp
0x180048263  push    rsi
0x180048264  push    rdi
0x180048265  sub     rsp, 28h
0x180048269  mov     rdi, rcx
0x18004826c  mov     rbp, r8
0x18004826f  add     rcx, 8; lpCriticalSection
0x180048273  mov     rbx, rdx
0x180048276  call    cs:__imp_EnterCriticalSection
0x18004827c  mov     rdx, rbx
0x18004827f  mov     rcx, rdi
0x180048282  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x180048287  movzx   r9d, word ptr [rbp+0]
0x18004828c  sub     r9d, 5
0x180048290  jz      short loc_1800482C6
0x180048292  sub     r9d, 8
0x180048296  jz      short loc_1800482C6
0x180048298  sub     r9d, 6
0x18004829c  jz      short loc_1800482C6
0x18004829e  sub     r9d, 2
0x1800482a2  jz      short loc_1800482C6
0x1800482a4  sub     r9d, 0Ah
0x1800482a8  jz      short loc_1800482C6
0x1800482aa  sub     r9d, 29h ; ')'
0x1800482ae  jz      short loc_1800482C6
0x1800482b0  sub     r9d, 0FC9h
0x1800482b7  jz      short loc_1800482C6
0x1800482b9  cmp     r9d, 0Eh
0x1800482bd  jz      short loc_1800482C6
0x1800482bf  mov     ebx, 0C00D36BDh
0x1800482c4  jmp     short loc_1800482E7
0x1800482c6  test    rax, rax
0x1800482c9  jnz     short loc_1800482D2
0x1800482cb  mov     ebx, 8007000Eh
0x1800482d0  jmp     short loc_1800482E7
0x1800482d2  mov     rdx, rbp; pvarSrc
0x1800482d5  mov     rcx, rax; pvarDest
0x1800482d8  call    cs:__imp_PropVariantCopy
0x1800482de  mov     ebx, eax
0x1800482e0  mov     dword ptr [rdi+40h], 1
0x1800482e7  lea     rcx, [rdi+8]; lpCriticalSection
0x1800482eb  call    cs:__imp_LeaveCriticalSection
0x1800482f1  mov     eax, ebx
0x1800482f3  add     rsp, 28h
0x1800482f7  pop     rdi
0x1800482f8  pop     rsi
0x1800482f9  pop     rbp
0x1800482fa  pop     rbx
0x1800482fb  retn
```
