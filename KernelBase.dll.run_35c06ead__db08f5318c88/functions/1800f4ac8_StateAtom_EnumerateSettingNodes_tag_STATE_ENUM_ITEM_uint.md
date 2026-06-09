# StateAtom::EnumerateSettingNodes(tag_STATE_ENUM_ITEM *,uint *)

- ea: `0x1800f4ac8`
- end: `0x1800f4d30`
- name: `?EnumerateSettingNodes@StateAtom@@QEBAJPEAUtag_STATE_ENUM_ITEM@@PEAI@Z`
- size: `616`
- prototype: `__int64 __fastcall(StateAtom *__hidden this, struct tag_STATE_ENUM_ITEM *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800f4a14`

## callees

- `0x180056554`
- `0x1800f4ac8`
- `0x1800f4d38`
- `0x1800f4f50`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800f4bc8`
- `ntdll!RtlDeleteCriticalSection` at `0x1800f4c61`
- `ntdll!RtlDeleteCriticalSection` at `0x1800f4d0b`
- `ntdll!RtlDeleteCriticalSection` at `0x1800f4bc8`
- `ntdll!RtlDeleteCriticalSection` at `0x1800f4c61`
- `ntdll!RtlDeleteCriticalSection` at `0x1800f4d0b`
- `ntdll!RtlInitializeCriticalSection` at `0x1800f4b68`
- `ntdll!RtlInitializeCriticalSection` at `0x1800f4b68`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4bad`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4c27`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4c46`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4cf0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4bad`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4c27`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4c46`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800f4cf0`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800f4b10`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800f4b10`
- `ntdll!RtlFreeHeap` at `0x1800f4be0`
- `ntdll!RtlFreeHeap` at `0x1800f4c79`
- `ntdll!RtlFreeHeap` at `0x1800f4d23`
- `ntdll!RtlFreeHeap` at `0x1800f4be0`
- `ntdll!RtlFreeHeap` at `0x1800f4c79`
- `ntdll!RtlFreeHeap` at `0x1800f4d23`
- `ntdll!RtlAllocateHeap` at `0x1800f4b2c`
- `ntdll!RtlAllocateHeap` at `0x1800f4b2c`

## string_xrefs

- `0x1800f4cd7`: `Create %u`

## pseudocode

