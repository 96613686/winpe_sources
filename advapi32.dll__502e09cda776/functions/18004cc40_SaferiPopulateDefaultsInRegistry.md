# SaferiPopulateDefaultsInRegistry

- ea: `0x18004cc40`
- end: `0x18004d34f`
- name: `SaferiPopulateDefaultsInRegistry`
- size: `1807`
- prototype: `__int64 __fastcall(void *, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18004c398`
- `0x18004cc40`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004cda9`
- `ntdll!NtOpenKey` at `0x18004cda9`
- `ntdll!NtQueryValueKey` at `0x18004ce44`
- `ntdll!NtQueryValueKey` at `0x18004ce94`
- `ntdll!NtQueryValueKey` at `0x18004cee4`
- `ntdll!NtQueryValueKey` at `0x18004cf30`
- `ntdll!NtQueryValueKey` at `0x18004ce44`
- `ntdll!NtQueryValueKey` at `0x18004ce94`
- `ntdll!NtQueryValueKey` at `0x18004cee4`
- `ntdll!NtQueryValueKey` at `0x18004cf30`
- `ntdll!NtClose` at `0x18004d301`
- `ntdll!NtClose` at `0x18004d301`
- `ntdll!NtCreateKey` at `0x18004cdee`
- `ntdll!NtCreateKey` at `0x18004cdee`
- `ntdll!NtSetValueKey` at `0x18004cf94`
- `ntdll!NtSetValueKey` at `0x18004cfe5`
- `ntdll!NtSetValueKey` at `0x18004d039`
- `ntdll!NtSetValueKey` at `0x18004d179`
- `ntdll!NtSetValueKey` at `0x18004cf94`
- `ntdll!NtSetValueKey` at `0x18004cfe5`
- `ntdll!NtSetValueKey` at `0x18004d039`
- `ntdll!NtSetValueKey` at `0x18004d179`
- `ntdll!RtlFreeHeap` at `0x18004d197`
- `ntdll!RtlFreeHeap` at `0x18004d197`
- `ntdll!RtlAllocateHeap` at `0x18004d07e`
- `ntdll!RtlAllocateHeap` at `0x18004d07e`
- `ntdll!RtlInitUnicodeString` at `0x18004cd69`
- `ntdll!RtlInitUnicodeString` at `0x18004ce10`
- `ntdll!RtlInitUnicodeString` at `0x18004ce65`
- `ntdll!RtlInitUnicodeString` at `0x18004ceb5`
- `ntdll!RtlInitUnicodeString` at `0x18004cf01`
- `ntdll!RtlInitUnicodeString` at `0x18004cf5a`
- `ntdll!RtlInitUnicodeString` at `0x18004cfbb`
- `ntdll!RtlInitUnicodeString` at `0x18004d00f`
- `ntdll!RtlInitUnicodeString` at `0x18004d05b`
- `ntdll!RtlInitUnicodeString` at `0x18004d1dd`
- `ntdll!RtlInitUnicodeString` at `0x18004d27d`
- `ntdll!RtlInitUnicodeString` at `0x18004cd69`
- `ntdll!RtlInitUnicodeString` at `0x18004ce10`
- `ntdll!RtlInitUnicodeString` at `0x18004ce65`
- `ntdll!RtlInitUnicodeString` at `0x18004ceb5`
- `ntdll!RtlInitUnicodeString` at `0x18004cf01`
- `ntdll!RtlInitUnicodeString` at `0x18004cf5a`
- `ntdll!RtlInitUnicodeString` at `0x18004cfbb`
- `ntdll!RtlInitUnicodeString` at `0x18004d00f`
- `ntdll!RtlInitUnicodeString` at `0x18004d05b`
- `ntdll!RtlInitUnicodeString` at `0x18004d1dd`
- `ntdll!RtlInitUnicodeString` at `0x18004d27d`
- `KERNEL32!BaseSetLastNTError` at `0x18004d318`
- `KERNEL32!BaseSetLastNTError` at `0x18004d318`

## pseudocode

```c
__int64 __fastcall SaferiPopulateDefaultsInRegistry(void *a1, _DWORD *a2)
{
  NTSTATUS v4; // ebx
  _OWORD *Heap; // rax
  void *v6; // rbx
  int Data; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v14[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v15; // [rsp+B8h] [rbp-48h]
  int v16; // [rsp+BCh] [rbp-44h]
  int v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C4h] [rbp-3Ch]
  __int16 v19; // [rsp+D0h] [rbp-30h]
  const WCHAR *v20; // [rsp+2D0h] [rbp+1D0h]
  int v21; // [rsp+2D8h] [rbp+1D8h]
  int v22; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v23; // [rsp+2E4h] [rbp+1E4h]
  int v24; // [rsp+2E8h] [rbp+1E8h]
  int v25; // [rsp+2ECh] [rbp+1ECh]
  int v26; // [rsp+2F0h] [rbp+1F0h]
  int v27; // [rsp+2F4h] [rbp+1F4h]
  int v28; // [rsp+2F8h] [rbp+1F8h]
  int v29; // [rsp+300h] [rbp+200h]
  struct _UNICODE_STRING v30; // [rsp+308h] [rbp+208h] BYREF
  int v31; // [rsp+318h] [rbp+218h]
  WCHAR SourceString[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE KeyValueInformation[80]; // [rsp+420h] [rbp+320h] BYREF

  Data = 0;
  ValueName = 0;
  wcscpy(SourceString, L"Software\\Policies\\Microsoft\\Windows\\Safer\\CodeIdentifirs");
  DestinationString = 0;
  KeyHandle = 0;
  SourceString[58] = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(&v22, 0, 0xB8u);
  memset_0(v14, 0, 0x230u);
  ResultLength = 0;
  if ( a1 && a2 )
  {
    *a2 = 1;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
    if ( v4 == -1073741772 )
      v4 = NtCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&ValueName, L"DefaultLevel");
      if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x50u, &ResultLength) == -1073741772
        || (RtlInitUnicodeString(&ValueName, L"TransparentEnabled"),
            NtQueryValueKey(
              KeyHandle,
              &ValueName,
              KeyValuePartialInformation,
              KeyValueInformation,
              0x50u,
              &ResultLength) == -1073741772)
        || (RtlInitUnicodeString(&ValueName, L"PolicyScope"),
            NtQueryValueKey(
              KeyHandle,
              &ValueName,
              KeyValuePartialInformation,
              KeyValueInformation,
              0x50u,
              &ResultLength) == -1073741772)
        || (RtlInitUnicodeString(&ValueName, L"ExecutableTypes"),
            v4 = NtQueryValueKey(
                   KeyHandle,
                   &ValueName,
                   KeyValuePartialInformation,
                   KeyValueInformation,
                   0x50u,
                   &ResultLength),
            v4 == -1073741772) )
      {
        RtlInitUnicodeString(&ValueName, L"DefaultLevel");
        Data = 0x40000;
        v4 = NtSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
        if ( v4 >= 0 )
        {
          Data = 1;
          RtlInitUnicodeString(&ValueName, L"TransparentEnabled");
          v4 = NtSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
          if ( v4 >= 0 )
          {
            Data = 0;
            RtlInitUnicodeString(&ValueName, L"PolicyScope");
            v4 = NtSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
            if ( v4 >= 0 )
            {
              RtlInitUnicodeString(&ValueName, L"ExecutableTypes");
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xF8u);
              v6 = Heap;
              if ( Heap )
              {
                *Heap = *(_OWORD *)L"ADE";
                Heap[1] = xmmword_180088A40;
                Heap[2] = xmmword_180088A50;
                Heap[3] = xmmword_180088A60;
                Heap[4] = xmmword_180088A70;
                Heap[5] = xmmword_180088A80;
                Heap[6] = xmmword_180088A90;
                Heap[7] = xmmword_180088AA0;
                Heap[8] = xmmword_180088AB0;
                Heap[9] = xmmword_180088AC0;
                Heap[10] = xmmword_180088AD0;
                Heap[11] = xmmword_180088AE0;
                Heap[12] = xmmword_180088AF0;
                Heap[13] = xmmword_180088B00;
                Heap[14] = xmmword_180088B10;
                *((_QWORD *)Heap + 30) = 4390995;
                NtSetValueKey(KeyHandle, &ValueName, 0, 7u, Heap, 0xF8u);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
                v26 = 1;
                v27 = 0x40000;
                v28 = 3;
                v29 = 1;
                v31 = 0;
                RtlInitUnicodeString(
                  &v30,
                  L"%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SystemRoot%");
                v23 = 1243083328;
                v22 = 421320698;
                v15 = 421320698;
                v24 = -728463735;
                v25 = -892819840;
                v14[1] = 32;
                v14[0] = 1;
                v16 = 1243083328;
                v17 = -728463735;
                v18 = -892819840;
                v21 = 0;
                v20 = L"%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SystemRoot%";
                v19 = 0;
                v4 = SaferpSetSingleIdentificationPath(421320449, &v22, v14, 0);
                if ( v4 >= 0 )
                {
                  RtlInitUnicodeString(
                    &v30,
                    L"%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ProgramFilesDir%");
                  v23 = 1186091674;
                  v22 = -758953294;
                  v15 = -758953294;
                  v24 = -2047044686;
                  v25 = -361574849;
                  v16 = 1186091674;
                  v17 = -2047044686;
                  v18 = -361574849;
                  v20 = L"%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ProgramFilesDir%";
                  v4 = SaferpSetSingleIdentificationPath(3536013825LL, &v22, v14, 0);
                }
              }
              else
              {
                v4 = -1073741801;
              }
            }
          }
        }
      }
      else
      {
        *a2 = 0;
      }
    }
  }
  else
  {
    v4 = -1073741811;
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v4 >= 0 )
    return 1;
  BaseSetLastNTError((unsigned int)v4);
  return 0;
}

