# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x14002c114`
- end: `0x14002c4ac`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `920`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x140017680`
- `0x14002bc90`
- `0x14004986c`
- `0x14005a240`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14002c114`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x14002c290`
- `ntdll!NtOpenEvent` at `0x14002c290`
- `ntdll!NtClose` at `0x14002c2d6`
- `ntdll!NtClose` at `0x14002c47d`
- `ntdll!NtClose` at `0x14002c2d6`
- `ntdll!NtClose` at `0x14002c47d`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14002c1b9`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14002c1b9`
- `ntdll!ZwUpdateWnfStateData` at `0x14002c1e8`
- `ntdll!ZwUpdateWnfStateData` at `0x14002c1e8`
- `ntdll!EtwEventWriteNoRegistration` at `0x14002c20b`
- `ntdll!EtwEventWriteNoRegistration` at `0x14002c20b`
- `ntdll!NtWaitForSingleObject` at `0x14002c2c9`
- `ntdll!NtWaitForSingleObject` at `0x14002c2c9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002c32c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002c32c`
- `ntdll!NtAlpcConnectPort` at `0x14002c3dd`
- `ntdll!NtAlpcConnectPort` at `0x14002c3dd`
- `ntdll!NtQuerySystemInformation` at `0x14002c231`
- `ntdll!NtQuerySystemInformation` at `0x14002c231`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14002c43a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14002c43a`
- `ntdll!RtlFreeSid` at `0x14002c46e`
- `ntdll!RtlFreeSid` at `0x14002c46e`
- `ntdll!RtlInitUnicodeString` at `0x14002c35d`
- `ntdll!RtlInitUnicodeString` at `0x14002c35d`

## string_xrefs

