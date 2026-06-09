# CCachedFolderItem::UpdateFolderItemInfo(SYNCMGR_FOLDERITEMINFO const *)

- ea: `0x18004e420`
- end: `0x18004e4c1`
- name: `?UpdateFolderItemInfo@CCachedFolderItem@@UEAAJPEBUSYNCMGR_FOLDERITEMINFO@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CCachedFolderItem *__hidden this, const struct SYNCMGR_FOLDERITEMINFO *Src)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18004e420`
- `0x18004e9f8`
- `0x180052906`
- `0x180052912`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e4a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e4a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e43a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e43a`
- `USER32!CopyIcon` at `0x18004e48f`
- `USER32!CopyIcon` at `0x18004e48f`
- `USER32!DestroyIcon` at `0x18004e464`
- `USER32!DestroyIcon` at `0x18004e464`

## pseudocode

```c
__int64 __fastcall CCachedFolderItem::UpdateFolderItemInfo(
        CCachedFolderItem *this,
        const struct SYNCMGR_FOLDERITEMINFO *Src)
{
  unsigned int v4; // edi
  HICON v5; // rcx
  HICON v6; // rcx

  v4 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( memcmp_0((char *)this + 64, Src, 0x550u) )
  {
    v5 = (HICON)*((_QWORD *)this + 110);
    v4 = 0;
    if ( v5 )
    {
      DestroyIcon(v5);
      *((_QWORD *)this + 110) = 0;
    }
    memcpy_0((char *)this + 64, Src, 0x550u);
    v6 = (HICON)*((_QWORD *)this + 110);
    if ( v6 )
      *((_QWORD *)this + 110) = CopyIcon(v6);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !v4 )
    return (unsigned int)CCachedFolderItem::_UpdateProgressValues(this);
  return v4;
}

```

## disassembly

```asm
0x18004e420  push    rbx
0x18004e422  push    rbp
0x18004e423  push    rsi
0x18004e424  push    rdi
0x18004e425  push    r14
0x18004e427  sub     rsp, 20h
0x18004e42b  mov     rbx, rcx
0x18004e42e  mov     rbp, rdx
0x18004e431  add     rcx, 18h; lpCriticalSection
0x18004e435  mov     edi, 1
0x18004e43a  call    cs:__imp_EnterCriticalSection
0x18004e440  mov     r8d, 550h; Size
0x18004e446  lea     rcx, [rbx+40h]; Buf1
0x18004e44a  mov     rdx, rbp; Buf2
0x18004e44d  call    memcmp_0
0x18004e452  test    eax, eax
0x18004e454  jz      short loc_18004E49C
0x18004e456  mov     rcx, [rbx+370h]; hIcon
0x18004e45d  xor     edi, edi
0x18004e45f  test    rcx, rcx
0x18004e462  jz      short loc_18004E471
0x18004e464  call    cs:__imp_DestroyIcon
0x18004e46a  mov     [rbx+370h], rdi
0x18004e471  lea     rcx, [rbx+40h]; void *
0x18004e475  mov     rdx, rbp; Src
0x18004e478  mov     r8d, 550h; Size
0x18004e47e  call    memcpy_0
0x18004e483  mov     rcx, [rbx+370h]; hIcon
0x18004e48a  test    rcx, rcx
0x18004e48d  jz      short loc_18004E49C
0x18004e48f  call    cs:__imp_CopyIcon
0x18004e495  mov     [rbx+370h], rax
0x18004e49c  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004e4a0  call    cs:__imp_LeaveCriticalSection
0x18004e4a6  test    edi, edi
0x18004e4a8  jnz     short loc_18004E4B4
0x18004e4aa  mov     rcx, rbx; this
0x18004e4ad  call    ?_UpdateProgressValues@CCachedFolderItem@@AEAAJXZ; CCachedFolderItem::_UpdateProgressValues(void)
0x18004e4b2  mov     edi, eax
0x18004e4b4  mov     eax, edi
0x18004e4b6  add     rsp, 20h
0x18004e4ba  pop     r14
0x18004e4bc  pop     rdi
0x18004e4bd  pop     rsi
0x18004e4be  pop     rbp
0x18004e4bf  pop     rbx
0x18004e4c0  retn
```
