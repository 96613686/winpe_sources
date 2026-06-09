# CbsOfflineUtil::CbsShutdownImageStack(void)

- ea: `0x180194190`
- end: `0x18019426f`
- name: `?CbsShutdownImageStack@CbsOfflineUtil@@UEAAXXZ`
- size: `223`
- prototype: `void __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180194190`
- `0x180194278`
- `0x180194310`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18019421a`
- `ntdll!RtlFreeHeap` at `0x180194253`
- `ntdll!RtlFreeHeap` at `0x18019421a`
- `ntdll!RtlFreeHeap` at `0x180194253`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801941e6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801941e6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801941f6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801941f6`

## string_xrefs

- `0x1801941c2`: `\ssshim.dll`

## pseudocode

```c
void __fastcall CbsOfflineUtil::CbsShutdownImageStack(CbsOfflineUtil *this)
{
  void *v2; // r8
  int v3; // eax
  int v4; // eax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v6[4]; // [rsp+28h] [rbp-20h] BYREF

  lpFileName = 0;
  Windows::AutoSsShim::Close((CbsOfflineUtil *)((char *)this + 24));
  if ( *((_QWORD *)this + 2) )
  {
    v6[0] = *((_QWORD *)this + 2);
    v6[1] = L"\\ssshim.dll";
    if ( !(unsigned int)ConcatManyStrings(2, v6, &lpFileName) )
    {
      DeleteFileW(lpFileName);
      RemoveDirectoryW(*((LPCWSTR *)this + 2));
    }
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      LOBYTE(v3) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
      if ( !v3 )
        __fastfail(7u);
      *((_QWORD *)this + 2) = 0;
    }
    if ( lpFileName )
    {
      LOBYTE(v4) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)lpFileName);
      if ( !v4 )
        __fastfail(7u);
    }
  }
}

```

## disassembly

```asm
0x180194190  push    rdi
0x180194192  sub     rsp, 40h
0x180194196  mov     rdi, rcx
0x180194199  mov     [rsp+48h+lpFileName], 0
0x1801941a2  add     rcx, 18h; this
0x1801941a6  call    ?Close@AutoSsShim@Windows@@QEAAXXZ; Windows::AutoSsShim::Close(void)
0x1801941ab  mov     rax, [rdi+10h]
0x1801941af  test    rax, rax
0x1801941b2  jz      loc_180194268
0x1801941b8  mov     [rsp+48h+var_20], rax
0x1801941bd  lea     r8, [rsp+48h+lpFileName]
0x1801941c2  lea     rax, aSsshimDll_0; "\\ssshim.dll"
0x1801941c9  mov     ecx, 2
0x1801941ce  lea     rdx, [rsp+48h+var_20]
0x1801941d3  mov     [rsp+48h+var_18], rax
0x1801941d8  call    ConcatManyStrings
0x1801941dd  test    eax, eax
0x1801941df  jnz     short loc_180194202
0x1801941e1  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x1801941e6  call    cs:__imp_DeleteFileW
0x1801941ed  nop     dword ptr [rax+rax+00h]
0x1801941f2  mov     rcx, [rdi+10h]; lpPathName
0x1801941f6  call    cs:__imp_RemoveDirectoryW
0x1801941fd  nop     dword ptr [rax+rax+00h]
0x180194202  mov     r8, [rdi+10h]; P
0x180194206  test    r8, r8
0x180194209  jz      short loc_180194237
0x18019420b  mov     rcx, gs:60h
0x180194214  xor     edx, edx; Flags
0x180194216  mov     rcx, [rcx+30h]; HeapHandle
0x18019421a  call    cs:__imp_RtlFreeHeap
0x180194221  nop     dword ptr [rax+rax+00h]
0x180194226  test    eax, eax
0x180194228  jnz     short loc_18019422F
0x18019422a  lea     ecx, [rax+7]
0x18019422d  int     29h; Win8: RtlFailFast(ecx)
0x18019422f  mov     qword ptr [rdi+10h], 0
0x180194237  cmp     [rsp+48h+lpFileName], 0
0x18019423d  jz      short loc_180194268
0x18019423f  mov     rcx, gs:60h
0x180194248  xor     edx, edx; Flags
0x18019424a  mov     r8, [rsp+48h+lpFileName]; P
0x18019424f  mov     rcx, [rcx+30h]; HeapHandle
0x180194253  call    cs:__imp_RtlFreeHeap
0x18019425a  nop     dword ptr [rax+rax+00h]
0x18019425f  test    eax, eax
0x180194261  jnz     short loc_180194268
0x180194263  lea     ecx, [rax+7]
0x180194266  int     29h; Win8: RtlFailFast(ecx)
0x180194268  add     rsp, 40h
0x18019426c  pop     rdi
0x18019426d  retn
```
