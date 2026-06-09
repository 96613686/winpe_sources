# FaxAccessCheck

- ea: `0x18000b250`
- end: `0x18000b3e8`
- name: `FaxAccessCheck`
- size: `408`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, DWORD AccessMask)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000abe4`
- `0x18000b250`
- `0x18000b3f0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b2bc`
- `KERNEL32!SetLastError` at `0x18000b2ff`
- `KERNEL32!SetLastError` at `0x18000b3a4`
- `KERNEL32!SetLastError` at `0x18000b2bc`
- `KERNEL32!SetLastError` at `0x18000b2ff`
- `KERNEL32!SetLastError` at `0x18000b3a4`

## pseudocode

```c
BOOL __stdcall FaxAccessCheck(HANDLE FaxHandle, DWORD AccessMask)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // edx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 88;
    goto LABEL_35;
  }
  if ( (AccessMask & 0xF10E007F) == 0 )
  {
    SetLastError(0);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 89;
LABEL_35:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( (AccessMask & 0xEE0FF80) != 0 )
  {
    SetLastError(0);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 90;
    goto LABEL_35;
  }
  v6 = AccessMask & 1 | 8;
  if ( (AccessMask & 2) == 0 )
    v6 = AccessMask & 1;
  v7 = v6 | 0x20;
  if ( (AccessMask & 4) == 0 )
    v7 = v6;
  v8 = v7 | 0x40;
  if ( (AccessMask & 8) == 0 )
    v8 = v7;
  v9 = v8 | 0x20;
  if ( (AccessMask & 0x10) == 0 )
    v9 = v8;
  v10 = v9 | 0x40;
  if ( (AccessMask & 0x20) == 0 )
    v10 = v9;
  v11 = v10 | 0x10;
  if ( (AccessMask & 0x40) == 0 )
    v11 = v10;
  return FaxAccessCheckEx(FaxHandle, AccessMask & 0xFFEE0000 | v11, 0);
}

```

## disassembly

```asm
0x18000b250  push    rbx
0x18000b252  push    rbp
0x18000b253  push    rsi
0x18000b254  push    rdi
0x18000b255  sub     rsp, 28h
0x18000b259  mov     edi, edx
0x18000b25b  mov     rbx, rcx
0x18000b25e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b265  lea     rbp, WPP_GLOBAL_Control
0x18000b26c  mov     esi, 1000h
0x18000b271  cmp     rcx, rbp
0x18000b274  jz      short loc_18000B296
0x18000b276  test    [rcx+1Ch], esi
0x18000b279  jz      short loc_18000B296
0x18000b27b  cmp     byte ptr [rcx+19h], 5
0x18000b27f  jb      short loc_18000B296
0x18000b281  mov     rcx, [rcx+10h]
0x18000b285  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b28c  mov     edx, 57h ; 'W'
0x18000b291  call    WPP_SF_
0x18000b296  test    rbx, rbx
0x18000b299  jz      loc_18000B39F
0x18000b29f  cmp     dword ptr [rbx], 0
0x18000b2a2  jz      loc_18000B39F
0x18000b2a8  cmp     dword ptr [rbx+10h], 0
0x18000b2ac  jnz     loc_18000B39F
0x18000b2b2  test    edi, 0F10E007Fh
0x18000b2b8  jnz     short loc_18000B2F5
0x18000b2ba  xor     ecx, ecx; dwErrCode
0x18000b2bc  call    cs:__imp_SetLastError
0x18000b2c3  nop     dword ptr [rax+rax+00h]
0x18000b2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2cf  cmp     rcx, rbp
0x18000b2d2  jz      loc_18000B3DC
0x18000b2d8  test    [rcx+1Ch], esi
0x18000b2db  jz      loc_18000B3DC
0x18000b2e1  cmp     byte ptr [rcx+19h], 2
0x18000b2e5  jb      loc_18000B3DC
0x18000b2eb  mov     edx, 59h ; 'Y'
0x18000b2f0  jmp     loc_18000B3CC
0x18000b2f5  test    edi, 0EE0FF80h
0x18000b2fb  jz      short loc_18000B338
0x18000b2fd  xor     ecx, ecx; dwErrCode
0x18000b2ff  call    cs:__imp_SetLastError
0x18000b306  nop     dword ptr [rax+rax+00h]
0x18000b30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b312  cmp     rcx, rbp
0x18000b315  jz      loc_18000B3DC
0x18000b31b  test    [rcx+1Ch], esi
0x18000b31e  jz      loc_18000B3DC
0x18000b324  cmp     byte ptr [rcx+19h], 2
0x18000b328  jb      loc_18000B3DC
0x18000b32e  mov     edx, 5Ah ; 'Z'
0x18000b333  jmp     loc_18000B3CC
0x18000b338  mov     ecx, edi
0x18000b33a  and     ecx, 1
0x18000b33d  mov     edx, ecx
0x18000b33f  or      edx, 8
0x18000b342  test    dil, 2
0x18000b346  cmovz   edx, ecx
0x18000b349  mov     ecx, edx
0x18000b34b  or      ecx, 20h
0x18000b34e  test    dil, 4
0x18000b352  cmovz   ecx, edx
0x18000b355  mov     edx, ecx
0x18000b357  or      edx, 40h
0x18000b35a  test    dil, 8
0x18000b35e  cmovz   edx, ecx
0x18000b361  mov     ecx, edx
0x18000b363  or      ecx, 20h
0x18000b366  test    dil, 10h
0x18000b36a  cmovz   ecx, edx
0x18000b36d  mov     r8d, ecx
0x18000b370  or      r8d, 40h
0x18000b374  test    dil, 20h
0x18000b378  cmovz   r8d, ecx
0x18000b37c  mov     rcx, rbx; void *
0x18000b37f  mov     edx, r8d
0x18000b382  or      edx, 10h
0x18000b385  test    dil, 40h
0x18000b389  cmovz   edx, r8d
0x18000b38d  and     edi, 0FFEE0000h
0x18000b393  or      edx, edi; unsigned int
0x18000b395  xor     r8d, r8d; unsigned int *
0x18000b398  call    FaxAccessCheckEx
0x18000b39d  jmp     short loc_18000B3DE
0x18000b39f  mov     ecx, 6; dwErrCode
0x18000b3a4  call    cs:__imp_SetLastError
0x18000b3ab  nop     dword ptr [rax+rax+00h]
0x18000b3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3b7  cmp     rcx, rbp
0x18000b3ba  jz      short loc_18000B3DC
0x18000b3bc  test    [rcx+1Ch], esi
0x18000b3bf  jz      short loc_18000B3DC
0x18000b3c1  cmp     byte ptr [rcx+19h], 2
0x18000b3c5  jb      short loc_18000B3DC
0x18000b3c7  mov     edx, 58h ; 'X'
0x18000b3cc  mov     rcx, [rcx+10h]
0x18000b3d0  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b3d7  call    WPP_SF_
0x18000b3dc  xor     eax, eax
0x18000b3de  add     rsp, 28h
0x18000b3e2  pop     rdi
0x18000b3e3  pop     rsi
0x18000b3e4  pop     rbp
0x18000b3e5  pop     rbx
0x18000b3e6  retn
```
