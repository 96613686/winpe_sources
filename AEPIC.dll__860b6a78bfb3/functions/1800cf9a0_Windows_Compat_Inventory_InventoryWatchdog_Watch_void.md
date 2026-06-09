# Windows::Compat::Inventory::InventoryWatchdog::Watch(void)

- ea: `0x1800cf9a0`
- end: `0x1800cfc1c`
- name: `?Watch@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `636`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ce9f0`

## callees

- `0x180008570`
- `0x1800295dc`
- `0x1800ca5fc`
- `0x1800cf9a0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfa3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfa7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfa3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfa7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cf9d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cf9d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf9e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf9e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cfa86`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cfa86`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800cfa62`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800cfa62`

## string_xrefs

- `0x1800cfbc5`: `m_threadRunningEvent not initialized [%#x]`
- `0x1800cfb08`: `Max lifetime process commit %zu bytes`
- `0x1800cfb8b`: `Avg lifetime process commit %zu bytes`
- `0x1800cfa20`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfaf0`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfb15`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfb6d`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfb98`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfbb4`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800cfbf8`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::InventoryWatchdog::Watch(RTL_SRWLOCK *this)
{
  PVOID Ptr; // rcx
  char v3; // si
  DWORD v4; // ebp
  DWORD v5; // eax
  void (*v6)(void); // rax
  __int64 v7; // rcx
  float v8; // xmm1_4
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // r8
  DWORD LastError; // [rsp+20h] [rbp-38h]
  HANDLE Handles[5]; // [rsp+30h] [rbp-28h] BYREF
  RTL_SRWLOCK *v14; // [rsp+60h] [rbp+8h] BYREF

  if ( !this[5].Ptr )
  {
    v10 = "m_stillAliveEvent not initialized [%#x]";
    v11 = 256;
    goto LABEL_26;
  }
  if ( !this[6].Ptr )
  {
    v10 = "m_shutdownEvent not initialized [%#x]";
    v11 = 262;
    goto LABEL_26;
  }
  Ptr = this[7].Ptr;
  if ( !Ptr )
  {
    v10 = "m_threadRunningEvent not initialized [%#x]";
    v11 = 268;
LABEL_26:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", v11, v10, -2147418113);
    return;
  }
  if ( !SetEvent(Ptr) )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 274, "SetEvent failed [%d]", LastError);
    return;
  }
  Handles[0] = this[5].Ptr;
  Handles[1] = this[6].Ptr;
  v3 = 0;
  AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 283, "Starting InventoryWatchdog...");
  do
  {
    AcquireSRWLockExclusive(this + 3);
    v14 = this + 3;
    v4 = (DWORD)this->Ptr;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
    v5 = WaitForMultipleObjects(2u, Handles, 0, v4);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 == 258 )
    {
      AcquireSRWLockExclusive(this + 3);
      v14 = this + 3;
      if ( IsDebuggerPresent() || v4 < LODWORD(this->Ptr) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
        goto LABEL_16;
      }
      v6 = Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction;
      if ( this[1].Ptr )
        v6 = (void (*)(void))this[1].Ptr;
      v6();
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
    }
    v3 = 1;
LABEL_16:
    Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage((Windows::Compat::Inventory::InventoryWatchdog *)this);
  }
  while ( !v3 );
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InventoryWatchdog::Watch",
    334,
    "Max lifetime process CPU %f%%",
    *((float *)&this[12].Ptr + 1));
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InventoryWatchdog::Watch",
    335,
    "Max lifetime process commit %zu bytes",
    this[9].Ptr);
  v7 = (__int64)this[11].Ptr;
  if ( v7 )
  {
    if ( v7 < 0 )
    {
      v9 = (__int64)this[11].Ptr & 1 | ((unsigned __int64)v7 >> 1);
      v8 = (float)(int)v9 + (float)(int)v9;
    }
    else
    {
      v8 = (float)(int)v7;
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InventoryWatchdog::Watch",
      338,
      "Avg lifetime process CPU %f%%",
      (float)(*(float *)&this[13].Ptr / v8));
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InventoryWatchdog::Watch",
      339,
      "Avg lifetime process commit %zu bytes",
      (unsigned __int64)this[10].Ptr / (unsigned __int64)this[11].Ptr);
  }
  AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 343, "Stopping InventoryWatchdog.");
}

