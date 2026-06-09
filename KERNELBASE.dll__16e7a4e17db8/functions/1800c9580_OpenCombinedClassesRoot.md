# OpenCombinedClassesRoot

- ea: `0x1800c9580`
- end: `0x1800c9777`
- name: `OpenCombinedClassesRoot`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c9130`
- `0x1800c9270`

## callees

- `0x18005cb00`
- `0x18005cc40`
- `0x1800c9580`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800c96e6`
- `ntdll!RtlFreeUnicodeString` at `0x1800c96f0`
- `ntdll!RtlFreeUnicodeString` at `0x1800c972a`
- `ntdll!RtlFreeUnicodeString` at `0x1800c96e6`
- `ntdll!RtlFreeUnicodeString` at `0x1800c96f0`
- `ntdll!RtlFreeUnicodeString` at `0x1800c972a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c960d`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c960d`
- `ntdll!RtlCopyUnicodeString` at `0x1800c95fc`
- `ntdll!RtlCopyUnicodeString` at `0x1800c95fc`
- `ntdll!NtClose` at `0x1800c976c`
- `ntdll!NtClose` at `0x1800c976c`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800c95b3`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800c95b3`
- `ntdll!RtlFreeHeap` at `0x1800c96c9`
- `ntdll!RtlFreeHeap` at `0x1800c96c9`
- `ntdll!RtlAllocateHeap` at `0x1800c95e1`
- `ntdll!RtlAllocateHeap` at `0x1800c95e1`
- `ntdll!NtOpenKeyEx` at `0x1800c96a9`
- `ntdll!NtOpenKeyEx` at `0x1800c96a9`
- `ntdll!NtSetInformationKey` at `0x1800c9758`
- `ntdll!NtSetInformationKey` at `0x1800c9758`

## pseudocode

```c
NTSTATUS __fastcall OpenCombinedClassesRoot(unsigned int a1, _QWORD *a2, __int64 a3)
{
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
  int v8; // esi
  int KeySetInformation; // [rsp+30h] [rbp-79h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  __int64 v12; // [rsp+50h] [rbp-59h] BYREF
  __int16 v13; // [rsp+58h] [rbp-51h]
  char v14; // [rsp+5Ah] [rbp-4Fh]
  PVOID P; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+68h] [rbp-41h] BYREF
  __int128 v17; // [rsp+78h] [rbp-31h] BYREF
  __int128 v18; // [rsp+88h] [rbp-21h]
  __int128 v19; // [rsp+98h] [rbp-11h]
  _OWORD v20[5]; // [rsp+A8h] [rbp-1h] BYREF
  char v21; // [rsp+128h] [rbp+7Fh] BYREF

  DWORD1(v17) = 0;
  HIDWORD(v18) = 0;
  KeyPath = 0;
  DestinationString = 0;
  result = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( result < 0 )
    return result;
  DestinationString.MaximumLength = KeyPath.MaximumLength + 18;
  DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                      NtCurrentPeb()->ProcessHeap,
                                      0,
                                      (unsigned __int16)(KeyPath.MaximumLength + 18));
  if ( !DestinationString.Buffer )
  {
    RtlFreeUnicodeString(&KeyPath);
    return -1073741670;
  }
  RtlCopyUnicodeString(&DestinationString, &KeyPath);
  RtlAppendUnicodeToString(&DestinationString, L"_Classes");
  LODWORD(v17) = 48;
  *(_QWORD *)&v18 = &DestinationString;
  *((_QWORD *)&v17 + 1) = 0;
  DWORD2(v18) = 64;
  v19 = 0;
  if ( a3 )
  {
    v7 = Wow64NtOpenKey((_DWORD)a2, a1, (unsigned int)&v17, 0, a3);
  }
  else
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    KeyHandle = 0;
    v21 = 0;
    P = 0;
    v20[0] = v17;
    KeySetInformation = 0;
    v20[1] = v18;
    v20[2] = 0;
    v7 = ConstructKernelKeyPath(
           a1,
           (unsigned int)v20,
           (unsigned int)&KeySetInformation,
           (unsigned int)&v12,
           (__int64)&v21,
           (__int64)&P);
    if ( v7 >= 0 )
    {
      v8 = NtOpenKeyEx(&KeyHandle, a1, v20, 0);
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( v8 >= 0 )
      {
        if ( v21 )
        {
          if ( KeySetInformation )
          {
            KeySetInformation &= 0xF01u;
            v7 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
            if ( v7 < 0 )
            {
              NtClose(KeyHandle);
              goto LABEL_11;
            }
          }
        }
        *a2 = KeyHandle;
      }
      v7 = v8;
    }
  }
