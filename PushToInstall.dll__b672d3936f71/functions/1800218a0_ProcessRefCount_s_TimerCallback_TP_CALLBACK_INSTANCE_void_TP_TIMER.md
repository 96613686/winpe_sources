# ProcessRefCount::s_TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800218a0`
- end: `0x18002190e`
- name: `?s_TimerCallback@ProcessRefCount@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `110`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800218a0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021907`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800218ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800218ec`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800218f2`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800218f2`

## pseudocode

```c
void __fastcall ProcessRefCount::s_TimerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  int v4; // eax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    v4 = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, PVOID, PTP_TIMER))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 24LL))(
           Microsoft::WRL::Details::ModuleBase::module_,
           Context,
           Timer);
  else
    v4 = 0;
  if ( v4 == *((_DWORD *)Context + 3) || *((_DWORD *)Context + 2) > 6u )
  {
    SetEvent(*((HANDLE *)Context + 3));
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)Context + 2);
    v5 = (struct _TP_TIMER *)*((_QWORD *)Context + 4);
    pftDueTime = (struct _FILETIME)-50000000LL;
    SetThreadpoolTimer(v5, &pftDueTime, 0, 0);
    CoFreeUnusedLibraries();
  }
}

```

## disassembly

```asm
0x1800218a0  push    rbx
0x1800218a2  sub     rsp, 20h
0x1800218a6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800218ad  mov     rbx, rdx
0x1800218b0  test    rcx, rcx
0x1800218b3  jnz     short loc_1800218B9
0x1800218b5  xor     eax, eax
0x1800218b7  jmp     short loc_1800218C5
0x1800218b9  mov     rax, [rcx]
0x1800218bc  mov     rax, [rax+18h]
0x1800218c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c5  cmp     eax, [rbx+0Ch]
0x1800218c8  jz      short loc_1800218FE
0x1800218ca  cmp     dword ptr [rbx+8], 6
0x1800218ce  ja      short loc_1800218FE
0x1800218d0  lock inc dword ptr [rbx+8]
0x1800218d4  mov     rcx, [rbx+20h]; pti
0x1800218d8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800218dd  xor     r9d, r9d; msWindowLength
0x1800218e0  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800218e9  xor     r8d, r8d; msPeriod
0x1800218ec  call    cs:__imp_SetThreadpoolTimer
0x1800218f2  call    cs:__imp_CoFreeUnusedLibraries
0x1800218f8  add     rsp, 20h
0x1800218fc  pop     rbx
0x1800218fd  retn
0x1800218fe  mov     rcx, [rbx+18h]
0x180021902  add     rsp, 20h
0x180021906  pop     rbx
0x180021907  jmp     cs:__imp_SetEvent
```
