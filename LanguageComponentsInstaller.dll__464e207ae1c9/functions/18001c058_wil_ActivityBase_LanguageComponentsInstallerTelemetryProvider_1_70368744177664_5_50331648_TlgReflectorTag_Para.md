# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001c058`
- end: `0x18001c19b`
- name: `?Stop@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `323`
- prototype: `void __fastcall(_QWORD *, DWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800140e0`
- `0x180014788`

## callees

- `0x18000196c`
- `0x180004118`
- `0x18000a0b0`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x18001c058`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c101`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v14; // [rsp+100h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v3 = a1[34];
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v14 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v7,
          (int)byte_18002F32B,
          a1[34] + 8,
          v9,
          (__int64)&v14,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18001c058  mov     rax, rsp
0x18001c05b  mov     [rax+20h], rbx
0x18001c05f  mov     [rax+10h], edx
0x18001c062  push    rdi
0x18001c063  sub     rsp, 0E0h
0x18001c06a  mov     rbx, rcx
0x18001c06d  lea     rdx, [rax+8]
0x18001c071  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c076  mov     rax, [rbx+110h]
0x18001c07d  mov     edi, [rax+0F8h]
0x18001c083  cmp     edi, 1
0x18001c086  jl      loc_18001C17E
0x18001c08c  cmp     dword ptr [rax+48h], 0
0x18001c090  jl      short loc_18001C099
0x18001c092  mov     dword ptr [rax+48h], 0
0x18001c099  dec     edi
0x18001c09b  mov     [rax+0F8h], edi
0x18001c0a1  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x18001c0a9  test    rcx, rcx
0x18001c0ac  jz      short loc_18001C0B4
0x18001c0ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c0b4  test    edi, edi
0x18001c0b6  jnz     short loc_18001C0CC
0x18001c0b8  mov     rax, [rbx]
0x18001c0bb  mov     rcx, rbx
0x18001c0be  mov     rax, [rax+8]
0x18001c0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0c7  jmp     loc_18001C166
0x18001c0cc  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001c0d1  mov     rdi, rax
0x18001c0d4  mov     ecx, [rax]
0x18001c0d6  cmp     ecx, 5
0x18001c0d9  jbe     loc_18001C166
0x18001c0df  mov     rax, [rax+18h]
0x18001c0e3  mov     rcx, [rdi+10h]
0x18001c0e7  mov     rdx, 400000000000h
0x18001c0f1  test    rdx, rcx
0x18001c0f4  jz      short loc_18001C166
0x18001c0f6  mov     rcx, rax
0x18001c0f9  and     rcx, rdx
0x18001c0fc  cmp     rcx, rax
0x18001c0ff  jnz     short loc_18001C166
0x18001c101  call    cs:__imp_GetCurrentThreadId
0x18001c107  mov     [rsp+0E8h+arg_8], eax
0x18001c10e  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x18001c119  mov     [rsp+0E8h+arg_10], 1000000h
0x18001c125  mov     r8, [rbx+110h]
0x18001c12c  add     r8, 8
0x18001c130  lea     rax, [rsp+0E8h+arg_8]
0x18001c138  mov     [rsp+0E8h+var_B8], rax
0x18001c13d  lea     rax, [rsp+0E8h+SRWLock]
0x18001c145  mov     [rsp+0E8h+var_C0], rax
0x18001c14a  lea     rax, [rsp+0E8h+arg_10]
0x18001c152  mov     [rsp+0E8h+var_C8], rax
0x18001c157  lea     rdx, byte_18002F32B
0x18001c15e  mov     rcx, rdi
0x18001c161  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c166  mov     rcx, rbx
0x18001c169  mov     rbx, [rsp+0E8h+arg_18]
0x18001c171  add     rsp, 0E0h
0x18001c178  pop     rdi
0x18001c179  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001c17e  xor     edx, edx; Val
0x18001c180  mov     r8d, 98h; Size
0x18001c186  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18001c18b  call    memset_0
0x18001c190  lea     rcx, [rsp+0E8h+var_A8]; this
0x18001c195  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
