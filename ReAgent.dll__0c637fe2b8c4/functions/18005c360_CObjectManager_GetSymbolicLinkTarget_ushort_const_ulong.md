# CObjectManager::GetSymbolicLinkTarget(ushort const *,ulong *)

- ea: `0x18005c360`
- end: `0x18005c586`
- name: `?GetSymbolicLinkTarget@CObjectManager@@SAPEAGPEBGPEAK@Z`
- size: `550`
- prototype: `unsigned __int16 *__fastcall(WCHAR *SourceString, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180054cb4`
- `0x18005c190`

## callees

- `0x180002ba8`
- `0x18004f620`
- `0x18004f8d0`
- `0x18004fb04`
- `0x18005c360`
- `0x18005c58c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtQuerySymbolicLinkObject` at `0x18005c463`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18005c463`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18005c435`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18005c435`
- `ntdll!RtlInitUnicodeString` at `0x18005c3f8`
- `ntdll!RtlInitUnicodeString` at `0x18005c3f8`
- `ntdll!RtlNtStatusToDosError` at `0x18005c4cd`
- `ntdll!RtlNtStatusToDosError` at `0x18005c50e`
- `ntdll!RtlNtStatusToDosError` at `0x18005c4cd`
- `ntdll!RtlNtStatusToDosError` at `0x18005c50e`
- `KERNEL32!CloseHandle` at `0x18005c552`
- `KERNEL32!CloseHandle` at `0x18005c552`

## pseudocode

```c
unsigned __int16 *__fastcall CObjectManager::GetSymbolicLinkTarget(WCHAR *SourceString, unsigned int *a2)
{
  unsigned __int16 *v4; // r14
  int v5; // eax
  unsigned int v6; // esi
  int v7; // eax
  char v8; // si
  USHORT Length; // ax
  unsigned __int64 v10; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  void *SymbolicLinkHandle; // [rsp+40h] [rbp-C0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SourceStringa[264]; // [rsp+80h] [rbp-80h] BYREF

  SymbolicLinkHandle = (void *)-1LL;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(SourceStringa, 0, 0x208u);
  if ( !SourceString || !a2 )
    return 0;
  v4 = 0;
  *a2 = 0;
  if ( (unsigned int)CObjectManager::IsSymbolicLink(SourceString) )
  {
    while ( 1 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x20001u, &ObjectAttributes);
      v6 = v5;
      if ( v5 < 0 )
        break;
      DestinationString.Buffer = SourceStringa;
      *(_DWORD *)&DestinationString.Length = 33816576;
      v7 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &DestinationString, 0);
      v8 = v7;
      if ( v7 < 0 )
      {
        *a2 = RtlNtStatusToDosError(v7);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            (unsigned int)WPP_9d13d05dc9203195c8b3dfde0951cfa5_Traceguids,
            (_DWORD)SourceString,
            v8);
        goto LABEL_19;
      }
      Length = DestinationString.Length;
      if ( DestinationString.Length > DestinationString.MaximumLength )
        Length = DestinationString.MaximumLength;
      v10 = Length & 0xFFFE;
      DestinationString.Length = Length;
      if ( v10 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)SourceStringa + v10) = 0;
      if ( !(unsigned int)CObjectManager::IsSymbolicLink(SourceStringa) )
      {
        v4 = Utils::StrDupe(SourceStringa, a2);
        goto LABEL_19;
      }
      SourceString = SourceStringa;
    }
    *a2 = RtlNtStatusToDosError(v5);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9d13d05dc9203195c8b3dfde0951cfa5_Traceguids, v6);
  }
LABEL_19:
  if ( SymbolicLinkHandle != (void *)-1LL )
    CloseHandle(SymbolicLinkHandle);
  return v4;
}

