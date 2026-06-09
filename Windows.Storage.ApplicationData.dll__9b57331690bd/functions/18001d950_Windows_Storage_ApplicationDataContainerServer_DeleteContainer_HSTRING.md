# Windows::Storage::ApplicationDataContainerServer::DeleteContainer(HSTRING__ *)

- ea: `0x18001d950`
- end: `0x18001da58`
- name: `?DeleteContainer@ApplicationDataContainerServer@Storage@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `264`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerServer *this, HSTRING__ *name)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005ee0`
- `0x1800092d0`
- `0x180009778`
- `0x1800187c0`
- `0x18001d950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d985`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d985`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9eb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainer` at `0x18001d9b0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainer` at `0x18001d9b0`

## string_xrefs

- `0x18001d9fb`: `DeleteStateContainer %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerServer::DeleteContainer(
        Windows::Storage::ApplicationDataContainerServer *this,
        HSTRING name)
{
  HRESULT v4; // ebx
  PCWSTR v5; // rax
  signed int LastError; // eax
  PCWSTR StringRawBuffer; // [rsp+28h] [rbp-10h]
  PCWSTR v9; // [rsp+28h] [rbp-10h]
  void *retaddr; // [rsp+38h] [rbp+0h]
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+50h] [rbp+18h] BYREF

  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_DELETECONTAINER_START);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&lock, &this->m_containerStateLock.SRWLock_);
  if ( !this->m_containerHandle )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(name, 0);
    v4 = -2147483629;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x22Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      -2147483629,
      "Name %ws",
      StringRawBuffer);
LABEL_9:
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    goto LABEL_14;
  }
  v5 = WindowsGetStringRawBuffer(name, 0);
  if ( !(unsigned int)DeleteStateContainer(this->m_containerHandle, v5) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 4312 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      Windows::Storage::StateABIHelpers::ReportError(v4, 8u);
      if ( v4 < 0 )
      {
        v9 = WindowsGetStringRawBuffer(name, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x23Bu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
          v4,
          "DeleteStateContainer %ws",
          v9);
      }
      goto LABEL_9;
    }
  }
  if ( lock.sync_ )
    ReleaseSRWLockExclusive(lock.sync_);
  v4 = 0;
LABEL_14:
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_DELETECONTAINER_STOP);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d950  mov     [rsp+arg_0], rbx
0x18001d955  push    rdi
0x18001d956  sub     rsp, 30h
0x18001d95a  mov     rbx, this
0x18001d95d  mov     rdi, name
0x18001d960  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_DELETECONTAINER_START; eventDescriptor
0x18001d967  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18001d96c  lea     name, [rbx+68h]; __annotation("WILSTG:|60365716|Feature_689378619|AlwaysEnabled")
0x18001d970  lea     this, [rsp+38h+lock]; result
0x18001d975  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001d97a  xor     edx, edx; length
0x18001d97c  mov     this, rdi; string
0x18001d97f  cmp     [rbx+58h], name
0x18001d983  jnz     short loc_18001D9A3
0x18001d985  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d98b  mov     [rsp+38h+var_10], rax
0x18001d990  mov     ebx, 80000013h
0x18001d995  lea     rax, aNameWs; "Name %ws"
0x18001d99c  mov     edx, 22Fh
0x18001d9a1  jmp     short loc_18001DA02
0x18001d9a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d9a9  mov     this, [rbx+58h]
0x18001d9ad  mov     name, rax
0x18001d9b0  call    cs:__imp_DeleteStateContainer
0x18001d9b6  test    eax, eax
0x18001d9b8  jnz     short loc_18001DA2D
0x18001d9ba  call    cs:__imp_GetLastError
0x18001d9c0  mov     ebx, eax
0x18001d9c2  cmp     eax, 10D8h
0x18001d9c7  jz      short loc_18001DA2D
0x18001d9c9  test    eax, eax
0x18001d9cb  jle     short loc_18001D9D6
0x18001d9cd  movzx   ebx, ax
0x18001d9d0  or      ebx, 80070000h
0x18001d9d6  mov     edx, 8; idsValue
0x18001d9db  mov     ecx, ebx; hr
0x18001d9dd  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18001d9e2  test    ebx, ebx
0x18001d9e4  jns     short loc_18001DA1B
0x18001d9e6  xor     edx, edx; length
0x18001d9e8  mov     this, rdi; string
0x18001d9eb  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d9f1  mov     [rsp+38h+var_10], rax
0x18001d9f6  mov     edx, 23Bh; lineNumber
0x18001d9fb  lea     rax, aDeletestatecon_1; "DeleteStateContainer %ws"
0x18001da02  mov     this, [rsp+38h]; callerReturnAddress
0x18001da07  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001da0e  mov     r9d, ebx; hr
0x18001da11  mov     [rsp+38h+formatString], rax; formatString
0x18001da16  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001da1b  mov     this, [rsp+38h+lock.sync_]; SRWLock
0x18001da20  test    this, this
0x18001da23  jz      short loc_18001DA3F
0x18001da25  call    cs:__imp_ReleaseSRWLockExclusive
0x18001da2b  jmp     short loc_18001DA3F
0x18001da2d  mov     this, [rsp+38h+lock.sync_]; SRWLock
0x18001da32  test    this, this
0x18001da35  jz      short loc_18001DA3D
0x18001da37  call    cs:__imp_ReleaseSRWLockExclusive
0x18001da3d  xor     ebx, ebx
0x18001da3f  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_DELETECONTAINER_STOP; eventDescriptor
0x18001da46  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18001da4b  mov     eax, ebx
0x18001da4d  mov     rbx, [rsp+38h+arg_0]
0x18001da52  add     rsp, 30h
0x18001da56  pop     rdi
0x18001da57  retn
```
