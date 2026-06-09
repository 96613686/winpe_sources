# AslDoesDirectoryExistNtPath

- ea: `0x18007fefc`
- end: `0x180080032`
- name: `AslDoesDirectoryExistNtPath`
- size: `310`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e45f8`
- `0x1800e7310`

## callees

- `0x180012920`
- `0x18007fefc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007ff42`
- `msvcrt!_wcsnicmp` at `0x18007ff42`
- `ntdll!ZwClose` at `0x18007ffe8`
- `ntdll!ZwClose` at `0x18007ffe8`
- `ntdll!ZwOpenFile` at `0x18007ffda`
- `ntdll!ZwOpenFile` at `0x18007ffda`
- `ntdll!RtlInitUnicodeString` at `0x18007ff91`
- `ntdll!RtlInitUnicodeString` at `0x18007ff91`
- `ntdll!RtlFreeUnicodeString` at `0x180080015`
- `ntdll!RtlFreeUnicodeString` at `0x180080015`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007ff59`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007ff59`

## string_xrefs

- `0x18007ff67`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18007ff79`: `AslDoesDirectoryExistNtPath`

## pseudocode

```c
__int64 __fastcall AslDoesDirectoryExistNtPath(PCWSTR SourceString)
{
  unsigned int v2; // esi
  int v3; // eax
  NTSTATUS v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  FileHandle = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = 0;
  IoStatusBlock = 0;
  if ( _wcsnicmp(SourceString, L"\\SystemRoot\\", 0xCu) )
  {
    v3 = RtlDosPathNameToNtPathName_U_WithStatus(SourceString, &DestinationString, 0, 0);
    if ( v3 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslDoesDirectoryExistNtPath",
        554,
        (unsigned int)"RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]",
        SourceString,
        v3,
        *(_QWORD *)&DestinationString.Length);
      goto LABEL_10;
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v4 >= 0 )
  {
    ZwClose(FileHandle);
LABEL_9:
    v2 = 1;
    goto LABEL_10;
  }
  if ( v4 == -1073741790 || v4 == -1073741757 )
    goto LABEL_9;
LABEL_10:
  if ( DestinationString.Buffer != SourceString && DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v2;
}

```

## disassembly

```asm
0x18007fefc  mov     [rsp-8+arg_8], rsi
0x18007ff01  mov     [rsp-8+arg_10], rdi
0x18007ff06  push    rbp
0x18007ff07  mov     rbp, rsp
0x18007ff0a  sub     rsp, 80h
0x18007ff11  xor     eax, eax
0x18007ff13  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x18007ff1a  xorps   xmm0, xmm0
0x18007ff1d  mov     qword ptr [rbp+DestinationString.Length], rax
0x18007ff21  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007ff25  mov     rdi, rcx
0x18007ff28  mov     [rbp+FileHandle], rax
0x18007ff2c  lea     r8d, [rax+0Ch]; MaxCount
0x18007ff30  mov     [rbp+DestinationString.Buffer], rax
0x18007ff34  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007ff38  xor     esi, esi
0x18007ff3a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18007ff3e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18007ff42  call    cs:__imp__wcsnicmp
0x18007ff48  test    eax, eax
0x18007ff4a  jz      short loc_18007FF8A
0x18007ff4c  xor     r9d, r9d
0x18007ff4f  lea     rdx, [rbp+DestinationString]
0x18007ff53  xor     r8d, r8d
0x18007ff56  mov     rcx, rdi
0x18007ff59  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18007ff5f  test    eax, eax
0x18007ff61  jns     short loc_18007FF97
0x18007ff63  mov     [rsp+80h+OpenOptions], eax
0x18007ff67  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18007ff6e  mov     r8d, 22Ah
0x18007ff74  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x18007ff79  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x18007ff80  lea     ecx, [rsi+1]
0x18007ff83  call    AslLogCallPrintf
0x18007ff88  jmp     short loc_180080003
0x18007ff8a  mov     rdx, rdi; SourceString
0x18007ff8d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007ff91  call    cs:__imp_RtlInitUnicodeString
0x18007ff97  lea     rax, [rbp+DestinationString]
0x18007ff9b  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x18007ffa3  xorps   xmm0, xmm0
0x18007ffa6  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007ffaa  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18007ffae  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007ffb5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007ffb9  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18007ffbd  mov     edx, 100080h; DesiredAccess
0x18007ffc2  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007ffc9  lea     rcx, [rbp+FileHandle]; FileHandle
0x18007ffcd  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x18007ffd5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007ffda  call    cs:__imp_ZwOpenFile
0x18007ffe0  test    eax, eax
0x18007ffe2  js      short loc_18007FFF0
0x18007ffe4  mov     rcx, [rbp+FileHandle]; Handle
0x18007ffe8  call    cs:__imp_ZwClose
0x18007ffee  jmp     short loc_18007FFFE
0x18007fff0  cmp     eax, 0C0000022h
0x18007fff5  jz      short loc_18007FFFE
0x18007fff7  cmp     eax, 0C0000043h
0x18007fffc  jnz     short loc_180080003
0x18007fffe  mov     esi, 1
0x180080003  mov     rcx, [rbp+DestinationString.Buffer]
0x180080007  cmp     rcx, rdi
0x18008000a  jz      short loc_18008001B
0x18008000c  test    rcx, rcx
0x18008000f  jz      short loc_18008001B
0x180080011  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180080015  call    cs:__imp_RtlFreeUnicodeString
0x18008001b  lea     r11, [rsp+80h+var_s0]
0x180080023  mov     eax, esi
0x180080025  mov     rsi, [r11+18h]
0x180080029  mov     rdi, [r11+20h]
0x18008002d  mov     rsp, r11
0x180080030  pop     rbp
0x180080031  retn
```
