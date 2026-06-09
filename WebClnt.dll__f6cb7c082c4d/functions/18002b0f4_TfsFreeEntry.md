# TfsFreeEntry

- ea: `0x18002b0f4`
- end: `0x18002b1d8`
- name: `TfsFreeEntry`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD *hMem, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002bfa4`

## callees

- `0x18000b81c`
- `0x18002b0f4`
- `0x18002ccfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b14b`
- `KERNEL32!LocalFree` at `0x18002b1b0`
- `KERNEL32!LocalFree` at `0x18002b1b9`
- `KERNEL32!LocalFree` at `0x18002b1b0`
- `KERNEL32!LocalFree` at `0x18002b1b9`
- `KERNEL32!DeleteFileW` at `0x18002b141`
- `KERNEL32!DeleteFileW` at `0x18002b141`

## pseudocode

```c
__int64 __fastcall TfsFreeEntry(_QWORD *hMem, int a2, int a3)
{
  DWORD v4; // edi
  DWORD LastError; // eax
  _QWORD *v6; // rax
  HLOCAL *v7; // rcx
  void *v8; // rcx

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qSl(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (_DWORD)hMem, hMem[6], *((_DWORD *)hMem + 5));
  if ( DeleteFileW((LPCWSTR)hMem[6]) )
    goto LABEL_9;
  LastError = GetLastError();
  v4 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
      LastError,
      hMem[6]);
  if ( (v4 & 0xFFFFFFFD) == 0 )
  {
LABEL_9:
    v6 = (_QWORD *)*hMem;
    if ( *(_QWORD **)(*hMem + 8LL) != hMem || (v7 = (HLOCAL *)hMem[1], *v7 != hMem) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = v7;
    v8 = (void *)hMem[8];
    if ( v8 )
      LocalFree(v8);
    LocalFree(hMem);
  }
  return v4;
}

```

## disassembly

```asm
0x18002b0f4  mov     [rsp+arg_0], rbx
0x18002b0f9  mov     [rsp+arg_8], rsi
0x18002b0fe  push    rdi
0x18002b0ff  sub     rsp, 30h
0x18002b103  mov     rbx, rcx
0x18002b106  xor     edi, edi
0x18002b108  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b10f  lea     rsi, WPP_GLOBAL_Control
0x18002b116  cmp     rcx, rsi
0x18002b119  jz      short loc_18002B13D
0x18002b11b  test    byte ptr [rcx+1Ch], 2
0x18002b11f  jz      short loc_18002B13D
0x18002b121  mov     eax, [rbx+14h]
0x18002b124  mov     r9, rbx
0x18002b127  mov     rcx, [rcx+10h]
0x18002b12b  mov     [rsp+38h+var_10], eax
0x18002b12f  mov     rax, [rbx+30h]
0x18002b133  mov     [rsp+38h+var_18], rax
0x18002b138  call    WPP_SF_qSl
0x18002b13d  mov     rcx, [rbx+30h]; lpFileName
0x18002b141  call    cs:__imp_DeleteFileW
0x18002b147  test    eax, eax
0x18002b149  jnz     short loc_18002B18E
0x18002b14b  call    cs:__imp_GetLastError
0x18002b151  mov     edi, eax
0x18002b153  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b15a  cmp     rcx, rsi
0x18002b15d  jz      short loc_18002B186
0x18002b15f  test    byte ptr [rcx+1Ch], 1
0x18002b163  jz      short loc_18002B186
0x18002b165  mov     r8, [rbx+30h]
0x18002b169  mov     edx, 15h
0x18002b16e  mov     rcx, [rcx+10h]
0x18002b172  mov     r9d, eax
0x18002b175  mov     [rsp+38h+var_18], r8
0x18002b17a  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002b181  call    WPP_SF_dS
0x18002b186  test    edi, 0FFFFFFFDh
0x18002b18c  jnz     short loc_18002B1BF
0x18002b18e  mov     rax, [rbx]
0x18002b191  cmp     [rax+8], rbx
0x18002b195  jnz     short loc_18002B1D1
0x18002b197  mov     rcx, [rbx+8]
0x18002b19b  cmp     [rcx], rbx
0x18002b19e  jnz     short loc_18002B1D1
0x18002b1a0  mov     [rcx], rax
0x18002b1a3  mov     [rax+8], rcx
0x18002b1a7  mov     rcx, [rbx+40h]; hMem
0x18002b1ab  test    rcx, rcx
0x18002b1ae  jz      short loc_18002B1B6
0x18002b1b0  call    cs:__imp_LocalFree
0x18002b1b6  mov     rcx, rbx; hMem
0x18002b1b9  call    cs:__imp_LocalFree
0x18002b1bf  mov     rbx, [rsp+38h+arg_0]
0x18002b1c4  mov     eax, edi
0x18002b1c6  mov     rsi, [rsp+38h+arg_8]
0x18002b1cb  add     rsp, 30h
0x18002b1cf  pop     rdi
0x18002b1d0  retn
0x18002b1d1  mov     ecx, 3
0x18002b1d6  int     29h; Win8: RtlFailFast(ecx)
```
