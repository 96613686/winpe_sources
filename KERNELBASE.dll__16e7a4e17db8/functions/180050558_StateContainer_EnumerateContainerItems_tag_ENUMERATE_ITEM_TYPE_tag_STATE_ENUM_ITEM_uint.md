# StateContainer::EnumerateContainerItems(tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM *,uint *)

- ea: `0x180050558`
- end: `0x180050942`
- name: `?EnumerateContainerItems@StateContainer@@QEAAJW4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800f2e00`

## callees

- `0x180050558`
- `0x180050cc4`
- `0x180052484`
- `0x180056554`
- `0x1800f4f50`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180050641`
- `ntdll!RtlDeleteCriticalSection` at `0x180050670`
- `ntdll!RtlDeleteCriticalSection` at `0x18005074a`
- `ntdll!RtlDeleteCriticalSection` at `0x180050779`
- `ntdll!RtlDeleteCriticalSection` at `0x1800507cf`
- `ntdll!RtlDeleteCriticalSection` at `0x1800507fe`
- `ntdll!RtlDeleteCriticalSection` at `0x180050861`
- `ntdll!RtlDeleteCriticalSection` at `0x180050890`
- `ntdll!RtlDeleteCriticalSection` at `0x180050641`
- `ntdll!RtlDeleteCriticalSection` at `0x180050670`
- `ntdll!RtlDeleteCriticalSection` at `0x18005074a`
- `ntdll!RtlDeleteCriticalSection` at `0x180050779`
- `ntdll!RtlDeleteCriticalSection` at `0x1800507cf`
- `ntdll!RtlDeleteCriticalSection` at `0x1800507fe`
- `ntdll!RtlDeleteCriticalSection` at `0x180050861`
- `ntdll!RtlDeleteCriticalSection` at `0x180050890`
- `ntdll!RtlInitializeCriticalSection` at `0x1800505ef`
- `ntdll!RtlInitializeCriticalSection` at `0x1800506e8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800505ef`
- `ntdll!RtlInitializeCriticalSection` at `0x1800506e8`
- `ntdll!RtlFreeHeap` at `0x180050659`
- `ntdll!RtlFreeHeap` at `0x180050688`
- `ntdll!RtlFreeHeap` at `0x180050762`
- `ntdll!RtlFreeHeap` at `0x180050791`
- `ntdll!RtlFreeHeap` at `0x1800507e7`
- `ntdll!RtlFreeHeap` at `0x180050816`
- `ntdll!RtlFreeHeap` at `0x180050879`
- `ntdll!RtlFreeHeap` at `0x1800508a8`
- `ntdll!RtlFreeHeap` at `0x180050659`
- `ntdll!RtlFreeHeap` at `0x180050688`
- `ntdll!RtlFreeHeap` at `0x180050762`
- `ntdll!RtlFreeHeap` at `0x180050791`
- `ntdll!RtlFreeHeap` at `0x1800507e7`
- `ntdll!RtlFreeHeap` at `0x180050816`
- `ntdll!RtlFreeHeap` at `0x180050879`
- `ntdll!RtlFreeHeap` at `0x1800508a8`
- `ntdll!RtlAllocateHeap` at `0x1800505b7`
- `ntdll!RtlAllocateHeap` at `0x1800506b0`
- `ntdll!RtlAllocateHeap` at `0x1800505b7`
- `ntdll!RtlAllocateHeap` at `0x1800506b0`

## string_xrefs

- `0x18005060c`: `Create RegKeyItemFetcher`
- `0x180050931`: `Create RegValueItemFetcher`

## pseudocode

```c
__int64 __fastcall StateContainer::EnumerateContainerItems(__int64 *a1, int a2, __int64 a3, int *a4)
{
  __int64 v7; // rax
  int v8; // ebx
  char *Heap; // rax
  char *v10; // rdi
  int Item; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  char *v14; // rdi
  char *v15; // rdi
  char *v17; // rax
  char *v18; // rdi
  int v19; // eax
  char *v20; // rbx
  char *v21; // rbx
  char *v22; // rbx
  char *v23; // rbx
  char *v24; // [rsp+28h] [rbp-28h]
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  PVOID v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  int v28; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char v30; // [rsp+88h] [rbp+38h] BYREF
  int v31; // [rsp+98h] [rbp+48h] BYREF

  v7 = *a1;
  v8 = *a4;
  v26 = 0;
  P = 0;
  v31 = 0;
  v30 = 0;
  if ( a2 == 1 )
  {
    v27 = v7;
    v28 = 0;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
    v10 = Heap;
    if ( Heap )
    {
      *(_QWORD *)Heap = a3;
      *((_QWORD *)Heap + 1) = 0;
      *((_DWORD *)Heap + 4) = v8;
      *((_QWORD *)Heap + 3) = &v31;
      *((_QWORD *)Heap + 4) = &v30;
      *((_QWORD *)Heap + 5) = &v27;
      RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 48));
      Item = 0;
    }
    else
    {
      LODWORD(v24) = v8;
      Item = -2147024882;
      v10 = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
        (const char *)0x8007000ELL,
        (int)"new %u",
        v24);
    }
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &v26,
      v10);
    if ( Item < 0 )
    {
      v12 = "Create RegKeyItemFetcher";
      v13 = 312;
LABEL_6:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statecontainer.cpp",
        (const char *)(unsigned int)Item,
        (int)v12,
        v24);
      v14 = (char *)P;
      P = 0;
      if ( v14 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      }
      v15 = (char *)v26;
      v26 = 0;
      if ( v15 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v15 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      }
      return (unsigned int)Item;
    }
    do
      Item = StateEnumerator<RegKeyItemFetcher>::EnumerateNextItem(v26);
    while ( Item >= 0 );
  }
  else
  {
    v27 = v7;
    v28 = 0;
    v17 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
    v18 = v17;
    if ( v17 )
    {
      *(_QWORD *)v17 = a3;
      *((_QWORD *)v17 + 1) = 0;
      *((_DWORD *)v17 + 4) = v8;
      *((_QWORD *)v17 + 3) = &v31;
      *((_QWORD *)v17 + 4) = &v30;
      *((_QWORD *)v17 + 5) = &v27;
      RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v17 + 48));
      Item = 0;
    }
    else
    {
      LODWORD(v24) = v8;
      Item = -2147024882;
      v18 = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
        (const char *)0x8007000ELL,
        (int)"new %u",
        v24);
    }
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      v18);
    if ( Item < 0 )
    {
      v12 = "Create RegValueItemFetcher";
      v13 = 335;
      goto LABEL_6;
    }
    do
      Item = StateEnumerator<RegValueItemFetcher>::EnumerateNextItem(P);
    while ( Item >= 0 );
  }
  if ( Item != -2147024637 )
  {
    LODWORD(v24) = a2;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statecontainer.cpp",
      (const char *)(unsigned int)Item,
      (int)"Type %u",
      v24);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      0);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &v26,
      0);
    return (unsigned int)Item;
  }
  v19 = v31;
  v20 = (char *)P;
  *a4 = v31;
  P = 0;
  if ( v19 )
  {
    if ( v30 )
    {
      if ( v20 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      }
      v23 = (char *)v26;
      v26 = 0;
      if ( v23 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v23 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      }
      return 2147942522LL;
    }
    else
    {
      if ( v20 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      }
      v21 = (char *)v26;
      v26 = 0;
      if ( v21 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v21 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      }
      return 0;
    }
  }
  else
  {
    if ( v20 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    }
    v22 = (char *)v26;
    v26 = 0;
    if ( v22 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v22 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
    }
    return 2147942659LL;
  }
}

