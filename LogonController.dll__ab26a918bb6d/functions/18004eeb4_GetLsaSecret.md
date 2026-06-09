# _GetLsaSecret

- ea: `0x18004eeb4`
- end: `0x18004efa3`
- name: `_GetLsaSecret`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dee8`

## callees

- `0x18004eeb4`
- `0x180064e40`
- `0x180091ff0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004ef25`
- `ntdll!RtlInitUnicodeString` at `0x18004ef25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004ef89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004ef89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004eef4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004eef4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18004ef37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18004ef37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004ef7f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004ef7f`

## pseudocode

```c
__int64 __fastcall GetLsaSecret(struct _LSA_UNICODE_STRING *a1, unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  int v4; // ebx
  NTSTATUS v5; // eax
  unsigned __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  PLSA_UNICODE_STRING v9; // rcx
  __int64 Length; // rdx
  PWSTR Buffer; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+70h] [rbp+10h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+18h] BYREF

  PrivateData = a1;
  *a2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v4 = ResultFromWin32FromStatus(v3);
  if ( v4 >= 0 )
  {
    PrivateData = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"DefaultPassword");
    v5 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
    v4 = ResultFromWin32FromStatus(v5);
    if ( v4 >= 0 )
    {
      v7 = RtlStringCchCopyUnicodeString(a2, v6, (const struct _UNICODE_STRING *)PrivateData);
      v8 = ResultFromWin32FromStatus(v7);
      v9 = PrivateData;
      v4 = v8;
      Length = PrivateData->Length;
      Buffer = PrivateData->Buffer;
      if ( PrivateData->Length )
      {
        do
        {
          *(_BYTE *)Buffer = 0;
          Buffer = (PWSTR)((char *)Buffer + 1);
          --Length;
        }
        while ( Length );
        v9 = PrivateData;
      }
      LsaFreeMemory(v9);
    }
    LsaClose(PolicyHandle);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004eeb4  mov     [rsp-8+arg_10], rbx
0x18004eeb9  mov     [rsp-8+arg_18], rdi
0x18004eebe  mov     [rsp-8+PrivateData], rcx
0x18004eec3  push    rbp
0x18004eec4  mov     rbp, rsp
0x18004eec7  sub     rsp, 60h
0x18004eecb  xor     eax, eax
0x18004eecd  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18004eed1  xorps   xmm0, xmm0
0x18004eed4  mov     [rdx], ax
0x18004eed7  mov     rdi, rdx
0x18004eeda  mov     [rbp+PolicyHandle], rax
0x18004eede  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18004eee2  xor     ecx, ecx; SystemName
0x18004eee4  lea     r8d, [rax+1]; DesiredAccess
0x18004eee8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004eeec  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004eef0  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004eef4  call    cs:__imp_LsaOpenPolicy
0x18004eefa  mov     ecx, eax; int
0x18004eefc  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18004ef01  mov     ebx, eax
0x18004ef03  test    eax, eax
0x18004ef05  js      loc_18004EF8F
0x18004ef0b  xorps   xmm0, xmm0
0x18004ef0e  mov     [rbp+PrivateData], 0
0x18004ef16  lea     rdx, SourceString; "DefaultPassword"
0x18004ef1d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004ef21  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004ef25  call    cs:__imp_RtlInitUnicodeString
0x18004ef2b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18004ef2f  lea     r8, [rbp+PrivateData]; PrivateData
0x18004ef33  lea     rdx, [rbp+DestinationString]; KeyName
0x18004ef37  call    cs:__imp_LsaRetrievePrivateData
0x18004ef3d  mov     ecx, eax; int
0x18004ef3f  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18004ef44  mov     ebx, eax
0x18004ef46  test    eax, eax
0x18004ef48  js      short loc_18004EF85
0x18004ef4a  mov     r8, [rbp+PrivateData]; struct _UNICODE_STRING *
0x18004ef4e  mov     rcx, rdi; unsigned __int16 *
0x18004ef51  call    ?RtlStringCchCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCchCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x18004ef56  mov     ecx, eax; int
0x18004ef58  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18004ef5d  mov     rcx, [rbp+PrivateData]
0x18004ef61  mov     ebx, eax
0x18004ef63  movzx   edx, word ptr [rcx]
0x18004ef66  mov     rax, [rcx+8]
0x18004ef6a  test    rdx, rdx
0x18004ef6d  jz      short loc_18004EF7F
0x18004ef6f  mov     byte ptr [rax], 0
0x18004ef72  inc     rax
0x18004ef75  sub     rdx, 1
0x18004ef79  jnz     short loc_18004EF6F
0x18004ef7b  mov     rcx, [rbp+PrivateData]; Buffer
0x18004ef7f  call    cs:__imp_LsaFreeMemory
0x18004ef85  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004ef89  call    cs:__imp_LsaClose
0x18004ef8f  lea     r11, [rsp+60h+var_s0]
0x18004ef94  mov     eax, ebx
0x18004ef96  mov     rbx, [r11+20h]
0x18004ef9a  mov     rdi, [r11+28h]
0x18004ef9e  mov     rsp, r11
0x18004efa1  pop     rbp
0x18004efa2  retn
```
