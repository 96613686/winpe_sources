# CCachedFolderItem::UpdateProperties(SYNCMGR_PROPERTYDATA const *)

- ea: `0x18004e500`
- end: `0x18004e59a`
- name: `?UpdateProperties@CCachedFolderItem@@UEAAJPEBUSYNCMGR_PROPERTYDATA@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(CCachedFolderItem *this, HICON *Src)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18004e500`
- `0x18004e9f8`
- `0x180052906`
- `0x180052912`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e579`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e51a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e51a`
- `USER32!CopyIcon` at `0x18004e568`
- `USER32!CopyIcon` at `0x18004e568`
- `USER32!DestroyIcon` at `0x18004e544`
- `USER32!DestroyIcon` at `0x18004e544`

## pseudocode

```c
__int64 __fastcall CCachedFolderItem::UpdateProperties(CCachedFolderItem *this, HICON *Src)
{
  unsigned int v4; // ebx
  HICON v5; // rcx
  HICON v6; // rcx

  v4 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( memcmp_0((char *)this + 64, Src, 0x550u) )
  {
    v5 = (HICON)*((_QWORD *)this + 110);
    v4 = 0;
    if ( v5 )
      DestroyIcon(v5);
    memcpy_0((char *)this + 64, Src, 0x550u);
    v6 = Src[102];
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
0x18004e500  push    rbx
0x18004e502  push    rbp
0x18004e503  push    rsi
0x18004e504  push    rdi
0x18004e505  push    r14
0x18004e507  sub     rsp, 20h
0x18004e50b  mov     rdi, rcx
0x18004e50e  mov     rsi, rdx
0x18004e511  add     rcx, 18h; lpCriticalSection
0x18004e515  mov     ebx, 1
0x18004e51a  call    cs:__imp_EnterCriticalSection
0x18004e520  mov     r8d, 550h; Size
0x18004e526  lea     rcx, [rdi+40h]; Buf1
0x18004e52a  mov     rdx, rsi; Buf2
0x18004e52d  call    memcmp_0
0x18004e532  test    eax, eax
0x18004e534  jz      short loc_18004E575
0x18004e536  mov     rcx, [rdi+370h]; hIcon
0x18004e53d  xor     ebx, ebx
0x18004e53f  test    rcx, rcx
0x18004e542  jz      short loc_18004E54A
0x18004e544  call    cs:__imp_DestroyIcon
0x18004e54a  lea     rcx, [rdi+40h]; void *
0x18004e54e  mov     rdx, rsi; Src
0x18004e551  mov     r8d, 550h; Size
0x18004e557  call    memcpy_0
0x18004e55c  mov     rcx, [rsi+330h]; hIcon
0x18004e563  test    rcx, rcx
0x18004e566  jz      short loc_18004E575
0x18004e568  call    cs:__imp_CopyIcon
0x18004e56e  mov     [rdi+370h], rax
0x18004e575  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004e579  call    cs:__imp_LeaveCriticalSection
0x18004e57f  test    ebx, ebx
0x18004e581  jnz     short loc_18004E58D
0x18004e583  mov     rcx, rdi; this
0x18004e586  call    ?_UpdateProgressValues@CCachedFolderItem@@AEAAJXZ; CCachedFolderItem::_UpdateProgressValues(void)
0x18004e58b  mov     ebx, eax
0x18004e58d  mov     eax, ebx
0x18004e58f  add     rsp, 20h
0x18004e593  pop     r14
0x18004e595  pop     rdi
0x18004e596  pop     rsi
0x18004e597  pop     rbp
0x18004e598  pop     rbx
0x18004e599  retn
```
