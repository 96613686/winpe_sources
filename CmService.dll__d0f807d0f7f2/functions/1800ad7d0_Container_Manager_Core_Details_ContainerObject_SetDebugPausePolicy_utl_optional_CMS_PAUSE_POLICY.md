# Container::Manager::Core::Details::ContainerObject::SetDebugPausePolicy(utl::optional<_CMS_PAUSE_POLICY>)

- ea: `0x1800ad7d0`
- end: `0x1800adb05`
- name: `?SetDebugPausePolicy@ContainerObject@Details@Core@Manager@Container@@QEAAJV?$optional@U_CMS_PAUSE_POLICY@@@utl@@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800232d0`

## callees

- `0x18000da88`
- `0x18000dad8`
- `0x18007a87c`
- `0x18007c61c`
- `0x1800ad7d0`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x1800ad9f0`
- `ntdll!RtlRbRemoveNode` at `0x1800ad9f0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ad94e`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ad94e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad7f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad85d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad7f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad85d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad8f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ada3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ada79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800adae5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad8f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ada3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ada79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800adae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad7fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad95a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad7fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad95a`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::SetDebugPausePolicy(__int64 a1, int *a2)
{
  __int64 v2; // rbx
  int v5; // edi
  char *v6; // r13
  __int64 v7; // rbp
  int v8; // edi
  __int64 v9; // r14
  int v10; // eax
  char v11; // r9
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // eax
  bool v17; // zf
  int v18; // eax
  unsigned int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a1 + 456;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
  *(_DWORD *)(v2 + 8) = GetCurrentThreadId();
  if ( (*(_BYTE *)(a1 + 92) & 0x10) != 0 )
  {
    v6 = (char *)(a2 + 6);
    if ( *(_DWORD *)(a1 + 88) != 1 )
    {
      if ( !*v6 )
        goto LABEL_37;
      if ( a2[2] )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1B1E,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
               (const char *)0x32,
               v20);
        goto LABEL_40;
      }
LABEL_32:
      if ( *v6 )
      {
        v18 = *a2;
        *(_BYTE *)(a1 + 1216) = 1;
        *(_DWORD *)(a1 + 1212) = v18;
LABEL_39:
        v5 = 0;
        goto LABEL_40;
      }
LABEL_37:
      if ( *(_BYTE *)(a1 + 1216) )
        *(_BYTE *)(a1 + 1216) = 0;
      goto LABEL_39;
    }
    v7 = *(_QWORD *)(a1 + 1384);
    v8 = *a2;
    v9 = *(_QWORD *)(a1 + 544);
    AcquireSRWLockExclusive((PSRWLOCK)v7);
    *(_DWORD *)(v7 + 8) = GetCurrentThreadId();
    if ( (*(_BYTE *)(v9 + 40) & 1) == 0 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2E8,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
              (const char *)0x139F,
              v20);
      goto LABEL_27;
    }
    v11 = *v6;
    if ( *v6 && (v12 = a2[2]) != 0 )
    {
      v13 = a2[1];
      if ( (v13 & 0xFFFFFFE0) != 0 )
      {
        v14 = 760;
LABEL_10:
        v5 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
          (const char *)0x80070057LL,
          v20);
        *(_DWORD *)(v7 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v7);
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B19,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v5,
          v21);
        goto LABEL_40;
      }
      if ( (v13 & 8) != 0 )
      {
        if ( (v13 & 4) == 0 )
        {
          v14 = 774;
          goto LABEL_10;
        }
        if ( (*(_BYTE *)(v9 + 40) & 2) == 0 )
        {
          v14 = 781;
          goto LABEL_10;
        }
      }
      if ( (v13 & 0xC) != 0 && (v13 & 0x10) != 0 )
      {
        v14 = 798;
        goto LABEL_10;
      }
      if ( *(_DWORD *)(v9 + 52) )
      {
        do
        {
          *(_DWORD *)(v7 + 8) = 0;
          SleepConditionVariableSRW((PCONDITION_VARIABLE)(v9 + 56), (PSRWLOCK)v7, 0xFFFFFFFF, 0);
          *(_DWORD *)(v7 + 8) = GetCurrentThreadId();
        }
        while ( *(_DWORD *)(v9 + 52) );
        v13 = a2[1];
        v12 = a2[2];
        v11 = *v6;
      }
      v15 = *(_DWORD *)(v9 + 48);
      if ( (v15 & v13) != v15 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x32F,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
                (const char *)0x139F,
                v20);
