# Utils::ForceDriveLetterForVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x18004d620`
- end: `0x18004d820`
- name: `?ForceDriveLetterForVolumeMountPoint@Utils@@SAKPEBGPEAGK@Z`
- size: `512`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x180053114`

## callees

- `0x18000c6f0`
- `0x18004d620`
- `0x18004da98`
- `0x18004f8d0`
- `0x18004faa4`
- `0x18004fb04`
- `0x18004fb7c`
- `0x18004fc28`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetVolumeMountPointW` at `0x18004d6ed`
- `KERNEL32!SetVolumeMountPointW` at `0x18004d6ed`
- `KERNEL32!GetLastError` at `0x18004d65d`
- `KERNEL32!GetLastError` at `0x18004d70d`
- `KERNEL32!GetLastError` at `0x18004d65d`
- `KERNEL32!GetLastError` at `0x18004d70d`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004d653`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004d653`

## pseudocode

```c
__int64 __fastcall Utils::ForceDriveLetterForVolumeMountPoint(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD v4; // eax
  DWORD v5; // ebx
  unsigned __int16 v6; // bx
  int v7; // eax
  _QWORD *v8; // rcx
  char LastError; // al
  WCHAR szVolumeMountPoint; // [rsp+30h] [rbp-248h] BYREF
  int v12; // [rsp+32h] [rbp-246h]
  __int16 v13; // [rsp+36h] [rbp-242h]
  WCHAR szVolumeName[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x104u) )
  {
    v6 = 67;
    while ( 1 )
    {
      szVolumeMountPoint = 0;
      v12 = 0;
      v13 = 0;
      v7 = StringCchPrintfW(&szVolumeMountPoint, 4u, L"%c:\\", v6);
      if ( v7 < 0 )
        break;
      if ( SetVolumeMountPointW(&szVolumeMountPoint, szVolumeName) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            155,
            (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
            (unsigned int)szVolumeName,
            (__int64)&szVolumeMountPoint);
        return Utils::GetDriveLetterForVolumeMountPoint(a1, a2, 4u);
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, LastError);
        v8 = WPP_GLOBAL_Control;
      }
      if ( ++v6 > 0x5Au )
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
          WPP_SF_S(v8[2], 156, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, a1);
        return 1627;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        153,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (unsigned int)v7);
    return 266;
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        152,
        (unsigned int)WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (_DWORD)a1,
        v4);
  }
  return v5;
}

```

## disassembly

