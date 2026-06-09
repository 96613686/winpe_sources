# ABO_WRAPPER::FTreeValid(void)

- ea: `0x18000d544`
- end: `0x18000d5cf`
- name: `?FTreeValid@ABO_WRAPPER@@QEAAHXZ`
- size: `139`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dde0`
- `0x18002a070`

## callees

- `0x180001f90`
- `0x18000d544`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d5b2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d5b2`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::FTreeValid(ABO_WRAPPER *this)
{
  unsigned int v1; // ebx
  __int64 v3; // rcx
  int v4; // eax
  FILETIME FileTime2; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v3 = *((_QWORD *)this + 15);
  FileTime1 = 0;
  FileTime2 = 0;
  if ( v3 && *((_QWORD *)this + 3) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v3 + 176LL))(v3, &FileTime1);
    if ( v4 >= 0 )
    {
      FileTime2 = *(FILETIME *)(*((_QWORD *)this + 3) + 68LL);
      return CompareFileTime(&FileTime1, &FileTime2) == 0;
    }
    else
    {
      ABO_MAPPER_LOG::WriteLogEntry(
        (HANDLE *)g_pAboLog,
        L" GetFileChangeTime failed with Error = %X, Invaliding Tree",
        (unsigned int)v4);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000d544  mov     r11, rsp
0x18000d547  mov     [r11+18h], rbx
0x18000d54b  push    rdi
0x18000d54c  sub     rsp, 20h
0x18000d550  xor     ebx, ebx
0x18000d552  mov     rdi, rcx
0x18000d555  mov     rcx, [rcx+78h]
0x18000d559  mov     [r11+10h], rbx
0x18000d55d  mov     [r11+8], rbx
0x18000d561  test    rcx, rcx
0x18000d564  jz      short loc_18000D5C2
0x18000d566  cmp     [rdi+18h], rbx
0x18000d56a  jz      short loc_18000D5C2
0x18000d56c  mov     rax, [rcx]
0x18000d56f  lea     rdx, [r11+10h]
0x18000d573  mov     rax, [rax+0B0h]
0x18000d57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57f  test    eax, eax
0x18000d581  jns     short loc_18000D59B
0x18000d583  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000d58a  lea     rdx, aGetfilechanget; " GetFileChangeTime failed with Error = "...
0x18000d591  mov     r8d, eax
0x18000d594  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000d599  jmp     short loc_18000D5C2
0x18000d59b  mov     rcx, [rdi+18h]
0x18000d59f  mov     rdx, [rcx+44h]
0x18000d5a3  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18000d5a8  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], rdx
0x18000d5ad  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18000d5b2  call    cs:__imp_CompareFileTime
0x18000d5b8  test    eax, eax
0x18000d5ba  mov     ecx, 1
0x18000d5bf  cmovz   ebx, ecx
0x18000d5c2  mov     eax, ebx
0x18000d5c4  mov     rbx, [rsp+28h+arg_10]
0x18000d5c9  add     rsp, 20h
0x18000d5cd  pop     rdi
0x18000d5ce  retn
```
