# SaferpQueryActualDriveLetterFromDriveLetter

- ea: `0x180013668`
- end: `0x18001386e`
- name: `SaferpQueryActualDriveLetterFromDriveLetter`
- size: `518`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800130ec`
- `0x1800135b8`
- `0x180013668`

## callees

- `0x180013668`
- `0x180013874`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x180013783`
- `ntdll!NtClose` at `0x180013783`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180013743`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180013743`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180013776`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180013776`
- `ntdll!RtlPrefixUnicodeString` at `0x1800137ac`
- `ntdll!RtlPrefixUnicodeString` at `0x1800137c9`
- `ntdll!RtlPrefixUnicodeString` at `0x1800137ac`
- `ntdll!RtlPrefixUnicodeString` at `0x1800137c9`
- `ntdll!RtlInitUnicodeString` at `0x180013702`
- `ntdll!RtlInitUnicodeString` at `0x180013702`

## pseudocode

```c
char __fastcall SaferpQueryActualDriveLetterFromDriveLetter(__int64 a1, __int16 a2, _WORD *a3, __int16 a4)
{
  NTSTATUS v8; // ebx
  __int64 v10; // rdx
  ULONG DataWritten; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SourceString[4]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v17; // [rsp+88h] [rbp-78h]
  int v18; // [rsp+8Ah] [rbp-76h]
  char v19; // [rsp+90h] [rbp-70h] BYREF

  v18 = 58;
  SymbolicLinkHandle = 0;
  *(_QWORD *)SourceString = 0x5C003F003F005CLL;
  DataWritten = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  LinkTarget = 0;
  if ( (unsigned __int16)(a2 - 65) > 0x19u && (unsigned __int16)(a2 - 97) > 0x19u )
    return 0;
  v17 = a2;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
    return 0;
  LinkTarget.Buffer = (PWSTR)&v19;
  *(_DWORD *)&LinkTarget.Length = 68157440;
  DataWritten = 0;
  v8 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
  NtClose(SymbolicLinkHandle);
  if ( v8 < 0 )
    return 0;
  if ( (unsigned __int8)SaferpIsNetworkVolume(a1) )
  {
    *a3 = 0;
    return 1;
  }
  if ( !RtlPrefixUnicodeString(&String1, &LinkTarget, 1u)
    || LinkTarget.Length < 0xCu
    || LinkTarget.Buffer[5] != 58
    || (v10 = LinkTarget.Buffer[4], (unsigned __int16)(v10 - 65) > 0x19u) && (unsigned __int16)(v10 - 97) > 0x19u )
  {
    if ( !RtlPrefixUnicodeString(&stru_180067140, &LinkTarget, 1u) )
      return 0;
    *a3 = a2;
    return 1;
  }
  if ( a4 <= 0 )
    return 0;
  return SaferpQueryActualDriveLetterFromDriveLetter(a1, v10, a3, (unsigned __int16)(a4 - 1));
}

```

## disassembly

