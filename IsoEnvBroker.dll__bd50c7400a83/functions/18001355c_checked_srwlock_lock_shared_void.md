# checked_srwlock::lock_shared(void)

- ea: `0x18001355c`
- end: `0x1800135bf`
- name: `?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012140`
- `0x180026870`
- `0x180028120`
- `0x1800307b0`
- `0x180037c80`
- `0x180037cd0`
- `0x180037d40`
- `0x180037db0`
- `0x180037e30`
- `0x180037e80`
- `0x180037ef0`
- `0x180037f60`
- `0x180037fd0`
- `0x1800481a0`
- `0x1800481f0`
- `0x180048240`
- `0x1800482b0`
- `0x1800483e0`
- `0x180048430`
- `0x1800485b0`
- `0x180048620`
- `0x180048670`
- `0x180049750`
- `0x180049a50`
- `0x18004b4a0`
- `0x18004b5c0`
- `0x18004c700`
- `0x18004c780`
- `0x18004c7d0`
- `0x18004fa10`
- `0x18004fa60`
- `0x18004fab0`
- `0x18004fb00`
- `0x180052c60`
- `0x1800555f0`
- `0x180055670`
- `0x180057870`
- `0x18005da50`
- `0x18005f190`
- `0x18005f240`
- `0x18005f2c0`

## callees

- `0x1800075e4`
- `0x18001355c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001358a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001358a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013576`

## string_xrefs

- `0x1800135ad`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
_QWORD *__fastcall checked_srwlock::lock_shared(__int64 a1, _QWORD *a2)
{
  int v2; // ebx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = dword_1800B9160;
  *a2 = 0;
  if ( v2 == GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v4);
  AcquireSRWLockShared(&g_lock);
  _InterlockedIncrement(&dword_1800B9164);
  *a2 = &g_lock;
  return a2;
}

```

## disassembly

```asm
0x18001355c  mov     [rsp+arg_0], rbx
0x180013561  push    rdi
0x180013562  sub     rsp, 20h
0x180013566  mov     ebx, cs:dword_1800B9160
0x18001356c  mov     rdi, rdx
0x18001356f  mov     qword ptr [rdx], 0
0x180013576  call    cs:__imp_GetCurrentThreadId
0x18001357c  cmp     ebx, eax
0x18001357e  jz      short loc_1800135A8
0x180013580  lea     rbx, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x180013587  mov     rcx, rbx; SRWLock
0x18001358a  call    cs:__imp_AcquireSRWLockShared
0x180013590  lock inc cs:dword_1800B9164
0x180013597  mov     [rdi], rbx
0x18001359a  mov     rax, rdi
0x18001359d  mov     rbx, [rsp+28h+arg_0]
0x1800135a2  add     rsp, 20h
0x1800135a6  pop     rdi
0x1800135a7  retn
0x1800135a8  mov     rcx, [rsp+28h]; this
0x1800135ad  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800135b4  mov     edx, 2Ch ; ','; void *
0x1800135b9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
