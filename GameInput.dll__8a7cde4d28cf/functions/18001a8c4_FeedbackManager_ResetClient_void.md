# FeedbackManager::ResetClient(void)

- ea: `0x18001a8c4`
- end: `0x18001aa60`
- name: `?ResetClient@FeedbackManager@@QEAAXXZ`
- size: `412`
- prototype: `void __fastcall(FeedbackManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003b238`
- `0x18003ee94`

## callees

- `0x180001304`
- `0x180002164`
- `0x18001a274`
- `0x18001a8c4`

## import_xrefs

- `ntdll!NtAlertThread` at `0x18001a9d3`
- `ntdll!NtAlertThread` at `0x18001a9d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a963`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a963`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9c3`

## pseudocode

```c
void __fastcall FeedbackManager::ResetClient(FeedbackManager *this, __int64 a2, int a3, int a4)
{
  __int64 v5; // rax
  void *v6; // rdi
  NTSTATUS v7; // eax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  __int16 v12; // [rsp+48h] [rbp-8h]
  int v13; // [rsp+70h] [rbp+20h] BYREF
  const char *v14; // [rsp+78h] [rbp+28h] BYREF
  const char *v15; // [rsp+80h] [rbp+30h] BYREF

  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v5 = *(_QWORD *)this + 172LL;
    v13 = 328;
    v11 = v5;
    v12 = 32;
    v14 = "Removing client from feedback manager";
    v15 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperArray<1>>(
      qword_180069018,
      (unsigned int)byte_18005BB5B,
      a3,
      a4,
      (__int64)&v15,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&v11);
  }
  AcquireSRWLockExclusive(*(PSRWLOCK *)this);
  v6 = *(void **)(*(_QWORD *)this + 8LL);
  *(_QWORD *)(*(_QWORD *)this + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 32LL) = 0;
  *(_BYTE *)(*(_QWORD *)this + 40LL) = 0;
  _InterlockedOr8(
    (volatile signed __int8 *)(*(_QWORD *)this + 169LL),
    *(_QWORD *)(*(_QWORD *)this + 120LL) != 0 ? 7 : 1);
  ReleaseSRWLockExclusive(*(PSRWLOCK *)this);
  v7 = NtAlertThread(*((HANDLE *)this + 1));
  if ( v7 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
  {
    v10 = qword_180069018 & 8;
    if ( v10 == qword_180069018 )
    {
      v13 = v7;
      LODWORD(v14) = 364;
      v15 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_18005CEA5,
        v8,
        v9,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  if ( v6 )
    GipEquationManager::ReleaseReference(v6);
}

```

## disassembly

