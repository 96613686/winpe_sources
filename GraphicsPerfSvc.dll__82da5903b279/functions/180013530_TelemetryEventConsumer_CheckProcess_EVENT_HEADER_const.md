# TelemetryEventConsumer::CheckProcess(_EVENT_HEADER const &)

- ea: `0x180013530`
- end: `0x1800136fa`
- name: `?CheckProcess@TelemetryEventConsumer@@UEAA_NAEBU_EVENT_HEADER@@@Z`
- size: `458`
- prototype: `bool __fastcall(TelemetryEventConsumer *__hidden this, const struct _EVENT_HEADER *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180003ab0`
- `0x18000d778`
- `0x180011fb0`
- `0x180011fe0`
- `0x180012004`
- `0x1800124b0`
- `0x180013498`
- `0x180013530`
- `0x180022dec`
- `0x180022e90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001360f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001360f`
- `ntdll!NtQueryWnfStateData` at `0x1800135c8`
- `ntdll!NtQueryWnfStateData` at `0x1800135c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800135eb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800135eb`

## pseudocode

```c
bool __fastcall TelemetryEventConsumer::CheckProcess(TelemetryEventConsumer *this, const struct _EVENT_HEADER *a2)
{
  DWORD *v4; // rdi
  char *v5; // rbx
  __int64 ProcessName; // rax
  __int128 v7; // xmm7
  __int128 v8; // xmm6
  __int64 v9; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp-69h] BYREF
  int v12; // [rsp+3Ch] [rbp-65h] BYREF
  DWORD ExitCode; // [rsp+40h] [rbp-61h] BYREF
  int v14; // [rsp+44h] [rbp-5Dh] BYREF
  __int128 v15; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v17[28]; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v18[32]; // [rsp+98h] [rbp-9h] BYREF

  v4 = (DWORD *)((char *)this + 216);
  if ( !*((_BYTE *)this + 220) )
  {
    *v4 = 0;
    *((_BYTE *)this + 220) = 1;
    std::string::string(v18);
    v14 = 0;
    dwProcessId = 0;
    v12 = 4;
    if ( (int)NtQueryWnfStateData(&WNF_DX_GPM_TARGET, 0, 0, &v14, &dwProcessId, &v12) >= 0 && v12 == 4 )
    {
      v5 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
      *(_QWORD *)&v15 = v5;
      if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        ExitCode = 0;
        if ( GetExitCodeProcess(v5, &ExitCode)
          && ExitCode == 259
          && (int)GetProcessTelemetryAppSessionGuid(v5, (struct _GUID *)((char *)this + 200)) >= 0 )
        {
          *v4 = dwProcessId;
        }
        ProcessName = GetProcessName(v17, v5);
        std::string::operator=(v18, ProcessName);
        std::string::_Tidy_deallocate((__int64)v17);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    }
    v7 = *(_OWORD *)((char *)this + 200);
    *(_OWORD *)v17 = *((_OWORD *)g::spTraceConsumer + 17);
    *(_OWORD *)&v17[12] = *(_OWORD *)((char *)g::spTraceConsumer + 284);
    v8 = *(_OWORD *)&v17[12];
    v9 = std::string::string(v16, v18);
    v15 = v7;
    *(_OWORD *)&v17[12] = v8;
    gpm::TraceProvider::LogCheckProcess(*v4, v9, v17, &v15);
    std::string::_Tidy_deallocate((__int64)v18);
  }
  return a2->ProcessId == *v4;
}

```

## disassembly

