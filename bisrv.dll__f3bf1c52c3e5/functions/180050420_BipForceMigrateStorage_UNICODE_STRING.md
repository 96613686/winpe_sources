# BipForceMigrateStorage(_UNICODE_STRING *)

- ea: `0x180050420`
- end: `0x180050893`
- name: `?BipForceMigrateStorage@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800639b0`

## callees

- `0x180025a50`
- `0x1800260e8`
- `0x180049844`
- `0x180050420`
- `0x18006d5cc`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18005060d`
- `ntdll!NtCreateFile` at `0x180050735`
- `ntdll!NtCreateFile` at `0x18005060d`
- `ntdll!NtCreateFile` at `0x180050735`
- `ntdll!NtSaveKeyEx` at `0x18005077a`
- `ntdll!NtSaveKeyEx` at `0x18005077a`
- `ntdll!NtDeleteValueKey` at `0x18005080d`
- `ntdll!NtDeleteValueKey` at `0x180050835`
- `ntdll!NtDeleteValueKey` at `0x18005080d`
- `ntdll!NtDeleteValueKey` at `0x180050835`
- `ntdll!RtlAcquirePrivilege` at `0x18005075b`
- `ntdll!RtlAcquirePrivilege` at `0x18005075b`
- `ntdll!NtDeleteFile` at `0x180050662`
- `ntdll!NtDeleteFile` at `0x1800506ad`
- `ntdll!NtDeleteFile` at `0x180050662`
- `ntdll!NtDeleteFile` at `0x1800506ad`
- `ntdll!RtlReleasePrivilege` at `0x18005086f`
- `ntdll!RtlReleasePrivilege` at `0x18005086f`
- `ntdll!RtlAppendUnicodeToString` at `0x180050795`
- `ntdll!RtlAppendUnicodeToString` at `0x1800507cf`
- `ntdll!RtlAppendUnicodeToString` at `0x180050795`
- `ntdll!RtlAppendUnicodeToString` at `0x1800507cf`
- `ntdll!RtlInitUnicodeString` at `0x1800504bd`
- `ntdll!RtlInitUnicodeString` at `0x180050530`
- `ntdll!RtlInitUnicodeString` at `0x1800507fc`
- `ntdll!RtlInitUnicodeString` at `0x180050824`
- `ntdll!RtlInitUnicodeString` at `0x1800504bd`
- `ntdll!RtlInitUnicodeString` at `0x180050530`
- `ntdll!RtlInitUnicodeString` at `0x1800507fc`
- `ntdll!RtlInitUnicodeString` at `0x180050824`
- `ntdll!NtClose` at `0x180050850`
- `ntdll!NtClose` at `0x180050860`
- `ntdll!NtClose` at `0x180050850`
- `ntdll!NtClose` at `0x180050860`

## pseudocode

```c
__int64 __fastcall BipForceMigrateStorage(PCUNICODE_STRING Source)
{
  int v2; // eax
  NTSTATUS appended; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ULONG Privilege; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v8; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+C8h] [rbp-38h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp-28h] BYREF
  PVOID ReturnedState; // [rsp+E0h] [rbp-20h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  char v16; // [rsp+100h] [rbp+0h] BYREF
  char v17; // [rsp+500h] [rbp+400h] BYREF

  FileHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  *(_QWORD *)&Destination.Length = 0x4000000;
  Destination.Buffer = (PWSTR)&v16;
  *(_QWORD *)&v8.Length = 0x8000000;
  v8.Buffer = (PWSTR)&v17;
  IoStatusBlock = 0;
  Privilege = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ReturnedState = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Version");
  v2 = BipReadRegUlong(KeyHandle, &DestinationString);
  appended = v2;
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"MinorVersion");
    v2 = BipReadRegUlong(KeyHandle, &DestinationString);
    appended = v2;
    if ( v2 == -1073741772 || v2 >= 0 )
    {
      appended = BipStorageAppendToPath(Source, L"bbimigrate", &v8);
      if ( appended >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &v8;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        appended = NtCreateFile(
                     &FileHandle,
                     0x40100100u,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x80u,
                     3u,
                     3u,
                     0x21u,
                     0,
                     0);
        if ( appended >= 0 )
        {
          appended = BipStorageAppendToPath(Source, L"bbimigrate\\BBI.LOG1", &v8);
          if ( appended >= 0 )
          {
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &v8;
            ObjectAttributes.RootDirectory = 0;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            ObjectAttributes.Attributes = 64;
            NtDeleteFile(&ObjectAttributes);
            appended = BipStorageAppendToPath(Source, L"bbimigrate\\BBI.LOG2", &v8);
            if ( appended >= 0 )
            {
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &v8;
              ObjectAttributes.RootDirectory = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              ObjectAttributes.Attributes = 64;
              NtDeleteFile(&ObjectAttributes);
              appended = BipStorageAppendToPath(Source, L"bbimigrate\\BBI", &v8);
              if ( appended >= 0 )
              {
                ObjectAttributes.Length = 48;
                ObjectAttributes.RootDirectory = 0;
                ObjectAttributes.Attributes = 64;
                ObjectAttributes.ObjectName = &v8;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                appended = NtCreateFile(
                             &Handle,
                             0x40100100u,
                             &ObjectAttributes,
                             &IoStatusBlock,
                             0,
                             0x80u,
                             1u,
                             5u,
                             0x60u,
                             0,
                             0);
                if ( appended >= 0 )
                {
                  Privilege = 17;
                  appended = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
                  if ( appended >= 0 )
                  {
                    appended = NtSaveKeyEx(KeyHandle, Handle, 2u);
                    if ( appended >= 0 )
                    {
                      appended = RtlAppendUnicodeToString(&Destination, L"Events");
                      if ( appended >= 0 )
                      {
                        appended = BipDeleteKey(KeyHandle, &Destination);
                        if ( appended >= 0 )
                        {
                          Destination.Length = 0;
                          appended = RtlAppendUnicodeToString(&Destination, L"WorkItems");
                          if ( appended >= 0 )
                          {
                            appended = BipDeleteKey(KeyHandle, &Destination);
                            if ( appended >= 0 )
                            {
                              RtlInitUnicodeString(&DestinationString, L"Version");
                              appended = NtDeleteValueKey(KeyHandle, &DestinationString);
                              if ( appended >= 0 )
                              {
                                RtlInitUnicodeString(&DestinationString, L"MinorVersion");
                                appended = NtDeleteValueKey(KeyHandle, &DestinationString);
                                if ( appended == -1073741772 )
                                  appended = 0;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 43;
        goto LABEL_7;
      }
    }
  }
  else
  {
    if ( v2 == -1073741772 )
    {
      appended = 0;
      goto LABEL_28;
    }
    v4 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 42;
LABEL_7:
      WPP_SF_d(v4[2], v5, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids, (unsigned int)v2);
    }
  }
LABEL_28:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180050420  push    rbp
0x180050422  push    rbx
0x180050423  push    rsi
0x180050424  push    r14
0x180050426  lea     rbp, [rsp-0C18h]
0x18005042e  sub     rsp, 0D18h
0x180050435  mov     rax, cs:__security_cookie
0x18005043c  xor     rax, rsp
0x18005043f  mov     [rbp+0C30h+var_30], rax
0x180050446  xorps   xmm0, xmm0
0x180050449  lea     rdx, aVersion; "Version"
0x180050450  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050454  xor     r14d, r14d
0x180050457  mov     [rbp+0C30h+FileHandle], rax
0x18005045b  mov     rsi, rcx
0x18005045e  mov     [rbp+0C30h+Handle], rax
0x180050462  lea     rcx, [rbp+0C30h+DestinationString]; DestinationString
0x180050466  movups  xmmword ptr [rbp+0C30h+Destination.Length], xmm0
0x18005046a  mov     eax, 400h
0x18005046f  mov     [rsp+0D30h+var_CCC], r14d
0x180050474  mov     [rbp+0C30h+Destination.MaximumLength], ax
0x180050478  lea     rax, [rbp+0C30h+var_C30]
0x18005047c  mov     [rbp+0C30h+Destination.Buffer], rax
0x180050480  mov     eax, 800h
0x180050485  movups  xmmword ptr [rsp+0D30h+var_CC0.Length], xmm0
0x18005048a  mov     [rsp+0D30h+var_CC0.MaximumLength], ax
0x18005048f  lea     rax, [rbp+0C30h+var_830]
0x180050496  mov     [rsp+0D30h+var_CC0.Buffer], rax
0x18005049b  movups  xmmword ptr [rbp+0C30h+IoStatusBlock], xmm0
0x18005049f  mov     [rsp+0D30h+Privilege], r14d
0x1800504a4  movups  xmmword ptr [rbp+0C30h+ObjectAttributes.Length], xmm0
0x1800504a8  mov     [rsp+0D30h+var_CD0], r14d
0x1800504ad  movups  xmmword ptr [rbp+0C30h+ObjectAttributes.ObjectName], xmm0
0x1800504b1  mov     [rbp+0C30h+ReturnedState], r14
0x1800504b5  movups  xmmword ptr [rbp+0C30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800504b9  movups  xmmword ptr [rbp+0C30h+DestinationString.Length], xmm0
0x1800504bd  call    cs:__imp_RtlInitUnicodeString
0x1800504c3  mov     rcx, cs:KeyHandle; KeyHandle
0x1800504ca  lea     r8, [rsp+0D30h+var_CD0]
0x1800504cf  lea     rdx, [rbp+0C30h+DestinationString]; ValueName
0x1800504d3  call    BipReadRegUlong
0x1800504d8  mov     ebx, eax
0x1800504da  test    eax, eax
0x1800504dc  jns     short loc_180050525
0x1800504de  cmp     eax, 0C0000034h
0x1800504e3  jnz     short loc_1800504ED
0x1800504e5  mov     ebx, r14d
0x1800504e8  jmp     loc_180050846
0x1800504ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504f4  test    byte ptr [rcx+1Ch], 8
0x1800504f8  jz      loc_180050846
0x1800504fe  cmp     byte ptr [rcx+19h], 2
0x180050502  jb      loc_180050846
0x180050508  mov     edx, 2Ah ; '*'
0x18005050d  mov     rcx, [rcx+10h]
0x180050511  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180050518  mov     r9d, eax
0x18005051b  call    WPP_SF_d
0x180050520  jmp     loc_180050846
0x180050525  lea     rdx, aMinorversion; "MinorVersion"
0x18005052c  lea     rcx, [rbp+0C30h+DestinationString]; DestinationString
0x180050530  call    cs:__imp_RtlInitUnicodeString
0x180050536  mov     rcx, cs:KeyHandle; KeyHandle
0x18005053d  lea     r8, [rsp+0D30h+var_CCC]
0x180050542  lea     rdx, [rbp+0C30h+DestinationString]; ValueName
0x180050546  call    BipReadRegUlong
0x18005054b  mov     ebx, eax
0x18005054d  cmp     eax, 0C0000034h
0x180050552  jz      short loc_18005058C
0x180050554  test    eax, eax
0x180050556  jns     short loc_18005057A
0x180050558  mov     rcx, cs:WPP_GLOBAL_Control
0x18005055f  test    byte ptr [rcx+1Ch], 8
0x180050563  jz      loc_180050846
0x180050569  cmp     byte ptr [rcx+19h], 2
0x18005056d  jb      loc_180050846
0x180050573  mov     edx, 2Bh ; '+'
0x180050578  jmp     short loc_18005050D
0x18005057a  cmp     [rsp+0D30h+var_CD0], 3
0x18005057f  jnz     short loc_18005058C
0x180050581  cmp     [rsp+0D30h+var_CCC], 2
0x180050586  jz      loc_180050846
0x18005058c  lea     r8, [rsp+0D30h+var_CC0]; Destination
0x180050591  mov     rcx, rsi; Source
0x180050594  lea     rdx, aBbimigrate; "bbimigrate"
0x18005059b  call    BipStorageAppendToPath
0x1800505a0  mov     ebx, eax
0x1800505a2  test    eax, eax
0x1800505a4  js      loc_180050846
0x1800505aa  mov     [rsp+0D30h+EaLength], r14d; EaLength
0x1800505af  lea     rax, [rsp+0D30h+var_CC0]
0x1800505b4  mov     [rsp+0D30h+EaBuffer], r14; EaBuffer
0x1800505b9  lea     r9, [rbp+0C30h+IoStatusBlock]; IoStatusBlock
0x1800505bd  mov     [rsp+0D30h+CreateOptions], 21h ; '!'; CreateOptions
0x1800505c5  lea     r8, [rbp+0C30h+ObjectAttributes]; ObjectAttributes
0x1800505c9  mov     [rsp+0D30h+CreateDisposition], 3; CreateDisposition
0x1800505d1  lea     rcx, [rbp+0C30h+FileHandle]; FileHandle
0x1800505d5  mov     [rsp+0D30h+ShareAccess], 3; ShareAccess
0x1800505dd  xorps   xmm0, xmm0
0x1800505e0  mov     [rsp+0D30h+FileAttributes], 80h; FileAttributes
0x1800505e8  mov     edx, 40100100h; DesiredAccess
0x1800505ed  mov     [rsp+0D30h+AllocationSize], r14; AllocationSize
0x1800505f2  mov     [rbp+0C30h+ObjectAttributes.Length], 30h ; '0'
0x1800505f9  mov     [rbp+0C30h+ObjectAttributes.RootDirectory], r14
0x1800505fd  mov     [rbp+0C30h+ObjectAttributes.Attributes], 40h ; '@'
0x180050604  mov     [rbp+0C30h+ObjectAttributes.ObjectName], rax
0x180050608  movdqu  xmmword ptr [rbp+0C30h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005060d  call    cs:__imp_NtCreateFile
0x180050613  mov     ebx, eax
0x180050615  test    eax, eax
0x180050617  js      loc_180050846
0x18005061d  lea     r8, [rsp+0D30h+var_CC0]; Destination
0x180050622  mov     rcx, rsi; Source
0x180050625  lea     rdx, aBbimigrateBbiL; "bbimigrate\\BBI.LOG1"
0x18005062c  call    BipStorageAppendToPath
0x180050631  mov     ebx, eax
0x180050633  test    eax, eax
0x180050635  js      loc_180050846
0x18005063b  lea     rax, [rsp+0D30h+var_CC0]
0x180050640  mov     [rbp+0C30h+ObjectAttributes.Length], 30h ; '0'
0x180050647  xorps   xmm0, xmm0
0x18005064a  mov     [rbp+0C30h+ObjectAttributes.ObjectName], rax
0x18005064e  lea     rcx, [rbp+0C30h+ObjectAttributes]; ObjectAttributes
0x180050652  mov     [rbp+0C30h+ObjectAttributes.RootDirectory], r14
0x180050656  movdqu  xmmword ptr [rbp+0C30h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005065b  mov     [rbp+0C30h+ObjectAttributes.Attributes], 40h ; '@'
0x180050662  call    cs:__imp_NtDeleteFile
0x180050668  lea     r8, [rsp+0D30h+var_CC0]; Destination
0x18005066d  mov     rcx, rsi; Source
0x180050670  lea     rdx, aBbimigrateBbiL_0; "bbimigrate\\BBI.LOG2"
0x180050677  call    BipStorageAppendToPath
0x18005067c  mov     ebx, eax
0x18005067e  test    eax, eax
0x180050680  js      loc_180050846
0x180050686  lea     rax, [rsp+0D30h+var_CC0]
0x18005068b  mov     [rbp+0C30h+ObjectAttributes.Length], 30h ; '0'
0x180050692  xorps   xmm0, xmm0
0x180050695  mov     [rbp+0C30h+ObjectAttributes.ObjectName], rax
0x180050699  lea     rcx, [rbp+0C30h+ObjectAttributes]; ObjectAttributes
0x18005069d  mov     [rbp+0C30h+ObjectAttributes.RootDirectory], r14
0x1800506a1  movdqu  xmmword ptr [rbp+0C30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800506a6  mov     [rbp+0C30h+ObjectAttributes.Attributes], 40h ; '@'
0x1800506ad  call    cs:__imp_NtDeleteFile
0x1800506b3  lea     r8, [rsp+0D30h+var_CC0]; Destination
0x1800506b8  mov     rcx, rsi; Source
0x1800506bb  lea     rdx, aBbimigrateBbi; "bbimigrate\\BBI"
0x1800506c2  call    BipStorageAppendToPath
0x1800506c7  mov     ebx, eax
0x1800506c9  test    eax, eax
0x1800506cb  js      loc_180050846
0x1800506d1  mov     [rsp+0D30h+EaLength], r14d; EaLength
0x1800506d6  lea     rax, [rsp+0D30h+var_CC0]
0x1800506db  mov     [rsp+0D30h+EaBuffer], r14; EaBuffer
0x1800506e0  lea     r9, [rbp+0C30h+IoStatusBlock]; IoStatusBlock
0x1800506e4  mov     [rsp+0D30h+CreateOptions], 60h ; '`'; CreateOptions
0x1800506ec  lea     r8, [rbp+0C30h+ObjectAttributes]; ObjectAttributes
0x1800506f0  mov     [rsp+0D30h+CreateDisposition], 5; CreateDisposition
0x1800506f8  lea     rcx, [rbp+0C30h+Handle]; FileHandle
0x1800506fc  xorps   xmm0, xmm0
0x1800506ff  mov     [rbp+0C30h+ObjectAttributes.Length], 30h ; '0'
0x180050706  mov     esi, 1
0x18005070b  mov     [rbp+0C30h+ObjectAttributes.RootDirectory], r14
0x18005070f  mov     [rsp+0D30h+ShareAccess], esi; ShareAccess
0x180050713  mov     edx, 40100100h; DesiredAccess
0x180050718  mov     [rsp+0D30h+FileAttributes], 80h; FileAttributes
0x180050720  mov     [rsp+0D30h+AllocationSize], r14; AllocationSize
0x180050725  mov     [rbp+0C30h+ObjectAttributes.Attributes], 40h ; '@'
0x18005072c  mov     [rbp+0C30h+ObjectAttributes.ObjectName], rax
0x180050730  movdqu  xmmword ptr [rbp+0C30h+ObjectAttributes.SecurityDescriptor], xmm0
0x180050735  call    cs:__imp_NtCreateFile
0x18005073b  mov     ebx, eax
0x18005073d  test    eax, eax
0x18005073f  js      loc_180050846
0x180050745  lea     r9, [rbp+0C30h+ReturnedState]; ReturnedState
0x180050749  mov     [rsp+0D30h+Privilege], 11h
0x180050751  xor     r8d, r8d; Flags
0x180050754  lea     rcx, [rsp+0D30h+Privilege]; Privilege
0x180050759  mov     edx, esi; NumPriv
0x18005075b  call    cs:__imp_RtlAcquirePrivilege
0x180050761  mov     ebx, eax
0x180050763  test    eax, eax
0x180050765  js      loc_180050846
0x18005076b  mov     rdx, [rbp+0C30h+Handle]; FileHandle
0x18005076f  lea     r8d, [rsi+1]; Flags
0x180050773  mov     rcx, cs:KeyHandle; KeyHandle
0x18005077a  call    cs:__imp_NtSaveKeyEx
0x180050780  mov     ebx, eax
0x180050782  test    eax, eax
0x180050784  js      loc_180050846
0x18005078a  lea     rdx, Source; "Events"
0x180050791  lea     rcx, [rbp+0C30h+Destination]; Destination
0x180050795  call    cs:__imp_RtlAppendUnicodeToString
0x18005079b  mov     ebx, eax
0x18005079d  test    eax, eax
0x18005079f  js      loc_180050846
0x1800507a5  mov     rcx, cs:KeyHandle
0x1800507ac  lea     rdx, [rbp+0C30h+Destination]
0x1800507b0  call    BipDeleteKey
0x1800507b5  mov     ebx, eax
0x1800507b7  test    eax, eax
0x1800507b9  js      loc_180050846
0x1800507bf  lea     rdx, aWorkitems; "WorkItems"
0x1800507c6  mov     [rbp+0C30h+Destination.Length], r14w
0x1800507cb  lea     rcx, [rbp+0C30h+Destination]; Destination
0x1800507cf  call    cs:__imp_RtlAppendUnicodeToString
0x1800507d5  mov     ebx, eax
0x1800507d7  test    eax, eax
0x1800507d9  js      short loc_180050846
0x1800507db  mov     rcx, cs:KeyHandle
0x1800507e2  lea     rdx, [rbp+0C30h+Destination]
0x1800507e6  call    BipDeleteKey
0x1800507eb  mov     ebx, eax
0x1800507ed  test    eax, eax
0x1800507ef  js      short loc_180050846
0x1800507f1  lea     rdx, aVersion; "Version"
0x1800507f8  lea     rcx, [rbp+0C30h+DestinationString]; DestinationString
0x1800507fc  call    cs:__imp_RtlInitUnicodeString
0x180050802  mov     rcx, cs:KeyHandle; KeyHandle
0x180050809  lea     rdx, [rbp+0C30h+DestinationString]; ValueName
0x18005080d  call    cs:__imp_NtDeleteValueKey
0x180050813  mov     ebx, eax
0x180050815  test    eax, eax
0x180050817  js      short loc_180050846
0x180050819  lea     rdx, aMinorversion; "MinorVersion"
0x180050820  lea     rcx, [rbp+0C30h+DestinationString]; DestinationString
0x180050824  call    cs:__imp_RtlInitUnicodeString
0x18005082a  mov     rcx, cs:KeyHandle; KeyHandle
0x180050831  lea     rdx, [rbp+0C30h+DestinationString]; ValueName
0x180050835  call    cs:__imp_NtDeleteValueKey
0x18005083b  cmp     eax, 0C0000034h
0x180050840  mov     ebx, eax
0x180050842  cmovz   ebx, r14d
0x180050846  mov     rcx, [rbp+0C30h+FileHandle]; Handle
0x18005084a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005084e  jz      short loc_180050856
0x180050850  call    cs:__imp_NtClose
0x180050856  mov     rcx, [rbp+0C30h+Handle]; Handle
0x18005085a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005085e  jz      short loc_180050866
0x180050860  call    cs:__imp_NtClose
0x180050866  mov     rcx, [rbp+0C30h+ReturnedState]; ReturnedState
0x18005086a  test    rcx, rcx
0x18005086d  jz      short loc_180050875
0x18005086f  call    cs:__imp_RtlReleasePrivilege
0x180050875  mov     eax, ebx
0x180050877  mov     rcx, [rbp+0C30h+var_30]
0x18005087e  xor     rcx, rsp; StackCookie
0x180050881  call    __security_check_cookie
0x180050886  add     rsp, 0D18h
0x18005088d  pop     r14
0x18005088f  pop     rsi
0x180050890  pop     rbx
0x180050891  pop     rbp
0x180050892  retn
```
