# Microsoft::CoreUI::ICallbackMessageConversationHost::Interface$::ImportDispatcher::OnItemMessage(System::Object *,uint,uint,void *,void *,uint)

- ea: `0x180007d90`
- end: `0x180007f80`
- name: `?OnItemMessage@ImportDispatcher@Interface$@ICallbackMessageConversationHost@CoreUI@Microsoft@@UEBAXPEAVObject@System@@IIPEAX1I@Z`
- size: `496`
- prototype: `void __fastcall(Microsoft::CoreUI::ICallbackMessageConversationHost::Interface$::ImportDispatcher *__hidden this, struct System::Object *, unsigned int, unsigned int, void *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180007d80`
- `0x180007d90`
- `0x180007f88`
- `0x1800080a8`
- `0x1800080f8`
- `0x18008d574`
- `0x18008d5bc`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ee3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007e1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007f18`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007e1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007f18`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007dcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007efc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007dcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007efc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::CoreUI::ICallbackMessageConversationHost::Interface$::ImportDispatcher::OnItemMessage(
        Microsoft::CoreUI::ICallbackMessageConversationHost::Interface$::ImportDispatcher *this,
        struct System::Object *a2,
        int a3,
        int a4,
        void *a5,
        void *a6,
        signed int a7)
{
  LPVOID Value; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  void *v13; // r14
  _QWORD *v14; // rbx
  __int64 v15; // rcx
  _QWORD *v17; // rsi
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rbx
  int v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  void (__fastcall *v27)(__int64, __int64, __int64); // rax
  signed int v28; // [rsp+20h] [rbp-50h] BYREF
  void *v29; // [rsp+28h] [rbp-48h] BYREF
  void *v30; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v31[7]; // [rsp+38h] [rbp-38h] BYREF
  int v32; // [rsp+A0h] [rbp+30h] BYREF
  int v33; // [rsp+A8h] [rbp+38h] BYREF

  v28 = a7;
  v30 = a6;
  v29 = a5;
  v33 = a4;
  v32 = a3;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  a5 = (void *)CFlat::ComImportAdapter::GetNativeInterface$<Microsoft::CoreUI::ICallbackMessageConversationHost,IMessageConversationHost>(a2);
  v13 = CFlat::EntryExit::ValidateCall(Value, a5, 3);
  v14 = (_QWORD *)*((_QWORD *)Value + 10);
  *((_QWORD *)Value + 10) = 0;
  if ( *((_BYTE *)Value + 78) )
LABEL_2:
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v10,
      v9,
      v11,
      v12);
  if ( *((_QWORD *)Value + 11) )
  {
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
      goto LABEL_2;
    v15 = *((_QWORD *)Value + 11);
    if ( (*(_DWORD *)(v15 + 60))-- == 1 )
    {
      *(_QWORD *)(v15 + 64) = 0;
      *(_DWORD *)(v15 + 72) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 16));
  }
  if ( v14 )
  {
    while ( 1 )
    {
      v17 = (_QWORD *)*v14;
      *v14 = 0;
      v18 = v14[3];
      v19 = *((unsigned __int8 *)v14 + 8);
      if ( !*((_BYTE *)v14 + 8) )
        break;
      v19 = (unsigned int)(v19 - 1);
      if ( !(_DWORD)v19 )
      {
        v27 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 16LL);
LABEL_22:
        v26 = v14[3];
        goto LABEL_20;
      }
      if ( (_DWORD)v19 == 1 )
      {
        v26 = v14[2];
        v27 = (void (__fastcall *)(__int64, __int64, __int64))v14[3];
LABEL_20:
        v27(v26, v19, v18);
      }
      free(v14);
      v14 = v17;
      if ( !v17 )
        goto LABEL_13;
    }
    v27 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 8LL);
    goto LABEL_22;
  }
