# BiLoadHive

- ea: `0x14001f570`
- end: `0x14001f979`
- name: `BiLoadHive`
- size: `1033`
- prototype: `__int64 __fastcall(PCWSTR SourceString, __int64, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001af00`

## callees

- `0x1400133e4`
- `0x14001f570`
- `0x14001fb48`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `ntdll!ZwQueryAttributesFile` at `0x14001f6a7`
- `ntdll!ZwQueryAttributesFile` at `0x14001f6a7`
- `ntdll!ZwClose` at `0x14001f8fe`
- `ntdll!ZwClose` at `0x14001f8fe`
- `ntdll!ZwLoadKey` at `0x14001f843`
- `ntdll!ZwLoadKey` at `0x14001f843`
- `ntdll!ZwUnloadKey` at `0x14001f8bf`
- `ntdll!ZwUnloadKey` at `0x14001f8bf`
- `ntdll!ZwOpenKey` at `0x14001f89b`
- `ntdll!ZwOpenKey` at `0x14001f89b`
- `ntdll!RtlInitUnicodeString` at `0x14001f657`
- `ntdll!RtlInitUnicodeString` at `0x14001f714`
- `ntdll!RtlInitUnicodeString` at `0x14001f755`
- `ntdll!RtlInitUnicodeString` at `0x14001f657`
- `ntdll!RtlInitUnicodeString` at `0x14001f714`
- `ntdll!RtlInitUnicodeString` at `0x14001f755`

## string_xrefs

- `0x14001f6ce`: `\Registry\Machine`
- `0x14001f6e9`: `\Registry\Machine`
- `0x14001f7b5`: `\Registry\Machine`
- `0x14001f6f0`: `Failed open key %ws. Status: %x`
- `0x14001f8dc`: `Failed open newly loaded key %ws. Flags: 0x%x Status: %x`

## pseudocode

