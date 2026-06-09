# CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)

- ea: `0x18001a5d8`
- end: `0x18001a651`
- name: `?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(CPhotoPropertyItemList *__hidden this, const struct _tagpropertykey *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a988`
- `0x18001aa2c`
- `0x18001b014`
- `0x18001b1fc`

## callees

- `0x18001a5d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a643`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a643`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a63a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a63a`

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
0x18001a5d8  push    rbx
0x18001a5da  sub     rsp, 20h
0x18001a5de  mov     rbx, [rcx]
0x18001a5e1  test    rbx, rbx
0x18001a5e4  jz      short loc_18001A649
0x18001a5e6  mov     r9d, [rdx+10h]
0x18001a5ea  xor     r8d, r8d
0x18001a5ed  cmp     [rbx+10h], r9d
0x18001a5f1  jnz     short loc_18001A605
0x18001a5f3  mov     rax, [rbx]
0x18001a5f6  cmp     rax, [rdx]
0x18001a5f9  jnz     short loc_18001A605
0x18001a5fb  mov     rax, [rbx+8]
0x18001a5ff  cmp     rax, [rdx+8]
0x18001a603  jz      short loc_18001A611
0x18001a605  mov     r8, rbx
0x18001a608  mov     rbx, [rbx+38h]
0x18001a60c  test    rbx, rbx
0x18001a60f  jnz     short loc_18001A5ED
0x18001a611  test    rbx, rbx
0x18001a614  jz      short loc_18001A649
0x18001a616  mov     rax, [rbx+38h]
0x18001a61a  test    r8, r8
0x18001a61d  jnz     short loc_18001A624
0x18001a61f  mov     [rcx], rax
0x18001a622  jmp     short loc_18001A628
0x18001a624  mov     [r8+38h], rax
0x18001a628  cmp     byte ptr [rbx+30h], 0
0x18001a62c  jz      short loc_18001A631
0x18001a62e  dec     dword ptr [rcx+10h]
0x18001a631  lea     rcx, [rbx+18h]; pvar
0x18001a635  test    rcx, rcx
0x18001a638  jz      short loc_18001A640
0x18001a63a  call    cs:__imp_PropVariantClear
0x18001a640  mov     rcx, rbx; hMem
0x18001a643  call    cs:__imp_LocalFree
0x18001a649  xor     eax, eax
0x18001a64b  add     rsp, 20h
0x18001a64f  pop     rbx
0x18001a650  retn
```