```

## disassembly

```asm
0x18005c360  mov     [rsp-8+arg_10], rbx
0x18005c365  mov     [rsp-8+arg_18], rsi
0x18005c36a  push    rbp
0x18005c36b  push    rdi
0x18005c36c  push    r14
0x18005c36e  lea     rbp, [rsp-1A0h]
0x18005c376  sub     rsp, 2A0h
0x18005c37d  mov     rax, cs:__security_cookie
0x18005c384  xor     rax, rsp
0x18005c387  mov     [rbp+1B0h+var_20], rax
0x18005c38e  xorps   xmm1, xmm1
0x18005c391  mov     [rsp+2B0h+SymbolicLinkHandle], 0FFFFFFFFFFFFFFFFh
0x18005c39a  mov     rbx, rdx
0x18005c39d  mov     rdi, rcx
0x18005c3a0  xorps   xmm0, xmm0
0x18005c3a3  lea     rcx, [rbp+1B0h+SourceString]; void *
0x18005c3a7  xor     edx, edx; Val
0x18005c3a9  mov     r8d, 208h; Size
0x18005c3af  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18005c3b4  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm1
0x18005c3b9  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm1
0x18005c3be  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18005c3c3  call    memset_0
0x18005c3c8  test    rdi, rdi
0x18005c3cb  jz      loc_18005C55D
0x18005c3d1  test    rbx, rbx
0x18005c3d4  jz      loc_18005C55D
0x18005c3da  xor     r14d, r14d
0x18005c3dd  mov     rcx, rdi; SourceString
0x18005c3e0  mov     [rbx], r14d
0x18005c3e3  call    ?IsSymbolicLink@CObjectManager@@SAHPEBG@Z; CObjectManager::IsSymbolicLink(ushort const *)
0x18005c3e8  test    eax, eax
0x18005c3ea  jz      loc_18005C547
0x18005c3f0  mov     rdx, rdi; SourceString
0x18005c3f3  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18005c3f8  call    cs:__imp_RtlInitUnicodeString
0x18005c3fe  lea     rax, [rsp+2B0h+DestinationString]
0x18005c403  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x18005c40b  xorps   xmm0, xmm0
0x18005c40e  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x18005c413  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x18005c418  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], r14
0x18005c41d  mov     edx, 20001h; DesiredAccess
0x18005c422  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005c42a  lea     rcx, [rsp+2B0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18005c42f  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c435  call    cs:__imp_NtOpenSymbolicLinkObject
0x18005c43b  mov     esi, eax
0x18005c43d  test    eax, eax
0x18005c43f  js      loc_18005C50C
0x18005c445  mov     rcx, [rsp+2B0h+SymbolicLinkHandle]; SymLinkObjHandle
0x18005c44a  lea     rax, [rbp+1B0h+SourceString]
0x18005c44e  xor     r8d, r8d; DataWritten
0x18005c451  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x18005c456  lea     rdx, [rsp+2B0h+DestinationString]; LinkTarget
0x18005c45b  mov     dword ptr [rsp+2B0h+DestinationString.Length], 2040000h
0x18005c463  call    cs:__imp_NtQuerySymbolicLinkObject
0x18005c469  mov     esi, eax
0x18005c46b  test    eax, eax
0x18005c46d  js      short loc_18005C4CB
0x18005c46f  movzx   eax, [rsp+2B0h+DestinationString.Length]
0x18005c474  cmp     ax, [rsp+2B0h+DestinationString.MaximumLength]
0x18005c479  cmova   ax, [rsp+2B0h+DestinationString.MaximumLength]
0x18005c47f  movzx   ecx, ax
0x18005c482  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18005c486  mov     [rsp+2B0h+DestinationString.Length], ax
0x18005c48b  cmp     rcx, 208h
0x18005c492  jnb     short loc_18005C4C5
0x18005c494  xor     eax, eax
0x18005c496  mov     [rbp+rcx+1B0h+SourceString], ax
0x18005c49b  lea     rcx, [rbp+1B0h+SourceString]; SourceString
0x18005c49f  call    ?IsSymbolicLink@CObjectManager@@SAHPEBG@Z; CObjectManager::IsSymbolicLink(ushort const *)
0x18005c4a4  test    eax, eax
0x18005c4a6  jz      short loc_18005C4B1
0x18005c4a8  lea     rdi, [rbp+1B0h+SourceString]
0x18005c4ac  jmp     loc_18005C3F0
0x18005c4b1  mov     rdx, rbx; unsigned int *
0x18005c4b4  lea     rcx, [rbp+1B0h+SourceString]; unsigned __int16 *
0x18005c4b8  call    ?StrDupe@Utils@@SAPEAGPEBGPEAK@Z; Utils::StrDupe(ushort const *,ulong *)
0x18005c4bd  mov     r14, rax
0x18005c4c0  jmp     loc_18005C547
0x18005c4c5  call    __report_rangecheckfailure
0x18005c4cb  mov     ecx, esi; Status
0x18005c4cd  call    cs:__imp_RtlNtStatusToDosError
0x18005c4d3  mov     [rbx], eax
0x18005c4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4dc  lea     rax, WPP_GLOBAL_Control
0x18005c4e3  cmp     rcx, rax
0x18005c4e6  jz      short loc_18005C547
0x18005c4e8  test    byte ptr [rcx+1Ch], 2
0x18005c4ec  jz      short loc_18005C547
0x18005c4ee  mov     rcx, [rcx+10h]
0x18005c4f2  lea     r8, WPP_9d13d05dc9203195c8b3dfde0951cfa5_Traceguids
0x18005c4f9  mov     edx, 0Bh
0x18005c4fe  mov     [rsp+2B0h+var_290], esi
0x18005c502  mov     r9, rdi
0x18005c505  call    WPP_SF_Sd
0x18005c50a  jmp     short loc_18005C547
0x18005c50c  mov     ecx, esi; Status
0x18005c50e  call    cs:__imp_RtlNtStatusToDosError
0x18005c514  mov     [rbx], eax
0x18005c516  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c51d  lea     rax, WPP_GLOBAL_Control
0x18005c524  cmp     rcx, rax
0x18005c527  jz      short loc_18005C547
0x18005c529  test    byte ptr [rcx+1Ch], 2
0x18005c52d  jz      short loc_18005C547
0x18005c52f  mov     rcx, [rcx+10h]
0x18005c533  lea     r8, WPP_9d13d05dc9203195c8b3dfde0951cfa5_Traceguids
0x18005c53a  mov     edx, 0Ah
0x18005c53f  mov     r9d, esi
0x18005c542  call    WPP_SF_d
0x18005c547  mov     rcx, [rsp+2B0h+SymbolicLinkHandle]; hObject
0x18005c54c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005c550  jz      short loc_18005C558
0x18005c552  call    cs:__imp_CloseHandle
0x18005c558  mov     rax, r14
0x18005c55b  jmp     short loc_18005C55F
0x18005c55d  xor     eax, eax
0x18005c55f  mov     rcx, [rbp+1B0h+var_20]
0x18005c566  xor     rcx, rsp; StackCookie
0x18005c569  call    __security_check_cookie
0x18005c56e  lea     r11, [rsp+2B0h+var_10]
0x18005c576  mov     rbx, [r11+30h]
0x18005c57a  mov     rsi, [r11+38h]
0x18005c57e  mov     rsp, r11
0x18005c581  pop     r14
0x18005c583  pop     rdi
0x18005c584  pop     rbp
0x18005c585  retn
```
