# NgscbGetVolumeFileSystemName

- ea: `0x180069f6c`
- end: `0x18006a082`
- name: `NgscbGetVolumeFileSystemName`
- size: `278`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName, LPWSTR lpFileSystemNameBuffer)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002c84c`
- `0x18006a088`

## callees

- `0x180009f60`
- `0x18001e260`
- `0x180069f6c`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180069f96`
- `ntdll!RtlSetThreadErrorMode` at `0x18006a063`
- `ntdll!RtlSetThreadErrorMode` at `0x180069f96`
- `ntdll!RtlSetThreadErrorMode` at `0x18006a063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069fd9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180069fc9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180069fc9`

## pseudocode

```c
__int64 __fastcall NgscbGetVolumeFileSystemName(LPCWSTR lpRootPathName, LPWSTR lpFileSystemNameBuffer)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  ULONG NewMode; // [rsp+60h] [rbp+18h] BYREF

  NewMode = 0;
  RtlSetThreadErrorMode(0x10u, &NewMode);
  *lpFileSystemNameBuffer = 0;
  if ( GetVolumeInformationW(lpRootPathName, 0, 0, 0, 0, 0, lpFileSystemNameBuffer, 0x105u) )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_b7e34095795c3f388dafa68a79cb47c9_Traceguids,
        (_DWORD)lpRootPathName,
        (__int64)lpFileSystemNameBuffer);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b7e34095795c3f388dafa68a79cb47c9_Traceguids, v5);
  }
  RtlSetThreadErrorMode(NewMode, 0);
  return v5;
}

```

## disassembly

```asm
0x180069f6c  mov     rax, rsp
0x180069f6f  mov     [rax+8], rbx
0x180069f73  mov     [rax+10h], rsi
0x180069f77  mov     [rax+18h], r8d
0x180069f7b  push    rdi
0x180069f7c  sub     rsp, 40h
0x180069f80  mov     rdi, rdx
0x180069f83  mov     dword ptr [rax+18h], 0
0x180069f8a  mov     rsi, rcx
0x180069f8d  lea     rdx, [rax+18h]; OldMode
0x180069f91  mov     ecx, 10h; NewMode
0x180069f96  call    cs:__imp_RtlSetThreadErrorMode
0x180069f9d  nop     dword ptr [rax+rax+00h]
0x180069fa2  xor     eax, eax
0x180069fa4  mov     [rsp+48h+nFileSystemNameSize], 105h; nFileSystemNameSize
0x180069fac  mov     [rsp+48h+lpFileSystemNameBuffer], rdi; lpFileSystemNameBuffer
0x180069fb1  xor     r9d, r9d; lpVolumeSerialNumber
0x180069fb4  mov     [rsp+48h+lpFileSystemFlags], rax; lpFileSystemFlags
0x180069fb9  xor     r8d, r8d; nVolumeNameSize
0x180069fbc  xor     edx, edx; lpVolumeNameBuffer
0x180069fbe  mov     [rsp+48h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x180069fc3  mov     rcx, rsi; lpRootPathName
0x180069fc6  mov     [rdi], ax
0x180069fc9  call    cs:__imp_GetVolumeInformationW
0x180069fd0  nop     dword ptr [rax+rax+00h]
0x180069fd5  test    eax, eax
0x180069fd7  jnz     short loc_18006A027
0x180069fd9  call    cs:__imp_GetLastError
0x180069fe0  nop     dword ptr [rax+rax+00h]
0x180069fe5  mov     ebx, eax
0x180069fe7  test    eax, eax
0x180069fe9  jle     short loc_180069FF4
0x180069feb  movzx   ebx, ax
0x180069fee  or      ebx, 80070000h
0x180069ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ffb  lea     rax, WPP_GLOBAL_Control
0x18006a002  cmp     rcx, rax
0x18006a005  jz      short loc_18006A05D
0x18006a007  test    byte ptr [rcx+1Ch], 40h
0x18006a00b  jz      short loc_18006A05D
0x18006a00d  mov     rcx, [rcx+10h]
0x18006a011  lea     r8, WPP_b7e34095795c3f388dafa68a79cb47c9_Traceguids
0x18006a018  mov     edx, 0Ah
0x18006a01d  mov     r9d, ebx
0x18006a020  call    WPP_SF_d
0x18006a025  jmp     short loc_18006A05D
0x18006a027  xor     ebx, ebx
0x18006a029  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a030  lea     rax, WPP_GLOBAL_Control
0x18006a037  cmp     rcx, rax
0x18006a03a  jz      short loc_18006A05D
0x18006a03c  test    byte ptr [rcx+1Ch], 8
0x18006a040  jz      short loc_18006A05D
0x18006a042  mov     rcx, [rcx+10h]
0x18006a046  lea     edx, [rbx+0Bh]
0x18006a049  mov     r9, rsi
0x18006a04c  mov     [rsp+48h+lpMaximumComponentLength], rdi
0x18006a051  lea     r8, WPP_b7e34095795c3f388dafa68a79cb47c9_Traceguids
0x18006a058  call    WPP_SF_SS
0x18006a05d  mov     ecx, [rsp+48h+NewMode]; NewMode
0x18006a061  xor     edx, edx; OldMode
0x18006a063  call    cs:__imp_RtlSetThreadErrorMode
0x18006a06a  nop     dword ptr [rax+rax+00h]
0x18006a06f  mov     rsi, [rsp+48h+arg_8]
0x18006a074  mov     eax, ebx
0x18006a076  mov     rbx, [rsp+48h+arg_0]
0x18006a07b  add     rsp, 40h
0x18006a07f  pop     rdi
0x18006a080  retn
```
