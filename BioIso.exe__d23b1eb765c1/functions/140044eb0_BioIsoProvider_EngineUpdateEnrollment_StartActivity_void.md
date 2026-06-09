# BioIsoProvider::EngineUpdateEnrollment::StartActivity(void)

- ea: `0x140044eb0`
- end: `0x140044f50`
- name: `?StartActivity@EngineUpdateEnrollment@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::EngineUpdateEnrollment *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140015200`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140044eb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140044ed2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140044ed2`

## pseudocode

```c
void __fastcall BioIsoProvider::EngineUpdateEnrollment::StartActivity(BioIsoProvider::EngineUpdateEnrollment *this)
{
  _DWORD *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
  if ( *v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)byte_1400975B9,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140044eb0  mov     [rsp+arg_10], rbx
0x140044eb5  push    rdi
0x140044eb6  sub     rsp, 30h
0x140044eba  mov     rbx, rcx
0x140044ebd  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140044ec2  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140044ec7  mov     rdi, [rax+8]
0x140044ecb  mov     eax, [rdi]
0x140044ecd  cmp     eax, 5
0x140044ed0  jbe     short loc_140044F3B
0x140044ed2  call    cs:__imp_GetCurrentThreadId
0x140044ed9  nop     dword ptr [rax+rax+00h]
0x140044ede  mov     [rsp+38h+arg_0], eax
0x140044ee2  xor     eax, eax
0x140044ee4  mov     [rsp+38h+arg_8], rax
0x140044ee9  mov     r8, [rbx+110h]
0x140044ef0  cmp     [r8+4], al
0x140044ef4  jz      short loc_140044F11
0x140044ef6  lea     r9, [r8+18h]
0x140044efa  cmp     [r9], eax
0x140044efd  jnz     short loc_140044F14
0x140044eff  cmp     [r9+4], eax
0x140044f03  jnz     short loc_140044F14
0x140044f05  cmp     [r9+8], eax
0x140044f09  jnz     short loc_140044F14
0x140044f0b  cmp     [r9+0Ch], eax
0x140044f0f  jnz     short loc_140044F14
0x140044f11  mov     r9, rax
0x140044f14  add     r8, 8
0x140044f18  lea     rax, [rsp+38h+arg_0]
0x140044f1d  mov     [rsp+38h+var_10], rax
0x140044f22  lea     rax, [rsp+38h+arg_8]
0x140044f27  mov     [rsp+38h+var_18], rax
0x140044f2c  lea     rdx, byte_1400975B9
0x140044f33  mov     rcx, rdi
0x140044f36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140044f3b  mov     rcx, rbx
0x140044f3e  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140044f43  nop
0x140044f44  mov     rbx, [rsp+38h+arg_10]
0x140044f49  add     rsp, 30h
0x140044f4d  pop     rdi
0x140044f4e  retn
```
