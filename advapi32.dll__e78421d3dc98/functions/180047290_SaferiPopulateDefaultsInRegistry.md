# SaferiPopulateDefaultsInRegistry

- ea: `0x180047290`
- end: `0x180047908`
- name: `SaferiPopulateDefaultsInRegistry`
- size: `1656`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180046b50`
- `0x180047290`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800473f3`
- `ntdll!NtOpenKey` at `0x1800473f3`
- `ntdll!NtQueryValueKey` at `0x18004747c`
- `ntdll!NtQueryValueKey` at `0x1800474c0`
- `ntdll!NtQueryValueKey` at `0x180047504`
- `ntdll!NtQueryValueKey` at `0x180047544`
- `ntdll!NtQueryValueKey` at `0x18004747c`
- `ntdll!NtQueryValueKey` at `0x1800474c0`
- `ntdll!NtQueryValueKey` at `0x180047504`
- `ntdll!NtQueryValueKey` at `0x180047544`
- `ntdll!NtClose` at `0x1800478c7`
- `ntdll!NtClose` at `0x1800478c7`
- `ntdll!NtCreateKey` at `0x180047432`
- `ntdll!NtCreateKey` at `0x180047432`
- `ntdll!NtSetValueKey` at `0x18004759c`
- `ntdll!NtSetValueKey` at `0x1800475e1`
- `ntdll!NtSetValueKey` at `0x180047629`
- `ntdll!NtSetValueKey` at `0x180047757`
- `ntdll!NtSetValueKey` at `0x18004759c`
- `ntdll!NtSetValueKey` at `0x1800475e1`
- `ntdll!NtSetValueKey` at `0x180047629`
- `ntdll!NtSetValueKey` at `0x180047757`
- `ntdll!RtlFreeHeap` at `0x18004776f`
- `ntdll!RtlFreeHeap` at `0x18004776f`
- `ntdll!RtlAllocateHeap` at `0x180047662`
- `ntdll!RtlAllocateHeap` at `0x180047662`
- `ntdll!RtlInitUnicodeString` at `0x1800473b9`
- `ntdll!RtlInitUnicodeString` at `0x18004744e`
- `ntdll!RtlInitUnicodeString` at `0x180047497`
- `ntdll!RtlInitUnicodeString` at `0x1800474db`
- `ntdll!RtlInitUnicodeString` at `0x18004751b`
- `ntdll!RtlInitUnicodeString` at `0x180047568`
- `ntdll!RtlInitUnicodeString` at `0x1800475bd`
- `ntdll!RtlInitUnicodeString` at `0x180047605`
- `ntdll!RtlInitUnicodeString` at `0x180047645`
- `ntdll!RtlInitUnicodeString` at `0x1800477af`
- `ntdll!RtlInitUnicodeString` at `0x180047849`
- `ntdll!RtlInitUnicodeString` at `0x1800473b9`
- `ntdll!RtlInitUnicodeString` at `0x18004744e`
- `ntdll!RtlInitUnicodeString` at `0x180047497`
- `ntdll!RtlInitUnicodeString` at `0x1800474db`
- `ntdll!RtlInitUnicodeString` at `0x18004751b`
- `ntdll!RtlInitUnicodeString` at `0x180047568`
- `ntdll!RtlInitUnicodeString` at `0x1800475bd`
- `ntdll!RtlInitUnicodeString` at `0x180047605`
- `ntdll!RtlInitUnicodeString` at `0x180047645`
- `ntdll!RtlInitUnicodeString` at `0x1800477af`
- `ntdll!RtlInitUnicodeString` at `0x180047849`
- `KERNEL32!BaseSetLastNTError` at `0x1800478d8`
- `KERNEL32!BaseSetLastNTError` at `0x1800478d8`

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
                Heap[1] = xmmword_18007A8B0;
                Heap[2] = xmmword_18007A8C0;
                Heap[3] = xmmword_18007A8D0;
                Heap[4] = xmmword_18007A8E0;
                Heap[5] = xmmword_18007A8F0;
                Heap[6] = xmmword_18007A900;
                Heap[7] = xmmword_18007A910;
                Heap[8] = xmmword_18007A920;
                Heap[9] = xmmword_18007A930;
                Heap[10] = xmmword_18007A940;
                Heap[11] = xmmword_18007A950;
                Heap[12] = xmmword_18007A960;
                Heap[13] = xmmword_18007A970;
                Heap[14] = xmmword_18007A980;
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
0x180047290  mov     [rsp-8+arg_10], rbx
0x180047295  mov     [rsp-8+arg_18], rdi
0x18004729a  push    rbp
0x18004729b  push    r12
0x18004729d  push    r14
0x18004729f  lea     rbp, [rsp-380h]
0x1800472a7  sub     rsp, 480h
0x1800472ae  mov     rax, cs:__security_cookie
0x1800472b5  xor     rax, rsp
0x1800472b8  mov     [rbp+390h+var_20], rax
0x1800472bf  xorps   xmm0, xmm0
0x1800472c2  mov     [rsp+490h+Data], 0
0x1800472ca  movups  xmmword ptr [rsp+490h+ValueName.Length], xmm0
0x1800472cf  mov     rdi, rdx
0x1800472d2  mov     rbx, rcx
0x1800472d5  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x1800472dc  xorps   xmm1, xmm1
0x1800472df  movaps  xmmword ptr [rbp+390h+SourceString], xmm0
0x1800472e6  lea     rcx, [rbp+390h+var_1B0]; void *
0x1800472ed  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+20h; "s\\Microsoft\\Windows\\Safer\\CodeIdent"...
0x1800472f4  xor     eax, eax
0x1800472f6  movups  xmmword ptr [rbp+390h+DestinationString.Length], xmm1
0x1800472fa  xor     edx, edx; Val
0x1800472fc  mov     r8d, 0B8h; Size
0x180047302  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+10h; "\\Policies\\Microsoft\\Windows\\Safer\\"...
0x180047309  movaps  [rbp+390h+var_D0], xmm0
0x180047310  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+40h; "ows\\Safer\\CodeIdentifiers"
0x180047317  movaps  [rbp+390h+var_E0], xmm1
0x18004731e  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+30h; "oft\\Windows\\Safer\\CodeIdentifiers"
0x180047325  movaps  [rbp+390h+var_B0], xmm0
0x18004732c  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_1+60h; "entifiers"
0x180047333  movaps  [rbp+390h+var_C0], xmm1
0x18004733a  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_1+50h; "r\\CodeIdentifiers"
0x180047341  movaps  [rbp+390h+var_90], xmm0
0x180047348  xorps   xmm0, xmm0
0x18004734b  movaps  [rbp+390h+var_A0], xmm1
0x180047352  movsd   xmm1, qword ptr cs:aSoftwarePolici_1+6Eh; "rs"
0x18004735a  movups  xmmword ptr [rsp+490h+ObjectAttributes.ObjectName], xmm0
0x18004735f  mov     [rsp+490h+KeyHandle], rax
0x180047364  movups  xmmword ptr [rbp+390h+ObjectAttributes+1Ch], xmm0
0x180047368  movsd   qword ptr [rbp+390h+var_90+0Eh], xmm1
0x180047370  movups  xmmword ptr [rsp+490h+ObjectAttributes.Length], xmm0
0x180047375  call    memset_0
0x18004737a  xor     edx, edx; Val
0x18004737c  lea     rcx, [rbp+390h+var_3E0]; void *
0x180047380  mov     r8d, 230h; Size
0x180047386  call    memset_0
0x18004738b  mov     [rsp+490h+ResultLength], 0
0x180047393  mov     r12d, 1
0x180047399  test    rbx, rbx
0x18004739c  jz      loc_1800478B8
0x1800473a2  test    rdi, rdi
0x1800473a5  jz      loc_1800478B8
0x1800473ab  lea     rdx, [rbp+390h+SourceString]; SourceString
0x1800473b2  mov     [rdi], r12d
0x1800473b5  lea     rcx, [rbp+390h+DestinationString]; DestinationString
0x1800473b9  call    cs:__imp_RtlInitUnicodeString
0x1800473bf  lea     rax, [rbp+390h+DestinationString]
0x1800473c3  mov     [rsp+490h+ObjectAttributes.Length], 30h ; '0'
0x1800473cb  xorps   xmm0, xmm0
0x1800473ce  mov     [rsp+490h+ObjectAttributes.ObjectName], rax
0x1800473d3  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x1800473d8  mov     [rsp+490h+ObjectAttributes.RootDirectory], rbx
0x1800473dd  mov     edx, 2001Fh; DesiredAccess
0x1800473e2  mov     [rbp+390h+ObjectAttributes.Attributes], 40h ; '@'
0x1800473e9  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x1800473ee  movdqu  xmmword ptr [rbp+390h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800473f3  call    cs:__imp_NtOpenKey
0x1800473f9  mov     r14d, 0C0000034h
0x1800473ff  mov     ebx, eax
0x180047401  cmp     eax, r14d
0x180047404  jnz     short loc_18004743A
0x180047406  mov     [rsp+490h+Disposition], 0; Disposition
0x18004740f  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x180047414  mov     [rsp+490h+CreateOptions], 0; CreateOptions
0x18004741c  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047421  xor     r9d, r9d; TitleIndex
0x180047424  mov     [rsp+490h+Class], 0; Class
0x18004742d  mov     edx, 2001Fh; DesiredAccess
0x180047432  call    cs:__imp_NtCreateKey
0x180047438  mov     ebx, eax
0x18004743a  test    ebx, ebx
0x18004743c  js      loc_1800478BD
0x180047442  lea     rdx, aDefaultlevel; "DefaultLevel"
0x180047449  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004744e  call    cs:__imp_RtlInitUnicodeString
0x180047454  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047459  lea     rax, [rsp+490h+ResultLength]
0x18004745e  mov     ebx, 50h ; 'P'
0x180047463  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x180047468  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x18004746f  mov     dword ptr [rsp+490h+Class], ebx; Length
0x180047473  lea     rdx, [rsp+490h+ValueName]; ValueName
0x180047478  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004747c  call    cs:__imp_NtQueryValueKey
0x180047482  cmp     eax, r14d
0x180047485  jz      loc_18004755C
0x18004748b  lea     rdx, aTransparentena; "TransparentEnabled"
0x180047492  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x180047497  call    cs:__imp_RtlInitUnicodeString
0x18004749d  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x1800474a2  lea     rax, [rsp+490h+ResultLength]
0x1800474a7  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x1800474ac  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x1800474b3  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x1800474b7  mov     dword ptr [rsp+490h+Class], ebx; Length
0x1800474bb  lea     rdx, [rsp+490h+ValueName]; ValueName
0x1800474c0  call    cs:__imp_NtQueryValueKey
0x1800474c6  cmp     eax, r14d
0x1800474c9  jz      loc_18004755C
0x1800474cf  lea     rdx, aPolicyscope; "PolicyScope"
0x1800474d6  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x1800474db  call    cs:__imp_RtlInitUnicodeString
0x1800474e1  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x1800474e6  lea     rax, [rsp+490h+ResultLength]
0x1800474eb  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x1800474f0  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x1800474f7  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x1800474fb  mov     dword ptr [rsp+490h+Class], ebx; Length
0x1800474ff  lea     rdx, [rsp+490h+ValueName]; ValueName
0x180047504  call    cs:__imp_NtQueryValueKey
0x18004750a  cmp     eax, r14d
0x18004750d  jz      short loc_18004755C
0x18004750f  lea     rdx, aExecutabletype; "ExecutableTypes"
0x180047516  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x18004751b  call    cs:__imp_RtlInitUnicodeString
0x180047521  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047526  lea     rax, [rsp+490h+ResultLength]
0x18004752b  mov     qword ptr [rsp+490h+CreateOptions], rax; ResultLength
0x180047530  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x180047537  lea     r8d, [rbx-4Eh]; KeyValueInformationClass
0x18004753b  mov     dword ptr [rsp+490h+Class], ebx; Length
0x18004753f  lea     rdx, [rsp+490h+ValueName]; ValueName
0x180047544  call    cs:__imp_NtQueryValueKey
0x18004754a  mov     ebx, eax
0x18004754c  cmp     eax, r14d
0x18004754f  jz      short loc_18004755C
0x180047551  mov     dword ptr [rdi], 0
0x180047557  jmp     loc_1800478BD
0x18004755c  lea     rdx, aDefaultlevel; "DefaultLevel"
0x180047563  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x180047568  call    cs:__imp_RtlInitUnicodeString
0x18004756e  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047573  lea     rax, [rsp+490h+Data]
0x180047578  mov     edi, 4
0x18004757d  lea     rdx, [rsp+490h+ValueName]; ValueName
0x180047582  mov     r14d, 40000h
0x180047588  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004758c  mov     r9d, edi; Type
0x18004758f  mov     [rsp+490h+Class], rax; Data
0x180047594  xor     r8d, r8d; TitleIndex
0x180047597  mov     [rsp+490h+Data], r14d
0x18004759c  call    cs:__imp_NtSetValueKey
0x1800475a2  mov     ebx, eax
0x1800475a4  test    eax, eax
0x1800475a6  js      loc_1800478BD
0x1800475ac  lea     rdx, aTransparentena; "TransparentEnabled"
0x1800475b3  mov     [rsp+490h+Data], r12d
0x1800475b8  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x1800475bd  call    cs:__imp_RtlInitUnicodeString
0x1800475c3  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x1800475c8  lea     rax, [rsp+490h+Data]
0x1800475cd  mov     [rsp+490h+CreateOptions], edi; DataSize
0x1800475d1  lea     rdx, [rsp+490h+ValueName]; ValueName
0x1800475d6  mov     r9d, edi; Type
0x1800475d9  mov     [rsp+490h+Class], rax; Data
0x1800475de  xor     r8d, r8d; TitleIndex
0x1800475e1  call    cs:__imp_NtSetValueKey
0x1800475e7  mov     ebx, eax
0x1800475e9  test    eax, eax
0x1800475eb  js      loc_1800478BD
0x1800475f1  lea     rdx, aPolicyscope; "PolicyScope"
0x1800475f8  mov     [rsp+490h+Data], 0
0x180047600  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x180047605  call    cs:__imp_RtlInitUnicodeString
0x18004760b  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047610  lea     rax, [rsp+490h+Data]
0x180047615  mov     [rsp+490h+CreateOptions], edi; DataSize
0x180047619  lea     rdx, [rsp+490h+ValueName]; ValueName
0x18004761e  mov     r9d, edi; Type
0x180047621  mov     [rsp+490h+Class], rax; Data
0x180047626  xor     r8d, r8d; TitleIndex
0x180047629  call    cs:__imp_NtSetValueKey
0x18004762f  mov     ebx, eax
0x180047631  test    eax, eax
0x180047633  js      loc_1800478BD
0x180047639  lea     rdx, aExecutabletype; "ExecutableTypes"
0x180047640  lea     rcx, [rsp+490h+ValueName]; DestinationString
0x180047645  call    cs:__imp_RtlInitUnicodeString
0x18004764b  mov     rcx, gs:60h
0x180047654  mov     edi, 0F8h
0x180047659  mov     r8d, edi; Size
0x18004765c  xor     edx, edx; Flags
0x18004765e  mov     rcx, [rcx+30h]; HeapHandle
0x180047662  call    cs:__imp_RtlAllocateHeap
0x180047668  mov     rbx, rax
0x18004766b  test    rax, rax
0x18004766e  jz      loc_1800478B1
0x180047674  movaps  xmm0, xmmword ptr cs:aAde; "ADE"
0x18004767b  lea     rdx, [rsp+490h+ValueName]; ValueName
0x180047680  movups  xmmword ptr [rax], xmm0
0x180047683  mov     r9d, 7; Type
0x180047689  mov     [rsp+490h+CreateOptions], edi; DataSize
0x18004768d  movaps  xmm1, cs:xmmword_18007A8B0
0x180047694  xor     r8d, r8d; TitleIndex
0x180047697  movups  xmmword ptr [rax+10h], xmm1
0x18004769b  mov     [rsp+490h+Class], rbx; Data
0x1800476a0  movaps  xmm0, cs:xmmword_18007A8C0
0x1800476a7  movups  xmmword ptr [rax+20h], xmm0
0x1800476ab  movaps  xmm1, cs:xmmword_18007A8D0
0x1800476b2  movups  xmmword ptr [rax+30h], xmm1
0x1800476b6  movaps  xmm0, cs:xmmword_18007A8E0
0x1800476bd  movups  xmmword ptr [rax+40h], xmm0
0x1800476c1  movaps  xmm1, cs:xmmword_18007A8F0
0x1800476c8  movups  xmmword ptr [rax+50h], xmm1
0x1800476cc  movaps  xmm0, cs:xmmword_18007A900
0x1800476d3  movups  xmmword ptr [rax+60h], xmm0
0x1800476d7  movaps  xmm1, cs:xmmword_18007A910
0x1800476de  movups  xmmword ptr [rax+70h], xmm1
0x1800476e2  movaps  xmm0, cs:xmmword_18007A920
0x1800476e9  movups  xmmword ptr [rax+80h], xmm0
0x1800476f0  movaps  xmm1, cs:xmmword_18007A930
0x1800476f7  movups  xmmword ptr [rax+90h], xmm1
0x1800476fe  movaps  xmm0, cs:xmmword_18007A940
0x180047705  movups  xmmword ptr [rax+0A0h], xmm0
0x18004770c  movaps  xmm1, cs:xmmword_18007A950
0x180047713  movups  xmmword ptr [rax+0B0h], xmm1
0x18004771a  movaps  xmm0, cs:xmmword_18007A960
0x180047721  movups  xmmword ptr [rax+0C0h], xmm0
0x180047728  movaps  xmm1, cs:xmmword_18007A970
0x18004772f  movups  xmmword ptr [rax+0D0h], xmm1
0x180047736  movaps  xmm0, cs:xmmword_18007A980
0x18004773d  movups  xmmword ptr [rax+0E0h], xmm0
0x180047744  mov     rax, cs:qword_18007A990
0x18004774b  mov     [rbx+0F0h], rax
0x180047752  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180047757  call    cs:__imp_NtSetValueKey
0x18004775d  mov     rcx, gs:60h
0x180047766  mov     r8, rbx; P
0x180047769  xor     edx, edx; Flags
0x18004776b  mov     rcx, [rcx+30h]; HeapHandle
0x18004776f  call    cs:__imp_RtlFreeHeap
0x180047775  lea     rbx, aHkeyLocalMachi_1; "%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsof"...
0x18004777c  mov     [rbp+390h+var_1A0], r12d
0x180047783  mov     rdx, rbx; SourceString
0x180047786  mov     [rbp+390h+var_19C], r14d
0x18004778d  lea     rcx, [rbp+390h+var_188]; DestinationString
0x180047794  mov     [rbp+390h+var_198], 3
0x18004779e  mov     [rbp+390h+var_190], r12d
0x1800477a5  mov     [rbp+390h+var_178], 0
0x1800477af  call    cs:__imp_RtlInitUnicodeString
0x1800477b5  mov     ecx, 191CD7FAh
0x1800477ba  mov     [rbp+390h+var_1AC], 4A17F240h
0x1800477c4  mov     [rbp+390h+var_1B0], ecx
0x1800477ca  lea     r8, [rbp+390h+var_3E0]
0x1800477ce  mov     [rbp+390h+var_3D8], ecx
0x1800477d1  lea     rdx, [rbp+390h+var_1B0]
0x1800477d8  xor     eax, eax
0x1800477da  mov     [rbp+390h+var_1A8], 0D4948689h
0x1800477e4  mov     cl, r12b
0x1800477e7  mov     [rbp+390h+var_1A4], 0CAC8A680h
0x1800477f1  xor     r9d, r9d
0x1800477f4  mov     [rbp+390h+var_3DC], 20h ; ' '
0x1800477fb  mov     [rbp+390h+var_3E0], r12d
0x1800477ff  mov     [rbp+390h+var_3D4], 4A17F240h
0x180047806  mov     [rbp+390h+var_3D0], 0D4948689h
0x18004780d  mov     [rbp+390h+var_3CC], 0CAC8A680h
0x180047814  mov     [rbp+390h+var_1B8], 0
0x18004781e  mov     [rbp+390h+var_1C0], rbx
0x180047825  mov     [rbp+390h+var_3C0], ax
0x180047829  call    SaferpSetSingleIdentificationPath
0x18004782e  mov     ebx, eax
0x180047830  test    eax, eax
0x180047832  js      loc_1800478BD
0x180047838  lea     rbx, aHkeyLocalMachi; "%HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsof"...
0x18004783f  mov     rdx, rbx; SourceString
0x180047842  lea     rcx, [rbp+390h+var_188]; DestinationString
0x180047849  call    cs:__imp_RtlInitUnicodeString
0x18004784f  mov     ecx, 0D2C34AB2h
0x180047854  mov     [rbp+390h+var_1AC], 46B2529Ah
0x18004785e  mov     [rbp+390h+var_1B0], ecx
0x180047864  lea     r8, [rbp+390h+var_3E0]
0x180047868  mov     [rbp+390h+var_3D8], ecx
0x18004786b  lea     rdx, [rbp+390h+var_1B0]
0x180047872  mov     cl, r12b
0x180047875  mov     [rbp+390h+var_1A8], 85FC93B2h
0x18004787f  xor     r9d, r9d
0x180047882  mov     [rbp+390h+var_1A4], 0EA72CE3Fh
0x18004788c  mov     [rbp+390h+var_3D4], 46B2529Ah
0x180047893  mov     [rbp+390h+var_3D0], 85FC93B2h
0x18004789a  mov     [rbp+390h+var_3CC], 0EA72CE3Fh
0x1800478a1  mov     [rbp+390h+var_1C0], rbx
0x1800478a8  call    SaferpSetSingleIdentificationPath
0x1800478ad  mov     ebx, eax
0x1800478af  jmp     short loc_1800478BD
0x1800478b1  mov     ebx, 0C0000017h
0x1800478b6  jmp     short loc_1800478BD
0x1800478b8  mov     ebx, 0C000000Dh
0x1800478bd  mov     rcx, [rsp+490h+KeyHandle]; Handle
0x1800478c2  test    rcx, rcx
  ... truncated ...
```
