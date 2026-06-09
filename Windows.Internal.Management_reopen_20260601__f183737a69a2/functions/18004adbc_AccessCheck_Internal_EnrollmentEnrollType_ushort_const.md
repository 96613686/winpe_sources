# AccessCheck_Internal(EnrollmentEnrollType,ushort const *)

- ea: `0x18004adbc`
- end: `0x18004afaf`
- name: `?AccessCheck_Internal@@YAJW4EnrollmentEnrollType@@PEBG@Z`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ac2c`
- `0x18004ac9c`

## callees

- `0x1800151e0`
- `0x180017a88`
- `0x1800181cc`
- `0x1800183bc`
- `0x180045a8c`
- `0x18004adbc`
- `0x18004be14`
- `0x1800598dc`
- `0x1800b67b4`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004aeeb`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004af33`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004aeeb`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004af33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ae33`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ae33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ae17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ae17`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18004ade5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18004ade5`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004af6c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004af6c`
- `ntdll!RtlIsMultiSessionSku` at `0x18004ae8c`
- `ntdll!RtlIsMultiSessionSku` at `0x18004ae8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AccessCheck_Internal(unsigned int a1, __int64 a2)
{
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-30h] BYREF
  int v10; // [rsp+24h] [rbp-2Ch] BYREF
  unsigned int Pid; // [rsp+28h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF

  v13[0] = 0;
  v13[2] = 0;
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(0, &Pid) == 1725 )
    goto LABEL_18;
  v4 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v13);
  if ( v4 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_6;
    }
    v15 = 0;
    v4 = CheckThreadAdmin(TokenHandle, &v15);
    if ( v4 < 0 || v15 != 1 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
      {
        String2 = 0;
        if ( (int)GetAppSid(TokenHandle, &String2) < 0
          || (wcscmp_0(
                L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
                String2)
           || (a1 > 0x18 || (v7 = 20971552, !_bittest(&v7, a1)))
           && ((v9 = 0, (int)DmIsSystemOrUserIsAdmin(&v9) < 0) || v9 != 1))
          && (wcscmp_0(L"S-1-15-2-2434737943-167758768-3180539153-984336765-1107280622-3591121930-2677285773", String2)
           || (v10 = 0, (int)DmIsSystemOrUserIsAdmin(&v10) < 0)
           || v10 != 1) )
        {
          CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&String2);
LABEL_25:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          v4 = -2147024891;
          goto LABEL_26;
        }
        CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&String2);
        goto LABEL_17;
      }
      AutoImpersonate::RevertToSelf((AutoImpersonate *)v13);
      LOBYTE(String2) = 0;
      v4 = CapabilityCheck(TokenHandle, a2, &String2);
      if ( v4 >= 0 )
      {
        if ( (_BYTE)String2 != 1 )
          goto LABEL_25;
LABEL_17:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_18:
        v4 = 0;
        goto LABEL_26;
      }
    }
LABEL_6:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
LABEL_26:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004adbc  mov     [rsp-18h+arg_0], rbx
0x18004adc1  push    rbp
0x18004adc2  push    rsi
0x18004adc3  push    rdi
0x18004adc4  mov     rbp, rsp
0x18004adc7  sub     rsp, 50h
0x18004adcb  mov     rsi, rdx
0x18004adce  mov     edi, ecx
0x18004add0  mov     [rbp+var_18], 0
0x18004add4  mov     [rbp+var_16], 0
0x18004add8  mov     [rbp+Pid], 0
0x18004addf  lea     rdx, [rbp+Pid]; Pid
0x18004ade3  xor     ecx, ecx; Binding
0x18004ade5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18004adec  nop     dword ptr [rax+rax+00h]
0x18004adf1  cmp     eax, 6BDh
0x18004adf6  jz      loc_18004AF14
0x18004adfc  lea     rcx, [rbp+var_18]; this
0x18004ae00  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18004ae05  mov     ebx, eax
0x18004ae07  test    eax, eax
0x18004ae09  js      loc_18004AF96
0x18004ae0f  mov     [rbp+TokenHandle], 0
0x18004ae17  call    cs:__imp_GetCurrentThread
0x18004ae1e  nop     dword ptr [rax+rax+00h]
0x18004ae23  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004ae27  mov     edx, 8; DesiredAccess
0x18004ae2c  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ae30  mov     rcx, rax; ThreadHandle
0x18004ae33  call    cs:__imp_OpenThreadToken
0x18004ae3a  nop     dword ptr [rax+rax+00h]
0x18004ae3f  test    eax, eax
0x18004ae41  jnz     short loc_18004AE6C
0x18004ae43  call    cs:__imp_GetLastError
0x18004ae4a  nop     dword ptr [rax+rax+00h]
0x18004ae4f  mov     ebx, eax
0x18004ae51  test    eax, eax
0x18004ae53  jle     short loc_18004AE5E
0x18004ae55  movzx   ebx, ax
0x18004ae58  or      ebx, 80070000h
0x18004ae5e  lea     rcx, [rbp+TokenHandle]
0x18004ae62  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ae67  jmp     loc_18004AF96
0x18004ae6c  mov     [rbp+arg_18], 0
0x18004ae73  lea     rdx, [rbp+arg_18]
0x18004ae77  mov     rcx, [rbp+TokenHandle]
0x18004ae7b  call    CheckThreadAdmin
0x18004ae80  mov     ebx, eax
0x18004ae82  test    eax, eax
0x18004ae84  js      short loc_18004AE8C
0x18004ae86  cmp     [rbp+arg_18], 1
0x18004ae8a  jz      short loc_18004AE5E
0x18004ae8c  call    cs:__imp_RtlIsMultiSessionSku
0x18004ae93  nop     dword ptr [rax+rax+00h]
0x18004ae98  test    al, al
0x18004ae9a  jz      loc_18004AF54
0x18004aea0  mov     [rbp+String2], 0
0x18004aea8  lea     rdx, [rbp+String2]
0x18004aeac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004aeb0  call    GetAppSid
0x18004aeb5  test    eax, eax
0x18004aeb7  js      loc_18004AF49
0x18004aebd  mov     rdx, [rbp+String2]; String2
0x18004aec1  lea     rcx, aS1152191009188; "S-1-15-2-1910091885-1573563583-11049412"...
0x18004aec8  call    wcscmp_0
0x18004aecd  test    eax, eax
0x18004aecf  jnz     short loc_18004AF18
0x18004aed1  cmp     edi, 18h
0x18004aed4  ja      short loc_18004AEE0
0x18004aed6  mov     eax, 1400020h
0x18004aedb  bt      eax, edi
0x18004aede  jb      short loc_18004AF01
0x18004aee0  mov     [rbp+var_30], 0
0x18004aee7  lea     rcx, [rbp+var_30]
0x18004aeeb  call    cs:__imp_?DmIsSystemOrUserIsAdmin@@YAJPEAH@Z; DmIsSystemOrUserIsAdmin(int *)
0x18004aef2  nop     dword ptr [rax+rax+00h]
0x18004aef7  test    eax, eax
0x18004aef9  js      short loc_18004AF18
0x18004aefb  cmp     [rbp+var_30], 1
0x18004aeff  jnz     short loc_18004AF18
0x18004af01  lea     rcx, [rbp+String2]
0x18004af05  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18004af0a  nop
0x18004af0b  lea     rcx, [rbp+TokenHandle]
0x18004af0f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004af14  xor     ebx, ebx
0x18004af16  jmp     short loc_18004AF96
0x18004af18  mov     rdx, [rbp+String2]; String2
0x18004af1c  lea     rcx, aS1152243473794; "S-1-15-2-2434737943-167758768-318053915"...
0x18004af23  call    wcscmp_0
0x18004af28  test    eax, eax
0x18004af2a  jnz     short loc_18004AF49
0x18004af2c  mov     [rbp+var_2C], eax
0x18004af2f  lea     rcx, [rbp+var_2C]
0x18004af33  call    cs:__imp_?DmIsSystemOrUserIsAdmin@@YAJPEAH@Z; DmIsSystemOrUserIsAdmin(int *)
0x18004af3a  nop     dword ptr [rax+rax+00h]
0x18004af3f  test    eax, eax
0x18004af41  js      short loc_18004AF49
0x18004af43  cmp     [rbp+var_2C], 1
0x18004af47  jz      short loc_18004AF01
0x18004af49  lea     rcx, [rbp+String2]
0x18004af4d  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18004af52  jmp     short loc_18004AF88
0x18004af54  lea     rcx, [rbp+var_18]; this
0x18004af58  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18004af5d  mov     byte ptr [rbp+String2], 0
0x18004af61  lea     r8, [rbp+String2]
0x18004af65  mov     rdx, rsi
0x18004af68  mov     rcx, [rbp+TokenHandle]
0x18004af6c  call    cs:__imp_CapabilityCheck
0x18004af73  nop     dword ptr [rax+rax+00h]
0x18004af78  mov     ebx, eax
0x18004af7a  test    eax, eax
0x18004af7c  js      loc_18004AE5E
0x18004af82  cmp     byte ptr [rbp+String2], 1
0x18004af86  jz      short loc_18004AF0B
0x18004af88  lea     rcx, [rbp+TokenHandle]
0x18004af8c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004af91  mov     ebx, 80070005h
0x18004af96  lea     rcx, [rbp+var_18]; this
0x18004af9a  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18004af9f  mov     eax, ebx
0x18004afa1  mov     rbx, [rsp+50h+arg_0]
0x18004afa6  add     rsp, 50h
0x18004afaa  pop     rdi
0x18004afab  pop     rsi
0x18004afac  pop     rbp
0x18004afad  retn
```
