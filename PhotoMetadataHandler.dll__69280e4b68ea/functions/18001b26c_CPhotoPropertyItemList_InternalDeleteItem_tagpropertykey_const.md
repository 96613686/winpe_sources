# CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)

- ea: `0x18001b26c`
- end: `0x18001b2f2`
- name: `?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CPhotoPropertyItemList *__hidden this, const struct _tagpropertykey *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b634`
- `0x18001b6d8`
- `0x18001bcc8`
- `0x18001beb8`

## callees

- `0x18001b26c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b2ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b2ce`

## pseudocode

```c
__int64 __fastcall CPhotoPropertyItemList::_InternalDeleteItem(PROPVARIANT **this, const struct _tagpropertykey *a2)
{
  PROPVARIANT *pvarVal; // rbx
  PROPVARIANT *v3; // r8
  LARGE_INTEGER hVal; // rax

  pvarVal = *this;
  if ( *this )
  {
    v3 = 0;
    do
    {
      if ( *((_DWORD *)&pvarVal->decVal + 4) == a2->pid
        && *(_QWORD *)&pvarVal->vt == *(_QWORD *)&a2->fmtid.Data1
        && pvarVal->hVal.QuadPart == *(_QWORD *)a2->fmtid.Data4 )
      {
        break;
      }
      v3 = pvarVal;
      pvarVal = pvarVal[2].pvarVal;
    }
    while ( pvarVal );
    if ( pvarVal )
    {
      hVal = pvarVal[2].hVal;
      if ( v3 )
        v3[2].hVal = hVal;
      else
        *this = (PROPVARIANT *)hVal.QuadPart;
      if ( LOBYTE(pvarVal[2].vt) )
        --*((_DWORD *)this + 4);
      if ( pvarVal != (PROPVARIANT *)-24LL )
        PropVariantClear(pvarVal + 1);
      LocalFree(pvarVal);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b26c  push    rbx
0x18001b26e  sub     rsp, 20h
0x18001b272  mov     rbx, [rcx]
0x18001b275  test    rbx, rbx
0x18001b278  jz      short loc_18001B2E9
0x18001b27a  mov     r9d, [rdx+10h]
0x18001b27e  xor     r8d, r8d
0x18001b281  cmp     [rbx+10h], r9d
0x18001b285  jnz     short loc_18001B299
0x18001b287  mov     rax, [rbx]
0x18001b28a  cmp     rax, [rdx]
0x18001b28d  jnz     short loc_18001B299
0x18001b28f  mov     rax, [rbx+8]
0x18001b293  cmp     rax, [rdx+8]
0x18001b297  jz      short loc_18001B2A5
0x18001b299  mov     r8, rbx
0x18001b29c  mov     rbx, [rbx+38h]
0x18001b2a0  test    rbx, rbx
0x18001b2a3  jnz     short loc_18001B281
0x18001b2a5  test    rbx, rbx
0x18001b2a8  jz      short loc_18001B2E9
0x18001b2aa  mov     rax, [rbx+38h]
0x18001b2ae  test    r8, r8
0x18001b2b1  jnz     short loc_18001B2B8
0x18001b2b3  mov     [rcx], rax
0x18001b2b6  jmp     short loc_18001B2BC
0x18001b2b8  mov     [r8+38h], rax
0x18001b2bc  cmp     byte ptr [rbx+30h], 0
0x18001b2c0  jz      short loc_18001B2C5
0x18001b2c2  dec     dword ptr [rcx+10h]
0x18001b2c5  lea     rcx, [rbx+18h]; pvar
0x18001b2c9  test    rcx, rcx
0x18001b2cc  jz      short loc_18001B2DA
0x18001b2ce  call    cs:__imp_PropVariantClear
0x18001b2d5  nop     dword ptr [rax+rax+00h]
0x18001b2da  mov     rcx, rbx; hMem
0x18001b2dd  call    cs:__imp_LocalFree
0x18001b2e4  nop     dword ptr [rax+rax+00h]
0x18001b2e9  xor     eax, eax
0x18001b2eb  add     rsp, 20h
0x18001b2ef  pop     rbx
0x18001b2f0  retn
```
