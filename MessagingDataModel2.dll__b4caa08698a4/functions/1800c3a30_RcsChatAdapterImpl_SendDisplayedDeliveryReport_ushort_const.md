# RcsChatAdapterImpl::SendDisplayedDeliveryReport(ushort const *)

- ea: `0x1800c3a30`
- end: `0x1800c3b29`
- name: `?SendDisplayedDeliveryReport@RcsChatAdapterImpl@@UEAAJPEBG@Z`
- size: `249`
- prototype: `__int64 __fastcall(RcsChatAdapterImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180030bd0`
- `0x1800bbc88`
- `0x1800be6e4`
- `0x1800c04f0`
- `0x1800c3a30`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3b14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3b14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3a4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3b01`

## string_xrefs

- `0x1800c3a75`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c3ab9`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatAdapterImpl::SendDisplayedDeliveryReport(
        RcsChatAdapterImpl *this,
        const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  string = 0;
  v4 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v11);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *((_QWORD *)this + 3);
    v12 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v6 + 88LL))(v6, string, &v12);
    v5 = v7;
    if ( v7 >= 0 )
    {
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, ChatSendDisplayed, a2);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      v5 = 0;
    }
    else
    {
      Log_HREvent_102(
        (unsigned int)v7,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
        269);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    }
  }
  else
  {
    Log_HREvent_102(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
      266);
  }
  WindowsDeleteString(string);
  string = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v5;
}

```

## disassembly

```asm
0x1800c3a30  mov     [rsp+arg_18], rbx
0x1800c3a35  mov     [rsp+arg_8], rdx
0x1800c3a3a  push    rbp
0x1800c3a3b  push    rsi
0x1800c3a3c  push    rdi
0x1800c3a3d  sub     rsp, 30h
0x1800c3a41  mov     rbp, rcx
0x1800c3a44  mov     rdi, rdx
0x1800c3a47  add     rcx, 40h ; '@'; lpCriticalSection
0x1800c3a4b  call    cs:__imp_EnterCriticalSection
0x1800c3a51  lea     rdx, [rsp+48h+arg_8]
0x1800c3a56  mov     [rsp+48h+string], 0
0x1800c3a5f  lea     rcx, [rsp+48h+string]
0x1800c3a64  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c3a69  mov     ebx, eax
0x1800c3a6b  test    eax, eax
0x1800c3a6d  jns     short loc_1800C3A8A
0x1800c3a6f  mov     r9d, 10Ah
0x1800c3a75  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c3a7c  mov     edx, 1
0x1800c3a81  mov     ecx, eax
0x1800c3a83  call    Log_HREvent_102
0x1800c3a88  jmp     short loc_1800C3AFC
0x1800c3a8a  mov     rcx, [rbp+18h]
0x1800c3a8e  lea     r8, [rsp+48h+arg_10]
0x1800c3a93  mov     rdx, [rsp+48h+string]
0x1800c3a98  mov     [rsp+48h+arg_10], 0
0x1800c3aa1  mov     rax, [rcx]
0x1800c3aa4  mov     rax, [rax+58h]
0x1800c3aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3aad  mov     ebx, eax
0x1800c3aaf  test    eax, eax
0x1800c3ab1  jns     short loc_1800C3AD8
0x1800c3ab3  mov     r9d, 10Dh
0x1800c3ab9  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c3ac0  mov     edx, 1
0x1800c3ac5  mov     ecx, eax
0x1800c3ac7  call    Log_HREvent_102
0x1800c3acc  lea     rcx, [rsp+48h+arg_10]
0x1800c3ad1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c3ad6  jmp     short loc_1800C3AFC
0x1800c3ad8  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x1800c3adf  jz      short loc_1800C3AF0
0x1800c3ae1  mov     r8, rdi
0x1800c3ae4  lea     rdx, ChatSendDisplayed
0x1800c3aeb  call    McTemplateU0z_EventWriteTransfer
0x1800c3af0  lea     rcx, [rsp+48h+arg_10]
0x1800c3af5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c3afa  xor     ebx, ebx
0x1800c3afc  mov     rcx, [rsp+48h+string]; string
0x1800c3b01  call    cs:__imp_WindowsDeleteString
0x1800c3b07  lea     rcx, [rbp+40h]; lpCriticalSection
0x1800c3b0b  mov     [rsp+48h+string], 0
0x1800c3b14  call    cs:__imp_LeaveCriticalSection
0x1800c3b1a  mov     eax, ebx
0x1800c3b1c  mov     rbx, [rsp+48h+arg_18]
0x1800c3b21  add     rsp, 30h
0x1800c3b25  pop     rdi
0x1800c3b26  pop     rsi
0x1800c3b27  pop     rbp
0x1800c3b28  retn
```
