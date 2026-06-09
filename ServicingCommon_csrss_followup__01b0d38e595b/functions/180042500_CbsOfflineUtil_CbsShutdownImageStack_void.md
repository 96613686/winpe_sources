# CbsOfflineUtil::CbsShutdownImageStack(void)

- ea: `0x180042500`
- end: `0x180042594`
- name: `?CbsShutdownImageStack@CbsOfflineUtil@@UEAAXXZ`
- size: `148`
- prototype: `void __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800438c0`

## callees

- `0x18001aac4`
- `0x18001bae0`
- `0x180042500`
- `0x18004259c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180042562`
- `KERNEL32!GetProcessHeap` at `0x180042562`
- `KERNEL32!HeapFree` at `0x180042578`
- `KERNEL32!HeapFree` at `0x180042578`
- `KERNEL32!DeleteFileW` at `0x18004253e`
- `KERNEL32!DeleteFileW` at `0x18004253e`
- `KERNEL32!RemoveDirectoryW` at `0x18004254e`
- `KERNEL32!RemoveDirectoryW` at `0x18004254e`

## string_xrefs

- `0x180042529`: `\ssshim.dll`

## pseudocode

```c
void __fastcall CbsOfflineUtil::CbsShutdownImageStack(CbsOfflineUtil *this)
{
  __int64 v2; // rcx
  HANDLE ProcessHeap; // rax
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF

  lpFileName = 0;
  Windows::AutoSsShim::Close((CbsOfflineUtil *)((char *)this + 24));
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( !(unsigned int)ConcatTwoStrings(v2, L"\\ssshim.dll", &lpFileName) )
    {
      DeleteFileW(lpFileName);
      RemoveDirectoryW(*((LPCWSTR *)this + 2));
    }
    if ( lpFileName )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)lpFileName);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((char *)this + 16);
  }
}

```

## disassembly

```asm
0x180042500  push    rbx
0x180042502  sub     rsp, 20h
0x180042506  mov     rbx, rcx
0x180042509  mov     [rsp+28h+lpFileName], 0
0x180042512  add     rcx, 18h; this
0x180042516  call    ?Close@AutoSsShim@Windows@@QEAAXXZ; Windows::AutoSsShim::Close(void)
0x18004251b  mov     rcx, [rbx+10h]
0x18004251f  test    rcx, rcx
0x180042522  jz      short loc_18004258D
0x180042524  lea     r8, [rsp+28h+lpFileName]
0x180042529  lea     rdx, aSsshimDll_0; "\\ssshim.dll"
0x180042530  call    ConcatTwoStrings
0x180042535  test    eax, eax
0x180042537  jnz     short loc_18004255A
0x180042539  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18004253e  call    cs:__imp_DeleteFileW
0x180042545  nop     dword ptr [rax+rax+00h]
0x18004254a  mov     rcx, [rbx+10h]; lpPathName
0x18004254e  call    cs:__imp_RemoveDirectoryW
0x180042555  nop     dword ptr [rax+rax+00h]
0x18004255a  cmp     [rsp+28h+lpFileName], 0
0x180042560  jz      short loc_180042584
0x180042562  call    cs:__imp_GetProcessHeap
0x180042569  nop     dword ptr [rax+rax+00h]
0x18004256e  mov     r8, [rsp+28h+lpFileName]; lpMem
0x180042573  xor     edx, edx; dwFlags
0x180042575  mov     rcx, rax; hHeap
0x180042578  call    cs:__imp_HeapFree
0x18004257f  nop     dword ptr [rax+rax+00h]
0x180042584  lea     rcx, [rbx+10h]
0x180042588  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18004258d  add     rsp, 20h
0x180042591  pop     rbx
0x180042592  retn
```
