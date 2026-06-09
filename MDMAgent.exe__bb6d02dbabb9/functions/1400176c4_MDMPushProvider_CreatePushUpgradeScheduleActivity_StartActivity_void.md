# MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(void)

- ea: `0x1400176c4`
- end: `0x14001775a`
- name: `?StartActivity@CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400151d8`

## callees

- `0x14000162c`
- `0x1400167e0`
- `0x140017078`
- `0x1400176c4`
- `0x140018098`
- `0x1400181d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400176e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400176e5`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = MDMPushProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_1400204CB,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x1400176c4  mov     [rsp+arg_10], rbx
0x1400176c9  push    rdi
0x1400176ca  sub     rsp, 30h
0x1400176ce  mov     rbx, rcx
0x1400176d1  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1400176d6  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400176db  mov     rdi, rax
0x1400176de  mov     edx, [rax]
0x1400176e0  cmp     edx, 5
0x1400176e3  jbe     short loc_140017745
0x1400176e5  call    cs:__imp_GetCurrentThreadId
0x1400176ec  nop     dword ptr [rax+rax+00h]
0x1400176f1  mov     [rsp+38h+arg_0], eax
0x1400176f5  mov     [rsp+38h+arg_8], 0
0x1400176fe  mov     r8, [rbx+110h]
0x140017705  cmp     byte ptr [r8+4], 0
0x14001770a  jz      short loc_140017719
0x14001770c  lea     rcx, [r8+18h]; struct _GUID *
0x140017710  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140017715  test    al, al
0x140017717  jz      short loc_14001771B
0x140017719  xor     ecx, ecx
0x14001771b  add     r8, 8
0x14001771f  lea     rax, [rsp+38h+arg_0]
0x140017724  mov     [rsp+38h+var_10], rax
0x140017729  lea     rax, [rsp+38h+arg_8]
0x14001772e  mov     [rsp+38h+var_18], rax
0x140017733  mov     r9, rcx
0x140017736  lea     rdx, byte_1400204CB
0x14001773d  mov     rcx, rdi
0x140017740  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140017745  mov     rcx, rbx
0x140017748  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14001774d  nop
0x14001774e  mov     rbx, [rsp+38h+arg_10]
0x140017753  add     rsp, 30h
0x140017757  pop     rdi
0x140017758  retn
```
