# Recycler::InitializeConcurrent(JsUtil::ThreadService *)

- ea: `0x1802544dc`
- end: `0x180254682`
- name: `?InitializeConcurrent@Recycler@@AEAA_NPEAVThreadService@JsUtil@@@Z`
- size: `422`
- prototype: `bool __fastcall(Recycler *__hidden this, struct JsUtil::ThreadService *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801a9858`

## callees

- `0x180107364`
- `0x180110cfc`
- `0x1801c9798`
- `0x1802544dc`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1802545f8`
- `msvcrt!_beginthreadex` at `0x1802545f8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180254643`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180254643`
- `KERNEL32!CreateEventW` at `0x180254513`
- `KERNEL32!CreateEventW` at `0x1802545b7`
- `KERNEL32!CreateEventW` at `0x180254513`
- `KERNEL32!CreateEventW` at `0x1802545b7`

## pseudocode

```c
char __fastcall Recycler::InitializeConcurrent(Recycler *this, struct JsUtil::ThreadService *a2)
{
  HANDLE EventW; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  HANDLE v7; // rax
  void *v8; // rcx
  char pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  char v11; // [rsp+31h] [rbp-27h] BYREF
  char v12; // [rsp+32h] [rbp-26h] BYREF
  char v13; // [rsp+33h] [rbp-25h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h]
  HANDLE Handles[3]; // [rsp+40h] [rbp-18h] BYREF

  v14 = -2;
  *((_QWORD *)this + 44) = a2;
  try
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 1618) = EventW;
    if ( !EventW )
      throw (Js::OutOfMemoryException *)&pExceptionObject;
    v5 = operator new<HeapAllocator>(96, &HeapAllocator::Instance, HeapAllocator::Alloc);
    if ( v5 )
    {
      *(_QWORD *)v5 = *((_QWORD *)this + 2037);
      *(_QWORD *)(v5 + 8) = 0;
      *(_QWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 24) = 0;
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = (char *)this + 12712;
      *(_QWORD *)(v5 + 48) = 0;
      *(_BYTE *)(v5 + 56) = 0;
      *(_QWORD *)(v5 + 64) = 0;
      *(_QWORD *)(v5 + 72) = 0;
      *(_DWORD *)(v5 + 80) = 0;
      *(_QWORD *)(v5 + 88) = 0;
    }
    else
    {
      v5 = 0;
    }
    *((_QWORD *)this + 2020) = v5;
    if ( !JsUtil::ThreadService::HasCallback(a2) )
    {
      v7 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 1617) = v7;
      if ( !v7 )
        throw (Js::OutOfMemoryException *)&v11;
      v8 = (void *)_beginthreadex(0, 0x493E0u, Recycler::StaticThreadProc, this, 0x10000u, 0);
      *((_QWORD *)this + 1619) = v8;
      if ( !v8 )
        throw (Js::OutOfMemoryException *)&v12;
      Handles[0] = *((HANDLE *)this + 1618);
      Handles[1] = v8;
      if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
      {
        *((_QWORD *)this + 1619) = 0;
        throw (Js::OutOfMemoryException *)&v13;
      }
    }
    *((_DWORD *)this + 27) = 0x200000;
  }
  catch ( Js::OutOfMemoryException )
  {
    if ( *((_QWORD *)this + 2020) )
    {
      DeleteObject<HeapAllocator,ArenaAllocator>(v6, *((_QWORD *)this + 2020));
      *((_QWORD *)this + 2020) = 0;
    }
    if ( *((_QWORD *)this + 1618) )
    {
      CloseHandle(*((HANDLE *)this + 1618));
      *((_QWORD *)this + 1618) = 0;
    }
    if ( *((_QWORD *)this + 1617) )
    {
      CloseHandle(*((HANDLE *)this + 1617));
      *((_QWORD *)this + 1617) = 0;
    }
    *((_QWORD *)this + 44) = 0;
    *(_WORD *)((char *)this + 12911) = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1802544dc  mov     rax, rsp
0x1802544df  mov     [rax+10h], rdx
0x1802544e3  mov     [rax+8], rcx
0x1802544e7  push    rdi
0x1802544e8  sub     rsp, 50h
0x1802544ec  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x1802544f4  mov     [rax+18h], rbx
0x1802544f8  mov     [rax+20h], rsi
0x1802544fc  mov     rdi, rdx
0x1802544ff  mov     rbx, rcx
0x180254502  mov     [rcx+160h], rdx
0x180254509  xor     r9d, r9d; lpName
0x18025450c  xor     r8d, r8d; bInitialState
0x18025450f  xor     edx, edx; bManualReset
0x180254511  xor     ecx, ecx; lpEventAttributes
0x180254513  call    cs:__imp_CreateEventW
0x180254519  mov     [rbx+3290h], rax
0x180254520  xor     esi, esi
0x180254522  test    rax, rax
0x180254525  jnz     short loc_180254538
0x180254527  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x18025452e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180254533  call    _CxxThrowException_0
0x180254538  lea     r8, ?Alloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18025453f  lea     rdx, ?Instance@HeapAllocator@@2U1@A; HeapAllocator HeapAllocator::Instance
0x180254546  mov     ecx, 60h ; '`'
0x18025454b  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x180254550  test    rax, rax
0x180254553  jz      short loc_180254593
0x180254555  mov     rcx, [rbx+3FA8h]
0x18025455c  mov     [rax], rcx
0x18025455f  mov     [rax+8], rsi
0x180254563  mov     [rax+10h], rsi
0x180254567  mov     [rax+18h], rsi
0x18025456b  mov     [rax+20h], rsi
0x18025456f  lea     rcx, [rbx+31A8h]
0x180254576  mov     [rax+28h], rcx
0x18025457a  mov     [rax+30h], rsi
0x18025457e  mov     [rax+38h], sil
0x180254582  mov     [rax+40h], rsi
0x180254586  mov     [rax+48h], rsi
0x18025458a  mov     [rax+50h], esi
0x18025458d  mov     [rax+58h], rsi
0x180254591  jmp     short loc_180254596
0x180254593  mov     rax, rsi
0x180254596  mov     [rbx+3F20h], rax
0x18025459d  mov     rcx, rdi; this
0x1802545a0  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1802545a5  test    al, al
0x1802545a7  jnz     loc_180254665
0x1802545ad  xor     r9d, r9d; lpName
0x1802545b0  xor     r8d, r8d; bInitialState
0x1802545b3  xor     edx, edx; bManualReset
0x1802545b5  xor     ecx, ecx; lpEventAttributes
0x1802545b7  call    cs:__imp_CreateEventW
0x1802545bd  mov     [rbx+3288h], rax
0x1802545c4  test    rax, rax
0x1802545c7  jnz     short loc_1802545DA
0x1802545c9  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x1802545d0  lea     rcx, [rsp+58h+var_27]; pExceptionObject
0x1802545d5  call    _CxxThrowException_0
0x1802545da  mov     [rsp+58h+ThrdAddr], rsi; ThrdAddr
0x1802545df  mov     [rsp+58h+InitFlag], 10000h; InitFlag
0x1802545e7  mov     r9, rbx; ArgList
0x1802545ea  lea     r8, ?StaticThreadProc@Recycler@@CAIPEAX@Z; StartAddress
0x1802545f1  mov     edx, 493E0h; StackSize
0x1802545f6  xor     ecx, ecx; Security
0x1802545f8  call    cs:__imp__beginthreadex
0x1802545fe  mov     rcx, rax
0x180254601  mov     [rbx+3298h], rax
0x180254608  test    rax, rax
0x18025460b  jnz     short loc_18025461E
0x18025460d  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x180254614  lea     rcx, [rsp+58h+var_26]; pExceptionObject
0x180254619  call    _CxxThrowException_0
0x18025461e  mov     rax, [rbx+3290h]
0x180254625  mov     [rsp+58h+Handles], rax
0x18025462a  mov     [rsp+58h+var_10], rcx
0x18025462f  mov     [rsp+58h+InitFlag], esi; bAlertable
0x180254633  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180254637  xor     r8d, r8d; bWaitAll
0x18025463a  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18025463f  lea     ecx, [r8+2]; nCount
0x180254643  call    cs:__imp_WaitForMultipleObjectsEx
0x180254649  test    eax, eax
0x18025464b  jz      short loc_180254665
0x18025464d  mov     [rbx+3298h], rsi
0x180254654  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x18025465b  lea     rcx, [rsp+58h+var_25]; pExceptionObject
0x180254660  call    _CxxThrowException_0
0x180254665  mov     dword ptr [rbx+6Ch], 200000h
0x18025466c  mov     al, 1
0x18025466e  jmp     short loc_180254672
0x180254670  xor     al, al
0x180254672  mov     rbx, [rsp+58h+arg_10]
0x180254677  mov     rsi, [rsp+58h+arg_18]
0x18025467c  add     rsp, 50h
0x180254680  pop     rdi
0x180254681  retn
```
