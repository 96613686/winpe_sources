# MountFileSystem(ushort const *)

- ea: `0x18000f290`
- end: `0x18000f74d`
- name: `?MountFileSystem@@YAXPEBG@Z`
- size: `1213`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800053a0`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000f290`
- `0x18002cac4`
- `0x18002e628`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000f494`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f514`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f494`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f514`
- `ntdll!RtlNtStatusToDosError` at `0x18000f4a2`
- `ntdll!RtlNtStatusToDosError` at `0x18000f4a2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000f4fa`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000f4fa`

## pseudocode

```c
void __fastcall MountFileSystem(const unsigned __int16 *a1)
{
  PVOID *v2; // rdi
  __int64 v3; // r11
  WCHAR *v4; // r8
  __int64 v5; // r10
  __int64 v6; // rcx
  __int64 v7; // r9
  const unsigned __int16 *v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  _WORD *v13; // rcx
  NTSTATUS v14; // eax
  signed int v15; // eax
  int v16; // r8d
  WCHAR *v17; // rcx
  const unsigned __int16 *v18; // rdx
  WCHAR *v19; // rax
  unsigned int KnownLastErrorHR; // eax
  ULONG OldMode[4]; // [rsp+40h] [rbp-678h] BYREF
  WCHAR RootPathName[262]; // [rsp+50h] [rbp-668h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+260h] [rbp-458h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+470h] [rbp-248h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  OldMode[0] = 0;
  memset_0(RootPathName, 0, sizeof(RootPathName));
  memset_0(VolumeNameBuffer, 0, 0x20Au);
  memset_0(FileSystemNameBuffer, 0, 0x20Au);
  if ( a1 )
  {
    v3 = 2147483646;
    v4 = RootPathName;
    v5 = 262;
    v6 = 2147483646;
    v7 = 262;
    v8 = a1;
    while ( v6 && *v8 )
    {
      *v4++ = *v8++;
      --v6;
      if ( !--v7 )
      {
        *(v4 - 1) = 0;
        if ( v2 == &WPP_GLOBAL_Control )
          return;
        if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
        {
          WPP_SF_S(v2[2], 13, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, a1);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v2 == &WPP_GLOBAL_Control )
          return;
        v11 = -2147024809;
        if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
          goto LABEL_35;
        v12 = 14;
        goto LABEL_57;
      }
    }
    *v4 = 0;
    v9 = RootPathName;
    v10 = 262;
    while ( *v9 )
    {
      ++v9;
      if ( !--v10 )
      {
        if ( v2 == &WPP_GLOBAL_Control )
          return;
        if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
        {
          WPP_SF_S(v2[2], 15, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, a1);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v2 == &WPP_GLOBAL_Control )
          return;
        v11 = -2147024809;
        if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
          goto LABEL_35;
        v12 = 16;
        goto LABEL_57;
      }
    }
    if ( (unsigned __int64)(262 - v10) <= 1 )
    {
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
      {
        WPP_SF_S(v2[2], 17, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, a1);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      v11 = -2147024809;
      if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
        goto LABEL_35;
      v12 = 18;
      goto LABEL_57;
    }
    v13 = (_WORD *)&OldMode[3] + 262 - v10 + 1;
    if ( *v13 != 92 && *v13 != 47 )
    {
      v19 = RootPathName;
      while ( *v19 )
      {
        ++v19;
        if ( !--v5 )
          goto LABEL_48;
      }
      v16 = 0;
      v17 = FileSystemNameBuffer - v5 + 1;
      v18 = L"\\";
      while ( v3 && *v18 )
      {
        *v17++ = *v18++;
        --v3;
        if ( !--v5 )
        {
          --v17;
          v16 = -2147024774;
          break;
        }
      }
      *v17 = 0;
      if ( v16 >= 0 )
        goto LABEL_29;
LABEL_48:
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
      {
        WPP_SF_S(v2[2], 19, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, a1);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      v11 = -2147024809;
      if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
        goto LABEL_35;
      v12 = 20;
      goto LABEL_57;
    }
    *v13 = 92;
LABEL_29:
    v14 = RtlSetThreadErrorMode(0x10u, OldMode);
    v15 = RtlNtStatusToDosError(v14);
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
    {
      if ( !GetVolumeInformationW(RootPathName, VolumeNameBuffer, 0x105u, 0, 0, 0, FileSystemNameBuffer, 0x105u) )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v11 = KnownLastErrorHR;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
            (unsigned int)RootPathName,
            KnownLastErrorHR);
      }
      RtlSetThreadErrorMode(OldMode[0], 0);
      goto LABEL_34;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 21;
      goto LABEL_57;
    }
LABEL_35:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
      WPP_SF_d(v2[2], 23, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v11);
    return;
  }
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
    {
      WPP_SF_(v2[2], 11, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control )
    {
      v11 = -2147024809;
      if ( (*((_BYTE *)v2 + 28) & 0x40) != 0 )
      {
        v12 = 12;
LABEL_57:
        WPP_SF_d(v2[2], v12, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v11);
LABEL_34:
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_35;
    }
  }
}

```

## disassembly

```asm
0x18000f290  push    rbx
0x18000f292  push    rbp
0x18000f293  push    rsi
0x18000f294  push    rdi
0x18000f295  sub     rsp, 698h
0x18000f29c  mov     rax, cs:__security_cookie
0x18000f2a3  xor     rax, rsp
0x18000f2a6  mov     [rsp+6B8h+var_38], rax
0x18000f2ae  mov     rbx, rcx
0x18000f2b1  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f2b8  lea     rsi, WPP_GLOBAL_Control
0x18000f2bf  cmp     rdi, rsi
0x18000f2c2  jnz     loc_18000F3E9
0x18000f2c8  xor     ebp, ebp
0x18000f2ca  lea     rcx, [rsp+6B8h+RootPathName]; void *
0x18000f2cf  xor     edx, edx; Val
0x18000f2d1  mov     [rsp+6B8h+OldMode], ebp
0x18000f2d5  mov     r8d, 20Ch; Size
0x18000f2db  call    memset_0
0x18000f2e0  xor     edx, edx; Val
0x18000f2e2  lea     rcx, [rsp+6B8h+VolumeNameBuffer]; void *
0x18000f2ea  mov     r8d, 20Ah; Size
0x18000f2f0  call    memset_0
0x18000f2f5  xor     edx, edx; Val
0x18000f2f7  lea     rcx, [rsp+6B8h+FileSystemNameBuffer]; void *
0x18000f2ff  mov     r8d, 20Ah; Size
0x18000f305  call    memset_0
0x18000f30a  test    rbx, rbx
0x18000f30d  jz      loc_18000F414
0x18000f313  mov     r11d, 7FFFFFFEh
0x18000f319  lea     r8, [rsp+6B8h+RootPathName]
0x18000f31e  mov     r10d, 106h
0x18000f324  mov     ecx, r11d
0x18000f327  mov     r9d, r10d
0x18000f32a  mov     rdx, rbx
0x18000f32d  nop     dword ptr [rax]
0x18000f330  test    rcx, rcx
0x18000f333  jz      short loc_18000F382
0x18000f335  movzx   eax, word ptr [rdx]
0x18000f338  test    ax, ax
0x18000f33b  jz      short loc_18000F37D
0x18000f33d  mov     [r8], ax
0x18000f341  add     rdx, 2
0x18000f345  add     r8, 2
0x18000f349  dec     rcx
0x18000f34c  sub     r9, 1
0x18000f350  jnz     short loc_18000F330
0x18000f352  mov     [r8-2], bp
0x18000f357  cmp     rdi, rsi
0x18000f35a  jnz     loc_18000F658
0x18000f360  mov     rcx, [rsp+6B8h+var_38]
0x18000f368  xor     rcx, rsp; StackCookie
0x18000f36b  call    __security_check_cookie
0x18000f370  add     rsp, 698h
0x18000f377  pop     rdi
0x18000f378  pop     rsi
0x18000f379  pop     rbp
0x18000f37a  pop     rbx
0x18000f37b  retn
0x18000f37d  test    r9, r9
0x18000f380  jz      short loc_18000F352
0x18000f382  mov     [r8], bp
0x18000f386  lea     rax, [rsp+6B8h+RootPathName]
0x18000f38b  mov     rcx, r10
0x18000f38e  cmp     [rax], bp
0x18000f391  jz      loc_18000F461
0x18000f397  add     rax, 2
0x18000f39b  sub     rcx, 1
0x18000f39f  jnz     short loc_18000F38E
0x18000f3a1  cmp     rdi, rsi
0x18000f3a4  jz      short loc_18000F360
0x18000f3a6  test    byte ptr [rdi+1Ch], 2
0x18000f3aa  jz      short loc_18000F3CB
0x18000f3ac  mov     rcx, [rdi+10h]
0x18000f3b0  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f3b7  mov     edx, 0Fh
0x18000f3bc  mov     r9, rbx
0x18000f3bf  call    WPP_SF_S
0x18000f3c4  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f3cb  cmp     rdi, rsi
0x18000f3ce  jz      short loc_18000F360
0x18000f3d0  test    byte ptr [rdi+1Ch], 40h
0x18000f3d4  mov     ebx, 80070057h
0x18000f3d9  jz      loc_18000F527
0x18000f3df  mov     edx, 10h
0x18000f3e4  jmp     loc_18000F640
0x18000f3e9  test    byte ptr [rdi+1Ch], 20h
0x18000f3ed  jz      loc_18000F2C8
0x18000f3f3  mov     rcx, [rdi+10h]
0x18000f3f7  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f3fe  mov     edx, 0Ah
0x18000f403  call    WPP_SF_
0x18000f408  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f40f  jmp     loc_18000F2C8
0x18000f414  cmp     rdi, rsi
0x18000f417  jz      loc_18000F360
0x18000f41d  test    byte ptr [rdi+1Ch], 2
0x18000f421  jz      short loc_18000F43F
0x18000f423  mov     rcx, [rdi+10h]
0x18000f427  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f42e  mov     edx, 0Bh
0x18000f433  call    WPP_SF_
0x18000f438  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f43f  cmp     rdi, rsi
0x18000f442  jz      loc_18000F360
0x18000f448  test    byte ptr [rdi+1Ch], 40h
0x18000f44c  mov     ebx, 80070057h
0x18000f451  jz      loc_18000F527
0x18000f457  mov     edx, 0Ch
0x18000f45c  jmp     loc_18000F640
0x18000f461  mov     rax, r10
0x18000f464  sub     rax, rcx
0x18000f467  cmp     rax, 1
0x18000f46b  jbe     loc_18000F686
0x18000f471  lea     rcx, [rsp+rax*2+6B8h+var_66A]
0x18000f476  movzx   eax, [rsp+rax*2+6B8h+var_66A]
0x18000f47b  cmp     ax, 5Ch ; '\'
0x18000f47f  jnz     loc_18000F6D6
0x18000f485  mov     word ptr [rcx], 5Ch ; '\'
0x18000f48a  lea     rdx, [rsp+6B8h+OldMode]; OldMode
0x18000f48f  mov     ecx, 10h; NewMode
0x18000f494  call    cs:__imp_RtlSetThreadErrorMode
0x18000f49b  nop     dword ptr [rax+rax+00h]
0x18000f4a0  mov     ecx, eax; Status
0x18000f4a2  call    cs:__imp_RtlNtStatusToDosError
0x18000f4a9  nop     dword ptr [rax+rax+00h]
0x18000f4ae  mov     ebx, eax
0x18000f4b0  test    eax, eax
0x18000f4b2  jle     short loc_18000F4BD
0x18000f4b4  movzx   ebx, ax
0x18000f4b7  or      ebx, 80070000h
0x18000f4bd  test    ebx, ebx
0x18000f4bf  js      loc_18000F6EA
0x18000f4c5  mov     [rsp+6B8h+nFileSystemNameSize], 105h; nFileSystemNameSize
0x18000f4cd  lea     rax, [rsp+6B8h+FileSystemNameBuffer]
0x18000f4d5  mov     [rsp+6B8h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18000f4da  lea     rdx, [rsp+6B8h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18000f4e2  mov     [rsp+6B8h+lpFileSystemFlags], rbp; lpFileSystemFlags
0x18000f4e7  lea     rcx, [rsp+6B8h+RootPathName]; lpRootPathName
0x18000f4ec  xor     r9d, r9d; lpVolumeSerialNumber
0x18000f4ef  mov     [rsp+6B8h+lpMaximumComponentLength], rbp; lpMaximumComponentLength
0x18000f4f4  mov     r8d, 105h; nVolumeNameSize
0x18000f4fa  call    cs:__imp_GetVolumeInformationW
0x18000f501  nop     dword ptr [rax+rax+00h]
0x18000f506  test    eax, eax
0x18000f508  jz      loc_18000F709
0x18000f50e  mov     ecx, [rsp+6B8h+OldMode]; NewMode
0x18000f512  xor     edx, edx; OldMode
0x18000f514  call    cs:__imp_RtlSetThreadErrorMode
0x18000f51b  nop     dword ptr [rax+rax+00h]
0x18000f520  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f527  cmp     rdi, rsi
0x18000f52a  jz      loc_18000F360
0x18000f530  test    byte ptr [rdi+1Ch], 20h
0x18000f534  jz      loc_18000F360
0x18000f53a  mov     rcx, [rdi+10h]
0x18000f53e  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f545  mov     edx, 17h
0x18000f54a  mov     r9d, ebx
0x18000f54d  call    WPP_SF_d
0x18000f552  jmp     loc_18000F360
0x18000f557  cmp     rdi, rsi
0x18000f55a  jz      loc_18000F360
0x18000f560  test    byte ptr [rdi+1Ch], 40h
0x18000f564  mov     ebx, 80070057h
0x18000f569  jz      short loc_18000F527
0x18000f56b  mov     edx, 0Eh
0x18000f570  jmp     loc_18000F640
0x18000f575  cmp     [rax], bp
0x18000f578  jnz     loc_18000F624
0x18000f57e  lea     rax, [r10+r10]
0x18000f582  mov     r8d, ebp
0x18000f585  lea     rcx, [rsp+6B8h+var_45C]
0x18000f58d  sub     rcx, rax
0x18000f590  lea     rdx, asc_180082AC0; "\\"
0x18000f597  test    r10, r10
0x18000f59a  jz      short loc_18000F5C1
0x18000f59c  test    r11, r11
0x18000f59f  jz      short loc_18000F5CB
0x18000f5a1  movzx   eax, word ptr [rdx]
0x18000f5a4  test    ax, ax
0x18000f5a7  jz      loc_18000F634
0x18000f5ad  mov     [rcx], ax
0x18000f5b0  add     rdx, 2
0x18000f5b4  add     rcx, 2
0x18000f5b8  dec     r11
0x18000f5bb  sub     r10, 1
0x18000f5bf  jnz     short loc_18000F59C
0x18000f5c1  sub     rcx, 2
0x18000f5c5  mov     r8d, 8007007Ah
0x18000f5cb  mov     [rcx], bp
0x18000f5ce  test    r8d, r8d
0x18000f5d1  jns     loc_18000F48A
0x18000f5d7  cmp     rdi, rsi
0x18000f5da  jz      loc_18000F360
0x18000f5e0  test    byte ptr [rdi+1Ch], 2
0x18000f5e4  jz      short loc_18000F605
0x18000f5e6  mov     rcx, [rdi+10h]
0x18000f5ea  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f5f1  mov     edx, 13h
0x18000f5f6  mov     r9, rbx
0x18000f5f9  call    WPP_SF_S
0x18000f5fe  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f605  cmp     rdi, rsi
0x18000f608  jz      loc_18000F360
0x18000f60e  test    byte ptr [rdi+1Ch], 40h
0x18000f612  mov     ebx, 80070057h
0x18000f617  jz      loc_18000F527
0x18000f61d  mov     edx, 14h
0x18000f622  jmp     short loc_18000F640
0x18000f624  add     rax, 2
0x18000f628  sub     r10, 1
0x18000f62c  jnz     loc_18000F575
0x18000f632  jmp     short loc_18000F5D7
0x18000f634  test    r10, r10
0x18000f637  jz      short loc_18000F5C1
0x18000f639  jmp     short loc_18000F5CB
0x18000f63b  mov     edx, 15h
0x18000f640  mov     rcx, [rdi+10h]
0x18000f644  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f64b  mov     r9d, ebx
0x18000f64e  call    WPP_SF_d
0x18000f653  jmp     loc_18000F520
0x18000f658  test    byte ptr [rdi+1Ch], 2
0x18000f65c  jz      loc_18000F557
0x18000f662  mov     rcx, [rdi+10h]
0x18000f666  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f66d  mov     edx, 0Dh
0x18000f672  mov     r9, rbx
0x18000f675  call    WPP_SF_S
0x18000f67a  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f681  jmp     loc_18000F557
0x18000f686  cmp     rdi, rsi
0x18000f689  jz      loc_18000F360
0x18000f68f  test    byte ptr [rdi+1Ch], 2
0x18000f693  jz      short loc_18000F6B4
0x18000f695  mov     rcx, [rdi+10h]
0x18000f699  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f6a0  mov     edx, 11h
0x18000f6a5  mov     r9, rbx
0x18000f6a8  call    WPP_SF_S
0x18000f6ad  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f6b4  cmp     rdi, rsi
0x18000f6b7  jz      loc_18000F360
0x18000f6bd  test    byte ptr [rdi+1Ch], 40h
0x18000f6c1  mov     ebx, 80070057h
0x18000f6c6  jz      loc_18000F527
0x18000f6cc  mov     edx, 12h
0x18000f6d1  jmp     loc_18000F640
0x18000f6d6  cmp     ax, 2Fh ; '/'
0x18000f6da  jz      loc_18000F485
0x18000f6e0  lea     rax, [rsp+6B8h+RootPathName]
0x18000f6e5  jmp     loc_18000F575
0x18000f6ea  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f6f1  cmp     rdi, rsi
0x18000f6f4  jz      loc_18000F360
0x18000f6fa  test    byte ptr [rdi+1Ch], 2
0x18000f6fe  jz      loc_18000F527
0x18000f704  jmp     loc_18000F63B
0x18000f709  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000f70e  mov     ebx, eax
0x18000f710  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f717  cmp     rcx, rsi
0x18000f71a  jz      loc_18000F50E
0x18000f720  test    byte ptr [rcx+1Ch], 2
0x18000f724  jz      loc_18000F50E
0x18000f72a  mov     rcx, [rcx+10h]
0x18000f72e  lea     r9, [rsp+6B8h+RootPathName]
0x18000f733  mov     edx, 16h
0x18000f738  mov     dword ptr [rsp+6B8h+lpMaximumComponentLength], eax
0x18000f73c  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000f743  call    WPP_SF_Sd
0x18000f748  jmp     loc_18000F50E
```