LABEL_11:
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&KeyPath);
  if ( v7 >= 0 )
    *a2 |= 2uLL;
  return v7;
}

```

## disassembly

```asm
0x1800c9580  push    rbp
0x1800c9582  push    rbx
0x1800c9583  push    rsi
0x1800c9584  push    rdi
0x1800c9585  lea     rbp, [rsp-3Fh]
0x1800c958a  sub     rsp, 0E8h
0x1800c9591  xor     eax, eax
0x1800c9593  mov     esi, ecx
0x1800c9595  xorps   xmm0, xmm0
0x1800c9598  mov     dword ptr [rbp+57h+var_88+4], eax
0x1800c959b  xorps   xmm1, xmm1
0x1800c959e  mov     dword ptr [rbp+57h+var_78+0Ch], eax
0x1800c95a1  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x1800c95a5  mov     rbx, r8
0x1800c95a8  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x1800c95ac  mov     rdi, rdx
0x1800c95af  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800c95b3  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800c95b9  test    eax, eax
0x1800c95bb  js      loc_1800C9700
0x1800c95c1  movzx   eax, [rbp+57h+KeyPath.MaximumLength]
0x1800c95c5  xor     edx, edx; Flags
0x1800c95c7  add     ax, 12h
0x1800c95cb  movzx   r8d, ax; Size
0x1800c95cf  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x1800c95d4  mov     rcx, gs:60h
0x1800c95dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800c95e1  call    cs:__imp_RtlAllocateHeap
0x1800c95e7  mov     [rbp+57h+DestinationString.Buffer], rax
0x1800c95eb  test    rax, rax
0x1800c95ee  jz      loc_1800C9726
0x1800c95f4  lea     rdx, [rbp+57h+KeyPath]; SourceString
0x1800c95f8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c95fc  call    cs:__imp_RtlCopyUnicodeString
0x1800c9602  lea     rdx, aClasses_0; "_Classes"
0x1800c9609  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1800c960d  call    cs:__imp_RtlAppendUnicodeToString
0x1800c9613  mov     dword ptr [rbp+57h+var_88], 30h ; '0'
0x1800c961a  lea     rax, [rbp+57h+DestinationString]
0x1800c961e  mov     qword ptr [rbp+57h+var_78], rax
0x1800c9622  xorps   xmm2, xmm2
0x1800c9625  mov     qword ptr [rbp+57h+var_88+8], 0
0x1800c962d  mov     dword ptr [rbp+57h+var_78+8], 40h ; '@'
0x1800c9634  movdqu  [rbp+57h+var_68], xmm2
0x1800c9639  test    rbx, rbx
0x1800c963c  jnz     loc_1800C970C
0x1800c9642  movups  xmm0, [rbp+57h+var_88]
0x1800c9646  xor     eax, eax
0x1800c9648  lea     r9, [rbp+57h+var_B0]
0x1800c964c  movups  xmm1, [rbp+57h+var_78]
0x1800c9650  mov     [rbp+57h+var_B0], rax
0x1800c9654  lea     r8, [rbp+57h+KeySetInformation]
0x1800c9658  mov     [rbp+57h+var_A8], ax
0x1800c965c  lea     rdx, [rbp+57h+var_58]
0x1800c9660  mov     [rbp+57h+var_A6], al
0x1800c9663  mov     ecx, esi
0x1800c9665  mov     [rbp+57h+KeyHandle], rax
0x1800c9669  mov     [rbp+57h+arg_18], al
0x1800c966c  lea     rax, [rbp+57h+P]
0x1800c9670  mov     [rsp+100h+var_D8], rax
0x1800c9675  lea     rax, [rbp+57h+arg_18]
0x1800c9679  mov     [rsp+100h+var_E0], rax
0x1800c967e  mov     [rbp+57h+P], rbx
0x1800c9682  movups  [rbp+57h+var_58], xmm0
0x1800c9686  mov     [rbp+57h+KeySetInformation], ebx
0x1800c9689  movups  [rbp+57h+var_48], xmm1
0x1800c968d  movups  [rbp+57h+var_38], xmm2
0x1800c9691  call    ConstructKernelKeyPath
0x1800c9696  mov     ebx, eax
0x1800c9698  test    eax, eax
0x1800c969a  js      short loc_1800C96E2
0x1800c969c  xor     r9d, r9d
0x1800c969f  lea     r8, [rbp+57h+var_58]
0x1800c96a3  mov     edx, esi
0x1800c96a5  lea     rcx, [rbp+57h+KeyHandle]
0x1800c96a9  call    cs:__imp_NtOpenKeyEx
0x1800c96af  mov     r8, [rbp+57h+P]; P
0x1800c96b3  mov     esi, eax
0x1800c96b5  test    r8, r8
0x1800c96b8  jz      short loc_1800C96CF
0x1800c96ba  mov     rcx, gs:60h
0x1800c96c3  xor     edx, edx; Flags
0x1800c96c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800c96c9  call    cs:__imp_RtlFreeHeap
0x1800c96cf  test    esi, esi
0x1800c96d1  js      short loc_1800C96E0
0x1800c96d3  cmp     [rbp+57h+arg_18], 0
0x1800c96d7  jnz     short loc_1800C9737
0x1800c96d9  mov     rax, [rbp+57h+KeyHandle]
0x1800c96dd  mov     [rdi], rax
0x1800c96e0  mov     ebx, esi
0x1800c96e2  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800c96e6  call    cs:__imp_RtlFreeUnicodeString
0x1800c96ec  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x1800c96f0  call    cs:__imp_RtlFreeUnicodeString
0x1800c96f6  test    ebx, ebx
0x1800c96f8  js      short loc_1800C96FE
0x1800c96fa  or      qword ptr [rdi], 2
0x1800c96fe  mov     eax, ebx
0x1800c9700  add     rsp, 0E8h
0x1800c9707  pop     rdi
0x1800c9708  pop     rsi
0x1800c9709  pop     rbx
0x1800c970a  pop     rbp
0x1800c970b  retn
0x1800c970c  xor     r9d, r9d
0x1800c970f  mov     [rsp+100h+var_E0], rbx
0x1800c9714  lea     r8, [rbp+57h+var_88]
0x1800c9718  mov     edx, esi
0x1800c971a  mov     rcx, rdi
0x1800c971d  call    Wow64NtOpenKey
0x1800c9722  mov     ebx, eax
0x1800c9724  jmp     short loc_1800C96E2
0x1800c9726  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x1800c972a  call    cs:__imp_RtlFreeUnicodeString
0x1800c9730  mov     eax, 0C000009Ah
0x1800c9735  jmp     short loc_1800C9700
0x1800c9737  mov     eax, [rbp+57h+KeySetInformation]
0x1800c973a  test    eax, eax
0x1800c973c  jz      short loc_1800C96D9
0x1800c973e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800c9742  lea     r8, [rbp+57h+KeySetInformation]; KeySetInformation
0x1800c9746  mov     r9d, 4; KeySetInformationLength
0x1800c974c  and     eax, 0F01h
0x1800c9751  mov     [rbp+57h+KeySetInformation], eax
0x1800c9754  lea     edx, [r9+1]; KeySetInformationClass
0x1800c9758  call    cs:__imp_NtSetInformationKey
0x1800c975e  mov     ebx, eax
0x1800c9760  test    eax, eax
0x1800c9762  jns     loc_1800C96D9
0x1800c9768  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800c976c  call    cs:__imp_NtClose
0x1800c9772  jmp     loc_1800C96E2
```
