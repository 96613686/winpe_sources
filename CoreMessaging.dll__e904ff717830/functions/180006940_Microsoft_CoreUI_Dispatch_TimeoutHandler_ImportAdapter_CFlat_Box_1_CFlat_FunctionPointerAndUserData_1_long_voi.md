# Microsoft::CoreUI::Dispatch::TimeoutHandler::ImportAdapter$(CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *)>> *)

- ea: `0x180006940`
- end: `0x180006a29`
- name: `?ImportAdapter$@TimeoutHandler@Dispatch@CoreUI@Microsoft@@SAXPEAV?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAX@Z@CFlat@@@CFlat@@@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006838`
- `0x180006940`
- `0x180007ce0`
- `0x180007d80`
- `0x180009750`
- `0x18008d574`
- `0x18008d5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800069ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800069ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000695a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000695a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069ce`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::TimeoutHandler::ImportAdapter$(__int64 a1)
{
  _QWORD *Value; // rdi
  void *v2; // rsi
  __int64 v3; // rbx
  int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  int v11; // [rsp+48h] [rbp+10h] BYREF

  v10 = a1;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v2 = CFlat::EntryExit::ValidateCall(Value, *(void **)(v10 + 24));
  CFlat::EntryExit::OnBeginCallToNative(Value);
  v11 = 0;
  v9[0] = &v11;
  v9[1] = &v10;
  CFlat::SehSafe::Execute__lambda_654db17c35df07198786f0867aa10de6___(Value, v9);
  v3 = Value[11];
  if ( v3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    v4 = *(_DWORD *)(v3 + 60);
    *(_DWORD *)(v3 + 60) = v4 + 1;
    if ( !v4 )
    {
      *(_QWORD *)(v3 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v3 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v6,
        v5,
        v7,
        v8);
  }
  Value[2] = v2;
  if ( v11 < 0 )
  {
    Cn::Process::NotifyCallbackError(v11, v2);
    System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(v11);
  }
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_10], rbx
0x180006945  mov     [rsp+arg_18], rsi
0x18000694a  mov     [rsp+arg_0], rcx
0x18000694f  push    rdi
0x180006950  sub     rsp, 30h
0x180006954  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000695a  call    cs:__imp_TlsGetValue
0x180006960  mov     rdx, [rsp+38h+arg_0]
0x180006965  mov     rcx, rax; void *
0x180006968  mov     rdi, rax
0x18000696b  mov     rdx, [rdx+18h]; void *
0x18000696f  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0@Z; CFlat::EntryExit::ValidateCall(void *,void *)
0x180006974  mov     rcx, rdi; void *
0x180006977  mov     rsi, rax
0x18000697a  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18000697f  lea     rax, [rsp+38h+arg_8]
0x180006984  mov     [rsp+38h+arg_8], 0
0x18000698c  mov     [rsp+38h+var_18], rax
0x180006991  lea     rdx, [rsp+38h+var_18]
0x180006996  lea     rax, [rsp+38h+arg_0]
0x18000699b  mov     rcx, rdi
0x18000699e  mov     [rsp+38h+var_10], rax
0x1800069a3  call    CFlat__SehSafe__Execute__lambda_654db17c35df07198786f0867aa10de6___
0x1800069a8  mov     rbx, [rdi+58h]
0x1800069ac  test    rbx, rbx
0x1800069af  jz      short loc_1800069F4
0x1800069b1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800069b5  call    cs:__imp_EnterCriticalSection
0x1800069bb  mov     ecx, [rbx+3Ch]
0x1800069be  lea     eax, [rcx+1]
0x1800069c1  mov     [rbx+3Ch], eax
0x1800069c4  test    ecx, ecx
0x1800069c6  jnz     short loc_1800069E1
0x1800069c8  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800069ce  call    cs:__imp_TlsGetValue
0x1800069d4  mov     [rbx+40h], rax
0x1800069d8  call    cs:__imp_GetCurrentThreadId
0x1800069de  mov     [rbx+48h], eax
0x1800069e1  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800069e7  mov     rdx, rdi; lpTlsValue
0x1800069ea  call    cs:__imp_TlsSetValue
0x1800069f0  test    eax, eax
0x1800069f2  jz      short loc_180006A10
0x1800069f4  mov     [rdi+10h], rsi
0x1800069f8  mov     ecx, [rsp+38h+arg_8]; int
0x1800069fc  test    ecx, ecx
0x1800069fe  js      short loc_180006A16
0x180006a00  mov     rbx, [rsp+38h+arg_10]
0x180006a05  mov     rsi, [rsp+38h+arg_18]
0x180006a0a  add     rsp, 30h
0x180006a0e  pop     rdi
0x180006a0f  retn
0x180006a10  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180006a16  mov     rdx, rsi; void *
0x180006a19  call    ?NotifyCallbackError@Process@Cn@@SAXHPEAX@Z; Cn::Process::NotifyCallbackError(int,void *)
0x180006a1e  mov     ecx, [rsp+38h+arg_8]; int
0x180006a22  call    ?ThrowExceptionForHR@Marshal@InteropServices@Runtime@System@@SAXH@Z; System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int)
0x180006a27  jmp     short loc_180006A00
```
