# Windows::ApplicationModel::Resources::Core::PerViewContextManager::InitializeForThread(Microsoft::Resources::Runtime::ContextType,Windows::UI::IWindowContextPartner *,_CONTEXT_ID *)

- ea: `0x180043f50`
- end: `0x1800441cb`
- name: `?InitializeForThread@PerViewContextManager@Core@Resources@ApplicationModel@Windows@@UEAAJW4ContextType@Runtime@3Microsoft@@PEAUIWindowContextPartner@UI@5@PEAU_CONTEXT_ID@@@Z`
- size: `635`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800218b4`
- `0x18002c8d0`
- `0x180043f50`
- `0x1800441d4`
- `0x180044418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004408b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800440d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004415b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004408b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800440d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004415b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043fce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043fce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043f94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004405f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044143`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043f94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004405f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044143`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044014`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043fa7`

## string_xrefs

- `0x1800440c4`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180044170`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180044195`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::PerViewContextManager::InitializeForThread(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  __int64 v5; // rsi
  RTL_SRWLOCK *v7; // r12
  unsigned __int64 v8; // rsi
  PVOID Ptr; // r15
  int v10; // ebx
  void *i; // rax
  _QWORD *v12; // rdx
  void *j; // rax
  __int64 v14; // rbx
  _QWORD *v15; // rcx
  __int128 v16; // xmm6
  __int64 v17; // xmm7_8
  _QWORD *v18; // rax
  unsigned int PerViewContext; // ebx
  __int128 v21; // xmm6
  __int64 v22; // xmm7_8
  void *k; // rax
  __int64 v24; // rbx
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  int *v28; // [rsp+28h] [rbp-49h]
  RTL_SRWLOCK *v29; // [rsp+38h] [rbp-39h] BYREF
  char v30; // [rsp+40h] [rbp-31h]
  _QWORD v31[2]; // [rsp+48h] [rbp-29h] BYREF
  int v32[4]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v33; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v5 = (int)a2;
  v7 = a1 + 7;
  v29 = a1 + 7;
  v30 = 0;
  AcquireSRWLockExclusive(a1 + 7);
  a1[10].Ptr = (PVOID)Windows::ApplicationModel::Resources::Core::GetWindowId(a3);
  v8 = GetCurrentThreadId() | (unsigned __int64)(v5 << 32);
  Ptr = a1[10].Ptr;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  AcquireSRWLockShared(a1 + 6);
  v10 = -2147023728;
  for ( i = 0; i < a1[5].Ptr; i = (char *)i + 1 )
  {
    v12 = a1[2].Ptr;
    if ( v12[5 * (_QWORD)i] == v8 && (PVOID)v12[5 * (_QWORD)i + 1] == Ptr )
    {
      v10 = 0;
      *(_OWORD *)v32 = *(_OWORD *)&v12[5 * (_QWORD)i + 2];
      v33 = v12[5 * (_QWORD)i + 4];
      break;
    }
  }
  ReleaseSRWLockShared(a1 + 6);
  if ( v10 >= 0 )
  {
LABEL_8:
    if ( *(_QWORD *)v32 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v33);
      for ( j = 0; j < a1[5].Ptr; j = (char *)j + 1 )
      {
        v14 = 5LL * (_QWORD)j;
        v15 = a1[2].Ptr;
        if ( v15[5 * (_QWORD)j] == v8 && (PVOID)v15[5 * (_QWORD)j + 1] == Ptr )
        {
          v16 = *(_OWORD *)v32;
          v17 = v33;
          AcquireSRWLockExclusive(a1 + 6);
          v18 = a1[2].Ptr;
          *(_OWORD *)&v18[v14 + 2] = v16;
          v18[v14 + 4] = v17;
          ReleaseSRWLockExclusive(a1 + 6);
          *a4 = v8;
          a4[1] = (unsigned __int64)Ptr;
          ReleaseSRWLockExclusive(v7);
          return 0;
        }
      }
      PerViewContext = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x546,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
        (const char *)0x80070490LL,
        (int)v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x543,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
        (const char *)0x80073B27LL,
        (int)v28);
      PerViewContext = -2147009753;
    }
    goto LABEL_16;
  }
  v31[0] = v8;
  v31[1] = Ptr;
  v28 = v32;
  PerViewContext = Windows::ApplicationModel::Resources::Core::PerViewContextManager::_CreatePerViewContext(
                     a1,
                     v31,
                     a2,
                     a3);
  if ( (PerViewContext & 0x80000000) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v33);
    v21 = *(_OWORD *)v32;
    v22 = v33;
    for ( k = 0; k < a1[5].Ptr; k = (char *)k + 1 )
    {
      v24 = 5LL * (_QWORD)k;
      v25 = a1[2].Ptr;
      if ( v25[5 * (_QWORD)k] == v8 && (PVOID)v25[5 * (_QWORD)k + 1] == Ptr )
      {
        AcquireSRWLockExclusive(a1 + 6);
        v26 = a1[2].Ptr;
        *(_OWORD *)&v26[v24 + 2] = v21;
        v26[v24 + 4] = v22;
        ReleaseSRWLockExclusive(a1 + 6);
        goto LABEL_8;
      }
    }
    PerViewContext = -2147023728;
    v27 = 1336;
    goto LABEL_27;
  }
  if ( PerViewContext != -2147009753 )
  {
    v27 = 1331;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
      (const char *)PerViewContext,
      (int)v32);
    Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock((Microsoft::Resources::AutoReaderWriterLock *)&v29);
    return PerViewContext;
  }
