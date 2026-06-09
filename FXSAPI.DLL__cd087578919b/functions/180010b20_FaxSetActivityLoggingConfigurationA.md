# FaxSetActivityLoggingConfigurationA

- ea: `0x180010b20`
- end: `0x180010cd0`
- name: `FaxSetActivityLoggingConfigurationA`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x180010b20`
- `0x180010ce0`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010ba0`
- `KERNEL32!SetLastError` at `0x180010be3`
- `KERNEL32!SetLastError` at `0x180010c8d`
- `KERNEL32!SetLastError` at `0x180010ba0`
- `KERNEL32!SetLastError` at `0x180010be3`
- `KERNEL32!SetLastError` at `0x180010c8d`

## pseudocode

```c
__int64 __fastcall FaxSetActivityLoggingConfigurationA(_DWORD *a1, __int128 *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int128 v6; // xmm0
  const CHAR *v7; // rcx
  unsigned int v8; // ebx
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-38h]

  v10 = 0;
  lpMem = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 182;
    goto LABEL_29;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 183;
    goto LABEL_29;
  }
  if ( *(_DWORD *)a2 != 24 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 184;
    goto LABEL_29;
  }
  v6 = *a2;
  v7 = (const CHAR *)*((_QWORD *)a2 + 2);
  lpMem = 0;
  v10 = v6;
  LODWORD(v10) = 24;
  if ( !v7 || (lpMem = AnsiStringToUnicodeString(v7)) != 0 )
  {
    v8 = FaxSetActivityLoggingConfigurationW((__int64)a1, (__int64)&v10);
    pMemFree(lpMem);
    return v8;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 185;
LABEL_29:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180010b20  push    rbx
0x180010b22  push    rbp
0x180010b23  push    rdi
0x180010b24  push    r14
0x180010b26  push    r15
0x180010b28  sub     rsp, 40h
0x180010b2c  xorps   xmm0, xmm0
0x180010b2f  xor     eax, eax
0x180010b31  movups  [rsp+68h+var_48], xmm0
0x180010b36  mov     [rsp+68h+lpMem], rax
0x180010b3b  mov     rdi, rdx
0x180010b3e  mov     rbx, rcx
0x180010b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b48  lea     r15, WPP_GLOBAL_Control
0x180010b4f  lea     r14, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010b56  mov     ebp, 1000h
0x180010b5b  cmp     rcx, r15
0x180010b5e  jz      short loc_180010B7C
0x180010b60  test    [rcx+1Ch], ebp
0x180010b63  jz      short loc_180010B7C
0x180010b65  cmp     byte ptr [rcx+19h], 5
0x180010b69  jb      short loc_180010B7C
0x180010b6b  mov     rcx, [rcx+10h]
0x180010b6f  mov     edx, 0B5h
0x180010b74  mov     r8, r14
0x180010b77  call    WPP_SF_
0x180010b7c  test    rbx, rbx
0x180010b7f  jz      loc_180010C88
0x180010b85  cmp     dword ptr [rbx], 0
0x180010b88  jz      loc_180010C88
0x180010b8e  cmp     dword ptr [rbx+10h], 0
0x180010b92  jnz     loc_180010C88
0x180010b98  test    rdi, rdi
0x180010b9b  jnz     short loc_180010BD9
0x180010b9d  lea     ecx, [rdi+57h]; dwErrCode
0x180010ba0  call    cs:__imp_SetLastError
0x180010ba7  nop     dword ptr [rax+rax+00h]
0x180010bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bb3  cmp     rcx, r15
0x180010bb6  jz      loc_180010CC1
0x180010bbc  test    [rcx+1Ch], ebp
0x180010bbf  jz      loc_180010CC1
0x180010bc5  cmp     byte ptr [rcx+19h], 2
0x180010bc9  jb      loc_180010CC1
0x180010bcf  mov     edx, 0B7h
0x180010bd4  jmp     loc_180010CB5
0x180010bd9  cmp     dword ptr [rdi], 18h
0x180010bdc  jz      short loc_180010C1C
0x180010bde  mov     ecx, 57h ; 'W'; dwErrCode
0x180010be3  call    cs:__imp_SetLastError
0x180010bea  nop     dword ptr [rax+rax+00h]
0x180010bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bf6  cmp     rcx, r15
0x180010bf9  jz      loc_180010CC1
0x180010bff  test    [rcx+1Ch], ebp
0x180010c02  jz      loc_180010CC1
0x180010c08  cmp     byte ptr [rcx+19h], 2
0x180010c0c  jb      loc_180010CC1
0x180010c12  mov     edx, 0B8h
0x180010c17  jmp     loc_180010CB5
0x180010c1c  movups  xmm0, xmmword ptr [rdi]
0x180010c1f  mov     rcx, [rdi+10h]; lpMultiByteStr
0x180010c23  mov     [rsp+68h+lpMem], 0
0x180010c2c  movups  [rsp+68h+var_48], xmm0
0x180010c31  mov     dword ptr [rsp+68h+var_48], 18h
0x180010c39  test    rcx, rcx
0x180010c3c  jz      short loc_180010C6B
0x180010c3e  call    AnsiStringToUnicodeString
0x180010c43  mov     [rsp+68h+lpMem], rax
0x180010c48  test    rax, rax
0x180010c4b  jnz     short loc_180010C6B
0x180010c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c54  cmp     rcx, r15
0x180010c57  jz      short loc_180010CC1
0x180010c59  test    [rcx+1Ch], ebp
0x180010c5c  jz      short loc_180010CC1
0x180010c5e  cmp     byte ptr [rcx+19h], 2
0x180010c62  jb      short loc_180010CC1
0x180010c64  mov     edx, 0B9h
0x180010c69  jmp     short loc_180010CB5
0x180010c6b  lea     rdx, [rsp+68h+var_48]
0x180010c70  mov     rcx, rbx
0x180010c73  call    FaxSetActivityLoggingConfigurationW
0x180010c78  mov     rcx, [rsp+68h+lpMem]; lpMem
0x180010c7d  mov     ebx, eax
0x180010c7f  call    pMemFree
0x180010c84  mov     eax, ebx
0x180010c86  jmp     short loc_180010CC3
0x180010c88  mov     ecx, 6; dwErrCode
0x180010c8d  call    cs:__imp_SetLastError
0x180010c94  nop     dword ptr [rax+rax+00h]
0x180010c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ca0  cmp     rcx, r15
0x180010ca3  jz      short loc_180010CC1
0x180010ca5  test    [rcx+1Ch], ebp
0x180010ca8  jz      short loc_180010CC1
0x180010caa  cmp     byte ptr [rcx+19h], 2
0x180010cae  jb      short loc_180010CC1
0x180010cb0  mov     edx, 0B6h
0x180010cb5  mov     rcx, [rcx+10h]
0x180010cb9  mov     r8, r14
0x180010cbc  call    WPP_SF_
0x180010cc1  xor     eax, eax
0x180010cc3  add     rsp, 40h
0x180010cc7  pop     r15
0x180010cc9  pop     r14
0x180010ccb  pop     rdi
0x180010ccc  pop     rbp
0x180010ccd  pop     rbx
0x180010cce  retn
```
