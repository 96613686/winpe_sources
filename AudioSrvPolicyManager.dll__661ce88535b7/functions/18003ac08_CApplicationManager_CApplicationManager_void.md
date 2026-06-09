# CApplicationManager::~CApplicationManager(void)

- ea: `0x18003ac08`
- end: `0x18003acf2`
- name: `??1CApplicationManager@@MEAA@XZ`
- size: `234`
- prototype: `void __fastcall(CApplicationManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ad30`

## callees

- `0x1800088d0`
- `0x18000cb50`
- `0x18000cd24`
- `0x18000f4e0`
- `0x18001b080`
- `0x18001b750`
- `0x180022a3c`
- `0x1800273a4`
- `0x180038798`
- `0x18003ac08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003acb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003acb8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003acd2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003acd2`

## pseudocode

```c
void __fastcall CApplicationManager::~CApplicationManager(CApplicationManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rcx
  struct CProcess **Next; // rax
  struct CProcess *v5; // rdi
  CApplication *v6; // rcx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &CApplicationManager::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v7 = *((_QWORD *)this + 16);
  while ( v7 )
  {
    Next = (struct CProcess **)ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(v3, &v7);
    v5 = *Next;
    if ( *Next )
    {
      v6 = (CApplication *)*((_QWORD *)v5 + 28);
      if ( v6 )
        CApplication::DelinkProcess(v6, *Next);
      CProcess::Cleanup(v5, 1);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(v5);
    }
  }
  v7 = *((_QWORD *)this + 9);
  while ( v7 )
  {
    v3 = *(_QWORD *)ATL::CAtlList<CHostedAppInteractivity *,ATL::CElementTraits<CHostedAppInteractivity *>>::GetNext(
                      v3,
                      &v7);
    if ( v3 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll((char *)this + 128);
  ATL::CAtlList<CApplication *,ATL::CElementTraits<CApplication *>>::RemoveAll((char *)this + 72);
  DeleteCriticalSection(v2);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18003ac08  push    rbx
0x18003ac0a  push    rsi
0x18003ac0b  push    rdi
0x18003ac0c  push    r14
0x18003ac0e  sub     rsp, 28h
0x18003ac12  mov     rsi, rcx
0x18003ac15  lea     rax, ??_7CApplicationManager@@6B@; const CApplicationManager::`vftable'
0x18003ac1c  mov     [rcx], rax
0x18003ac1f  lea     rbx, [rcx+20h]
0x18003ac23  mov     rcx, rbx; lpCriticalSection
0x18003ac26  call    cs:__imp_EnterCriticalSection
0x18003ac2c  lea     r14, [rsi+80h]
0x18003ac33  mov     rax, [r14]
0x18003ac36  mov     [rsp+48h+arg_0], rax
0x18003ac3b  test    rax, rax
0x18003ac3e  jz      short loc_18003AC83
0x18003ac40  lea     rdx, [rsp+48h+arg_0]
0x18003ac45  call    ?GetNext@?$CAtlList@PEAVCProcess@@V?$CElementTraits@PEAVCProcess@@@ATL@@@ATL@@QEAAAEAPEAVCProcess@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(__POSITION * &)
0x18003ac4a  mov     rdi, [rax]
0x18003ac4d  test    rdi, rdi
0x18003ac50  jz      short loc_18003AC7B
0x18003ac52  mov     rcx, [rdi+0E0h]; this
0x18003ac59  test    rcx, rcx
0x18003ac5c  jz      short loc_18003AC66
0x18003ac5e  mov     rdx, rdi; struct CProcess *
0x18003ac61  call    ?DelinkProcess@CApplication@@QEAAJPEAVCProcess@@@Z; CApplication::DelinkProcess(CProcess *)
0x18003ac66  mov     edx, 1; int
0x18003ac6b  mov     rcx, rdi; this
0x18003ac6e  call    ?Cleanup@CProcess@@QEAAJH@Z; CProcess::Cleanup(int)
0x18003ac73  mov     rcx, rdi
0x18003ac76  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioProcess@@UIAudioProcessInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(void)
0x18003ac7b  cmp     [rsp+48h+arg_0], 0
0x18003ac81  jnz     short loc_18003AC40
0x18003ac83  mov     rax, [rsi+48h]
0x18003ac87  mov     [rsp+48h+arg_0], rax
0x18003ac8c  test    rax, rax
0x18003ac8f  jz      short loc_18003ACB0
0x18003ac91  lea     rdx, [rsp+48h+arg_0]
0x18003ac96  call    ?GetNext@?$CAtlList@PEAVCHostedAppInteractivity@@V?$CElementTraits@PEAVCHostedAppInteractivity@@@ATL@@@ATL@@QEAAAEAPEAVCHostedAppInteractivity@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CHostedAppInteractivity *,ATL::CElementTraits<CHostedAppInteractivity *>>::GetNext(__POSITION * &)
0x18003ac9b  mov     rcx, [rax]
0x18003ac9e  test    rcx, rcx
0x18003aca1  jz      short loc_18003ACA8
0x18003aca3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18003aca8  cmp     [rsp+48h+arg_0], 0
0x18003acae  jnz     short loc_18003AC91
0x18003acb0  test    rbx, rbx
0x18003acb3  jz      short loc_18003ACBE
0x18003acb5  mov     rcx, rbx; lpCriticalSection
0x18003acb8  call    cs:__imp_LeaveCriticalSection
0x18003acbe  mov     rcx, r14
0x18003acc1  call    ?RemoveAll@?$CAtlList@PEAVCPickerHostContext@@V?$CElementTraits@PEAVCPickerHostContext@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll(void)
0x18003acc6  lea     rcx, [rsi+48h]
0x18003acca  call    ?RemoveAll@?$CAtlList@PEAVCApplication@@V?$CElementTraits@PEAVCApplication@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CApplication *,ATL::CElementTraits<CApplication *>>::RemoveAll(void)
0x18003accf  mov     rcx, rbx; lpCriticalSection
0x18003acd2  call    cs:__imp_DeleteCriticalSection
0x18003acd8  lea     rcx, [rsi+10h]
0x18003acdc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ace1  mov     dword ptr [rsi+0Ch], 0C0000001h
0x18003ace8  add     rsp, 28h
0x18003acec  pop     r14
0x18003acee  pop     rdi
0x18003acef  pop     rsi
0x18003acf0  pop     rbx
0x18003acf1  retn
```