LABEL_27:
        *(_DWORD *)(v7 + 8) = 0;
        v5 = v10;
        ReleaseSRWLockExclusive((PSRWLOCK)v7);
        if ( v5 < 0 )
          goto LABEL_28;
        goto LABEL_32;
      }
      v16 = a2[5];
      *(_QWORD *)(v9 + 84) = *(_QWORD *)(a2 + 3);
      *(_DWORD *)(v9 + 92) = v16;
      *(_DWORD *)(v9 + 97) = *(int *)((char *)a2 + 25);
      *(_WORD *)(v9 + 101) = *(_WORD *)((char *)a2 + 29);
      *(_BYTE *)(v9 + 103) = *((_BYTE *)a2 + 31);
      *(_DWORD *)(v9 + 72) = v8;
      *(_DWORD *)(v9 + 76) = v13;
      *(_DWORD *)(v9 + 80) = v12;
      *(_BYTE *)(v9 + 96) = v11;
      if ( *(_DWORD *)(v9 + 44) )
      {
        v17 = *(_QWORD *)(v9 + 16) == -1;
        *(_DWORD *)(v9 + 44) = v13 & ~v15;
        if ( !v17 )
        {
          RtlRbRemoveNode(v7 + 56, v9);
          *(_QWORD *)(v9 + 16) = -1;
          Csl::IntrusivePriorityQueue<Container::Manager::Core::Details::ContainerMemoryContext,0,&private: static long Container::Manager::Core::Details::MemoryManager::CompareContainerMemoryContexts(Container::Manager::Core::Details::ContainerMemoryContext const &,Container::Manager::Core::Details::ContainerMemoryContext const &)>::Push(
            v7 + 56,
            v9);
        }
        Container::Manager::Core::Details::MemoryManager::CheckRemediationActionsAndSignalRemediationThread((Container::Manager::Core::Details::MemoryManager *)v7);
      }
    }
    else if ( *(_BYTE *)(v9 + 96) )
    {
      *(_BYTE *)(v9 + 96) = 0;
    }
    *(_DWORD *)(v7 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v7);
    goto LABEL_32;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1B11,
         (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
         (const char *)0x32,
         v20);
LABEL_40:
  *(_DWORD *)(v2 + 8) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ad7d0  push    rbx
