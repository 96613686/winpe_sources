# Utils::GetDriveLetterForVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x18004da98`
- end: `0x18004dcbb`
- name: `?GetDriveLetterForVolumeMountPoint@Utils@@SAKPEBGPEAGK@Z`
- size: `547`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18004d620`
- `0x1800502e0`
- `0x180052d8c`
- `0x180053114`

## callees

- `0x180001f94`
- `0x180001fa0`
- `0x180006ed8`
- `0x18004da98`
- `0x18004f8d0`
- `0x18004fb04`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004dae0`
- `KERNEL32!GetLastError` at `0x18004db47`
- `KERNEL32!GetLastError` at `0x18004dc1c`
- `KERNEL32!GetLastError` at `0x18004dae0`
- `KERNEL32!GetLastError` at `0x18004db47`
- `KERNEL32!GetLastError` at `0x18004dc1c`
- `KERNEL32!SetLastError` at `0x18004db2c`
- `KERNEL32!SetLastError` at `0x18004dbfa`
- `KERNEL32!SetLastError` at `0x18004db2c`
- `KERNEL32!SetLastError` at `0x18004dbfa`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004dad6`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004dad6`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004db41`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004dc12`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004db41`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004dc12`

## pseudocode

```c
__int64 __fastcall Utils::GetDriveLetterForVolumeMountPoint(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // r14
  int v5; // esi
  WCHAR *v6; // rdi
  DWORD LastError; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD cchReturnLength[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR szVolumeName[264]; // [rsp+40h] [rbp-248h] BYREF

  v3 = a3;
  cchReturnLength[0] = 0;
  v5 = (int)a1;
  v6 = 0;
  if ( !GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        v5,
        LastError);
    goto LABEL_25;
  }
  SetLastError(0);
  GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, cchReturnLength);
  LastError = GetLastError();
  if ( LastError != 234 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_25;
    v9 = 148;
    goto LABEL_9;
  }
  v6 = (WCHAR *)operator new[](saturated_mul(cchReturnLength[0], 2u));
  if ( v6 )
  {
    SetLastError(0);
    if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, v6, cchReturnLength[0], cchReturnLength) )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_25;
      v9 = 150;
LABEL_9:
      WPP_SF_d(v8[2], v9, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, LastError);
      goto LABEL_25;
    }
    LastError = StringCchCopyW(a2, v3, v6);
    if ( (LastError & 0x80000000) == 0 )
    {
      LastError = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, LastError);
      LastError = (unsigned __int16)LastError;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        cchReturnLength[0]);
    LastError = 14;
  }
LABEL_25:
  operator delete(v6);
  return LastError;
}

```

## disassembly

