# Windows::Compat::Inventory::InventoryWatchdog::Watch(void)

- ea: `0x1800297c8`
- end: `0x180029a4e`
- name: `?Watch@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `646`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066ba0`

## callees

- `0x1800197d4`
- `0x1800297c8`
- `0x180029a54`
- `0x18004869c`
- `0x180130010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800298b6`
- `KERNEL32!IsDebuggerPresent` at `0x1800298b6`
- `KERNEL32!WaitForMultipleObjects` at `0x180029892`
- `KERNEL32!WaitForMultipleObjects` at `0x180029892`
- `KERNEL32!SetEvent` at `0x180029809`
- `KERNEL32!SetEvent` at `0x180029809`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002986d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800298ab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002986d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800298ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002987d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002987d`
- `KERNEL32!GetLastError` at `0x180029813`
- `KERNEL32!GetLastError` at `0x180029813`

## string_xrefs

- `0x180029851`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180029920`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180029945`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x18002999d`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800299c8`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800299e4`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180029a28`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180029938`: `Max lifetime process commit %zu bytes`
- `0x1800299f5`: `m_threadRunningEvent not initialized [%#x]`
- `0x1800299bb`: `Avg lifetime process commit %zu bytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::InventoryWatchdog::Watch(RTL_SRWLOCK *this)
{
  PVOID Ptr; // rcx
  const char *v3; // r9
  int v4; // r8d
  char v5; // bp
  DWORD v6; // esi
  DWORD v7; // eax
  void (*v8)(void); // rax
  HANDLE Handles[3]; // [rsp+38h] [rbp-30h] BYREF
  RTL_SRWLOCK *v10; // [rsp+70h] [rbp+8h] BYREF

  if ( !this[5].Ptr )
  {
    v3 = "m_stillAliveEvent not initialized [%#x]";
    v4 = 256;
    goto LABEL_25;
  }
  if ( !this[6].Ptr )
  {
    v3 = "m_shutdownEvent not initialized [%#x]";
    v4 = 262;
    goto LABEL_25;
  }
  Ptr = this[7].Ptr;
  if ( !Ptr )
  {
    v3 = "m_threadRunningEvent not initialized [%#x]";
    v4 = 268;
    goto LABEL_25;
  }
  if ( !SetEvent(Ptr) )
  {
    GetLastError();
    v3 = "SetEvent failed [%d]";
    v4 = 274;
LABEL_25:
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch", v4, (_DWORD)v3);
    return;
  }
  Handles[0] = this[5].Ptr;
  Handles[1] = this[6].Ptr;
  v5 = 0;
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
    283,
    (unsigned int)"Starting InventoryWatchdog...");
  do
  {
    AcquireSRWLockExclusive(this + 3);
    v6 = (DWORD)this->Ptr;
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockExclusive(this + 3);
    v7 = WaitForMultipleObjects(2u, Handles, 0, v6);
    if ( v7 )
    {
      if ( v7 == 258 )
      {
        AcquireSRWLockExclusive(this + 3);
        v10 = this + 3;
        if ( IsDebuggerPresent() || v6 < LODWORD(this->Ptr) )
        {
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
          goto LABEL_18;
        }
        v8 = Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction;
        if ( this[1].Ptr )
          v8 = (void (*)(void))this[1].Ptr;
        v8();
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
      }
      v5 = 1;
    }
LABEL_18:
    Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage((Windows::Compat::Inventory::InventoryWatchdog *)this);
  }
  while ( !v5 );
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
    334,
    (unsigned int)"Max lifetime process CPU %f%%");
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
    335,
    (unsigned int)"Max lifetime process commit %zu bytes");
  if ( this[11].Ptr )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
      338,
      (unsigned int)"Avg lifetime process CPU %f%%");
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
      339,
      (unsigned int)"Avg lifetime process commit %zu bytes");
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Watch",
    343,
    (unsigned int)"Stopping InventoryWatchdog.");
}

```

## disassembly

