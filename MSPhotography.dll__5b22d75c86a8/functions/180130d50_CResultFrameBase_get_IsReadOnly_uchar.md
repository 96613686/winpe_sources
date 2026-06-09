# CResultFrameBase::get_IsReadOnly(uchar *)

- ea: `0x180130d50`
- end: `0x180130eb7`
- name: `?get_IsReadOnly@CResultFrameBase@@UEAAJPEAE@Z`
- size: `359`
- prototype: `__int64 __fastcall(CResultFrameBase *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009784`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18012f850`
- `0x180130d50`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180130ea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180130ea4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130e2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130e2c`

## string_xrefs

- `0x180130d74`: `CResultFrameBase::get_IsReadOnly`
- `0x180130e05`: `CResultFrameBase::get_IsReadOnly`

## pseudocode

```c
__int64 __fastcall CResultFrameBase::get_IsReadOnly(CResultFrameBase *this, unsigned __int8 *a2)
{
  __int64 *v4; // rcx
  unsigned int v5; // ebx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v8; // r8d
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  char v12; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+18h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CResultFrameBase::get_IsReadOnly", 73);
  if ( *((_BYTE *)this + 80) )
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147483629;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147483629 )
      {
        v8 = 77;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CResultFrameBase::get_IsReadOnly", v8, v5);
      }
    }
  }
  else if ( a2 )
  {
    *a2 = 1;
    v5 = 0;
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
      {
        v8 = 80;
        goto LABEL_10;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return v5;
}

```

## disassembly

```asm
0x180130d50  mov     [rsp+arg_8], rbx
0x180130d55  push    rdi
0x180130d56  sub     rsp, 20h
0x180130d5a  mov     rdi, rdx
0x180130d5d  mov     rbx, rcx
0x180130d60  lea     rdx, [rcx+38h]
0x180130d64  lea     rcx, [rsp+28h+SRWLock]
0x180130d69  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180130d6e  mov     r8d, 49h ; 'I'; int
0x180130d74  lea     rdx, aCresultframeba_4; "CResultFrameBase::get_IsReadOnly"
0x180130d7b  lea     rcx, [rsp+28h+arg_0]; this
0x180130d80  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180130d85  cmp     byte ptr [rbx+50h], 0
0x180130d89  jz      loc_180130E16
0x180130d8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180130d96  mov     ebx, 80000013h
0x180130d9b  test    rcx, rcx
0x180130d9e  jnz     short loc_180130DE1
0x180130da0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180130da6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180130dad  mov     rcx, rax
0x180130db0  test    rax, rax
0x180130db3  jz      short loc_180130DD3
0x180130db5  mov     rax, [rax]
0x180130db8  mov     edx, 7F0h
0x180130dbd  mov     rax, [rax+8]
0x180130dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180130dc6  test    eax, eax
0x180130dc8  jz      short loc_180130DD3
0x180130dca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180130dd1  jmp     short loc_180130DE1
0x180130dd3  lea     rcx, qword_18015FF10; this
0x180130dda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180130de1  cmp     byte ptr [rcx+8], 0
0x180130de5  jz      loc_180130E90
0x180130deb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180130df0  cmp     [rax+7CCh], ebx
0x180130df6  jz      loc_180130E90
0x180130dfc  mov     r8d, 4Dh ; 'M'; int
0x180130e02  mov     r9d, ebx; int
0x180130e05  lea     rdx, aCresultframeba_4; "CResultFrameBase::get_IsReadOnly"
0x180130e0c  mov     rcx, rax; this
0x180130e0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180130e14  jmp     short loc_180130E90
0x180130e16  test    rdi, rdi
0x180130e19  jnz     short loc_180130E8B
0x180130e1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180130e22  mov     ebx, 80004003h
0x180130e27  test    rcx, rcx
0x180130e2a  jnz     short loc_180130E6D
0x180130e2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180130e32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180130e39  mov     rcx, rax
0x180130e3c  test    rax, rax
0x180130e3f  jz      short loc_180130E5F
0x180130e41  mov     rax, [rax]
0x180130e44  mov     edx, 7F0h
0x180130e49  mov     rax, [rax+8]
0x180130e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180130e52  test    eax, eax
0x180130e54  jz      short loc_180130E5F
0x180130e56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180130e5d  jmp     short loc_180130E6D
0x180130e5f  lea     rcx, qword_18015FF10; this
0x180130e66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180130e6d  cmp     byte ptr [rcx+8], 0
0x180130e71  jz      short loc_180130E90
0x180130e73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180130e78  cmp     [rax+7CCh], ebx
0x180130e7e  jz      short loc_180130E90
0x180130e80  mov     r8d, 50h ; 'P'
0x180130e86  jmp     loc_180130E02
0x180130e8b  mov     byte ptr [rdi], 1
0x180130e8e  xor     ebx, ebx
0x180130e90  lea     rcx, [rsp+28h+arg_0]; this
0x180130e95  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180130e9a  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180130e9f  test    rcx, rcx
0x180130ea2  jz      short loc_180130EAA
0x180130ea4  call    cs:__imp_ReleaseSRWLockExclusive
0x180130eaa  mov     eax, ebx
0x180130eac  mov     rbx, [rsp+28h+arg_8]
0x180130eb1  add     rsp, 20h
0x180130eb5  pop     rdi
0x180130eb6  retn
```
