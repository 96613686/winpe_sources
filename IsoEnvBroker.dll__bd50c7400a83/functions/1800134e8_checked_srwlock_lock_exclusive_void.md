# checked_srwlock::lock_exclusive(void)

- ea: `0x1800134e8`
- end: `0x180013556`
- name: `?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010b00`
- `0x180013b04`
- `0x1800238a0`
- `0x180023fb0`
- `0x180025a90`
- `0x1800274e0`
- `0x180028ac0`
- `0x180029ad0`
- `0x1800373a0`
- `0x180048f30`
- `0x180049e70`
- `0x18004a440`
- `0x18004a870`
- `0x18004ebc0`
- `0x18004f960`
- `0x1800501c0`
- `0x1800547c0`
- `0x180054d30`
- `0x1800556f0`
- `0x1800564f0`
- `0x180056d90`
- `0x180057c30`
- `0x180057f40`
- `0x180058e80`
- `0x18005b590`
- `0x18005da50`
- `0x18005deb0`
- `0x18005e6a0`
- `0x180061100`
- `0x180062b20`
- `0x180062ba8`

## callees

- `0x1800075e4`
- `0x1800134e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001351d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001351d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013507`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013507`

## string_xrefs

- `0x180013544`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
_QWORD *__fastcall checked_srwlock::lock_exclusive(__int64 a1, _QWORD *a2)
{
  int v2; // ebx
  DWORD CurrentThreadId; // esi
  const char *v5; // r9
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = dword_1800B9160;
  *a2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( v2 == CurrentThreadId )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v5);
  AcquireSRWLockExclusive(&g_lock);
  dword_1800B9160 = CurrentThreadId;
  result = a2;
  *a2 = &g_lock;
  return result;
}

```

## disassembly

```asm
0x1800134e8  mov     [rsp+arg_0], rbx
0x1800134ed  mov     [rsp+arg_8], rsi
0x1800134f2  push    rdi
0x1800134f3  sub     rsp, 20h
0x1800134f7  mov     ebx, cs:dword_1800B9160
0x1800134fd  mov     rdi, rdx
0x180013500  mov     qword ptr [rdx], 0
0x180013507  call    cs:__imp_GetCurrentThreadId
0x18001350d  mov     esi, eax
0x18001350f  cmp     ebx, eax
0x180013511  jz      short loc_18001353F
0x180013513  lea     rbx, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x18001351a  mov     rcx, rbx; SRWLock
0x18001351d  call    cs:__imp_AcquireSRWLockExclusive
0x180013523  mov     cs:dword_1800B9160, esi
0x180013529  mov     rax, rdi
0x18001352c  mov     rsi, [rsp+28h+arg_8]
0x180013531  mov     [rdi], rbx
0x180013534  mov     rbx, [rsp+28h+arg_0]
0x180013539  add     rsp, 20h
0x18001353d  pop     rdi
0x18001353e  retn
0x18001353f  mov     rcx, [rsp+28h]; this
0x180013544  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18001354b  mov     edx, 2Ch ; ','; void *
0x180013550  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
