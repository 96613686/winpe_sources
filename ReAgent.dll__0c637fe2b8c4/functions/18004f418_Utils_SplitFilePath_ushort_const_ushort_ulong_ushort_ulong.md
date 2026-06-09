# Utils::SplitFilePath(ushort const *,ushort *,ulong,ushort *,ulong)

- ea: `0x18004f418`
- end: `0x18004f619`
- name: `?SplitFilePath@Utils@@SAKPEBGPEAGK1K@Z`
- size: `513`
- prototype: `static unsigned int(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18004d0a4`

## callees

- `0x18004f418`
- `0x18004f718`
- `0x18004f8d0`
- `0x18004fb04`
- `0x18004fb7c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f459`
- `KERNEL32!GetLastError` at `0x18004f5ba`
- `KERNEL32!GetLastError` at `0x18004f459`
- `KERNEL32!GetLastError` at `0x18004f5ba`
- `KERNEL32!GetVolumePathNameW` at `0x18004f44c`
- `KERNEL32!GetVolumePathNameW` at `0x18004f44c`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004f5b0`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004f5b0`

## pseudocode

```c
__int64 __fastcall Utils::SplitFilePath(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned __int16 **v7; // r9
  DWORD LastError; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  WCHAR *v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  int v15; // eax
  unsigned int v17; // [rsp+28h] [rbp-260h]
  unsigned __int64 v18; // [rsp+30h] [rbp-258h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
  {
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( szVolumePathName[v14] );
    v18 = v14;
    do
      ++v13;
    while ( a1[v13] );
    if ( v14 <= v13 )
    {
      v15 = StringCchCopyExW(a4, (unsigned __int64)szVolumePathName, &a1[v14], v7, &v18, v17);
      LOWORD(v9) = v15;
      if ( v15 >= 0 )
      {
        if ( 520 - v18 < 0x207 )
        {
          *(_DWORD *)&a4[520 - v18] = 92;
          v9 = 0;
          if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, a2, 0x208u) )
          {
            LastError = GetLastError();
            v9 = LastError;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v11 = 54;
              v12 = szVolumePathName;
              goto LABEL_28;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, 0);
          return 122;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
            (unsigned int)v15);
        return (unsigned __int16)v9;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
          (unsigned int)szVolumePathName,
          (__int64)a1);
      return 31;
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 50;
      LODWORD(v12) = (_DWORD)a1;
LABEL_28:
      WPP_SF_Sd(v10[2], v11, (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (_DWORD)v12, LastError);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18004f418  push    rbx
0x18004f41a  push    rbp
0x18004f41b  push    rsi
0x18004f41c  push    rdi
0x18004f41d  push    r14
0x18004f41f  sub     rsp, 260h
0x18004f426  mov     rax, cs:__security_cookie
0x18004f42d  xor     rax, rsp
0x18004f430  mov     [rsp+288h+var_38], rax
0x18004f438  mov     rbp, rdx
0x18004f43b  mov     r8d, 104h; cchBufferLength
0x18004f441  lea     rdx, [rsp+288h+szVolumePathName]; lpszVolumePathName
0x18004f446  mov     rsi, r9
0x18004f449  mov     rdi, rcx
0x18004f44c  call    cs:__imp_GetVolumePathNameW
0x18004f452  xor     r14d, r14d
0x18004f455  test    eax, eax
0x18004f457  jnz     short loc_18004F48E
0x18004f459  call    cs:__imp_GetLastError
0x18004f45f  mov     ebx, eax
0x18004f461  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f468  lea     rdx, WPP_GLOBAL_Control
0x18004f46f  cmp     rcx, rdx
0x18004f472  jz      loc_18004F5F9
0x18004f478  test    byte ptr [rcx+1Ch], 2
0x18004f47c  jz      loc_18004F5F9
0x18004f482  lea     edx, [r14+32h]
0x18004f486  mov     r9, rdi
0x18004f489  jmp     loc_18004F5E5
0x18004f48e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004f492  lea     rdx, [rsp+288h+szVolumePathName]; unsigned __int64
0x18004f497  mov     rax, rcx
0x18004f49a  inc     rax
0x18004f49d  cmp     [rdx+rax*2], r14w
0x18004f4a2  jnz     short loc_18004F49A
0x18004f4a4  mov     [rsp+288h+var_258], rax
0x18004f4a9  inc     rcx
0x18004f4ac  cmp     [rdi+rcx*2], r14w
0x18004f4b1  jnz     short loc_18004F4A9
0x18004f4b3  cmp     rax, rcx
0x18004f4b6  jbe     short loc_18004F4FA
0x18004f4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f4bf  lea     rdx, WPP_GLOBAL_Control
0x18004f4c6  cmp     rcx, rdx
0x18004f4c9  jz      short loc_18004F4F0
0x18004f4cb  test    byte ptr [rcx+1Ch], 2
0x18004f4cf  jz      short loc_18004F4F0
0x18004f4d1  mov     rcx, [rcx+10h]
0x18004f4d5  lea     r9, [rsp+288h+szVolumePathName]
0x18004f4da  mov     edx, 33h ; '3'
0x18004f4df  mov     [rsp+288h+var_268], rdi
0x18004f4e4  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f4eb  call    WPP_SF_SS
0x18004f4f0  mov     ebx, 1Fh
0x18004f4f5  jmp     loc_18004F5F9
0x18004f4fa  lea     r8, [rdi+rax*2]; unsigned __int16 *
0x18004f4fe  mov     rcx, rsi; unsigned __int16 *
0x18004f501  lea     rax, [rsp+288h+var_258]
0x18004f506  mov     [rsp+288h+var_268], rax; unsigned __int64 *
0x18004f50b  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18004f510  mov     ebx, eax
0x18004f512  test    eax, eax
0x18004f514  jns     short loc_18004F54F
0x18004f516  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f51d  lea     rdx, WPP_GLOBAL_Control
0x18004f524  cmp     rcx, rdx
0x18004f527  jz      short loc_18004F547
0x18004f529  test    byte ptr [rcx+1Ch], 2
0x18004f52d  jz      short loc_18004F547
0x18004f52f  mov     rcx, [rcx+10h]
0x18004f533  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f53a  mov     edx, 34h ; '4'
0x18004f53f  mov     r9d, eax
0x18004f542  call    WPP_SF_d
0x18004f547  movzx   ebx, bx
0x18004f54a  jmp     loc_18004F5F9
0x18004f54f  mov     r8d, 208h; cchBufferLength
0x18004f555  mov     ecx, r8d
0x18004f558  sub     rcx, [rsp+288h+var_258]
0x18004f55d  cmp     rcx, 207h
0x18004f564  jb      short loc_18004F59E
0x18004f566  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f56d  lea     rdx, WPP_GLOBAL_Control
0x18004f574  cmp     rcx, rdx
0x18004f577  jz      short loc_18004F597
0x18004f579  test    byte ptr [rcx+1Ch], 2
0x18004f57d  jz      short loc_18004F597
0x18004f57f  mov     rcx, [rcx+10h]
0x18004f583  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f58a  mov     edx, 35h ; '5'
0x18004f58f  xor     r9d, r9d
0x18004f592  call    WPP_SF_d
0x18004f597  mov     ebx, 7Ah ; 'z'
0x18004f59c  jmp     short loc_18004F5F9
0x18004f59e  mov     dword ptr [rsi+rcx*2], 5Ch ; '\'
0x18004f5a5  mov     rdx, rbp; lpszVolumeName
0x18004f5a8  lea     rcx, [rsp+288h+szVolumePathName]; lpszVolumeMountPoint
0x18004f5ad  mov     ebx, r14d
0x18004f5b0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004f5b6  test    eax, eax
0x18004f5b8  jnz     short loc_18004F5F9
0x18004f5ba  call    cs:__imp_GetLastError
0x18004f5c0  mov     ebx, eax
0x18004f5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5c9  lea     rdx, WPP_GLOBAL_Control
0x18004f5d0  cmp     rcx, rdx
0x18004f5d3  jz      short loc_18004F5F9
0x18004f5d5  test    byte ptr [rcx+1Ch], 2
0x18004f5d9  jz      short loc_18004F5F9
0x18004f5db  mov     edx, 36h ; '6'
0x18004f5e0  lea     r9, [rsp+288h+szVolumePathName]
0x18004f5e5  mov     rcx, [rcx+10h]
0x18004f5e9  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f5f0  mov     dword ptr [rsp+288h+var_268], eax
0x18004f5f4  call    WPP_SF_Sd
0x18004f5f9  mov     eax, ebx
0x18004f5fb  mov     rcx, [rsp+288h+var_38]
0x18004f603  xor     rcx, rsp; StackCookie
0x18004f606  call    __security_check_cookie
0x18004f60b  add     rsp, 260h
0x18004f612  pop     r14
0x18004f614  pop     rdi
0x18004f615  pop     rsi
0x18004f616  pop     rbp
0x18004f617  pop     rbx
0x18004f618  retn
```
