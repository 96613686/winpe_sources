# CPhotoPropertyItemList::GetItemAtIndex(uint,tagPROPVARIANT *,_tagpropertykey *)

- ea: `0x180009f90`
- end: `0x180009fe7`
- name: `?GetItemAtIndex@CPhotoPropertyItemList@@QEAAJIPEAUtagPROPVARIANT@@PEAU_tagpropertykey@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(CPhotoPropertyItemList *__hidden this, unsigned int, struct tagPROPVARIANT *, struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x180009f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009fdc`

## pseudocode

```c
HRESULT __fastcall CPhotoPropertyItemList::GetItemAtIndex(
        CPhotoPropertyItemList *this,
        int a2,
        struct tagPROPVARIANT *a3,
        struct _tagpropertykey *a4)
{
  int v5; // eax
  __int64 v6; // rdx

  v5 = 0;
  v6 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return -2147467259;
  while ( *(_BYTE *)(v6 + 49) == 1 )
  {
LABEL_8:
    v6 = *(_QWORD *)(v6 + 56);
    if ( !v6 )
      return -2147467259;
  }
  if ( v5 != a2 )
  {
    ++v5;
    goto LABEL_8;
  }
  if ( a4 )
    *a4 = *(struct _tagpropertykey *)v6;
  if ( a3 )
    return PropVariantCopy(a3, (const PROPVARIANT *)(v6 + 24));
  else
    return 0;
}

```

## disassembly

```asm
0x180009f90  mov     r10d, edx
0x180009f93  xor     eax, eax
0x180009f95  mov     rdx, [rcx]
0x180009f98  test    rdx, rdx
0x180009f9b  jz      short loc_180009FCF
0x180009f9d  nop     dword ptr [rax]
0x180009fa0  cmp     byte ptr [rdx+31h], 1
0x180009fa4  jz      short loc_180009FC6
0x180009fa6  cmp     eax, r10d
0x180009fa9  jnz     short loc_180009FE3
0x180009fab  test    r9, r9
0x180009fae  jz      short loc_180009FBE
0x180009fb0  movups  xmm0, xmmword ptr [rdx]
0x180009fb3  movups  xmmword ptr [r9], xmm0
0x180009fb7  mov     eax, [rdx+10h]
0x180009fba  mov     [r9+10h], eax
0x180009fbe  test    r8, r8
0x180009fc1  jnz     short loc_180009FD5
0x180009fc3  xor     eax, eax
0x180009fc5  retn
0x180009fc6  mov     rdx, [rdx+38h]
0x180009fca  test    rdx, rdx
0x180009fcd  jnz     short loc_180009FA0
0x180009fcf  mov     eax, 80004005h
0x180009fd4  retn
0x180009fd5  add     rdx, 18h
0x180009fd9  mov     rcx, r8
0x180009fdc  jmp     cs:__imp_PropVariantCopy
0x180009fe3  inc     eax
0x180009fe5  jmp     short loc_180009FC6
```