- `0x14002c246`: `\KernelObjects\SystemErrorPortReady`

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
0x14002c114  mov     [rsp-8+arg_18], rbx
0x14002c119  push    rbp
0x14002c11a  push    rsi
0x14002c11b  push    rdi
0x14002c11c  push    r12
0x14002c11e  push    r13
0x14002c120  push    r14
0x14002c122  push    r15
0x14002c124  lea     rbp, [rsp-80h]
0x14002c129  sub     rsp, 180h
0x14002c130  mov     rax, cs:__security_cookie
0x14002c137  xor     rax, rsp
0x14002c13a  mov     [rbp+0B0h+var_40], rax
0x14002c13e  xorps   xmm0, xmm0
0x14002c141  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x14002c147  xor     r13d, r13d
0x14002c14a  mov     r14, r8
0x14002c14d  mov     r15, rdx
0x14002c150  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r13d
0x14002c154  mov     r12, rcx
0x14002c157  xor     edx, edx; Val
0x14002c159  lea     rcx, [rbp+0B0h+var_90]; void *
0x14002c15d  lea     r8d, [r13+48h]; Size
0x14002c161  movups  [rbp+0B0h+var_108], xmm0
0x14002c165  movups  [rbp+0B0h+var_F8], xmm0
0x14002c169  movups  [rbp+0B0h+var_E8], xmm0
0x14002c16d  call    memset_0
0x14002c172  xorps   xmm0, xmm0
0x14002c175  mov     [rbp+0B0h+var_120], r13
0x14002c179  lea     edi, [r13+1]
0x14002c17d  mov     [rbp+0B0h+Handle], r13
0x14002c181  mov     edx, edi
0x14002c183  mov     [rsp+1B0h+var_138], r13
0x14002c188  lea     r9, [rsp+1B0h+EventHandle]
0x14002c18d  mov     [rsp+1B0h+var_140], r13
0x14002c192  xor     r8d, r8d
0x14002c195  mov     [rsp+1B0h+SystemInformation], r13
0x14002c19a  lea     rcx, WNF_WER_SERVICE_START
0x14002c1a1  mov     dword ptr [rsp+1B0h+EventHandle], r13d
0x14002c1a6  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14002c1aa  mov     ebx, r13d
0x14002c1ad  mov     [rsp+1B0h+SubAuthority2], 4
0x14002c1b5  movups  [rbp+0B0h+var_A0], xmm0
0x14002c1b9  call    cs:__imp_ZwQueryWnfStateNameInformation
0x14002c1bf  test    eax, eax
0x14002c1c1  js      short loc_14002C1F3
0x14002c1c3  cmp     dword ptr [rsp+1B0h+EventHandle], r13d
0x14002c1c8  jz      short loc_14002C1F3
0x14002c1ca  mov     [rsp+1B0h+SubAuthority4], r13d
0x14002c1cf  lea     rcx, WNF_WER_SERVICE_START
0x14002c1d6  mov     [rsp+1B0h+SubAuthority3], r13d
0x14002c1db  xor     r9d, r9d
0x14002c1de  xor     r8d, r8d
0x14002c1e1  mov     qword ptr [rsp+1B0h+SubAuthority2], r13
0x14002c1e6  xor     edx, edx
0x14002c1e8  call    cs:__imp_ZwUpdateWnfStateData
0x14002c1ee  test    eax, eax
0x14002c1f0  cmovns  ebx, edi
0x14002c1f3  xorps   xmm0, xmm0
0x14002c1f6  lea     rdx, [rbp+0B0h+var_A0]
0x14002c1fa  xor     r9d, r9d
0x14002c1fd  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x14002c204  xor     r8d, r8d
0x14002c207  movups  [rbp+0B0h+var_A0], xmm0
0x14002c20b  call    cs:__imp_EtwEventWriteNoRegistration
0x14002c211  test    eax, eax
0x14002c213  lea     ecx, [rbx+1]
0x14002c216  cmovnz  ecx, ebx
0x14002c219  test    ecx, ecx
0x14002c21b  jz      loc_14002C45F
0x14002c221  xor     r9d, r9d; ReturnLength
0x14002c224  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x14002c229  lea     r8d, [r9+8]; SystemInformationLength
0x14002c22d  lea     ecx, [r9+73h]; SystemInformationClass
0x14002c231  call    cs:__imp_NtQuerySystemInformation
0x14002c237  mov     ebx, eax
0x14002c239  test    eax, eax
0x14002c23b  js      loc_14002C464
0x14002c241  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x14002c246  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x14002c24d  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x14002c251  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x14002c255  lea     rax, [rbp+0B0h+var_A0]
0x14002c259  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x14002c261  xorps   xmm0, xmm0
0x14002c264  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14002c268  mov     edx, 100001h; DesiredAccess
0x14002c26d  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x14002c275  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x14002c27a  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r13
0x14002c27e  mov     [rsp+1B0h+EventHandle], r13
0x14002c283  mov     [rbp+0B0h+var_128], r13
0x14002c287  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r13
0x14002c28b  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c290  call    cs:__imp_NtOpenEvent
0x14002c296  mov     ebx, eax
0x14002c298  test    eax, eax
0x14002c29a  js      loc_14002C464
0x14002c2a0  cmp     esi, 0FFFFFFFFh
0x14002c2a3  jnz     short loc_14002C2AA
0x14002c2a5  mov     dl, dil
0x14002c2a8  jmp     short loc_14002C2B8
0x14002c2aa  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x14002c2b1  mov     dl, r13b
0x14002c2b4  mov     [rbp+0B0h+var_128], rcx
0x14002c2b8  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14002c2bd  lea     r8, [rbp+0B0h+var_128]
0x14002c2c1  test    dl, dl
0x14002c2c3  cmovnz  r8, r13; Timeout
0x14002c2c7  xor     edx, edx; Alertable
0x14002c2c9  call    cs:__imp_NtWaitForSingleObject
0x14002c2cf  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14002c2d4  mov     ebx, eax
0x14002c2d6  call    cs:__imp_NtClose
0x14002c2dc  test    ebx, ebx
0x14002c2de  js      loc_14002C464
0x14002c2e4  cmp     ebx, 102h
0x14002c2ea  jnz     short loc_14002C2F6
0x14002c2ec  mov     ebx, 0C0000353h
0x14002c2f1  jmp     loc_14002C464
0x14002c2f6  lea     rax, [rsp+1B0h+var_138]
0x14002c2fb  xor     r9d, r9d; SubAuthority1
0x14002c2fe  mov     [rsp+1B0h+Sid], rax; Sid
0x14002c303  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x14002c307  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x14002c30c  mov     dl, dil; SubAuthorityCount
0x14002c30f  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x14002c314  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x14002c319  lea     r8d, [r9+12h]; SubAuthority0
0x14002c31d  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x14002c322  mov     [rsp+1B0h+SubAuthority3], r13d; SubAuthority3
0x14002c327  mov     [rsp+1B0h+SubAuthority2], r13d; SubAuthority2
0x14002c32c  call    cs:__imp_RtlAllocateAndInitializeSid
0x14002c332  mov     ebx, eax
0x14002c334  test    eax, eax
0x14002c336  js      loc_14002C464
0x14002c33c  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x14002c341  jz      short loc_14002C356
0x14002c343  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x14002c348  mov     dil, r13b
0x14002c34b  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14002c352  mov     [rbp+0B0h+var_120], rcx
0x14002c356  mov     rdx, r12; SourceString
0x14002c359  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002c35d  call    cs:__imp_RtlInitUnicodeString
0x14002c363  xor     edx, edx; Val
0x14002c365  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x14002c36c  xorps   xmm0, xmm0
0x14002c36f  mov     qword ptr [rbp+0B0h+var_108+8], r13
0x14002c373  lea     rcx, [rbp+0B0h+var_90]; void *
0x14002c377  mov     dword ptr [rbp+0B0h+var_F8+8], r13d
0x14002c37b  mov     qword ptr [rbp+0B0h+var_F8], r13
0x14002c37f  lea     r8d, [rdx+48h]; Size
0x14002c383  movdqu  [rbp+0B0h+var_E8], xmm0
0x14002c388  call    memset_0
0x14002c38d  mov     rax, [rsp+1B0h+var_138]
0x14002c392  lea     rsi, [rbp+0B0h+var_120]
0x14002c396  test    dil, dil
0x14002c399  lea     r9, [rbp+0B0h+var_90]
0x14002c39d  mov     r12d, 578h
0x14002c3a3  lea     r8, [rbp+0B0h+var_108]
0x14002c3a7  cmovnz  rsi, r13
0x14002c3ab  mov     [rbp+0B0h+var_80], r12
0x14002c3af  mov     [rsp+1B0h+Sid], rsi
0x14002c3b4  lea     rdx, [rbp+0B0h+DestinationString]
0x14002c3b8  mov     qword ptr [rsp+1B0h+SubAuthority7], r13
0x14002c3bd  lea     rcx, [rbp+0B0h+Handle]
0x14002c3c1  mov     qword ptr [rsp+1B0h+SubAuthority6], r13
0x14002c3c6  mov     qword ptr [rsp+1B0h+SubAuthority5], r13
0x14002c3cb  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x14002c3d0  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14002c3d5  mov     [rsp+1B0h+SubAuthority2], 20000h
0x14002c3dd  call    cs:__imp_NtAlpcConnectPort
0x14002c3e3  mov     ebx, eax
0x14002c3e5  test    eax, eax
0x14002c3e7  js      short loc_14002C464
0x14002c3e9  mov     edi, 102h
0x14002c3ee  cmp     eax, edi
0x14002c3f0  jz      loc_14002C2EC
0x14002c3f6  lea     rcx, [r14+4]; void *
0x14002c3fa  xor     edx, edx; Val
0x14002c3fc  lea     r8d, [r12-4]; Size
0x14002c401  call    memset_0
0x14002c406  mov     rcx, [rbp+0B0h+Handle]
0x14002c40a  lea     rax, [rsp+1B0h+var_140]
0x14002c40f  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x14002c414  xor     r9d, r9d
0x14002c417  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x14002c41c  mov     r8, r15
0x14002c41f  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14002c424  mov     edx, 20000h
0x14002c429  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x14002c42e  mov     dword ptr [r14], 5780550h
0x14002c435  mov     [rsp+1B0h+var_140], r12
0x14002c43a  call    cs:__imp_NtAlpcSendWaitReceivePort
0x14002c440  mov     ebx, eax
0x14002c442  test    eax, eax
0x14002c444  js      short loc_14002C464
0x14002c446  cmp     eax, edi
0x14002c448  jz      short loc_14002C464
0x14002c44a  mov     rax, [rsp+1B0h+var_140]
0x14002c44f  sub     rax, r12
0x14002c452  neg     rax
0x14002c455  sbb     ebx, ebx
0x14002c457  and     ebx, 0C000021Fh
0x14002c45d  jmp     short loc_14002C464
0x14002c45f  mov     ebx, 0C0000080h
0x14002c464  mov     rcx, [rsp+1B0h+var_138]; Sid
0x14002c469  test    rcx, rcx
0x14002c46c  jz      short loc_14002C474
0x14002c46e  call    cs:__imp_RtlFreeSid
0x14002c474  mov     rcx, [rbp+0B0h+Handle]; Handle
0x14002c478  test    rcx, rcx
0x14002c47b  jz      short loc_14002C483
0x14002c47d  call    cs:__imp_NtClose
0x14002c483  mov     eax, ebx
0x14002c485  mov     rcx, [rbp+0B0h+var_40]
0x14002c489  xor     rcx, rsp; StackCookie
0x14002c48c  call    __security_check_cookie
0x14002c491  mov     rbx, [rsp+1B0h+arg_18]
0x14002c499  add     rsp, 180h
0x14002c4a0  pop     r15
0x14002c4a2  pop     r14
0x14002c4a4  pop     r13
0x14002c4a6  pop     r12
0x14002c4a8  pop     rdi
0x14002c4a9  pop     rsi
0x14002c4aa  pop     rbp
0x14002c4ab  retn
```
