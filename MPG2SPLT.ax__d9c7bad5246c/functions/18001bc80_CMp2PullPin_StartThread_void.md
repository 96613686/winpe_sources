# CMp2PullPin::StartThread(void)

- ea: `0x18001bc80`
- end: `0x18001bd29`
- name: `?StartThread@CMp2PullPin@@QEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(CMp2PullPin *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a8a0`

## callees

- `0x180007054`
- `0x180007114`
- `0x18001bc80`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001bcdf`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd01`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd0e`
- `KERNEL32!LeaveCriticalSection` at `0x18001bcdf`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd01`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd0e`
- `KERNEL32!EnterCriticalSection` at `0x18001bc99`
- `KERNEL32!EnterCriticalSection` at `0x18001bc99`

## pseudocode

```c
__int64 __fastcall CMp2PullPin::StartThread(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ULONG_PTR SpinCount; // rcx
  int v4; // esi
  unsigned int v6; // ebx

  v1 = this + 1;
  EnterCriticalSection(this + 1);
  SpinCount = this[3].SpinCount;
  if ( SpinCount && this[3].DebugInfo )
  {
    if ( !this->SpinCount )
    {
      v4 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 40LL))(SpinCount);
      if ( v4 < 0 )
      {
LABEL_7:
        LeaveCriticalSection(v1);
        return (unsigned int)v4;
      }
      if ( !CAMThread::Create(this) )
      {
        v4 = -2147467259;
        goto LABEL_7;
      }
    }
    HIDWORD(this[4].OwningThread) = 1;
    v6 = CAMThread::CallWorker(this, 1);
    LeaveCriticalSection(v1);
    return v6;
  }
  else
  {
    LeaveCriticalSection(v1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001bc80  mov     [rsp+arg_0], rbx
0x18001bc85  mov     [rsp+arg_8], rsi
0x18001bc8a  push    rdi
0x18001bc8b  sub     rsp, 20h
0x18001bc8f  lea     rdi, [rcx+28h]
0x18001bc93  mov     rbx, rcx
0x18001bc96  mov     rcx, rdi; lpCriticalSection
0x18001bc99  call    cs:__imp_EnterCriticalSection
0x18001bc9f  mov     rcx, [rbx+98h]
0x18001bca6  test    rcx, rcx
0x18001bca9  jz      short loc_18001BD0B
0x18001bcab  cmp     qword ptr [rbx+78h], 0
0x18001bcb0  jz      short loc_18001BD0B
0x18001bcb2  cmp     qword ptr [rbx+20h], 0
0x18001bcb7  jnz     short loc_18001BCE9
0x18001bcb9  mov     rax, [rcx]
0x18001bcbc  mov     rax, [rax+28h]
0x18001bcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc5  mov     esi, eax
0x18001bcc7  test    eax, eax
0x18001bcc9  js      short loc_18001BCDC
0x18001bccb  mov     rcx, rbx; this
0x18001bcce  call    ?Create@CAMThread@@QEAAHXZ; CAMThread::Create(void)
0x18001bcd3  test    eax, eax
0x18001bcd5  jnz     short loc_18001BCE9
0x18001bcd7  mov     esi, 80004005h
0x18001bcdc  mov     rcx, rdi; lpCriticalSection
0x18001bcdf  call    cs:__imp_LeaveCriticalSection
0x18001bce5  mov     eax, esi
0x18001bce7  jmp     short loc_18001BD19
0x18001bce9  mov     edx, 1; unsigned int
0x18001bcee  mov     rcx, rbx; this
0x18001bcf1  mov     [rbx+0B4h], edx
0x18001bcf7  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18001bcfc  mov     rcx, rdi; lpCriticalSection
0x18001bcff  mov     ebx, eax
0x18001bd01  call    cs:__imp_LeaveCriticalSection
0x18001bd07  mov     eax, ebx
0x18001bd09  jmp     short loc_18001BD19
0x18001bd0b  mov     rcx, rdi; lpCriticalSection
0x18001bd0e  call    cs:__imp_LeaveCriticalSection
0x18001bd14  mov     eax, 8000FFFFh
0x18001bd19  mov     rbx, [rsp+28h+arg_0]
0x18001bd1e  mov     rsi, [rsp+28h+arg_8]
0x18001bd23  add     rsp, 20h
0x18001bd27  pop     rdi
0x18001bd28  retn
```
