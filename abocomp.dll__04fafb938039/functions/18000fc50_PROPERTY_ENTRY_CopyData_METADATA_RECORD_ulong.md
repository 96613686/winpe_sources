# PROPERTY_ENTRY::CopyData(_METADATA_RECORD *,ulong *)

- ea: `0x18000fc50`
- end: `0x18000fd3f`
- name: `?CopyData@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@PEAK@Z`
- size: `239`
- prototype: `__int64 __fastcall(PROPERTY_ENTRY *__hidden this, struct _METADATA_RECORD *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f28`
- `0x18000fe3c`
- `0x18000ff30`

## callees

- `0x180003402`
- `0x18000fc50`
- `0x18001013c`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc84`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc9f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fccb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcd7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd00`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd0f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd1e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc84`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc9f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fccb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcd7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fcf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd00`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd0f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd1e`

## pseudocode

```c
__int64 __fastcall PROPERTY_ENTRY::CopyData(PROPERTY_ENTRY *this, struct _METADATA_RECORD *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  BUFFER *v7; // rdi
  unsigned int *Ptr; // rbx
  const void **v9; // rax

  if ( a2 )
  {
    PROPERTY_ENTRY::ReadProperty(this);
    v7 = (PROPERTY_ENTRY *)((char *)this + 16);
    if ( !a2->dwMDDataType || a2->dwMDDataType == *((_DWORD *)BUFFER::QueryPtr(v7) + 3) )
    {
      if ( a2->dwMDDataLen >= *((_DWORD *)BUFFER::QueryPtr(v7) + 4) )
      {
        Ptr = (unsigned int *)BUFFER::QueryPtr(v7);
        v9 = (const void **)BUFFER::QueryPtr(v7);
        memcpy_0(a2->pbMDData, v9[3], Ptr[4]);
        a2->dwMDDataLen = *((_DWORD *)BUFFER::QueryPtr(v7) + 4);
        a2->dwMDAttributes = *((_DWORD *)BUFFER::QueryPtr(v7) + 1);
        a2->dwMDDataType = *((_DWORD *)BUFFER::QueryPtr(v7) + 3);
        v6 = 0;
        a2->dwMDUserType = *((_DWORD *)BUFFER::QueryPtr(v7) + 2);
        a2->dwMDDataTag = 0;
      }
      else
      {
        v6 = -2147024774;
        if ( a3 )
          *a3 = *((_DWORD *)BUFFER::QueryPtr(v7) + 4);
      }
    }
    else
    {
      return (unsigned int)-2146646015;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fc50  push    rbx
0x18000fc52  push    rsi
0x18000fc53  push    rdi
0x18000fc54  push    r14
0x18000fc56  sub     rsp, 28h
0x18000fc5a  mov     r14, r8
0x18000fc5d  mov     rsi, rdx
0x18000fc60  mov     rdi, rcx
0x18000fc63  test    rdx, rdx
0x18000fc66  jnz     short loc_18000FC72
0x18000fc68  mov     ebx, 80070057h
0x18000fc6d  jmp     loc_18000FD33
0x18000fc72  call    ?ReadProperty@PROPERTY_ENTRY@@QEAAJXZ; PROPERTY_ENTRY::ReadProperty(void)
0x18000fc77  add     rdi, 10h
0x18000fc7b  cmp     dword ptr [rsi+0Ch], 0
0x18000fc7f  jz      short loc_18000FC9C
0x18000fc81  mov     rcx, rdi
0x18000fc84  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fc8a  mov     ecx, [rax+0Ch]
0x18000fc8d  cmp     [rsi+0Ch], ecx
0x18000fc90  jz      short loc_18000FC9C
0x18000fc92  mov     ebx, 800CC801h
0x18000fc97  jmp     loc_18000FD33
0x18000fc9c  mov     rcx, rdi
0x18000fc9f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fca5  mov     eax, [rax+10h]
0x18000fca8  cmp     [rsi+10h], eax
0x18000fcab  jnb     short loc_18000FCC8
0x18000fcad  mov     ebx, 8007007Ah
0x18000fcb2  test    r14, r14
0x18000fcb5  jz      short loc_18000FD33
0x18000fcb7  mov     rcx, rdi
0x18000fcba  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fcc0  mov     ecx, [rax+10h]
0x18000fcc3  mov     [r14], ecx
0x18000fcc6  jmp     short loc_18000FD33
0x18000fcc8  mov     rcx, rdi
0x18000fccb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fcd1  mov     rcx, rdi
0x18000fcd4  mov     rbx, rax
0x18000fcd7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fcdd  mov     r8d, [rbx+10h]; Size
0x18000fce1  mov     rcx, [rsi+18h]; void *
0x18000fce5  mov     rdx, [rax+18h]; Src
0x18000fce9  call    memcpy_0
0x18000fcee  mov     rcx, rdi
0x18000fcf1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fcf7  mov     ecx, [rax+10h]
0x18000fcfa  mov     [rsi+10h], ecx
0x18000fcfd  mov     rcx, rdi
0x18000fd00  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fd06  mov     ecx, [rax+4]
0x18000fd09  mov     [rsi+4], ecx
0x18000fd0c  mov     rcx, rdi
0x18000fd0f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fd15  mov     ecx, [rax+0Ch]
0x18000fd18  mov     [rsi+0Ch], ecx
0x18000fd1b  mov     rcx, rdi
0x18000fd1e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fd24  xor     ebx, ebx
0x18000fd26  mov     ecx, [rax+8]
0x18000fd29  mov     [rsi+8], ecx
0x18000fd2c  mov     dword ptr [rsi+20h], 0
0x18000fd33  mov     eax, ebx
0x18000fd35  add     rsp, 28h
0x18000fd39  pop     r14
0x18000fd3b  pop     rdi
0x18000fd3c  pop     rsi
0x18000fd3d  pop     rbx
0x18000fd3e  retn
```