```asm
0x18004d620  mov     [rsp+arg_10], rbx
0x18004d625  push    rbp
0x18004d626  push    rdi
0x18004d627  push    r14
0x18004d629  sub     rsp, 260h
0x18004d630  mov     rax, cs:__security_cookie
0x18004d637  xor     rax, rsp
0x18004d63a  mov     [rsp+278h+var_28], rax
0x18004d642  mov     r14, rdx
0x18004d645  mov     r8d, 104h; cchBufferLength
0x18004d64b  lea     rdx, [rsp+278h+szVolumeName]; lpszVolumeName
0x18004d650  mov     rbp, rcx
0x18004d653  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004d659  test    eax, eax
0x18004d65b  jnz     short loc_18004D6A7
0x18004d65d  call    cs:__imp_GetLastError
0x18004d663  mov     ebx, eax
0x18004d665  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d66c  lea     rdi, WPP_GLOBAL_Control
0x18004d673  cmp     rcx, rdi
0x18004d676  jz      loc_18004D7FA
0x18004d67c  test    byte ptr [rcx+1Ch], 2
0x18004d680  jz      loc_18004D7FA
0x18004d686  mov     rcx, [rcx+10h]
0x18004d68a  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d691  mov     edx, 98h
0x18004d696  mov     dword ptr [rsp+278h+var_258], eax
0x18004d69a  mov     r9, rbp
0x18004d69d  call    WPP_SF_Sd
0x18004d6a2  jmp     loc_18004D7FA
0x18004d6a7  mov     ebx, 43h ; 'C'
0x18004d6ac  lea     rdi, WPP_GLOBAL_Control
0x18004d6b3  xor     eax, eax
0x18004d6b5  movzx   r9d, bx
0x18004d6b9  lea     r8, aC; "%c:\\"
0x18004d6c0  mov     [rsp+278h+szVolumeMountPoint], ax
0x18004d6c5  lea     rcx, [rsp+278h+szVolumeMountPoint]; unsigned __int16 *
0x18004d6ca  mov     [rsp+278h+var_246], eax
0x18004d6ce  mov     [rsp+278h+var_242], ax
0x18004d6d3  lea     edx, [rax+4]; unsigned __int64
0x18004d6d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d6db  test    eax, eax
0x18004d6dd  js      loc_18004D7CB
0x18004d6e3  lea     rdx, [rsp+278h+szVolumeName]; lpszVolumeName
0x18004d6e8  lea     rcx, [rsp+278h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18004d6ed  call    cs:__imp_SetVolumeMountPointW
0x18004d6f3  test    eax, eax
0x18004d6f5  jnz     loc_18004D780
0x18004d6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d702  cmp     rcx, rdi
0x18004d705  jz      short loc_18004D749
0x18004d707  test    byte ptr [rcx+1Ch], 8
0x18004d70b  jz      short loc_18004D749
0x18004d70d  call    cs:__imp_GetLastError
0x18004d713  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d71a  lea     r9, [rsp+278h+szVolumeMountPoint]
0x18004d71f  mov     dword ptr [rsp+278h+var_250], eax; char
0x18004d723  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d72a  lea     rax, [rsp+278h+szVolumeName]
0x18004d72f  mov     edx, 9Ah
0x18004d734  mov     [rsp+278h+var_258], rax; __int64
0x18004d739  mov     rcx, [rcx+10h]; LoggerHandle
0x18004d73d  call    WPP_SF_SSD
0x18004d742  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d749  inc     bx
0x18004d74c  cmp     bx, 5Ah ; 'Z'
0x18004d750  jbe     loc_18004D6B3
0x18004d756  cmp     rcx, rdi
0x18004d759  jz      short loc_18004D779
0x18004d75b  test    byte ptr [rcx+1Ch], 2
0x18004d75f  jz      short loc_18004D779
0x18004d761  mov     rcx, [rcx+10h]
0x18004d765  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d76c  mov     edx, 9Ch
0x18004d771  mov     r9, rbp
0x18004d774  call    WPP_SF_S
0x18004d779  mov     ebx, 65Bh
0x18004d77e  jmp     short loc_18004D7FA
0x18004d780  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d787  cmp     rcx, rdi
0x18004d78a  jz      short loc_18004D7B6
0x18004d78c  test    byte ptr [rcx+1Ch], 8
0x18004d790  jz      short loc_18004D7B6
0x18004d792  mov     rcx, [rcx+10h]
0x18004d796  lea     rax, [rsp+278h+szVolumeMountPoint]
0x18004d79b  mov     edx, 9Bh
0x18004d7a0  mov     [rsp+278h+var_258], rax
0x18004d7a5  lea     r9, [rsp+278h+szVolumeName]
0x18004d7aa  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d7b1  call    WPP_SF_SS
0x18004d7b6  mov     r8d, 4; unsigned int
0x18004d7bc  mov     rdx, r14; unsigned __int16 *
0x18004d7bf  mov     rcx, rbp; unsigned __int16 *
0x18004d7c2  call    ?GetDriveLetterForVolumeMountPoint@Utils@@SAKPEBGPEAGK@Z; Utils::GetDriveLetterForVolumeMountPoint(ushort const *,ushort *,ulong)
0x18004d7c7  mov     ebx, eax
0x18004d7c9  jmp     short loc_18004D7FA
0x18004d7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d7d2  cmp     rcx, rdi
0x18004d7d5  jz      short loc_18004D7F5
0x18004d7d7  test    byte ptr [rcx+1Ch], 2
0x18004d7db  jz      short loc_18004D7F5
0x18004d7dd  mov     rcx, [rcx+10h]
0x18004d7e1  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004d7e8  mov     edx, 99h
0x18004d7ed  mov     r9d, eax
0x18004d7f0  call    WPP_SF_d
0x18004d7f5  mov     ebx, 10Ah
0x18004d7fa  mov     eax, ebx
0x18004d7fc  mov     rcx, [rsp+278h+var_28]
0x18004d804  xor     rcx, rsp; StackCookie
0x18004d807  call    __security_check_cookie
0x18004d80c  mov     rbx, [rsp+278h+arg_10]
0x18004d814  add     rsp, 260h
0x18004d81b  pop     r14
0x18004d81d  pop     rdi
0x18004d81e  pop     rbp
0x18004d81f  retn
```
