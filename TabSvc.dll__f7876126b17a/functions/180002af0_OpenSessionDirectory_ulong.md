# _OpenSessionDirectory(ulong)

- ea: `0x180002af0`
- end: `0x180002cc1`
- name: `?_OpenSessionDirectory@@YAPEAXK@Z`
- size: `465`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002940`
- `0x18002e484`

## callees

- `0x180002af0`
- `0x1800037d0`
- `0x18001bbe0`
- `0x18001c684`
- `0x18002b404`
- `0x18002b4cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002b95`
- `ntdll!RtlInitUnicodeString` at `0x180002b95`
- `ntdll!NtOpenDirectoryObject` at `0x180002bce`
- `ntdll!NtOpenDirectoryObject` at `0x180002bce`

## string_xrefs

- `0x180002c62`: `PENSERVICE__OpenSessionDirectory`
- `0x180002c98`: `PENSERVICE__OpenSessionDirectory`

## pseudocode

```c
void *__fastcall _OpenSessionDirectory(unsigned int a1)
{
  __int64 v2; // rdx
  NTSTATUS v3; // eax
  __int64 v5; // rax
  const wchar_t *v6; // r8
  WCHAR *v7; // r9
  WCHAR *v8; // rcx
  void *FileHandle; // [rsp+30h] [rbp-278h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-270h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-260h] BYREF
  WCHAR SourceString[264]; // [rsp+80h] [rbp-228h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(SourceString, 0, 0x208u);
  v2 = 260;
  if ( a1 )
  {
    StringCchPrintfW(SourceString, 0x104u, L"\\Sessions\\%d\\BaseNamedObjects", a1);
  }
  else
  {
    v5 = 2147483646;
    v6 = L"\\BaseNamedObjects";
    v7 = SourceString;
    do
    {
      if ( !v5 )
        break;
      if ( !*v6 )
        break;
      *v7++ = *v6++;
      --v5;
      --v2;
    }
    while ( v2 );
    v8 = v7 - 1;
    if ( v2 )
      v8 = v7;
    *v8 = 0;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sS(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      10,
      (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      (unsigned int)"PENSERVICE__OpenSessionDirectory",
      (__int64)SourceString);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenDirectoryObject(&FileHandle, 4u, &ObjectAttributes);
  if ( v3 >= 0 )
    return FileHandle;
  FileHandle = 0;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      11,
      (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      (unsigned int)"PENSERVICE__OpenSessionDirectory",
      v3);
    return FileHandle;
  }
  return 0;
}

```

## disassembly

```asm
0x180002af0  mov     [rsp+arg_8], rbx
0x180002af5  push    rdi
0x180002af6  sub     rsp, 2A0h
0x180002afd  mov     rax, cs:__security_cookie
0x180002b04  xor     rax, rsp
0x180002b07  mov     [rsp+2A8h+var_18], rax
0x180002b0f  xorps   xmm0, xmm0
0x180002b12  mov     ebx, ecx
0x180002b14  xor     edi, edi
0x180002b16  lea     rcx, [rsp+2A8h+SourceString]; void *
0x180002b1e  xor     edx, edx; Val
0x180002b20  mov     [rsp+2A8h+FileHandle], rdi
0x180002b25  mov     r8d, 208h; Size
0x180002b2b  movups  xmmword ptr [rsp+2A8h+ObjectAttributes.Length], xmm0
0x180002b30  movups  xmmword ptr [rsp+2A8h+ObjectAttributes.ObjectName], xmm0
0x180002b35  movups  xmmword ptr [rsp+2A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002b3a  call    memset_0
0x180002b3f  mov     edx, 104h; unsigned __int64
0x180002b44  test    ebx, ebx
0x180002b46  jz      loc_180002C02
0x180002b4c  mov     r9d, ebx
0x180002b4f  lea     r8, aSessionsDBasen; "\\Sessions\\%d\\BaseNamedObjects"
0x180002b56  lea     rcx, [rsp+2A8h+SourceString]; unsigned __int16 *
0x180002b5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b6a  lea     rbx, WPP_GLOBAL_Control
0x180002b71  cmp     rcx, rbx
0x180002b74  jz      short loc_180002B80
0x180002b76  test    byte ptr [rcx+1Ch], 10h
0x180002b7a  jnz     loc_180002C4C
0x180002b80  xorps   xmm0, xmm0
0x180002b83  lea     rdx, [rsp+2A8h+SourceString]; SourceString
0x180002b8b  lea     rcx, [rsp+2A8h+DestinationString]; DestinationString
0x180002b90  movups  xmmword ptr [rsp+2A8h+DestinationString.Length], xmm0
0x180002b95  call    cs:__imp_RtlInitUnicodeString
0x180002b9b  lea     rax, [rsp+2A8h+DestinationString]
0x180002ba0  mov     [rsp+2A8h+ObjectAttributes.Length], 30h ; '0'
0x180002ba8  xorps   xmm0, xmm0
0x180002bab  mov     [rsp+2A8h+ObjectAttributes.ObjectName], rax
0x180002bb0  lea     r8, [rsp+2A8h+ObjectAttributes]; ObjectAttributes
0x180002bb5  mov     [rsp+2A8h+ObjectAttributes.RootDirectory], rdi
0x180002bba  mov     edx, 4; DesiredAccess
0x180002bbf  mov     [rsp+2A8h+ObjectAttributes.Attributes], edi
0x180002bc3  lea     rcx, [rsp+2A8h+FileHandle]; FileHandle
0x180002bc8  movdqu  xmmword ptr [rsp+2A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002bce  call    cs:__imp_NtOpenDirectoryObject
0x180002bd4  test    eax, eax
0x180002bd6  js      loc_180002C7A
0x180002bdc  mov     rax, [rsp+2A8h+FileHandle]
0x180002be1  mov     rcx, [rsp+2A8h+var_18]
0x180002be9  xor     rcx, rsp; StackCookie
0x180002bec  call    __security_check_cookie
0x180002bf1  mov     rbx, [rsp+2A8h+arg_8]
0x180002bf9  add     rsp, 2A0h
0x180002c00  pop     rdi
0x180002c01  retn
0x180002c02  mov     eax, 7FFFFFFEh
0x180002c07  lea     r8, aBasenamedobjec; "\\BaseNamedObjects"
0x180002c0e  lea     r9, [rsp+2A8h+SourceString]
0x180002c16  test    rax, rax
0x180002c19  jz      short loc_180002C39
0x180002c1b  movzx   ecx, word ptr [r8]
0x180002c1f  test    cx, cx
0x180002c22  jz      short loc_180002C39
0x180002c24  mov     [r9], cx
0x180002c28  add     r8, 2
0x180002c2c  add     r9, 2
0x180002c30  dec     rax
0x180002c33  sub     rdx, 1
0x180002c37  jnz     short loc_180002C16
0x180002c39  test    rdx, rdx
0x180002c3c  lea     rcx, [r9-2]
0x180002c40  cmovnz  rcx, r9
0x180002c44  mov     [rcx], di
0x180002c47  jmp     loc_180002B63
0x180002c4c  mov     rcx, [rcx+10h]
0x180002c50  lea     rax, [rsp+2A8h+SourceString]
0x180002c58  mov     edx, 0Ah
0x180002c5d  mov     [rsp+2A8h+var_288], rax
0x180002c62  lea     r9, aPenserviceOpen; "PENSERVICE__OpenSessionDirectory"
0x180002c69  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002c70  call    WPP_SF_sS
0x180002c75  jmp     loc_180002B80
0x180002c7a  mov     rdx, rdi
0x180002c7d  mov     [rsp+2A8h+FileHandle], rdx
0x180002c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c89  cmp     rcx, rbx
0x180002c8c  jz      short loc_180002CB9
0x180002c8e  test    byte ptr [rcx+1Ch], 4
0x180002c92  jz      short loc_180002CB9
0x180002c94  mov     rcx, [rcx+10h]
0x180002c98  lea     r9, aPenserviceOpen; "PENSERVICE__OpenSessionDirectory"
0x180002c9f  mov     edx, 0Bh
0x180002ca4  mov     dword ptr [rsp+2A8h+var_288], eax
0x180002ca8  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002caf  call    WPP_SF_sd
0x180002cb4  jmp     loc_180002BDC
0x180002cb9  mov     rax, rdx
0x180002cbc  jmp     loc_180002BE1
```
