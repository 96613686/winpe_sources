# UtilIsMemoryErrorEventSet(void)

- ea: `0x140015324`
- end: `0x140015450`
- name: `?UtilIsMemoryErrorEventSet@@YA_NXZ`
- size: `300`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400135c0`

## callees

- `0x140005498`
- `0x140014474`
- `0x140015324`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001543a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001543a`
- `ntdll!NtQueryEvent` at `0x1400153f8`
- `ntdll!NtQueryEvent` at `0x1400153f8`
- `ntdll!NtOpenEvent` at `0x1400153a2`
- `ntdll!NtOpenEvent` at `0x1400153a2`
- `ntdll!RtlInitUnicodeString` at `0x140015361`
- `ntdll!RtlInitUnicodeString` at `0x140015361`

## pseudocode

```c
bool UtilIsMemoryErrorEventSet(void)
{
  bool v0; // bl
  void **v1; // rax
  NTSTATUS v2; // eax
  __int64 v3; // r9
  CUserModeHangReport *v4; // rcx
  __int64 v5; // rdx
  NTSTATUS v6; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  HANDLE EventHandle; // [rsp+80h] [rbp+10h] BYREF
  __int64 EventInformation; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  EventInformation = 0;
  v0 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\MemoryErrors");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 0;
  v1 = tlx::replace<tlx::file_handle_traits>(&EventHandle);
  v2 = NtOpenEvent(v1, 1u, &ObjectAttributes);
  v3 = (unsigned int)v2;
  if ( v2 >= 0 )
  {
    v6 = NtQueryEvent(EventHandle, EventBasicInformation, &EventInformation, 8u, 0);
    v3 = (unsigned int)v6;
    if ( v6 >= 0 )
    {
      v0 = HIDWORD(EventInformation) == 1;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 19;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 18;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, v3);
    }
  }
  if ( (unsigned __int64)EventHandle + 1 > 1 )
    CloseHandle(EventHandle);
  return v0;
}

```

## disassembly

```asm
0x140015324  mov     [rsp-8+arg_10], rbx
0x140015329  push    rbp
0x14001532a  mov     rbp, rsp
0x14001532d  sub     rsp, 70h
0x140015331  xorps   xmm0, xmm0
0x140015334  mov     [rbp+EventHandle], 0
0x14001533c  lea     rdx, SourceString; "\\KernelObjects\\MemoryErrors"
0x140015343  mov     [rbp+EventInformation], 0
0x14001534b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001534f  xor     bl, bl
0x140015351  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140015355  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140015359  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001535d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140015361  call    cs:__imp_RtlInitUnicodeString
0x140015367  lea     rax, [rbp+DestinationString]
0x14001536b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140015372  xorps   xmm0, xmm0
0x140015375  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140015379  lea     rcx, [rbp+EventHandle]
0x14001537d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140015385  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001538a  mov     [rbp+ObjectAttributes.Attributes], 0
0x140015391  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140015396  mov     rcx, rax; EventHandle
0x140015399  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001539d  mov     edx, 1; DesiredAccess
0x1400153a2  call    cs:__imp_NtOpenEvent
0x1400153a8  mov     r9d, eax
0x1400153ab  test    eax, eax
0x1400153ad  jns     short loc_1400153DF
0x1400153af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153b6  lea     rax, WPP_GLOBAL_Control
0x1400153bd  cmp     rcx, rax
0x1400153c0  jz      short loc_14001542C
0x1400153c2  test    byte ptr [rcx+1Ch], 1
0x1400153c6  jz      short loc_14001542C
0x1400153c8  mov     edx, 12h
0x1400153cd  mov     rcx, [rcx+10h]
0x1400153d1  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1400153d8  call    WPP_SF_d
0x1400153dd  jmp     short loc_14001542C
0x1400153df  mov     rcx, [rbp+EventHandle]; EventHandle
0x1400153e3  lea     r8, [rbp+EventInformation]; EventInformation
0x1400153e7  mov     r9d, 8; EventInformationLength
0x1400153ed  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1400153f6  xor     edx, edx; EventInformationClass
0x1400153f8  call    cs:__imp_NtQueryEvent
0x1400153fe  mov     r9d, eax
0x140015401  test    eax, eax
0x140015403  jns     short loc_140015425
0x140015405  mov     rcx, cs:WPP_GLOBAL_Control
0x14001540c  lea     rax, WPP_GLOBAL_Control
0x140015413  cmp     rcx, rax
0x140015416  jz      short loc_14001542C
0x140015418  test    byte ptr [rcx+1Ch], 1
0x14001541c  jz      short loc_14001542C
0x14001541e  mov     edx, 13h
0x140015423  jmp     short loc_1400153CD
0x140015425  cmp     dword ptr [rbp+EventInformation+4], 1
0x140015429  setz    bl
0x14001542c  mov     rcx, [rbp+EventHandle]; hObject
0x140015430  lea     rdx, [rcx+1]
0x140015434  cmp     rdx, 1
0x140015438  jbe     short loc_140015440
0x14001543a  call    cs:__imp_CloseHandle
0x140015440  mov     al, bl
0x140015442  mov     rbx, [rsp+70h+arg_10]
0x14001544a  add     rsp, 70h
0x14001544e  pop     rbp
0x14001544f  retn
```