```

## disassembly

```asm
0x180050558  mov     [rsp-28h+arg_0], rbx
0x18005055d  mov     [rsp-28h+arg_10], rsi
0x180050562  push    rbp
0x180050563  push    rdi
0x180050564  push    r12
0x180050566  push    r14
0x180050568  push    r15
0x18005056a  mov     rbp, rsp
0x18005056d  sub     rsp, 50h
0x180050571  mov     r14, r9
0x180050574  mov     rsi, r8
0x180050577  mov     r15d, edx
0x18005057a  mov     rax, [rcx]; __annotation("Debug", "TelemetryAssert", "enumerateItemType > ENUMERATE_ITEM_UNDEFINED && enumerateItemType < ENUMERATE_ITEM_LAST")
0x18005057d  xor     r12d, r12d
0x180050580  mov     ebx, [r9]
0x180050583  mov     [rbp+var_18], r12
0x180050587  mov     [rbp+P], r12
0x18005058b  mov     [rbp+arg_18], r12d
0x18005058f  mov     [rbp+arg_8], r12b
0x180050593  cmp     edx, 1
0x180050596  jnz     loc_180050695
0x18005059c  mov     [rbp+var_10], rax; __annotation("Debug", "TelemetryAssert", "containerKey != NULL")
0x1800505a0  lea     r8d, [r15+57h]; Size
0x1800505a4  mov     [rbp+var_8], r12d
0x1800505a8  xor     edx, edx; Flags
0x1800505aa  mov     rcx, gs:60h
0x1800505b3  mov     rcx, [rcx+30h]; HeapHandle
0x1800505b7  call    cs:__imp_RtlAllocateHeap
0x1800505bd  mov     rdi, rax
0x1800505c0  test    rax, rax
0x1800505c3  jz      loc_180050823
0x1800505c9  mov     [rax], rsi
0x1800505cc  lea     rcx, [rdi+30h]; CriticalSection
0x1800505d0  mov     [rax+8], r12
0x1800505d4  mov     [rax+10h], ebx
0x1800505d7  lea     rax, [rbp+arg_18]
0x1800505db  mov     [rdi+18h], rax
0x1800505df  lea     rax, [rbp+arg_8]
0x1800505e3  mov     [rdi+20h], rax
0x1800505e7  lea     rax, [rbp+var_10]
0x1800505eb  mov     [rdi+28h], rax
0x1800505ef  call    cs:__imp_RtlInitializeCriticalSection
0x1800505f5  mov     ebx, r12d
0x1800505f8  mov     rdx, rdi
0x1800505fb  lea     rcx, [rbp+var_18]
0x1800505ff  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x180050604  test    ebx, ebx
0x180050606  jns     loc_1800507B2
0x18005060c  lea     rax, aCreateRegkeyit; "Create RegKeyItemFetcher"
0x180050613  mov     edx, 138h; void *
0x180050618  mov     rcx, [rbp+28h]; this
0x18005061c  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\statemanager\\"...
0x180050623  mov     r9d, ebx; char *
0x180050626  mov     qword ptr [rsp+50h+var_30], rax; int
0x18005062b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050630  mov     rdi, [rbp+P]
0x180050634  mov     [rbp+P], r12
0x180050638  test    rdi, rdi
0x18005063b  jz      short loc_18005065F
0x18005063d  lea     rcx, [rdi+30h]; CriticalSection
0x180050641  call    cs:__imp_RtlDeleteCriticalSection
0x180050647  mov     rcx, gs:60h
0x180050650  mov     r8, rdi; P
0x180050653  xor     edx, edx; Flags
0x180050655  mov     rcx, [rcx+30h]; HeapHandle
0x180050659  call    cs:__imp_RtlFreeHeap
0x18005065f  mov     rdi, [rbp+var_18]
0x180050663  mov     [rbp+var_18], r12
0x180050667  test    rdi, rdi
0x18005066a  jz      short loc_18005068E
0x18005066c  lea     rcx, [rdi+30h]; CriticalSection
0x180050670  call    cs:__imp_RtlDeleteCriticalSection
0x180050676  mov     rcx, gs:60h
0x18005067f  mov     r8, rdi; P
0x180050682  xor     edx, edx; Flags
0x180050684  mov     rcx, [rcx+30h]; HeapHandle
0x180050688  call    cs:__imp_RtlFreeHeap
0x18005068e  mov     eax, ebx
0x180050690  jmp     loc_180050799
0x180050695  mov     [rbp+var_10], rax; __annotation("Debug", "TelemetryAssert", "containerKey != NULL")
0x180050699  xor     edx, edx; Flags
0x18005069b  mov     [rbp+var_8], r12d
0x18005069f  mov     rcx, gs:60h
0x1800506a8  lea     r8d, [rdx+58h]; Size
0x1800506ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800506b0  call    cs:__imp_RtlAllocateHeap
0x1800506b6  mov     rdi, rax
0x1800506b9  test    rax, rax
0x1800506bc  jz      loc_1800508B8
0x1800506c2  mov     [rax], rsi
0x1800506c5  lea     rcx, [rdi+30h]; CriticalSection
0x1800506c9  mov     [rax+8], r12
0x1800506cd  mov     [rax+10h], ebx
0x1800506d0  lea     rax, [rbp+arg_18]
0x1800506d4  mov     [rdi+18h], rax
0x1800506d8  lea     rax, [rbp+arg_8]
0x1800506dc  mov     [rdi+20h], rax
0x1800506e0  lea     rax, [rbp+var_10]
0x1800506e4  mov     [rdi+28h], rax
0x1800506e8  call    cs:__imp_RtlInitializeCriticalSection
0x1800506ee  mov     ebx, r12d
0x1800506f1  mov     rdx, rdi
0x1800506f4  lea     rcx, [rbp+P]
0x1800506f8  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800506fd  test    ebx, ebx
0x1800506ff  js      loc_180050931
0x180050705  mov     rcx, [rbp+P]; __annotation("Debug", "TelemetryAssert", "containerValueEnumerator != NULL")
0x180050709  call    ?EnumerateNextItem@?$StateEnumerator@VRegValueItemFetcher@@@@QEAAJXZ; StateEnumerator<RegValueItemFetcher>::EnumerateNextItem(void)
0x18005070e  mov     ebx, eax
0x180050710  test    eax, eax
0x180050712  jns     short loc_180050705
0x180050714  mov     edi, 80070103h
0x180050719  cmp     ebx, edi
0x18005071b  jnz     loc_1800508ED
0x180050721  mov     eax, [rbp+arg_18]
0x180050724  mov     rbx, [rbp+P]
0x180050728  mov     [r14], eax
0x18005072b  mov     [rbp+P], r12
0x18005072f  test    eax, eax
0x180050731  jz      loc_1800507C6
0x180050737  cmp     [rbp+arg_8], r12b
0x18005073b  jnz     loc_180050858
0x180050741  test    rbx, rbx
0x180050744  jz      short loc_180050768
0x180050746  lea     rcx, [rbx+30h]; CriticalSection
0x18005074a  call    cs:__imp_RtlDeleteCriticalSection
0x180050750  mov     rcx, gs:60h
0x180050759  mov     r8, rbx; P
0x18005075c  xor     edx, edx; Flags
0x18005075e  mov     rcx, [rcx+30h]; HeapHandle
0x180050762  call    cs:__imp_RtlFreeHeap
0x180050768  mov     rbx, [rbp+var_18]
0x18005076c  mov     [rbp+var_18], r12
0x180050770  test    rbx, rbx
0x180050773  jz      short loc_180050797
0x180050775  lea     rcx, [rbx+30h]; CriticalSection
0x180050779  call    cs:__imp_RtlDeleteCriticalSection
0x18005077f  mov     rcx, gs:60h
0x180050788  mov     r8, rbx; P
0x18005078b  xor     edx, edx; Flags
0x18005078d  mov     rcx, [rcx+30h]; HeapHandle
0x180050791  call    cs:__imp_RtlFreeHeap
0x180050797  xor     eax, eax
0x180050799  lea     r11, [rsp+50h+var_s0]
0x18005079e  mov     rbx, [r11+30h]
0x1800507a2  mov     rsi, [r11+40h]
0x1800507a6  mov     rsp, r11
0x1800507a9  pop     r15
0x1800507ab  pop     r14
0x1800507ad  pop     r12
0x1800507af  pop     rdi
0x1800507b0  pop     rbp
0x1800507b1  retn
0x1800507b2  mov     rcx, [rbp+var_18]; __annotation("Debug", "TelemetryAssert", "containerKeyEnumerator != NULL")
0x1800507b6  call    ?EnumerateNextItem@?$StateEnumerator@VRegKeyItemFetcher@@@@QEAAJXZ; StateEnumerator<RegKeyItemFetcher>::EnumerateNextItem(void)
0x1800507bb  mov     ebx, eax
0x1800507bd  test    eax, eax
0x1800507bf  jns     short loc_1800507B2
0x1800507c1  jmp     loc_180050714
0x1800507c6  test    rbx, rbx
0x1800507c9  jz      short loc_1800507ED
0x1800507cb  lea     rcx, [rbx+30h]; CriticalSection
0x1800507cf  call    cs:__imp_RtlDeleteCriticalSection
0x1800507d5  mov     rcx, gs:60h
0x1800507de  mov     r8, rbx; P
0x1800507e1  xor     edx, edx; Flags
0x1800507e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800507e7  call    cs:__imp_RtlFreeHeap
0x1800507ed  mov     rbx, [rbp+var_18]
0x1800507f1  mov     [rbp+var_18], r12
0x1800507f5  test    rbx, rbx
0x1800507f8  jz      short loc_18005081C
0x1800507fa  lea     rcx, [rbx+30h]; CriticalSection
0x1800507fe  call    cs:__imp_RtlDeleteCriticalSection
0x180050804  mov     rcx, gs:60h
0x18005080d  mov     r8, rbx; P
0x180050810  xor     edx, edx; Flags
0x180050812  mov     rcx, [rcx+30h]; HeapHandle
0x180050816  call    cs:__imp_RtlFreeHeap
0x18005081c  mov     eax, edi
0x18005081e  jmp     loc_180050799
0x180050823  mov     rcx, [rbp+28h]; this
0x180050827  lea     rax, aNewU; "new %u"
0x18005082e  mov     dword ptr [rsp+50h+var_28], ebx; char *
0x180050832  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x180050839  mov     ebx, 8007000Eh
0x18005083e  mov     qword ptr [rsp+50h+var_30], rax; int
0x180050843  mov     r9d, ebx; char *
0x180050846  mov     edx, 0D9h; void *
0x18005084b  mov     rdi, r12
0x18005084e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050853  jmp     loc_1800505F8
0x180050858  test    rbx, rbx
0x18005085b  jz      short loc_18005087F
0x18005085d  lea     rcx, [rbx+30h]; CriticalSection
0x180050861  call    cs:__imp_RtlDeleteCriticalSection
0x180050867  mov     rcx, gs:60h
0x180050870  mov     r8, rbx; P
0x180050873  xor     edx, edx; Flags
0x180050875  mov     rcx, [rcx+30h]; HeapHandle
0x180050879  call    cs:__imp_RtlFreeHeap
0x18005087f  mov     rbx, [rbp+var_18]
0x180050883  mov     [rbp+var_18], r12
0x180050887  test    rbx, rbx
0x18005088a  jz      short loc_1800508AE
0x18005088c  lea     rcx, [rbx+30h]; CriticalSection
0x180050890  call    cs:__imp_RtlDeleteCriticalSection
0x180050896  mov     rcx, gs:60h
0x18005089f  mov     r8, rbx; P
0x1800508a2  xor     edx, edx; Flags
0x1800508a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800508a8  call    cs:__imp_RtlFreeHeap
0x1800508ae  mov     eax, 8007007Ah
0x1800508b3  jmp     loc_180050799
0x1800508b8  mov     rcx, [rbp+28h]; this
0x1800508bc  lea     rax, aNewU; "new %u"
0x1800508c3  mov     dword ptr [rsp+50h+var_28], ebx; char *
0x1800508c7  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x1800508ce  mov     ebx, 8007000Eh
0x1800508d3  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800508d8  mov     r9d, ebx; char *
0x1800508db  mov     edx, 0D9h; void *
0x1800508e0  mov     rdi, r12
0x1800508e3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800508e8  jmp     loc_1800506F1
0x1800508ed  mov     rcx, [rbp+28h]; this
0x1800508f1  lea     rax, aTypeU; "Type %u"
0x1800508f8  mov     dword ptr [rsp+50h+var_28], r15d; char *
0x1800508fd  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\statemanager\\"...
0x180050904  mov     r9d, ebx; char *
0x180050907  mov     qword ptr [rsp+50h+var_30], rax; int
0x18005090c  mov     edx, 16Eh; void *
0x180050911  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050916  xor     edx, edx
0x180050918  lea     rcx, [rbp+P]
0x18005091c  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x180050921  xor     edx, edx
0x180050923  lea     rcx, [rbp+var_18]
0x180050927  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x18005092c  jmp     loc_18005068E
0x180050931  lea     rax, aCreateRegvalue; "Create RegValueItemFetcher"
0x180050938  mov     edx, 14Fh
0x18005093d  jmp     loc_180050618
```
