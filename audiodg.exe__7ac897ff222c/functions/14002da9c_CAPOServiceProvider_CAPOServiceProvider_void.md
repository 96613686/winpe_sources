# CAPOServiceProvider::~CAPOServiceProvider(void)

- ea: `0x14002da9c`
- end: `0x14002db55`
- name: `??1CAPOServiceProvider@@UEAA@XZ`
- size: `185`
- prototype: `void(CAPOServiceProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002da60`

## callees

- `0x140008124`
- `0x14000f3f8`
- `0x14002da9c`
- `0x14002db5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002db46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002db46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002dadc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002dadc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002dafb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002dafb`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14002db34`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14002db34`

## string_xrefs

- `0x14002db20`: `avcore\audiocore\server\audiodg\exe\aposerviceprovider.cpp`

## pseudocode

```c
void __fastcall CAPOServiceProvider::~CAPOServiceProvider(CAPOServiceProvider *this)
{
  bool v1; // zf
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  CRTThreadManager *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *((_DWORD *)this + 24) == 0;
  *(_QWORD *)this = &CAPOServiceProvider::`vftable';
  *((_QWORD *)this + 1) = &CAPOServiceProvider::`vftable'{for `IAudioProcessingObjectLoggingService'};
  *((_QWORD *)this + 2) = &CAPOServiceProvider::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioProcessingObjectRTQueueService>'};
  if ( v1 )
    goto LABEL_2;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = (CRTThreadManager *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    v5 = CRTThreadManager::UnlockMmcssWorkQueue(v4, *((_DWORD *)this + 24));
    if ( v5 >= 0 )
      goto LABEL_8;
    v6 = 151;
    goto LABEL_6;
  }
  v5 = RtwqUnlockWorkQueue(*((_DWORD *)this + 24));
  if ( v5 < 0 )
  {
    v6 = 155;
LABEL_6:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\aposerviceprovider.cpp",
      (const char *)(unsigned int)v5,
      v7);
  }
LABEL_8:
  if ( v3 )
    LeaveCriticalSection(v3);
LABEL_2:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 7) = -1073741823;
}

```

## disassembly

```asm
0x14002da9c  mov     [rsp+arg_0], rbx
0x14002daa1  push    rdi; int
0x14002daa2  sub     rsp, 20h
0x14002daa6  cmp     dword ptr [rcx+60h], 0
0x14002daaa  lea     rax, ??_7CAPOServiceProvider@@6B@; const CAPOServiceProvider::`vftable'
0x14002dab1  mov     [rcx], rax
0x14002dab4  mov     rbx, rcx
0x14002dab7  lea     rax, ??_7CAPOServiceProvider@@6BIAudioProcessingObjectLoggingService@@@; const CAPOServiceProvider::`vftable'{for `IAudioProcessingObjectLoggingService'}
0x14002dabe  mov     [rcx+8], rax
0x14002dac2  lea     rax, ??_7CAPOServiceProvider@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAudioProcessingObjectRTQueueService@@@Details@WRL@Microsoft@@@; const CAPOServiceProvider::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAudioProcessingObjectRTQueueService>'}
0x14002dac9  mov     [rcx+10h], rax
0x14002dacd  jnz     short loc_14002DAF4
0x14002dacf  lea     rcx, [rbx+58h]
0x14002dad3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14002dad8  lea     rcx, [rbx+30h]; lpCriticalSection
0x14002dadc  call    cs:__imp_DeleteCriticalSection
0x14002dae2  mov     dword ptr [rbx+1Ch], 0C0000001h
0x14002dae9  mov     rbx, [rsp+28h+arg_0]
0x14002daee  add     rsp, 20h
0x14002daf2  pop     rdi
0x14002daf3  retn
0x14002daf4  lea     rdi, [rcx+30h]
0x14002daf8  mov     rcx, rdi; lpCriticalSection
0x14002dafb  call    cs:__imp_EnterCriticalSection
0x14002db01  mov     rcx, [rbx+58h]; this
0x14002db05  test    rcx, rcx
0x14002db08  jz      short loc_14002DB31
0x14002db0a  mov     edx, [rbx+60h]; unsigned int
0x14002db0d  call    ?UnlockMmcssWorkQueue@CRTThreadManager@@QEAAJK@Z; CRTThreadManager::UnlockMmcssWorkQueue(ulong)
0x14002db12  test    eax, eax
0x14002db14  jns     short loc_14002DB3E
0x14002db16  mov     edx, 97h; void *
0x14002db1b  mov     rcx, [rsp+28h]; this
0x14002db20  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14002db27  mov     r9d, eax; char *
0x14002db2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002db2f  jmp     short loc_14002DB3E
0x14002db31  mov     ecx, [rbx+60h]; workQueueId
0x14002db34  call    cs:__imp_RtwqUnlockWorkQueue
0x14002db3a  test    eax, eax
0x14002db3c  js      short loc_14002DB4E
0x14002db3e  test    rdi, rdi
0x14002db41  jz      short loc_14002DACF
0x14002db43  mov     rcx, rdi; lpCriticalSection
0x14002db46  call    cs:__imp_LeaveCriticalSection
0x14002db4c  jmp     short loc_14002DACF
0x14002db4e  mov     edx, 9Bh
0x14002db53  jmp     short loc_14002DB1B
```