```

## disassembly

```asm
0x18004cc40  mov     [rsp-8+arg_10], rbx
0x18004cc45  mov     [rsp-8+arg_18], rdi
0x18004cc4a  push    rbp
0x18004cc4b  push    r12
0x18004cc4d  push    r14
0x18004cc4f  lea     rbp, [rsp-380h]
0x18004cc57  sub     rsp, 480h
0x18004cc5e  mov     rax, cs:__security_cookie
0x18004cc65  xor     rax, rsp
0x18004cc68  mov     [rbp+390h+var_20], rax
0x18004cc6f  xorps   xmm0, xmm0
0x18004cc72  mov     [rsp+490h+Data], 0
0x18004cc7a  movups  xmmword ptr [rsp+490h+ValueName.Length], xmm0
0x18004cc7f  mov     rdi, rdx
0x18004cc82  mov     rbx, rcx
0x18004cc85  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18004cc8c  xorps   xmm1, xmm1
0x18004cc8f  movaps  xmmword ptr [rbp+390h+SourceString], xmm0
0x18004cc96  lea     rcx, [rbp+390h+var_1B0]; void *
0x18004cc9d  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+20h; "s\\Microsoft\\Windows\\Safer\\CodeIdent"...
0x18004cca4  xor     eax, eax
0x18004cca6  movups  xmmword ptr [rbp+390h+DestinationString.Length], xmm1
0x18004ccaa  xor     edx, edx; Val
0x18004ccac  mov     r8d, 0B8h; Size
0x18004ccb2  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+10h; "\\Policies\\Microsoft\\Windows\\Safer\\"...
0x18004ccb9  movaps  [rbp+390h+var_D0], xmm0
0x18004ccc0  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+40h; "ows\\Safer\\CodeIdentifiers"
0x18004ccc7  movaps  [rbp+390h+var_E0], xmm1
0x18004ccce  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+30h; "oft\\Windows\\Safer\\CodeIdentifiers"
0x18004ccd5  movaps  [rbp+390h+var_B0], xmm0
0x18004ccdc  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+60h; "entifiers"
0x18004cce3  movaps  [rbp+390h+var_C0], xmm1
0x18004ccea  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+50h; "r\\CodeIdentifiers"
0x18004ccf1  movaps  [rbp+390h+var_90], xmm0
0x18004ccf8  xorps   xmm0, xmm0
0x18004ccfb  movaps  [rbp+390h+var_A0], xmm1
0x18004cd02  movsd   xmm1, qword ptr cs:aSoftwarePolici_1+6Eh; "rs"
0x18004cd0a  movups  xmmword ptr [rsp+490h+ObjectAttributes.ObjectName], xmm0
0x18004cd0f  mov     [rsp+490h+KeyHandle], rax
0x18004cd14  movups  xmmword ptr [rbp+390h+ObjectAttributes+1Ch], xmm0
0x18004cd18  movsd   qword ptr [rbp+390h+var_90+0Eh], xmm1
0x18004cd20  movups  xmmword ptr [rsp+490h+ObjectAttributes.Length], xmm0
0x18004cd25  call    memset_0
0x18004cd2a  xor     edx, edx; Val
0x18004cd2c  lea     rcx, [rbp+390h+var_3E0]; void *
0x18004cd30  mov     r8d, 230h; Size
0x18004cd36  call    memset_0
0x18004cd3b  mov     [rsp+490h+ResultLength], 0
0x18004cd43  mov     r12d, 1
0x18004cd49  test    rbx, rbx
0x18004cd4c  jz      loc_18004D2F2
0x18004cd52  test    rdi, rdi
0x18004cd55  jz      loc_18004D2F2
0x18004cd5b  lea     rdx, [rbp+390h+SourceString]; SourceString
0x18004cd62  mov     [rdi], r12d
0x18004cd65  lea     rcx, [rbp+390h+DestinationString]; DestinationString
0x18004cd69  call    cs:__imp_RtlInitUnicodeString
0x18004cd70  nop     dword ptr [rax+rax+00h]
0x18004cd75  lea     rax, [rbp+390h+DestinationString]
0x18004cd79  mov     [rsp+490h+ObjectAttributes.Length], 30h ; '0'
0x18004cd81  xorps   xmm0, xmm0
0x18004cd84  mov     [rsp+490h+ObjectAttributes.ObjectName], rax
0x18004cd89  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x18004cd8e  mov     [rsp+490h+ObjectAttributes.RootDirectory], rbx
0x18004cd93  mov     edx, 2001Fh; DesiredAccess
0x18004cd98  mov     [rbp+390h+ObjectAttributes.Attributes], 40h ; '@'
0x18004cd9f  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cda4  movdqu  xmmword ptr [rbp+390h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004cda9  call    cs:__imp_NtOpenKey
0x18004cdb0  nop     dword ptr [rax+rax+00h]
0x18004cdb5  mov     r14d, 0C0000034h
0x18004cdbb  mov     ebx, eax
0x18004cdbd  cmp     eax, r14d
0x18004cdc0  jnz     short loc_18004CDFC
0x18004cdc2  mov     [rsp+490h+Disposition], 0; Disposition
0x18004cdcb  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x18004cdd0  mov     [rsp+490h+CreateOptions], 0; CreateOptions
0x18004cdd8  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cddd  xor     r9d, r9d; TitleIndex
0x18004cde0  mov     [rsp+490h+Class], 0; Class
0x18004cde9  mov     edx, 2001Fh; DesiredAccess
0x18004cdee  call    cs:__imp_NtCreateKey
0x18004cdf5  nop     dword ptr [rax+rax+00h]
0x18004cdfa  mov     ebx, eax
0x18004cdfc  test    ebx, ebx
0x18004cdfe  js      loc_18004D2F7
0x18004ce04  lea     rdx, aDefaultlevel; "DefaultLevel"
0x18004ce0b  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004ce10  call    cs:__imp_RtlInitUnicodeString
0x18004ce17  nop     dword ptr [rax+rax+00h]
0x18004ce1c  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004ce21  lea     rax, [rsp+490h+ResultLength]
0x18004ce26  mov     ebx, 50h ; 'P'
0x18004ce2b  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x18004ce30  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x18004ce37  mov     dword ptr [rsp+490h+Class], ebx; Length
0x18004ce3b  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004ce40  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004ce44  call    cs:__imp_NtQueryValueKey
0x18004ce4b  nop     dword ptr [rax+rax+00h]
0x18004ce50  cmp     eax, r14d
0x18004ce53  jz      loc_18004CF4E
0x18004ce59  lea     rdx, aTransparentena; "TransparentEnabled"
0x18004ce60  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004ce65  call    cs:__imp_RtlInitUnicodeString
0x18004ce6c  nop     dword ptr [rax+rax+00h]
0x18004ce71  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004ce76  lea     rax, [rsp+490h+ResultLength]
0x18004ce7b  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x18004ce80  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x18004ce87  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004ce8b  mov     dword ptr [rsp+490h+Class], ebx; Length
0x18004ce8f  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004ce94  call    cs:__imp_NtQueryValueKey
0x18004ce9b  nop     dword ptr [rax+rax+00h]
0x18004cea0  cmp     eax, r14d
0x18004cea3  jz      loc_18004CF4E
0x18004cea9  lea     rdx, aPolicyscope; "PolicyScope"
0x18004ceb0  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004ceb5  call    cs:__imp_RtlInitUnicodeString
0x18004cebc  nop     dword ptr [rax+rax+00h]
0x18004cec1  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cec6  lea     rax, [rsp+490h+ResultLength]
0x18004cecb  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x18004ced0  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x18004ced7  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004cedb  mov     dword ptr [rsp+490h+Class], ebx; Length
0x18004cedf  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004cee4  call    cs:__imp_NtQueryValueKey
0x18004ceeb  nop     dword ptr [rax+rax+00h]
0x18004cef0  cmp     eax, r14d
0x18004cef3  jz      short loc_18004CF4E
0x18004cef5  lea     rdx, aExecutabletype; "ExecutableTypes"
0x18004cefc  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004cf01  call    cs:__imp_RtlInitUnicodeString
0x18004cf08  nop     dword ptr [rax+rax+00h]
0x18004cf0d  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cf12  lea     rax, [rsp+490h+ResultLength]
0x18004cf17  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x18004cf1c  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x18004cf23  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004cf27  mov     dword ptr [rsp+490h+Class], ebx; Length
0x18004cf2b  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004cf30  call    cs:__imp_NtQueryValueKey
0x18004cf37  nop     dword ptr [rax+rax+00h]
0x18004cf3c  mov     ebx, eax
0x18004cf3e  cmp     eax, r14d
0x18004cf41  jz      short loc_18004CF4E
0x18004cf43  mov     dword ptr [rdi], 0
0x18004cf49  jmp     loc_18004D2F7
0x18004cf4e  lea     rdx, aDefaultlevel; "DefaultLevel"
0x18004cf55  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004cf5a  call    cs:__imp_RtlInitUnicodeString
0x18004cf61  nop     dword ptr [rax+rax+00h]
0x18004cf66  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cf6b  lea     rax, [rsp+490h+Data]
0x18004cf70  mov     edi, 4
0x18004cf75  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004cf7a  mov     r14d, 40000h
0x18004cf80  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004cf84  mov     r9d, edi; Type
0x18004cf87  mov     [rsp+490h+Class], rax; Data
0x18004cf8c  xor     r8d, r8d; TitleIndex
0x18004cf8f  mov     [rsp+490h+Data], r14d
0x18004cf94  call    cs:__imp_NtSetValueKey
0x18004cf9b  nop     dword ptr [rax+rax+00h]
0x18004cfa0  mov     ebx, eax
0x18004cfa2  test    eax, eax
0x18004cfa4  js      loc_18004D2F7
0x18004cfaa  lea     rdx, aTransparentena; "TransparentEnabled"
0x18004cfb1  mov     [rsp+490h+Data], r12d
0x18004cfb6  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004cfbb  call    cs:__imp_RtlInitUnicodeString
0x18004cfc2  nop     dword ptr [rax+rax+00h]
0x18004cfc7  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004cfcc  lea     rax, [rsp+490h+Data]
0x18004cfd1  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004cfd5  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004cfda  mov     r9d, edi; Type
0x18004cfdd  mov     [rsp+490h+Class], rax; Data
0x18004cfe2  xor     r8d, r8d; TitleIndex
0x18004cfe5  call    cs:__imp_NtSetValueKey
0x18004cfec  nop     dword ptr [rax+rax+00h]
0x18004cff1  mov     ebx, eax
0x18004cff3  test    eax, eax
0x18004cff5  js      loc_18004D2F7
0x18004cffb  lea     rdx, aPolicyscope; "PolicyScope"
0x18004d002  mov     [rsp+490h+Data], 0
0x18004d00a  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004d00f  call    cs:__imp_RtlInitUnicodeString
0x18004d016  nop     dword ptr [rax+rax+00h]
0x18004d01b  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004d020  lea     rax, [rsp+490h+Data]
0x18004d025  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004d029  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004d02e  mov     r9d, edi; Type
0x18004d031  mov     [rsp+490h+Class], rax; Data
0x18004d036  xor     r8d, r8d; TitleIndex
0x18004d039  call    cs:__imp_NtSetValueKey
0x18004d040  nop     dword ptr [rax+rax+00h]
0x18004d045  mov     ebx, eax
0x18004d047  test    eax, eax
0x18004d049  js      loc_18004D2F7
0x18004d04f  lea     rdx, aExecutabletype; "ExecutableTypes"
0x18004d056  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004d05b  call    cs:__imp_RtlInitUnicodeString
0x18004d062  nop     dword ptr [rax+rax+00h]
0x18004d067  mov     rcx, gs:60h
0x18004d070  mov     edi, 0F8h
0x18004d075  mov     r8d, edi; Size
0x18004d078  xor     edx, edx; Flags
0x18004d07a  mov     rcx, [rcx+30h]; HeapHandle
0x18004d07e  call    cs:__imp_RtlAllocateHeap
0x18004d085  nop     dword ptr [rax+rax+00h]
0x18004d08a  mov     rbx, rax
0x18004d08d  test    rax, rax
0x18004d090  jz      loc_18004D2EB
0x18004d096  movaps  xmm0, xmmword ptr cs:aAde; "ADE"
0x18004d09d  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004d0a2  movups  xmmword ptr [rax], xmm0
0x18004d0a5  mov     r9d, 7; Type
0x18004d0ab  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004d0af  movaps  xmm1, cs:xmmword_180088A40
0x18004d0b6  xor     r8d, r8d; TitleIndex
0x18004d0b9  movups  xmmword ptr [rax+10h], xmm1
0x18004d0bd  mov     [rsp+490h+Class], rbx; Data
0x18004d0c2  movaps  xmm0, cs:xmmword_180088A50
0x18004d0c9  movups  xmmword ptr [rax+20h], xmm0
0x18004d0cd  movaps  xmm1, cs:xmmword_180088A60
0x18004d0d4  movups  xmmword ptr [rax+30h], xmm1
0x18004d0d8  movaps  xmm0, cs:xmmword_180088A70
0x18004d0df  movups  xmmword ptr [rax+40h], xmm0
0x18004d0e3  movaps  xmm1, cs:xmmword_180088A80
0x18004d0ea  movups  xmmword ptr [rax+50h], xmm1
0x18004d0ee  movaps  xmm0, cs:xmmword_180088A90
0x18004d0f5  movups  xmmword ptr [rax+60h], xmm0
0x18004d0f9  movaps  xmm1, cs:xmmword_180088AA0
0x18004d100  movups  xmmword ptr [rax+70h], xmm1
0x18004d104  movaps  xmm0, cs:xmmword_180088AB0
0x18004d10b  movups  xmmword ptr [rax+80h], xmm0
0x18004d112  movaps  xmm1, cs:xmmword_180088AC0
0x18004d119  movups  xmmword ptr [rax+90h], xmm1
0x18004d120  movaps  xmm0, cs:xmmword_180088AD0
0x18004d127  movups  xmmword ptr [rax+0A0h], xmm0
0x18004d12e  movaps  xmm1, cs:xmmword_180088AE0
0x18004d135  movups  xmmword ptr [rax+0B0h], xmm1
0x18004d13c  movaps  xmm0, cs:xmmword_180088AF0
0x18004d143  movups  xmmword ptr [rax+0C0h], xmm0
0x18004d14a  movaps  xmm1, cs:xmmword_180088B00
0x18004d151  movups  xmmword ptr [rax+0D0h], xmm1
0x18004d158  movaps  xmm0, cs:xmmword_180088B10
0x18004d15f  movups  xmmword ptr [rax+0E0h], xmm0
0x18004d166  mov     rax, cs:qword_180088B20
0x18004d16d  mov     [rbx+0F0h], rax
0x18004d174  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004d179  call    cs:__imp_NtSetValueKey
0x18004d180  nop     dword ptr [rax+rax+00h]
0x18004d185  mov     rcx, gs:60h
0x18004d18e  mov     r8, rbx; P
0x18004d191  xor     edx, edx; Flags
0x18004d193  mov     rcx, [rcx+30h]; HeapHandle
0x18004d197  call    cs:__imp_RtlFreeHeap
0x18004d19e  nop     dword ptr [rax+rax+00h]
0x18004d1a3  lea     rbx, aHkeyLocalMachi_1; "%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsof"...
0x18004d1aa  mov     [rbp+390h+var_1A0], r12d
0x18004d1b1  mov     rdx, rbx; SourceString
0x18004d1b4  mov     [rbp+390h+var_19C], r14d
0x18004d1bb  lea     rcx, [rbp+390h+var_188]; DestinationString
0x18004d1c2  mov     [rbp+390h+var_198], 3
0x18004d1cc  mov     [rbp+390h+var_190], r12d
0x18004d1d3  mov     [rbp+390h+var_178], 0
0x18004d1dd  call    cs:__imp_RtlInitUnicodeString
0x18004d1e4  nop     dword ptr [rax+rax+00h]
0x18004d1e9  mov     ecx, 191CD7FAh
0x18004d1ee  mov     [rbp+390h+var_1AC], 4A17F240h
0x18004d1f8  mov     [rbp+390h+var_1B0], ecx
0x18004d1fe  lea     r8, [rbp+390h+var_3E0]
0x18004d202  mov     [rbp+390h+var_3D8], ecx
0x18004d205  lea     rdx, [rbp+390h+var_1B0]
0x18004d20c  xor     eax, eax
0x18004d20e  mov     [rbp+390h+var_1A8], 0D4948689h
0x18004d218  mov     cl, r12b
0x18004d21b  mov     [rbp+390h+var_1A4], 0CAC8A680h
0x18004d225  xor     r9d, r9d
0x18004d228  mov     [rbp+390h+var_3DC], 20h ; ' '
0x18004d22f  mov     [rbp+390h+var_3E0], r12d
0x18004d233  mov     [rbp+390h+var_3D4], 4A17F240h
0x18004d23a  mov     [rbp+390h+var_3D0], 0D4948689h
0x18004d241  mov     [rbp+390h+var_3CC], 0CAC8A680h
0x18004d248  mov     [rbp+390h+var_1B8], 0
0x18004d252  mov     [rbp+390h+var_1C0], rbx
0x18004d259  mov     [rbp+390h+var_3C0], ax
0x18004d25d  call    SaferpSetSingleIdentificationPath
0x18004d262  mov     ebx, eax
0x18004d264  test    eax, eax
0x18004d266  js      loc_18004D2F7
0x18004d26c  lea     rbx, aHkeyLocalMachi; "%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsof"...
0x18004d273  mov     rdx, rbx; SourceString
0x18004d276  lea     rcx, [rbp+390h+var_188]; DestinationString
0x18004d27d  call    cs:__imp_RtlInitUnicodeString
  ... truncated ...
```
