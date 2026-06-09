# UtilIsMemoryErrorEventSet(void)

- ea: `0x140015e5c`
- end: `0x140015fa1`
- name: `?UtilIsMemoryErrorEventSet@@YA_NXZ`
- size: `325`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013f04`

## callees

- `0x140005550`
- `0x140014f14`
- `0x140015e5c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f84`
- `ntdll!NtQueryEvent` at `0x140015f3c`
- `ntdll!NtQueryEvent` at `0x140015f3c`
- `ntdll!NtOpenEvent` at `0x140015ee0`
- `ntdll!NtOpenEvent` at `0x140015ee0`
- `ntdll!RtlInitUnicodeString` at `0x140015e99`
- `ntdll!RtlInitUnicodeString` at `0x140015e99`

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
  v1 = (void **)tlx::replace<tlx::file_handle_traits>(&EventHandle);
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
0x140015e5c  mov     [rsp-8+arg_10], rbx
0x140015e61  push    rbp
0x140015e62  mov     rbp, rsp
0x140015e65  sub     rsp, 70h
0x140015e69  xorps   xmm0, xmm0
0x140015e6c  mov     [rbp+EventHandle], 0
0x140015e74  lea     rdx, SourceString; "\\KernelObjects\\MemoryErrors"
0x140015e7b  mov     [rbp+EventInformation], 0
0x140015e83  lea     rcx, [rbp+DestinationString]; DestinationString
0x140015e87  xor     bl, bl
0x140015e89  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140015e8d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140015e91  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140015e95  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140015e99  call    cs:__imp_RtlInitUnicodeString
0x140015ea0  nop     dword ptr [rax+rax+00h]
0x140015ea5  lea     rax, [rbp+DestinationString]
0x140015ea9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140015eb0  xorps   xmm0, xmm0
0x140015eb3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140015eb7  lea     rcx, [rbp+EventHandle]
0x140015ebb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140015ec3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140015ec8  mov     [rbp+ObjectAttributes.Attributes], 0
0x140015ecf  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140015ed4  mov     rcx, rax; EventHandle
0x140015ed7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140015edb  mov     edx, 1; DesiredAccess
0x140015ee0  call    cs:__imp_NtOpenEvent
0x140015ee7  nop     dword ptr [rax+rax+00h]
0x140015eec  mov     r9d, eax
0x140015eef  test    eax, eax
0x140015ef1  jns     short loc_140015F23
0x140015ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140015efa  lea     rax, WPP_GLOBAL_Control
0x140015f01  cmp     rcx, rax
0x140015f04  jz      short loc_140015F76
0x140015f06  test    byte ptr [rcx+1Ch], 1
0x140015f0a  jz      short loc_140015F76
0x140015f0c  mov     edx, 12h
0x140015f11  mov     rcx, [rcx+10h]
0x140015f15  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x140015f1c  call    WPP_SF_d
0x140015f21  jmp     short loc_140015F76
0x140015f23  mov     rcx, [rbp+EventHandle]; EventHandle
0x140015f27  lea     r8, [rbp+EventInformation]; EventInformation
0x140015f2b  mov     r9d, 8; EventInformationLength
0x140015f31  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x140015f3a  xor     edx, edx; EventInformationClass
0x140015f3c  call    cs:__imp_NtQueryEvent
0x140015f43  nop     dword ptr [rax+rax+00h]
0x140015f48  mov     r9d, eax
0x140015f4b  test    eax, eax
0x140015f4d  jns     short loc_140015F6F
0x140015f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f56  lea     rax, WPP_GLOBAL_Control
0x140015f5d  cmp     rcx, rax
0x140015f60  jz      short loc_140015F76
0x140015f62  test    byte ptr [rcx+1Ch], 1
0x140015f66  jz      short loc_140015F76
0x140015f68  mov     edx, 13h
0x140015f6d  jmp     short loc_140015F11
0x140015f6f  cmp     dword ptr [rbp+EventInformation+4], 1
0x140015f73  setz    bl
0x140015f76  mov     rcx, [rbp+EventHandle]; hObject
0x140015f7a  lea     rdx, [rcx+1]
0x140015f7e  cmp     rdx, 1
0x140015f82  jbe     short loc_140015F90
0x140015f84  call    cs:__imp_CloseHandle
0x140015f8b  nop     dword ptr [rax+rax+00h]
0x140015f90  mov     al, bl
0x140015f92  mov     rbx, [rsp+70h+arg_10]
0x140015f9a  add     rsp, 70h
0x140015f9e  pop     rbp
0x140015f9f  retn
```
