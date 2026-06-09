# Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::PingAndWait(Microsoft::CoreUI::Messaging::Connection *,void *,uint)

- ea: `0x180089b10`
- end: `0x180089c75`
- name: `?PingAndWait@InterconnectMessageAdapter@Messaging@CoreUI@Microsoft@@UEAA?AW4MessagingResults@234@PEAVConnection@234@PEAXI@Z`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007d80`
- `0x18000ec10`
- `0x180026ae8`
- `0x180089b10`
- `0x180089c7c`
- `0x180089cb0`
- `0x18008ae1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180089c38`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180089c38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089b3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089b3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180089bfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180089bfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::PingAndWait(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4)
{
  HANDLE v8; // r10
  HANDLE EventW; // rax
  __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  _DWORD *v13; // rdi
  void *v14; // rdi
  System::Object *v15; // rbx
  HANDLE v16; // rax
  unsigned int v17; // edi
  DWORD v18; // edi
  const char16_t *v19; // rcx
  HANDLE Handles[9]; // [rsp+40h] [rbp-48h] BYREF
  HANDLE v22; // [rsp+90h] [rbp+8h] BYREF

  v8 = *(HANDLE *)(a1 + 40);
  if ( !v8 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v8 = EventW;
    if ( !EventW )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
    *(_QWORD *)(a1 + 40) = EventW;
  }
  v10 = a2[31];
  v22 = (HANDLE)v10;
  if ( v10 )
    ++*(_DWORD *)(v10 + 16);
  v11 = a2[28];
  v12 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 64LL);
  v13 = *(_DWORD **)(v10 + 48);
  Handles[0] = v13;
  if ( v13 )
    ++v13[4];
  Microsoft::CoreUI::Services::ThreadEndpointCaller::LocalPingAndWait(v13, v11, v12, v11 >> 46, a3, a4, v8);
  if ( v13 )
    System::Object::ReleaseNotFrozen$((System::Object *)v13);
  System::Object::ReleaseNotFrozen$((System::Object *)v10);
  v22 = (HANDLE)a2[33];
  CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Threading::InterconnectSender>,System::Object *>(
    Handles,
    &v22);
  v14 = *(void **)(a1 + 40);
  v15 = (System::Object *)Handles[0];
  v16 = OpenThread(0x100000u, 0, *(_DWORD *)(*((_QWORD *)Handles[0] + 4) + 140LL));
  v22 = v16;
  if ( v16 )
  {
    Handles[0] = v14;
    Handles[1] = v16;
    v18 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    Microsoft::CoreUI::Support::Win32Handle::SafeClose(&v22);
    if ( !v18 )
    {
      v17 = 0;
      goto LABEL_17;
    }
    if ( v18 != 1 )
      CFlat::Abandonment::Fail(v19);
  }
  v17 = 5;
LABEL_17:
  System::Object::ReleaseNotFrozen$(v15);
  return v17;
}

```

## disassembly

