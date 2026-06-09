# PdcManager::AsyncPowerSession::AsyncPowerSession(_GUID const &,_NET_LUID_LH const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)

- ea: `0x180034e08`
- end: `0x180034ee3`
- name: `??0AsyncPowerSession@PdcManager@@QEAA@AEBU_GUID@@AEBT_NET_LUID_LH@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034d80`

## callees

- `0x180034e08`
- `0x180085be8`
- `0x180094da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eb0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180034e91`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180034e91`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180034e61`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180034e61`

## string_xrefs

- `0x180034eb9`: `ctl::ctThreadIocp::ctThreadIocp`
- `0x180034ec0`: `CreateThreadpoolIo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PdcManager::AsyncPowerSession::AsyncPowerSession(__int64 a1, _OWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v5; // rcx
  void *v6; // rcx
  PTP_IO ThreadpoolIo; // rax
  DWORD LastError; // eax
  bool v10; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = *a4;
  *a4 = -1;
  *(_OWORD *)(a1 + 16) = *a2;
  *(_QWORD *)(a1 + 32) = *a3;
  v5 = a1 + 40;
  *(_QWORD *)v5 = 0;
  *(_QWORD *)(v5 + 8) = 0;
  *(_OWORD *)(v5 + 16) = 0;
  *(_DWORD *)(v5 + 32) = 0;
  *(_DWORD *)(v5 + 36) = 2;
  *(_DWORD *)(v5 + 40) = 1;
  QueryPerformanceFrequency((LARGE_INTEGER *)v5);
  *(_DWORD *)(a1 + 88) = 0;
  v6 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  ThreadpoolIo = CreateThreadpoolIo(v6, ctl::ctThreadIocp::IoCompletionCallback, (PVOID)(a1 + 96), 0);
  *(_QWORD *)(a1 + 96) = ThreadpoolIo;
  if ( !ThreadpoolIo )
  {
    LastError = GetLastError();
    ctl::ctException::ctException(
      (ctl::ctException *)pExceptionObject,
      LastError,
      L"CreateThreadpoolIo",
      L"ctl::ctThreadIocp::ctThreadIocp",
      v10);
    throw (ctl::ctException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180034e08  mov     [rsp+arg_8], rbx
0x180034e0d  mov     [rsp+arg_0], rcx
0x180034e12  push    rdi
0x180034e13  sub     rsp, 70h
0x180034e17  mov     rdi, rcx
0x180034e1a  xor     eax, eax
0x180034e1c  mov     [rcx], rax
0x180034e1f  mov     rax, [r9]
0x180034e22  mov     [rcx+8], rax
0x180034e26  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x180034e2d  movups  xmm0, xmmword ptr [rdx]
0x180034e30  movdqu  xmmword ptr [rcx+10h], xmm0
0x180034e35  mov     rax, [r8]
0x180034e38  mov     [rcx+20h], rax
0x180034e3c  add     rcx, 28h ; '('; lpFrequency
0x180034e40  xor     eax, eax
0x180034e42  mov     [rcx], rax
0x180034e45  mov     [rcx+8], rax
0x180034e49  xorps   xmm0, xmm0
0x180034e4c  movups  xmmword ptr [rcx+10h], xmm0
0x180034e50  mov     [rcx+20h], eax
0x180034e53  mov     dword ptr [rcx+24h], 2
0x180034e5a  mov     dword ptr [rcx+28h], 1
0x180034e61  call    cs:__imp_QueryPerformanceFrequency
0x180034e67  mov     dword ptr [rdi+58h], 0
0x180034e6e  lea     rbx, [rdi+60h]
0x180034e72  mov     rcx, [rdi+8]; fl
0x180034e76  mov     qword ptr [rbx], 0
0x180034e7d  mov     dword ptr [rbx+8], 0
0x180034e84  xor     r9d, r9d; pcbe
0x180034e87  mov     r8, rbx; pv
0x180034e8a  lea     rdx, ?IoCompletionCallback@ctThreadIocp@ctl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180034e91  call    cs:__imp_CreateThreadpoolIo
0x180034e97  mov     [rbx], rax
0x180034e9a  test    rax, rax
0x180034e9d  jz      short loc_180034EB0
0x180034e9f  mov     rax, rdi
0x180034ea2  mov     rbx, [rsp+78h+arg_8]
0x180034eaa  add     rsp, 70h
0x180034eae  pop     rdi
0x180034eaf  retn
0x180034eb0  call    cs:__imp_GetLastError
0x180034eb6  nop
0x180034eb7  mov     edx, eax; unsigned int
0x180034eb9  lea     r9, aCtlCtthreadioc; "ctl::ctThreadIocp::ctThreadIocp"
0x180034ec0  lea     r8, aCreatethreadpo; "CreateThreadpoolIo"
0x180034ec7  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180034ecc  call    ??0ctException@ctl@@QEAA@KPEBG0_N@Z; ctl::ctException::ctException(ulong,ushort const *,ushort const *,bool)
0x180034ed1  lea     rdx, _TI2?AVctException@ctl@@; pThrowInfo
0x180034ed8  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180034edd  call    _CxxThrowException_0
```
