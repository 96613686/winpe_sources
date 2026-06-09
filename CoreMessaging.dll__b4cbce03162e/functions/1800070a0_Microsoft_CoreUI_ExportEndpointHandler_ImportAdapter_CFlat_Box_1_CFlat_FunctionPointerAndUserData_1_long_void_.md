# Microsoft::CoreUI::ExportEndpointHandler::ImportAdapter$(CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,void const *,int)>> *,void *,int)

- ea: `0x1800070a0`
- end: `0x18000718f`
- name: `?ImportAdapter$@ExportEndpointHandler@CoreUI@Microsoft@@SAXPEAV?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXPEBXH@Z@CFlat@@@CFlat@@PEAXH@Z`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007054`
- `0x1800070a0`
- `0x180007ce0`
- `0x180007d80`
- `0x180009750`
- `0x18008d574`
- `0x18008d5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007147`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007159`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007159`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000713d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000713d`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::ExportEndpointHandler::ImportAdapter$(__int64 a1, __int64 a2, int a3)
{
  _QWORD *Value; // rdi
  void *v4; // rsi
  __int64 v5; // rbx
  int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD v11[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+70h] [rbp+28h] BYREF
  __int64 v13; // [rsp+78h] [rbp+30h] BYREF
  int v14; // [rsp+80h] [rbp+38h] BYREF
  int v15; // [rsp+88h] [rbp+40h] BYREF

  v14 = a3;
  v13 = a2;
  v12 = a1;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v4 = CFlat::EntryExit::ValidateCall(Value, *(void **)(v12 + 24));
  CFlat::EntryExit::OnBeginCallToNative(Value);
  v15 = 0;
  v11[0] = &v15;
  v11[1] = &v12;
  v11[2] = &v13;
  v11[3] = &v14;
  CFlat::SehSafe::Execute__lambda_280372abce11bf370a1caac9f83c624c___(Value, v11);
  v5 = Value[11];
  if ( v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    v6 = *(_DWORD *)(v5 + 60);
    *(_DWORD *)(v5 + 60) = v6 + 1;
    if ( !v6 )
    {
      *(_QWORD *)(v5 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v5 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v8,
        v7,
        v9,
        v10);
  }
  Value[2] = v4;
  if ( v15 < 0 )
  {
    Cn::Process::NotifyCallbackError(v15, v4);
    System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(v15);
  }
}

```

## disassembly

```asm
0x1800070a0  mov     [rsp-20h+arg_10], r8d
0x1800070a5  mov     [rsp-20h+arg_8], rdx
0x1800070aa  mov     [rsp-20h+arg_0], rcx
0x1800070af  push    rbp
0x1800070b0  push    rbx
0x1800070b1  push    rsi
0x1800070b2  push    rdi
0x1800070b3  mov     rbp, rsp
0x1800070b6  sub     rsp, 48h
0x1800070ba  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800070c0  call    cs:__imp_TlsGetValue
0x1800070c6  mov     rdx, [rbp+arg_0]
0x1800070ca  mov     rcx, rax; void *
0x1800070cd  mov     rdi, rax
0x1800070d0  mov     rdx, [rdx+18h]; void *
0x1800070d4  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0@Z; CFlat::EntryExit::ValidateCall(void *,void *)
0x1800070d9  mov     rcx, rdi; void *
0x1800070dc  mov     rsi, rax
0x1800070df  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x1800070e4  lea     rax, [rbp+arg_18]
0x1800070e8  mov     [rbp+arg_18], 0
0x1800070ef  mov     [rbp+var_28], rax
0x1800070f3  lea     rdx, [rbp+var_28]
0x1800070f7  lea     rax, [rbp+arg_0]
0x1800070fb  mov     rcx, rdi
0x1800070fe  mov     [rbp+var_20], rax
0x180007102  lea     rax, [rbp+arg_8]
0x180007106  mov     [rbp+var_18], rax
0x18000710a  lea     rax, [rbp+arg_10]
0x18000710e  mov     [rbp+var_10], rax
0x180007112  call    CFlat__SehSafe__Execute__lambda_280372abce11bf370a1caac9f83c624c___
0x180007117  mov     rbx, [rdi+58h]
0x18000711b  test    rbx, rbx
0x18000711e  jz      short loc_180007163
0x180007120  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007124  call    cs:__imp_EnterCriticalSection
0x18000712a  mov     ecx, [rbx+3Ch]
0x18000712d  lea     eax, [rcx+1]
0x180007130  mov     [rbx+3Ch], eax
0x180007133  test    ecx, ecx
0x180007135  jnz     short loc_180007150
0x180007137  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000713d  call    cs:__imp_TlsGetValue
0x180007143  mov     [rbx+40h], rax
0x180007147  call    cs:__imp_GetCurrentThreadId
0x18000714d  mov     [rbx+48h], eax
0x180007150  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007156  mov     rdx, rdi; lpTlsValue
0x180007159  call    cs:__imp_TlsSetValue
0x18000715f  test    eax, eax
0x180007161  jz      short loc_180007177
0x180007163  mov     [rdi+10h], rsi
0x180007167  mov     ecx, [rbp+arg_18]; int
0x18000716a  test    ecx, ecx
0x18000716c  js      short loc_18000717D
0x18000716e  add     rsp, 48h
0x180007172  pop     rdi
0x180007173  pop     rsi
0x180007174  pop     rbx
0x180007175  pop     rbp
0x180007176  retn
0x180007177  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18000717d  mov     rdx, rsi; void *
0x180007180  call    ?NotifyCallbackError@Process@Cn@@SAXHPEAX@Z; Cn::Process::NotifyCallbackError(int,void *)
0x180007185  mov     ecx, [rbp+arg_18]; int
0x180007188  call    ?ThrowExceptionForHR@Marshal@InteropServices@Runtime@System@@SAXH@Z; System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int)
0x18000718d  jmp     short loc_18000716E
```
