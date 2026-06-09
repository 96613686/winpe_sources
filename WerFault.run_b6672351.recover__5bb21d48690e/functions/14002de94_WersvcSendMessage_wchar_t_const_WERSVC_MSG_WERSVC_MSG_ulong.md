# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x14002de94`
- end: `0x14002e27f`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `1003`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1400183d0`
- `0x14002d9b0`
- `0x14004cc34`
- `0x14005e058`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14002de94`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x14002e028`
- `ntdll!NtOpenEvent` at `0x14002e028`
- `ntdll!NtClose` at `0x14002e07a`
- `ntdll!NtClose` at `0x14002e249`
- `ntdll!NtClose` at `0x14002e07a`
- `ntdll!NtClose` at `0x14002e249`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14002df39`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14002df39`
- `ntdll!ZwUpdateWnfStateData` at `0x14002df6e`
- `ntdll!ZwUpdateWnfStateData` at `0x14002df6e`
- `ntdll!EtwEventWriteNoRegistration` at `0x14002df97`
- `ntdll!EtwEventWriteNoRegistration` at `0x14002df97`
- `ntdll!NtWaitForSingleObject` at `0x14002e067`
- `ntdll!NtWaitForSingleObject` at `0x14002e067`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002e0d6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002e0d6`
- `ntdll!NtAlpcConnectPort` at `0x14002e193`
- `ntdll!NtAlpcConnectPort` at `0x14002e193`
- `ntdll!NtQuerySystemInformation` at `0x14002dfc3`
- `ntdll!NtQuerySystemInformation` at `0x14002dfc3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14002e1fa`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14002e1fa`
- `ntdll!RtlFreeSid` at `0x14002e234`
- `ntdll!RtlFreeSid` at `0x14002e234`
- `ntdll!RtlInitUnicodeString` at `0x14002e10d`
- `ntdll!RtlInitUnicodeString` at `0x14002e10d`

## string_xrefs

- `0x14002dfde`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(PCWSTR SourceString, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  char v6; // di
  BOOL v7; // ebx
  int v8; // eax
  int v9; // ecx
  NTSTATUS v10; // ebx
  __int64 v11; // rsi
  char v12; // dl
  union _LARGE_INTEGER *v13; // r8
  __int64 *v14; // rsi
  int v15; // eax
  HANDLE v16; // rcx
  int v17; // eax
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+108h] [rbp+8h] BYREF
  __int128 v32; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v34; // [rsp+130h] [rbp+30h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v33, 0, 0x48u);
  v25 = 0;
  v6 = 1;
  Handle = 0;
  Sid = 0;
  v21 = 0;
  SystemInformation = 0;
  LODWORD(EventHandle) = 0;
  DestinationString = 0;
  v7 = 0;
  v32 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v7 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v32 = 0;
  v8 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v32, 0, 0);
  v9 = v7 + 1;
  if ( v8 )
    v9 = v7;
  if ( v9 )
  {
    v10 = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( v10 >= 0 )
    {
      v11 = (int)SystemInformation;
      *((_QWORD *)&v32 + 1) = L"\\KernelObjects\\SystemErrorPortReady";
      *(_QWORD *)&v32 = 4718662;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      EventHandle = 0;
      v24 = 0;
      ObjectAttributes.RootDirectory = 0;
      v10 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
      if ( v10 >= 0 )
      {
        if ( (_DWORD)v11 == -1 )
        {
          v12 = 1;
        }
        else
        {
          v12 = 0;
          v24 = -10000 * v11;
        }
        v13 = (union _LARGE_INTEGER *)&v24;
        if ( v12 )
          v13 = 0;
        v10 = NtWaitForSingleObject(EventHandle, 0, v13);
        NtClose(EventHandle);
        if ( v10 >= 0 )
        {
          if ( v10 == 258 )
          {
LABEL_16:
            v10 = -1073740973;
            goto LABEL_28;
          }
          v10 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
          if ( v10 >= 0 )
          {
            if ( HIDWORD(SystemInformation) != -1 )
            {
              v6 = 0;
              v25 = -10000LL * SHIDWORD(SystemInformation);
            }
            RtlInitUnicodeString(&DestinationString, SourceString);
            LODWORD(v27) = 48;
            *((_QWORD *)&v27 + 1) = 0;
            DWORD2(v28) = 0;
            *(_QWORD *)&v28 = 0;
            v29 = 0;
            memset_0(v33, 0, 0x48u);
            v14 = &v25;
            if ( v6 )
              v14 = 0;
            v34 = 1400;
            v15 = NtAlpcConnectPort(&Handle, &DestinationString, &v27, v33, 0x20000, Sid, 0, 0, 0, 0, v14);
            v10 = v15;
            if ( v15 >= 0 )
            {
              if ( v15 == 258 )
                goto LABEL_16;
              memset_0((char *)a3 + 4, 0, 0x574u);
              v16 = Handle;
              *(_DWORD *)a3 = 91751760;
              v21 = 1400;
              v17 = NtAlpcSendWaitReceivePort(v16, 0x20000, a2, 0, a3, &v21, 0, v14);
              v10 = v17;
              if ( v17 >= 0 && v17 != 258 )
                v10 = v21 != 1400 ? 0xC000021F : 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = -1073741696;
  }
LABEL_28:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002de94  mov     [rsp-8+arg_18], rbx
0x14002de99  push    rbp
0x14002de9a  push    rsi
0x14002de9b  push    rdi
0x14002de9c  push    r12
0x14002de9e  push    r13
0x14002dea0  push    r14
0x14002dea2  push    r15
0x14002dea4  lea     rbp, [rsp-80h]
0x14002dea9  sub     rsp, 180h
0x14002deb0  mov     rax, cs:__security_cookie
0x14002deb7  xor     rax, rsp
0x14002deba  mov     [rbp+0B0h+var_40], rax
0x14002debe  xorps   xmm0, xmm0
0x14002dec1  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x14002dec7  xor     r13d, r13d
0x14002deca  mov     r14, r8
0x14002decd  mov     r15, rdx
0x14002ded0  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r13d
0x14002ded4  mov     r12, rcx
0x14002ded7  xor     edx, edx; Val
0x14002ded9  lea     rcx, [rbp+0B0h+var_90]; void *
0x14002dedd  lea     r8d, [r13+48h]; Size
0x14002dee1  movups  [rbp+0B0h+var_108], xmm0
0x14002dee5  movups  [rbp+0B0h+var_F8], xmm0
0x14002dee9  movups  [rbp+0B0h+var_E8], xmm0
0x14002deed  call    memset_0
0x14002def2  xorps   xmm0, xmm0
0x14002def5  mov     [rbp+0B0h+var_120], r13
0x14002def9  lea     edi, [r13+1]
0x14002defd  mov     [rbp+0B0h+Handle], r13
0x14002df01  mov     edx, edi
0x14002df03  mov     [rsp+1B0h+var_138], r13
0x14002df08  lea     r9, [rsp+1B0h+EventHandle]
0x14002df0d  mov     [rsp+1B0h+var_140], r13
0x14002df12  xor     r8d, r8d
0x14002df15  mov     [rsp+1B0h+SystemInformation], r13
0x14002df1a  lea     rcx, WNF_WER_SERVICE_START
0x14002df21  mov     dword ptr [rsp+1B0h+EventHandle], r13d
0x14002df26  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14002df2a  mov     ebx, r13d
0x14002df2d  mov     [rsp+1B0h+SubAuthority2], 4
0x14002df35  movups  [rbp+0B0h+var_A0], xmm0
0x14002df39  call    cs:__imp_ZwQueryWnfStateNameInformation
0x14002df40  nop     dword ptr [rax+rax+00h]
0x14002df45  test    eax, eax
0x14002df47  js      short loc_14002DF7F
0x14002df49  cmp     dword ptr [rsp+1B0h+EventHandle], r13d
0x14002df4e  jz      short loc_14002DF7F
0x14002df50  mov     [rsp+1B0h+SubAuthority4], r13d
0x14002df55  lea     rcx, WNF_WER_SERVICE_START
0x14002df5c  mov     [rsp+1B0h+SubAuthority3], r13d
0x14002df61  xor     r9d, r9d
0x14002df64  xor     r8d, r8d
0x14002df67  mov     qword ptr [rsp+1B0h+SubAuthority2], r13
0x14002df6c  xor     edx, edx
0x14002df6e  call    cs:__imp_ZwUpdateWnfStateData
0x14002df75  nop     dword ptr [rax+rax+00h]
0x14002df7a  test    eax, eax
0x14002df7c  cmovns  ebx, edi
0x14002df7f  xorps   xmm0, xmm0
0x14002df82  lea     rdx, [rbp+0B0h+var_A0]
0x14002df86  xor     r9d, r9d
0x14002df89  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x14002df90  xor     r8d, r8d
0x14002df93  movups  [rbp+0B0h+var_A0], xmm0
0x14002df97  call    cs:__imp_EtwEventWriteNoRegistration
0x14002df9e  nop     dword ptr [rax+rax+00h]
0x14002dfa3  test    eax, eax
0x14002dfa5  lea     ecx, [rbx+1]
0x14002dfa8  cmovnz  ecx, ebx
0x14002dfab  test    ecx, ecx
0x14002dfad  jz      loc_14002E225
0x14002dfb3  xor     r9d, r9d; ReturnLength
0x14002dfb6  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x14002dfbb  lea     r8d, [r9+8]; SystemInformationLength
0x14002dfbf  lea     ecx, [r9+73h]; SystemInformationClass
0x14002dfc3  call    cs:__imp_NtQuerySystemInformation
0x14002dfca  nop     dword ptr [rax+rax+00h]
0x14002dfcf  mov     ebx, eax
0x14002dfd1  test    eax, eax
0x14002dfd3  js      loc_14002E22A
0x14002dfd9  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x14002dfde  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x14002dfe5  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x14002dfe9  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x14002dfed  lea     rax, [rbp+0B0h+var_A0]
0x14002dff1  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x14002dff9  xorps   xmm0, xmm0
0x14002dffc  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14002e000  mov     edx, 100001h; DesiredAccess
0x14002e005  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x14002e00d  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x14002e012  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r13
0x14002e016  mov     [rsp+1B0h+EventHandle], r13
0x14002e01b  mov     [rbp+0B0h+var_128], r13
0x14002e01f  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r13
0x14002e023  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002e028  call    cs:__imp_NtOpenEvent
0x14002e02f  nop     dword ptr [rax+rax+00h]
0x14002e034  mov     ebx, eax
0x14002e036  test    eax, eax
0x14002e038  js      loc_14002E22A
0x14002e03e  cmp     esi, 0FFFFFFFFh
0x14002e041  jnz     short loc_14002E048
0x14002e043  mov     dl, dil
0x14002e046  jmp     short loc_14002E056
0x14002e048  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x14002e04f  mov     dl, r13b
0x14002e052  mov     [rbp+0B0h+var_128], rcx
0x14002e056  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14002e05b  lea     r8, [rbp+0B0h+var_128]
0x14002e05f  test    dl, dl
0x14002e061  cmovnz  r8, r13; Timeout
0x14002e065  xor     edx, edx; Alertable
0x14002e067  call    cs:__imp_NtWaitForSingleObject
0x14002e06e  nop     dword ptr [rax+rax+00h]
0x14002e073  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14002e078  mov     ebx, eax
0x14002e07a  call    cs:__imp_NtClose
0x14002e081  nop     dword ptr [rax+rax+00h]
0x14002e086  test    ebx, ebx
0x14002e088  js      loc_14002E22A
0x14002e08e  cmp     ebx, 102h
0x14002e094  jnz     short loc_14002E0A0
0x14002e096  mov     ebx, 0C0000353h
0x14002e09b  jmp     loc_14002E22A
0x14002e0a0  lea     rax, [rsp+1B0h+var_138]
0x14002e0a5  xor     r9d, r9d; SubAuthority1
0x14002e0a8  mov     [rsp+1B0h+Sid], rax; Sid
0x14002e0ad  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x14002e0b1  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x14002e0b6  mov     dl, dil; SubAuthorityCount
0x14002e0b9  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x14002e0be  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x14002e0c3  lea     r8d, [r9+12h]; SubAuthority0
0x14002e0c7  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x14002e0cc  mov     [rsp+1B0h+SubAuthority3], r13d; SubAuthority3
0x14002e0d1  mov     [rsp+1B0h+SubAuthority2], r13d; SubAuthority2
0x14002e0d6  call    cs:__imp_RtlAllocateAndInitializeSid
0x14002e0dd  nop     dword ptr [rax+rax+00h]
0x14002e0e2  mov     ebx, eax
0x14002e0e4  test    eax, eax
0x14002e0e6  js      loc_14002E22A
0x14002e0ec  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x14002e0f1  jz      short loc_14002E106
0x14002e0f3  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x14002e0f8  mov     dil, r13b
0x14002e0fb  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14002e102  mov     [rbp+0B0h+var_120], rcx
0x14002e106  mov     rdx, r12; SourceString
0x14002e109  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002e10d  call    cs:__imp_RtlInitUnicodeString
0x14002e114  nop     dword ptr [rax+rax+00h]
0x14002e119  xor     edx, edx; Val
0x14002e11b  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x14002e122  xorps   xmm0, xmm0
0x14002e125  mov     qword ptr [rbp+0B0h+var_108+8], r13
0x14002e129  lea     rcx, [rbp+0B0h+var_90]; void *
0x14002e12d  mov     dword ptr [rbp+0B0h+var_F8+8], r13d
0x14002e131  mov     qword ptr [rbp+0B0h+var_F8], r13
0x14002e135  lea     r8d, [rdx+48h]; Size
0x14002e139  movdqu  [rbp+0B0h+var_E8], xmm0
0x14002e13e  call    memset_0
0x14002e143  mov     rax, [rsp+1B0h+var_138]
0x14002e148  lea     rsi, [rbp+0B0h+var_120]
0x14002e14c  test    dil, dil
0x14002e14f  lea     r9, [rbp+0B0h+var_90]
0x14002e153  mov     r12d, 578h
0x14002e159  lea     r8, [rbp+0B0h+var_108]
0x14002e15d  cmovnz  rsi, r13
0x14002e161  mov     [rbp+0B0h+var_80], r12
0x14002e165  mov     [rsp+1B0h+Sid], rsi
0x14002e16a  lea     rdx, [rbp+0B0h+DestinationString]
0x14002e16e  mov     qword ptr [rsp+1B0h+SubAuthority7], r13
0x14002e173  lea     rcx, [rbp+0B0h+Handle]
0x14002e177  mov     qword ptr [rsp+1B0h+SubAuthority6], r13
0x14002e17c  mov     qword ptr [rsp+1B0h+SubAuthority5], r13
0x14002e181  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x14002e186  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14002e18b  mov     [rsp+1B0h+SubAuthority2], 20000h
0x14002e193  call    cs:__imp_NtAlpcConnectPort
0x14002e19a  nop     dword ptr [rax+rax+00h]
0x14002e19f  mov     ebx, eax
0x14002e1a1  test    eax, eax
0x14002e1a3  js      loc_14002E22A
0x14002e1a9  mov     edi, 102h
0x14002e1ae  cmp     eax, edi
0x14002e1b0  jz      loc_14002E096
0x14002e1b6  lea     rcx, [r14+4]; void *
0x14002e1ba  xor     edx, edx; Val
0x14002e1bc  lea     r8d, [r12-4]; Size
0x14002e1c1  call    memset_0
0x14002e1c6  mov     rcx, [rbp+0B0h+Handle]
0x14002e1ca  lea     rax, [rsp+1B0h+var_140]
0x14002e1cf  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x14002e1d4  xor     r9d, r9d
0x14002e1d7  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x14002e1dc  mov     r8, r15
0x14002e1df  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14002e1e4  mov     edx, 20000h
0x14002e1e9  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x14002e1ee  mov     dword ptr [r14], 5780550h
0x14002e1f5  mov     [rsp+1B0h+var_140], r12
0x14002e1fa  call    cs:__imp_NtAlpcSendWaitReceivePort
0x14002e201  nop     dword ptr [rax+rax+00h]
0x14002e206  mov     ebx, eax
0x14002e208  test    eax, eax
0x14002e20a  js      short loc_14002E22A
0x14002e20c  cmp     eax, edi
0x14002e20e  jz      short loc_14002E22A
0x14002e210  mov     rax, [rsp+1B0h+var_140]
0x14002e215  sub     rax, r12
0x14002e218  neg     rax
0x14002e21b  sbb     ebx, ebx
0x14002e21d  and     ebx, 0C000021Fh
0x14002e223  jmp     short loc_14002E22A
0x14002e225  mov     ebx, 0C0000080h
0x14002e22a  mov     rcx, [rsp+1B0h+var_138]; Sid
0x14002e22f  test    rcx, rcx
0x14002e232  jz      short loc_14002E240
0x14002e234  call    cs:__imp_RtlFreeSid
0x14002e23b  nop     dword ptr [rax+rax+00h]
0x14002e240  mov     rcx, [rbp+0B0h+Handle]; Handle
0x14002e244  test    rcx, rcx
0x14002e247  jz      short loc_14002E255
0x14002e249  call    cs:__imp_NtClose
0x14002e250  nop     dword ptr [rax+rax+00h]
0x14002e255  mov     eax, ebx
0x14002e257  mov     rcx, [rbp+0B0h+var_40]
0x14002e25b  xor     rcx, rsp; StackCookie
0x14002e25e  call    __security_check_cookie
0x14002e263  mov     rbx, [rsp+1B0h+arg_18]
0x14002e26b  add     rsp, 180h
0x14002e272  pop     r15
0x14002e274  pop     r14
0x14002e276  pop     r13
0x14002e278  pop     r12
0x14002e27a  pop     rdi
0x14002e27b  pop     rsi
0x14002e27c  pop     rbp
0x14002e27d  retn
```
