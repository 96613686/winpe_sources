# Csl::DeletePath(Csl::Path const &)

- ea: `0x18000bc6c`
- end: `0x18000bd21`
- name: `?DeletePath@Csl@@YAJAEBVPath@1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(LPCWSTR *this, const struct Path *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180028afc`
- `0x180029070`
- `0x180029928`

## callees

- `0x18000b7a0`
- `0x18000bc6c`
- `0x18000d80c`
- `0x18000e014`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bc7c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bc7c`

## string_xrefs

- `0x18000bcb4`: `Failed to delete directory %ws`
- `0x18000bd05`: `Failed to delete file %ws`

## pseudocode

```c
__int64 __fastcall Csl::DeletePath(LPCWSTR *this, const struct Path *a2)
{
  DWORD FileAttributesW; // eax
  __int64 v4; // r9
  LPCWSTR v5; // rcx
  __int64 result; // rax
  unsigned int v7; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  FileAttributesW = GetFileAttributesW(*this);
  v5 = *this;
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    result = WcpRemoveFile((__int64)v5, 0, 0, v4, 1);
    v7 = result;
    if ( (unsigned int)(result + 2147024894) <= 1 )
      return result;
    if ( (int)result < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)result,
        (int)"Failed to delete file %ws",
        (const char *)*this);
      return v7;
    }
  }
  else
  {
    result = WcRemoveFilesInDirectory((int)v5);
    v7 = result;
    if ( (unsigned int)(result + 2147024894) <= 1 )
      return result;
    if ( (int)result < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)result,
        (int)"Failed to delete directory %ws",
        (const char *)*this);
      return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bc6c  mov     [rsp+arg_8], rbx
0x18000bc71  push    rdi
0x18000bc72  sub     rsp, 30h
0x18000bc76  mov     rdi, rcx
0x18000bc79  mov     rcx, [rcx]; lpFileName
0x18000bc7c  call    cs:__imp_GetFileAttributesW
0x18000bc83  nop     dword ptr [rax+rax+00h]
0x18000bc88  mov     rcx, [rdi]; int
0x18000bc8b  cmp     eax, 0FFFFFFFFh
0x18000bc8e  jz      short loc_18000BCDD
0x18000bc90  bt      eax, 4
0x18000bc94  jnb     short loc_18000BCDD
0x18000bc96  call    WcRemoveFilesInDirectory
0x18000bc9b  mov     ebx, eax
0x18000bc9d  lea     ecx, [rax+7FF8FFFEh]
0x18000bca3  cmp     ecx, 1
0x18000bca6  jbe     short loc_18000BD15
0x18000bca8  test    eax, eax
0x18000bcaa  jns     short loc_18000BD13
0x18000bcac  mov     rdx, [rdi]
0x18000bcaf  mov     [rsp+38h+var_10], rdx; char *
0x18000bcb4  lea     rax, aFailedToDelete; "Failed to delete directory %ws"
0x18000bcbb  mov     edx, 2B4h; void *
0x18000bcc0  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000bcc7  mov     r9d, ebx; char *
0x18000bcca  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000bccf  mov     rcx, [rsp+38h]; this
0x18000bcd4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bcd9  mov     eax, ebx
0x18000bcdb  jmp     short loc_18000BD15
0x18000bcdd  mov     byte ptr [rsp+38h+var_18], 1
0x18000bce2  xor     r8d, r8d
0x18000bce5  xor     edx, edx
0x18000bce7  call    WcpRemoveFile
0x18000bcec  mov     ebx, eax
0x18000bcee  lea     ecx, [rax+7FF8FFFEh]
0x18000bcf4  cmp     ecx, 1
0x18000bcf7  jbe     short loc_18000BD15
0x18000bcf9  test    eax, eax
0x18000bcfb  jns     short loc_18000BD13
0x18000bcfd  mov     rdx, [rdi]
0x18000bd00  mov     [rsp+38h+var_10], rdx
0x18000bd05  lea     rax, aFailedToDelete_0; "Failed to delete file %ws"
0x18000bd0c  mov     edx, 2C3h
0x18000bd11  jmp     short loc_18000BCC0
0x18000bd13  xor     eax, eax
0x18000bd15  mov     rbx, [rsp+38h+arg_8]
0x18000bd1a  add     rsp, 30h
0x18000bd1e  pop     rdi
0x18000bd1f  retn
```