LABEL_13:
  a7 = 0;
  v31[0] = &a7;
  v31[1] = &a5;
  v31[2] = &v32;
  v31[3] = &v33;
  v31[4] = &v29;
  v31[5] = &v30;
  v31[6] = &v28;
  CFlat::SehSafe::Execute__lambda_de6cc8128f8f9f99144226758963eeb9___(Value, v31);
  v20 = *((_QWORD *)Value + 11);
  if ( v20 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
    v21 = *(_DWORD *)(v20 + 60);
    *(_DWORD *)(v20 + 60) = v21 + 1;
    if ( !v21 )
    {
      *(_QWORD *)(v20 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v20 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v23,
        v22,
        v24,
        v25);
  }
  *((_QWORD *)Value + 2) = v13;
  if ( a7 < 0 )
  {
    Cn::Process::NotifyCallbackError(a7, v13);
    System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(a7);
  }
}

```

## disassembly

```asm
0x180007d90  mov     [rsp-18h+arg_0], rbx
0x180007d95  mov     [rsp-18h+arg_8], rsi
0x180007d9a  push    rbp
0x180007d9b  push    rdi
0x180007d9c  push    r14
0x180007d9e  mov     rbp, rsp
0x180007da1  sub     rsp, 70h
0x180007da5  mov     rbx, rdx
0x180007da8  mov     eax, [rbp+arg_30]
0x180007dab  mov     [rbp+var_50], eax
0x180007dae  mov     rax, [rbp+arg_28]
0x180007db2  mov     [rbp+var_40], rax
0x180007db6  mov     rax, [rbp+arg_20]
0x180007dba  mov     [rbp+var_48], rax
0x180007dbe  mov     [rbp+arg_18], r9d
0x180007dc2  mov     [rbp+arg_10], r8d
0x180007dc6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007dcc  call    cs:__imp_TlsGetValue
0x180007dd2  mov     rdi, rax
0x180007dd5  mov     rcx, rbx; struct CFlat::ComImportAdapter *
0x180007dd8  call    ??$GetNativeInterface$@VICallbackMessageConversationHost@CoreUI@Microsoft@@UIMessageConversationHost@@@ComImportAdapter@CFlat@@QEAAPEAUIMessageConversationHost@@XZ; CFlat::ComImportAdapter::GetNativeInterface$<Microsoft::CoreUI::ICallbackMessageConversationHost,IMessageConversationHost>(void)
0x180007ddd  mov     [rbp+arg_20], rax
0x180007de1  mov     r8d, 3; int
0x180007de7  mov     rdx, rax; void *
0x180007dea  mov     rcx, rdi; void *
0x180007ded  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x180007df2  mov     r14, rax
0x180007df5  mov     rbx, [rdi+50h]
0x180007df9  mov     qword ptr [rdi+50h], 0
0x180007e01  cmp     byte ptr [rdi+4Eh], 0
0x180007e05  jz      short loc_180007E0D
0x180007e07  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180007e0d  cmp     qword ptr [rdi+58h], 0
0x180007e12  jz      short loc_180007E49
0x180007e14  xor     edx, edx; lpTlsValue
0x180007e16  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007e1c  call    cs:__imp_TlsSetValue
0x180007e22  test    eax, eax
0x180007e24  jz      short loc_180007E07
0x180007e26  mov     rcx, [rdi+58h]
0x180007e2a  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x180007e2e  jnz     short loc_180007E3F
0x180007e30  mov     qword ptr [rcx+40h], 0
0x180007e38  mov     dword ptr [rcx+48h], 0
0x180007e3f  add     rcx, 10h; lpCriticalSection
0x180007e43  call    cs:__imp_LeaveCriticalSection
0x180007e49  test    rbx, rbx
0x180007e4c  jz      short loc_180007E8B
0x180007e4e  mov     rsi, [rbx]
0x180007e51  mov     qword ptr [rbx], 0
0x180007e58  mov     r8, [rbx+18h]
0x180007e5c  movzx   edx, byte ptr [rbx+8]
0x180007e60  test    edx, edx
0x180007e62  jz      loc_180007F5F
0x180007e68  sub     edx, 1
0x180007e6b  jz      loc_180007F53
0x180007e71  cmp     edx, 1
0x180007e74  jz      loc_180007F42
0x180007e7a  mov     rcx, rbx; Block
0x180007e7d  call    cs:__imp_free
0x180007e83  mov     rbx, rsi
0x180007e86  test    rsi, rsi
0x180007e89  jnz     short loc_180007E4E
0x180007e8b  mov     [rbp+arg_30], 0
0x180007e92  lea     rax, [rbp+arg_30]
0x180007e96  mov     [rbp+var_38], rax
0x180007e9a  lea     rax, [rbp+arg_20]
0x180007e9e  mov     [rbp+var_30], rax
0x180007ea2  lea     rax, [rbp+arg_10]
0x180007ea6  mov     [rbp+var_28], rax
0x180007eaa  lea     rax, [rbp+arg_18]
0x180007eae  mov     [rbp+var_20], rax
0x180007eb2  lea     rax, [rbp+var_48]
0x180007eb6  mov     [rbp+var_18], rax
0x180007eba  lea     rax, [rbp+var_40]
0x180007ebe  mov     [rbp+var_10], rax
0x180007ec2  lea     rax, [rbp+var_50]
0x180007ec6  mov     [rbp+var_8], rax
0x180007eca  lea     rdx, [rbp+var_38]
0x180007ece  mov     rcx, rdi
0x180007ed1  call    CFlat__SehSafe__Execute__lambda_de6cc8128f8f9f99144226758963eeb9___
0x180007ed6  mov     rbx, [rdi+58h]
0x180007eda  test    rbx, rbx
0x180007edd  jz      short loc_180007F22
0x180007edf  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007ee3  call    cs:__imp_EnterCriticalSection
0x180007ee9  mov     ecx, [rbx+3Ch]
0x180007eec  lea     eax, [rcx+1]
0x180007eef  mov     [rbx+3Ch], eax
0x180007ef2  test    ecx, ecx
0x180007ef4  jnz     short loc_180007F0F
0x180007ef6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007efc  call    cs:__imp_TlsGetValue
0x180007f02  mov     [rbx+40h], rax
0x180007f06  call    cs:__imp_GetCurrentThreadId
0x180007f0c  mov     [rbx+48h], eax
0x180007f0f  mov     rdx, rdi; lpTlsValue
0x180007f12  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007f18  call    cs:__imp_TlsSetValue
0x180007f1e  test    eax, eax
0x180007f20  jz      short loc_180007F68
0x180007f22  mov     [rdi+10h], r14
0x180007f26  mov     ecx, [rbp+arg_30]; int
0x180007f29  test    ecx, ecx
0x180007f2b  js      short loc_180007F6E
0x180007f2d  lea     r11, [rsp+70h+var_s0]
0x180007f32  mov     rbx, [r11+20h]
0x180007f36  mov     rsi, [r11+28h]
0x180007f3a  mov     rsp, r11
0x180007f3d  pop     r14
0x180007f3f  pop     rdi
0x180007f40  pop     rbp
0x180007f41  retn
0x180007f42  mov     rcx, [rbx+10h]
0x180007f46  mov     rax, r8
0x180007f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4e  jmp     loc_180007E7A
0x180007f53  mov     rax, [r8]
0x180007f56  mov     rax, [rax+10h]
0x180007f5a  mov     rcx, r8
0x180007f5d  jmp     short loc_180007F49
0x180007f5f  mov     rax, [r8]
0x180007f62  mov     rax, [rax+8]
0x180007f66  jmp     short loc_180007F5A
0x180007f68  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180007f6e  mov     rdx, r14; void *
0x180007f71  call    ?NotifyCallbackError@Process@Cn@@SAXHPEAX@Z; Cn::Process::NotifyCallbackError(int,void *)
0x180007f76  mov     ecx, [rbp+arg_30]; int
0x180007f79  call    ?ThrowExceptionForHR@Marshal@InteropServices@Runtime@System@@SAXH@Z; System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int)
0x180007f7e  jmp     short loc_180007F2D
```