```asm
0x18004da98  push    rbx
0x18004da9a  push    rbp
0x18004da9b  push    rsi
0x18004da9c  push    rdi
0x18004da9d  push    r14
0x18004da9f  sub     rsp, 260h
0x18004daa6  mov     rax, cs:__security_cookie
0x18004daad  xor     rax, rsp
0x18004dab0  mov     [rsp+288h+var_38], rax
0x18004dab8  mov     r14d, r8d
0x18004dabb  mov     rbp, rdx
0x18004dabe  mov     r8d, 104h; cchBufferLength
0x18004dac4  mov     [rsp+288h+cchReturnLength], 0
0x18004dacc  lea     rdx, [rsp+288h+szVolumeName]; lpszVolumeName
0x18004dad1  mov     rsi, rcx
0x18004dad4  xor     edi, edi
0x18004dad6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004dadc  test    eax, eax
0x18004dade  jnz     short loc_18004DB2A
0x18004dae0  call    cs:__imp_GetLastError
0x18004dae6  mov     ebx, eax
0x18004dae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004daef  lea     rax, WPP_GLOBAL_Control
0x18004daf6  cmp     rcx, rax
0x18004daf9  jz      loc_18004DC93
0x18004daff  test    byte ptr [rcx+1Ch], 2
0x18004db03  jz      loc_18004DC93
0x18004db09  mov     rcx, [rcx+10h]
0x18004db0d  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004db14  mov     edx, 93h
0x18004db19  mov     [rsp+288h+var_268], ebx
0x18004db1d  mov     r9, rsi
0x18004db20  call    WPP_SF_Sd
0x18004db25  jmp     loc_18004DC93
0x18004db2a  xor     ecx, ecx; dwErrCode
0x18004db2c  call    cs:__imp_SetLastError
0x18004db32  lea     r9, [rsp+288h+cchReturnLength]; lpcchReturnLength
0x18004db37  xor     r8d, r8d; cchBufferLength
0x18004db3a  xor     edx, edx; lpszVolumePathNames
0x18004db3c  lea     rcx, [rsp+288h+szVolumeName]; lpszVolumeName
0x18004db41  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004db47  call    cs:__imp_GetLastError
0x18004db4d  mov     ebx, eax
0x18004db4f  cmp     eax, 0EAh
0x18004db54  jz      short loc_18004DB94
0x18004db56  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db5d  lea     rax, WPP_GLOBAL_Control
0x18004db64  cmp     rcx, rax
0x18004db67  jz      loc_18004DC93
0x18004db6d  test    byte ptr [rcx+1Ch], 2
0x18004db71  jz      loc_18004DC93
0x18004db77  mov     edx, 94h
0x18004db7c  mov     rcx, [rcx+10h]
0x18004db80  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004db87  mov     r9d, ebx
0x18004db8a  call    WPP_SF_d
0x18004db8f  jmp     loc_18004DC93
0x18004db94  mov     ecx, [rsp+288h+cchReturnLength]
0x18004db98  mov     eax, 2
0x18004db9d  mul     rcx
0x18004dba0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004dba7  cmovb   rax, rcx
0x18004dbab  mov     rcx, rax; unsigned __int64
0x18004dbae  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004dbb3  mov     rdi, rax
0x18004dbb6  test    rax, rax
0x18004dbb9  jnz     short loc_18004DBF8
0x18004dbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dbc2  lea     rax, WPP_GLOBAL_Control
0x18004dbc9  cmp     rcx, rax
0x18004dbcc  jz      short loc_18004DBEE
0x18004dbce  test    byte ptr [rcx+1Ch], 2
0x18004dbd2  jz      short loc_18004DBEE
0x18004dbd4  mov     r9d, [rsp+288h+cchReturnLength]
0x18004dbd9  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004dbe0  mov     rcx, [rcx+10h]
0x18004dbe4  mov     edx, 95h
0x18004dbe9  call    WPP_SF_d
0x18004dbee  mov     ebx, 0Eh
0x18004dbf3  jmp     loc_18004DC93
0x18004dbf8  xor     ecx, ecx; dwErrCode
0x18004dbfa  call    cs:__imp_SetLastError
0x18004dc00  mov     r8d, [rsp+288h+cchReturnLength]; cchBufferLength
0x18004dc05  lea     r9, [rsp+288h+cchReturnLength]; lpcchReturnLength
0x18004dc0a  mov     rdx, rdi; lpszVolumePathNames
0x18004dc0d  lea     rcx, [rsp+288h+szVolumeName]; lpszVolumeName
0x18004dc12  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004dc18  test    eax, eax
0x18004dc1a  jnz     short loc_18004DC47
0x18004dc1c  call    cs:__imp_GetLastError
0x18004dc22  mov     ebx, eax
0x18004dc24  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc2b  lea     rax, WPP_GLOBAL_Control
0x18004dc32  cmp     rcx, rax
0x18004dc35  jz      short loc_18004DC93
0x18004dc37  test    byte ptr [rcx+1Ch], 2
0x18004dc3b  jz      short loc_18004DC93
0x18004dc3d  mov     edx, 96h
0x18004dc42  jmp     loc_18004DB7C
0x18004dc47  mov     rdx, r14; unsigned __int64
0x18004dc4a  mov     r8, rdi; unsigned __int16 *
0x18004dc4d  mov     rcx, rbp; unsigned __int16 *
0x18004dc50  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004dc55  mov     ebx, eax
0x18004dc57  test    eax, eax
0x18004dc59  jns     short loc_18004DC91
0x18004dc5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc62  lea     rax, WPP_GLOBAL_Control
0x18004dc69  cmp     rcx, rax
0x18004dc6c  jz      short loc_18004DC8C
0x18004dc6e  test    byte ptr [rcx+1Ch], 2
0x18004dc72  jz      short loc_18004DC8C
0x18004dc74  mov     rcx, [rcx+10h]
0x18004dc78  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004dc7f  mov     edx, 97h
0x18004dc84  mov     r9d, ebx
0x18004dc87  call    WPP_SF_d
0x18004dc8c  movzx   ebx, bx
0x18004dc8f  jmp     short loc_18004DC93
0x18004dc91  xor     ebx, ebx
0x18004dc93  mov     rcx, rdi; Block
0x18004dc96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004dc9b  mov     eax, ebx
0x18004dc9d  mov     rcx, [rsp+288h+var_38]
0x18004dca5  xor     rcx, rsp; StackCookie
0x18004dca8  call    __security_check_cookie
0x18004dcad  add     rsp, 260h
0x18004dcb4  pop     r14
0x18004dcb6  pop     rdi
0x18004dcb7  pop     rsi
0x18004dcb8  pop     rbp
0x18004dcb9  pop     rbx
0x18004dcba  retn
```
