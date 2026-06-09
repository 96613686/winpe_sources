# EaLibClearAndReleaseTimer

- ea: `0x180003d90`
- end: `0x180003e12`
- name: `EaLibClearAndReleaseTimer`
- size: `130`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001460`
- `0x180005cc0`

## callees

- `0x180003d90`

## import_xrefs

- `ntdll!TpWaitForTimer` at `0x180003de5`
- `ntdll!TpWaitForTimer` at `0x180003de5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003dc6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003dc6`
- `ntdll!TpReleaseTimer` at `0x180003dee`
- `ntdll!TpReleaseTimer` at `0x180003dee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003df7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003df7`
- `ntdll!TpSetTimer` at `0x180003dd7`
- `ntdll!TpSetTimer` at `0x180003dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003dfd`

## pseudocode

```c
void __fastcall EaLibClearAndReleaseTimer(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi

  if ( *(_BYTE *)(a1 + 120) )
  {
    v1 = *(_QWORD *)(a1 + 128);
    *(_QWORD *)(a1 + 128) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    v2 = a1 + 80;
    *(_DWORD *)(a1 + 88) = 0;
    RtlReleaseSRWLockExclusive(a1 + 80);
    TpSetTimer(v1, 0, 0, 0);
    TpWaitForTimer(v1, 1);
    TpReleaseTimer(v1);
    RtlAcquireSRWLockExclusive(v2);
    *(_DWORD *)(v2 + 8) = GetCurrentThreadId();
  }
}

```

## disassembly

```asm
0x180003d90  sub     rsp, 28h
0x180003d94  cmp     byte ptr [rcx+78h], 0
0x180003d98  jnz     short loc_180003D9F
0x180003d9a  add     rsp, 28h
0x180003d9e  retn
0x180003d9f  xor     eax, eax
0x180003da1  mov     [rsp+28h+arg_0], rbx
0x180003da6  mov     rbx, [rcx+80h]
0x180003dad  mov     [rcx+80h], rax
0x180003db4  mov     [rcx+78h], al
0x180003db7  mov     [rsp+28h+var_8], rdi
0x180003dbc  lea     rdi, [rcx+50h]
0x180003dc0  mov     rcx, rdi
0x180003dc3  mov     [rdi+8], eax
0x180003dc6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003dcc  xor     r9d, r9d
0x180003dcf  xor     r8d, r8d
0x180003dd2  xor     edx, edx
0x180003dd4  mov     rcx, rbx
0x180003dd7  call    cs:__imp_TpSetTimer
0x180003ddd  mov     edx, 1
0x180003de2  mov     rcx, rbx
0x180003de5  call    cs:__imp_TpWaitForTimer
0x180003deb  mov     rcx, rbx
0x180003dee  call    cs:__imp_TpReleaseTimer
0x180003df4  mov     rcx, rdi
0x180003df7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003dfd  call    cs:__imp_GetCurrentThreadId
0x180003e03  mov     rbx, [rsp+28h+arg_0]
0x180003e08  mov     [rdi+8], eax
0x180003e0b  mov     rdi, [rsp+28h+var_8]
0x180003e10  jmp     short loc_180003D9A
```
