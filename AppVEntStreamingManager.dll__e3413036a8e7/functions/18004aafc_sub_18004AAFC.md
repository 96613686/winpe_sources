# sub_18004AAFC

- ea: `0x18004aafc`
- end: `0x18004ac1e`
- name: `sub_18004AAFC`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004ac70`

## callees

- `0x18000f110`
- `0x18000fd34`
- `0x18004a9c8`
- `0x18004aafc`
- `0x18004acb0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004abfd`
- `KERNEL32!DeleteCriticalSection` at `0x18004abfd`
- `KERNEL32!CloseHandle` at `0x18004abe8`
- `KERNEL32!CloseHandle` at `0x18004abe8`
- `KERNEL32!GetCurrentThreadId` at `0x18004ab38`
- `KERNEL32!GetCurrentThreadId` at `0x18004ab38`
- `KERNEL32!LeaveCriticalSection` at `0x18004ab87`
- `KERNEL32!LeaveCriticalSection` at `0x18004ab87`
- `KERNEL32!EnterCriticalSection` at `0x18004ab1f`
- `KERNEL32!EnterCriticalSection` at `0x18004ab1f`
- `KERNEL32!QueueUserWorkItem` at `0x18004ab5f`
- `KERNEL32!QueueUserWorkItem` at `0x18004ab5f`

## pseudocode

```c
__int64 __fastcall sub_18004AAFC(__int64 a1)
{
  int v2; // edx
  DWORD CurrentThreadId; // eax
  volatile signed __int32 *v4; // rdi
  void *v5; // rcx

  *(_QWORD *)a1 = &Streaming::ForegroundFilesystemDataReceiver::`vftable';
  sub_18004ACB0();
  EnterCriticalSection(&stru_1800AA790);
  v2 = qword_1800AA7B8 + 1;
  LODWORD(qword_1800AA7B8) = v2;
  if ( v2 == 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v2 = qword_1800AA7B8;
    HIDWORD(qword_1800AA7B8) = CurrentThreadId;
  }
  if ( !--dword_1800AA58C )
  {
    QueueUserWorkItem((LPTHREAD_START_ROUTINE)Function, 0, 0);
    v2 = qword_1800AA7B8;
  }
  LODWORD(qword_1800AA7B8) = v2 - 1;
  if ( v2 == 1 )
    qword_1800AA7B8 = 0;
  LeaveCriticalSection(&stru_1800AA790);
  sub_18000F110(a1 + 192);
  v4 = *(volatile signed __int32 **)(a1 + 176);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = *(void **)(a1 + 152);
  if ( v5 )
  {
    CloseHandle(v5);
    *(_QWORD *)(a1 + 152) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  sub_18004A9C8(a1 + 64);
  return sub_18000FD34(a1);
}

```

## disassembly

```asm
0x18004aafc  mov     [rsp+arg_8], rbx
0x18004ab01  push    rdi
0x18004ab02  sub     rsp, 20h
0x18004ab06  lea     rax, ??_7ForegroundFilesystemDataReceiver@Streaming@@6B@; const Streaming::ForegroundFilesystemDataReceiver::`vftable'
0x18004ab0d  mov     rbx, rcx
0x18004ab10  mov     [rcx], rax
0x18004ab13  call    sub_18004ACB0
0x18004ab18  lea     rcx, stru_1800AA790; lpCriticalSection
0x18004ab1f  call    cs:EnterCriticalSection
0x18004ab25  mov     edx, dword ptr cs:qword_1800AA7B8
0x18004ab2b  inc     edx
0x18004ab2d  mov     dword ptr cs:qword_1800AA7B8, edx
0x18004ab33  cmp     edx, 1
0x18004ab36  jnz     short loc_18004AB4A
0x18004ab38  call    cs:GetCurrentThreadId
0x18004ab3e  mov     edx, dword ptr cs:qword_1800AA7B8
0x18004ab44  mov     dword ptr cs:qword_1800AA7B8+4, eax
0x18004ab4a  sub     cs:dword_1800AA58C, 1
0x18004ab51  jnz     short loc_18004AB6B
0x18004ab53  xor     r8d, r8d; Flags
0x18004ab56  lea     rcx, Function; Function
0x18004ab5d  xor     edx, edx; Context
0x18004ab5f  call    cs:QueueUserWorkItem
0x18004ab65  mov     edx, dword ptr cs:qword_1800AA7B8
0x18004ab6b  sub     edx, 1
0x18004ab6e  mov     dword ptr cs:qword_1800AA7B8, edx
0x18004ab74  jnz     short loc_18004AB80
0x18004ab76  mov     dword ptr cs:qword_1800AA7B8+4, 0
0x18004ab80  lea     rcx, stru_1800AA790; lpCriticalSection
0x18004ab87  call    cs:LeaveCriticalSection
0x18004ab8d  lea     rcx, [rbx+0C0h]
0x18004ab94  call    sub_18000F110
0x18004ab99  mov     rdi, [rbx+0B0h]
0x18004aba0  test    rdi, rdi
0x18004aba3  jz      short loc_18004ABDC
0x18004aba5  or      eax, 0FFFFFFFFh
0x18004aba8  lock xadd [rdi+8], eax
0x18004abad  cmp     eax, 1
0x18004abb0  jnz     short loc_18004ABDC
0x18004abb2  mov     rax, [rdi]
0x18004abb5  mov     rcx, rdi
0x18004abb8  mov     rax, [rax]
0x18004abbb  call    j__guard_dispatch_icall
0x18004abc0  or      eax, 0FFFFFFFFh
0x18004abc3  lock xadd [rdi+0Ch], eax
0x18004abc8  cmp     eax, 1
0x18004abcb  jnz     short loc_18004ABDC
0x18004abcd  mov     rax, [rdi]
0x18004abd0  mov     rcx, rdi
0x18004abd3  mov     rax, [rax+8]
0x18004abd7  call    j__guard_dispatch_icall
0x18004abdc  mov     rcx, [rbx+98h]; hObject
0x18004abe3  test    rcx, rcx
0x18004abe6  jz      short loc_18004ABF9
0x18004abe8  call    cs:CloseHandle
0x18004abee  mov     qword ptr [rbx+98h], 0
0x18004abf9  lea     rcx, [rbx+68h]; lpCriticalSection
0x18004abfd  call    cs:__imp_DeleteCriticalSection
0x18004ac03  lea     rcx, [rbx+40h]
0x18004ac07  call    sub_18004A9C8
0x18004ac0c  mov     rcx, rbx
0x18004ac0f  mov     rbx, [rsp+28h+arg_8]
0x18004ac14  add     rsp, 20h
0x18004ac18  pop     rdi
0x18004ac19  jmp     sub_18000FD34
```
