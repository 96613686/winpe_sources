# OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::ForceTerminateServiceProcess(SC_HANDLE__ *,ulong)

- ea: `0x1800f31b0`
- end: `0x1800f3321`
- name: `?ForceTerminateServiceProcess@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEAUSC_HANDLE__@@K@Z`
- size: `369`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this, SC_HANDLE, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f3d68`

## callees

- `0x1800529ec`
- `0x1800ab918`
- `0x1800aed10`
- `0x1800f31b0`
- `0x1800f4cb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f32c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f32c7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800f32a1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800f32a1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f3240`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f3240`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f31e6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f31e6`

## string_xrefs

- `0x1800f326c`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f32e8`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f3204`: `Failed to open service process %u for termination`
- `0x1800f327d`: `Failed to terminate service process %u. Current service process ID is different: %u`
- `0x1800f3250`: `Failed to query service status for process %u during termination`
- `0x1800f32d8`: `Failed to wait for service process %u to exit after termination`
- `0x1800f32b1`: `Failed to terminate service process %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::ForceTerminateServiceProcess(
        OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this,
        SC_HANDLE a2,
        DWORD a3)
{
  HANDLE v5; // rbx
  const char *v6; // r9
  __int64 v7; // rdx
  const char *pcbBytesNeeded; // [rsp+20h] [rbp-60h]
  char *v9; // [rsp+28h] [rbp-58h]
  int v10; // [rsp+30h] [rbp-50h]
  HANDLE v11; // [rsp+40h] [rbp-40h] BYREF
  DWORD v12; // [rsp+48h] [rbp-38h] BYREF
  BYTE Buffer[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a3 )
  {
    v5 = OpenProcess(0x100001u, 0, a3);
    v11 = v5;
    if ( (((unsigned __int64)v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v15 = 0;
      v12 = 0;
      *(_OWORD *)Buffer = 0;
      v14 = 0;
      if ( QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v12) )
      {
        if ( HIDWORD(v14) == a3 )
        {
          if ( !TerminateProcess(v5, 1u) )
          {
            v6 = "Failed to terminate service process %u";
            v7 = 1005;
            goto LABEL_12;
          }
          if ( WaitForSingleObject(v5, 0x7530u) == -1 )
          {
            v6 = "Failed to wait for service process %u to exit after termination";
            v7 = 1011;
            goto LABEL_12;
          }
        }
        else
        {
          v10 = HIDWORD(v14);
          LODWORD(v9) = a3;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
            (const char *)0x80070057LL,
            (int)"Failed to terminate service process %u. Current service process ID is different: %u",
            v9,
            v10);
        }
LABEL_13:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
        return;
      }
      v6 = "Failed to query service status for process %u during termination";
      v7 = 993;
    }
    else
    {
      v6 = "Failed to open service process %u for termination";
      v7 = 979;
    }
LABEL_12:
    LODWORD(pcbBytesNeeded) = a3;
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v6,
      pcbBytesNeeded);
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x1800f31b0  test    r8d, r8d
0x1800f31b3  jz      locret_1800F331F
0x1800f31b9  mov     [rsp-18h+arg_0], rbx
0x1800f31be  push    rbp
0x1800f31bf  push    rsi
0x1800f31c0  push    rdi
0x1800f31c1  mov     rbp, rsp
0x1800f31c4  sub     rsp, 80h
0x1800f31cb  mov     rax, cs:__security_cookie
0x1800f31d2  xor     rax, rsp
0x1800f31d5  mov     [rbp+var_8], rax
0x1800f31d9  mov     rsi, rdx
0x1800f31dc  mov     ecx, 100001h; dwDesiredAccess
0x1800f31e1  xor     edx, edx; bInheritHandle
0x1800f31e3  mov     edi, r8d
0x1800f31e6  call    cs:__imp_OpenProcess
0x1800f31ed  nop     dword ptr [rax+rax+00h]
0x1800f31f2  mov     rbx, rax
0x1800f31f5  mov     [rbp+var_40], rax
0x1800f31f9  inc     rax
0x1800f31fc  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800f3202  jnz     short loc_1800F3215
0x1800f3204  lea     r9, aFailedToOpenSe; "Failed to open service process %u for t"...
0x1800f320b  mov     edx, 3D3h
0x1800f3210  jmp     loc_1800F32E4
0x1800f3215  xor     eax, eax
0x1800f3217  lea     r8, [rbp+Buffer]; lpBuffer
0x1800f321b  xorps   xmm0, xmm0
0x1800f321e  mov     [rbp+var_10], eax
0x1800f3221  mov     [rbp+var_38], eax
0x1800f3224  mov     r9d, 24h ; '$'; cbBufSize
0x1800f322a  lea     rax, [rbp+var_38]
0x1800f322e  xor     edx, edx; InfoLevel
0x1800f3230  mov     rcx, rsi; hService
0x1800f3233  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800f3238  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800f323c  movups  [rbp+var_20], xmm0
0x1800f3240  call    cs:__imp_QueryServiceStatusEx
0x1800f3247  nop     dword ptr [rax+rax+00h]
0x1800f324c  test    eax, eax
0x1800f324e  jnz     short loc_1800F3261
0x1800f3250  lea     r9, aFailedToQueryS; "Failed to query service status for proc"...
0x1800f3257  mov     edx, 3E1h
0x1800f325c  jmp     loc_1800F32E4
0x1800f3261  mov     eax, dword ptr [rbp+var_20+0Ch]
0x1800f3264  cmp     eax, edi
0x1800f3266  jz      short loc_1800F3299
0x1800f3268  mov     rcx, [rbp+18h]; this
0x1800f326c  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800f3273  mov     [rsp+80h+var_50], eax
0x1800f3277  mov     r9d, 80070057h; char *
0x1800f327d  lea     rax, aFailedToTermin_0; "Failed to terminate service process %u."...
0x1800f3284  mov     dword ptr [rsp+80h+var_58], edi; char *
0x1800f3288  mov     edx, 3E7h; void *
0x1800f328d  mov     [rsp+80h+pcbBytesNeeded], rax; int
0x1800f3292  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f3297  jmp     short loc_1800F32F8
0x1800f3299  mov     edx, 1; uExitCode
0x1800f329e  mov     rcx, rbx; hProcess
0x1800f32a1  call    cs:__imp_TerminateProcess
0x1800f32a8  nop     dword ptr [rax+rax+00h]
0x1800f32ad  test    eax, eax
0x1800f32af  jnz     short loc_1800F32BF
0x1800f32b1  lea     r9, aFailedToTermin; "Failed to terminate service process %u"
0x1800f32b8  mov     edx, 3EDh
0x1800f32bd  jmp     short loc_1800F32E4
0x1800f32bf  mov     edx, 7530h; dwMilliseconds
0x1800f32c4  mov     rcx, rbx; hHandle
0x1800f32c7  call    cs:__imp_WaitForSingleObject
0x1800f32ce  nop     dword ptr [rax+rax+00h]
0x1800f32d3  cmp     eax, 0FFFFFFFFh
0x1800f32d6  jnz     short loc_1800F32F8
0x1800f32d8  lea     r9, aFailedToWaitFo; "Failed to wait for service process %u t"...
0x1800f32df  mov     edx, 3F3h; void *
0x1800f32e4  mov     rcx, [rbp+18h]; this
0x1800f32e8  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800f32ef  mov     dword ptr [rsp+80h+pcbBytesNeeded], edi; char *
0x1800f32f3  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800f32f8  lea     rcx, [rbp+var_40]
0x1800f32fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f3301  mov     rcx, [rbp+var_8]
0x1800f3305  xor     rcx, rsp; StackCookie
0x1800f3308  call    __security_check_cookie
0x1800f330d  mov     rbx, [rsp+80h+arg_0]
0x1800f3315  add     rsp, 80h
0x1800f331c  pop     rdi
0x1800f331d  pop     rsi
0x1800f331e  pop     rbp
0x1800f331f  retn
```
