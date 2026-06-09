# KdcInitializeTrace

- ea: `0x180040664`
- end: `0x18004075f`
- name: `KdcInitializeTrace`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x180002ad0`
- `0x1800101ec`
- `0x180040664`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040686`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040686`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004069f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004069f`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180040707`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180040707`

## string_xrefs

- `0x18004067f`: `kdcsvc.dll`
- `0x1800406a9`: `kdcsvc.dll`

## pseudocode

```c
__int64 KdcInitializeTrace()
{
  HMODULE ModuleHandleW; // rax
  unsigned int v1; // ebx
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kdcsvc.dll");
  if ( !ModuleHandleW || !GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    wcscpy(Filename, L"kdcsvcdll");
  v1 = ((__int64 (__fastcall *)(unsigned int (__fastcall *)(enum WMIDPREQUESTCODE, void *, unsigned int *, void *), _QWORD, __int64 *, __int64, struct _TRACE_GUID_REGISTRATION near **, WCHAR *, const wchar_t *, __int64 *))EtwRegisterTraceGuidsW)(
         KdcTraceControlCallback,
         0,
         KdcControlGuid,
         3,
         &KdcTraceGuids,
         Filename,
         L"MofResource",
         &KdcTraceRegistrationHandle);
  if ( v1
    && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_aa1fff3ca3ee36d0f2982aba4dfee772_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180040664  push    rbx
0x180040666  sub     rsp, 260h
0x18004066d  mov     rax, cs:__security_cookie
0x180040674  xor     rax, rsp
0x180040677  mov     [rsp+268h+var_18], rax
0x18004067f  lea     rcx, aKdcsvcDll_0; "kdcsvc.dll"
0x180040686  call    cs:__imp_GetModuleHandleW
0x18004068c  test    rax, rax
0x18004068f  jz      short loc_1800406A9
0x180040691  mov     r8d, 104h; nSize
0x180040697  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18004069c  mov     rcx, rax; hModule
0x18004069f  call    cs:__imp_GetModuleFileNameW
0x1800406a5  test    eax, eax
0x1800406a7  jnz     short loc_1800406C3
0x1800406a9  movups  xmm0, xmmword ptr cs:aKdcsvcDll_0; "kdcsvc.dll"
0x1800406b0  movsd   xmm1, qword ptr cs:aKdcsvcDll_0+0Eh; "dll"
0x1800406b8  movaps  xmmword ptr [rsp+268h+Filename], xmm0
0x1800406bd  movsd   qword ptr [rsp+268h+Filename+0Eh], xmm1
0x1800406c3  lea     rax, KdcTraceRegistrationHandle
0x1800406ca  mov     r9d, 3
0x1800406d0  mov     [rsp+268h+var_230], rax
0x1800406d5  lea     r8, KdcControlGuid
0x1800406dc  lea     rax, aMofresource; "MofResource"
0x1800406e3  xor     edx, edx
0x1800406e5  mov     [rsp+268h+var_238], rax
0x1800406ea  lea     rcx, ?KdcTraceControlCallback@@YAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; KdcTraceControlCallback(WMIDPREQUESTCODE,void *,ulong *,void *)
0x1800406f1  lea     rax, [rsp+268h+Filename]
0x1800406f6  mov     [rsp+268h+var_240], rax
0x1800406fb  lea     rax, ?KdcTraceGuids@@3PAU_TRACE_GUID_REGISTRATION@@A; _TRACE_GUID_REGISTRATION near * KdcTraceGuids
0x180040702  mov     [rsp+268h+var_248], rax
0x180040707  call    cs:__imp_EtwRegisterTraceGuidsW
0x18004070d  mov     ebx, eax
0x18004070f  test    eax, eax
0x180040711  jz      short loc_180040744
0x180040713  mov     rcx, cs:WPP_GLOBAL_Control
0x18004071a  lea     rax, WPP_GLOBAL_Control
0x180040721  cmp     rcx, rax
0x180040724  jz      short loc_180040744
0x180040726  test    byte ptr [rcx+1Ch], 4
0x18004072a  jz      short loc_180040744
0x18004072c  mov     rcx, [rcx+10h]
0x180040730  lea     r8, WPP_aa1fff3ca3ee36d0f2982aba4dfee772_Traceguids
0x180040737  mov     edx, 0Ah
0x18004073c  mov     r9d, ebx
0x18004073f  call    WPP_SF_d
0x180040744  mov     eax, ebx
0x180040746  mov     rcx, [rsp+268h+var_18]
0x18004074e  xor     rcx, rsp; StackCookie
0x180040751  call    __security_check_cookie
0x180040756  add     rsp, 260h
0x18004075d  pop     rbx
0x18004075e  retn
```
