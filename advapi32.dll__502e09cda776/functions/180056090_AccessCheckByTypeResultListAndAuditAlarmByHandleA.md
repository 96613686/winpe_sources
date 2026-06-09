# AccessCheckByTypeResultListAndAuditAlarmByHandleA

- ea: `0x180056090`
- end: `0x18005626b`
- name: `AccessCheckByTypeResultListAndAuditAlarmByHandleA`
- size: `475`
- prototype: `BOOL __stdcall(LPCSTR SubsystemName, LPVOID HandleId, HANDLE ClientToken, LPCSTR ObjectTypeName, LPCSTR ObjectName, PSECURITY_DESCRIPTOR SecurityDescriptor, PSID PrincipalSelfSid, DWORD DesiredAccess, AUDIT_EVENT_TYPE AuditType, DWORD Flags, POBJECT_TYPE_LIST ObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING GenericMapping, BOOL ObjectCreation, LPDWORD GrantedAccess, LPDWORD AccessStatusList, LPBOOL pfGenerateOnClose)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180056090`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005613e`
- `ntdll!RtlFreeUnicodeString` at `0x180056186`
- `ntdll!RtlFreeUnicodeString` at `0x18005623e`
- `ntdll!RtlFreeUnicodeString` at `0x18005624e`
- `ntdll!RtlFreeUnicodeString` at `0x18005613e`
- `ntdll!RtlFreeUnicodeString` at `0x180056186`
- `ntdll!RtlFreeUnicodeString` at `0x18005623e`
- `ntdll!RtlFreeUnicodeString` at `0x18005624e`
- `ntdll!RtlInitAnsiString` at `0x1800560ce`
- `ntdll!RtlInitAnsiString` at `0x180056111`
- `ntdll!RtlInitAnsiString` at `0x180056156`
- `ntdll!RtlInitAnsiString` at `0x1800560ce`
- `ntdll!RtlInitAnsiString` at `0x180056111`
- `ntdll!RtlInitAnsiString` at `0x180056156`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800560e5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056128`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056170`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800560e5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056128`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056170`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmByHandleW` at `0x18005622c`
- `api-ms-win-security-base-l1-1-0!AccessCheckByTypeResultListAndAuditAlarmByHandleW` at `0x18005622c`
- `KERNEL32!BaseSetLastNTError` at `0x1800560f7`
- `KERNEL32!BaseSetLastNTError` at `0x1800560f7`

## pseudocode

```c
BOOL __stdcall AccessCheckByTypeResultListAndAuditAlarmByHandleA(
        LPCSTR SubsystemName,
        LPVOID HandleId,
        HANDLE ClientToken,
        LPCSTR ObjectTypeName,
        LPCSTR ObjectName,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSID PrincipalSelfSid,
        DWORD DesiredAccess,
        AUDIT_EVENT_TYPE AuditType,
        DWORD Flags,
        POBJECT_TYPE_LIST ObjectTypeList,
        DWORD ObjectTypeListLength,
        PGENERIC_MAPPING GenericMapping,
        BOOL ObjectCreation,
        LPDWORD GrantedAccess,
        LPDWORD AccessStatusList,
        LPBOOL pfGenerateOnClose)
{
  struct _TEB *v20; // rdi
  NTSTATUS v21; // eax
  __int64 v22; // rcx
  NTSTATUS v24; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  BOOL v26; // ebx
  struct _STRING DestinationString; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A0h] [rbp-19h] BYREF
  struct _UNICODE_STRING v29; // [rsp+B0h] [rbp-9h] BYREF

  DestinationString = 0;
  UnicodeString = 0;
  v29 = 0;
  v20 = NtCurrentTeb();
  RtlInitAnsiString(&DestinationString, SubsystemName);
  v21 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v21 < 0 )
  {
    v22 = (unsigned int)v21;
LABEL_3:
    BaseSetLastNTError(v22);
    return 0;
  }
  RtlInitAnsiString(&DestinationString, ObjectTypeName);
  v24 = RtlAnsiStringToUnicodeString(&v29, &DestinationString, 1u);
  if ( v24 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_6:
    RtlFreeUnicodeString(p_UnicodeString);
    v22 = (unsigned int)v24;
    goto LABEL_3;
  }
  RtlInitAnsiString(&DestinationString, ObjectName);
  v24 = RtlAnsiStringToUnicodeString(&v20->StaticUnicodeString, &DestinationString, 0);
  if ( v24 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v29;
    goto LABEL_6;
  }
  v26 = AccessCheckByTypeResultListAndAuditAlarmByHandleW(
          UnicodeString.Buffer,
          HandleId,
          ClientToken,
          v29.Buffer,
          v20->StaticUnicodeString.Buffer,
          SecurityDescriptor,
          PrincipalSelfSid,
          DesiredAccess,
          AuditType,
          Flags,
          ObjectTypeList,
          ObjectTypeListLength,
          GenericMapping,
          ObjectCreation,
          GrantedAccess,
          AccessStatusList,
          pfGenerateOnClose);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v29);
  return v26;
}

```