LABEL_16:
  ReleaseSRWLockExclusive(v7);
  return PerViewContext;
}

```

## disassembly

```asm
0x180043f50  mov     rax, rsp
0x180043f53  mov     [rax+8], rbx
0x180043f57  mov     [rax+20h], r9
0x180043f5b  mov     [rax+10h], edx
0x180043f5e  push    rbp
0x180043f5f  push    rsi
0x180043f60  push    rdi
0x180043f61  push    r12
0x180043f63  push    r13
0x180043f65  push    r14
0x180043f67  push    r15
0x180043f69  lea     rbp, [rax-5Fh]
0x180043f6d  sub     rsp, 90h
0x180043f74  movaps  xmmword ptr [rax-48h], xmm6
0x180043f78  movaps  xmmword ptr [rax-58h], xmm7
0x180043f7c  mov     r13, r8
0x180043f7f  movsxd  rsi, edx
0x180043f82  mov     rdi, rcx
0x180043f85  lea     r12, [rcx+38h]
0x180043f89  mov     [rbp+57h+var_90], r12
0x180043f8d  mov     [rbp+57h+var_88], 0
0x180043f91  mov     rcx, r12; SRWLock
0x180043f94  call    cs:__imp_AcquireSRWLockExclusive
0x180043f9a  nop
0x180043f9b  mov     rcx, r13
0x180043f9e  call    ?GetWindowId@Core@Resources@ApplicationModel@Windows@@YA?AUWindowId@UI@4@PEAUIWindowContextPartner@64@@Z; Windows::ApplicationModel::Resources::Core::GetWindowId(Windows::UI::IWindowContextPartner *)
0x180043fa3  mov     [rdi+50h], rax
0x180043fa7  call    cs:__imp_GetCurrentThreadId
0x180043fad  shl     rsi, 20h
0x180043fb1  mov     eax, eax
0x180043fb3  or      rsi, rax
0x180043fb6  mov     r15, [rdi+50h]
0x180043fba  xorps   xmm0, xmm0
0x180043fbd  xor     eax, eax
0x180043fbf  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180043fc3  mov     [rbp+57h+var_60], rax
0x180043fc7  lea     r14, [rdi+30h]
0x180043fcb  mov     rcx, r14; SRWLock
0x180043fce  call    cs:__imp_AcquireSRWLockShared
0x180043fd4  mov     ebx, 80070490h
0x180043fd9  xor     eax, eax
0x180043fdb  cmp     rax, [rdi+28h]
0x180043fdf  jnb     short loc_180044011
0x180043fe1  lea     rcx, [rax+rax*4]
0x180043fe5  mov     rdx, [rdi+10h]
0x180043fe9  cmp     [rdx+rcx*8], rsi
0x180043fed  jz      short loc_180043FF4
0x180043fef  inc     rax
0x180043ff2  jmp     short loc_180043FDB
0x180043ff4  cmp     [rdx+rcx*8+8], r15
0x180043ff9  jnz     short loc_180043FEF
0x180043ffb  xor     ebx, ebx
0x180043ffd  movups  xmm0, xmmword ptr [rdx+rcx*8+10h]
0x180044002  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180044006  movsd   xmm1, qword ptr [rdx+rcx*8+20h]
0x18004400c  movsd   [rbp+57h+var_60], xmm1
0x180044011  mov     rcx, r14; SRWLock
0x180044014  call    cs:__imp_ReleaseSRWLockShared
0x18004401a  test    ebx, ebx
0x18004401c  js      loc_1800440E3
0x180044022  cmp     qword ptr [rbp+57h+var_70], 0
0x180044027  jz      loc_180044166
0x18004402d  lock inc dword ptr [rbp+57h+var_60]
0x180044031  xor     eax, eax
0x180044033  cmp     rax, [rdi+28h]
0x180044037  jnb     short loc_1800440B8
0x180044039  lea     rbx, [rax+rax*4]
0x18004403d  mov     rcx, [rdi+10h]
0x180044041  cmp     [rcx+rbx*8], rsi
0x180044045  jz      short loc_18004404C
0x180044047  inc     rax
0x18004404a  jmp     short loc_180044033
0x18004404c  cmp     [rcx+rbx*8+8], r15
0x180044051  jnz     short loc_180044047
0x180044053  movups  xmm6, xmmword ptr [rbp+57h+var_70]
0x180044057  movsd   xmm7, [rbp+57h+var_60]
0x18004405c  mov     rcx, r14; SRWLock
0x18004405f  call    cs:__imp_AcquireSRWLockExclusive
0x180044065  mov     rax, [rdi+10h]
0x180044069  movups  xmmword ptr [rax+rbx*8+10h], xmm6
0x18004406e  movsd   qword ptr [rax+rbx*8+20h], xmm7
0x180044074  mov     rcx, r14; SRWLock
0x180044077  call    cs:__imp_ReleaseSRWLockExclusive
0x18004407d  mov     rax, [rbp+57h+arg_18]
0x180044081  mov     [rax], rsi
0x180044084  mov     [rax+8], r15
0x180044088  mov     rcx, r12; SRWLock
0x18004408b  call    cs:__imp_ReleaseSRWLockExclusive
0x180044091  xor     eax, eax
0x180044093  lea     r11, [rsp+0C0h+var_30]
0x18004409b  mov     rbx, [r11+40h]
0x18004409f  movaps  xmm6, xmmword ptr [r11-10h]
0x1800440a4  movaps  xmm7, [rsp+0C0h+var_58+8]
0x1800440a9  mov     rsp, r11
0x1800440ac  pop     r15
0x1800440ae  pop     r14
0x1800440b0  pop     r13
0x1800440b2  pop     r12
0x1800440b4  pop     rdi
0x1800440b5  pop     rsi
0x1800440b6  pop     rbp
0x1800440b7  retn
0x1800440b8  mov     rcx, [rbp+5Fh]; this
0x1800440bc  mov     ebx, 80070490h
0x1800440c1  mov     r9d, ebx; char *
0x1800440c4  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800440cb  mov     edx, 546h; void *
0x1800440d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800440d5  nop
0x1800440d6  mov     rcx, r12; SRWLock
0x1800440d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800440df  mov     eax, ebx
0x1800440e1  jmp     short loc_180044093
0x1800440e3  mov     [rbp+57h+var_80], rsi
0x1800440e7  mov     [rbp+57h+var_78], r15
0x1800440eb  lea     rax, [rbp+57h+var_70]
0x1800440ef  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800440f4  mov     r9, r13
0x1800440f7  mov     r8d, [rbp+57h+arg_8]
0x1800440fb  lea     rdx, [rbp+57h+var_80]
0x1800440ff  mov     rcx, rdi
0x180044102  call    ?_CreatePerViewContext@PerViewContextManager@Core@Resources@ApplicationModel@Windows@@AEAAJU_CONTEXT_ID@@W4ContextType@Runtime@3Microsoft@@PEAUIWindowContextPartner@UI@5@PEAUCONTEXT_PER_VIEW@12345@@Z; Windows::ApplicationModel::Resources::Core::PerViewContextManager::_CreatePerViewContext(_CONTEXT_ID,Microsoft::Resources::Runtime::ContextType,Windows::UI::IWindowContextPartner *,Windows::ApplicationModel::Resources::Core::PerViewContextManager::CONTEXT_PER_VIEW *)
0x180044107  mov     ebx, eax
0x180044109  test    eax, eax
0x18004410b  js      loc_1800441B7
0x180044111  lock inc dword ptr [rbp+57h+var_60]
0x180044115  movups  xmm6, xmmword ptr [rbp+57h+var_70]
0x180044119  movsd   xmm7, [rbp+57h+var_60]
0x18004411e  xor     eax, eax
0x180044120  cmp     rax, [rdi+28h]
0x180044124  jnb     short loc_18004418B
0x180044126  lea     rbx, [rax+rax*4]
0x18004412a  mov     rcx, [rdi+10h]
0x18004412e  cmp     [rcx+rbx*8], rsi
0x180044132  jz      short loc_180044139
0x180044134  inc     rax
0x180044137  jmp     short loc_180044120
0x180044139  cmp     [rcx+rbx*8+8], r15
0x18004413e  jnz     short loc_180044134
0x180044140  mov     rcx, r14; SRWLock
0x180044143  call    cs:__imp_AcquireSRWLockExclusive
0x180044149  mov     rax, [rdi+10h]
0x18004414d  movups  xmmword ptr [rax+rbx*8+10h], xmm6
0x180044152  movsd   qword ptr [rax+rbx*8+20h], xmm7
0x180044158  mov     rcx, r14; SRWLock
0x18004415b  call    cs:__imp_ReleaseSRWLockExclusive
0x180044161  jmp     loc_180044022
0x180044166  mov     rcx, [rbp+5Fh]; this
0x18004416a  mov     r9d, 80073B27h; char *
0x180044170  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180044177  mov     edx, 543h; void *
0x18004417c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044181  mov     ebx, 80073B27h
0x180044186  jmp     loc_1800440D6
0x18004418b  mov     ebx, 80070490h
0x180044190  mov     edx, 538h; void *
0x180044195  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18004419c  mov     r9d, ebx; char *
0x18004419f  mov     rcx, [rbp+5Fh]; this
0x1800441a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800441a8  nop
0x1800441a9  lea     rcx, [rbp+57h+var_90]; this
0x1800441ad  call    ??1AutoReaderWriterLock@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock(void)
0x1800441b2  jmp     loc_1800440DF
0x1800441b7  cmp     ebx, 80073B27h
0x1800441bd  jz      loc_1800440D6
0x1800441c3  mov     edx, 533h
0x1800441c8  jmp     short loc_180044195
```