0x1800ad7d2  push    rbp
0x1800ad7d3  push    rsi
0x1800ad7d4  push    rdi
0x1800ad7d5  push    r12
0x1800ad7d7  push    r13
0x1800ad7d9  push    r14
0x1800ad7db  push    r15
0x1800ad7dd  sub     rsp, 28h
0x1800ad7e1  lea     rbx, [rcx+1C8h]
0x1800ad7e8  mov     r15, rcx
0x1800ad7eb  mov     rcx, rbx; SRWLock
0x1800ad7ee  mov     r12, rdx
0x1800ad7f1  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad7f8  nop     dword ptr [rax+rax+00h]
0x1800ad7fd  call    cs:__imp_GetCurrentThreadId
0x1800ad804  nop     dword ptr [rax+rax+00h]
0x1800ad809  mov     [rbx+8], eax
0x1800ad80c  test    byte ptr [r15+5Ch], 10h
0x1800ad811  jnz     short loc_1800AD838
0x1800ad813  mov     rcx, [rsp+68h]; this
0x1800ad818  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ad81f  mov     r9d, 32h ; '2'; char *
0x1800ad825  mov     edx, 1B11h; void *
0x1800ad82a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ad82f  mov     edi, eax
0x1800ad831  xor     esi, esi
0x1800ad833  jmp     loc_1800ADADF
0x1800ad838  cmp     dword ptr [r15+58h], 1
0x1800ad83d  lea     r13, [r12+18h]
0x1800ad842  jnz     loc_1800ADAA0
0x1800ad848  mov     rbp, [r15+568h]
0x1800ad84f  mov     edi, [r12]
0x1800ad853  mov     rcx, rbp; SRWLock
0x1800ad856  mov     r14, [r15+220h]
0x1800ad85d  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad864  nop     dword ptr [rax+rax+00h]
0x1800ad869  call    cs:__imp_GetCurrentThreadId
0x1800ad870  nop     dword ptr [rax+rax+00h]
0x1800ad875  mov     [rbp+8], eax
0x1800ad878  test    byte ptr [r14+28h], 1
0x1800ad87d  jnz     short loc_1800AD8A2
0x1800ad87f  mov     rcx, [rsp+68h]; this
0x1800ad884  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ad88b  mov     r9d, 139Fh; char *
0x1800ad891  mov     edx, 2E8h; void *
0x1800ad896  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ad89b  xor     esi, esi
0x1800ad89d  jmp     loc_1800ADA36
0x1800ad8a2  mov     r9b, [r13+0]
0x1800ad8a6  xor     esi, esi
0x1800ad8a8  test    r9b, r9b
0x1800ad8ab  jz      loc_1800ADA69
0x1800ad8b1  mov     r8d, [r12+8]
0x1800ad8b6  test    r8d, r8d
0x1800ad8b9  jz      loc_1800ADA69
0x1800ad8bf  mov     edx, [r12+4]
0x1800ad8c4  test    edx, 0FFFFFFE0h
0x1800ad8ca  jz      short loc_1800AD901
0x1800ad8cc  mov     edx, 2F8h; void *
0x1800ad8d1  mov     rcx, [rsp+68h]; this
0x1800ad8d6  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ad8dd  mov     edi, 80070057h
0x1800ad8e2  mov     r9d, edi; char *
0x1800ad8e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad8ea  mov     rcx, rbp; SRWLock
0x1800ad8ed  mov     [rbp+8], esi
0x1800ad8f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad8f7  nop     dword ptr [rax+rax+00h]
0x1800ad8fc  jmp     loc_1800ADA4E
0x1800ad901  test    dl, 8
0x1800ad904  jz      short loc_1800AD920
0x1800ad906  test    dl, 4
0x1800ad909  jnz     short loc_1800AD912
0x1800ad90b  mov     edx, 306h
0x1800ad910  jmp     short loc_1800AD8D1
0x1800ad912  test    byte ptr [r14+28h], 2
0x1800ad917  jnz     short loc_1800AD920
0x1800ad919  mov     edx, 30Dh
0x1800ad91e  jmp     short loc_1800AD8D1
0x1800ad920  test    dl, 0Ch
0x1800ad923  setnz   cl
0x1800ad926  test    dl, 10h
0x1800ad929  setnz   al
0x1800ad92c  test    al, cl
0x1800ad92e  jz      short loc_1800AD937
0x1800ad930  mov     edx, 31Eh
0x1800ad935  jmp     short loc_1800AD8D1
0x1800ad937  cmp     [r14+34h], esi
0x1800ad93b  jz      short loc_1800AD97D
0x1800ad93d  xor     r9d, r9d; Flags
0x1800ad940  mov     [rbp+8], esi
0x1800ad943  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800ad947  lea     rcx, [r14+38h]; ConditionVariable
0x1800ad94b  mov     rdx, rbp; SRWLock
0x1800ad94e  call    cs:__imp_SleepConditionVariableSRW
0x1800ad955  nop     dword ptr [rax+rax+00h]
0x1800ad95a  call    cs:__imp_GetCurrentThreadId
0x1800ad961  nop     dword ptr [rax+rax+00h]
0x1800ad966  mov     [rbp+8], eax
0x1800ad969  cmp     [r14+34h], esi
0x1800ad96d  jnz     short loc_1800AD93D
0x1800ad96f  mov     edx, [r12+4]
0x1800ad974  mov     r8d, [r12+8]
0x1800ad979  mov     r9b, [r13+0]
0x1800ad97d  mov     ecx, [r14+30h]
0x1800ad981  mov     eax, edx
0x1800ad983  and     eax, ecx
0x1800ad985  cmp     eax, ecx
0x1800ad987  jnz     loc_1800ADA1A
0x1800ad98d  mov     eax, [r12+14h]
0x1800ad992  movsd   xmm0, qword ptr [r12+0Ch]
0x1800ad999  movsd   qword ptr [r14+54h], xmm0
0x1800ad99f  mov     [r14+5Ch], eax
0x1800ad9a3  mov     eax, [r12+19h]
0x1800ad9a8  mov     [r14+61h], eax
0x1800ad9ac  movzx   eax, word ptr [r12+1Dh]
0x1800ad9b2  mov     [r14+65h], ax
0x1800ad9b7  mov     al, [r12+1Fh]
0x1800ad9bc  mov     [r14+67h], al
0x1800ad9c0  mov     [r14+48h], edi
0x1800ad9c4  mov     [r14+4Ch], edx
0x1800ad9c8  mov     [r14+50h], r8d
0x1800ad9cc  mov     [r14+60h], r9b
0x1800ad9d0  cmp     [r14+2Ch], esi
0x1800ad9d4  jz      loc_1800ADA73
0x1800ad9da  not     ecx
0x1800ad9dc  and     ecx, edx
0x1800ad9de  cmp     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x1800ad9e3  mov     [r14+2Ch], ecx
0x1800ad9e7  jz      short loc_1800ADA10
0x1800ad9e9  mov     rdx, r14
0x1800ad9ec  lea     rcx, [rbp+38h]
0x1800ad9f0  call    cs:__imp_RtlRbRemoveNode
0x1800ad9f7  nop     dword ptr [rax+rax+00h]
0x1800ad9fc  mov     rdx, r14
0x1800ad9ff  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x1800ada07  lea     rcx, [rbp+38h]
0x1800ada0b  call    ?Push@?$IntrusivePriorityQueue@UContainerMemoryContext@Details@Core@Manager@Container@@$0A@$1?CompareContainerMemoryContexts@MemoryManager@2345@CAJAEBU12345@0@Z@Csl@@QEAAXAEAUContainerMemoryContext@Details@Core@Manager@Container@@@Z; Csl::IntrusivePriorityQueue<Container::Manager::Core::Details::ContainerMemoryContext,0,&Container::Manager::Core::Details::MemoryManager::CompareContainerMemoryContexts(Container::Manager::Core::Details::ContainerMemoryContext const &,Container::Manager::Core::Details::ContainerMemoryContext const &)>::Push(Container::Manager::Core::Details::ContainerMemoryContext &)
0x1800ada10  mov     rcx, rbp; this
0x1800ada13  call    ?CheckRemediationActionsAndSignalRemediationThread@MemoryManager@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::MemoryManager::CheckRemediationActionsAndSignalRemediationThread(void)
0x1800ada18  jmp     short loc_1800ADA73
0x1800ada1a  mov     rcx, [rsp+68h]; this
0x1800ada1f  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ada26  mov     r9d, 139Fh; char *
0x1800ada2c  mov     edx, 32Fh; void *
0x1800ada31  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ada36  mov     rcx, rbp; SRWLock
0x1800ada39  mov     [rbp+8], esi
0x1800ada3c  mov     edi, eax
0x1800ada3e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ada45  nop     dword ptr [rax+rax+00h]
0x1800ada4a  test    edi, edi
0x1800ada4c  jns     short loc_1800ADA85
0x1800ada4e  mov     rcx, [rsp+68h]; this
0x1800ada53  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ada5a  mov     r9d, edi; char *
0x1800ada5d  mov     edx, 1B19h; void *
0x1800ada62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ada67  jmp     short loc_1800ADADF
0x1800ada69  cmp     [r14+60h], sil
0x1800ada6d  jz      short loc_1800ADA73
0x1800ada6f  mov     [r14+60h], sil
0x1800ada73  mov     rcx, rbp; SRWLock
0x1800ada76  mov     [rbp+8], esi
0x1800ada79  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ada80  nop     dword ptr [rax+rax+00h]
0x1800ada85  cmp     [r13+0], sil
0x1800ada89  jz      short loc_1800ADACD
0x1800ada8b  mov     eax, [r12]
0x1800ada8f  mov     byte ptr [r15+4C0h], 1
0x1800ada97  mov     [r15+4BCh], eax
0x1800ada9e  jmp     short loc_1800ADADD
0x1800adaa0  xor     esi, esi
0x1800adaa2  cmp     [r13+0], sil
0x1800adaa6  jz      short loc_1800ADACD
0x1800adaa8  cmp     [r12+8], esi
0x1800adaad  jz      short loc_1800ADA85
0x1800adaaf  mov     rcx, [rsp+68h]; this
0x1800adab4  lea     r9d, [rsi+32h]; char *
0x1800adab8  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800adabf  mov     edx, 1B1Eh; void *
0x1800adac4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800adac9  mov     edi, eax
0x1800adacb  jmp     short loc_1800ADADF
0x1800adacd  cmp     [r15+4C0h], sil
0x1800adad4  jz      short loc_1800ADADD
0x1800adad6  mov     [r15+4C0h], sil
0x1800adadd  mov     edi, esi
0x1800adadf  mov     rcx, rbx; SRWLock
0x1800adae2  mov     [rbx+8], esi
0x1800adae5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800adaec  nop     dword ptr [rax+rax+00h]
0x1800adaf1  mov     eax, edi
0x1800adaf3  add     rsp, 28h
0x1800adaf7  pop     r15
0x1800adaf9  pop     r14
0x1800adafb  pop     r13
0x1800adafd  pop     r12
0x1800adaff  pop     rdi
0x1800adb00  pop     rsi
0x1800adb01  pop     rbp
0x1800adb02  pop     rbx
0x1800adb03  retn
```
