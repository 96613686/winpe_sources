# BaseSrvNlsLogon

- ea: `0x180006740`
- end: `0x180006924`
- name: `BaseSrvNlsLogon`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006740`
- `0x180006930`
- `0x180006990`
- `0x18000d164`
- `0x18000d460`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x180006871`
- `ntdll!NtClose` at `0x18000688f`
- `ntdll!NtClose` at `0x180006913`
- `ntdll!NtClose` at `0x180006871`
- `ntdll!NtClose` at `0x18000688f`
- `ntdll!NtClose` at `0x180006913`
- `ntdll!RtlEnterCriticalSection` at `0x1800067d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800068e9`
- `ntdll!RtlEnterCriticalSection` at `0x1800067d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800068e9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800067f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800067f4`
- `ntdll!NtCreateKey` at `0x18000685f`
- `ntdll!NtCreateKey` at `0x18000685f`
- `ntdll!RtlInitUnicodeString` at `0x18000680f`
- `ntdll!RtlInitUnicodeString` at `0x18000680f`
- `ntdll!RtlOpenCurrentUser` at `0x1800067ad`
- `ntdll!RtlOpenCurrentUser` at `0x1800067ad`

## pseudocode

```c
int __fastcall BaseSrvNlsLogon(int a1)
{
  int GlobalizationUserModelType; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int result; // eax
  NTSTATUS v6; // ebx
  int v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int v10; // [rsp+A0h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF

  Handle = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( sxsFunctions )
    (*(void (**)(void))(sxsFunctions + 16))();
  if ( !a1 )
  {
    RtlEnterCriticalSection(&NlsCacheCriticalSection);
    if ( hCPanelIntlKeyRead != (HANDLE)-1LL )
    {
      NtClose(hCPanelIntlKeyRead);
      hCPanelIntlKeyRead = (HANDLE)-1LL;
    }
LABEL_11:
    RtlLeaveCriticalSection(&NlsCacheCriticalSection);
    return 0;
  }
  if ( !pNlsRegUserInfo )
    return 0;
  GetThreadAuthenticationId();
  GlobalizationUserModelType = GetGlobalizationUserModelType();
  if ( GlobalizationUserModelType == 1 )
  {
    result = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
  }
  else
  {
    v7 = GlobalizationUserModelType - 2;
    if ( v7 )
    {
      if ( v7 != 1 )
        return -1073741595;
      v10 = 0;
      result = OpenGlobalizationUserSettingsKey_ForMua(v4, v3, &KeyHandle, &v10);
    }
    else
    {
      result = OpenGlobalizationUserSettingsKey_ForSingleUserModel(v4, &KeyHandle);
    }
  }
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Control Panel\\International");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
    NtClose(KeyHandle);
    if ( v6 < 0 )
      return v6;
    RtlEnterCriticalSection(&NlsCacheCriticalSection);
    if ( hCPanelIntlKeyRead == (HANDLE)-1LL )
      hCPanelIntlKeyRead = Handle;
    else
      NtClose(Handle);
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x180006740  push    rbp
0x180006742  push    rbx
0x180006743  push    rdi
0x180006744  mov     rbp, rsp
0x180006747  sub     rsp, 80h
0x18000674e  xorps   xmm0, xmm0
0x180006751  xor     edi, edi
0x180006753  xor     eax, eax
0x180006755  mov     [rbp+Handle], rdi
0x180006759  mov     rax, cs:sxsFunctions
0x180006760  mov     ebx, ecx
0x180006762  mov     [rbp+KeyHandle], rdi
0x180006766  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000676a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000676e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180006772  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180006776  test    rax, rax
0x180006779  jz      short loc_180006784
0x18000677b  mov     rax, [rax+10h]
0x18000677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006784  test    ebx, ebx
0x180006786  jz      short loc_1800067C9
0x180006788  cmp     cs:pNlsRegUserInfo, rdi
0x18000678f  jz      short loc_180006800
0x180006791  call    GetThreadAuthenticationId
0x180006796  call    GetGlobalizationUserModelType
0x18000679b  cmp     eax, 1
0x18000679e  jnz     loc_1800068AB
0x1800067a4  lea     rdx, [rbp+KeyHandle]; KeyHandle
0x1800067a8  mov     ecx, 2000000h; DesiredAccess
0x1800067ad  call    cs:__imp_RtlOpenCurrentUser
0x1800067b4  nop     dword ptr [rax+rax+00h]
0x1800067b9  test    eax, eax
0x1800067bb  jns     short loc_180006804
0x1800067bd  add     rsp, 80h
0x1800067c4  pop     rdi
0x1800067c5  pop     rbx
0x1800067c6  pop     rbp
0x1800067c7  retn
0x1800067c9  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x1800067d0  call    cs:__imp_RtlEnterCriticalSection
0x1800067d7  nop     dword ptr [rax+rax+00h]
0x1800067dc  mov     rcx, cs:hCPanelIntlKeyRead; Handle
0x1800067e3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800067e7  jnz     loc_18000688F
0x1800067ed  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x1800067f4  call    cs:__imp_RtlLeaveCriticalSection
0x1800067fb  nop     dword ptr [rax+rax+00h]
0x180006800  xor     eax, eax
0x180006802  jmp     short loc_1800067BD
0x180006804  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x18000680b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000680f  call    cs:__imp_RtlInitUnicodeString
0x180006816  nop     dword ptr [rax+rax+00h]
0x18000681b  mov     rax, [rbp+KeyHandle]
0x18000681f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180006823  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180006827  lea     rcx, [rbp+Handle]; KeyHandle
0x18000682b  lea     rax, [rbp+DestinationString]
0x18000682f  mov     [rsp+80h+Disposition], rdi; Disposition
0x180006834  xorps   xmm0, xmm0
0x180006837  mov     [rsp+80h+CreateOptions], edi; CreateOptions
0x18000683b  xor     r9d, r9d; TitleIndex
0x18000683e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180006842  mov     edx, 20019h; DesiredAccess
0x180006847  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000684e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180006855  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000685a  mov     [rsp+80h+Class], rdi; Class
0x18000685f  call    cs:__imp_NtCreateKey
0x180006866  nop     dword ptr [rax+rax+00h]
0x18000686b  mov     rcx, [rbp+KeyHandle]; Handle
0x18000686f  mov     ebx, eax
0x180006871  call    cs:__imp_NtClose
0x180006878  nop     dword ptr [rax+rax+00h]
0x18000687d  test    ebx, ebx
0x18000687f  jns     short loc_1800068E2
0x180006881  mov     eax, ebx
0x180006883  add     rsp, 80h
0x18000688a  pop     rdi
0x18000688b  pop     rbx
0x18000688c  pop     rbp
0x18000688d  retn
0x18000688f  call    cs:__imp_NtClose
0x180006896  nop     dword ptr [rax+rax+00h]
0x18000689b  mov     cs:hCPanelIntlKeyRead, 0FFFFFFFFFFFFFFFFh
0x1800068a6  jmp     loc_1800067ED
0x1800068ab  sub     eax, 2
0x1800068ae  jz      short loc_1800068D4
0x1800068b0  cmp     eax, 1
0x1800068b3  jz      short loc_1800068BF
0x1800068b5  mov     eax, 0C00000E5h
0x1800068ba  jmp     loc_1800067BD
0x1800068bf  lea     r9, [rbp+arg_0]
0x1800068c3  mov     [rbp+arg_0], edi
0x1800068c6  lea     r8, [rbp+KeyHandle]
0x1800068ca  call    OpenGlobalizationUserSettingsKey_ForMua
0x1800068cf  jmp     loc_1800067B9
0x1800068d4  lea     rdx, [rbp+KeyHandle]
0x1800068d8  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x1800068dd  jmp     loc_1800067B9
0x1800068e2  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x1800068e9  call    cs:__imp_RtlEnterCriticalSection
0x1800068f0  nop     dword ptr [rax+rax+00h]
0x1800068f5  cmp     cs:hCPanelIntlKeyRead, 0FFFFFFFFFFFFFFFFh
0x1800068fd  jnz     short loc_18000690F
0x1800068ff  mov     rax, [rbp+Handle]
0x180006903  mov     cs:hCPanelIntlKeyRead, rax
0x18000690a  jmp     loc_1800067ED
0x18000690f  mov     rcx, [rbp+Handle]; Handle
0x180006913  call    cs:__imp_NtClose
0x18000691a  nop     dword ptr [rax+rax+00h]
0x18000691f  jmp     loc_1800067ED
```