## disassembly

```asm
0x180056090  push    rbp
0x180056092  push    rbx
0x180056093  push    rsi
0x180056094  push    rdi
0x180056095  push    r14
0x180056097  lea     rbp, [rsp-7]
0x18005609c  sub     rsp, 0C0h
0x1800560a3  xorps   xmm0, xmm0
0x1800560a6  mov     r14, rdx
0x1800560a9  xorps   xmm1, xmm1
0x1800560ac  mov     rdx, rcx; SourceString
0x1800560af  movups  xmmword ptr [rbp+27h+DestinationString.Length], xmm0
0x1800560b3  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x1800560b7  mov     rbx, r9
0x1800560ba  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x1800560be  mov     rsi, r8
0x1800560c1  movups  xmmword ptr [rbp+27h+var_30.Length], xmm0
0x1800560c5  mov     rdi, gs:30h
0x1800560ce  call    cs:__imp_RtlInitAnsiString
0x1800560d5  nop     dword ptr [rax+rax+00h]
0x1800560da  mov     r8b, 1; AllocateDestinationString
0x1800560dd  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x1800560e1  lea     rcx, [rbp+27h+UnicodeString]; DestinationString
0x1800560e5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800560ec  nop     dword ptr [rax+rax+00h]
0x1800560f1  test    eax, eax
0x1800560f3  jns     short loc_18005610A
0x1800560f5  mov     ecx, eax
0x1800560f7  call    cs:__imp_BaseSetLastNTError
0x1800560fe  nop     dword ptr [rax+rax+00h]
0x180056103  xor     eax, eax
0x180056105  jmp     loc_18005625C
0x18005610a  mov     rdx, rbx; SourceString
0x18005610d  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180056111  call    cs:__imp_RtlInitAnsiString
0x180056118  nop     dword ptr [rax+rax+00h]
0x18005611d  mov     r8b, 1; AllocateDestinationString
0x180056120  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180056124  lea     rcx, [rbp+27h+var_30]; DestinationString
0x180056128  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18005612f  nop     dword ptr [rax+rax+00h]
0x180056134  mov     ebx, eax
0x180056136  test    eax, eax
0x180056138  jns     short loc_18005614E
0x18005613a  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18005613e  call    cs:__imp_RtlFreeUnicodeString
0x180056145  nop     dword ptr [rax+rax+00h]
0x18005614a  mov     ecx, ebx
0x18005614c  jmp     short loc_1800560F7
0x18005614e  mov     rdx, [rbp+27h+ObjectName]; SourceString
0x180056152  lea     rcx, [rbp+27h+DestinationString]; DestinationString
0x180056156  call    cs:__imp_RtlInitAnsiString
0x18005615d  nop     dword ptr [rax+rax+00h]
0x180056162  xor     r8d, r8d; AllocateDestinationString
0x180056165  lea     rdx, [rbp+27h+DestinationString]; SourceString
0x180056169  lea     rcx, [rdi+1258h]; DestinationString
0x180056170  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180056177  nop     dword ptr [rax+rax+00h]
0x18005617c  mov     ebx, eax
0x18005617e  test    eax, eax
0x180056180  jns     short loc_180056198
0x180056182  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180056186  call    cs:__imp_RtlFreeUnicodeString
0x18005618d  nop     dword ptr [rax+rax+00h]
0x180056192  lea     rcx, [rbp+27h+var_30]
0x180056196  jmp     short loc_18005613E
0x180056198  mov     rax, [rbp+27h+pfGenerateOnClose]
0x18005619f  mov     r8, rsi; ClientToken
0x1800561a2  mov     r9, [rbp+27h+var_30.Buffer]; ObjectTypeName
0x1800561a6  mov     rdx, r14; HandleId
0x1800561a9  mov     rcx, [rbp+27h+UnicodeString.Buffer]; SubsystemName
0x1800561ad  mov     [rsp+0E0h+var_60], rax; pfGenerateOnClose
0x1800561b5  mov     rax, [rbp+27h+AccessStatusList]
0x1800561bc  mov     [rsp+0E0h+var_68], rax; AccessStatusList
0x1800561c1  mov     rax, [rbp+27h+GrantedAccess]
0x1800561c8  mov     [rsp+0E0h+GrantedAccessList], rax; GrantedAccessList
0x1800561cd  mov     eax, [rbp+27h+ObjectCreation]
0x1800561d3  mov     [rsp+0E0h+var_78], eax; ObjectCreation
0x1800561d7  mov     rax, [rbp+27h+GenericMapping]
0x1800561de  mov     [rsp+0E0h+var_80], rax; GenericMapping
0x1800561e3  mov     eax, [rbp+27h+ObjectTypeListLength]
0x1800561e9  mov     [rsp+0E0h+var_88], eax; ObjectTypeListLength
0x1800561ed  mov     rax, [rbp+27h+ObjectTypeList]
0x1800561f4  mov     [rsp+0E0h+var_90], rax; ObjectTypeList
0x1800561f9  mov     eax, [rbp+27h+Flags]
0x1800561fc  mov     [rsp+0E0h+var_98], eax; Flags
0x180056200  mov     eax, [rbp+27h+AuditType]
0x180056203  mov     [rsp+0E0h+var_A0], eax; AuditType
0x180056207  mov     eax, [rbp+27h+DesiredAccess]
0x18005620a  mov     [rsp+0E0h+var_A8], eax; DesiredAccess
0x18005620e  mov     rax, [rbp+27h+PrincipalSelfSid]
0x180056212  mov     [rsp+0E0h+var_B0], rax; PrincipalSelfSid
0x180056217  mov     rax, [rbp+27h+SecurityDescriptor]
0x18005621b  mov     [rsp+0E0h+var_B8], rax; SecurityDescriptor
0x180056220  mov     rax, [rdi+1260h]
0x180056227  mov     [rsp+0E0h+var_C0], rax; ObjectName
0x18005622c  call    cs:__imp_AccessCheckByTypeResultListAndAuditAlarmByHandleW
0x180056233  nop     dword ptr [rax+rax+00h]
0x180056238  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x18005623c  mov     ebx, eax
0x18005623e  call    cs:__imp_RtlFreeUnicodeString
0x180056245  nop     dword ptr [rax+rax+00h]
0x18005624a  lea     rcx, [rbp+27h+var_30]; UnicodeString
0x18005624e  call    cs:__imp_RtlFreeUnicodeString
0x180056255  nop     dword ptr [rax+rax+00h]
0x18005625a  mov     eax, ebx
0x18005625c  add     rsp, 0C0h
0x180056263  pop     r14
0x180056265  pop     rdi
0x180056266  pop     rsi
0x180056267  pop     rbx
0x180056268  pop     rbp
0x180056269  retn
```
