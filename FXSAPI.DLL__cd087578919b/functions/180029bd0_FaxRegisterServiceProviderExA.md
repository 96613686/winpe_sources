# FaxRegisterServiceProviderExA

- ea: `0x180029bd0`
- end: `0x180029e09`
- name: `FaxRegisterServiceProviderExA`
- size: `569`
- prototype: `__int64 __fastcall(void *, LPCCH lpMultiByteStr, LPCCH, LPCCH, LPCCH, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180029bd0`
- `0x180029e10`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029c49`
- `KERNEL32!GetLastError` at `0x180029cb5`
- `KERNEL32!GetLastError` at `0x180029d0a`
- `KERNEL32!GetLastError` at `0x180029d66`
- `KERNEL32!GetLastError` at `0x180029c49`
- `KERNEL32!GetLastError` at `0x180029cb5`
- `KERNEL32!GetLastError` at `0x180029d0a`
- `KERNEL32!GetLastError` at `0x180029d66`

## pseudocode

```c
__int64 __fastcall FaxRegisterServiceProviderExA(
        _DWORD *a1,
        LPCCH lpMultiByteStr,
        LPCCH a3,
        LPCCH a4,
        LPCCH lpMultiByteStra,
        int a6,
        int a7)
{
  WCHAR *v7; // rbp
  WCHAR *v8; // r12
  WCHAR *v9; // r15
  WCHAR *v10; // r14
  DWORD LastError; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int v19; // [rsp+98h] [rbp+10h]

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  if ( !lpMultiByteStr || (v8 = AnsiStringToUnicodeString(lpMultiByteStr)) != 0 )
  {
    if ( !a3 || (v9 = AnsiStringToUnicodeString(a3)) != 0 )
    {
      if ( !a4 || (v7 = AnsiStringToUnicodeString(a4)) != 0 )
      {
        if ( !lpMultiByteStra || (v10 = AnsiStringToUnicodeString(lpMultiByteStra)) != 0 )
        {
          v19 = FaxRegisterServiceProviderExW(a1, v8, (__int64)v9, (__int64)v7, v10, a6, a7);
          goto LABEL_31;
        }
        LastError = GetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 55;
          goto LABEL_11;
        }
      }
      else
      {
        LastError = GetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 54;
          goto LABEL_11;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 53;
        goto LABEL_11;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 52;
LABEL_11:
      WPP_SF_d(v16[2], v17, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, LastError);
    }
  }
LABEL_31:
  pMemFree(v8);
  pMemFree(v9);
  pMemFree(v7);
  pMemFree(v10);
  return v19;
}

