# BasepGetNamedObjectDirectoryForToken

- ea: `0x18006e604`
- end: `0x18006ee21`
- name: `BasepGetNamedObjectDirectoryForToken`
- size: `2077`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006cdc0`
- `0x18006e3f0`
- `0x1800af490`
- `0x1800b62a0`
- `0x18017d680`

## callees

- `0x18006e604`
- `0x18006fd7c`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1801908ee`
- `ntdll!RtlSubAuthoritySid` at `0x1801908ff`
- `ntdll!RtlSubAuthoritySid` at `0x180190910`
- `ntdll!RtlSubAuthoritySid` at `0x180190921`
- `ntdll!RtlSubAuthoritySid` at `0x1801908ee`
- `ntdll!RtlSubAuthoritySid` at `0x1801908ff`
- `ntdll!RtlSubAuthoritySid` at `0x180190910`
- `ntdll!RtlSubAuthoritySid` at `0x180190921`
- `ntdll!RtlFreeUnicodeString` at `0x18006e802`
- `ntdll!RtlFreeUnicodeString` at `0x18006ee16`
- `ntdll!RtlFreeUnicodeString` at `0x18006e802`
- `ntdll!RtlFreeUnicodeString` at `0x18006ee16`
- `ntdll!RtlInitUnicodeString` at `0x18006e9f2`
- `ntdll!RtlInitUnicodeString` at `0x18006ec09`
- `ntdll!RtlInitUnicodeString` at `0x18006ec73`
- `ntdll!RtlInitUnicodeString` at `0x18006ecdd`
- `ntdll!RtlInitUnicodeString` at `0x18019096a`
- `ntdll!RtlInitUnicodeString` at `0x18006e9f2`
- `ntdll!RtlInitUnicodeString` at `0x18006ec09`
- `ntdll!RtlInitUnicodeString` at `0x18006ec73`
- `ntdll!RtlInitUnicodeString` at `0x18006ecdd`
- `ntdll!RtlInitUnicodeString` at `0x18019096a`
- `ntdll!RtlLengthRequiredSid` at `0x18006ea02`
- `ntdll!RtlLengthRequiredSid` at `0x18006ea02`
- `ntdll!NtQueryInformationToken` at `0x18006e6e6`
- `ntdll!NtQueryInformationToken` at `0x18006e712`
- `ntdll!NtQueryInformationToken` at `0x18006e73b`
- `ntdll!NtQueryInformationToken` at `0x18006e990`
- `ntdll!NtQueryInformationToken` at `0x18006ea4b`
- `ntdll!NtQueryInformationToken` at `0x18006ed8e`
- `ntdll!NtQueryInformationToken` at `0x180190851`
- `ntdll!NtQueryInformationToken` at `0x18006e6e6`
- `ntdll!NtQueryInformationToken` at `0x18006e712`
- `ntdll!NtQueryInformationToken` at `0x18006e73b`
- `ntdll!NtQueryInformationToken` at `0x18006e990`
- `ntdll!NtQueryInformationToken` at `0x18006ea4b`
- `ntdll!NtQueryInformationToken` at `0x18006ed8e`
- `ntdll!NtQueryInformationToken` at `0x180190851`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006ebaa`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006eda9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1801908d5`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006ebaa`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18006eda9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1801908d5`
- `ntdll!NtClose` at `0x18006e820`
- `ntdll!NtClose` at `0x18006ec55`
- `ntdll!NtClose` at `0x18006ed2d`
- `ntdll!NtClose` at `0x18006edfc`
- `ntdll!NtClose` at `0x1801908ac`
- `ntdll!NtClose` at `0x18006e820`
- `ntdll!NtClose` at `0x18006ec55`
- `ntdll!NtClose` at `0x18006ed2d`
- `ntdll!NtClose` at `0x18006edfc`
- `ntdll!NtClose` at `0x1801908ac`
- `ntdll!RtlFreeSid` at `0x18006ee07`
- `ntdll!RtlFreeSid` at `0x18006ee07`
- `ntdll!RtlGetAppContainerSidType` at `0x18006eb85`
- `ntdll!RtlGetAppContainerSidType` at `0x18006eb85`
- `ntdll!RtlGetAppContainerParent` at `0x18006ed5e`
- `ntdll!RtlGetAppContainerParent` at `0x18006ed5e`
- `ntdll!RtlFreeHeap` at `0x18006e84a`
- `ntdll!RtlFreeHeap` at `0x18019080d`
- `ntdll!RtlFreeHeap` at `0x18006e84a`
- `ntdll!RtlFreeHeap` at `0x18019080d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18006e765`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18006e765`
- `ntdll!NtOpenDirectoryObject` at `0x18006e961`
- `ntdll!NtOpenDirectoryObject` at `0x18006e9d1`
- `ntdll!NtOpenDirectoryObject` at `0x18006eb62`
- `ntdll!NtOpenDirectoryObject` at `0x18006ebeb`
- `ntdll!NtOpenDirectoryObject` at `0x18006ec48`
- `ntdll!NtOpenDirectoryObject` at `0x18006ecaf`
- `ntdll!NtOpenDirectoryObject` at `0x18006ed15`
- `ntdll!NtOpenDirectoryObject` at `0x180190897`
- `ntdll!NtOpenDirectoryObject` at `0x1801909a1`
- `ntdll!NtOpenDirectoryObject` at `0x18006e961`
- `ntdll!NtOpenDirectoryObject` at `0x18006e9d1`
- `ntdll!NtOpenDirectoryObject` at `0x18006eb62`
- `ntdll!NtOpenDirectoryObject` at `0x18006ebeb`
- `ntdll!NtOpenDirectoryObject` at `0x18006ec48`
- `ntdll!NtOpenDirectoryObject` at `0x18006ecaf`
- `ntdll!NtOpenDirectoryObject` at `0x18006ed15`
- `ntdll!NtOpenDirectoryObject` at `0x180190897`
- `ntdll!NtOpenDirectoryObject` at `0x1801909a1`
- `ntdll!RtlAllocateHeap` at `0x18006ea1d`
- `ntdll!RtlAllocateHeap` at `0x180190827`
- `ntdll!RtlAllocateHeap` at `0x18006ea1d`
- `ntdll!RtlAllocateHeap` at `0x180190827`

## pseudocode

```c
__int64 __fastcall BasepGetNamedObjectDirectoryForToken(HANDLE TokenHandle, int a2, int a3, __int64 a4, _QWORD *a5)
{
  int v5; // esi
  _QWORD *Heap; // r12
  NTSTATUS AppContainerSidType; // ebx
  int v10; // eax
  int CurrentServiceSessionId; // eax
  int v12; // ecx
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rax
  WCHAR *v17; // rcx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HANDLE v20; // rax
  ULONG v21; // ebx
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E0h]
  ULONG v28; // [rsp+28h] [rbp-D8h]
  ULONG v29; // [rsp+30h] [rbp-D0h]
  ULONG v30; // [rsp+38h] [rbp-C8h]
  ULONG TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v33; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  int TokenInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+A8h] [rbp-58h] BYREF
  int v40; // [rsp+ACh] [rbp-54h] BYREF
  int v41; // [rsp+B0h] [rbp-50h]
  PSID v42; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v44; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v45; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v46; // [rsp+E8h] [rbp-18h] BYREF
  PSID Sid[12]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SourceString[256]; // [rsp+160h] [rbp+60h] BYREF
  PCWSTR v49; // [rsp+360h] [rbp+260h] BYREF
  char v50; // [rsp+368h] [rbp+268h]
  WCHAR v51[264]; // [rsp+480h] [rbp+380h] BYREF

  v45 = a5;
  v5 = a3;
  v41 = a3;
  v39 = 0;
  TokenInformationLength = 0;
  v40 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  UnicodeString = 0;
  memset_0(v51, 0, 0x208u);
  v46 = 0;
  v44 = 0;
  memset_0(SourceString, 0, sizeof(SourceString));
  TokenInformation = 0;
  v32 = 0;
  Handle = 0;
  v33 = 0;
  FileHandle = 0;
  Heap = 0;
  v42 = 0;
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenSessionId,
                          &TokenInformation,
                          4u,
                          &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  v39 = 0;
  AppContainerSidType = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v39, 4u, &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenIsRestricted|TokenGroups,
                          &v32,
                          4u,
                          &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  v10 = v32;
  if ( v32 )
  {
    AppContainerSidType = NtQueryInformationToken(TokenHandle, TokenUser, Sid, 0x54u, &TokenInformationLength);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    AppContainerSidType = RtlConvertSidToUnicodeString(&v44, Sid[0], 1u);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    v10 = v32;
  }
  if ( v39 )
  {
    v21 = RtlLengthRequiredSid(0xCu) + 8;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
    if ( Heap )
    {
      v22 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, Heap, v21, &TokenInformationLength);
      AppContainerSidType = v22;
      if ( v22 >= 0 )
      {
LABEL_47:
        LODWORD(ReturnLengtha) = TokenInformation;
        AppContainerSidType = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects",
                                L"\\Sessions",
                                ReturnLengtha);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( a2 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
        }
        else
        {
          DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 2520);
          if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
            DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                             + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                             + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                             - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                         + 2536)
                                             - (unsigned __int64)NtCurrentPeb()[1].Ldr);
          else
            DestinationString.Buffer = 0;
        }
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        AppContainerSidType = NtOpenDirectoryObject(&Handle, 2u, &ObjectAttributes);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( v32 )
        {
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v44;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          AppContainerSidType = NtOpenDirectoryObject(&v33, 2u, &ObjectAttributes);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          NtClose(Handle);
          Handle = v33;
          v33 = 0;
        }
        AppContainerSidType = RtlGetAppContainerSidType(*Heap, &v40);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( v40 == 2 )
        {
          AppContainerSidType = RtlConvertSidToUnicodeString(&UnicodeString, (PSID)*Heap, 1u);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &UnicodeString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v23 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
        }
        else
        {
          AppContainerSidType = RtlGetAppContainerParent(*Heap, &v42);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          v24 = RtlConvertSidToUnicodeString(&UnicodeString, v42, 1u);
          AppContainerSidType = v24;
          if ( v24 < 0 )
            goto LABEL_18;
          v30 = *RtlSubAuthoritySid((PSID)*Heap, 0xBu);
          v29 = *RtlSubAuthoritySid((PSID)*Heap, 0xAu);
          v28 = *RtlSubAuthoritySid((PSID)*Heap, 9u);
          LODWORD(ReturnLengthb) = *RtlSubAuthoritySid((PSID)*Heap, 8u);
          AppContainerSidType = RtlStringCchPrintfW(
                                  v51,
                                  260,
                                  L"%s\\%u-%u-%u-%u",
                                  UnicodeString.Buffer,
                                  ReturnLengthb,
                                  v28,
                                  v29,
                                  v30);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          RtlInitUnicodeString(&v46, v51);
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v46;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v23 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
          v5 = v41;
        }
        AppContainerSidType = v23;
        goto LABEL_58;
      }
      if ( v22 != -1073741789 )
        goto LABEL_18;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      if ( Heap )
      {
        AppContainerSidType = NtQueryInformationToken(
                                TokenHandle,
                                TokenAppContainerSid,
                                Heap,
                                TokenInformationLength,
                                &TokenInformationLength);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        goto LABEL_47;
      }
    }
    AppContainerSidType = -1073741670;
    goto LABEL_18;
  }
  if ( v10 )
  {
    v12 = TokenInformation;
  }
  else
  {
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
    v12 = TokenInformation;
    if ( TokenInformation == CurrentServiceSessionId )
    {
      v13 = 2147483646;
      v14 = L"\\BaseNamedObjects";
      v15 = 256;
      v16 = SourceString;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v16 - 1;
      if ( v15 )
        v17 = v16;
      AppContainerSidType = v15 == 0 ? 0x80000005 : 0;
      *v17 = 0;
      goto LABEL_17;
    }
  }
  LODWORD(ReturnLength) = v12;
  AppContainerSidType = RtlStringCchPrintfW(
                          SourceString,
                          256,
                          L"%ws\\%ld\\BaseNamedObjects",
                          L"\\Sessions",
                          ReturnLength);
