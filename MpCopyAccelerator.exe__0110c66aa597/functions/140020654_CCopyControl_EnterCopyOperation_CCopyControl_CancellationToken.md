# CCopyControl::EnterCopyOperation(CCopyControl::CancellationToken *)

- ea: `0x140020654`
- end: `0x140020728`
- name: `?EnterCopyOperation@CCopyControl@@QEAA?AW4eEnterCopyResult@1@PEAUCancellationToken@1@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f6a0`

## callees

- `0x140005900`
- `0x140005da0`
- `0x140020654`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14002069e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14002069e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400206f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400206f7`
- `KERNEL32!WaitForSingleObject` at `0x140020671`
- `KERNEL32!WaitForSingleObject` at `0x140020671`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCopyControl::EnterCopyOperation(RTL_SRWLOCK *a1, __int64 a2)
{
  DWORD v4; // eax
  RTL_SRWLOCK *v6; // rbp
  RTL_SRWLOCK *v7; // rdi
  _QWORD *Ptr; // r14
  _QWORD *v9; // rax
  _QWORD *v10; // rdx

  v4 = WaitForSingleObject(a1->Ptr, 0);
  if ( !v4 )
    return 1;
  if ( v4 != 258 )
    return 2;
  if ( a2 )
  {
    v6 = a1 + 3;
    AcquireSRWLockExclusive(a1 + 3);
    v7 = a1 + 1;
    Ptr = v7->Ptr;
    if ( v7[1].Ptr == (PVOID)0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("list too long");
    v9 = operator new(0x18u);
    v9[2] = a2;
    ++v7[1].Ptr;
    v10 = (_QWORD *)Ptr[1];
    *v9 = Ptr;
    v9[1] = v10;
    Ptr[1] = v9;
    *v10 = v9;
    ReleaseSRWLockExclusive(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x140020654  mov     [rsp+arg_8], rbx
0x140020659  mov     [rsp+arg_10], rbp
0x14002065e  push    rsi
0x14002065f  push    rdi
0x140020660  push    r14
0x140020662  sub     rsp, 40h
0x140020666  mov     rsi, rdx
0x140020669  mov     rdi, rcx
0x14002066c  xor     edx, edx; dwMilliseconds
0x14002066e  mov     rcx, [rcx]; hHandle
0x140020671  call    cs:__imp_WaitForSingleObject
0x140020677  test    eax, eax
0x140020679  jz      loc_140020701
0x14002067f  cmp     eax, 102h
0x140020684  jz      short loc_14002068D
0x140020686  mov     ebx, 2
0x14002068b  jmp     short loc_140020706
0x14002068d  test    rsi, rsi
0x140020690  jz      short loc_1400206FD
0x140020692  lea     rbp, [rdi+18h]
0x140020696  mov     [rsp+58h+var_38], rbp
0x14002069b  mov     rcx, rbp; SRWLock
0x14002069e  call    cs:__imp_AcquireSRWLockExclusive
0x1400206a4  mov     ebx, 1
0x1400206a9  mov     [rsp+58h+var_30], bl
0x1400206ad  add     rdi, 8
0x1400206b1  mov     r14, [rdi]
0x1400206b4  mov     rax, 0AAAAAAAAAAAAAAAh
0x1400206be  cmp     [rdi+8], rax
0x1400206c2  jz      short loc_14002071B
0x1400206c4  mov     [rsp+58h+var_28], rdi
0x1400206c9  mov     [rsp+58h+var_20], 0
0x1400206d2  lea     ecx, [rbx+17h]; Size
0x1400206d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400206da  mov     [rax+10h], rsi
0x1400206de  add     [rdi+8], rbx
0x1400206e2  mov     rdx, [r14+8]
0x1400206e6  mov     [rax], r14
0x1400206e9  mov     [rax+8], rdx
0x1400206ed  mov     [r14+8], rax
0x1400206f1  mov     [rdx], rax
0x1400206f4  mov     rcx, rbp; SRWLock
0x1400206f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400206fd  xor     eax, eax
0x1400206ff  jmp     short loc_140020708
0x140020701  mov     ebx, 1
0x140020706  mov     eax, ebx
0x140020708  mov     rbx, [rsp+58h+arg_8]
0x14002070d  mov     rbp, [rsp+58h+arg_10]
0x140020712  add     rsp, 40h
0x140020716  pop     r14
0x140020718  pop     rdi
0x140020719  pop     rsi
0x14002071a  retn
0x14002071b  lea     rcx, aListTooLong; "list too long"
0x140020722  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
