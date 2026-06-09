# SdbUnregisterDatabase

- ea: `0x18004a780`
- end: `0x18004a937`
- name: `SdbUnregisterDatabase`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f114`
- `0x180015f80`
- `0x18001ab9c`
- `0x18002f8e0`
- `0x18004a780`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18004a8e8`
- `ntdll!NtDeleteKey` at `0x18004a8e8`
- `ntdll!NtClose` at `0x18004a914`
- `ntdll!NtClose` at `0x18004a914`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004a859`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004a859`
- `ntdll!NtOpenKey` at `0x18004a8a0`
- `ntdll!NtOpenKey` at `0x18004a8a0`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a837`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a849`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a837`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a849`

## string_xrefs

- `0x18004a826`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x18004a8b9`: `Failed to open key "%ws" [%x]`
- `0x18004a8f6`: `Failed to delete key "%ws" [%x]`

## pseudocode

```c
__int64 __fastcall SdbUnregisterDatabase(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  NTSTATUS v4; // eax
  int v5; // ecx
  NTSTATUS v6; // eax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v12[528]; // [rsp+90h] [rbp-70h] BYREF

  Destination = 0;
  v2 = 0;
  Source = 0;
  memset_0(v12, 0, 0x208u);
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = AslGuidToString_UStr(&Source, a1);
  if ( v3 >= 0 )
  {
    *(_DWORD *)&Destination.Length = 34078720;
    Destination.Buffer = (PWSTR)v12;
    RtlAppendUnicodeToString(
      &Destination,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeStringToString(&Destination, &Source);
    AslUnicodeStringFree(&Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenKey(&KeyHandle, 0x10100u, &ObjectAttributes);
    if ( v4 >= 0 || (unsigned int)AslFileNotFound((unsigned int)v4) )
    {
      v6 = NtDeleteKey(KeyHandle);
      if ( v6 >= 0 )
        v2 = 1;
      else
        AslLogCallPrintf(1, "SdbUnregisterDatabase", 1298, "Failed to delete key \"%ws\" [%x]", Destination.Buffer, v6);
    }
    else
    {
      AslLogCallPrintf(1, "SdbUnregisterDatabase", 1288, "Failed to open key \"%ws\" [%x]", Destination.Buffer, v5);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbUnregisterDatabase", 1259, "Cannot convert guid to unicode string [%x]", v3);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x18004a780  push    rbp
0x18004a782  push    rbx
0x18004a783  push    rsi
0x18004a784  push    rdi
0x18004a785  lea     rbp, [rsp-1B8h]
0x18004a78d  sub     rsp, 2B8h
0x18004a794  mov     rax, cs:__security_cookie
0x18004a79b  xor     rax, rsp
0x18004a79e  mov     [rbp+1D0h+var_30], rax
0x18004a7a5  mov     rbx, rcx
0x18004a7a8  xorps   xmm0, xmm0
0x18004a7ab  xorps   xmm1, xmm1
0x18004a7ae  lea     rcx, [rbp+1D0h+var_240]; void *
0x18004a7b2  xor     edx, edx; Val
0x18004a7b4  mov     r8d, 208h; Size
0x18004a7ba  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm0
0x18004a7bf  xor     edi, edi
0x18004a7c1  movups  xmmword ptr [rsp+2D0h+Source.Length], xmm1
0x18004a7c6  call    memset_0
0x18004a7cb  xorps   xmm0, xmm0
0x18004a7ce  mov     [rsp+2D0h+KeyHandle], rdi
0x18004a7d3  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x18004a7d8  xor     eax, eax
0x18004a7da  lea     rcx, [rsp+2D0h+Source]
0x18004a7df  mov     rdx, rbx
0x18004a7e2  movups  xmmword ptr [rsp+2D0h+ObjectAttributes+1Ch], xmm0
0x18004a7e7  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x18004a7ec  call    AslGuidToString_UStr
0x18004a7f1  test    eax, eax
0x18004a7f3  jns     short loc_18004A81A
0x18004a7f5  lea     r9, aCannotConvertG; "Cannot convert guid to unicode string ["...
0x18004a7fc  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x18004a800  mov     r8d, 4EBh
0x18004a806  lea     rdx, aSdbunregisterd_0; "SdbUnregisterDatabase"
0x18004a80d  lea     ecx, [rdi+1]
0x18004a810  call    AslLogCallPrintf
0x18004a815  jmp     loc_18004A90A
0x18004a81a  lea     rax, [rbp+1D0h+var_240]
0x18004a81e  mov     dword ptr [rsp+2D0h+Destination.Length], 2080000h
0x18004a826  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18004a82d  mov     [rsp+2D0h+Destination.Buffer], rax
0x18004a832  lea     rcx, [rsp+2D0h+Destination]; Destination
0x18004a837  call    cs:__imp_RtlAppendUnicodeToString
0x18004a83d  lea     rdx, pszSrc; "\\"
0x18004a844  lea     rcx, [rsp+2D0h+Destination]; Destination
0x18004a849  call    cs:__imp_RtlAppendUnicodeToString
0x18004a84f  lea     rdx, [rsp+2D0h+Source]; Source
0x18004a854  lea     rcx, [rsp+2D0h+Destination]; Destination
0x18004a859  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004a85f  lea     rcx, [rsp+2D0h+Source]
0x18004a864  call    AslUnicodeStringFree
0x18004a869  lea     rax, [rsp+2D0h+Destination]
0x18004a86e  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x18004a876  xorps   xmm0, xmm0
0x18004a879  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x18004a87e  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x18004a883  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rdi
0x18004a888  mov     edx, 10100h; DesiredAccess
0x18004a88d  mov     [rsp+2D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18004a895  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x18004a89a  movdqu  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004a8a0  call    cs:__imp_NtOpenKey
0x18004a8a6  mov     ecx, eax
0x18004a8a8  test    eax, eax
0x18004a8aa  jns     short loc_18004A8E3
0x18004a8ac  call    AslFileNotFound
0x18004a8b1  test    eax, eax
0x18004a8b3  jnz     short loc_18004A8E3
0x18004a8b5  mov     [rsp+2D0h+var_2A8], ecx
0x18004a8b9  lea     r9, aFailedToOpenKe_2; "Failed to open key \"%ws\" [%x]"
0x18004a8c0  mov     r8d, 508h
0x18004a8c6  mov     rax, [rsp+2D0h+Destination.Buffer]
0x18004a8cb  lea     rdx, aSdbunregisterd_0; "SdbUnregisterDatabase"
0x18004a8d2  mov     ecx, 1
0x18004a8d7  mov     [rsp+2D0h+var_2B0], rax
0x18004a8dc  call    AslLogCallPrintf
0x18004a8e1  jmp     short loc_18004A90A
0x18004a8e3  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x18004a8e8  call    cs:__imp_NtDeleteKey
0x18004a8ee  test    eax, eax
0x18004a8f0  jns     short loc_18004A905
0x18004a8f2  mov     [rsp+2D0h+var_2A8], eax
0x18004a8f6  lea     r9, aFailedToDelete; "Failed to delete key \"%ws\" [%x]"
0x18004a8fd  mov     r8d, 512h
0x18004a903  jmp     short loc_18004A8C6
0x18004a905  mov     edi, 1
0x18004a90a  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x18004a90f  test    rcx, rcx
0x18004a912  jz      short loc_18004A91A
0x18004a914  call    cs:__imp_NtClose
0x18004a91a  mov     eax, edi
0x18004a91c  mov     rcx, [rbp+1D0h+var_30]
0x18004a923  xor     rcx, rsp; StackCookie
0x18004a926  call    __security_check_cookie
0x18004a92b  add     rsp, 2B8h
0x18004a932  pop     rdi
0x18004a933  pop     rsi
0x18004a934  pop     rbx
0x18004a935  pop     rbp
0x18004a936  retn
```