```c
__int64 __fastcall BiLoadHive(PCWSTR SourceString, __int64 a2, void **a3)
{
  unsigned int i; // esi
  HANDLE v5; // rdi
  const WCHAR *v6; // r13
  int v7; // eax
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-168h]
  __int64 v13; // [rsp+28h] [rbp-160h]
  __int64 v14; // [rsp+30h] [rbp-158h]
  HANDLE Handle; // [rsp+38h] [rbp-150h] BYREF
  __int64 v16; // [rsp+40h] [rbp-148h] BYREF
  __int64 v17; // [rsp+48h] [rbp-140h]
  PHANDLE KeyHandle; // [rsp+50h] [rbp-138h]
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+58h] [rbp-130h] BYREF
  PCWSTR v20; // [rsp+88h] [rbp-100h]
  __int64 v21; // [rsp+90h] [rbp-F8h]
  void **v22; // [rsp+98h] [rbp-F0h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+A0h] [rbp-E8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp-88h] BYREF
  struct _UNICODE_STRING v26; // [rsp+110h] [rbp-78h] BYREF
  struct _UNICODE_STRING v27; // [rsp+120h] [rbp-68h] BYREF
  struct _FILE_BASIC_INFORMATION FileInformation; // [rsp+130h] [rbp-58h] BYREF

  KeyHandle = a3;
  v17 = a2;
  v20 = SourceString;
  v21 = a2;
  v22 = a3;
  memset(&FileObjectAttributes, 0, 44);
  memset(&KeyObjectAttributes, 0, 44);
  v16 = 0;
  v27 = 0;
  v26 = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 0;
    Handle = 0;
    memset(&ObjectAttributes, 0, 44);
    memset(&FileInformation, 0, sizeof(FileInformation));
    DestinationString = 0;
    v6 = (const WCHAR *)(a2 + 12);
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(a2 + 12));
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwQueryAttributesFile(&ObjectAttributes, &FileInformation) < 0 || (FileInformation.FileAttributes & 0x10) != 0 )
    {
      v8 = -1073741809;
    }
    else
    {
      v7 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, &Handle);
      v8 = v7;
      if ( v7 >= 0 )
      {
        RtlInitUnicodeString(&v26, SourceString);
        KeyObjectAttributes.Length = 48;
        v5 = Handle;
        KeyObjectAttributes.RootDirectory = Handle;
        KeyObjectAttributes.Attributes = 64;
        KeyObjectAttributes.ObjectName = &v26;
        *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
        RtlInitUnicodeString(&v27, v6);
        FileObjectAttributes.Length = 48;
        FileObjectAttributes.RootDirectory = 0;
        FileObjectAttributes.Attributes = 64;
        FileObjectAttributes.ObjectName = &v27;
        *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
        v9 = BiAcquirePrivilege(0x12u, (__int64)&v16);
        v8 = v9;
        if ( v9 >= 0 )
        {
          Handle = 0;
          v8 = BiLookupNtdllProcedureAddress("ZwLoadKey2");
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                   &KeyObjectAttributes,
                   &FileObjectAttributes,
                   6016);
            if ( v8 < 0 )
              v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                     &KeyObjectAttributes,
                     &FileObjectAttributes,
                     4992);
          }
          if ( v8 < 0 )
            v8 = ZwLoadKey(&KeyObjectAttributes, &FileObjectAttributes);
          BiReleasePrivilege(&v16);
          if ( v8 >= 0 )
          {
            v8 = ZwOpenKey(KeyHandle, 0x20019u, &KeyObjectAttributes);
            if ( v8 < 0 )
            {
              BiAcquirePrivilege(0x11u, (__int64)&v16);
              ZwUnloadKey(&KeyObjectAttributes);
              BiReleasePrivilege(&v16);
              LODWORD(v12) = v8;
              BiLogMessage(4, L"Failed open newly loaded key %ws. Flags: 0x%x Status: %x", SourceString, 64, v12);
            }
          }
          else
          {
            LODWORD(v14) = v8;
            v10 = 2;
            if ( v8 != -1073741790 )
              v10 = 4;
            LODWORD(v13) = v8;
            BiLogMessage(v10, L"Failed load key %ws. Flags: 0x%x File: %s Status: %x", SourceString, 64, v6, v13, v14);
          }
        }
        else
        {
          BiLogMessage(
            4,
            L"Failed to acquire permissions to load hive. Status: %x",
            L"\\Registry\\Machine",
            (unsigned int)v9);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed open key %ws. Status: %x", L"\\Registry\\Machine", (unsigned int)v7);
        v5 = Handle;
      }
    }
    if ( v5 )
      ZwClose(v5);
    if ( v8 != -1073741443 )
      break;
    __debugbreak();
    a2 = v17;
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001f570  mov     r11, rsp
0x14001f573  mov     [r11+20h], rbx
0x14001f577  push    rsi
0x14001f578  push    rdi
0x14001f579  push    r12
0x14001f57b  push    r13
0x14001f57d  push    r14
0x14001f57f  sub     rsp, 160h
0x14001f586  mov     rax, cs:__security_cookie
0x14001f58d  xor     rax, rsp
0x14001f590  mov     [rsp+188h+var_30], rax
0x14001f598  mov     rax, r8
0x14001f59b  mov     [rsp+188h+KeyHandle], rax
0x14001f5a0  mov     [rsp+188h+var_140], rdx
0x14001f5a5  mov     r12, rcx
0x14001f5a8  mov     [rsp+188h+var_100], rcx
0x14001f5b0  mov     [rsp+188h+var_F8], rdx
0x14001f5b8  mov     [rsp+188h+var_F0], rax
0x14001f5c0  xor     eax, eax
0x14001f5c2  xorps   xmm0, xmm0
0x14001f5c5  movups  xmmword ptr [rsp+188h+FileObjectAttributes.Length], xmm0
0x14001f5cd  movups  xmmword ptr [rsp+188h+FileObjectAttributes.ObjectName], xmm0
0x14001f5d5  movups  xmmword ptr [rsp+188h+FileObjectAttributes+1Ch], xmm0
0x14001f5dd  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.Length], xmm0
0x14001f5e2  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.ObjectName], xmm0
0x14001f5e7  movups  xmmword ptr [rsp+188h+KeyObjectAttributes+1Ch], xmm0
0x14001f5ec  mov     [rsp+188h+var_148], rax
0x14001f5f1  movups  xmmword ptr [r11-68h], xmm0
0x14001f5f6  xorps   xmm1, xmm1
0x14001f5f9  movups  xmmword ptr [r11-78h], xmm1
0x14001f5fe  xor     esi, esi
0x14001f600  lea     r14d, [rax+4]
0x14001f604  xor     edi, edi
0x14001f606  mov     [rsp+188h+Handle], rdi
0x14001f60b  xor     eax, eax
0x14001f60d  xorps   xmm0, xmm0
0x14001f610  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x14001f618  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x14001f620  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x14001f628  movups  xmmword ptr [rsp+188h+FileInformation.CreationTime], xmm0
0x14001f630  movups  xmmword ptr [rsp+188h+FileInformation.LastWriteTime], xmm0
0x14001f638  mov     qword ptr [rsp+188h+FileInformation.FileAttributes], rax
0x14001f640  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x14001f648  lea     r13, [rdx+0Ch]
0x14001f64c  mov     rdx, r13; SourceString
0x14001f64f  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x14001f657  call    cs:__imp_RtlInitUnicodeString
0x14001f65d  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x14001f668  mov     [rsp+188h+ObjectAttributes.RootDirectory], rdi
0x14001f670  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x14001f67b  lea     rax, [rsp+188h+DestinationString]
0x14001f683  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x14001f68b  xorps   xmm0, xmm0
0x14001f68e  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f697  lea     rdx, [rsp+188h+FileInformation]; FileInformation
0x14001f69f  lea     rcx, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x14001f6a7  call    cs:__imp_ZwQueryAttributesFile
0x14001f6ad  test    eax, eax
0x14001f6af  js      loc_14001F8ED
0x14001f6b5  test    byte ptr [rsp+188h+FileInformation.FileAttributes], 10h
0x14001f6bd  jnz     loc_14001F8ED
0x14001f6c3  lea     r9, [rsp+188h+Handle]
0x14001f6c8  mov     r8d, 0F003Fh
0x14001f6ce  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x14001f6d5  xor     ecx, ecx
0x14001f6d7  call    BiOpenKeyNonBcd
0x14001f6dc  mov     ebx, eax
0x14001f6de  mov     dword ptr [rsp+188h+var_158], eax
0x14001f6e2  test    eax, eax
0x14001f6e4  jns     short loc_14001F709
0x14001f6e6  mov     r9d, eax
0x14001f6e9  lea     r8, aRegistryMachin_2; "\\Registry\\Machine"
0x14001f6f0  lea     rdx, aFailedOpenKeyW; "Failed open key %ws. Status: %x"
0x14001f6f7  mov     ecx, r14d
0x14001f6fa  call    BiLogMessage
0x14001f6ff  mov     rdi, [rsp+188h+Handle]
0x14001f704  jmp     loc_14001F8F6
0x14001f709  mov     rdx, r12; SourceString
0x14001f70c  lea     rcx, [rsp+188h+var_78]; DestinationString
0x14001f714  call    cs:__imp_RtlInitUnicodeString
0x14001f71a  mov     [rsp+188h+KeyObjectAttributes.Length], 30h ; '0'
0x14001f722  mov     rdi, [rsp+188h+Handle]
0x14001f727  mov     [rsp+188h+KeyObjectAttributes.RootDirectory], rdi
0x14001f72c  mov     [rsp+188h+KeyObjectAttributes.Attributes], 40h ; '@'
0x14001f734  lea     rax, [rsp+188h+var_78]
0x14001f73c  mov     [rsp+188h+KeyObjectAttributes.ObjectName], rax
0x14001f741  xorps   xmm0, xmm0
0x14001f744  movdqu  xmmword ptr [rsp+188h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x14001f74a  mov     rdx, r13; SourceString
0x14001f74d  lea     rcx, [rsp+188h+var_68]; DestinationString
0x14001f755  call    cs:__imp_RtlInitUnicodeString
0x14001f75b  mov     [rsp+188h+FileObjectAttributes.Length], 30h ; '0'
0x14001f766  mov     [rsp+188h+FileObjectAttributes.RootDirectory], 0
0x14001f772  mov     [rsp+188h+FileObjectAttributes.Attributes], 40h ; '@'
0x14001f77d  lea     rax, [rsp+188h+var_68]
0x14001f785  mov     [rsp+188h+FileObjectAttributes.ObjectName], rax
0x14001f78d  xorps   xmm0, xmm0
0x14001f790  movdqu  xmmword ptr [rsp+188h+FileObjectAttributes.SecurityDescriptor], xmm0
0x14001f799  lea     rdx, [rsp+188h+var_148]
0x14001f79e  mov     ecx, 12h
0x14001f7a3  call    BiAcquirePrivilege
0x14001f7a8  mov     ebx, eax
0x14001f7aa  mov     dword ptr [rsp+188h+var_158], eax
0x14001f7ae  test    eax, eax
0x14001f7b0  jns     short loc_14001F7D0
0x14001f7b2  mov     r9d, eax
0x14001f7b5  lea     r8, aRegistryMachin_2; "\\Registry\\Machine"
0x14001f7bc  lea     rdx, aFailedToAcquir_1; "Failed to acquire permissions to load h"...
0x14001f7c3  mov     ecx, r14d
0x14001f7c6  call    BiLogMessage
0x14001f7cb  jmp     loc_14001F8F6
0x14001f7d0  mov     [rsp+188h+Handle], 0
0x14001f7d9  lea     rdx, [rsp+188h+Handle]
0x14001f7de  lea     rcx, aZwloadkey2; "ZwLoadKey2"
0x14001f7e5  call    BiLookupNtdllProcedureAddress
0x14001f7ea  mov     ebx, eax
0x14001f7ec  test    eax, eax
0x14001f7ee  js      short loc_14001F832
0x14001f7f0  mov     r8d, 1780h
0x14001f7f6  lea     rdx, [rsp+188h+FileObjectAttributes]
0x14001f7fe  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x14001f803  mov     rax, [rsp+188h+Handle]
0x14001f808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f80d  mov     ebx, eax
0x14001f80f  test    eax, eax
0x14001f811  jns     short loc_14001F832
0x14001f813  mov     r8d, 1380h
0x14001f819  lea     rdx, [rsp+188h+FileObjectAttributes]
0x14001f821  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x14001f826  mov     rax, [rsp+188h+Handle]
0x14001f82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f830  mov     ebx, eax
0x14001f832  test    ebx, ebx
0x14001f834  jns     short loc_14001F84B
0x14001f836  lea     rdx, [rsp+188h+FileObjectAttributes]; FileObjectAttributes
0x14001f83e  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x14001f843  call    cs:__imp_ZwLoadKey
0x14001f849  mov     ebx, eax
0x14001f84b  lea     rcx, [rsp+188h+var_148]
0x14001f850  call    BiReleasePrivilege
0x14001f855  test    ebx, ebx
0x14001f857  jns     short loc_14001F88C
0x14001f859  mov     dword ptr [rsp+188h+var_158], ebx
0x14001f85d  mov     ecx, 2
0x14001f862  cmp     ebx, 0C0000022h
0x14001f868  cmovnz  ecx, r14d
0x14001f86c  mov     dword ptr [rsp+188h+var_160], ebx
0x14001f870  mov     [rsp+188h+var_168], r13
0x14001f875  mov     r9d, 40h ; '@'
0x14001f87b  mov     r8, r12
0x14001f87e  lea     rdx, aFailedLoadKeyW; "Failed load key %ws. Flags: 0x%x File: "...
0x14001f885  call    BiLogMessage
0x14001f88a  jmp     short loc_14001F8F6
0x14001f88c  lea     r8, [rsp+188h+KeyObjectAttributes]; ObjectAttributes
0x14001f891  mov     edx, 20019h; DesiredAccess
0x14001f896  mov     rcx, [rsp+188h+KeyHandle]; KeyHandle
0x14001f89b  call    cs:__imp_ZwOpenKey
0x14001f8a1  mov     ebx, eax
0x14001f8a3  mov     dword ptr [rsp+188h+var_158], eax
0x14001f8a7  test    eax, eax
0x14001f8a9  jns     short loc_14001F8F6
0x14001f8ab  lea     rdx, [rsp+188h+var_148]
0x14001f8b0  mov     ecx, 11h
0x14001f8b5  call    BiAcquirePrivilege
0x14001f8ba  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x14001f8bf  call    cs:__imp_ZwUnloadKey
0x14001f8c5  lea     rcx, [rsp+188h+var_148]
0x14001f8ca  call    BiReleasePrivilege
0x14001f8cf  mov     dword ptr [rsp+188h+var_168], ebx
0x14001f8d3  mov     r9d, 40h ; '@'
0x14001f8d9  mov     r8, r12
0x14001f8dc  lea     rdx, aFailedOpenNewl; "Failed open newly loaded key %ws. Flags"...
0x14001f8e3  mov     ecx, r14d
0x14001f8e6  call    BiLogMessage
0x14001f8eb  jmp     short loc_14001F8F6
0x14001f8ed  mov     ebx, 0C000000Fh
0x14001f8f2  mov     dword ptr [rsp+188h+var_158], ebx
0x14001f8f6  test    rdi, rdi
0x14001f8f9  jz      short loc_14001F904
0x14001f8fb  mov     rcx, rdi; Handle
0x14001f8fe  call    cs:__imp_ZwClose
0x14001f904  cmp     ebx, 0C000017Dh
0x14001f90a  jnz     short loc_14001F94F
0x14001f90c  int     3; Trap to Debugger
0x14001f90d  mov     rdx, [rsp+188h+var_140]
0x14001f912  jmp     short loc_14001F943
0x14001f914  mov     esi, 5
0x14001f919  lea     r14d, [rsi-1]
0x14001f91d  mov     ebx, dword ptr [rsp+188h+var_158]
0x14001f921  mov     r12, [rsp+188h+var_100]
0x14001f929  mov     rdx, [rsp+188h+var_F8]
0x14001f931  mov     [rsp+188h+var_140], rdx
0x14001f936  mov     rax, [rsp+188h+var_F0]
0x14001f93e  mov     [rsp+188h+KeyHandle], rax
0x14001f943  cmp     esi, 5
0x14001f946  jnb     short loc_14001F94F
0x14001f948  inc     esi
0x14001f94a  jmp     loc_14001F604
0x14001f94f  mov     eax, ebx
0x14001f951  mov     rcx, [rsp+188h+var_30]
0x14001f959  xor     rcx, rsp; StackCookie
0x14001f95c  call    __security_check_cookie
0x14001f961  mov     rbx, [rsp+188h+arg_18]
0x14001f969  add     rsp, 160h
0x14001f970  pop     r14
0x14001f972  pop     r13
0x14001f974  pop     r12
0x14001f976  pop     rdi
0x14001f977  pop     rsi
0x14001f978  retn
```
