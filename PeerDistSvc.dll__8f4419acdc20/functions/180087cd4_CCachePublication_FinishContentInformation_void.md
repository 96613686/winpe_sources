# CCachePublication::FinishContentInformation(void)

- ea: `0x180087cd4`
- end: `0x180087e8d`
- name: `?FinishContentInformation@CCachePublication@@AEAAKXZ`
- size: `441`
- prototype: `__int64 __fastcall(CCachePublication *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180087510`

## callees

- `0x180008290`
- `0x1800082d0`
- `0x18000cfc0`
- `0x180087cd4`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087dec`
- `KERNEL32!CloseHandle` at `0x180087db7`
- `KERNEL32!CloseHandle` at `0x180087db7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180087d61`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180087d61`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180087de2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180087de2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCachePublication::FinishContentInformation(CCachePublication *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  __int64 v3; // r9
  DWORD v4; // ebx
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  char *v8; // rbx
  int v9; // esi
  DWORD v10; // eax
  DWORD v11; // edi

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((unsigned int *)this + 4);
  if ( (_DWORD)v3 != 3 )
  {
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) )
      WPP_SF_d(*((_QWORD *)v2 + 12), 56, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v3);
    return 87;
  }
  if ( !FlushFileBuffers(*((HANDLE *)this + 213)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v4;
    }
    v7 = 57;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v6 + 12), v7, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, LastError);
    return v4;
  }
  CloseHandle(*((HANDLE *)this + 213));
  v8 = (char *)this + 144;
  *((_QWORD *)this + 213) = -1;
  v9 = (_DWORD)this + 664;
  if ( MoveFileExW((LPCWSTR)this + 332, (LPCWSTR)this + 72, 1u) )
  {
    LastError = (*(__int64 (__fastcall **)(_QWORD, CCachePublication *, _QWORD))(**((_QWORD **)this + 11) + 144LL))(
                  *((_QWORD *)this + 11),
                  this,
                  *((_QWORD *)this + 237));
    v4 = LastError;
    if ( !LastError )
    {
      *((_BYTE *)this + 1777) = 0;
      return v4;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 59;
      goto LABEL_16;
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        58,
        (unsigned int)WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
        v9,
        (__int64)v8,
        v10);
    }
    v4 = 0;
    if ( v11 != 2 )
      return v11;
  }
  return v4;
}