```asm
0x1800297c8  mov     rax, rsp
0x1800297cb  push    rsi
0x1800297cc  push    rdi
0x1800297cd  push    r15
0x1800297cf  sub     rsp, 50h
0x1800297d3  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800297db  mov     [rax+10h], rbx
0x1800297df  mov     [rax+18h], rbp
0x1800297e3  mov     rbx, rcx
0x1800297e6  cmp     qword ptr [rcx+28h], 0
0x1800297eb  jz      loc_180029A13
0x1800297f1  cmp     qword ptr [rcx+30h], 0
0x1800297f6  jz      loc_180029A04
0x1800297fc  mov     rcx, [rcx+38h]; hEvent
0x180029800  test    rcx, rcx
0x180029803  jz      loc_1800299F5
0x180029809  call    cs:__imp_SetEvent
0x18002980f  test    eax, eax
0x180029811  jnz     short loc_18002982F
0x180029813  call    cs:__imp_GetLastError
0x180029819  mov     dword ptr [rsp+68h+var_48], eax
0x18002981d  lea     r9, aSeteventFailed; "SetEvent failed [%d]"
0x180029824  mov     r8d, 112h
0x18002982a  jmp     loc_180029A28
0x18002982f  mov     rax, [rbx+28h]
0x180029833  mov     [rsp+68h+Handles], rax
0x180029838  mov     rax, [rbx+30h]
0x18002983c  mov     [rsp+68h+var_28], rax
0x180029841  xor     bpl, bpl
0x180029844  lea     r9, aStartingInvent; "Starting InventoryWatchdog..."
0x18002984b  mov     r8d, 11Bh
0x180029851  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x180029858  mov     r15d, 3
0x18002985e  mov     ecx, r15d
0x180029861  call    AslLogCallPrintf
0x180029866  lea     rdi, [rbx+18h]
0x18002986a  mov     rcx, rdi; SRWLock
0x18002986d  call    cs:__imp_AcquireSRWLockExclusive
0x180029873  mov     esi, [rbx]
0x180029875  test    rdi, rdi
0x180029878  jz      short loc_180029883
0x18002987a  mov     rcx, rdi; SRWLock
0x18002987d  call    cs:__imp_ReleaseSRWLockExclusive
0x180029883  mov     r9d, esi; dwMilliseconds
0x180029886  xor     r8d, r8d; bWaitAll
0x180029889  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18002988e  lea     ecx, [r8+2]; nCount
0x180029892  call    cs:__imp_WaitForMultipleObjects
0x180029898  test    eax, eax
0x18002989a  jz      short loc_1800298F4
0x18002989c  sub     eax, 1
0x18002989f  jz      short loc_1800298F1
0x1800298a1  cmp     eax, 101h
0x1800298a6  jnz     short loc_1800298F1
0x1800298a8  mov     rcx, rdi; SRWLock
0x1800298ab  call    cs:__imp_AcquireSRWLockExclusive
0x1800298b1  mov     [rsp+68h+arg_0], rdi
0x1800298b6  call    cs:__imp_IsDebuggerPresent
0x1800298bc  test    eax, eax
0x1800298be  jz      short loc_1800298CC
0x1800298c0  lea     rcx, [rsp+68h+arg_0]
0x1800298c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800298ca  jmp     short loc_1800298F4
0x1800298cc  cmp     esi, [rbx]
0x1800298ce  jb      short loc_1800298C0
0x1800298d0  lea     rax, ?DefaultTimeoutAction@InventoryWatchdog@Inventory@Compat@Windows@@CAXXZ; Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction(void)
0x1800298d7  cmp     qword ptr [rbx+8], 0
0x1800298dc  cmovnz  rax, [rbx+8]
0x1800298e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298e6  nop
0x1800298e7  lea     rcx, [rsp+68h+arg_0]
0x1800298ec  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800298f1  mov     bpl, 1
0x1800298f4  mov     rcx, rbx; this
0x1800298f7  call    ?CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)
0x1800298fc  test    bpl, bpl
0x1800298ff  jz      loc_18002986A
0x180029905  movss   xmm0, dword ptr [rbx+64h]
0x18002990a  cvtps2pd xmm0, xmm0
0x18002990d  movsd   [rsp+68h+var_48], xmm0
0x180029913  lea     r9, aMaxLifetimePro_0; "Max lifetime process CPU %f%%"
0x18002991a  mov     r8d, 14Eh
0x180029920  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x180029927  mov     ecx, r15d
0x18002992a  call    AslLogCallPrintf
0x18002992f  mov     rax, [rbx+48h]
0x180029933  mov     [rsp+68h+var_48], rax
0x180029938  lea     r9, aMaxLifetimePro; "Max lifetime process commit %zu bytes"
0x18002993f  mov     r8d, 14Fh
0x180029945  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x18002994c  mov     ecx, r15d
0x18002994f  call    AslLogCallPrintf
0x180029954  mov     rcx, [rbx+58h]
0x180029958  test    rcx, rcx
0x18002995b  jz      short loc_1800299D7
0x18002995d  xorps   xmm1, xmm1
0x180029960  js      short loc_180029969
0x180029962  cvtsi2ss xmm1, rcx
0x180029967  jmp     short loc_18002997E
0x180029969  mov     rax, rcx
0x18002996c  shr     rax, 1
0x18002996f  and     ecx, 1
0x180029972  or      rax, rcx
0x180029975  cvtsi2ss xmm1, rax
0x18002997a  addss   xmm1, xmm1
0x18002997e  movss   xmm0, dword ptr [rbx+68h]
0x180029983  divss   xmm0, xmm1
0x180029987  cvtps2pd xmm0, xmm0
0x18002998a  movsd   [rsp+68h+var_48], xmm0
0x180029990  lea     r9, aAvgLifetimePro; "Avg lifetime process CPU %f%%"
0x180029997  mov     r8d, 152h
0x18002999d  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800299a4  mov     ecx, r15d
0x1800299a7  call    AslLogCallPrintf
0x1800299ac  xor     edx, edx
0x1800299ae  mov     rax, [rbx+50h]
0x1800299b2  div     qword ptr [rbx+58h]
0x1800299b6  mov     [rsp+68h+var_48], rax
0x1800299bb  lea     r9, aAvgLifetimePro_0; "Avg lifetime process commit %zu bytes"
0x1800299c2  mov     r8d, 153h
0x1800299c8  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800299cf  mov     ecx, r15d
0x1800299d2  call    AslLogCallPrintf
0x1800299d7  lea     r9, aStoppingInvent; "Stopping InventoryWatchdog."
0x1800299de  mov     r8d, 157h
0x1800299e4  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x1800299eb  mov     ecx, r15d
0x1800299ee  call    AslLogCallPrintf
0x1800299f3  jmp     short loc_180029A39
0x1800299f5  lea     r9, aMThreadrunning; "m_threadRunningEvent not initialized [%"...
0x1800299fc  mov     r8d, 10Ch
0x180029a02  jmp     short loc_180029A20
0x180029a04  lea     r9, aMShutdownevent; "m_shutdownEvent not initialized [%#x]"
0x180029a0b  mov     r8d, 106h
0x180029a11  jmp     short loc_180029A20
0x180029a13  lea     r9, aMStillaliveeve; "m_stillAliveEvent not initialized [%#x]"
0x180029a1a  mov     r8d, 100h
0x180029a20  mov     dword ptr [rsp+68h+var_48], 8000FFFFh
0x180029a28  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::InventoryWa"...
0x180029a2f  mov     ecx, 1
0x180029a34  call    AslLogCallPrintf
0x180029a39  lea     r11, [rsp+68h+var_18]
0x180029a3e  mov     rbx, [r11+28h]
0x180029a42  mov     rbp, [r11+30h]
0x180029a46  mov     rsp, r11
0x180029a49  pop     r15
0x180029a4b  pop     rdi
0x180029a4c  pop     rsi
0x180029a4d  retn
```