```

## disassembly

```asm
0x1800cf9a0  mov     [rsp+arg_8], rbx
0x1800cf9a5  mov     [rsp+arg_10], rbp
0x1800cf9aa  push    rsi
0x1800cf9ab  push    rdi
0x1800cf9ac  push    r15
0x1800cf9ae  sub     rsp, 40h
0x1800cf9b2  mov     rbx, rcx
0x1800cf9b5  cmp     qword ptr [rcx+28h], 0
0x1800cf9ba  jz      loc_1800CFBE3
0x1800cf9c0  cmp     qword ptr [rcx+30h], 0
0x1800cf9c5  jz      loc_1800CFBD4
0x1800cf9cb  mov     rcx, [rcx+38h]; hEvent
0x1800cf9cf  test    rcx, rcx
0x1800cf9d2  jz      loc_1800CFBC5
0x1800cf9d8  call    cs:__imp_SetEvent
0x1800cf9de  test    eax, eax
0x1800cf9e0  jnz     short loc_1800CF9FE
0x1800cf9e2  call    cs:__imp_GetLastError
0x1800cf9e8  mov     [rsp+58h+var_38], eax
0x1800cf9ec  lea     r9, aSeteventFailed; "SetEvent failed [%d]"
0x1800cf9f3  mov     r8d, 112h
0x1800cf9f9  jmp     loc_1800CFBF8
0x1800cf9fe  mov     rax, [rbx+28h]
0x1800cfa02  mov     [rsp+58h+Handles], rax
0x1800cfa07  mov     rax, [rbx+30h]
0x1800cfa0b  mov     [rsp+58h+var_20], rax
0x1800cfa10  xor     sil, sil
0x1800cfa13  lea     r9, aStartingInvent; "Starting InventoryWatchdog..."
0x1800cfa1a  mov     r8d, 11Bh
0x1800cfa20  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfa27  mov     r15d, 3
0x1800cfa2d  mov     ecx, r15d
0x1800cfa30  call    AslLogCallPrintf
0x1800cfa35  lea     rdi, [rbx+18h]
0x1800cfa39  mov     rcx, rdi; SRWLock
0x1800cfa3c  call    cs:__imp_AcquireSRWLockExclusive
0x1800cfa42  mov     [rsp+58h+arg_0], rdi
0x1800cfa47  mov     ebp, [rbx]
0x1800cfa49  lea     rcx, [rsp+58h+arg_0]
0x1800cfa4e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cfa53  mov     r9d, ebp; dwMilliseconds
0x1800cfa56  xor     r8d, r8d; bWaitAll
0x1800cfa59  lea     rdx, [rsp+58h+Handles]; lpHandles
0x1800cfa5e  lea     ecx, [r8+2]; nCount
0x1800cfa62  call    cs:__imp_WaitForMultipleObjects
0x1800cfa68  test    eax, eax
0x1800cfa6a  jz      short loc_1800CFAC4
0x1800cfa6c  sub     eax, 1
0x1800cfa6f  jz      short loc_1800CFAC1
0x1800cfa71  cmp     eax, 101h
0x1800cfa76  jnz     short loc_1800CFAC1
0x1800cfa78  mov     rcx, rdi; SRWLock
0x1800cfa7b  call    cs:__imp_AcquireSRWLockExclusive
0x1800cfa81  mov     [rsp+58h+arg_0], rdi
0x1800cfa86  call    cs:__imp_IsDebuggerPresent
0x1800cfa8c  test    eax, eax
0x1800cfa8e  jz      short loc_1800CFA9C
0x1800cfa90  lea     rcx, [rsp+58h+arg_0]
0x1800cfa95  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cfa9a  jmp     short loc_1800CFAC4
0x1800cfa9c  cmp     ebp, [rbx]
0x1800cfa9e  jb      short loc_1800CFA90
0x1800cfaa0  lea     rax, ?DefaultTimeoutAction@InventoryWatchdog@Inventory@Compat@Windows@@CAXXZ; Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction(void)
0x1800cfaa7  cmp     qword ptr [rbx+8], 0
0x1800cfaac  cmovnz  rax, [rbx+8]
0x1800cfab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfab6  nop
0x1800cfab7  lea     rcx, [rsp+58h+arg_0]
0x1800cfabc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cfac1  mov     sil, 1
0x1800cfac4  mov     rcx, rbx; this
0x1800cfac7  call    ?CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)
0x1800cfacc  test    sil, sil
0x1800cfacf  jz      loc_1800CFA39
0x1800cfad5  movss   xmm0, dword ptr [rbx+64h]
0x1800cfada  cvtps2pd xmm0, xmm0
0x1800cfadd  movsd   qword ptr [rsp+58h+var_38], xmm0
0x1800cfae3  lea     r9, aMaxLifetimePro_0; "Max lifetime process CPU %f%%"
0x1800cfaea  mov     r8d, 14Eh
0x1800cfaf0  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfaf7  mov     ecx, r15d
0x1800cfafa  call    AslLogCallPrintf
0x1800cfaff  mov     rax, [rbx+48h]
0x1800cfb03  mov     qword ptr [rsp+58h+var_38], rax
0x1800cfb08  lea     r9, aMaxLifetimePro; "Max lifetime process commit %zu bytes"
0x1800cfb0f  mov     r8d, 14Fh
0x1800cfb15  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfb1c  mov     ecx, r15d
0x1800cfb1f  call    AslLogCallPrintf
0x1800cfb24  mov     rcx, [rbx+58h]
0x1800cfb28  test    rcx, rcx
0x1800cfb2b  jz      short loc_1800CFBA7
0x1800cfb2d  xorps   xmm1, xmm1
0x1800cfb30  js      short loc_1800CFB39
0x1800cfb32  cvtsi2ss xmm1, rcx
0x1800cfb37  jmp     short loc_1800CFB4E
0x1800cfb39  mov     rax, rcx
0x1800cfb3c  shr     rax, 1
0x1800cfb3f  and     ecx, 1
0x1800cfb42  or      rax, rcx
0x1800cfb45  cvtsi2ss xmm1, rax
0x1800cfb4a  addss   xmm1, xmm1
0x1800cfb4e  movss   xmm0, dword ptr [rbx+68h]
0x1800cfb53  divss   xmm0, xmm1
0x1800cfb57  cvtps2pd xmm0, xmm0
0x1800cfb5a  movsd   qword ptr [rsp+58h+var_38], xmm0
0x1800cfb60  lea     r9, aAvgLifetimePro; "Avg lifetime process CPU %f%%"
0x1800cfb67  mov     r8d, 152h
0x1800cfb6d  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfb74  mov     ecx, r15d
0x1800cfb77  call    AslLogCallPrintf
0x1800cfb7c  xor     edx, edx
0x1800cfb7e  mov     rax, [rbx+50h]
0x1800cfb82  div     qword ptr [rbx+58h]
0x1800cfb86  mov     qword ptr [rsp+58h+var_38], rax
0x1800cfb8b  lea     r9, aAvgLifetimePro_0; "Avg lifetime process commit %zu bytes"
0x1800cfb92  mov     r8d, 153h
0x1800cfb98  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfb9f  mov     ecx, r15d
0x1800cfba2  call    AslLogCallPrintf
0x1800cfba7  lea     r9, aStoppingInvent; "Stopping InventoryWatchdog."
0x1800cfbae  mov     r8d, 157h
0x1800cfbb4  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfbbb  mov     ecx, r15d
0x1800cfbbe  call    AslLogCallPrintf
0x1800cfbc3  jmp     short loc_1800CFC09
0x1800cfbc5  lea     r9, aMThreadrunning; "m_threadRunningEvent not initialized [%"...
0x1800cfbcc  mov     r8d, 10Ch
0x1800cfbd2  jmp     short loc_1800CFBF0
0x1800cfbd4  lea     r9, aMShutdownevent; "m_shutdownEvent not initialized [%#x]"
0x1800cfbdb  mov     r8d, 106h
0x1800cfbe1  jmp     short loc_1800CFBF0
0x1800cfbe3  lea     r9, aMStillaliveeve; "m_stillAliveEvent not initialized [%#x]"
0x1800cfbea  mov     r8d, 100h
0x1800cfbf0  mov     [rsp+58h+var_38], 8000FFFFh
0x1800cfbf8  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800cfbff  mov     ecx, 1
0x1800cfc04  call    AslLogCallPrintf
0x1800cfc09  mov     rbx, [rsp+58h+arg_8]
0x1800cfc0e  mov     rbp, [rsp+58h+arg_10]
0x1800cfc13  add     rsp, 40h
0x1800cfc17  pop     r15
0x1800cfc19  pop     rdi
0x1800cfc1a  pop     rsi
0x1800cfc1b  retn
```
