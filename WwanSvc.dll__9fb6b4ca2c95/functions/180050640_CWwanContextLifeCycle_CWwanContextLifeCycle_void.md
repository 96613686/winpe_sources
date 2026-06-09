# CWwanContextLifeCycle::~CWwanContextLifeCycle(void)

- ea: `0x180050640`
- end: `0x1800506f5`
- name: `??1CWwanContextLifeCycle@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(CWwanContextLifeCycle *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047dd8`
- `0x18004cd38`
- `0x1800c9516`
- `0x1800c9541`
- `0x1800c9dd7`

## callees

- `0x180014f1c`
- `0x180050640`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x18005068e`
- `MobileNetworking!StopTimer` at `0x18005068e`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800506ce`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800506ce`
- `MobileNetworking!AcquireWriteLock` at `0x18005067e`
- `MobileNetworking!AcquireWriteLock` at `0x18005067e`
- `MobileNetworking!ReleaseWriteLock` at `0x1800506a7`
- `MobileNetworking!ReleaseWriteLock` at `0x1800506a7`
- `MobileNetworking!DeleteTimer` at `0x1800506c5`
- `MobileNetworking!DeleteTimer` at `0x1800506c5`

## string_xrefs

- `0x1800506ad`: `Timer Stop Completed`
- `0x1800506d4`: `Timer Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanContextLifeCycle::~CWwanContextLifeCycle(CWwanContextLifeCycle *this)
{
  char *v1; // rdi

  v1 = (char *)this + 2680;
  if ( *((_DWORD *)this + 698) )
  {
    AcquireWriteLock(*((_QWORD *)this + 348), v1, "CWwanContextLifeCycle::~CWwanContextLifeCycle", 59);
    StopTimer(*((_QWORD *)this + 348), "CWwanContextLifeCycle::~CWwanContextLifeCycle");
    ReleaseWriteLock(*((_QWORD *)this + 348), v1, "CWwanContextLifeCycle::~CWwanContextLifeCycle", 61);
    WwanLog::Info("CWwanContextLifeCycle::~CWwanContextLifeCycle", 0, L"Timer Stop Completed");
    DeleteTimer(*((_QWORD *)this + 348));
    DeleteReadWriteLock(v1);
    WwanLog::Info("CWwanContextLifeCycle::~CWwanContextLifeCycle", 0, L"Timer Deinitialization Completed");
  }
}

```

## disassembly

```asm
0x180050640  mov     [rsp+arg_0], rbx
0x180050645  mov     [rsp+arg_8], rsi
0x18005064a  push    rdi
0x18005064b  sub     rsp, 20h
0x18005064f  lea     rdi, [rcx+0A78h]
0x180050656  mov     rbx, rcx
0x180050659  mov     eax, [rdi+70h]
0x18005065c  test    eax, eax
0x18005065e  jz      loc_1800506E5
0x180050664  mov     rcx, [rcx+0AE0h]
0x18005066b  lea     rsi, aCwwancontextli_26; "CWwanContextLifeCycle::~CWwanContextLif"...
0x180050672  mov     r8, rsi
0x180050675  mov     r9d, 3Bh ; ';'
0x18005067b  mov     rdx, rdi
0x18005067e  call    cs:__imp_AcquireWriteLock
0x180050684  mov     rcx, [rbx+0AE0h]
0x18005068b  mov     rdx, rsi
0x18005068e  call    cs:__imp_StopTimer
0x180050694  mov     rcx, [rbx+0AE0h]
0x18005069b  mov     r9d, 3Dh ; '='
0x1800506a1  mov     r8, rsi
0x1800506a4  mov     rdx, rdi
0x1800506a7  call    cs:__imp_ReleaseWriteLock
0x1800506ad  lea     r8, aTimerStopCompl; "Timer Stop Completed"
0x1800506b4  xor     edx, edx; struct _GUID *
0x1800506b6  mov     rcx, rsi; char *
0x1800506b9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800506be  mov     rcx, [rbx+0AE0h]
0x1800506c5  call    cs:__imp_DeleteTimer
0x1800506cb  mov     rcx, rdi
0x1800506ce  call    cs:__imp_DeleteReadWriteLock
0x1800506d4  lea     r8, aTimerDeinitial_0; "Timer Deinitialization Completed"
0x1800506db  xor     edx, edx; struct _GUID *
0x1800506dd  mov     rcx, rsi; char *
0x1800506e0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800506e5  mov     rbx, [rsp+28h+arg_0]
0x1800506ea  mov     rsi, [rsp+28h+arg_8]
0x1800506ef  add     rsp, 20h
0x1800506f3  pop     rdi
0x1800506f4  retn
```
