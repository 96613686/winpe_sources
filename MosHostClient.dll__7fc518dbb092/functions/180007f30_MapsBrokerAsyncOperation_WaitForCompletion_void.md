# MapsBrokerAsyncOperation::WaitForCompletion(void)

- ea: `0x180007f30`
- end: `0x180007f87`
- name: `?WaitForCompletion@MapsBrokerAsyncOperation@@UEAAJXZ`
- size: `87`
- prototype: `DWORD __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007948`

## callees

- `0x1800047f0`
- `0x180006214`
- `0x180007f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007f3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007f3e`

## string_xrefs

- `0x180007f56`: `onecoreuap\windows\maps\moshost\client\mapsbrokerasyncoperation.cpp`

## pseudocode

```c
DWORD __fastcall MapsBrokerAsyncOperation::WaitForCompletion(HANDLE *this)
{
  DWORD result; // eax
  int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = WaitForSingleObjectEx(this[11], 0xFFFFFFFF, 0);
  if ( result == 258 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsbrokerasyncoperation.cpp",
      (const char *)0x8000FFFFLL);
    return -2147418113;
  }
  else if ( result )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007f30  sub     rsp, 28h
0x180007f34  mov     rcx, [rcx+58h]; hHandle
0x180007f38  xor     r8d, r8d; bAlertable
0x180007f3b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007f3e  call    cs:__imp_WaitForSingleObjectEx
0x180007f44  cmp     eax, 102h
0x180007f49  jz      short loc_180007F51
0x180007f4b  test    eax, eax
0x180007f4d  jnz     short loc_180007F77
0x180007f4f  jmp     short loc_180007F72
0x180007f51  mov     rcx, [rsp+28h]; this
0x180007f56  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180007f5d  mov     r9d, 8000FFFFh; char *
0x180007f63  mov     edx, 32h ; '2'; void *
0x180007f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f6d  mov     eax, 8000FFFFh
0x180007f72  add     rsp, 28h
0x180007f76  retn
0x180007f77  mov     rcx, [rsp+28h]; this
0x180007f7c  mov     edx, 0B0Fh; void *
0x180007f81  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
