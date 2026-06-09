# FreeSecurityDescriptor

- ea: `0x180003c90`
- end: `0x180003e24`
- name: `FreeSecurityDescriptor`
- size: `404`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003c90`
- `0x180004cb0`
- `0x180008ff0`
- `0x180009130`
- `0x18000b774`
- `0x18000b800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cdf`

## string_xrefs

- `0x180003d4c`: `FreeSecurityDescriptor`
- `0x180003dc0`: `FreeSecurityDescriptor`
- `0x180003de5`: `FreeSecurityDescriptor`

## pseudocode

```c
void __fastcall FreeSecurityDescriptor(LPVOID *a1)
{
  PVOID *v2; // rcx
  HANDLE ProcessHeap; // rdi
  int v4; // edx
  int v5; // r8d
  DWORD LastError; // eax
  int v7; // r8d
  DWORD v8; // eax
  int v9; // r8d

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*a1 )
    goto LABEL_12;
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap || (v8 = GetLastError()) == 0 )
  {
    if ( HeapFree(ProcessHeap, 0, *a1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, (unsigned int)"FreeSecurityDescriptor", 161, (char)*a1);
      *a1 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_12;
        WPP_SF_sdqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          v7,
          (unsigned int)"FreeSecurityDescriptor",
          161,
          (char)*a1,
          LastError);
      }
    }
    goto LABEL_11;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v9, (unsigned int)"FreeSecurityDescriptor", 161, v8);
LABEL_11:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_L(v2[2], 48, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
}

```

## disassembly

```asm
0x180003c90  mov     [rsp+arg_8], rbx
0x180003c95  push    rsi
0x180003c96  sub     rsp, 40h
0x180003c9a  mov     rbx, rcx
0x180003c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ca4  lea     rsi, WPP_GLOBAL_Control
0x180003cab  cmp     rcx, rsi
0x180003cae  jz      short loc_180003CBA
0x180003cb0  test    byte ptr [rcx+1Ch], 8
0x180003cb4  jnz     loc_180003D73
0x180003cba  cmp     qword ptr [rbx], 0
0x180003cbe  mov     [rsp+48h+arg_0], rdi
0x180003cc3  jz      short loc_180003D0D
0x180003cc5  call    cs:__imp_GetProcessHeap
0x180003ccb  mov     rdi, rax
0x180003cce  test    rax, rax
0x180003cd1  jz      loc_180003D94
0x180003cd7  mov     r8, [rbx]; lpMem
0x180003cda  xor     edx, edx; dwFlags
0x180003cdc  mov     rcx, rdi; hHeap
0x180003cdf  call    cs:__imp_HeapFree
0x180003ce5  test    eax, eax
0x180003ce7  jz      short loc_180003D2C
0x180003ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cf0  cmp     rcx, rsi
0x180003cf3  jz      short loc_180003CFF
0x180003cf5  test    byte ptr [rcx+1Ch], 2
0x180003cf9  jnz     loc_180003DE2
0x180003cff  mov     qword ptr [rbx], 0
0x180003d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d0d  cmp     rcx, rsi
0x180003d10  jz      short loc_180003D1C
0x180003d12  test    byte ptr [rcx+1Ch], 8
0x180003d16  jnz     loc_180003E07
0x180003d1c  mov     rdi, [rsp+48h+arg_0]
0x180003d21  mov     rbx, [rsp+48h+arg_8]
0x180003d26  add     rsp, 40h
0x180003d2a  pop     rsi
0x180003d2b  retn
0x180003d2c  call    cs:__imp_GetLastError
0x180003d32  test    eax, eax
0x180003d34  jz      short loc_180003D06
0x180003d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d3d  cmp     rcx, rsi
0x180003d40  jz      short loc_180003D1C
0x180003d42  test    byte ptr [rcx+1Ch], 4
0x180003d46  jz      short loc_180003D0D
0x180003d48  mov     rcx, [rcx+10h]
0x180003d4c  lea     r9, aFreesecurityde_0; "FreeSecurityDescriptor"
0x180003d53  mov     [rsp+48h+var_18], eax
0x180003d57  mov     edx, 0Fh
0x180003d5c  mov     rax, [rbx]
0x180003d5f  mov     [rsp+48h+var_20], rax
0x180003d64  mov     [rsp+48h+var_28], 1A1h
0x180003d6c  call    WPP_SF_sdqd
0x180003d71  jmp     short loc_180003D06
0x180003d73  mov     rcx, [rcx+10h]
0x180003d77  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003d7e  mov     edx, 2Fh ; '/'
0x180003d83  call    WPP_SF_
0x180003d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d8f  jmp     loc_180003CBA
0x180003d94  call    cs:__imp_GetLastError
0x180003d9a  test    eax, eax
0x180003d9c  jz      loc_180003CD7
0x180003da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da9  cmp     rcx, rsi
0x180003dac  jz      loc_180003D1C
0x180003db2  test    byte ptr [rcx+1Ch], 4
0x180003db6  jz      loc_180003D0D
0x180003dbc  mov     rcx, [rcx+10h]
0x180003dc0  lea     r9, aFreesecurityde_0; "FreeSecurityDescriptor"
0x180003dc7  mov     dword ptr [rsp+48h+var_20], eax
0x180003dcb  mov     edx, 0Dh
0x180003dd0  mov     [rsp+48h+var_28], 1A1h
0x180003dd8  call    WPP_SF_sdd
0x180003ddd  jmp     loc_180003D06
0x180003de2  mov     rax, [rbx]
0x180003de5  lea     r9, aFreesecurityde_0; "FreeSecurityDescriptor"
0x180003dec  mov     rcx, [rcx+10h]
0x180003df0  mov     [rsp+48h+var_20], rax
0x180003df5  mov     [rsp+48h+var_28], 1A1h
0x180003dfd  call    WPP_SF_sdq
0x180003e02  jmp     loc_180003CFF
0x180003e07  mov     rcx, [rcx+10h]
0x180003e0b  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003e12  mov     edx, 30h ; '0'
0x180003e17  xor     r9d, r9d
0x180003e1a  call    WPP_SF_L
0x180003e1f  jmp     loc_180003D1C
```
