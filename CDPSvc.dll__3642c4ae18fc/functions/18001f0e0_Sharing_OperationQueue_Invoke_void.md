# Sharing::OperationQueue::Invoke(void)

- ea: `0x18001f0e0`
- end: `0x18001f1ef`
- name: `?Invoke@OperationQueue@Sharing@@AEAAXXZ`
- size: `271`
- prototype: `void __fastcall(Sharing::OperationQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180049010`

## callees

- `0x180004928`
- `0x18001b404`
- `0x18001f0e0`
- `0x18001f200`
- `0x18004b904`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f150`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f150`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f190`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Sharing::OperationQueue::Invoke(Sharing::OperationQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  char *v3; // rbp
  char *v4; // rsi
  int v5; // eax
  struct Sharing::IQueuedOperation *v6; // rcx
  DWORD CurrentThreadId; // eax
  struct Sharing::IQueuedOperation *v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  v3 = (char *)this + 40;
  v4 = (char *)this + 40;
  while ( 1 )
  {
    v8 = 0;
    EnterCriticalSection(v2);
    *((_BYTE *)this + 33) = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v8);
    v5 = Sharing::OperationQueue::PopNextOperation(this, &v8);
    if ( v5 >= 0 )
      goto LABEL_5;
    if ( v5 != -2147023728 )
      break;
    v4 = v3;
LABEL_5:
    v6 = v8;
    if ( v8 )
    {
      Microsoft::WRL::ComPtr<ICDPDevice>::operator=(v4, &v8);
      CurrentThreadId = GetCurrentThreadId();
      v6 = v8;
    }
    else
    {
      *((_BYTE *)this + 32) = 0;
      CurrentThreadId = 0;
      v4 = v3;
    }
    *((_DWORD *)this + 9) = CurrentThreadId;
    if ( v2 )
    {
      LeaveCriticalSection(v2);
      v6 = v8;
    }
    if ( !v6 )
      goto LABEL_16;
    (*(void (__fastcall **)(struct Sharing::IQueuedOperation *))(*(_QWORD *)v6 + 56LL))(v6);
    EnterCriticalSection(v2);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v4);
    if ( v2 )
      LeaveCriticalSection(v2);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v8);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v8);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
LABEL_16:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v8);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::Release(this);
}

```

## disassembly

```asm
0x18001f0e0  push    rbx
0x18001f0e2  push    rbp
0x18001f0e3  push    rsi
0x18001f0e4  push    rdi
0x18001f0e5  sub     rsp, 28h
0x18001f0e9  mov     rdi, rcx
0x18001f0ec  lea     rbx, [rcx+120h]
0x18001f0f3  lea     rbp, [rcx+28h]
0x18001f0f7  mov     rsi, rbp
0x18001f0fa  mov     [rsp+48h+arg_0], 0
0x18001f103  mov     rcx, rbx; lpCriticalSection
0x18001f106  call    cs:__imp_EnterCriticalSection
0x18001f10c  mov     byte ptr [rdi+21h], 0
0x18001f110  lea     rcx, [rsp+48h+arg_0]
0x18001f115  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f11a  lea     rdx, [rsp+48h+arg_0]; struct Sharing::IQueuedOperation **
0x18001f11f  mov     rcx, rdi; this
0x18001f122  call    ?PopNextOperation@OperationQueue@Sharing@@AEAAJPEAPEAUIQueuedOperation@2@@Z; Sharing::OperationQueue::PopNextOperation(Sharing::IQueuedOperation * *)
0x18001f127  test    eax, eax
0x18001f129  jns     short loc_18001F139
0x18001f12b  cmp     eax, 80070490h
0x18001f130  jnz     loc_18001F1C6
0x18001f136  mov     rsi, rbp
0x18001f139  mov     rcx, [rsp+48h+arg_0]
0x18001f13e  test    rcx, rcx
0x18001f141  jz      short loc_18001F15D
0x18001f143  lea     rdx, [rsp+48h+arg_0]
0x18001f148  mov     rcx, rsi
0x18001f14b  call    ??4?$ComPtr@VICDPDevice@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ICDPDevice>::operator=(Microsoft::WRL::ComPtr<ICDPDevice> const &)
0x18001f150  call    cs:__imp_GetCurrentThreadId
0x18001f156  mov     rcx, [rsp+48h+arg_0]
0x18001f15b  jmp     short loc_18001F166
0x18001f15d  mov     byte ptr [rdi+20h], 0
0x18001f161  xor     eax, eax
0x18001f163  mov     rsi, rbp
0x18001f166  mov     [rdi+24h], eax
0x18001f169  test    rbx, rbx
0x18001f16c  jz      short loc_18001F17C
0x18001f16e  mov     rcx, rbx; lpCriticalSection
0x18001f171  call    cs:__imp_LeaveCriticalSection
0x18001f177  mov     rcx, [rsp+48h+arg_0]
0x18001f17c  test    rcx, rcx
0x18001f17f  jz      short loc_18001F1D5
0x18001f181  mov     rax, [rcx]
0x18001f184  mov     rax, [rax+38h]
0x18001f188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f18d  mov     rcx, rbx; lpCriticalSection
0x18001f190  call    cs:__imp_EnterCriticalSection
0x18001f196  mov     rcx, rsi
0x18001f199  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f19e  test    rbx, rbx
0x18001f1a1  jz      short loc_18001F1AC
0x18001f1a3  mov     rcx, rbx; lpCriticalSection
0x18001f1a6  call    cs:__imp_LeaveCriticalSection
0x18001f1ac  lea     rcx, [rsp+48h+arg_0]
0x18001f1b1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f1b6  nop
0x18001f1b7  lea     rcx, [rsp+48h+arg_0]
0x18001f1bc  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f1c1  jmp     loc_18001F0FA
0x18001f1c6  test    rbx, rbx
0x18001f1c9  jz      short loc_18001F1D5
0x18001f1cb  mov     rcx, rbx; lpCriticalSection
0x18001f1ce  call    cs:__imp_LeaveCriticalSection
0x18001f1d4  nop
0x18001f1d5  lea     rcx, [rsp+48h+arg_0]
0x18001f1da  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f1df  mov     rcx, rdi
0x18001f1e2  add     rsp, 28h
0x18001f1e6  pop     rdi
0x18001f1e7  pop     rsi
0x18001f1e8  pop     rbp
0x18001f1e9  pop     rbx
0x18001f1ea  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::Release(void)
```
