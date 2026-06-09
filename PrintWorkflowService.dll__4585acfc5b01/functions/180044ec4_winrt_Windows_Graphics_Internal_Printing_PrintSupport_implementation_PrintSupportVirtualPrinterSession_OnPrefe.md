# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::OnPreferredPdlConversionStarted(void)

- ea: `0x180044ec4`
- end: `0x180044f8a`
- name: `?OnPreferredPdlConversionStarted@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAAXXZ`
- size: `198`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004b810`

## callees

- `0x180003cd0`
- `0x1800127a4`
- `0x18001a7c0`
- `0x180021eac`
- `0x180023664`
- `0x180044a90`
- `0x180044ec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180044f03`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180044f03`

## string_xrefs

- `0x180044f63`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180044f78`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::OnPreferredPdlConversionStarted(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *this)
{
  int CallerProcessId; // eax
  HANDLE v3; // rax
  const char *v4; // r9
  _QWORD *v5; // rax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _QWORD *dwProcessId; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(dwProcessId) = 0;
  CallerProcessId = GetCallerProcessId((unsigned int *)&dwProcessId);
  if ( CallerProcessId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)CallerProcessId,
      v6);
  v3 = OpenProcess(0x101000u, 0, (DWORD)dwProcessId);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 464,
    v3);
  if ( !*((_QWORD *)this + 58) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x216,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      v4);
  *((_BYTE *)this + 489) = 0;
  v5 = operator new(0x40u);
  dwProcessId = v5;
  v5[7] = this;
  *v5 = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::MonitorPdlConversionTask__ResumeCoro_1;
  *((_DWORD *)v5 + 2) = 65538;
  *((_BYTE *)v5 + 48) = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::MonitorPdlConversionTask__ResumeCoro_1(v5);
}

```

## disassembly

```asm
0x180044ec4  mov     [rsp+arg_0], rbx
0x180044ec9  push    rdi
0x180044eca  sub     rsp, 30h
0x180044ece  mov     rdi, rcx
0x180044ed1  mov     dword ptr [rsp+38h+dwProcessId], 0
0x180044ed9  lea     rcx, [rsp+38h+dwProcessId]; unsigned int *
0x180044ede  call    ?GetCallerProcessId@@YAJPEAK@Z; GetCallerProcessId(ulong *)
0x180044ee3  mov     rcx, [rsp+38h]; this
0x180044ee8  test    eax, eax
0x180044eea  js      loc_180044F75
0x180044ef0  lea     rbx, [rdi+1D0h]
0x180044ef7  mov     r8d, dword ptr [rsp+38h+dwProcessId]; dwProcessId
0x180044efc  xor     edx, edx; bInheritHandle
0x180044efe  mov     ecx, 101000h; dwDesiredAccess
0x180044f03  call    cs:__imp_OpenProcess
0x180044f09  mov     rdx, rax
0x180044f0c  mov     rcx, rbx
0x180044f0f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044f14  mov     rcx, [rsp+38h]; this
0x180044f19  cmp     qword ptr [rbx], 0
0x180044f1d  jz      short loc_180044F63
0x180044f1f  mov     byte ptr [rdi+1E9h], 0
0x180044f26  mov     ecx, 40h ; '@'; Size
0x180044f2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044f30  mov     [rsp+38h+dwProcessId], rax
0x180044f35  mov     [rax+38h], rdi
0x180044f39  lea     rcx, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__MonitorPdlConversionTask$_ResumeCoro$1
0x180044f40  mov     [rax], rcx
0x180044f43  mov     dword ptr [rax+8], 10002h
0x180044f4a  xor     ecx, ecx
0x180044f4c  mov     [rax+30h], cl
0x180044f4f  mov     rcx, rax
0x180044f52  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__MonitorPdlConversionTask$_ResumeCoro$1
0x180044f57  nop
0x180044f58  mov     rbx, [rsp+38h+arg_0]
0x180044f5d  add     rsp, 30h
0x180044f61  pop     rdi
0x180044f62  retn
0x180044f63  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180044f6a  mov     edx, 216h; void *
0x180044f6f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180044f75  mov     r9d, eax; char *
0x180044f78  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180044f7f  mov     edx, 213h; void *
0x180044f84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