```asm
0x180089b10  push    rbx
0x180089b12  push    rbp
0x180089b13  push    rsi
0x180089b14  push    rdi
0x180089b15  push    r14
0x180089b17  push    r15
0x180089b19  sub     rsp, 58h
0x180089b1d  mov     r14d, r9d
0x180089b20  mov     r15, r8
0x180089b23  mov     rbp, rdx
0x180089b26  mov     rsi, rcx
0x180089b29  mov     r10, [rcx+28h]
0x180089b2d  test    r10, r10
0x180089b30  jnz     short loc_180089B54
0x180089b32  xor     r9d, r9d; lpName
0x180089b35  xor     r8d, r8d; bInitialState
0x180089b38  xor     edx, edx; bManualReset
0x180089b3a  xor     ecx, ecx; lpEventAttributes
0x180089b3c  call    cs:__imp_CreateEventW
0x180089b42  mov     r10, rax
0x180089b45  test    rax, rax
0x180089b48  jnz     short loc_180089B50
0x180089b4a  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180089b50  mov     [rsi+28h], rax
0x180089b54  mov     rbx, [rbp+0F8h]
0x180089b5b  mov     [rsp+88h+arg_0], rbx
0x180089b63  test    rbx, rbx
0x180089b66  jz      short loc_180089B6B
0x180089b68  inc     dword ptr [rbx+10h]
0x180089b6b  mov     rdx, [rbp+0E0h]
0x180089b72  mov     r9, rdx
0x180089b75  shr     r9, 2Eh
0x180089b79  mov     rax, [rbx+40h]
0x180089b7d  mov     r8, [rax+40h]
0x180089b81  mov     rdi, [rbx+30h]
0x180089b85  mov     [rsp+88h+Handles], rdi
0x180089b8a  test    rdi, rdi
0x180089b8d  jz      short loc_180089B92
0x180089b8f  inc     dword ptr [rdi+10h]
0x180089b92  mov     [rsp+88h+var_58], r10
0x180089b97  mov     [rsp+88h+var_60], r14d
0x180089b9c  mov     qword ptr [rsp+88h+bAlertable], r15
0x180089ba1  mov     rcx, rdi
0x180089ba4  call    ?LocalPingAndWait@ThreadEndpointCaller@Services@CoreUI@Microsoft@@SAXPEAVMessageSession@Messaging@34@UHENDPOINT@34@W4RegistrarClientId@Registrar@34@IUIntPtr@System@@IUWin32Handle@Support@34@@Z; Microsoft::CoreUI::Services::ThreadEndpointCaller::LocalPingAndWait(Microsoft::CoreUI::Messaging::MessageSession *,Microsoft::CoreUI::HENDPOINT,Microsoft::CoreUI::Registrar::RegistrarClientId,uint,System::IntPtr,uint,Microsoft::CoreUI::Support::Win32Handle)
0x180089ba9  nop
0x180089baa  test    rdi, rdi
0x180089bad  jz      short loc_180089BB8
0x180089baf  mov     rcx, rdi; this
0x180089bb2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180089bb7  nop
0x180089bb8  mov     rcx, rbx; this
0x180089bbb  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180089bc0  mov     rax, [rbp+108h]
0x180089bc7  mov     [rsp+88h+arg_0], rax
0x180089bcf  lea     rdx, [rsp+88h+arg_0]
0x180089bd7  lea     rcx, [rsp+88h+Handles]
0x180089bdc  call    ??$Checked@V?$SmartPtr@VInterconnectSender@Threading@CoreUI@Microsoft@@@CFlat@@PEAVObject@System@@@Cast@CFlat@@SA?A_P$$QEAPEAVObject@System@@@Z
0x180089be1  mov     rdi, [rsi+28h]
0x180089be5  mov     rbx, [rsp+88h+Handles]
0x180089bea  mov     r8, [rbx+20h]
0x180089bee  mov     r8d, [r8+8Ch]; dwThreadId
0x180089bf5  xor     edx, edx; bInheritHandle
0x180089bf7  mov     ecx, 100000h; dwDesiredAccess
0x180089bfc  call    cs:__imp_OpenThread
0x180089c02  mov     [rsp+88h+arg_0], rax
0x180089c0a  test    rax, rax
0x180089c0d  jnz     short loc_180089C16
0x180089c0f  mov     edi, 5
0x180089c14  jmp     short loc_180089C5E
0x180089c16  mov     [rsp+88h+Handles], rdi
0x180089c1b  mov     [rsp+88h+var_40], rax
0x180089c20  mov     [rsp+88h+bAlertable], 0; bAlertable
0x180089c28  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180089c2c  xor     r8d, r8d; bWaitAll
0x180089c2f  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180089c34  lea     ecx, [r8+2]; nCount
0x180089c38  call    cs:__imp_WaitForMultipleObjectsEx
0x180089c3e  mov     edi, eax
0x180089c40  lea     rcx, [rsp+88h+arg_0]
0x180089c48  call    ?SafeClose@Win32Handle@Support@CoreUI@Microsoft@@SAXU?$Ref@UWin32Handle@Support@CoreUI@Microsoft@@@CFlat@@@Z; Microsoft::CoreUI::Support::Win32Handle::SafeClose(CFlat::Ref<Microsoft::CoreUI::Support::Win32Handle>)
0x180089c4d  test    edi, edi
0x180089c4f  jz      short loc_180089C5C
0x180089c51  cmp     edi, 1
0x180089c54  jz      short loc_180089C0F
0x180089c56  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180089c5c  xor     edi, edi
0x180089c5e  mov     rcx, rbx; this
0x180089c61  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180089c66  mov     eax, edi
0x180089c68  add     rsp, 58h
0x180089c6c  pop     r15
0x180089c6e  pop     r14
0x180089c70  pop     rdi
0x180089c71  pop     rsi
0x180089c72  pop     rbp
0x180089c73  pop     rbx
0x180089c74  retn
```
