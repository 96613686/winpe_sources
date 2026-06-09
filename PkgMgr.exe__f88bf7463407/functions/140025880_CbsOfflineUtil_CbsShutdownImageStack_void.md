# CbsOfflineUtil::CbsShutdownImageStack(void)

- ea: `0x140025880`
- end: `0x1400258e7`
- name: `?CbsShutdownImageStack@CbsOfflineUtil@@UEAAXXZ`
- size: `103`
- prototype: `void __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x140025880`
- `0x1400258f0`
- `0x140025964`
- `0x140025b08`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400258c8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400258c8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400258be`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400258be`

## string_xrefs

- `0x1400258a9`: `\ssshim.dll`

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
0x140025880  push    rbx
0x140025882  sub     rsp, 30h
0x140025886  mov     rbx, rcx
0x140025889  mov     [rsp+38h+lpFileName], 0
0x140025892  add     rcx, 18h; this
0x140025896  call    ?Close@AutoSsShim@Windows@@QEAAXXZ; Windows::AutoSsShim::Close(void)
0x14002589b  mov     rcx, [rbx+10h]
0x14002589f  test    rcx, rcx
0x1400258a2  jz      short loc_1400258D7
0x1400258a4  lea     r8, [rsp+38h+lpFileName]
0x1400258a9  lea     rdx, aSsshimDll_0; "\\ssshim.dll"
0x1400258b0  call    ConcatTwoStrings
0x1400258b5  test    eax, eax
0x1400258b7  jnz     short loc_1400258CE
0x1400258b9  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x1400258be  call    cs:__imp_DeleteFileW
0x1400258c4  mov     rcx, [rbx+10h]; lpPathName
0x1400258c8  call    cs:__imp_RemoveDirectoryW
0x1400258ce  lea     rcx, [rbx+10h]
0x1400258d2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x1400258d7  lea     rcx, [rsp+38h+lpFileName]
0x1400258dc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x1400258e1  add     rsp, 30h
0x1400258e5  pop     rbx
0x1400258e6  retn
```
