# Microsoft::CoreUI::CompletionHandlerCallback::ImportAdapter$(CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,void *,void *)>> *,System::UIntPtr,System::UIntPtr)

- ea: `0x180007b20`
- end: `0x180007cd7`
- name: `?ImportAdapter$@CompletionHandlerCallback@CoreUI@Microsoft@@SAXPEAV?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAX00@Z@CFlat@@@CFlat@@UUIntPtr@System@@1@Z`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b20`
- `0x180007ce0`
- `0x180007d28`
- `0x180007d80`
- `0x18008d574`
- `0x18008d5bc`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bf6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c67`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007b95`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007c79`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007b95`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007c79`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007b52`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007c5d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007b52`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007c5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::CoreUI::CompletionHandlerCallback::ImportAdapter$(__int64 a1, __int64 a2, __int64 a3)
{
  LPVOID Value; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  void *v8; // r14
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  _QWORD *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  void (__fastcall *v22)(__int64, __int64, __int64); // rax
  __int64 *v23; // [rsp+28h] [rbp-38h] BYREF
  __int64 *v24; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v25[5]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v26; // [rsp+90h] [rbp+30h] BYREF
  __int64 v27; // [rsp+98h] [rbp+38h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF

  v28 = a3;
  v27 = a2;
  v26 = a1;
  v23 = &v27;
  v24 = &v28;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v8 = CFlat::EntryExit::ValidateCall(Value, *(void **)(v26 + 24));
  v9 = (_QWORD *)*((_QWORD *)Value + 10);
  *((_QWORD *)Value + 10) = 0;
  if ( *((_BYTE *)Value + 78) )
LABEL_2:
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v5,
      v4,
      v6,
      v7);
  if ( *((_QWORD *)Value + 11) )
  {
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
      goto LABEL_2;
    v10 = *((_QWORD *)Value + 11);
    if ( (*(_DWORD *)(v10 + 60))-- == 1 )
    {
      *(_QWORD *)(v10 + 64) = 0;
      *(_DWORD *)(v10 + 72) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 16));
  }
  if ( v9 )
  {
    while ( 1 )
    {
      v12 = (_QWORD *)*v9;
      *v9 = 0;
      v13 = v9[3];
      v14 = *((unsigned __int8 *)v9 + 8);
      if ( !*((_BYTE *)v9 + 8) )
        break;
      v14 = (unsigned int)(v14 - 1);
      if ( !(_DWORD)v14 )
      {
        v22 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 16LL);
LABEL_22:
        v21 = v9[3];
        goto LABEL_20;
      }
      if ( (_DWORD)v14 == 1 )
      {
        v21 = v9[2];
        v22 = (void (__fastcall *)(__int64, __int64, __int64))v9[3];
LABEL_20:
        v22(v21, v14, v13);
      }
      free(v9);
      v9 = v12;
      if ( !v12 )
        goto LABEL_13;
    }
    v22 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 8LL);
    goto LABEL_22;
  }
LABEL_13:
  v29 = 0;
  v25[0] = &v29;
  v25[1] = &v26;
  v25[2] = &v23;
  v25[3] = &v24;
  CFlat::SehSafe::Execute__lambda_eb5352968f08d319e2f856e8548d7452___(Value, v25);
  v15 = *((_QWORD *)Value + 11);
  if ( v15 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 16));
    v16 = *(_DWORD *)(v15 + 60);
    *(_DWORD *)(v15 + 60) = v16 + 1;
    if ( !v16 )
    {
      *(_QWORD *)(v15 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v15 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v18,
        v17,
        v19,
        v20);
  }
  *((_QWORD *)Value + 2) = v8;
  if ( v29 < 0 )
  {
    Cn::Process::NotifyCallbackError(v29, v8);
    System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(v29);
  }
}

