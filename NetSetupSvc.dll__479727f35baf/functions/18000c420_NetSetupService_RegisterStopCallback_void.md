# NetSetupService::RegisterStopCallback(void)

- ea: `0x18000c420`
- end: `0x18000c549`
- name: `?RegisterStopCallback@NetSetupService@@AEAAXXZ`
- size: `297`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x18000964c`
- `0x18000c420`
- `0x180031010`

## pseudocode

```c
void __fastcall NetSetupService::RegisterStopCallback(NetSetupService *this)
{
  __int64 v1; // r8
  __int64 (__fastcall *v3)(__int64 *, const WCHAR *, __int64, void (__fastcall *)(void *), NetSetupService *, int); // rax
  unsigned int v4; // edi
  __int64 v5; // rdx
  _QWORD v6[3]; // [rsp+40h] [rbp-108h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v8; // [rsp+128h] [rbp-20h] BYREF

  v1 = *((_QWORD *)this + 13);
  v3 = (__int64 (__fastcall *)(__int64 *, const WCHAR *, __int64, void (__fastcall *)(void *), NetSetupService *, int))*((_QWORD *)g_SvchostSharedGlobals + 24);
  v8 = 0;
  v4 = v3(&v8, L"netsetupsvc", v1, NetSetupService::OnStopThunk, this, 24);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v4);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v4);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( !v8 )
  {
    v6[2] = 0;
    v6[1] = "bad allocation";
    v6[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)v6;
  }
  v5 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v8;
  if ( v5 )
    SafeHandleCleanupIsUnregisterWait::operator()();
}

```

## disassembly

```asm
0x18000c420  mov     r11, rsp
0x18000c423  mov     [r11+10h], rbx
0x18000c427  push    rdi
0x18000c428  sub     rsp, 140h
0x18000c42f  mov     rax, cs:__security_cookie
0x18000c436  xor     rax, rsp
0x18000c439  mov     [rsp+148h+var_18], rax
0x18000c441  mov     rax, cs:?g_SvchostSharedGlobals@@3PEBU_SVCHOST_GLOBAL_DATA@@EB; _SVCHOST_GLOBAL_DATA const * const g_SvchostSharedGlobals
0x18000c448  lea     r9, ?OnStopThunk@NetSetupService@@CAXPEAXE@Z; NetSetupService::OnStopThunk(void *,uchar)
0x18000c44f  mov     r8, [rcx+68h]
0x18000c453  lea     rdx, ServiceName; "netsetupsvc"
0x18000c45a  mov     rbx, rcx
0x18000c45d  mov     [rsp+148h+var_120], 18h
0x18000c465  mov     [rsp+148h+var_128], rcx
0x18000c46a  lea     rcx, [r11-20h]
0x18000c46e  mov     rax, [rax+0C0h]
0x18000c475  mov     qword ptr [r11-20h], 0
0x18000c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c482  mov     edi, eax
0x18000c484  test    eax, eax
0x18000c486  jz      short loc_18000C4D7
0x18000c488  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c48f  lea     rax, WPP_GLOBAL_Control
0x18000c496  cmp     rcx, rax
0x18000c499  jz      short loc_18000C4B9
0x18000c49b  cmp     byte ptr [rcx+19h], 2
0x18000c49f  jb      short loc_18000C4B9
0x18000c4a1  mov     rcx, [rcx+10h]
0x18000c4a5  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000c4ac  mov     edx, 12h
0x18000c4b1  mov     r9d, edi
0x18000c4b4  call    WPP_SF_d
0x18000c4b9  mov     edx, edi; int
0x18000c4bb  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18000c4c0  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000c4c5  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000c4cc  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000c4d1  call    _CxxThrowException_0
0x18000c4d7  mov     rax, [rsp+148h+var_20]
0x18000c4df  test    rax, rax
0x18000c4e2  jnz     short loc_18000C516
0x18000c4e4  xorps   xmm0, xmm0
0x18000c4e7  lea     rax, aBadAllocation; "bad allocation"
0x18000c4ee  movups  [rsp+148h+var_100], xmm0
0x18000c4f3  mov     qword ptr [rsp+148h+var_100], rax
0x18000c4f8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000c4ff  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000c506  lea     rcx, [rsp+148h+var_108]; pExceptionObject
0x18000c50b  mov     [rsp+148h+var_108], rax
0x18000c510  call    _CxxThrowException_0
0x18000c516  mov     rdx, [rbx+70h]
0x18000c51a  mov     [rbx+70h], rax
0x18000c51e  test    rdx, rdx
0x18000c521  jz      short loc_18000C528
0x18000c523  call    ??RSafeHandleCleanupIsUnregisterWait@@QEBAXPEAX@Z; SafeHandleCleanupIsUnregisterWait::operator()(void *)
0x18000c528  mov     rcx, [rsp+148h+var_18]
0x18000c530  xor     rcx, rsp; StackCookie
0x18000c533  call    __security_check_cookie
0x18000c538  mov     rbx, [rsp+148h+arg_8]
0x18000c540  add     rsp, 140h
0x18000c547  pop     rdi
0x18000c548  retn
```
