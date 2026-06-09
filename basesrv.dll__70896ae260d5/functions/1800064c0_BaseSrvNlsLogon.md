# BaseSrvNlsLogon

- ea: `0x1800064c0`
- end: `0x180006698`
- name: `BaseSrvNlsLogon`
- size: `472`
- prototype: `NTSTATUS __fastcall(int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800064c0`
- `0x1800066a0`
- `0x180006700`
- `0x18000cd80`
- `0x18000d074`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x1800065e6`
- `ntdll!NtClose` at `0x180006632`
- `ntdll!NtClose` at `0x180006660`
- `ntdll!NtClose` at `0x1800065e6`
- `ntdll!NtClose` at `0x180006632`
- `ntdll!NtClose` at `0x180006660`
- `ntdll!RtlEnterCriticalSection` at `0x18000660b`
- `ntdll!RtlEnterCriticalSection` at `0x180006647`
- `ntdll!RtlEnterCriticalSection` at `0x18000660b`
- `ntdll!RtlEnterCriticalSection` at `0x180006647`
- `ntdll!RtlLeaveCriticalSection` at `0x18000667e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000667e`
- `ntdll!NtCreateKey` at `0x1800065d4`
- `ntdll!NtCreateKey` at `0x1800065d4`
- `ntdll!RtlInitUnicodeString` at `0x180006584`
- `ntdll!RtlInitUnicodeString` at `0x180006584`
- `ntdll!RtlOpenCurrentUser` at `0x180006565`
- `ntdll!RtlOpenCurrentUser` at `0x180006565`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvNlsLogon(int a1)
{
  int GlobalizationUserModelType; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
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
LABEL_20:
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
    v5 = GlobalizationUserModelType - 2;
    if ( v5 )
    {
      if ( v5 != 1 )
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
    v7 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
    NtClose(KeyHandle);
    if ( v7 < 0 )
      return v7;
    RtlEnterCriticalSection(&NlsCacheCriticalSection);
    if ( hCPanelIntlKeyRead == (HANDLE)-1LL )
      hCPanelIntlKeyRead = Handle;
    else
      NtClose(Handle);
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x1800064c0  push    rbp
0x1800064c2  push    rbx
0x1800064c3  push    rdi
0x1800064c4  mov     rbp, rsp
0x1800064c7  sub     rsp, 80h
0x1800064ce  xor     eax, eax
0x1800064d0  xor     edi, edi
0x1800064d2  xorps   xmm0, xmm0
0x1800064d5  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x1800064d9  mov     dword ptr [rbp+ObjectAttributes.SecurityQualityOfService], eax
0x1800064dc  mov     ebx, ecx
0x1800064de  mov     rax, cs:sxsFunctions
0x1800064e5  mov     [rbp+Handle], rdi
0x1800064e9  mov     [rbp+KeyHandle], rdi
0x1800064ed  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800064f1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800064f5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800064f9  test    rax, rax
0x1800064fc  jz      short loc_180006507
0x1800064fe  mov     rax, [rax+10h]
0x180006502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006507  test    ebx, ebx
0x180006509  jz      loc_180006640
0x18000650f  cmp     cs:pNlsRegUserInfo, rdi
0x180006516  jz      loc_18000668A
0x18000651c  call    GetThreadAuthenticationId
0x180006521  call    GetGlobalizationUserModelType
0x180006526  cmp     eax, 1
0x180006529  jz      short loc_18000655C
0x18000652b  sub     eax, 2
0x18000652e  jz      short loc_180006551
0x180006530  cmp     eax, 1
0x180006533  jz      short loc_18000653F
0x180006535  mov     eax, 0C00000E5h
0x18000653a  jmp     loc_18000668C
0x18000653f  lea     r9, [rbp+arg_0]
0x180006543  mov     [rbp+arg_0], edi
0x180006546  lea     r8, [rbp+KeyHandle]
0x18000654a  call    OpenGlobalizationUserSettingsKey_ForMua
0x18000654f  jmp     short loc_180006571
0x180006551  lea     rdx, [rbp+KeyHandle]
0x180006555  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18000655a  jmp     short loc_180006571
0x18000655c  lea     rdx, [rbp+KeyHandle]; KeyHandle
0x180006560  mov     ecx, 2000000h; DesiredAccess
0x180006565  call    cs:__imp_RtlOpenCurrentUser
0x18000656c  nop     dword ptr [rax+rax+00h]
0x180006571  test    eax, eax
0x180006573  js      loc_18000668C
0x180006579  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x180006580  lea     rcx, [rbp+DestinationString]; DestinationString
0x180006584  call    cs:__imp_RtlInitUnicodeString
0x18000658b  nop     dword ptr [rax+rax+00h]
0x180006590  mov     rax, [rbp+KeyHandle]
0x180006594  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180006598  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18000659c  lea     rcx, [rbp+Handle]; KeyHandle
0x1800065a0  lea     rax, [rbp+DestinationString]
0x1800065a4  mov     [rsp+80h+Disposition], rdi; Disposition
0x1800065a9  xorps   xmm0, xmm0
0x1800065ac  mov     [rsp+80h+CreateOptions], edi; CreateOptions
0x1800065b0  xor     r9d, r9d; TitleIndex
0x1800065b3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800065b7  mov     edx, 20019h; DesiredAccess
0x1800065bc  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800065c3  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800065ca  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800065cf  mov     [rsp+80h+Class], rdi; Class
0x1800065d4  call    cs:__imp_NtCreateKey
0x1800065db  nop     dword ptr [rax+rax+00h]
0x1800065e0  mov     rcx, [rbp+KeyHandle]; Handle
0x1800065e4  mov     ebx, eax
0x1800065e6  call    cs:__imp_NtClose
0x1800065ed  nop     dword ptr [rax+rax+00h]
0x1800065f2  test    ebx, ebx
0x1800065f4  jns     short loc_180006604
0x1800065f6  mov     eax, ebx
0x1800065f8  add     rsp, 80h
0x1800065ff  pop     rdi
0x180006600  pop     rbx
0x180006601  pop     rbp
0x180006602  retn
0x180006604  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x18000660b  call    cs:__imp_RtlEnterCriticalSection
0x180006612  nop     dword ptr [rax+rax+00h]
0x180006617  cmp     cs:hCPanelIntlKeyRead, 0FFFFFFFFFFFFFFFFh
0x18000661f  jnz     short loc_18000662E
0x180006621  mov     rax, [rbp+Handle]
0x180006625  mov     cs:hCPanelIntlKeyRead, rax
0x18000662c  jmp     short loc_180006677
0x18000662e  mov     rcx, [rbp+Handle]; Handle
0x180006632  call    cs:__imp_NtClose
0x180006639  nop     dword ptr [rax+rax+00h]
0x18000663e  jmp     short loc_180006677
0x180006640  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x180006647  call    cs:__imp_RtlEnterCriticalSection
0x18000664e  nop     dword ptr [rax+rax+00h]
0x180006653  mov     rcx, cs:hCPanelIntlKeyRead; Handle
0x18000665a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000665e  jz      short loc_180006677
0x180006660  call    cs:__imp_NtClose
0x180006667  nop     dword ptr [rax+rax+00h]
0x18000666c  mov     cs:hCPanelIntlKeyRead, 0FFFFFFFFFFFFFFFFh
0x180006677  lea     rcx, NlsCacheCriticalSection; CriticalSection
0x18000667e  call    cs:__imp_RtlLeaveCriticalSection
0x180006685  nop     dword ptr [rax+rax+00h]
0x18000668a  xor     eax, eax
0x18000668c  add     rsp, 80h
0x180006693  pop     rdi
0x180006694  pop     rbx
0x180006695  pop     rbp
0x180006696  retn
```
