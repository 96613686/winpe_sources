# UnionFs::UfsPersistenceManager::StartPersistenceWorker(UnionFs::StackEventTracer &)

- ea: `0x140053d00`
- end: `0x140053f08`
- name: `?StartPersistenceWorker@UfsPersistenceManager@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z`
- size: `520`
- prototype: `__int64 __fastcall(PVOID StartContext, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fa18`
- `0x14005b418`

## callees

- `0x140001008`
- `0x140050594`
- `0x140053d00`
- `0x140056bd0`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140053dcf`
- `ntoskrnl!PsCreateSystemThread` at `0x140053dcf`
- `ntoskrnl!ZwClose` at `0x140053e8c`
- `ntoskrnl!ZwClose` at `0x140053edd`
- `ntoskrnl!ZwClose` at `0x140053e8c`
- `ntoskrnl!ZwClose` at `0x140053edd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140053eaf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140053eaf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053e29`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053e29`
- `ntoskrnl!ObfDereferenceObject` at `0x140053e50`
- `ntoskrnl!ObfDereferenceObject` at `0x140053e50`

## string_xrefs

- `0x140053de1`: `API: Starting persistence worker thread`
- `0x140053e60`: `API: Referencing thread object`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::StartPersistenceWorker(
        void **StartContext,
        struct UnionFs::StackEventTracer *a2,
        __int64 a3,
        int a4)
{
  int v4; // edi
  NTSTATUS v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  void *v9; // rcx
  const char *StartRoutine; // [rsp+28h] [rbp-48h]
  const char *v12; // [rsp+40h] [rbp-30h] BYREF
  const char *v13; // [rsp+48h] [rbp-28h] BYREF
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  void **v15; // [rsp+58h] [rbp-18h]
  PVOID Object; // [rsp+60h] [rbp-10h] BYREF
  char v17; // [rsp+68h] [rbp-8h]
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  void *ThreadHandle; // [rsp+A8h] [rbp+38h] BYREF

  v4 = (int)a2;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v18 = 676;
    v12 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    v13 = "UnionFs::UfsPersistenceManager::StartPersistenceWorker";
    v14 = "ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      0x8000,
      (unsigned int)byte_140097EEB,
      qword_14009E190,
      a4,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v18);
  }
  ThreadHandle = 0;
  v6 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         0,
         0,
         0,
         UnionFs::UfsPersistenceManager::PersistPayloadsWorker,
         StartContext);
  if ( v6 < 0 )
  {
    v7 = "API: Starting persistence worker thread";
    v8 = 0x2B9001702B5LL;
    goto LABEL_12;
  }
  v15 = StartContext + 14;
  Object = 0;
  v17 = 1;
  v6 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
  if ( v17 )
  {
    v9 = *v15;
    *v15 = Object;
    if ( v9 )
      ObfDereferenceObject(v9);
  }
  if ( v6 < 0 )
  {
    v7 = "API: Referencing thread object";
    v8 = 0x2BA001702C0LL;
    goto LABEL_12;
  }
  v6 = KeWaitForSingleObject(StartContext + 8, Executive, 0, 0, 0);
  if ( v6 < 0 )
  {
    v7 = "API: Waiting for worker to start";
    v8 = 0x2BB001702CALL;
LABEL_12:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v6,
      v4,
      (struct UnionFs::StackEventTracer *)v8,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::StartPersistenceWorker",
      v7,
      StartRoutine);
    if ( ThreadHandle )
      ZwClose(ThreadHandle);
    goto LABEL_19;
  }
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  v6 = 0;
LABEL_19:
  lambda_93a48e1e1df64eb08a002aa2c4b5f5d5_::operator()();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140053d00  mov     r11, rsp
