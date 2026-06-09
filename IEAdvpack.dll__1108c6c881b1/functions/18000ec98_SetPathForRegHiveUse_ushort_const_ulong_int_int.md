# SetPathForRegHiveUse(ushort const *,ulong *,int,int)

- ea: `0x18000ec98`
- end: `0x18000ed43`
- name: `?SetPathForRegHiveUse@@YAXPEBGPEAKHH@Z`
- size: `171`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int *, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e060`

## callees

- `0x1800022bc`
- `0x18000521c`
- `0x18000ec98`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000ecec`
- `KERNEL32!GetFileAttributesW` at `0x18000ecec`
- `KERNEL32!SetFileAttributesW` at `0x18000ed04`
- `KERNEL32!SetFileAttributesW` at `0x18000ed04`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000ed0f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000ed0f`

## pseudocode

```c
void __fastcall SetPathForRegHiveUse(const unsigned __int16 *a1, unsigned int *a2, __int64 a3, int a4)
{
  __int64 v6; // rbx
  DWORD v7; // edx
  WCHAR FileName[264]; // [rsp+20h] [rbp-238h] BYREF

  StringCchCopyW(FileName, 0x104u, a1);
  if ( a4 )
    CreateFullPath(FileName, 0);
  v6 = 0;
  do
  {
    if ( a4 )
    {
      a2[v6] = GetFileAttributesW(FileName);
      v7 = 128;
    }
    else
    {
      v7 = a2[v6];
    }
    SetFileAttributesW(FileName, v7);
    if ( !PathRemoveFileSpecW(FileName) )
      break;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (int)v6 < 8 );
}

```

## disassembly

```asm
0x18000ec98  mov     [rsp+arg_10], rbx
0x18000ec9d  push    rbp
0x18000ec9e  push    rsi
0x18000ec9f  push    rdi
0x18000eca0  sub     rsp, 240h
0x18000eca7  mov     rax, cs:__security_cookie
0x18000ecae  xor     rax, rsp
0x18000ecb1  mov     [rsp+258h+var_28], rax
0x18000ecb9  mov     rsi, rdx
0x18000ecbc  mov     r8, rcx; unsigned __int16 *
0x18000ecbf  mov     edx, 104h; unsigned __int64
0x18000ecc4  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x18000ecc9  mov     ebp, r9d
0x18000eccc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ecd1  test    ebp, ebp
0x18000ecd3  jz      short loc_18000ECE1
0x18000ecd5  xor     edx, edx; int
0x18000ecd7  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x18000ecdc  call    ?CreateFullPath@@YAJPEBGH@Z; CreateFullPath(ushort const *,int)
0x18000ece1  xor     ebx, ebx
0x18000ece3  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18000ece8  test    ebp, ebp
0x18000ecea  jz      short loc_18000ED01
0x18000ecec  call    cs:__imp_GetFileAttributesW
0x18000ecf2  mov     [rsi+rbx*4], eax
0x18000ecf5  mov     edx, 80h
0x18000ecfa  lea     rcx, [rsp+258h+FileName]
0x18000ecff  jmp     short loc_18000ED04
0x18000ed01  mov     edx, [rsi+rbx*4]; dwFileAttributes
0x18000ed04  call    cs:__imp_SetFileAttributesW
0x18000ed0a  lea     rcx, [rsp+258h+FileName]; pszPath
0x18000ed0f  call    cs:__imp_PathRemoveFileSpecW
0x18000ed15  test    eax, eax
0x18000ed17  jz      short loc_18000ED20
0x18000ed19  inc     ebx
0x18000ed1b  cmp     ebx, 8
0x18000ed1e  jl      short loc_18000ECE3
0x18000ed20  mov     rcx, [rsp+258h+var_28]
0x18000ed28  xor     rcx, rsp; StackCookie
0x18000ed2b  call    __security_check_cookie
0x18000ed30  mov     rbx, [rsp+258h+arg_10]
0x18000ed38  add     rsp, 240h
0x18000ed3f  pop     rdi
0x18000ed40  pop     rsi
0x18000ed41  pop     rbp
0x18000ed42  retn
```