```asm
0x180013530  mov     rax, rsp
0x180013533  mov     [rax+10h], rbx
0x180013537  mov     [rax+18h], rsi
0x18001353b  push    rbp
0x18001353c  push    rdi
0x18001353d  push    r14
0x18001353f  lea     rbp, [rax-5Fh]
0x180013543  sub     rsp, 0E0h
0x18001354a  movaps  xmmword ptr [rax-28h], xmm6
0x18001354e  movaps  xmmword ptr [rax-38h], xmm7
0x180013552  mov     rax, cs:__security_cookie
0x180013559  xor     rax, rsp
0x18001355c  mov     [rbp+57h+var_40], rax
0x180013560  mov     r14, rdx
0x180013563  mov     rsi, rcx
0x180013566  lea     rdi, [rcx+0D8h]
0x18001356d  cmp     byte ptr [rcx+0DCh], 0
0x180013574  jnz     loc_1800136C3
0x18001357a  mov     dword ptr [rdi], 0
0x180013580  mov     byte ptr [rcx+0DCh], 1
0x180013587  lea     rcx, [rbp+57h+var_60]
0x18001358b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180013590  nop
0x180013591  mov     [rbp+57h+var_B4], 0
0x180013598  mov     [rbp+57h+dwProcessId], 0
0x18001359f  mov     [rbp+57h+var_BC], 4
0x1800135a6  lea     rax, [rbp+57h+var_BC]
0x1800135aa  mov     [rsp+0F0h+var_C8], rax
0x1800135af  lea     rax, [rbp+57h+dwProcessId]
0x1800135b3  mov     [rsp+0F0h+var_D0], rax
0x1800135b8  lea     r9, [rbp+57h+var_B4]
0x1800135bc  xor     r8d, r8d
0x1800135bf  xor     edx, edx
0x1800135c1  lea     rcx, WNF_DX_GPM_TARGET
0x1800135c8  call    cs:__imp_NtQueryWnfStateData
0x1800135ce  test    eax, eax
0x1800135d0  js      loc_180013665
0x1800135d6  cmp     [rbp+57h+var_BC], 4
0x1800135da  jnz     loc_180013665
0x1800135e0  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1800135e4  xor     edx, edx; bInheritHandle
0x1800135e6  mov     ecx, 1000h; dwDesiredAccess
0x1800135eb  call    cs:__imp_OpenProcess
0x1800135f1  mov     rbx, rax
0x1800135f4  mov     qword ptr [rbp+57h+var_B0], rax
0x1800135f8  dec     rax
0x1800135fb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800135ff  ja      short loc_18001365C
0x180013601  mov     [rbp+57h+ExitCode], 0
0x180013608  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18001360c  mov     rcx, rbx; hProcess
0x18001360f  call    cs:__imp_GetExitCodeProcess
0x180013615  test    eax, eax
0x180013617  jz      short loc_18001363A
0x180013619  cmp     [rbp+57h+ExitCode], 103h
0x180013620  jnz     short loc_18001363A
0x180013622  lea     rdx, [rsi+0C8h]; struct _GUID *
0x180013629  mov     rcx, rbx; ProcessHandle
0x18001362c  call    ?GetProcessTelemetryAppSessionGuid@@YAJPEAXPEAU_GUID@@@Z; GetProcessTelemetryAppSessionGuid(void *,_GUID *)
0x180013631  test    eax, eax
0x180013633  js      short loc_18001363A
0x180013635  mov     eax, [rbp+57h+dwProcessId]
0x180013638  mov     [rdi], eax
0x18001363a  mov     rdx, rbx
0x18001363d  lea     rcx, [rbp+57h+var_80]
0x180013641  call    ?GetProcessName@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetProcessName(void *)
0x180013646  mov     rdx, rax
0x180013649  lea     rcx, [rbp+57h+var_60]
0x18001364d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180013652  lea     rcx, [rbp+57h+var_80]
0x180013656  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001365b  nop
0x18001365c  lea     rcx, [rbp+57h+var_B0]
0x180013660  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013665  movups  xmm7, xmmword ptr [rsi+0C8h]
0x18001366c  mov     rax, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180013673  movups  xmm0, xmmword ptr [rax+110h]
0x18001367a  movups  [rbp+57h+var_80], xmm0
0x18001367e  movups  xmm6, xmmword ptr [rax+11Ch]
0x180013685  movups  [rbp+57h+var_80+0Ch], xmm6
0x180013689  lea     rdx, [rbp+57h+var_60]
0x18001368d  lea     rcx, [rbp+57h+var_A0]
0x180013691  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180013696  movdqu  [rbp+57h+var_B0], xmm7
0x18001369b  movups  xmm0, [rbp+57h+var_80]
0x18001369f  movaps  [rbp+57h+var_80], xmm0
0x1800136a3  movups  [rbp+57h+var_80+0Ch], xmm6
0x1800136a7  lea     r9, [rbp+57h+var_B0]
0x1800136ab  lea     r8, [rbp+57h+var_80]
0x1800136af  mov     rdx, rax
0x1800136b2  mov     ecx, [rdi]
0x1800136b4  call    ?LogCheckProcess@TraceProvider@gpm@@SAXKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UConfig@PresentTraceConsumerCore@@U_GUID@@@Z; gpm::TraceProvider::LogCheckProcess(ulong,std::string,PresentTraceConsumerCore::Config,_GUID)
0x1800136b9  nop
0x1800136ba  lea     rcx, [rbp+57h+var_60]
0x1800136be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800136c3  mov     eax, [rdi]
0x1800136c5  cmp     [r14+0Ch], eax
0x1800136c9  setz    al
0x1800136cc  mov     rcx, [rbp+57h+var_40]
0x1800136d0  xor     rcx, rsp; StackCookie
0x1800136d3  call    __security_check_cookie
0x1800136d8  lea     r11, [rsp+0F0h+var_10]
0x1800136e0  mov     rbx, [r11+28h]
0x1800136e4  mov     rsi, [r11+30h]
0x1800136e8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800136ed  movaps  xmm7, xmmword ptr [r11-20h]
0x1800136f2  mov     rsp, r11
0x1800136f5  pop     r14
0x1800136f7  pop     rdi
0x1800136f8  pop     rbp
0x1800136f9  retn
```