LABEL_17:
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  if ( v32 )
  {
    if ( a2 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
    }
    else
    {
      DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 2544);
      if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
        DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                         + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                         - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                     - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                     + 2536)
                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr);
      else
        DestinationString.Buffer = 0;
    }
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AppContainerSidType = NtOpenDirectoryObject(&Handle, 2u, &ObjectAttributes);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    ObjectAttributes.RootDirectory = Handle;
    p_DestinationString = &v44;
  }
  else
  {
    if ( a2 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
    }
    else
    {
      DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 32);
      if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
        DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                         + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                         - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                     - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                     + 2536)
                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr);
      else
        DestinationString.Buffer = 0;
    }
    ObjectAttributes.RootDirectory = 0;
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.ObjectName = p_DestinationString;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  AppContainerSidType = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
  if ( AppContainerSidType >= 0 )
    goto LABEL_37;
  AppContainerSidType = NtOpenDirectoryObject(&v33, 2u, &ObjectAttributes);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  ObjectAttributes.RootDirectory = v33;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180198D48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  AppContainerSidType = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
  NtClose(v33);
  v33 = 0;
LABEL_58:
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
LABEL_37:
  if ( !v5 )
  {
LABEL_40:
    v20 = FileHandle;
LABEL_41:
    FileHandle = 0;
    *v45 = v20;
    goto LABEL_18;
  }
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenIsRestricted|TokenOwner,
                          &v49,
                          0x120u,
                          &TokenInformationLength);
  if ( AppContainerSidType >= 0 )
  {
    if ( !v50 )
      goto LABEL_40;
    RtlInitUnicodeString(&DestinationString, v49);
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AppContainerSidType = NtOpenDirectoryObject(&v33, 0xFu, &ObjectAttributes);
    if ( AppContainerSidType >= 0 )
    {
      NtClose(FileHandle);
      v20 = v33;
      v33 = 0;
      goto LABEL_41;
    }
  }