```

## disassembly

```asm
0x180029bd0  push    rbx
0x180029bd2  push    rbp
0x180029bd3  push    rsi
0x180029bd4  push    rdi
0x180029bd5  push    r12
0x180029bd7  push    r13
0x180029bd9  push    r14
0x180029bdb  push    r15
0x180029bdd  sub     rsp, 48h
0x180029be1  xor     ebp, ebp
0x180029be3  xor     r12d, r12d
0x180029be6  xor     r15d, r15d
0x180029be9  mov     [rsp+88h+arg_8], ebp
0x180029bf0  xor     r14d, r14d
0x180029bf3  mov     rsi, r9
0x180029bf6  mov     rdi, r8
0x180029bf9  mov     rbx, rdx
0x180029bfc  mov     r13, rcx
0x180029bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c06  lea     rax, WPP_GLOBAL_Control
0x180029c0d  cmp     rcx, rax
0x180029c10  jz      short loc_180029C34
0x180029c12  test    dword ptr [rcx+1Ch], 1000h
0x180029c19  jz      short loc_180029C34
0x180029c1b  cmp     byte ptr [rcx+19h], 5
0x180029c1f  jb      short loc_180029C34
0x180029c21  mov     rcx, [rcx+10h]
0x180029c25  lea     edx, [rbp+33h]
0x180029c28  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180029c2f  call    WPP_SF_
0x180029c34  test    rbx, rbx
0x180029c37  jz      short loc_180029CA0
0x180029c39  mov     rcx, rbx; lpMultiByteStr
0x180029c3c  call    AnsiStringToUnicodeString
0x180029c41  mov     r12, rax
0x180029c44  test    rax, rax
0x180029c47  jnz     short loc_180029CA0
0x180029c49  call    cs:__imp_GetLastError
0x180029c50  nop     dword ptr [rax+rax+00h]
0x180029c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c5c  lea     rdx, WPP_GLOBAL_Control
0x180029c63  cmp     rcx, rdx
0x180029c66  jz      loc_180029DD0
0x180029c6c  test    dword ptr [rcx+1Ch], 1000h
0x180029c73  jz      loc_180029DD0
0x180029c79  cmp     byte ptr [rcx+19h], 2
0x180029c7d  jb      loc_180029DD0
0x180029c83  lea     edx, [r12+34h]
0x180029c88  mov     rcx, [rcx+10h]
0x180029c8c  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180029c93  mov     r9d, eax
0x180029c96  call    WPP_SF_d
0x180029c9b  jmp     loc_180029DD0
0x180029ca0  test    rdi, rdi
0x180029ca3  jz      short loc_180029CF5
0x180029ca5  mov     rcx, rdi; lpMultiByteStr
0x180029ca8  call    AnsiStringToUnicodeString
0x180029cad  mov     r15, rax
0x180029cb0  test    rax, rax
0x180029cb3  jnz     short loc_180029CF5
0x180029cb5  call    cs:__imp_GetLastError
0x180029cbc  nop     dword ptr [rax+rax+00h]
0x180029cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cc8  lea     rdx, WPP_GLOBAL_Control
0x180029ccf  cmp     rcx, rdx
0x180029cd2  jz      loc_180029DD0
0x180029cd8  test    dword ptr [rcx+1Ch], 1000h
0x180029cdf  jz      loc_180029DD0
0x180029ce5  cmp     byte ptr [rcx+19h], 2
0x180029ce9  jb      loc_180029DD0
0x180029cef  lea     edx, [r15+35h]
0x180029cf3  jmp     short loc_180029C88
0x180029cf5  test    rsi, rsi
0x180029cf8  jz      short loc_180029D4C
0x180029cfa  mov     rcx, rsi; lpMultiByteStr
0x180029cfd  call    AnsiStringToUnicodeString
0x180029d02  mov     rbp, rax
0x180029d05  test    rax, rax
0x180029d08  jnz     short loc_180029D4C
0x180029d0a  call    cs:__imp_GetLastError
0x180029d11  nop     dword ptr [rax+rax+00h]
0x180029d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d1d  lea     rdx, WPP_GLOBAL_Control
0x180029d24  cmp     rcx, rdx
0x180029d27  jz      loc_180029DD0
0x180029d2d  test    dword ptr [rcx+1Ch], 1000h
0x180029d34  jz      loc_180029DD0
0x180029d3a  cmp     byte ptr [rcx+19h], 2
0x180029d3e  jb      loc_180029DD0
0x180029d44  lea     edx, [rbp+36h]
0x180029d47  jmp     loc_180029C88
0x180029d4c  mov     rcx, [rsp+88h+lpMultiByteStr]; lpMultiByteStr
0x180029d54  test    rcx, rcx
0x180029d57  jz      short loc_180029D9D
0x180029d59  call    AnsiStringToUnicodeString
0x180029d5e  mov     r14, rax
0x180029d61  test    rax, rax
0x180029d64  jnz     short loc_180029D9D
0x180029d66  call    cs:__imp_GetLastError
0x180029d6d  nop     dword ptr [rax+rax+00h]
0x180029d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d79  lea     rdx, WPP_GLOBAL_Control
0x180029d80  cmp     rcx, rdx
0x180029d83  jz      short loc_180029DD0
0x180029d85  test    dword ptr [rcx+1Ch], 1000h
0x180029d8c  jz      short loc_180029DD0
0x180029d8e  cmp     byte ptr [rcx+19h], 2
0x180029d92  jb      short loc_180029DD0
0x180029d94  lea     edx, [r14+37h]
0x180029d98  jmp     loc_180029C88
0x180029d9d  mov     eax, [rsp+88h+arg_30]
0x180029da4  mov     r9, rbp
0x180029da7  mov     [rsp+88h+var_58], eax; int
0x180029dab  mov     r8, r15
0x180029dae  mov     eax, [rsp+88h+arg_28]
0x180029db5  mov     rdx, r12; lpsz
0x180029db8  mov     [rsp+88h+var_60], eax; int
0x180029dbc  mov     rcx, r13; void *
0x180029dbf  mov     [rsp+88h+var_68], r14; __int64
0x180029dc4  call    FaxRegisterServiceProviderExW
0x180029dc9  mov     [rsp+88h+arg_8], eax
0x180029dd0  mov     rcx, r12; lpMem
0x180029dd3  call    pMemFree
0x180029dd8  mov     rcx, r15; lpMem
0x180029ddb  call    pMemFree
0x180029de0  mov     rcx, rbp; lpMem
0x180029de3  call    pMemFree
0x180029de8  mov     rcx, r14; lpMem
0x180029deb  call    pMemFree
0x180029df0  mov     eax, [rsp+88h+arg_8]
0x180029df7  add     rsp, 48h
0x180029dfb  pop     r15
0x180029dfd  pop     r14
0x180029dff  pop     r13
0x180029e01  pop     r12
0x180029e03  pop     rdi
0x180029e04  pop     rsi
0x180029e05  pop     rbp
0x180029e06  pop     rbx
0x180029e07  retn
```
