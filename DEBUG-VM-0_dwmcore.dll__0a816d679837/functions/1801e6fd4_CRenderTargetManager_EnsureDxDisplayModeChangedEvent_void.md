# CRenderTargetManager::EnsureDxDisplayModeChangedEvent(void)

- ea: `0x1801e6fd4`
- end: `0x1801e70b4`
- name: `?EnsureDxDisplayModeChangedEvent@CRenderTargetManager@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CRenderTargetManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18010b7d0`

## callees

- `0x1800098f8`
- `0x180042de0`
- `0x1801e6fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801e7086`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801e7086`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e700f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e700f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e70a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e70a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801e7027`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801e7027`

## pseudocode

```c
__int64 __fastcall CRenderTargetManager::EnsureDxDisplayModeChangedEvent(CRenderTargetManager *this)
{
  signed int v1; // ebx
  char *v2; // rdi
  unsigned __int64 v3; // rax
  signed int LastError; // eax
  HANDLE v5; // rax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = (char *)this + 696;
  v3 = *((_QWORD *)this + 87) - 1LL;
  SecurityDescriptor = 0;
  if ( v3 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)&EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    SetLastError(0);
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100002;;;WD)", 1u, &SecurityDescriptor, 0) )
    {
      v5 = CreateEventW(&EventAttributes, 1, 0, L"DWM_DX_FULLSCREEN_TRANSITION_EVENT");
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v2,
        v5);
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 >= 0 )
        v1 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, 0x1Cu, 0);
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801e6fd4  mov     r11, rsp
0x1801e6fd7  mov     [r11+10h], rbx
0x1801e6fdb  push    rdi
0x1801e6fdc  sub     rsp, 50h
0x1801e6fe0  xor     ebx, ebx
0x1801e6fe2  lea     rdi, [rcx+2B8h]
0x1801e6fe9  mov     rax, [rdi]
0x1801e6fec  dec     rax
0x1801e6fef  mov     [r11+8], rbx
0x1801e6ff3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e6ff7  jbe     loc_1801E70A7
0x1801e6ffd  xor     ecx, ecx; dwErrCode
0x1801e6fff  mov     qword ptr [r11-28h], 18h
0x1801e7007  mov     [r11-20h], rbx
0x1801e700b  mov     [r11-18h], rbx
0x1801e700f  call    cs:__imp_SetLastError
0x1801e7015  xor     r9d, r9d; SecurityDescriptorSize
0x1801e7018  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1801e701d  lea     edx, [rbx+1]; StringSDRevision
0x1801e7020  lea     rcx, aDA0x00100002Wd; "D:(A;;0x00100002;;;WD)"
0x1801e7027  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801e702d  test    eax, eax
0x1801e702f  jnz     short loc_1801E7073
0x1801e7031  call    cs:__imp_GetLastError
0x1801e7037  mov     ebx, eax
0x1801e7039  test    eax, eax
0x1801e703b  jle     short loc_1801E7046
0x1801e703d  movzx   ebx, ax
0x1801e7040  or      ebx, 80070000h
0x1801e7046  test    ebx, ebx
0x1801e7048  mov     [rsp+58h+var_30], 0; void *
0x1801e7051  mov     eax, 88980003h
0x1801e7056  mov     [rsp+58h+var_38], 1Ch; unsigned int
0x1801e705e  cmovns  ebx, eax
0x1801e7061  xor     edx, edx; int *
0x1801e7063  mov     r9d, ebx; int
0x1801e7066  xor     r8d, r8d; unsigned int
0x1801e7069  lea     ecx, [rdx+14h]; unsigned int
0x1801e706c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e7071  jmp     short loc_1801E7097
0x1801e7073  xor     r8d, r8d; bInitialState
0x1801e7076  lea     r9, aDwmDxFullscree; "DWM_DX_FULLSCREEN_TRANSITION_EVENT"
0x1801e707d  lea     rcx, [rsp+58h+EventAttributes]; lpEventAttributes
0x1801e7082  lea     edx, [r8+1]; bManualReset
0x1801e7086  call    cs:__imp_CreateEventW
0x1801e708c  mov     rdx, rax
0x1801e708f  mov     rcx, rdi
0x1801e7092  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801e7097  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1801e709c  test    rcx, rcx
0x1801e709f  jz      short loc_1801E70A7
0x1801e70a1  call    cs:__imp_LocalFree
0x1801e70a7  mov     eax, ebx
0x1801e70a9  mov     rbx, [rsp+58h+arg_8]
0x1801e70ae  add     rsp, 50h
0x1801e70b2  pop     rdi
0x1801e70b3  retn
```