LABEL_18:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v42 )
    RtlFreeSid(v42);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v44.Buffer )
    RtlFreeUnicodeString(&v44);
  return (unsigned int)AppContainerSidType;
}

```

## disassembly

```asm
0x18006e604  push    rbp
0x18006e606  push    rbx
0x18006e607  push    rsi
0x18006e608  push    rdi
0x18006e609  push    r12
0x18006e60b  push    r13
0x18006e60d  push    r14
0x18006e60f  push    r15
0x18006e611  lea     rbp, [rsp-5A8h]
0x18006e619  sub     rsp, 6A8h
0x18006e620  mov     rax, cs:__security_cookie
0x18006e627  xor     rax, rsp
0x18006e62a  mov     [rbp+5E0h+var_50], rax
0x18006e631  mov     rax, [rbp+5E0h+arg_20]
0x18006e638  xorps   xmm0, xmm0
0x18006e63b  xor     r15d, r15d
0x18006e63e  mov     [rbp+5E0h+var_600], rax
0x18006e642  mov     esi, r8d
0x18006e645  mov     [rbp+5E0h+var_630], r8d
0x18006e649  mov     edi, edx
0x18006e64b  mov     [rbp+5E0h+var_638], r15d
0x18006e64f  mov     r13, rcx
0x18006e652  mov     [rsp+6E0h+TokenInformationLength], r15d
0x18006e657  xorps   xmm1, xmm1
0x18006e65a  mov     [rbp+5E0h+var_634], r15d
0x18006e65e  movups  xmmword ptr [rbp+5E0h+ObjectAttributes.ObjectName], xmm0
0x18006e662  xor     eax, eax
0x18006e664  lea     rcx, [rbp+5E0h+var_260]; void *
0x18006e66b  xor     edx, edx; Val
0x18006e66d  mov     r8d, 208h; Size
0x18006e673  movups  xmmword ptr [rsp+6E0h+ObjectAttributes.Length], xmm0
0x18006e678  movups  xmmword ptr [rbp+5E0h+ObjectAttributes+1Ch], xmm0
0x18006e67c  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x18006e681  movups  xmmword ptr [rbp+5E0h+UnicodeString.Length], xmm1
0x18006e685  call    memset_0
0x18006e68a  xorps   xmm0, xmm0
0x18006e68d  lea     rcx, [rbp+5E0h+SourceString]; void *
0x18006e691  xorps   xmm1, xmm1
0x18006e694  xor     edx, edx; Val
0x18006e696  mov     r8d, 200h; Size
0x18006e69c  movups  xmmword ptr [rbp+5E0h+var_5F8.Length], xmm0
0x18006e6a0  movups  xmmword ptr [rbp+5E0h+var_610.Length], xmm1
0x18006e6a4  call    memset_0
0x18006e6a9  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18006e6ae  mov     [rsp+6E0h+TokenInformation], r15d
0x18006e6b3  lea     r14d, [r15+4]
0x18006e6b7  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18006e6bc  mov     r9d, r14d; TokenInformationLength
0x18006e6bf  mov     [rsp+6E0h+var_69C], r15d
0x18006e6c4  lea     r8, [rsp+6E0h+TokenInformation]; TokenInformation
0x18006e6c9  mov     [rsp+6E0h+Handle], r15
0x18006e6ce  lea     edx, [r15+0Ch]; TokenInformationClass
0x18006e6d2  mov     [rsp+6E0h+var_698], r15
0x18006e6d7  mov     rcx, r13; TokenHandle
0x18006e6da  mov     [rsp+6E0h+FileHandle], r15
0x18006e6df  mov     r12d, r15d
0x18006e6e2  mov     [rbp+5E0h+var_628], r15
0x18006e6e6  call    cs:__imp_NtQueryInformationToken
0x18006e6ec  mov     ebx, eax
0x18006e6ee  test    eax, eax
0x18006e6f0  js      loc_18006E7F8
0x18006e6f6  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18006e6fb  mov     [rbp+5E0h+var_638], r15d
0x18006e6ff  mov     r9d, r14d; TokenInformationLength
0x18006e702  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18006e707  lea     r8, [rbp+5E0h+var_638]; TokenInformation
0x18006e70b  mov     rcx, r13; TokenHandle
0x18006e70e  lea     edx, [r15+1Dh]; TokenInformationClass
0x18006e712  call    cs:__imp_NtQueryInformationToken
0x18006e718  mov     ebx, eax
0x18006e71a  test    eax, eax
0x18006e71c  js      loc_18006E7F8
0x18006e722  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18006e727  mov     r9d, r14d; TokenInformationLength
0x18006e72a  lea     r8, [rsp+6E0h+var_69C]; TokenInformation
0x18006e72f  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18006e734  lea     edx, [r15+2Ah]; TokenInformationClass
0x18006e738  mov     rcx, r13; TokenHandle
0x18006e73b  call    cs:__imp_NtQueryInformationToken
0x18006e741  mov     ebx, eax
0x18006e743  test    eax, eax
0x18006e745  js      loc_18006E7F8
0x18006e74b  mov     eax, [rsp+6E0h+var_69C]
0x18006e74f  test    eax, eax
0x18006e751  jnz     loc_18006ED73
0x18006e757  cmp     [rbp+5E0h+var_638], r15d
0x18006e75b  jnz     loc_18006E9FD
0x18006e761  test    eax, eax
0x18006e763  jnz     short loc_18006E7CA
0x18006e765  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18006e76b  mov     ecx, [rsp+6E0h+TokenInformation]
0x18006e76f  cmp     ecx, eax
0x18006e771  jnz     short loc_18006E7CE
0x18006e773  mov     ecx, 7FFFFFFEh
0x18006e778  lea     r8, aBasenamedobjec; "\\BaseNamedObjects"
0x18006e77f  mov     edx, 100h
0x18006e784  lea     rax, [rbp+5E0h+SourceString]
0x18006e788  test    rcx, rcx
0x18006e78b  jz      short loc_18006E7AC
0x18006e78d  movzx   r9d, word ptr [r8]
0x18006e791  test    r9w, r9w
0x18006e795  jz      short loc_18006E7AC
0x18006e797  mov     [rax], r9w
0x18006e79b  add     r8, 2
0x18006e79f  add     rax, 2
0x18006e7a3  dec     rcx
0x18006e7a6  sub     rdx, 1
0x18006e7aa  jnz     short loc_18006E788
0x18006e7ac  test    rdx, rdx
0x18006e7af  lea     rcx, [rax-2]
0x18006e7b3  cmovnz  rcx, rax
0x18006e7b7  neg     rdx
0x18006e7ba  sbb     ebx, ebx
0x18006e7bc  not     ebx
0x18006e7be  and     ebx, 80000005h
0x18006e7c4  mov     [rcx], r15w
0x18006e7c8  jmp     short loc_18006E7F0
0x18006e7ca  mov     ecx, [rsp+6E0h+TokenInformation]
0x18006e7ce  mov     dword ptr [rsp+6E0h+ReturnLength], ecx
0x18006e7d2  lea     r9, aSessions; "\\Sessions"
0x18006e7d9  lea     rcx, [rbp+5E0h+SourceString]
0x18006e7dd  mov     edx, 100h
0x18006e7e2  lea     r8, aWsLdBasenamedo_0; "%ws\\%ld\\BaseNamedObjects"
0x18006e7e9  call    RtlStringCchPrintfW
0x18006e7ee  mov     ebx, eax
0x18006e7f0  test    ebx, ebx
0x18006e7f2  jns     loc_18006E87F
0x18006e7f8  cmp     [rbp+5E0h+UnicodeString.Buffer], r15
0x18006e7fc  jz      short loc_18006E808
0x18006e7fe  lea     rcx, [rbp+5E0h+UnicodeString]; UnicodeString
0x18006e802  call    cs:__imp_RtlFreeUnicodeString
0x18006e808  mov     rcx, [rsp+6E0h+FileHandle]; Handle
0x18006e80d  test    rcx, rcx
0x18006e810  jnz     loc_18006EDFC
0x18006e816  mov     rcx, [rsp+6E0h+Handle]; Handle
0x18006e81b  test    rcx, rcx
0x18006e81e  jz      short loc_18006E826
0x18006e820  call    cs:__imp_NtClose
0x18006e826  mov     rcx, [rbp+5E0h+var_628]; Sid
0x18006e82a  test    rcx, rcx
0x18006e82d  jnz     loc_18006EE07
0x18006e833  test    r12, r12
0x18006e836  jz      short loc_18006E850
0x18006e838  mov     rcx, gs:60h
0x18006e841  mov     r8, r12; P
0x18006e844  xor     edx, edx; Flags
0x18006e846  mov     rcx, [rcx+30h]; HeapHandle
0x18006e84a  call    cs:__imp_RtlFreeHeap
0x18006e850  cmp     [rbp+5E0h+var_610.Buffer], r15
0x18006e854  jnz     loc_18006EE12
0x18006e85a  mov     eax, ebx
0x18006e85c  mov     rcx, [rbp+5E0h+var_50]
0x18006e863  xor     rcx, rsp; StackCookie
0x18006e866  call    __security_check_cookie
0x18006e86b  add     rsp, 6A8h
0x18006e872  pop     r15
0x18006e874  pop     r14
0x18006e876  pop     r13
0x18006e878  pop     r12
0x18006e87a  pop     rdi
0x18006e87b  pop     rsi
0x18006e87c  pop     rbx
0x18006e87d  pop     rbp
0x18006e87e  retn
0x18006e87f  cmp     [rsp+6E0h+var_69C], r15d
0x18006e884  jnz     loc_18006EC62
0x18006e88a  test    edi, edi
0x18006e88c  jnz     loc_18006E9E9
0x18006e892  mov     rax, cs:BaseStaticServerData
0x18006e899  movups  xmm0, xmmword ptr [rax+20h]
0x18006e89d  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x18006e8a2  psrldq  xmm0, 8
0x18006e8a7  movq    rax, xmm0
0x18006e8ac  test    rax, rax
0x18006e8af  jz      loc_18006ED4C
0x18006e8b5  mov     rax, gs:60h
0x18006e8be  mov     rcx, [rax+98h]
0x18006e8c5  mov     rax, gs:60h
0x18006e8ce  mov     r8, [rcx+8]
0x18006e8d2  sub     r8, [rax+380h]
0x18006e8d9  mov     rax, gs:60h
0x18006e8e2  mov     rdx, [rax+88h]
0x18006e8e9  mov     rax, gs:60h
0x18006e8f2  mov     rcx, [rax+98h]
0x18006e8f9  mov     rax, gs:60h
0x18006e902  mov     r9, [rcx+8]
0x18006e906  sub     r9, [r8+rdx+9E8h]
0x18006e90e  sub     r9, [rax+380h]
0x18006e915  mov     rax, gs:60h
0x18006e91e  add     r9, [rax+88h]
0x18006e925  add     [rsp+6E0h+DestinationString.Buffer], r9
0x18006e92a  mov     r14d, 30h ; '0'
0x18006e930  mov     [rbp+5E0h+ObjectAttributes.RootDirectory], r15
0x18006e934  lea     rax, [rsp+6E0h+DestinationString]
0x18006e939  lea     r15d, [r14+10h]
0x18006e93d  xorps   xmm0, xmm0
0x18006e940  mov     [rbp+5E0h+ObjectAttributes.ObjectName], rax
0x18006e944  lea     r8, [rsp+6E0h+ObjectAttributes]; ObjectAttributes
0x18006e949  mov     [rbp+5E0h+ObjectAttributes.Attributes], r15d
0x18006e94d  mov     edx, 0Fh; DesiredAccess
0x18006e952  mov     [rsp+6E0h+ObjectAttributes.Length], r14d
0x18006e957  lea     rcx, [rsp+6E0h+FileHandle]; FileHandle
0x18006e95c  movdqu  xmmword ptr [rbp+5E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006e961  call    cs:__imp_NtOpenDirectoryObject
0x18006e967  mov     ebx, eax
0x18006e969  test    eax, eax
0x18006e96b  js      short loc_18006E9C2
0x18006e96d  test    esi, esi
0x18006e96f  jz      short loc_18006E9A9
0x18006e971  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18006e976  mov     r9d, 120h; TokenInformationLength
0x18006e97c  lea     r8, [rbp+5E0h+var_380]; TokenInformation
0x18006e983  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18006e988  mov     edx, 2Ch ; ','; TokenInformationClass
0x18006e98d  mov     rcx, r13; TokenHandle
0x18006e990  call    cs:__imp_NtQueryInformationToken
0x18006e996  mov     ebx, eax
0x18006e998  test    eax, eax
0x18006e99a  js      short loc_18006E9E1
0x18006e99c  cmp     [rbp+5E0h+var_378], 0
0x18006e9a3  jnz     loc_18006ECD1
0x18006e9a9  mov     rax, [rsp+6E0h+FileHandle]
0x18006e9ae  xor     r15d, r15d
0x18006e9b1  mov     rcx, [rbp+5E0h+var_600]
0x18006e9b5  mov     [rsp+6E0h+FileHandle], r15
0x18006e9ba  mov     [rcx], rax
0x18006e9bd  jmp     loc_18006E7F8
0x18006e9c2  lea     r8, [rsp+6E0h+ObjectAttributes]; ObjectAttributes
0x18006e9c7  mov     edx, 2; DesiredAccess
0x18006e9cc  lea     rcx, [rsp+6E0h+var_698]; FileHandle
0x18006e9d1  call    cs:__imp_NtOpenDirectoryObject
0x18006e9d7  mov     ebx, eax
0x18006e9d9  test    eax, eax
0x18006e9db  jns     loc_18006EC14
0x18006e9e1  xor     r15d, r15d
0x18006e9e4  jmp     loc_18006E7F8
0x18006e9e9  lea     rdx, [rbp+5E0h+SourceString]; SourceString
0x18006e9ed  lea     rcx, [rsp+6E0h+DestinationString]; DestinationString
0x18006e9f2  call    cs:__imp_RtlInitUnicodeString
0x18006e9f8  jmp     loc_18006E92A
0x18006e9fd  mov     ecx, 0Ch; SubAuthorityCount
0x18006ea02  call    cs:__imp_RtlLengthRequiredSid
0x18006ea08  mov     rcx, gs:60h
0x18006ea11  xor     edx, edx; Flags
0x18006ea13  lea     ebx, [rax+8]
0x18006ea16  mov     rcx, [rcx+30h]; HeapHandle
0x18006ea1a  mov     r8d, ebx; Size
0x18006ea1d  call    cs:__imp_RtlAllocateHeap
0x18006ea23  mov     r12, rax
0x18006ea26  test    rax, rax
0x18006ea29  jz      loc_18006EDF2
0x18006ea2f  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18006ea34  mov     r14d, 1Fh
0x18006ea3a  mov     edx, r14d; TokenInformationClass
0x18006ea3d  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18006ea42  mov     r9d, ebx; TokenInformationLength
0x18006ea45  mov     r8, r12; TokenInformation
0x18006ea48  mov     rcx, r13; TokenHandle
0x18006ea4b  call    cs:__imp_NtQueryInformationToken
0x18006ea51  mov     ebx, eax
0x18006ea53  test    eax, eax
0x18006ea55  js      loc_1801907F0
0x18006ea5b  mov     eax, [rsp+6E0h+TokenInformation]
0x18006ea5f  lea     r9, aSessions; "\\Sessions"
0x18006ea66  lea     r8, aWsLdAppcontain_1; "%ws\\%ld\\AppContainerNamedObjects"
0x18006ea6d  mov     dword ptr [rsp+6E0h+ReturnLength], eax
0x18006ea71  mov     edx, 100h
0x18006ea76  lea     rcx, [rbp+5E0h+SourceString]
0x18006ea7a  call    RtlStringCchPrintfW
0x18006ea7f  mov     ebx, eax
0x18006ea81  test    eax, eax
0x18006ea83  js      loc_18006E7F8
0x18006ea89  test    edi, edi
0x18006ea8b  jnz     loc_18006EC00
0x18006ea91  mov     rax, cs:BaseStaticServerData
0x18006ea98  movups  xmm0, xmmword ptr [rax+9D8h]
0x18006ea9f  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x18006eaa4  psrldq  xmm0, 8
0x18006eaa9  movq    rax, xmm0
0x18006eaae  test    rax, rax
0x18006eab1  jz      loc_18006ED42
0x18006eab7  mov     rax, gs:60h
0x18006eac0  mov     rcx, [rax+98h]
0x18006eac7  mov     rax, gs:60h
0x18006ead0  mov     r8, [rcx+8]
0x18006ead4  sub     r8, [rax+380h]
0x18006eadb  mov     rax, gs:60h
0x18006eae4  mov     rdx, [rax+88h]
0x18006eaeb  mov     rax, gs:60h
0x18006eaf4  mov     rcx, [rax+98h]
0x18006eafb  mov     rax, gs:60h
0x18006eb04  mov     r9, [rcx+8]
0x18006eb08  sub     r9, [r8+rdx+9E8h]
0x18006eb10  sub     r9, [rax+380h]
0x18006eb17  mov     rax, gs:60h
0x18006eb20  add     r9, [rax+88h]
0x18006eb27  add     [rsp+6E0h+DestinationString.Buffer], r9
0x18006eb2c  mov     r14d, 30h ; '0'
0x18006eb32  mov     [rbp+5E0h+ObjectAttributes.RootDirectory], r15
0x18006eb36  lea     rax, [rsp+6E0h+DestinationString]
  ... truncated ...
```
