# WimpFSFSetBackgroundPriorities

- ea: `0x14002aa88`
- end: `0x14002ab89`
- name: `WimpFSFSetBackgroundPriorities`
- size: `257`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028f44`

## callees

- `0x140011560`
- `0x14002aa88`
- `0x14002ab90`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14002ab23`
- `ntoskrnl!KeQueryPriorityThread` at `0x14002ab23`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aacf`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002ab05`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aacf`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002ab05`

## pseudocode

```c
__int64 __fastcall WimpFSFSetBackgroundPriorities(__int64 a1)
{
  NTSTATUS InformationThread; // edi
  KPRIORITY PriorityThread; // eax
  __int64 v4; // rdx
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)a1 = 0;
  v6 = 0;
  InformationThread = ZwQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, (PVOID)(a1 + 4), 4u, 0);
  if ( InformationThread >= 0 )
  {
    *(_DWORD *)a1 |= 1u;
    InformationThread = ZwQueryInformationThread(
                          (HANDLE)0xFFFFFFFFFFFFFFFELL,
                          ThreadPagePriority,
                          (PVOID)(a1 + 8),
                          4u,
                          0);
    if ( InformationThread >= 0 )
    {
      *(_DWORD *)a1 |= 2u;
      PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
      *(_DWORD *)a1 |= 4u;
      LODWORD(v6) = v6 | 7;
      *(_DWORD *)(a1 + 12) = PriorityThread;
      *((_QWORD *)&v6 + 1) = 0x400000001LL;
      DWORD1(v6) = 0;
      InformationThread = WimpFSFSetPriorities(&v6, 0);
      if ( InformationThread < 0 )
      {
        LOBYTE(v4) = 1;
        WimpFSFSetPriorities(a1, v4);
      }
    }
  }
  return (unsigned int)InformationThread;
}

```

## disassembly

```asm
0x14002aa88  mov     [rsp+arg_8], rbx
0x14002aa8d  push    rdi
0x14002aa8e  sub     rsp, 50h
0x14002aa92  mov     rax, cs:__security_cookie
0x14002aa99  xor     rax, rsp
0x14002aa9c  mov     [rsp+58h+var_18], rax
0x14002aaa1  mov     edx, 16h; ThreadInformationClass
0x14002aaa6  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x14002aaaf  xorps   xmm1, xmm1
0x14002aab2  lea     r8, [rcx+4]; ThreadInformation
0x14002aab6  mov     rbx, rcx
0x14002aab9  xorps   xmm0, xmm0
0x14002aabc  movups  xmmword ptr [rcx], xmm1
0x14002aabf  lea     r9d, [rdx-12h]; ThreadInformationLength
0x14002aac3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002aaca  movups  [rsp+58h+var_28], xmm0
0x14002aacf  call    cs:__imp_ZwQueryInformationThread
0x14002aad6  nop     dword ptr [rax+rax+00h]
0x14002aadb  mov     edi, eax
0x14002aadd  test    eax, eax
0x14002aadf  js      loc_14002AB6E
0x14002aae5  or      dword ptr [rbx], 1
0x14002aae8  lea     r8, [rbx+8]; ThreadInformation
0x14002aaec  mov     edx, 18h; ThreadInformationClass
0x14002aaf1  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x14002aafa  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002ab01  lea     r9d, [rdx-14h]; ThreadInformationLength
0x14002ab05  call    cs:__imp_ZwQueryInformationThread
0x14002ab0c  nop     dword ptr [rax+rax+00h]
0x14002ab11  mov     edi, eax
0x14002ab13  test    eax, eax
0x14002ab15  js      short loc_14002AB6E
0x14002ab17  or      dword ptr [rbx], 2
0x14002ab1a  mov     rcx, gs:188h; Thread
0x14002ab23  call    cs:__imp_KeQueryPriorityThread
0x14002ab2a  nop     dword ptr [rax+rax+00h]
0x14002ab2f  or      dword ptr [rbx], 4
0x14002ab32  lea     rcx, [rsp+58h+var_28]
0x14002ab37  or      dword ptr [rsp+58h+var_28], 7
0x14002ab3c  xor     edx, edx
0x14002ab3e  mov     [rbx+0Ch], eax
0x14002ab41  mov     dword ptr [rsp+58h+var_28+0Ch], 4
0x14002ab49  mov     dword ptr [rsp+58h+var_28+8], 1
0x14002ab51  mov     dword ptr [rsp+58h+var_28+4], 0
0x14002ab59  call    WimpFSFSetPriorities
0x14002ab5e  mov     edi, eax
0x14002ab60  test    eax, eax
0x14002ab62  jns     short loc_14002AB6E
0x14002ab64  mov     dl, 1
0x14002ab66  mov     rcx, rbx
0x14002ab69  call    WimpFSFSetPriorities
0x14002ab6e  mov     eax, edi
0x14002ab70  mov     rcx, [rsp+58h+var_18]
0x14002ab75  xor     rcx, rsp; StackCookie
0x14002ab78  call    __security_check_cookie
0x14002ab7d  mov     rbx, [rsp+58h+arg_8]
0x14002ab82  add     rsp, 50h
0x14002ab86  pop     rdi
0x14002ab87  retn
```