0x140053d03  mov     [r11+8], rbx
0x140053d07  mov     [r11+10h], rsi
0x140053d0b  push    rbp
0x140053d0c  push    rdi
0x140053d0d  push    r15
0x140053d0f  mov     rbp, rsp
0x140053d12  sub     rsp, 70h
0x140053d16  mov     eax, cs:dword_14009E178
0x140053d1c  lea     r15, aUnionfsUfspers_1; "UnionFs::UfsPersistenceManager::StartPe"...
0x140053d23  mov     rdi, rdx
0x140053d26  mov     rsi, rcx
0x140053d29  cmp     eax, 5
0x140053d2c  jbe     short loc_140053D9E
0x140053d2e  mov     r8, cs:qword_14009E190
0x140053d35  mov     ecx, 8000h
0x140053d3a  mov     rax, cs:qword_14009E188
0x140053d41  test    rcx, rax
0x140053d44  jz      short loc_140053D9E
0x140053d46  mov     rax, r8
0x140053d49  and     rax, rcx
0x140053d4c  cmp     rax, r8
0x140053d4f  jnz     short loc_140053D9E
0x140053d51  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140053d58  mov     [rbp+arg_10], 2A4h
0x140053d5f  mov     [rbp+var_30], rax
0x140053d63  lea     rdx, byte_140097EEB
0x140053d6a  lea     rax, aEnter; "ENTER"
0x140053d71  mov     [rbp+var_28], r15
0x140053d75  mov     [rbp+var_20], rax
0x140053d79  lea     rax, [rbp+arg_10]
0x140053d7d  mov     [r11-50h], rax
0x140053d81  lea     rax, [rbp+var_30]
0x140053d85  mov     [r11-58h], rax
0x140053d89  lea     rax, [rbp+var_28]
0x140053d8d  mov     [r11-60h], rax
0x140053d91  lea     rax, [rbp+var_20]
0x140053d95  mov     [r11-68h], rax
0x140053d99  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140053d9e  lea     rax, ?PersistPayloadsWorker@UfsPersistenceManager@UnionFs@@KAXPEAX@Z; UnionFs::UfsPersistenceManager::PersistPayloadsWorker(void *)
0x140053da5  mov     [rsp+70h+StartContext], rsi; StartContext
0x140053daa  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x140053daf  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140053db3  xor     r9d, r9d; ProcessHandle
0x140053db6  mov     [rsp+70h+ClientId], 0; ClientId
0x140053dbf  xor     r8d, r8d; ObjectAttributes
0x140053dc2  mov     [rbp+ThreadHandle], 0
0x140053dca  mov     edx, 1FFFFFh; DesiredAccess
0x140053dcf  call    cs:__imp_PsCreateSystemThread
0x140053dd6  nop     dword ptr [rax+rax+00h]
0x140053ddb  mov     ebx, eax
0x140053ddd  test    eax, eax
0x140053ddf  jns     short loc_140053DF4
0x140053de1  lea     rax, aApiStartingPer; "API: Starting persistence worker thread"
0x140053de8  mov     r8, 2B9001702B5h
0x140053df2  jmp     short loc_140053E71
0x140053df4  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053df8  lea     rax, [rsi+70h]
0x140053dfc  mov     [rbp+var_18], rax
0x140053e00  xor     r9d, r9d; AccessMode
0x140053e03  lea     rax, [rbp+Object]
0x140053e07  mov     [rsp+70h+StartRoutine], 0; char *
0x140053e10  xor     r8d, r8d; ObjectType
0x140053e13  mov     [rsp+70h+ClientId], rax; Object
0x140053e18  mov     edx, 1FFFFFh; DesiredAccess
0x140053e1d  mov     [rbp+Object], 0
0x140053e25  mov     [rbp+var_8], 1
0x140053e29  call    cs:__imp_ObReferenceObjectByHandle
0x140053e30  nop     dword ptr [rax+rax+00h]
0x140053e35  cmp     [rbp+var_8], 0
0x140053e39  mov     ebx, eax
0x140053e3b  jz      short loc_140053E5C
0x140053e3d  mov     r8, [rbp+var_18]
0x140053e41  mov     rdx, [rbp+Object]
0x140053e45  mov     rcx, [r8]; Object
0x140053e48  mov     [r8], rdx
0x140053e4b  test    rcx, rcx
0x140053e4e  jz      short loc_140053E5C
0x140053e50  call    cs:__imp_ObfDereferenceObject
0x140053e57  nop     dword ptr [rax+rax+00h]
0x140053e5c  test    ebx, ebx
0x140053e5e  jns     short loc_140053E9A
0x140053e60  lea     rax, aApiReferencing_0; "API: Referencing thread object"
0x140053e67  mov     r8, 2BA001702C0h; struct UnionFs::StackEventTracer *
0x140053e71  mov     r9, r15; unsigned __int64
0x140053e74  mov     [rsp+70h+ClientId], rax; char *
0x140053e79  mov     rdx, rdi; int
0x140053e7c  mov     ecx, ebx; this
0x140053e7e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140053e83  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053e87  test    rcx, rcx
0x140053e8a  jz      short loc_140053EEB
0x140053e8c  call    cs:__imp_ZwClose
0x140053e93  nop     dword ptr [rax+rax+00h]
0x140053e98  jmp     short loc_140053EEB
0x140053e9a  lea     rcx, [rsi+40h]; Object
0x140053e9e  mov     [rsp+70h+ClientId], 0; Timeout
0x140053ea7  xor     r9d, r9d; Alertable
0x140053eaa  xor     r8d, r8d; WaitMode
0x140053ead  xor     edx, edx; WaitReason
0x140053eaf  call    cs:__imp_KeWaitForSingleObject
0x140053eb6  nop     dword ptr [rax+rax+00h]
0x140053ebb  mov     ebx, eax
0x140053ebd  test    eax, eax
0x140053ebf  jns     short loc_140053ED4
0x140053ec1  lea     rax, aApiWaitingForW; "API: Waiting for worker to start"
0x140053ec8  mov     r8, 2BB001702CAh
0x140053ed2  jmp     short loc_140053E71
0x140053ed4  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053ed8  test    rcx, rcx
0x140053edb  jz      short loc_140053EE9
0x140053edd  call    cs:__imp_ZwClose
0x140053ee4  nop     dword ptr [rax+rax+00h]
0x140053ee9  xor     ebx, ebx
0x140053eeb  call    _lambda_93a48e1e1df64eb08a002aa2c4b5f5d5___operator__
0x140053ef0  lea     r11, [rsp+70h+var_s0]
0x140053ef5  mov     eax, ebx
0x140053ef7  mov     rbx, [r11+20h]
0x140053efb  mov     rsi, [r11+28h]
0x140053eff  mov     rsp, r11
0x140053f02  pop     r15
0x140053f04  pop     rdi
0x140053f05  pop     rbp
0x140053f06  retn
```
