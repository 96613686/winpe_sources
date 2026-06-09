# FdiWrite

- ea: `0x18000c690`
- end: `0x18000c700`
- name: `FdiWrite`
- size: `112`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004dec`
- `0x18000c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c6d3`
- `KERNEL32!GetLastError` at `0x18000c6d3`
- `KERNEL32!WriteFile` at `0x18000c6aa`
- `KERNEL32!WriteFile` at `0x18000c6aa`

## pseudocode

```c
__int64 __fastcall FdiWrite(INT_PTR hf, void *pv, UINT cb)
{
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( WriteFile((HANDLE)hf, pv, cb, &NumberOfBytesWritten, 0) )
    return NumberOfBytesWritten;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids, LastError);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000c690  sub     rsp, 38h
0x18000c694  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c699  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18000c6a1  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000c6aa  call    cs:__imp_WriteFile
0x18000c6b0  test    eax, eax
0x18000c6b2  jz      short loc_18000C6BA
0x18000c6b4  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18000c6b8  jmp     short loc_18000C6FB
0x18000c6ba  mov     rax, cs:WPP_GLOBAL_Control
0x18000c6c1  lea     rcx, WPP_GLOBAL_Control
0x18000c6c8  cmp     rax, rcx
0x18000c6cb  jz      short loc_18000C6F8
0x18000c6cd  test    byte ptr [rax+1Ch], 1
0x18000c6d1  jz      short loc_18000C6F8
0x18000c6d3  call    cs:__imp_GetLastError
0x18000c6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6e0  lea     r8, WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids
0x18000c6e7  mov     edx, 0Fh
0x18000c6ec  mov     r9d, eax
0x18000c6ef  mov     rcx, [rcx+10h]
0x18000c6f3  call    WPP_SF_d
0x18000c6f8  or      eax, 0FFFFFFFFh
0x18000c6fb  add     rsp, 38h
0x18000c6ff  retn
```