```c
__int64 __fastcall StateAtom::EnumerateSettingNodes(StateAtom *this, struct tag_STATE_ENUM_ITEM *a2, unsigned int *a3)
{
  char *v5; // rbx
  int v6; // esi
  char *Heap; // rax
  char *v8; // rdi
  int v9; // esi
  int Item; // eax
  unsigned int v11; // edi
  unsigned int v12; // eax
  char *v13; // rcx
  char *v14; // rbx
  char *v16; // rbx
  char *v17; // rbx
  char *v18; // [rsp+28h] [rbp-18h]
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v22; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF

  v5 = (char *)this + 24;
  v19 = *((_QWORD *)this + 2);
  v20 = *((unsigned int *)this + 1);
  P = 0;
  v23 = 0;
  v22 = 0;
  RtlAcquireSRWLockShared((char *)this + 24);
  v6 = *a3;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
  v8 = Heap;
  if ( Heap )
  {
    *(_QWORD *)Heap = a2;
    *((_QWORD *)Heap + 1) = 0;
    *((_DWORD *)Heap + 4) = v6;
    *((_QWORD *)Heap + 3) = &v23;
    *((_QWORD *)Heap + 4) = &v22;
    *((_QWORD *)Heap + 5) = &v19;
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 48));
    v9 = 0;
  }
  else
  {
    LODWORD(v18) = v6;
    v9 = -2147024882;
    v8 = 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
      (const char *)0x8007000ELL,
      (int)"new %u",
      v18,
      v19,
      v20);
  }
  wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
    &P,
    v8);
  if ( v9 < 0 )
  {
    LODWORD(v18) = *a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\stateatom.cpp",
      (const char *)(unsigned int)v9,
      (int)"Create %u",
      v18);
    v13 = v5;
LABEL_7:
    RtlReleaseSRWLockShared(v13);
    v14 = (char *)P;
    P = 0;
    if ( v14 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    }
    return (unsigned int)v9;
  }
  do
  {
    Item = StateEnumerator<AtomSettingsItemFetcher>::EnumerateNextItem(P);
    v11 = Item;
  }
  while ( Item >= 0 );
  v9 = -2147024637;
  if ( Item != -2147024637 )
  {
    LODWORD(v18) = *a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\stateatom.cpp",
      (const char *)(unsigned int)Item,
      (int)"EnumerateNextItem %u",
      v18);
    RtlReleaseSRWLockShared(v5);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      0);
    return v11;
  }
  v12 = v23;
  v13 = v5;
  *a3 = v23;
  if ( !v12 )
    goto LABEL_7;
  if ( v22 )
  {
    RtlReleaseSRWLockShared(v5);
    v16 = (char *)P;
    P = 0;
    if ( v16 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v16 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    }
    return 2147942522LL;
  }
  else
  {
    RtlReleaseSRWLockShared(v5);
    v17 = (char *)P;
    P = 0;
    if ( v17 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v17 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800f4ac8  mov     [rsp-28h+arg_8], rbx
0x1800f4acd  push    rbp
0x1800f4ace  push    rsi
0x1800f4acf  push    rdi
0x1800f4ad0  push    r14
0x1800f4ad2  push    r15
0x1800f4ad4  mov     rbp, rsp
0x1800f4ad7  sub     rsp, 40h
0x1800f4adb  mov     r14, r8
0x1800f4ade  mov     r15, rdx
0x1800f4ae1  mov     rax, [rcx+10h]; __annotation("Debug", "TelemetryAssert", "bufferLength != NULL")
0x1800f4ae5  lea     rbx, [rcx+18h]
0x1800f4ae9  mov     [rbp+var_10], rax
0x1800f4aed  mov     eax, [rcx+4]
0x1800f4af0  mov     rcx, rbx
0x1800f4af3  mov     [rbp+var_8], eax
0x1800f4af6  mov     [rbp+var_4], 0
0x1800f4afd  mov     [rbp+P], 0
0x1800f4b05  mov     [rbp+arg_10], 0
0x1800f4b0c  mov     [rbp+arg_0], 0
0x1800f4b10  call    cs:__imp_RtlAcquireSRWLockShared
0x1800f4b16  mov     rcx, gs:60h
0x1800f4b1f  xor     edx, edx; Flags
0x1800f4b21  mov     esi, [r14]
0x1800f4b24  mov     rcx, [rcx+30h]; HeapHandle
0x1800f4b28  lea     r8d, [rdx+58h]; Size
0x1800f4b2c  call    cs:__imp_RtlAllocateHeap
0x1800f4b32  mov     rdi, rax
0x1800f4b35  test    rax, rax
0x1800f4b38  jz      loc_1800F4C89
0x1800f4b3e  mov     [rax], r15
0x1800f4b41  lea     rcx, [rdi+30h]; CriticalSection
0x1800f4b45  mov     qword ptr [rax+8], 0
0x1800f4b4d  mov     [rax+10h], esi
0x1800f4b50  lea     rax, [rbp+arg_10]
0x1800f4b54  mov     [rdi+18h], rax
0x1800f4b58  lea     rax, [rbp+arg_0]
0x1800f4b5c  mov     [rdi+20h], rax
0x1800f4b60  lea     rax, [rbp+var_10]
0x1800f4b64  mov     [rdi+28h], rax
0x1800f4b68  call    cs:__imp_RtlInitializeCriticalSection
0x1800f4b6e  xor     esi, esi
0x1800f4b70  mov     rdx, rdi
0x1800f4b73  lea     rcx, [rbp+P]
0x1800f4b77  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800f4b7c  test    esi, esi
0x1800f4b7e  js      loc_1800F4CBD
0x1800f4b84  mov     rcx, [rbp+P]; __annotation("Debug", "TelemetryAssert", "containerValueEnumerator.get() != NULL")
0x1800f4b88  call    ?EnumerateNextItem@?$StateEnumerator@VAtomSettingsItemFetcher@@@@QEAAJXZ; StateEnumerator<AtomSettingsItemFetcher>::EnumerateNextItem(void)
0x1800f4b8d  mov     edi, eax
0x1800f4b8f  test    eax, eax
0x1800f4b91  jns     short loc_1800F4B84
0x1800f4b93  mov     esi, 80070103h
0x1800f4b98  cmp     eax, esi
0x1800f4b9a  jnz     short loc_1800F4BF9
0x1800f4b9c  mov     eax, [rbp+arg_10]
0x1800f4b9f  mov     rcx, rbx
0x1800f4ba2  mov     [r14], eax
0x1800f4ba5  test    eax, eax
0x1800f4ba7  jnz     loc_1800F4C3C
0x1800f4bad  call    cs:__imp_RtlReleaseSRWLockShared
0x1800f4bb3  mov     rbx, [rbp+P]
0x1800f4bb7  mov     [rbp+P], 0
0x1800f4bbf  test    rbx, rbx
0x1800f4bc2  jz      short loc_1800F4BE6
0x1800f4bc4  lea     rcx, [rbx+30h]; CriticalSection
0x1800f4bc8  call    cs:__imp_RtlDeleteCriticalSection
0x1800f4bce  mov     rcx, gs:60h
0x1800f4bd7  mov     r8, rbx; P
0x1800f4bda  xor     edx, edx; Flags
0x1800f4bdc  mov     rcx, [rcx+30h]; HeapHandle
0x1800f4be0  call    cs:__imp_RtlFreeHeap
0x1800f4be6  mov     eax, esi
0x1800f4be8  mov     rbx, [rsp+40h+arg_8]
0x1800f4bed  add     rsp, 40h
0x1800f4bf1  pop     r15
0x1800f4bf3  pop     r14
0x1800f4bf5  pop     rdi
0x1800f4bf6  pop     rsi
0x1800f4bf7  pop     rbp
0x1800f4bf8  retn
0x1800f4bf9  mov     eax, [r14]
0x1800f4bfc  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\statemanager\\"...
0x1800f4c03  mov     rcx, [rbp+28h]; this
0x1800f4c07  mov     r9d, edi; char *
0x1800f4c0a  mov     dword ptr [rsp+40h+var_18], eax; char *
0x1800f4c0e  mov     edx, 2D4h; void *
0x1800f4c13  lea     rax, aEnumeratenexti; "EnumerateNextItem %u"
0x1800f4c1a  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800f4c1f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f4c24  mov     rcx, rbx
0x1800f4c27  call    cs:__imp_RtlReleaseSRWLockShared
0x1800f4c2d  xor     edx, edx
0x1800f4c2f  lea     rcx, [rbp+P]
0x1800f4c33  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800f4c38  mov     eax, edi
0x1800f4c3a  jmp     short loc_1800F4BE8
0x1800f4c3c  cmp     [rbp+arg_0], 0
0x1800f4c40  jz      loc_1800F4CF0
0x1800f4c46  call    cs:__imp_RtlReleaseSRWLockShared
0x1800f4c4c  mov     rbx, [rbp+P]
0x1800f4c50  mov     [rbp+P], 0
0x1800f4c58  test    rbx, rbx
0x1800f4c5b  jz      short loc_1800F4C7F
0x1800f4c5d  lea     rcx, [rbx+30h]; CriticalSection
0x1800f4c61  call    cs:__imp_RtlDeleteCriticalSection
0x1800f4c67  mov     rcx, gs:60h
0x1800f4c70  mov     r8, rbx; P
0x1800f4c73  xor     edx, edx; Flags
0x1800f4c75  mov     rcx, [rcx+30h]; HeapHandle
0x1800f4c79  call    cs:__imp_RtlFreeHeap
0x1800f4c7f  mov     eax, 8007007Ah
0x1800f4c84  jmp     loc_1800F4BE8
0x1800f4c89  mov     rcx, [rbp+28h]; this
0x1800f4c8d  lea     rax, aNewU; "new %u"
0x1800f4c94  mov     dword ptr [rsp+40h+var_18], esi; char *
0x1800f4c98  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x1800f4c9f  mov     esi, 8007000Eh
0x1800f4ca4  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800f4ca9  mov     r9d, esi; char *
0x1800f4cac  xor     edi, edi
0x1800f4cae  mov     edx, 0D9h; void *
0x1800f4cb3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f4cb8  jmp     loc_1800F4B70
0x1800f4cbd  mov     eax, [r14]
0x1800f4cc0  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\statemanager\\"...
0x1800f4cc7  mov     rcx, [rbp+28h]; this
0x1800f4ccb  mov     r9d, esi; char *
0x1800f4cce  mov     dword ptr [rsp+40h+var_18], eax; char *
0x1800f4cd2  mov     edx, 2B4h; void *
0x1800f4cd7  lea     rax, aCreateU; "Create %u"
0x1800f4cde  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800f4ce3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f4ce8  mov     rcx, rbx
0x1800f4ceb  jmp     loc_1800F4BAD
0x1800f4cf0  call    cs:__imp_RtlReleaseSRWLockShared
0x1800f4cf6  mov     rbx, [rbp+P]
0x1800f4cfa  mov     [rbp+P], 0
0x1800f4d02  test    rbx, rbx
0x1800f4d05  jz      short loc_1800F4D29
0x1800f4d07  lea     rcx, [rbx+30h]; CriticalSection
0x1800f4d0b  call    cs:__imp_RtlDeleteCriticalSection
0x1800f4d11  mov     rcx, gs:60h
0x1800f4d1a  mov     r8, rbx; P
0x1800f4d1d  xor     edx, edx; Flags
0x1800f4d1f  mov     rcx, [rcx+30h]; HeapHandle
0x1800f4d23  call    cs:__imp_RtlFreeHeap
0x1800f4d29  xor     eax, eax
0x1800f4d2b  jmp     loc_1800F4BE8
```