```asm
0x180013668  mov     [rsp-8+arg_8], rbx
0x18001366d  push    rbp
0x18001366e  push    rsi
0x18001366f  push    rdi
0x180013670  push    r12
0x180013672  push    r13
0x180013674  push    r14
0x180013676  push    r15
0x180013678  lea     rbp, [rsp-3B0h]
0x180013680  sub     rsp, 4B0h
0x180013687  mov     rax, cs:__security_cookie
0x18001368e  xor     rax, rsp
0x180013691  mov     [rbp+3E0h+var_40], rax
0x180013698  xorps   xmm0, xmm0
0x18001369b  mov     [rbp+3E0h+var_456], 3Ah ; ':'
0x1800136a2  xor     eax, eax
0x1800136a4  xor     r12d, r12d
0x1800136a7  mov     rax, 5C003F003F005Ch
0x1800136b1  mov     [rsp+4E0h+SymbolicLinkHandle], r12
0x1800136b6  movzx   r14d, dx
0x1800136ba  mov     qword ptr [rbp+3E0h+SourceString], rax
0x1800136be  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.ObjectName], xmm0
0x1800136c3  movzx   edi, r9w
0x1800136c7  mov     [rsp+4E0h+DataWritten], r12d
0x1800136cc  mov     rsi, r8
0x1800136cf  mov     r15, rcx
0x1800136d2  lea     eax, [r14-41h]
0x1800136d6  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x1800136db  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x1800136e0  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+1Ch], xmm0
0x1800136e5  movups  xmmword ptr [rsp+4E0h+LinkTarget.Length], xmm0
0x1800136ea  cmp     ax, 19h
0x1800136ee  ja      loc_180013804
0x1800136f4  lea     rdx, [rbp+3E0h+SourceString]; SourceString
0x1800136f8  mov     [rbp+3E0h+var_458], r14w
0x1800136fd  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180013702  call    cs:__imp_RtlInitUnicodeString
0x180013708  lea     rax, [rsp+4E0h+DestinationString]
0x18001370d  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x180013715  xorps   xmm0, xmm0
0x180013718  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x18001371d  mov     r13d, 1
0x180013723  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], r12
0x180013728  mov     edx, r13d; DesiredAccess
0x18001372b  mov     [rsp+4E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180013733  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x180013738  lea     rcx, [rsp+4E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18001373d  movdqu  xmmword ptr [rsp+4E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013743  call    cs:__imp_NtOpenSymbolicLinkObject
0x180013749  test    eax, eax
0x18001374b  js      loc_180013812
0x180013751  mov     rcx, [rsp+4E0h+SymbolicLinkHandle]; SymLinkObjHandle
0x180013756  lea     rax, [rbp+3E0h+var_450]
0x18001375a  lea     r8, [rsp+4E0h+DataWritten]; DataWritten
0x18001375f  mov     [rsp+4E0h+LinkTarget.Buffer], rax
0x180013764  lea     rdx, [rsp+4E0h+LinkTarget]; LinkTarget
0x180013769  mov     dword ptr [rsp+4E0h+LinkTarget.Length], 4100000h
0x180013771  mov     [rsp+4E0h+DataWritten], r12d
0x180013776  call    cs:__imp_NtQuerySymbolicLinkObject
0x18001377c  mov     rcx, [rsp+4E0h+SymbolicLinkHandle]; Handle
0x180013781  mov     ebx, eax
0x180013783  call    cs:__imp_NtClose
0x180013789  test    ebx, ebx
0x18001378b  js      loc_180013812
0x180013791  mov     rcx, r15
0x180013794  call    SaferpIsNetworkVolume
0x180013799  test    al, al
0x18001379b  jnz     short loc_180013816
0x18001379d  mov     r8b, r13b; CaseInsensitive
0x1800137a0  lea     rdx, [rsp+4E0h+LinkTarget]; String2
0x1800137a5  lea     rcx, String1; String1
0x1800137ac  call    cs:__imp_RtlPrefixUnicodeString
0x1800137b2  test    al, al
0x1800137b4  jnz     loc_18001384C
0x1800137ba  mov     r8b, r13b; CaseInsensitive
0x1800137bd  lea     rdx, [rsp+4E0h+LinkTarget]; String2
0x1800137c2  lea     rcx, stru_180067140; String1
0x1800137c9  call    cs:__imp_RtlPrefixUnicodeString
0x1800137cf  test    al, al
0x1800137d1  jz      short loc_180013812
0x1800137d3  mov     [rsi], r14w
0x1800137d7  mov     al, r13b
0x1800137da  mov     rcx, [rbp+3E0h+var_40]
0x1800137e1  xor     rcx, rsp; StackCookie
0x1800137e4  call    __security_check_cookie
0x1800137e9  mov     rbx, [rsp+4E0h+arg_8]
0x1800137f1  add     rsp, 4B0h
0x1800137f8  pop     r15
0x1800137fa  pop     r14
0x1800137fc  pop     r13
0x1800137fe  pop     r12
0x180013800  pop     rdi
0x180013801  pop     rsi
0x180013802  pop     rbp
0x180013803  retn
0x180013804  lea     eax, [r14-61h]
0x180013808  cmp     ax, 19h
0x18001380c  jbe     loc_1800136F4
0x180013812  xor     al, al
0x180013814  jmp     short loc_1800137DA
0x180013816  mov     [rsi], r12w
0x18001381a  jmp     short loc_1800137D7
0x18001381c  movzx   edx, word ptr [rdx+8]
0x180013820  lea     eax, [rdx-41h]
0x180013823  cmp     ax, 19h
0x180013827  jbe     short loc_180013832
0x180013829  lea     eax, [rdx-61h]
0x18001382c  cmp     ax, 19h
0x180013830  ja      short loc_1800137BA
0x180013832  test    di, di
0x180013835  jle     short loc_180013812
0x180013837  sub     di, r13w
0x18001383b  mov     r8, rsi
0x18001383e  movzx   r9d, di
0x180013842  mov     rcx, r15
0x180013845  call    SaferpQueryActualDriveLetterFromDriveLetter
0x18001384a  jmp     short loc_1800137DA
0x18001384c  cmp     [rsp+4E0h+LinkTarget.Length], 0Ch
0x180013852  jb      loc_1800137BA
0x180013858  mov     rdx, [rsp+4E0h+LinkTarget.Buffer]
0x18001385d  mov     eax, 3Ah ; ':'
0x180013862  cmp     [rdx+0Ah], ax
0x180013866  jnz     loc_1800137BA
0x18001386c  jmp     short loc_18001381C
```