```

## disassembly

```asm
0x180087cd4  push    rbx
0x180087cd6  push    rsi
0x180087cd7  push    rdi
0x180087cd8  push    r14
0x180087cda  push    r15
0x180087cdc  sub     rsp, 30h
0x180087ce0  mov     rdi, rcx
0x180087ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180087cea  lea     r14, WPP_GLOBAL_Control
0x180087cf1  lea     r15, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180087cf8  cmp     rcx, r14
0x180087cfb  jz      short loc_180087D24
0x180087cfd  test    byte ptr [rcx+6Ch], 4
0x180087d01  jz      short loc_180087D24
0x180087d03  cmp     byte ptr [rcx+69h], 4
0x180087d07  jb      short loc_180087D24
0x180087d09  mov     rcx, [rcx+60h]
0x180087d0d  mov     edx, 37h ; '7'
0x180087d12  mov     r9, rdi
0x180087d15  mov     r8, r15
0x180087d18  call    WPP_SF_q
0x180087d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180087d24  mov     r9d, [rdi+10h]
0x180087d28  cmp     r9d, 3
0x180087d2c  jz      short loc_180087D5A
0x180087d2e  cmp     rcx, r14
0x180087d31  jz      short loc_180087D50
0x180087d33  test    byte ptr [rcx+6Ch], 4
0x180087d37  jz      short loc_180087D50
0x180087d39  cmp     byte ptr [rcx+69h], 1
0x180087d3d  jb      short loc_180087D50
0x180087d3f  mov     rcx, [rcx+60h]
0x180087d43  mov     edx, 38h ; '8'
0x180087d48  mov     r8, r15
0x180087d4b  call    WPP_SF_d
0x180087d50  mov     ebx, 57h ; 'W'
0x180087d55  jmp     loc_180087E7F
0x180087d5a  mov     rcx, [rdi+6A8h]; hFile
0x180087d61  call    cs:__imp_FlushFileBuffers
0x180087d67  test    eax, eax
0x180087d69  jnz     short loc_180087DB0
0x180087d6b  call    cs:__imp_GetLastError
0x180087d71  mov     ebx, eax
0x180087d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180087d7a  cmp     rcx, r14
0x180087d7d  jz      loc_180087E7F
0x180087d83  test    byte ptr [rcx+6Ch], 4
0x180087d87  jz      loc_180087E7F
0x180087d8d  cmp     byte ptr [rcx+69h], 1
0x180087d91  jb      loc_180087E7F
0x180087d97  mov     edx, 39h ; '9'
0x180087d9c  mov     rcx, [rcx+60h]
0x180087da0  mov     r9d, eax
0x180087da3  mov     r8, r15
0x180087da6  call    WPP_SF_d
0x180087dab  jmp     loc_180087E7F
0x180087db0  mov     rcx, [rdi+6A8h]; hObject
0x180087db7  call    cs:__imp_CloseHandle
0x180087dbd  lea     rbx, [rdi+90h]
0x180087dc4  mov     qword ptr [rdi+6A8h], 0FFFFFFFFFFFFFFFFh
0x180087dcf  lea     rsi, [rdi+298h]
0x180087dd6  mov     rdx, rbx; lpNewFileName
0x180087dd9  mov     rcx, rsi; lpExistingFileName
0x180087ddc  mov     r8d, 1; dwFlags
0x180087de2  call    cs:__imp_MoveFileExW
0x180087de8  test    eax, eax
0x180087dea  jnz     short loc_180087E33
0x180087dec  call    cs:__imp_GetLastError
0x180087df2  mov     edi, eax
0x180087df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180087dfb  cmp     rcx, r14
0x180087dfe  jz      short loc_180087E29
0x180087e00  test    byte ptr [rcx+6Ch], 4
0x180087e04  jz      short loc_180087E29
0x180087e06  cmp     byte ptr [rcx+69h], 1
0x180087e0a  jb      short loc_180087E29
0x180087e0c  mov     rcx, [rcx+60h]
0x180087e10  mov     edx, 3Ah ; ':'
0x180087e15  mov     [rsp+58h+var_30], eax
0x180087e19  mov     r9, rsi
0x180087e1c  mov     r8, r15
0x180087e1f  mov     [rsp+58h+var_38], rbx
0x180087e24  call    WPP_SF_SSD
0x180087e29  xor     ebx, ebx
0x180087e2b  cmp     edi, 2
0x180087e2e  cmovnz  ebx, edi
0x180087e31  jmp     short loc_180087E7F
0x180087e33  mov     rcx, [rdi+58h]
0x180087e37  mov     rdx, rdi
0x180087e3a  mov     r8, [rdi+768h]
0x180087e41  mov     rax, [rcx]
0x180087e44  mov     rax, [rax+90h]
0x180087e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e50  mov     ebx, eax
0x180087e52  test    eax, eax
0x180087e54  jz      short loc_180087E78
0x180087e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e5d  cmp     rcx, r14
0x180087e60  jz      short loc_180087E7F
0x180087e62  test    byte ptr [rcx+6Ch], 4
0x180087e66  jz      short loc_180087E7F
0x180087e68  cmp     byte ptr [rcx+69h], 1
0x180087e6c  jb      short loc_180087E7F
0x180087e6e  mov     edx, 3Bh ; ';'
0x180087e73  jmp     loc_180087D9C
0x180087e78  mov     byte ptr [rdi+6F1h], 0
0x180087e7f  mov     eax, ebx
0x180087e81  add     rsp, 30h
0x180087e85  pop     r15
0x180087e87  pop     r14
0x180087e89  pop     rdi
0x180087e8a  pop     rsi
0x180087e8b  pop     rbx
0x180087e8c  retn
```
