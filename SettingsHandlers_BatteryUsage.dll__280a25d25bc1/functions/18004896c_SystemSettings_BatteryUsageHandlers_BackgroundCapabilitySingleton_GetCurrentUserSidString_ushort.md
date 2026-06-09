# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(ushort * *)

- ea: `0x18004896c`
- end: `0x1800489ec`
- name: `?GetCurrentUserSidString@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAG@Z`
- size: `128`
- prototype: `int(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800483dc`
- `0x1800485c8`
- `0x18004876c`
- `0x180048b00`
- `0x180048ee8`

## callees

- `0x18000a13c`
- `0x180047fac`
- `0x18004884c`
- `0x18004896c`
- `0x180048d80`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800489c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800489c0`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        unsigned __int16 **a2)
{
  int CurrentUserSid; // eax
  unsigned int v4; // ebx
  unsigned int Error; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  Sid = 0;
  CurrentUserSid = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSid(this, &Sid);
  v4 = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, a2) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    v4 = Error;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  return v4;
}

```

## disassembly

```asm
0x18004896c  mov     rax, rsp
0x18004896f  mov     [rax+10h], rbx
0x180048973  mov     [rax+8], rcx
0x180048977  push    rdi; int
0x180048978  sub     rsp, 20h
0x18004897c  mov     rdi, rdx
0x18004897f  mov     qword ptr [rdx], 0
0x180048986  lea     rdx, [rax+8]; void **
0x18004898a  mov     qword ptr [rax+8], 0
0x180048992  call    ?GetCurrentUserSid@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAX@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSid(void * *)
0x180048997  mov     ebx, eax
0x180048999  test    eax, eax
0x18004899b  jns     short loc_1800489B8
0x18004899d  mov     rcx, [rsp+28h]; this
0x1800489a2  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x1800489a9  mov     r9d, eax; char *
0x1800489ac  mov     edx, 0DCh; void *
0x1800489b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800489b6  jmp     short loc_1800489D5
0x1800489b8  mov     rcx, [rsp+28h+Sid]; Sid
0x1800489bd  mov     rdx, rdi; StringSid
0x1800489c0  call    cs:__imp_ConvertSidToStringSidW
0x1800489c6  test    eax, eax
0x1800489c8  jz      short loc_1800489CE
0x1800489ca  xor     eax, eax
0x1800489cc  jmp     short loc_1800489D3
0x1800489ce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800489d3  mov     ebx, eax
0x1800489d5  lea     rcx, [rsp+28h+Sid]
0x1800489da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800489df  mov     eax, ebx
0x1800489e1  mov     rbx, [rsp+28h+arg_8]
0x1800489e6  add     rsp, 20h
0x1800489ea  pop     rdi
0x1800489eb  retn
```
