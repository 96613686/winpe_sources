# Utils::DeleteReadOnlyFile(ushort *)

- ea: `0x18004d230`
- end: `0x18004d2f6`
- name: `?DeleteReadOnlyFile@Utils@@SAKPEAG@Z`
- size: `198`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180026158`
- `0x180028e30`

## callees

- `0x18004d230`
- `0x18004f994`
- `0x18004fb04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004d254`
- `KERNEL32!GetLastError` at `0x18004d2ae`
- `KERNEL32!GetLastError` at `0x18004d254`
- `KERNEL32!GetLastError` at `0x18004d2ae`
- `KERNEL32!GetFileAttributesW` at `0x18004d242`
- `KERNEL32!GetFileAttributesW` at `0x18004d242`
- `KERNEL32!SetFileAttributesW` at `0x18004d297`
- `KERNEL32!SetFileAttributesW` at `0x18004d297`
- `KERNEL32!DeleteFileW` at `0x18004d2a0`
- `KERNEL32!DeleteFileW` at `0x18004d2a0`

## pseudocode

```c
__int64 __fastcall Utils::DeleteReadOnlyFile(unsigned __int16 *a1)
{
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  DWORD v5; // edi

  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1);
  }
  else if ( (FileAttributesW & 1) != 0 )
  {
    SetFileAttributesW(a1, FileAttributesW & 0xFFFFFFFE);
  }
  if ( DeleteFileW(a1) )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      271,
      (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
      (_DWORD)a1,
      LastError);
  return v5;
}

```

## disassembly

```asm
0x18004d230  mov     [rsp+arg_0], rbx
0x18004d235  mov     [rsp+arg_8], rsi
0x18004d23a  push    rdi
0x18004d23b  sub     rsp, 30h
0x18004d23f  mov     rbx, rcx
0x18004d242  call    cs:__imp_GetFileAttributesW
0x18004d248  lea     rsi, WPP_GLOBAL_Control
0x18004d24f  cmp     eax, 0FFFFFFFFh
0x18004d252  jnz     short loc_18004D28B
0x18004d254  call    cs:__imp_GetLastError
0x18004d25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d261  cmp     rcx, rsi
0x18004d264  jz      short loc_18004D29D
0x18004d266  test    byte ptr [rcx+1Ch], 2
0x18004d26a  jz      short loc_18004D29D
0x18004d26c  mov     rcx, [rcx+10h]; LoggerHandle
0x18004d270  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d277  mov     edx, 10Eh
0x18004d27c  mov     [rsp+38h+var_18], rbx; __int64
0x18004d281  mov     r9d, eax
0x18004d284  call    WPP_SF_DS
0x18004d289  jmp     short loc_18004D29D
0x18004d28b  test    al, 1
0x18004d28d  jz      short loc_18004D29D
0x18004d28f  and     eax, 0FFFFFFFEh
0x18004d292  mov     rcx, rbx; lpFileName
0x18004d295  mov     edx, eax; dwFileAttributes
0x18004d297  call    cs:__imp_SetFileAttributesW
0x18004d29d  mov     rcx, rbx; lpFileName
0x18004d2a0  call    cs:__imp_DeleteFileW
0x18004d2a6  test    eax, eax
0x18004d2a8  jz      short loc_18004D2AE
0x18004d2aa  xor     eax, eax
0x18004d2ac  jmp     short loc_18004D2E6
0x18004d2ae  call    cs:__imp_GetLastError
0x18004d2b4  mov     edi, eax
0x18004d2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d2bd  cmp     rcx, rsi
0x18004d2c0  jz      short loc_18004D2E4
0x18004d2c2  test    byte ptr [rcx+1Ch], 2
0x18004d2c6  jz      short loc_18004D2E4
0x18004d2c8  mov     rcx, [rcx+10h]
0x18004d2cc  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d2d3  mov     edx, 10Fh
0x18004d2d8  mov     dword ptr [rsp+38h+var_18], eax
0x18004d2dc  mov     r9, rbx
0x18004d2df  call    WPP_SF_Sd
0x18004d2e4  mov     eax, edi
0x18004d2e6  mov     rbx, [rsp+38h+arg_0]
0x18004d2eb  mov     rsi, [rsp+38h+arg_8]
0x18004d2f0  add     rsp, 30h
0x18004d2f4  pop     rdi
0x18004d2f5  retn
```