```asm
0x18001a8c4  mov     r11, rsp
0x18001a8c7  mov     [r11+20h], rbx
0x18001a8cb  push    rbp
0x18001a8cc  push    rdi
0x18001a8cd  push    r14
0x18001a8cf  mov     rbp, rsp
0x18001a8d2  sub     rsp, 50h
0x18001a8d6  mov     eax, cs:dword_180069000
0x18001a8dc  lea     r14, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18001a8e3  mov     rbx, rcx
0x18001a8e6  cmp     eax, 5
0x18001a8e9  jbe     short loc_18001A960
0x18001a8eb  mov     rcx, cs:qword_180069018
0x18001a8f2  mov     rax, cs:qword_180069010
0x18001a8f9  test    al, 8
0x18001a8fb  jz      short loc_18001A960
0x18001a8fd  mov     rax, rcx
0x18001a900  and     eax, 8
0x18001a903  cmp     rax, rcx
0x18001a906  jnz     short loc_18001A960
0x18001a908  mov     rax, [rbx]
0x18001a90b  lea     rdx, byte_18005BB5B
0x18001a912  add     rax, 0ACh
0x18001a918  mov     [rbp+arg_0], 148h
0x18001a91f  mov     [rbp+var_10], rax
0x18001a923  mov     eax, 20h ; ' '
0x18001a928  mov     [rbp+var_8], ax
0x18001a92c  lea     rax, aRemovingClient; "Removing client from feedback manager"
0x18001a933  mov     [rbp+arg_8], rax
0x18001a937  lea     rax, [rbp+var_10]
0x18001a93b  mov     [r11-30h], rax
0x18001a93f  lea     rax, [rbp+arg_8]
0x18001a943  mov     [r11-38h], rax
0x18001a947  lea     rax, [rbp+arg_0]
0x18001a94b  mov     [r11-40h], rax
0x18001a94f  lea     rax, [rbp+arg_10]
0x18001a953  mov     [r11-48h], rax
0x18001a957  mov     [rbp+arg_10], r14
0x18001a95b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperArray<1> const &)
0x18001a960  mov     rcx, [rbx]; SRWLock
0x18001a963  call    cs:__imp_AcquireSRWLockExclusive
0x18001a96a  nop     dword ptr [rax+rax+00h]
0x18001a96f  mov     rax, [rbx]
0x18001a972  mov     rdi, [rax+8]
0x18001a976  mov     qword ptr [rax+8], 0
0x18001a97e  mov     rax, [rbx]
0x18001a981  mov     qword ptr [rax+10h], 0
0x18001a989  mov     rax, [rbx]
0x18001a98c  mov     qword ptr [rax+18h], 0
0x18001a994  mov     rax, [rbx]
0x18001a997  mov     qword ptr [rax+20h], 0
0x18001a99f  mov     rax, [rbx]
0x18001a9a2  mov     byte ptr [rax+28h], 0
0x18001a9a6  mov     rdx, [rbx]
0x18001a9a9  mov     rax, [rdx+78h]
0x18001a9ad  nop
0x18001a9ae  neg     rax
0x18001a9b1  sbb     cl, cl
0x18001a9b3  and     cl, 6
0x18001a9b6  inc     cl
0x18001a9b8  lock or [rdx+0A9h], cl
0x18001a9bf  nop
0x18001a9c0  mov     rcx, [rbx]; SRWLock
0x18001a9c3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a9ca  nop     dword ptr [rax+rax+00h]
0x18001a9cf  mov     rcx, [rbx+8]; ThreadHandle
0x18001a9d3  call    cs:__imp_NtAlertThread
0x18001a9da  nop     dword ptr [rax+rax+00h]
0x18001a9df  test    eax, eax
0x18001a9e1  jns     short loc_18001AA41
0x18001a9e3  mov     ecx, cs:dword_180069000
0x18001a9e9  cmp     ecx, 2
0x18001a9ec  jbe     short loc_18001AA41
0x18001a9ee  mov     rdx, cs:qword_180069018
0x18001a9f5  mov     rcx, cs:qword_180069010
0x18001a9fc  test    cl, 8
0x18001a9ff  jz      short loc_18001AA41
0x18001aa01  mov     rcx, rdx
0x18001aa04  and     ecx, 8
0x18001aa07  cmp     rcx, rdx
0x18001aa0a  jnz     short loc_18001AA41
0x18001aa0c  mov     [rbp+arg_0], eax
0x18001aa0f  lea     rdx, byte_18005CEA5
0x18001aa16  lea     rax, [rbp+arg_0]
0x18001aa1a  mov     dword ptr [rbp+arg_8], 16Ch
0x18001aa21  mov     [rsp+50h+var_20], rax
0x18001aa26  lea     rax, [rbp+arg_8]
0x18001aa2a  mov     [rsp+50h+var_28], rax
0x18001aa2f  lea     rax, [rbp+arg_10]
0x18001aa33  mov     [rsp+50h+var_30], rax
0x18001aa38  mov     [rbp+arg_10], r14
0x18001aa3c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001aa41  test    rdi, rdi
0x18001aa44  jz      short loc_18001AA4E
0x18001aa46  mov     rcx, rdi; P
0x18001aa49  call    ?ReleaseReference@GipEquationManager@@QEAAXXZ; GipEquationManager::ReleaseReference(void)
0x18001aa4e  mov     rbx, [rsp+50h+arg_18]
0x18001aa56  add     rsp, 50h
0x18001aa5a  pop     r14
0x18001aa5c  pop     rdi
0x18001aa5d  pop     rbp
0x18001aa5e  retn
```
