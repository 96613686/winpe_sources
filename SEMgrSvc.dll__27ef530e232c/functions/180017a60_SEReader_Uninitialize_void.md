# SEReader::Uninitialize(void)

- ea: `0x180017a60`
- end: `0x180017bdb`
- name: `?Uninitialize@SEReader@@AEAAXXZ`
- size: `379`
- prototype: `void __fastcall(SEReader *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001630c`
- `0x180016e48`

## callees

- `0x180001194`
- `0x180016afc`
- `0x1800176a4`
- `0x180017a60`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017bd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a7c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180017ad6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180017ad6`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180017afe`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180017afe`

## string_xrefs

- `0x180017a99`: `SEReader::Uninitialize starts`
- `0x180017b92`: `SEReader::Uninitialize ends`
- `0x180017a8d`: `SEReader::Uninitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SEReader::Uninitialize(SEReader *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  volatile signed __int32 *v8; // rdi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+60h] [rbp+8h] BYREF
  const char *v13; // [rsp+68h] [rbp+10h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v12 = "SEReader::Uninitialize starts";
    v13 = "SEReader::Uninitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)&byte_180119B7F,
      v4,
      v5,
      (__int64)&v13,
      (__int64)&v12);
  }
  if ( *((_QWORD *)this + 50) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 50) = 0;
  }
  v6 = *((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = 0;
  if ( v6 )
    CM_Unregister_Notification();
  SEReader::DeinitializeHardwareDependent((struct _RTL_CRITICAL_SECTION *)this);
  v7 = (_QWORD *)((char *)this + 96);
  *((_QWORD *)this + 14) = 0;
  if ( *((_QWORD *)this + 15) > 7u )
    v7 = (_QWORD *)*v7;
  *(_WORD *)v7 = 0;
  *((_QWORD *)this + 16) = 0;
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  SEReader::ReleaseService(this);
  *((_DWORD *)this + 19) = 0;
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v12 = "SEReader::Uninitialize ends";
    v13 = "SEReader::Uninitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v9,
      (unsigned int)byte_180119B23,
      v10,
      v11,
      (__int64)&v13,
      (__int64)&v12);
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180017a60  mov     [rsp+arg_10], rbx
0x180017a65  push    rsi
0x180017a66  push    rdi
0x180017a67  push    r15
0x180017a69  sub     rsp, 40h
0x180017a6d  mov     rbx, rcx
0x180017a70  lea     rsi, [rcx+20h]
0x180017a74  mov     [rsp+58h+var_28], rsi
0x180017a79  mov     rcx, rsi; lpCriticalSection
0x180017a7c  call    cs:__imp_EnterCriticalSection
0x180017a82  mov     [rsp+58h+var_20], 1
0x180017a87  mov     eax, cs:dword_18012F048
0x180017a8d  lea     r15, aSereaderUninit_1; "SEReader::Uninitialize"
0x180017a94  cmp     eax, 5
0x180017a97  jbe     short loc_180017ACA
0x180017a99  lea     rax, aSereaderUninit; "SEReader::Uninitialize starts"
0x180017aa0  mov     [rsp+58h+arg_0], rax
0x180017aa5  mov     [rsp+58h+arg_8], r15
0x180017aaa  lea     rax, [rsp+58h+arg_0]
0x180017aaf  mov     [rsp+58h+var_30], rax
0x180017ab4  lea     rax, [rsp+58h+arg_8]
0x180017ab9  mov     [rsp+58h+var_38], rax
0x180017abe  lea     rdx, byte_180119B7F
0x180017ac5  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017aca  mov     rcx, [rbx+190h]
0x180017ad1  test    rcx, rcx
0x180017ad4  jz      short loc_180017AE7
0x180017ad6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180017adc  mov     qword ptr [rbx+190h], 0
0x180017ae7  mov     rcx, [rbx+110h]
0x180017aee  mov     qword ptr [rbx+110h], 0
0x180017af9  test    rcx, rcx
0x180017afc  jz      short loc_180017B04
0x180017afe  call    cs:__imp_CM_Unregister_Notification
0x180017b04  mov     rcx, rbx; this
0x180017b07  call    ?DeinitializeHardwareDependent@SEReader@@AEAAJXZ; SEReader::DeinitializeHardwareDependent(void)
0x180017b0c  lea     rcx, [rbx+60h]
0x180017b10  mov     qword ptr [rcx+10h], 0
0x180017b18  cmp     qword ptr [rcx+18h], 7
0x180017b1d  jbe     short loc_180017B22
0x180017b1f  mov     rcx, [rcx]
0x180017b22  xor     eax, eax
0x180017b24  mov     [rcx], ax
0x180017b27  mov     [rbx+80h], rax
0x180017b2e  mov     rdi, [rbx+88h]
0x180017b35  mov     [rbx+88h], rax
0x180017b3c  test    rdi, rdi
0x180017b3f  jz      short loc_180017B78
0x180017b41  or      eax, 0FFFFFFFFh
0x180017b44  lock xadd [rdi+8], eax
0x180017b49  cmp     eax, 1
0x180017b4c  jnz     short loc_180017B78
0x180017b4e  mov     rax, [rdi]
0x180017b51  mov     rcx, rdi
0x180017b54  mov     rax, [rax]
0x180017b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5c  or      eax, 0FFFFFFFFh
0x180017b5f  lock xadd [rdi+0Ch], eax
0x180017b64  cmp     eax, 1
0x180017b67  jnz     short loc_180017B78
0x180017b69  mov     rax, [rdi]
0x180017b6c  mov     rcx, rdi
0x180017b6f  mov     rax, [rax+8]
0x180017b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b78  mov     rcx, rbx; this
0x180017b7b  call    ?ReleaseService@SEReader@@AEAAXXZ; SEReader::ReleaseService(void)
0x180017b80  mov     dword ptr [rbx+4Ch], 0
0x180017b87  mov     eax, cs:dword_18012F048
0x180017b8d  cmp     eax, 5
0x180017b90  jbe     short loc_180017BC4
0x180017b92  lea     rax, aSereaderUninit_0; "SEReader::Uninitialize ends"
0x180017b99  mov     [rsp+58h+arg_0], rax
0x180017b9e  mov     [rsp+58h+arg_8], r15
0x180017ba3  lea     rax, [rsp+58h+arg_0]
0x180017ba8  mov     [rsp+58h+var_30], rax
0x180017bad  lea     rax, [rsp+58h+arg_8]
0x180017bb2  mov     [rsp+58h+var_38], rax
0x180017bb7  lea     rdx, byte_180119B23
0x180017bbe  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017bc3  nop
0x180017bc4  mov     rcx, rsi
0x180017bc7  mov     rbx, [rsp+58h+arg_10]
0x180017bcc  add     rsp, 40h
0x180017bd0  pop     r15
0x180017bd2  pop     rdi
0x180017bd3  pop     rsi
0x180017bd4  jmp     cs:__imp_LeaveCriticalSection
```
