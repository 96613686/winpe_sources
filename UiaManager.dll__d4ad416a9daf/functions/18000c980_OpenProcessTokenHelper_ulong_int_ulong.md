# OpenProcessTokenHelper(ulong,int,ulong)

- ea: `0x18000c980`
- end: `0x18000cb43`
- name: `?OpenProcessTokenHelper@@YAPEAXKHK@Z`
- size: `451`
- prototype: `void *(unsigned int, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000c890`
- `0x18006ef3c`

## callees

- `0x18000c980`
- `0x180010f78`
- `0x18002c958`
- `0x18007f048`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000caa5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000caa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cb35`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cb35`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ca4d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ca7b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ca4d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ca7b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18000caf9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18000caf9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18000ca0a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18000ca0a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000caca`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000caca`

## pseudocode

```c
void *__fastcall OpenProcessTokenHelper(__int64 a1, int a2, DWORD a3)
{
  char *v4; // rbx
  HANDLE ProcessHandle[2]; // [rsp+20h] [rbp-10h] BYREF
  int v7; // [rsp+48h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF

  v7 = a2;
  TokenHandle = 0;
  if ( !BasicUiaUtils::s_isHoloLensDetermined )
  {
    v7 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
    BasicUiaUtils::s_isHoloLens = v7 == 10;
    BasicUiaUtils::s_isHoloLensDetermined = 1;
  }
  if ( BasicUiaUtils::s_isHoloLens )
    goto LABEL_19;
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop && !BasicUiaUtils::IsWinPE() )
  {
LABEL_19:
    if ( (int)UMgrOpenProcessTokenForQuery(a3, &TokenHandle) < 0 )
      TokenHandle = 0;
  }
  if ( !TokenHandle )
  {
    if ( !BasicUiaUtils::s_isHoloLensDetermined )
    {
      v7 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
      BasicUiaUtils::s_isHoloLens = v7 == 10;
      BasicUiaUtils::s_isHoloLensDetermined = 1;
    }
    if ( BasicUiaUtils::s_isHoloLens || BasicUiaUtils::IsOneCore() )
    {
      ProcessHandle[0] = 0;
      if ( (int)UMgrOpenProcessHandleForAccess(4096, a3, ProcessHandle) >= 0 )
      {
        v4 = (char *)ProcessHandle[0];
        ProcessHandle[0] = 0;
        goto LABEL_13;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(ProcessHandle);
    }
    v4 = (char *)OpenProcess(0x1000u, 0, a3);
LABEL_13:
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( !OpenProcessToken(v4, 8u, &TokenHandle) )
        TokenHandle = 0;
      CloseHandle(v4);
    }
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x18000c980  mov     [rsp-8+arg_0], rbx
0x18000c985  mov     [rsp-8+arg_8], edx
0x18000c989  push    rbp
0x18000c98a  mov     rbp, rsp
0x18000c98d  sub     rsp, 30h
0x18000c991  mov     al, cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18000c997  mov     ebx, r8d
0x18000c99a  mov     [rbp+TokenHandle], 0
0x18000c9a2  nop
0x18000c9a3  test    al, al
0x18000c9a5  jz      loc_18000CA3D
0x18000c9ab  cmp     cs:?s_isHoloLens@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isHoloLens
0x18000c9b2  jnz     loc_18000CAF3
0x18000c9b8  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18000c9be  nop
0x18000c9bf  test    al, al
0x18000c9c1  jz      loc_18000CAC5
0x18000c9c7  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isDesktop
0x18000c9ce  jz      loc_18000CAE6
0x18000c9d4  cmp     [rbp+TokenHandle], 0
0x18000c9d9  jnz     short loc_18000CA2E
0x18000c9db  mov     al, cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18000c9e1  nop
0x18000c9e2  test    al, al
0x18000c9e4  jz      loc_18000CA6B
0x18000c9ea  cmp     cs:?s_isHoloLens@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isHoloLens
0x18000c9f1  jz      loc_18000CB14
0x18000c9f7  lea     r8, [rbp+ProcessHandle]
0x18000c9fb  mov     [rbp+ProcessHandle], 0
0x18000ca03  mov     edx, ebx
0x18000ca05  mov     ecx, 1000h
0x18000ca0a  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x18000ca10  test    eax, eax
0x18000ca12  js      loc_18000CB22
0x18000ca18  mov     rbx, [rbp+ProcessHandle]
0x18000ca1c  mov     [rbp+ProcessHandle], 0
0x18000ca24  lea     rax, [rbx-1]
0x18000ca28  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ca2c  jbe     short loc_18000CA99
0x18000ca2e  mov     rax, [rbp+TokenHandle]
0x18000ca32  mov     rbx, [rsp+30h+arg_0]
0x18000ca37  add     rsp, 30h
0x18000ca3b  pop     rbp
0x18000ca3c  retn
0x18000ca3d  xor     r8d, r8d
0x18000ca40  mov     [rbp+arg_8], 0
0x18000ca47  lea     rdx, [rbp+arg_8]
0x18000ca4b  xor     ecx, ecx
0x18000ca4d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000ca53  cmp     [rbp+arg_8], 0Ah
0x18000ca57  setz    cs:?s_isHoloLens@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isHoloLens
0x18000ca5e  nop
0x18000ca5f  mov     cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18000ca66  jmp     loc_18000C9AB
0x18000ca6b  xor     r8d, r8d
0x18000ca6e  mov     [rbp+arg_8], 0
0x18000ca75  lea     rdx, [rbp+arg_8]
0x18000ca79  xor     ecx, ecx
0x18000ca7b  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000ca81  cmp     [rbp+arg_8], 0Ah
0x18000ca85  setz    cs:?s_isHoloLens@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isHoloLens
0x18000ca8c  nop
0x18000ca8d  mov     cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18000ca94  jmp     loc_18000C9EA
0x18000ca99  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000ca9d  mov     edx, 8; DesiredAccess
0x18000caa2  mov     rcx, rbx; ProcessHandle
0x18000caa5  call    cs:__imp_OpenProcessToken
0x18000caab  test    eax, eax
0x18000caad  jnz     short loc_18000CAB7
0x18000caaf  mov     [rbp+TokenHandle], 0
0x18000cab7  mov     rcx, rbx; hObject
0x18000caba  call    cs:__imp_CloseHandle
0x18000cac0  jmp     loc_18000CA2E
0x18000cac5  mov     ecx, 1800h; nIndex
0x18000caca  call    cs:__imp_GetSystemMetrics
0x18000cad0  test    eax, eax
0x18000cad2  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x18000cad9  nop
0x18000cada  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18000cae1  jmp     loc_18000C9C7
0x18000cae6  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x18000caeb  test    al, al
0x18000caed  jnz     loc_18000C9D4
0x18000caf3  lea     rdx, [rbp+TokenHandle]
0x18000caf7  mov     ecx, ebx
0x18000caf9  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18000caff  test    eax, eax
0x18000cb01  jns     loc_18000C9D4
0x18000cb07  mov     [rbp+TokenHandle], 0
0x18000cb0f  jmp     loc_18000C9D4
0x18000cb14  call    ?IsOneCore@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsOneCore(void)
0x18000cb19  test    al, al
0x18000cb1b  jz      short loc_18000CB2B
0x18000cb1d  jmp     loc_18000C9F7
0x18000cb22  lea     rcx, [rbp+ProcessHandle]
0x18000cb26  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000cb2b  mov     r8d, ebx; dwProcessId
0x18000cb2e  xor     edx, edx; bInheritHandle
0x18000cb30  mov     ecx, 1000h; dwDesiredAccess
0x18000cb35  call    cs:__imp_OpenProcess
0x18000cb3b  mov     rbx, rax
0x18000cb3e  jmp     loc_18000CA24
```
