# sub_1801FBDAC

- ea: `0x1801fbdac`
- end: `0x1801fc096`
- name: `sub_1801FBDAC`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1801fc098`

## callees

- `0x1800502d0`
- `0x180051098`
- `0x180057e60`
- `0x180095ae0`
- `0x180095c58`
- `0x180097698`
- `0x180097740`
- `0x1800979f8`
- `0x180197870`
- `0x1801fbdac`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x1801fbfac`
- `KERNEL32!SetFileInformationByHandle` at `0x1801fbfac`
- `KERNEL32!DeleteFileW` at `0x1801fbf44`
- `KERNEL32!DeleteFileW` at `0x1801fc019`
- `KERNEL32!DeleteFileW` at `0x1801fbf44`
- `KERNEL32!DeleteFileW` at `0x1801fc019`
- `KERNEL32!CloseHandle` at `0x1801fbfef`
- `KERNEL32!CloseHandle` at `0x1801fbfef`
- `KERNEL32!CopyFileW` at `0x1801fbee2`
- `KERNEL32!CopyFileW` at `0x1801fbee2`
- `ADVAPI32!RevertToSelf` at `0x1801fc067`
- `ADVAPI32!RevertToSelf` at `0x1801fc067`

## pseudocode

```c
__int64 __fastcall sub_1801FBDAC(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // r9
  const WCHAR *v6; // rbx
  unsigned __int64 v7; // rdi
  const WCHAR *v8; // rcx
  _QWORD *v9; // rbp
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  char v12; // al
  const WCHAR *v13; // rcx
  char v14; // al
  void *v15; // rcx
  unsigned int v16; // eax
  void *v17; // rcx
  const WCHAR **v18; // rbx
  const WCHAR *v19; // rcx
  char v20; // al
  __int128 v22; // [rsp+30h] [rbp-38h] BYREF
  char FileInformation[8]; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  if ( *(_DWORD *)(a2 + 4) == 3 )
    v2 = *(_QWORD *)(a2 + 720);
  if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 4) != 0 )
  {
    v4 = (_QWORD *)(a2 + 272);
    if ( *(_QWORD *)(a2 + 296) > 7u )
      v4 = (_QWORD *)*v4;
    v5 = (_QWORD *)(a2 + 224);
    if ( *(_QWORD *)(a2 + 248) > 7u )
      v5 = (_QWORD *)*v5;
    sub_180097698(*((_QWORD *)off_18033CF60 + 2), 92, (unsigned int)&stru_1802D7620, (_DWORD)v5, (__int64)v4);
  }
  v22 = 0;
  sub_180197870(&v22, v2);
  v6 = (const WCHAR *)(a2 + 224);
  v7 = (-(__int64)(*(_BYTE *)(a2 + 50) != 0) & 0xFFFFFFFFFFFFFFC0uLL) + a2 + 336;
  v8 = (const WCHAR *)(a2 + 224);
  if ( *(_QWORD *)(a2 + 248) > 7u )
    v8 = *(const WCHAR **)v6;
  if ( (int)sub_1800502D0(v8) < 0 )
  {
    v10 = (const WCHAR *)(a2 + 224);
    if ( *(_QWORD *)(a2 + 248) > 7u )
      v10 = *(const WCHAR **)v6;
    v11 = (const WCHAR *)v7;
    if ( *(_QWORD *)(v7 + 24) > 7u )
      v11 = *(const WCHAR **)v7;
    v9 = (_QWORD *)(v7 + 24);
    if ( !CopyFileW(v11, v10, 1) )
    {
      v12 = sub_180051098();
      if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
      {
        if ( *(_QWORD *)(a2 + 248) > 7u )
          v6 = *(const WCHAR **)v6;
        sub_180097740(*((_QWORD *)off_18033CF60 + 2), (__int64)v6, v12);
      }
    }
  }
  else
  {
    if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 0x10) != 0 )
    {
      if ( *(_QWORD *)(a2 + 248) > 7u )
        v6 = *(const WCHAR **)v6;
      sub_180095C58(*((_QWORD *)off_18033CF60 + 2), 93, &stru_1802D7620, v6);
    }
    v9 = (_QWORD *)(v7 + 24);
  }
  v13 = (const WCHAR *)v7;
  if ( *v9 > 7u )
    v13 = *(const WCHAR **)v7;
  if ( !DeleteFileW(v13) )
  {
    v14 = sub_180051098();
    if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
    {
      if ( *v9 > 7u )
        v7 = *(_QWORD *)v7;
      sub_1800979F8(*((_QWORD *)off_18033CF60 + 2), 95, (unsigned int)&stru_1802D7620, v7, v14);
    }
  }
  v15 = *(void **)(a2 + 1800);
  if ( v15 != (void *)-1LL )
  {
    FileInformation[0] = 1;
    if ( !SetFileInformationByHandle(v15, FileDispositionInfo, FileInformation, 1u) )
    {
      v16 = sub_180051098();
      if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
        sub_180095AE0(*((_QWORD *)off_18033CF60 + 2), 96, &stru_1802D7620, v16);
      v17 = *(void **)(a2 + 1800);
      if ( v17 != (void *)-1LL )
      {
        CloseHandle(v17);
        *(_QWORD *)(a2 + 1800) = -1;
      }
    }
  }
  if ( *(_QWORD *)(a2 + 1800) == -1 )
  {
    v18 = (const WCHAR **)(a2 + 400);
    v19 = (const WCHAR *)(a2 + 400);
    if ( *(_QWORD *)(a2 + 424) > 7u )
      v19 = *v18;
    if ( !DeleteFileW(v19) )
    {
      v20 = sub_180051098();
      if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
      {
        if ( *(_QWORD *)(a2 + 424) > 7u )
          v18 = (const WCHAR **)*v18;
        sub_1800979F8(*((_QWORD *)off_18033CF60 + 2), 97, (unsigned int)&stru_1802D7620, (_DWORD)v18, v20);
      }
    }
  }
  if ( BYTE8(v22) )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1801fbdac  mov     [rsp+arg_0], rbx
0x1801fbdb1  mov     [rsp+arg_10], rbp
0x1801fbdb6  mov     [rsp+arg_18], rsi
0x1801fbdbb  push    rdi
0x1801fbdbc  push    r13
0x1801fbdbe  push    r14
0x1801fbdc0  sub     rsp, 50h
0x1801fbdc4  mov     rax, cs:__security_cookie
0x1801fbdcb  xor     rax, rsp
0x1801fbdce  mov     [rsp+68h+var_20], rax
0x1801fbdd3  xor     ebx, ebx
0x1801fbdd5  mov     rsi, rdx
0x1801fbdd8  cmp     dword ptr [rdx+4], 3
0x1801fbddc  jnz     short loc_1801FBDE5
0x1801fbdde  mov     rbx, [rdx+2D0h]
0x1801fbde5  mov     rcx, cs:off_18033CF60
0x1801fbdec  lea     r13, off_18033CF60
0x1801fbdf3  cmp     rcx, r13
0x1801fbdf6  jz      short loc_1801FBE3A
0x1801fbdf8  test    byte ptr [rcx+1Ch], 4
0x1801fbdfc  jz      short loc_1801FBE3A
0x1801fbdfe  lea     rax, [rdx+110h]
0x1801fbe05  cmp     qword ptr [rax+18h], 7
0x1801fbe0a  jbe     short loc_1801FBE0F
0x1801fbe0c  mov     rax, [rax]
0x1801fbe0f  lea     r9, [rdx+0E0h]
0x1801fbe16  cmp     qword ptr [r9+18h], 7
0x1801fbe1b  jbe     short loc_1801FBE20
0x1801fbe1d  mov     r9, [r9]
0x1801fbe20  mov     rcx, [rcx+10h]
0x1801fbe24  lea     r8, stru_1802D7620
0x1801fbe2b  mov     edx, 5Ch ; '\'
0x1801fbe30  mov     [rsp+68h+var_48], rax
0x1801fbe35  call    sub_180097698
0x1801fbe3a  xorps   xmm0, xmm0
0x1801fbe3d  lea     rcx, [rsp+68h+var_38]
0x1801fbe42  mov     rdx, rbx
0x1801fbe45  movups  [rsp+68h+var_38], xmm0
0x1801fbe4a  call    sub_180197870
0x1801fbe4f  mov     al, [rsi+32h]
0x1801fbe52  lea     rbx, [rsi+0E0h]
0x1801fbe59  neg     al
0x1801fbe5b  lea     rdi, [rsi+150h]
0x1801fbe62  sbb     rcx, rcx
0x1801fbe65  and     rcx, 0FFFFFFFFFFFFFFC0h
0x1801fbe69  add     rdi, rcx
0x1801fbe6c  mov     rcx, rbx
0x1801fbe6f  cmp     qword ptr [rbx+18h], 7
0x1801fbe74  jbe     short loc_1801FBE79
0x1801fbe76  mov     rcx, [rbx]
0x1801fbe79  call    sub_1800502D0
0x1801fbe7e  test    eax, eax
0x1801fbe80  js      short loc_1801FBEBC
0x1801fbe82  mov     rcx, cs:off_18033CF60
0x1801fbe89  cmp     rcx, r13
0x1801fbe8c  jz      short loc_1801FBEB6
0x1801fbe8e  test    byte ptr [rcx+1Ch], 10h
0x1801fbe92  jz      short loc_1801FBEB6
0x1801fbe94  cmp     qword ptr [rbx+18h], 7
0x1801fbe99  jbe     short loc_1801FBE9E
0x1801fbe9b  mov     rbx, [rbx]
0x1801fbe9e  mov     rcx, [rcx+10h]
0x1801fbea2  lea     r8, stru_1802D7620
0x1801fbea9  mov     edx, 5Dh ; ']'
0x1801fbeae  mov     r9, rbx
0x1801fbeb1  call    sub_180095C58
0x1801fbeb6  lea     rbp, [rdi+18h]
0x1801fbeba  jmp     short loc_1801FBF37
0x1801fbebc  cmp     qword ptr [rbx+18h], 7
0x1801fbec1  mov     rdx, rbx
0x1801fbec4  jbe     short loc_1801FBEC9
0x1801fbec6  mov     rdx, [rbx]; lpNewFileName
0x1801fbec9  lea     r14, [rdi+18h]
0x1801fbecd  mov     rcx, rdi
0x1801fbed0  cmp     qword ptr [r14], 7
0x1801fbed4  jbe     short loc_1801FBED9
0x1801fbed6  mov     rcx, [rdi]; lpExistingFileName
0x1801fbed9  mov     r8d, 1; bFailIfExists
0x1801fbedf  mov     rbp, r14
0x1801fbee2  call    cs:CopyFileW
0x1801fbee8  test    eax, eax
0x1801fbeea  jnz     short loc_1801FBF37
0x1801fbeec  call    sub_180051098
0x1801fbef1  mov     rcx, cs:off_18033CF60
0x1801fbef8  cmp     rcx, r13
0x1801fbefb  jz      short loc_1801FBF37
0x1801fbefd  test    byte ptr [rcx+1Ch], 1
0x1801fbf01  jz      short loc_1801FBF37
0x1801fbf03  cmp     qword ptr [rbx+18h], 7
0x1801fbf08  jbe     short loc_1801FBF0D
0x1801fbf0a  mov     rbx, [rbx]
0x1801fbf0d  cmp     qword ptr [r14], 7
0x1801fbf11  mov     r9, rdi
0x1801fbf14  jbe     short loc_1801FBF19
0x1801fbf16  mov     r9, [rdi]
0x1801fbf19  mov     rcx, [rcx+10h]; LoggerHandle
0x1801fbf1d  lea     r8, stru_1802D7620
0x1801fbf24  mov     dword ptr [rsp+68h+var_40], eax; char
0x1801fbf28  mov     edx, 5Eh ; '^'
0x1801fbf2d  mov     [rsp+68h+var_48], rbx; __int64
0x1801fbf32  call    sub_180097740
0x1801fbf37  cmp     qword ptr [rbp+0], 7
0x1801fbf3c  mov     rcx, rdi
0x1801fbf3f  jbe     short loc_1801FBF44
0x1801fbf41  mov     rcx, [rdi]; lpFileName
0x1801fbf44  call    cs:DeleteFileW
0x1801fbf4a  test    eax, eax
0x1801fbf4c  jnz     short loc_1801FBF8B
0x1801fbf4e  call    sub_180051098
0x1801fbf53  mov     rcx, cs:off_18033CF60
0x1801fbf5a  cmp     rcx, r13
0x1801fbf5d  jz      short loc_1801FBF8B
0x1801fbf5f  test    byte ptr [rcx+1Ch], 1
0x1801fbf63  jz      short loc_1801FBF8B
0x1801fbf65  cmp     qword ptr [rbp+0], 7
0x1801fbf6a  jbe     short loc_1801FBF6F
0x1801fbf6c  mov     rdi, [rdi]
0x1801fbf6f  mov     rcx, [rcx+10h]
0x1801fbf73  lea     r8, stru_1802D7620
0x1801fbf7a  mov     edx, 5Fh ; '_'
0x1801fbf7f  mov     dword ptr [rsp+68h+var_48], eax
0x1801fbf83  mov     r9, rdi
0x1801fbf86  call    sub_1800979F8
0x1801fbf8b  mov     rcx, [rsi+708h]; hFile
0x1801fbf92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801fbf96  cmp     rcx, rbx
0x1801fbf99  jz      short loc_1801FBFFC
0x1801fbf9b  lea     r9d, [rbx+2]; dwBufferSize
0x1801fbf9f  mov     [rsp+68h+FileInformation], 1
0x1801fbfa4  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x1801fbfa9  lea     edx, [rbx+5]; FileInformationClass
0x1801fbfac  call    cs:SetFileInformationByHandle
0x1801fbfb2  test    eax, eax
0x1801fbfb4  jnz     short loc_1801FBFFC
0x1801fbfb6  call    sub_180051098
0x1801fbfbb  mov     rcx, cs:off_18033CF60
0x1801fbfc2  cmp     rcx, r13
0x1801fbfc5  jz      short loc_1801FBFE3
0x1801fbfc7  test    byte ptr [rcx+1Ch], 1
0x1801fbfcb  jz      short loc_1801FBFE3
0x1801fbfcd  mov     rcx, [rcx+10h]
0x1801fbfd1  lea     edx, [rbx+61h]
0x1801fbfd4  mov     r9d, eax
0x1801fbfd7  lea     r8, stru_1802D7620
0x1801fbfde  call    sub_180095AE0
0x1801fbfe3  mov     rcx, [rsi+708h]; hObject
0x1801fbfea  cmp     rcx, rbx
0x1801fbfed  jz      short loc_1801FBFFC
0x1801fbfef  call    cs:CloseHandle
0x1801fbff5  mov     [rsi+708h], rbx
0x1801fbffc  cmp     [rsi+708h], rbx
0x1801fc003  jnz     short loc_1801FC060
0x1801fc005  lea     rbx, [rsi+190h]
0x1801fc00c  cmp     qword ptr [rbx+18h], 7
0x1801fc011  mov     rcx, rbx
0x1801fc014  jbe     short loc_1801FC019
0x1801fc016  mov     rcx, [rbx]; lpFileName
0x1801fc019  call    cs:DeleteFileW
0x1801fc01f  test    eax, eax
0x1801fc021  jnz     short loc_1801FC060
0x1801fc023  call    sub_180051098
0x1801fc028  mov     rcx, cs:off_18033CF60
0x1801fc02f  cmp     rcx, r13
0x1801fc032  jz      short loc_1801FC060
0x1801fc034  test    byte ptr [rcx+1Ch], 1
0x1801fc038  jz      short loc_1801FC060
0x1801fc03a  cmp     qword ptr [rbx+18h], 7
0x1801fc03f  jbe     short loc_1801FC044
0x1801fc041  mov     rbx, [rbx]
0x1801fc044  mov     rcx, [rcx+10h]
0x1801fc048  lea     r8, stru_1802D7620
0x1801fc04f  mov     edx, 61h ; 'a'
0x1801fc054  mov     dword ptr [rsp+68h+var_48], eax
0x1801fc058  mov     r9, rbx
0x1801fc05b  call    sub_1800979F8
0x1801fc060  cmp     byte ptr [rsp+68h+var_38+8], 0
0x1801fc065  jz      short loc_1801FC06D
0x1801fc067  call    cs:RevertToSelf
0x1801fc06d  xor     eax, eax
0x1801fc06f  mov     rcx, [rsp+68h+var_20]
0x1801fc074  xor     rcx, rsp; StackCookie
0x1801fc077  call    __security_check_cookie
0x1801fc07c  lea     r11, [rsp+68h+var_18]
0x1801fc081  mov     rbx, [r11+20h]
0x1801fc085  mov     rbp, [r11+30h]
0x1801fc089  mov     rsi, [r11+38h]
0x1801fc08d  mov     rsp, r11
0x1801fc090  pop     r14
0x1801fc092  pop     r13
0x1801fc094  pop     rdi
0x1801fc095  retn
```
