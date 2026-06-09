# __std_fs_create_directory

- ea: `0x1800046cc`
- end: `0x18000475b`
- name: `__std_fs_create_directory`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800392c8`

## callees

- `0x1800046cc`
- `0x180004834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800046e3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800046e3`

## pseudocode

```c
__int64 __fastcall _std_fs_create_directory(LPCWSTR lpFileName)
{
  DWORD LastError; // eax
  __int64 v4; // [rsp+58h] [rbp+18h]

  if ( CreateDirectoryW(lpFileName, 0) )
  {
    LastError = 0;
    LOBYTE(v4) = 1;
    *(_WORD *)((char *)&v4 + 1) = 0;
    BYTE3(v4) = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 183 )
    {
      LastError = _std_fs_get_stats(lpFileName);
      if ( !LastError )
        LastError = 183;
    }
    LOBYTE(v4) = 0;
    *(_WORD *)((char *)&v4 + 1) = 0;
    BYTE3(v4) = 0;
  }
  HIDWORD(v4) = LastError;
  return v4;
}

```

## disassembly

```asm
0x1800046cc  mov     [rsp-8+arg_0], rbx
0x1800046d1  mov     [rsp-8+arg_10], rdi
0x1800046d6  push    rbp
0x1800046d7  mov     rbp, rsp
0x1800046da  sub     rsp, 40h
0x1800046de  xor     edx, edx; lpSecurityAttributes
0x1800046e0  mov     rbx, rcx
0x1800046e3  call    cs:__imp_CreateDirectoryW
0x1800046e9  test    eax, eax
0x1800046eb  jz      short loc_1800046FC
0x1800046ed  xor     eax, eax
0x1800046ef  mov     byte ptr [rbp+arg_8], 1
0x1800046f3  mov     word ptr [rbp+arg_8+1], ax
0x1800046f7  mov     byte ptr [rbp+arg_8+3], al
0x1800046fa  jmp     short loc_180004744
0x1800046fc  call    cs:__imp_GetLastError
0x180004702  mov     edi, 0B7h
0x180004707  cmp     eax, edi
0x180004709  jnz     short loc_180004737
0x18000470b  xorps   xmm0, xmm0
0x18000470e  lea     rdx, [rbp+var_20]
0x180004712  or      r9d, 0FFFFFFFFh
0x180004716  mov     r8d, 3
0x18000471c  mov     rcx, rbx; lpFileName
0x18000471f  movups  [rbp+var_20], xmm0
0x180004723  movups  [rbp+var_10], xmm0
0x180004727  call    __std_fs_get_stats
0x18000472c  test    eax, eax
0x18000472e  jnz     short loc_180004737
0x180004730  test    byte ptr [rbp+var_10], 10h
0x180004734  cmovz   eax, edi
0x180004737  xor     ecx, ecx
0x180004739  mov     byte ptr [rbp+arg_8], 0
0x18000473d  mov     word ptr [rbp+arg_8+1], cx
0x180004741  mov     byte ptr [rbp+arg_8+3], cl
0x180004744  mov     rbx, [rsp+40h+arg_0]
0x180004749  mov     rdi, [rsp+40h+arg_10]
0x18000474e  mov     dword ptr [rbp+arg_8+4], eax
0x180004751  mov     rax, [rbp+arg_8]
0x180004755  add     rsp, 40h
0x180004759  pop     rbp
0x18000475a  retn
```
