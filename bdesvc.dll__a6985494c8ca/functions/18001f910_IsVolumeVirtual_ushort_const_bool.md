# IsVolumeVirtual(ushort const *,bool *)

- ea: `0x18001f910`
- end: `0x18001fb4f`
- name: `?IsVolumeVirtual@@YAJPEBGPEA_N@Z`
- size: `575`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800053a0`
- `0x180020650`
- `0x180064328`
- `0x180066b60`
- `0x1800671d0`
- `0x180067390`

## callees

- `0x180009f60`
- `0x18001f910`
- `0x180034070`
- `0x180034500`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb0f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001fa9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001fa9c`
- `VirtDisk!GetStorageDependencyInformation` at `0x18001fac8`
- `VirtDisk!GetStorageDependencyInformation` at `0x18001fac8`

## pseudocode

```c
__int64 __fastcall IsVolumeVirtual(WCHAR *a1, bool *a2)
{
  __int64 v5; // rdx
  __int64 v6; // rax
  WCHAR *v7; // r8
  unsigned int v8; // edi
  WCHAR *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  HANDLE FileW; // rbx
  signed int StorageDependencyInformation; // eax
  ULONG SizeUsed[4]; // [rsp+40h] [rbp-288h] BYREF
  struct _STORAGE_DEPENDENCY_INFO StorageDependencyInfo; // [rsp+50h] [rbp-278h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x20Cu);
  StorageDependencyInfo.Version = STORAGE_DEPENDENCY_INFO_VERSION_2;
  memset_0(&StorageDependencyInfo.NumberEntries, 0, 0x44u);
  SizeUsed[0] = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = 262;
  v6 = 2147483646;
  v7 = FileName;
  while ( v6 && *a1 )
  {
    *v7++ = *a1++;
    --v6;
    if ( !--v5 )
      return (unsigned int)-2147024774;
  }
  *v7 = 0;
  v9 = FileName;
  v10 = 262;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v8 = -2147024809;
  if ( v10 )
  {
    v11 = 262 - v10;
    if ( v10 == 262 || v10 == 261 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          2147942487LL);
      return v8;
    }
    if ( FileName[v11 - 1] == 92 )
    {
      v12 = 2 * v11 - 2;
      if ( v12 >= 0x20C )
        _report_rangecheckfailure(v12, 0);
      *(WCHAR *)((char *)FileName + v12) = 0;
    }
    FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
    StorageDependencyInformation = GetStorageDependencyInformation(
                                     FileW,
                                     GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                     0x48u,
                                     &StorageDependencyInfo,
                                     SizeUsed);
    v8 = StorageDependencyInformation;
    if ( (unsigned int)StorageDependencyInformation <= 1 || StorageDependencyInformation == -1069940715 )
    {
      *a2 = 0;
    }
    else
    {
      if ( StorageDependencyInformation != 122 )
      {
        if ( StorageDependencyInformation > 0 )
          v8 = (unsigned __int16)StorageDependencyInformation | 0x80070000;
        goto LABEL_28;
      }
      *a2 = 1;
    }
    v8 = 0;
LABEL_28:
    if ( FileW != (HANDLE)-1LL )
      CloseHandle(FileW);
    return v8;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18001f910  mov     [rsp+arg_10], rbx
0x18001f915  mov     [rsp+arg_18], rbp
0x18001f91a  push    rsi
0x18001f91b  sub     rsp, 2C0h
0x18001f922  mov     rax, cs:__security_cookie
0x18001f929  xor     rax, rsp
0x18001f92c  mov     [rsp+2C8h+var_18], rax
0x18001f934  mov     rsi, rdx
0x18001f937  mov     rbx, rcx
0x18001f93a  xor     edx, edx; Val
0x18001f93c  lea     rcx, [rsp+2C8h+FileName]; void *
0x18001f944  mov     r8d, 20Ch; Size
0x18001f94a  call    memset_0
0x18001f94f  xor     edx, edx; Val
0x18001f951  mov     [rsp+2C8h+StorageDependencyInfo.Version], 2
0x18001f959  mov     r8d, 44h ; 'D'; Size
0x18001f95f  lea     rcx, [rsp+2C8h+StorageDependencyInfo.NumberEntries]; void *
0x18001f964  call    memset_0
0x18001f969  xor     ebp, ebp
0x18001f96b  mov     [rsp+2C8h+SizeUsed], ebp
0x18001f96f  test    rsi, rsi
0x18001f972  jnz     short loc_18001F97E
0x18001f974  mov     eax, 80004003h
0x18001f979  jmp     loc_18001FB29
0x18001f97e  mov     r9d, 106h
0x18001f984  mov     [rsi], bpl
0x18001f987  mov     edx, r9d
0x18001f98a  mov     [rsp+2C8h+arg_0], rdi
0x18001f992  mov     eax, 7FFFFFFEh
0x18001f997  lea     r8, [rsp+2C8h+FileName]
0x18001f99f  nop
0x18001f9a0  test    rax, rax
0x18001f9a3  jz      short loc_18001F9D3
0x18001f9a5  movzx   ecx, word ptr [rbx]
0x18001f9a8  test    cx, cx
0x18001f9ab  jz      short loc_18001F9C4
0x18001f9ad  mov     [r8], cx
0x18001f9b1  add     rbx, 2
0x18001f9b5  add     r8, 2
0x18001f9b9  dec     rax
0x18001f9bc  sub     rdx, 1
0x18001f9c0  jnz     short loc_18001F9A0
0x18001f9c2  jmp     short loc_18001F9C9
0x18001f9c4  test    rdx, rdx
0x18001f9c7  jnz     short loc_18001F9D3
0x18001f9c9  mov     edi, 8007007Ah
0x18001f9ce  jmp     loc_18001FB1F
0x18001f9d3  mov     [r8], bp
0x18001f9d7  lea     rax, [rsp+2C8h+FileName]
0x18001f9df  mov     rcx, r9
0x18001f9e2  cmp     [rax], bp
0x18001f9e5  jz      short loc_18001F9F1
0x18001f9e7  add     rax, 2
0x18001f9eb  sub     rcx, 1
0x18001f9ef  jnz     short loc_18001F9E2
0x18001f9f1  mov     edi, 80070057h
0x18001f9f6  test    rcx, rcx
0x18001f9f9  mov     edx, edi
0x18001f9fb  cmovnz  edx, ebp
0x18001f9fe  jz      loc_18001FB1D
0x18001fa04  sub     r9, rcx
0x18001fa07  cmp     r9, 1
0x18001fa0b  ja      short loc_18001FA4B
0x18001fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa14  lea     rax, WPP_GLOBAL_Control
0x18001fa1b  cmp     rcx, rax
0x18001fa1e  jz      loc_18001FB1F
0x18001fa24  test    byte ptr [rcx+1Ch], 40h
0x18001fa28  jz      loc_18001FB1F
0x18001fa2e  mov     rcx, [rcx+10h]
0x18001fa32  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18001fa39  mov     edx, 45h ; 'E'
0x18001fa3e  mov     r9d, edi
0x18001fa41  call    WPP_SF_d
0x18001fa46  jmp     loc_18001FB1F
0x18001fa4b  cmp     [rsp+r9*2+2C8h+var_22A], 5Ch ; '\'
0x18001fa55  jnz     short loc_18001FA74
0x18001fa57  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[r9*2]
0x18001fa5f  cmp     rcx, 20Ch
0x18001fa66  jnb     loc_18001FAEC
0x18001fa6c  mov     [rsp+rcx+2C8h+FileName], bp
0x18001fa74  mov     [rsp+2C8h+hTemplateFile], rbp; hTemplateFile
0x18001fa79  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x18001fa81  mov     [rsp+2C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001fa89  xor     r9d, r9d; lpSecurityAttributes
0x18001fa8c  xor     edx, edx; dwDesiredAccess
0x18001fa8e  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x18001fa96  mov     r8d, 3; dwShareMode
0x18001fa9c  call    cs:__imp_CreateFileW
0x18001faa3  nop     dword ptr [rax+rax+00h]
0x18001faa8  lea     r9, [rsp+2C8h+StorageDependencyInfo]; StorageDependencyInfo
0x18001faad  mov     edx, 1; Flags
0x18001fab2  mov     rbx, rax
0x18001fab5  mov     r8d, 48h ; 'H'; StorageDependencyInfoSize
0x18001fabb  lea     rax, [rsp+2C8h+SizeUsed]
0x18001fac0  mov     rcx, rbx; ObjectHandle
0x18001fac3  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; SizeUsed
0x18001fac8  call    cs:__imp_GetStorageDependencyInformation
0x18001facf  nop     dword ptr [rax+rax+00h]
0x18001fad4  mov     edi, eax
0x18001fad6  cmp     eax, 1
0x18001fad9  jbe     short loc_18001FB01
0x18001fadb  cmp     eax, 0C03A0015h
0x18001fae0  jz      short loc_18001FB01
0x18001fae2  cmp     eax, 7Ah ; 'z'
0x18001fae5  jnz     short loc_18001FAF2
0x18001fae7  mov     byte ptr [rsi], 1
0x18001faea  jmp     short loc_18001FB04
0x18001faec  call    __report_rangecheckfailure
0x18001faf2  test    eax, eax
0x18001faf4  jle     short loc_18001FB06
0x18001faf6  movzx   edi, ax
0x18001faf9  or      edi, 80070000h
0x18001faff  jmp     short loc_18001FB06
0x18001fb01  mov     [rsi], bpl
0x18001fb04  mov     edi, ebp
0x18001fb06  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001fb0a  jz      short loc_18001FB1F
0x18001fb0c  mov     rcx, rbx; hObject
0x18001fb0f  call    cs:__imp_CloseHandle
0x18001fb16  nop     dword ptr [rax+rax+00h]
0x18001fb1b  jmp     short loc_18001FB1F
0x18001fb1d  mov     edi, edx
0x18001fb1f  mov     eax, edi
0x18001fb21  mov     rdi, [rsp+2C8h+arg_0]
0x18001fb29  mov     rcx, [rsp+2C8h+var_18]
0x18001fb31  xor     rcx, rsp; StackCookie
0x18001fb34  call    __security_check_cookie
0x18001fb39  lea     r11, [rsp+2C8h+var_8]
0x18001fb41  mov     rbx, [r11+20h]
0x18001fb45  mov     rbp, [r11+28h]
0x18001fb49  mov     rsp, r11
0x18001fb4c  pop     rsi
0x18001fb4d  retn
```