```

## disassembly

```asm
0x180007b20  mov     [rsp-28h+arg_10], r8
0x180007b25  mov     [rsp-28h+arg_8], rdx
0x180007b2a  mov     [rsp-28h+arg_0], rcx
0x180007b2f  push    rbp
0x180007b30  push    rbx
0x180007b31  push    rsi
0x180007b32  push    rdi
0x180007b33  push    r14
0x180007b35  mov     rbp, rsp
0x180007b38  sub     rsp, 60h
0x180007b3c  lea     rax, [rbp+arg_8]
0x180007b40  mov     [rbp+var_38], rax
0x180007b44  lea     rax, [rbp+arg_10]
0x180007b48  mov     [rbp+var_30], rax
0x180007b4c  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007b52  call    cs:__imp_TlsGetValue
0x180007b58  mov     rdi, rax
0x180007b5b  mov     rdx, [rbp+arg_0]
0x180007b5f  mov     rdx, [rdx+18h]; void *
0x180007b63  mov     rcx, rax; void *
0x180007b66  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0@Z; CFlat::EntryExit::ValidateCall(void *,void *)
0x180007b6b  mov     r14, rax
0x180007b6e  mov     rbx, [rdi+50h]
0x180007b72  mov     qword ptr [rdi+50h], 0
0x180007b7a  cmp     byte ptr [rdi+4Eh], 0
0x180007b7e  jz      short loc_180007B86
0x180007b80  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180007b86  cmp     qword ptr [rdi+58h], 0
0x180007b8b  jz      short loc_180007BC2
0x180007b8d  xor     edx, edx; lpTlsValue
0x180007b8f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007b95  call    cs:__imp_TlsSetValue
0x180007b9b  test    eax, eax
0x180007b9d  jz      short loc_180007B80
0x180007b9f  mov     rcx, [rdi+58h]
0x180007ba3  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x180007ba7  jnz     short loc_180007BB8
0x180007ba9  mov     qword ptr [rcx+40h], 0
0x180007bb1  mov     dword ptr [rcx+48h], 0
0x180007bb8  add     rcx, 10h; lpCriticalSection
0x180007bbc  call    cs:__imp_LeaveCriticalSection
0x180007bc2  test    rbx, rbx
0x180007bc5  jz      short loc_180007C04
0x180007bc7  mov     rsi, [rbx]
0x180007bca  mov     qword ptr [rbx], 0
0x180007bd1  mov     r8, [rbx+18h]
0x180007bd5  movzx   edx, byte ptr [rbx+8]
0x180007bd9  test    edx, edx
0x180007bdb  jz      loc_180007CB6
0x180007be1  sub     edx, 1
0x180007be4  jz      loc_180007CAA
0x180007bea  cmp     edx, 1
0x180007bed  jz      loc_180007C99
0x180007bf3  mov     rcx, rbx; Block
0x180007bf6  call    cs:__imp_free
0x180007bfc  mov     rbx, rsi
0x180007bff  test    rsi, rsi
0x180007c02  jnz     short loc_180007BC7
0x180007c04  mov     [rbp+arg_18], 0
0x180007c0b  lea     rax, [rbp+arg_18]
0x180007c0f  mov     [rbp+var_28], rax
0x180007c13  lea     rax, [rbp+arg_0]
0x180007c17  mov     [rbp+var_20], rax
0x180007c1b  lea     rax, [rbp+var_38]
0x180007c1f  mov     [rbp+var_18], rax
0x180007c23  lea     rax, [rbp+var_30]
0x180007c27  mov     [rbp+var_10], rax
0x180007c2b  lea     rdx, [rbp+var_28]
0x180007c2f  mov     rcx, rdi
0x180007c32  call    CFlat__SehSafe__Execute__lambda_eb5352968f08d319e2f856e8548d7452___
0x180007c37  mov     rbx, [rdi+58h]
0x180007c3b  test    rbx, rbx
0x180007c3e  jz      short loc_180007C83
0x180007c40  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007c44  call    cs:__imp_EnterCriticalSection
0x180007c4a  mov     ecx, [rbx+3Ch]
0x180007c4d  lea     eax, [rcx+1]
0x180007c50  mov     [rbx+3Ch], eax
0x180007c53  test    ecx, ecx
0x180007c55  jnz     short loc_180007C70
0x180007c57  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007c5d  call    cs:__imp_TlsGetValue
0x180007c63  mov     [rbx+40h], rax
0x180007c67  call    cs:__imp_GetCurrentThreadId
0x180007c6d  mov     [rbx+48h], eax
0x180007c70  mov     rdx, rdi; lpTlsValue
0x180007c73  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007c79  call    cs:__imp_TlsSetValue
0x180007c7f  test    eax, eax
0x180007c81  jz      short loc_180007CBF
0x180007c83  mov     [rdi+10h], r14
0x180007c87  mov     ecx, [rbp+arg_18]; int
0x180007c8a  test    ecx, ecx
0x180007c8c  js      short loc_180007CC5
0x180007c8e  add     rsp, 60h
0x180007c92  pop     r14
0x180007c94  pop     rdi
0x180007c95  pop     rsi
0x180007c96  pop     rbx
0x180007c97  pop     rbp
0x180007c98  retn
0x180007c99  mov     rcx, [rbx+10h]
0x180007c9d  mov     rax, r8
0x180007ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca5  jmp     loc_180007BF3
0x180007caa  mov     rax, [r8]
0x180007cad  mov     rax, [rax+10h]
0x180007cb1  mov     rcx, r8
0x180007cb4  jmp     short loc_180007CA0
0x180007cb6  mov     rax, [r8]
0x180007cb9  mov     rax, [rax+8]
0x180007cbd  jmp     short loc_180007CB1
0x180007cbf  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180007cc5  mov     rdx, r14; void *
0x180007cc8  call    ?NotifyCallbackError@Process@Cn@@SAXHPEAX@Z; Cn::Process::NotifyCallbackError(int,void *)
0x180007ccd  mov     ecx, [rbp+arg_18]; int
0x180007cd0  call    ?ThrowExceptionForHR@Marshal@InteropServices@Runtime@System@@SAXH@Z; System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int)
0x180007cd5  jmp     short loc_180007C8E
```
