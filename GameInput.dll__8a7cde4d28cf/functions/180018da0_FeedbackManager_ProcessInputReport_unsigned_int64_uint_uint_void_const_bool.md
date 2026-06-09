# FeedbackManager::ProcessInputReport(unsigned __int64,uint,uint,void const *,bool &)

- ea: `0x180018da0`
- end: `0x180018f2d`
- name: `?ProcessInputReport@FeedbackManager@@QEAAX_KIIPEBXAEA_N@Z`
- size: `397`
- prototype: `void __fastcall(FeedbackManager *__hidden this, unsigned __int64, unsigned int, unsigned int, const void *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003d990`

## callees

- `0x180001304`
- `0x180018da0`
- `0x18001a274`
- `0x18004d010`

## import_xrefs

- `ntdll!NtAlertThread` at `0x180018ea0`
- `ntdll!NtAlertThread` at `0x180018ea0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018de4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018de4`

## pseudocode

```c
void __fastcall FeedbackManager::ProcessInputReport(
        FeedbackManager *this,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        const void *a5,
        bool *a6)
{
  PSRWLOCK v6; // rbx
  void *v11; // rdi
  __int64 v12; // rax
  PVOID Ptr; // rcx
  NTSTATUS v14; // r8d
  int v15; // r9d
  NTSTATUS v16; // [rsp+50h] [rbp-48h] BYREF
  int v17; // [rsp+54h] [rbp-44h] BYREF
  const char *v18; // [rsp+58h] [rbp-40h] BYREF
  char v19; // [rsp+A0h] [rbp+8h] BYREF

  v6 = *(PSRWLOCK *)this;
  if ( *(_QWORD *)(*(_QWORD *)this + 112LL) )
  {
    v11 = 0;
    if ( !BYTE3(v6[21].Ptr) )
      goto LABEL_5;
    AcquireSRWLockExclusive(*(PSRWLOCK *)this);
    ReleaseSRWLockExclusive(v6);
    v6 = *(PSRWLOCK *)this;
    v12 = *(_QWORD *)(*(_QWORD *)this + 8LL);
    if ( !v12
      || (_InterlockedIncrement8((volatile signed __int8 *)(v12 + 4504)),
          v6 = *(PSRWLOCK *)this,
          v11 = *(void **)(*(_QWORD *)this + 8LL),
          (Ptr = v11) == 0) )
    {
LABEL_5:
      Ptr = v6[14].Ptr;
    }
    v19 = 0;
    (*(void (__fastcall **)(PVOID, __int64, _QWORD, _QWORD, const void *, _DWORD, PVOID, bool *, char *))(*(_QWORD *)Ptr + 16LL))(
      Ptr,
      a2,
      a3,
      a4,
      a5,
      v6[6].Ptr,
      v6[18].Ptr,
      a6,
      &v19);
    if ( v11 )
      GipEquationManager::ReleaseReference(v11);
    if ( v19 )
    {
      if ( !*(_BYTE *)(*(_QWORD *)this + 169LL) )
      {
        v14 = NtAlertThread(*((HANDLE *)this + 1));
        if ( v14 < 0
          && (unsigned int)dword_180069000 > 2
          && (qword_180069010 & 8) != 0
          && (qword_180069018 & 8) == qword_180069018 )
        {
          v16 = v14;
          v18 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
          v17 = 318;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&byte_18005D667,
            v14,
            v15,
            (__int64)&v18,
            (__int64)&v17,
            (__int64)&v16);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180018da0  push    rbx
0x180018da2  push    rbp
0x180018da3  push    rsi
0x180018da4  push    rdi
0x180018da5  push    r14
0x180018da7  push    r15
0x180018da9  sub     rsp, 68h
0x180018dad  mov     rbx, [rcx]
0x180018db0  mov     ebp, r9d
0x180018db3  mov     r14d, r8d
0x180018db6  mov     r15, rdx
0x180018db9  mov     rsi, rcx
0x180018dbc  cmp     qword ptr [rbx+70h], 0
0x180018dc1  jz      loc_180018F1F
0x180018dc7  xor     edi, edi
0x180018dc9  cmp     [rbx+0ABh], dil
0x180018dd0  jz      short loc_180018E14
0x180018dd2  mov     rcx, rbx; SRWLock
0x180018dd5  call    cs:__imp_AcquireSRWLockExclusive
0x180018ddc  nop     dword ptr [rax+rax+00h]
0x180018de1  mov     rcx, rbx; SRWLock
0x180018de4  call    cs:__imp_ReleaseSRWLockExclusive
0x180018deb  nop     dword ptr [rax+rax+00h]
0x180018df0  mov     rbx, [rsi]
0x180018df3  mov     rax, [rbx+8]
0x180018df7  test    rax, rax
0x180018dfa  jz      short loc_180018E14
0x180018dfc  nop
0x180018dfd  lock inc byte ptr [rax+1198h]
0x180018e04  nop
0x180018e05  mov     rbx, [rsi]
0x180018e08  mov     rdi, [rbx+8]
0x180018e0c  mov     rcx, rdi
0x180018e0f  test    rdi, rdi
0x180018e12  jnz     short loc_180018E18
0x180018e14  mov     rcx, [rbx+70h]
0x180018e18  mov     [rsp+98h+arg_0], 0
0x180018e20  lea     rdx, [rsp+98h+arg_0]
0x180018e28  mov     rax, [rcx]
0x180018e2b  mov     r9d, ebp
0x180018e2e  mov     [rsp+98h+var_58], rdx
0x180018e33  mov     r8d, r14d
0x180018e36  mov     rdx, [rsp+98h+arg_28]
0x180018e3e  mov     [rsp+98h+var_60], rdx
0x180018e43  mov     rdx, [rbx+90h]
0x180018e4a  mov     rax, [rax+10h]
0x180018e4e  mov     [rsp+98h+var_68], rdx
0x180018e53  mov     edx, [rbx+30h]
0x180018e56  mov     dword ptr [rsp+98h+var_70], edx
0x180018e5a  mov     rdx, [rsp+98h+arg_20]
0x180018e62  mov     [rsp+98h+var_78], rdx
0x180018e67  mov     rdx, r15
0x180018e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e6f  test    rdi, rdi
0x180018e72  jz      short loc_180018E7C
0x180018e74  mov     rcx, rdi; P
0x180018e77  call    ?ReleaseReference@GipEquationManager@@QEAAXXZ; GipEquationManager::ReleaseReference(void)
0x180018e7c  cmp     [rsp+98h+arg_0], 0
0x180018e84  jz      loc_180018F1F
0x180018e8a  mov     rax, [rsi]
0x180018e8d  mov     cl, [rax+0A9h]
0x180018e93  nop
0x180018e94  test    cl, cl
0x180018e96  jnz     loc_180018F1F
0x180018e9c  mov     rcx, [rsi+8]; ThreadHandle
0x180018ea0  call    cs:__imp_NtAlertThread
0x180018ea7  nop     dword ptr [rax+rax+00h]
0x180018eac  mov     r8d, eax
0x180018eaf  test    eax, eax
0x180018eb1  jns     short loc_180018F1F
0x180018eb3  mov     ecx, cs:dword_180069000
0x180018eb9  cmp     ecx, 2
0x180018ebc  jbe     short loc_180018F1F
0x180018ebe  mov     rdx, cs:qword_180069018
0x180018ec5  mov     rcx, cs:qword_180069010
0x180018ecc  test    cl, 8
0x180018ecf  jz      short loc_180018F1F
0x180018ed1  mov     rax, rdx
0x180018ed4  and     eax, 8
0x180018ed7  cmp     rax, rdx
0x180018eda  jnz     short loc_180018F1F
0x180018edc  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180018ee3  mov     [rsp+98h+var_48], r8d
0x180018ee8  mov     [rsp+98h+var_40], rax
0x180018eed  lea     rdx, byte_18005D667
0x180018ef4  lea     rax, [rsp+98h+var_48]
0x180018ef9  mov     [rsp+98h+var_44], 13Eh
0x180018f01  mov     [rsp+98h+var_68], rax
0x180018f06  lea     rax, [rsp+98h+var_44]
0x180018f0b  mov     [rsp+98h+var_70], rax
0x180018f10  lea     rax, [rsp+98h+var_40]
0x180018f15  mov     [rsp+98h+var_78], rax
0x180018f1a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018f1f  add     rsp, 68h
0x180018f23  pop     r15
0x180018f25  pop     r14
0x180018f27  pop     rdi
0x180018f28  pop     rsi
0x180018f29  pop     rbp
0x180018f2a  pop     rbx
0x180018f2b  retn
```
