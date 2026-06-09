# CbsOfflineUtil::CbsShutdownImageStack(void)

- ea: `0x18003f730`
- end: `0x18003f7a4`
- name: `?CbsShutdownImageStack@CbsOfflineUtil@@UEAAXXZ`
- size: `116`
- prototype: `void __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800403d0`

## callees

- `0x1800104e4`
- `0x180011ae0`
- `0x18003f730`
- `0x18003f7ac`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18003f76e`
- `KERNEL32!DeleteFileW` at `0x18003f76e`
- `KERNEL32!RemoveDirectoryW` at `0x18003f77e`
- `KERNEL32!RemoveDirectoryW` at `0x18003f77e`

## string_xrefs

- `0x18003f759`: `\ssshim.dll`

## pseudocode

```c
void __fastcall CbsOfflineUtil::CbsShutdownImageStack(CbsOfflineUtil *this)
{
  __int64 v2; // rcx
  LPCWSTR lpFileName[3]; // [rsp+20h] [rbp-18h] BYREF

  lpFileName[0] = 0;
  Windows::AutoSsShim::Close((CbsOfflineUtil *)((char *)this + 24));
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( !(unsigned int)ConcatTwoStrings(v2, L"\\ssshim.dll", lpFileName) )
    {
      DeleteFileW(lpFileName[0]);
      RemoveDirectoryW(*((LPCWSTR *)this + 2));
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((char *)this + 16);
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(lpFileName);
}

```

## disassembly

```asm
0x18003f730  push    rbx
0x18003f732  sub     rsp, 30h
0x18003f736  mov     rbx, rcx
0x18003f739  mov     [rsp+38h+lpFileName], 0
0x18003f742  add     rcx, 18h; this
0x18003f746  call    ?Close@AutoSsShim@Windows@@QEAAXXZ; Windows::AutoSsShim::Close(void)
0x18003f74b  mov     rcx, [rbx+10h]
0x18003f74f  test    rcx, rcx
0x18003f752  jz      short loc_18003F793
0x18003f754  lea     r8, [rsp+38h+lpFileName]
0x18003f759  lea     rdx, aSsshimDll_0; "\\ssshim.dll"
0x18003f760  call    ConcatTwoStrings
0x18003f765  test    eax, eax
0x18003f767  jnz     short loc_18003F78A
0x18003f769  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x18003f76e  call    cs:__imp_DeleteFileW
0x18003f775  nop     dword ptr [rax+rax+00h]
0x18003f77a  mov     rcx, [rbx+10h]; lpPathName
0x18003f77e  call    cs:__imp_RemoveDirectoryW
0x18003f785  nop     dword ptr [rax+rax+00h]
0x18003f78a  lea     rcx, [rbx+10h]
0x18003f78e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003f793  lea     rcx, [rsp+38h+lpFileName]
0x18003f798  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003f79d  add     rsp, 30h
0x18003f7a1  pop     rbx
0x18003f7a2  retn
```
