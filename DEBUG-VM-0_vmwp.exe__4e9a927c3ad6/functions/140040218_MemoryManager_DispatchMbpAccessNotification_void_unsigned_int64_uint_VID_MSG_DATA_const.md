# MemoryManager::DispatchMbpAccessNotification(void *,unsigned __int64,uint,_VID_MSG_DATA * const)

- ea: `0x140040218`
- end: `0x1400407d2`
- name: `?DispatchMbpAccessNotification@MemoryManager@@QEAA?AUDispatchMemoryNotificationResult@@PEAX_KIQEAU_VID_MSG_DATA@@@Z`
- size: `1466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140212350`

## callees

- `0x140040218`
- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x14009d7ac`
- `0x140132940`
- `0x1402139dc`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004056c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400405ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004063d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004056c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400405ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004063d`

## string_xrefs

- `0x14004059c`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040718`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040738`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MemoryManager::DispatchMbpAccessNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v8; // r15
  signed __int32 v9; // eax
  signed __int32 v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rbp
  __int64 v13; // rdi
  __int64 v14; // rbx
  char v15; // al
  _QWORD *v16; // r12
  _DWORD *v17; // r13
  __int64 **v18; // r13
  signed __int32 *v19; // r12
  signed __int32 v20; // eax
  signed __int32 v21; // ebx
  signed __int32 v22; // edx
  __int64 *v23; // rsi
  signed __int32 *v24; // rbx
  signed __int32 v25; // eax
  signed __int32 v26; // edi
  __int64 v27; // rcx
  int v28; // edx
  int v29; // edx
  __int64 v31; // r12
  __int64 v32; // rax
  int v33; // ecx
  int v34; // ecx
  signed __int32 v35; // edx
  signed __int32 v36; // edx
  bool v37; // zf
  unsigned int v38; // [rsp+20h] [rbp-B8h]
  __int64 v39; // [rsp+40h] [rbp-98h]
  _QWORD v42[3]; // [rsp+70h] [rbp-68h] BYREF
  char v43; // [rsp+88h] [rbp-50h]
  __int64 v44; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v44 = a1;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_OWORD *)(a2 + 32) = 0;
  *(_BYTE *)a2 = 1;
  v8 = *(_QWORD *)(a1 + 160) + 24LL;
  v9 = _InterlockedCompareExchange((volatile signed __int32 *)v8, 4, 0);
  v10 = v9;
  if ( v9 )
  {
    if ( (v9 & 1) != 0 && *(_DWORD *)(v8 + 4) == GetCurrentThreadId() )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    }
    else
    {
      do
      {
        while ( (v10 & 1) != 0 )
        {
          if ( !(unsigned int)RrwpLockWait(v8, 0xFFFFFFFFLL, 0) )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
              (const char *)0x102,
              v38);
          _m_prefetchw((const void *)v8);
          v10 = *(_DWORD *)v8;
        }
        v35 = v10;
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)v8, v10 + 4, v10);
      }
      while ( v10 != v35 );
    }
    a1 = v44;
  }
  v11 = 0;
  v12 = a4;
  v13 = 0;
  v14 = 0;
  v39 = 0;
  v15 = 1;
  v16 = (_QWORD *)(a2 + 16);
  v17 = (_DWORD *)(a2 + 4);
  while ( 1 )
  {
    if ( !v15 )
    {
      RrwLockRelease(v8);
      *(_QWORD *)(a2 + 32) = v13;
      *(_QWORD *)(a2 + 40) = v14;
      if ( !v13 )
        return a2;
      v44 = v12;
      *(_BYTE *)a2 = (**(unsigned int (__fastcall ***)(__int64, __int64, _QWORD, __int64, _DWORD *, __int64 *, _QWORD *))v13)(
                       v13,
                       v12,
                       a5,
                       v14,
                       v17,
                       &v44,
                       v16) == 1;
      if ( *(_DWORD *)(v13 + 8) == 2 )
      {
        if ( *v16 > 1u )
          *v16 = 1;
      }
      else
      {
        v12 = v44;
      }
      v27 = 0;
      v28 = *(_DWORD *)(v13 + 8);
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 == 1 )
            v27 = v12 - *(_QWORD *)(v11 + 8);
          goto LABEL_31;
        }
      }
      else if ( *(_BYTE *)v11 )
      {
        v27 = v12 - *(_QWORD *)(v11 + 144);
LABEL_31:
        *(_QWORD *)(a2 + 8) = v27;
        return a2;
      }
      v27 = v12;
      goto LABEL_31;
    }
    v18 = *(__int64 ***)(a1 + 160);
    v19 = (signed __int32 *)(v18 + 3);
    v20 = _InterlockedCompareExchange((volatile signed __int32 *)v18 + 6, 4, 0);
    v21 = v20;
    if ( v20 )
    {
      if ( (v20 & 1) != 0 && *((_DWORD *)v18 + 7) == GetCurrentThreadId() )
      {
        _InterlockedIncrement((volatile signed __int32 *)v18 + 8);
      }
      else
      {
        do
        {
          while ( (v21 & 1) != 0 )
          {
            if ( !(unsigned int)RrwpLockWait(v18 + 3, 0xFFFFFFFFLL, 0) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v38);
            _m_prefetchw(v19);
            v21 = *v19;
          }
          v22 = v21;
          v21 = _InterlockedCompareExchange(v19, v21 + 4, v21);
        }
        while ( v21 != v22 );
      }
    }
    v23 = *v18;
    if ( *v18 == v18[1] )
    {
LABEL_16:
      v11 = 0;
    }
    else
    {
      while ( *(_QWORD *)(*v23 + 152) != a3 )
      {
        if ( ++v23 == v18[1] )
          goto LABEL_16;
      }
      v11 = *v23;
    }
    RrwLockRelease(v18 + 3);
    if ( v11 )
      break;
    *(_QWORD *)(a2 + 8) = a4;
    v17 = (_DWORD *)(a2 + 4);
    *(_DWORD *)(a2 + 4) = 3;
    v16 = (_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 1;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x8000FFFFLL,
      v38);
    if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
      VmlDebugTraceEx(0, &off_1402DAC38);
    v14 = v39;
LABEL_42:
    v15 = 0;
    a1 = v44;
  }
  if ( (*(_BYTE *)(v11 + 168) & 8) == 0 )
  {
    v24 = (signed __int32 *)(v11 + 24);
    v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 24), 4, 0);
    v26 = v25;
    if ( v25 )
    {
      if ( (v25 & 1) != 0 && *(_DWORD *)(v11 + 28) == GetCurrentThreadId() )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 32));
      }
      else
      {
        do
        {
          while ( (v26 & 1) != 0 )
          {
            if ( !(unsigned int)RrwpLockWait(v11 + 24, 0xFFFFFFFFLL, 0) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v38);
            _m_prefetchw(v24);
            v26 = *v24;
          }
          v36 = v26;
          v26 = _InterlockedCompareExchange(v24, v26 + 4, v26);
        }
        while ( v26 != v36 );
      }
    }
    v31 = *(_QWORD *)(v11 + 88);
    if ( v31 == -1 )
    {
      IntervalTree<MemoryNotification>::Find(v11 + 72, v42, a4);
      if ( v43 )
      {
        v13 = v42[0];
        v32 = v42[1];
      }
      else
      {
        v13 = 0;
        v32 = 0;
      }
    }
    else
    {
      v13 = *(_QWORD *)(v11 + 88);
      v32 = *(_QWORD *)(v11 + 96);
    }
    v39 = v32;
    RrwLockRelease(v11 + 24);
    *(_BYTE *)(a2 + 24) = v31 == -1;
    v17 = (_DWORD *)(a2 + 4);
    if ( !v13 )
    {
      v14 = v39;
      v37 = v31 == -1;
      v16 = (_QWORD *)(a2 + 16);
      if ( v37 )
      {
        *v17 = 3;
        *(_QWORD *)(a2 + 8) = a4;
        *v16 = 1;
      }
      else
      {
        *v17 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *v16 = *(_QWORD *)(v11 + 120);
      }
      goto LABEL_42;
    }
    *v17 = 0;
    v16 = (_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 1;
    v12 = 0;
    v33 = *(_DWORD *)(v13 + 8);
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        if ( v34 == 1 )
          v12 = *(_QWORD *)(v11 + 8) + a4;
        goto LABEL_40;
      }
LABEL_65:
      v12 = a4;
    }
    else
    {
      if ( !*(_BYTE *)v11 )
        goto LABEL_65;
      v12 = *(_QWORD *)(v11 + 144) + a4;
    }
LABEL_40:
    v14 = v39;
    if ( !v39 )
    {
      v14 = a6;
      v39 = a6;
    }
    goto LABEL_42;
  }
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x387,
    (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
    (const char *)0x8000FFFFLL,
    v38);
  if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
    VmlDebugTraceEx(0, &off_1402DABE0);
  *(_BYTE *)a2 = 0;
  RrwLockRelease(v8);
  return a2;
}

```

## disassembly

```asm
0x140040218  mov     [rsp+arg_10], rbx
0x14004021d  push    rbp
0x14004021e  push    rsi
0x14004021f  push    rdi
0x140040220  push    r12
0x140040222  push    r13
0x140040224  push    r14
0x140040226  push    r15
0x140040228  sub     rsp, 0A0h
0x14004022f  mov     rax, cs:__security_cookie
0x140040236  xor     rax, rsp
0x140040239  mov     [rsp+0D8h+var_40], rax
0x140040241  mov     rdi, r9
0x140040244  mov     [rsp+0D8h+var_90], r9
0x140040249  mov     [rsp+0D8h+var_88], r8
0x14004024e  mov     r14, rdx
0x140040251  mov     [rsp+0D8h+var_48], rcx
0x140040259  mov     rax, [rsp+0D8h+arg_28]
0x140040261  mov     [rsp+0D8h+var_80], rax
0x140040266  xorps   xmm0, xmm0
0x140040269  movups  xmmword ptr [rdx], xmm0
0x14004026c  movups  xmmword ptr [rdx+10h], xmm0
0x140040270  movups  xmmword ptr [rdx+20h], xmm0
0x140040274  mov     byte ptr [rdx], 1
0x140040277  mov     r15, [rcx+0A0h]
0x14004027e  add     r15, 18h
0x140040282  mov     edx, 4
0x140040287  xor     eax, eax
0x140040289  lock cmpxchg [r15], edx
0x14004028e  mov     ebx, eax
0x140040290  jz      short loc_1400402CF
0x140040292  test    al, 1
0x140040294  jnz     loc_14004056C
0x14004029a  test    bl, 1
0x14004029d  jz      loc_140040513
0x1400402a3  xor     r8d, r8d
0x1400402a6  or      edx, 0FFFFFFFFh
0x1400402a9  mov     rcx, r15
0x1400402ac  call    RrwpLockWait
0x1400402b1  test    eax, eax
0x1400402b3  jz      loc_14004058E
0x1400402b9  prefetchw byte ptr [r15]
0x1400402bd  mov     ebx, [r15]
0x1400402c0  jmp     short loc_14004029A
0x1400402c2  mov     edx, 4
0x1400402c7  mov     rcx, [rsp+0D8h+var_48]
0x1400402cf  xor     esi, esi
0x1400402d1  mov     rbp, rdi
0x1400402d4  xor     edi, edi
0x1400402d6  xor     ebx, ebx
0x1400402d8  mov     [rsp+0D8h+var_98], rbx
0x1400402dd  mov     [rsp+0D8h+var_78], r15
0x1400402e2  mov     al, 1
0x1400402e4  mov     [rsp+0D8h+var_70], al
0x1400402e8  lea     r12, [r14+10h]
0x1400402ec  lea     r13, [r14+4]
0x1400402f0  test    al, al
0x1400402f2  jz      loc_1400403C0
0x1400402f8  mov     r13, [rcx+0A0h]
0x1400402ff  lea     r12, [r13+18h]
0x140040303  xor     eax, eax
0x140040305  lock cmpxchg [r12], edx
0x14004030b  mov     ebx, eax
0x14004030d  jz      short loc_140040333
0x14004030f  test    al, 1
0x140040311  jnz     loc_1400405AE
0x140040317  test    bl, 1
0x14004031a  jnz     loc_140040548
0x140040320  mov     edx, ebx
0x140040322  lea     ecx, [rbx+4]
0x140040325  mov     eax, ebx
0x140040327  lock cmpxchg [r12], ecx
0x14004032d  mov     ebx, eax
0x14004032f  cmp     eax, edx
0x140040331  jnz     short loc_140040317
0x140040333  mov     rsi, [r13+0]
0x140040337  cmp     rsi, [r13+8]
0x14004033b  jz      short loc_14004035C
0x14004033d  mov     rcx, [rsp+0D8h+var_88]
0x140040342  mov     rax, [rsi]
0x140040345  cmp     [rax+98h], rcx
0x14004034c  jz      loc_1400405D2
0x140040352  add     rsi, 8
0x140040356  cmp     rsi, [r13+8]
0x14004035a  jnz     short loc_140040342
0x14004035c  xor     esi, esi
0x14004035e  mov     rcx, r12
0x140040361  call    RrwLockRelease
0x140040366  test    rsi, rsi
0x140040369  jz      loc_1400405DA
0x14004036f  test    byte ptr [rsi+0A8h], 8
0x140040376  jnz     loc_14004074A
0x14004037c  lea     rbx, [rsi+18h]
0x140040380  xor     eax, eax
0x140040382  lea     ecx, [rax+4]
0x140040385  lock cmpxchg [rbx], ecx
0x140040389  mov     edi, eax
0x14004038b  jz      loc_14004047D
0x140040391  test    al, 1
0x140040393  jnz     loc_14004063D
0x140040399  test    dil, 1
0x14004039d  jz      loc_14004052E
0x1400403a3  xor     r8d, r8d
0x1400403a6  or      edx, 0FFFFFFFFh
0x1400403a9  mov     rcx, rbx
0x1400403ac  call    RrwpLockWait
0x1400403b1  test    eax, eax
0x1400403b3  jz      loc_14004072A
0x1400403b9  prefetchw byte ptr [rbx]
0x1400403bc  mov     edi, [rbx]
0x1400403be  jmp     short loc_140040399
0x1400403c0  mov     rcx, r15
0x1400403c3  call    RrwLockRelease
0x1400403c8  mov     [r14+20h], rdi
0x1400403cc  mov     [r14+28h], rbx
0x1400403d0  test    rdi, rdi
0x1400403d3  jz      short loc_14004044E
0x1400403d5  mov     [rsp+0D8h+var_48], rbp
0x1400403dd  mov     rax, [rdi]
0x1400403e0  mov     [rsp+0D8h+var_A8], r12
0x1400403e5  lea     rcx, [rsp+0D8h+var_48]
0x1400403ed  mov     [rsp+0D8h+var_B0], rcx
0x1400403f2  mov     [rsp+0D8h+var_B8], r13
0x1400403f7  mov     r9, rbx
0x1400403fa  mov     r8d, [rsp+0D8h+arg_20]
0x140040402  mov     rdx, rbp
0x140040405  mov     rcx, rdi
0x140040408  mov     rax, [rax]
0x14004040b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040410  cmp     eax, 1
0x140040413  setz    al
0x140040416  mov     [r14], al
0x140040419  cmp     dword ptr [rdi+8], 2
0x14004041d  jz      loc_140040793
0x140040423  mov     rbp, [rsp+0D8h+var_48]
0x14004042b  xor     ecx, ecx
0x14004042d  mov     edx, [rdi+8]
0x140040430  test    edx, edx
0x140040432  jz      loc_1400407B7
0x140040438  sub     edx, 1
0x14004043b  jz      loc_1400407CA
0x140040441  cmp     edx, 1
0x140040444  jz      loc_1400407AB
0x14004044a  mov     [r14+8], rcx
0x14004044e  mov     rax, r14
0x140040451  mov     rcx, [rsp+0D8h+var_40]
0x140040459  xor     rcx, rsp; StackCookie
0x14004045c  call    __security_check_cookie
0x140040461  mov     rbx, [rsp+0D8h+arg_10]
0x140040469  add     rsp, 0A0h
0x140040470  pop     r15
0x140040472  pop     r14
0x140040474  pop     r13
0x140040476  pop     r12
0x140040478  pop     rdi
0x140040479  pop     rsi
0x14004047a  pop     rbp
0x14004047b  retn
0x14004047d  mov     r12, [rsi+58h]
0x140040481  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140040485  setz    r13b
0x140040489  jz      loc_14004065D
0x14004048f  mov     rdi, r12
0x140040492  mov     rax, [rsi+60h]
0x140040496  mov     [rsp+0D8h+var_98], rax
0x14004049b  mov     rcx, rbx
0x14004049e  call    RrwLockRelease
0x1400404a3  mov     [r14+18h], r13b
0x1400404a7  lea     r13, [r14+4]
0x1400404ab  test    rdi, rdi
0x1400404ae  jz      loc_1400406C0
0x1400404b4  mov     dword ptr [r13+0], 0
0x1400404bc  lea     r12, [r14+10h]
0x1400404c0  mov     qword ptr [r12], 1
0x1400404c8  xor     ebp, ebp
0x1400404ca  mov     ecx, [rdi+8]
0x1400404cd  test    ecx, ecx
0x1400404cf  jz      loc_1400406A0
0x1400404d5  sub     ecx, 1
0x1400404d8  jz      loc_1400406B6
0x1400404de  cmp     ecx, 1
0x1400404e1  jz      loc_140040692
0x1400404e7  mov     rbx, [rsp+0D8h+var_98]
0x1400404ec  test    rbx, rbx
0x1400404ef  jnz     short loc_1400404FB
0x1400404f1  mov     rbx, [rsp+0D8h+var_80]
0x1400404f6  mov     [rsp+0D8h+var_98], rbx
0x1400404fb  xor     al, al
0x1400404fd  mov     [rsp+0D8h+var_70], al
0x140040501  mov     rcx, [rsp+0D8h+var_48]
0x140040509  mov     edx, 4
0x14004050e  jmp     loc_1400402F0
0x140040513  mov     edx, ebx
0x140040515  lea     ecx, [rbx+4]
0x140040518  mov     eax, ebx
0x14004051a  lock cmpxchg [r15], ecx
0x14004051f  mov     ebx, eax
0x140040521  cmp     eax, edx
0x140040523  jnz     loc_14004029A
0x140040529  jmp     loc_1400402C2
0x14004052e  mov     edx, edi
0x140040530  lea     ecx, [rdi+4]
0x140040533  mov     eax, edi
0x140040535  lock cmpxchg [rbx], ecx
0x140040539  mov     edi, eax
0x14004053b  cmp     eax, edx
0x14004053d  jnz     loc_140040399
0x140040543  jmp     loc_14004047D
0x140040548  xor     r8d, r8d
0x14004054b  or      edx, 0FFFFFFFFh
0x14004054e  mov     rcx, r12
0x140040551  call    RrwpLockWait
0x140040556  test    eax, eax
0x140040558  jz      loc_14004070A
0x14004055e  prefetchw byte ptr [r12]
0x140040563  mov     ebx, [r12]
0x140040567  jmp     loc_140040317
0x14004056c  call    cs:__imp_GetCurrentThreadId
0x140040573  nop     dword ptr [rax+rax+00h]
0x140040578  mov     ecx, [r15+4]
0x14004057c  cmp     ecx, eax
0x14004057e  jnz     loc_14004029A
0x140040584  lock inc dword ptr [r15+8]
0x140040589  jmp     loc_1400402C2
0x14004058e  mov     rcx, [rsp+0D8h]; this
0x140040596  mov     r9d, 102h; char *
0x14004059c  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400405a3  mov     edx, 249h; void *
0x1400405a8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400405ae  call    cs:__imp_GetCurrentThreadId
0x1400405b5  nop     dword ptr [rax+rax+00h]
0x1400405ba  mov     ecx, [r12+4]
0x1400405bf  cmp     ecx, eax
0x1400405c1  jnz     loc_140040317
0x1400405c7  lock inc dword ptr [r12+8]
0x1400405cd  jmp     loc_140040333
0x1400405d2  mov     rsi, rax
0x1400405d5  jmp     loc_14004035E
0x1400405da  mov     rax, [rsp+0D8h+var_90]
0x1400405df  mov     [r14+8], rax
0x1400405e3  lea     r13, [r14+4]
0x1400405e7  mov     dword ptr [r13+0], 3
0x1400405ef  lea     r12, [r14+10h]
0x1400405f3  mov     qword ptr [r12], 1
0x1400405fb  mov     rcx, [rsp+0D8h]; this
0x140040603  mov     r9d, 8000FFFFh; char *
0x140040609  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x140040610  mov     edx, 381h; void *
0x140040615  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14004061a  xor     ecx, ecx
0x14004061c  call    VmlIsDebugTraceEnabled
0x140040621  test    eax, eax
0x140040623  jz      short loc_140040633
0x140040625  lea     rdx, off_1402DAC38; "Unexpected error.\n"
0x14004062c  xor     ecx, ecx
0x14004062e  call    VmlDebugTraceEx
0x140040633  mov     rbx, [rsp+0D8h+var_98]
0x140040638  jmp     loc_1400404FB
0x14004063d  call    cs:__imp_GetCurrentThreadId
0x140040644  nop     dword ptr [rax+rax+00h]
0x140040649  mov     ecx, [rbx+4]
0x14004064c  cmp     ecx, eax
0x14004064e  jnz     loc_140040399
0x140040654  lock inc dword ptr [rbx+8]
0x140040658  jmp     loc_14004047D
0x14004065d  lea     rcx, [rsi+48h]
0x140040661  mov     r8, [rsp+0D8h+var_90]
0x140040666  lea     rdx, [rsp+0D8h+var_68]
0x14004066b  call    ?Find@?$IntervalTree@UMemoryNotification@@@@QEBA?AV?$optional@UMemoryNotification@@@std@@_K@Z; IntervalTree<MemoryNotification>::Find(unsigned __int64)
0x140040670  cmp     [rsp+0D8h+var_50], 0
0x140040678  jz      short loc_140040689
0x14004067a  mov     rdi, [rsp+0D8h+var_68]
0x14004067f  mov     rax, [rsp+0D8h+var_60]
0x140040684  jmp     loc_140040496
0x140040689  xor     edi, edi
0x14004068b  xor     eax, eax
0x14004068d  jmp     loc_140040496
0x140040692  mov     rbp, [rsp+0D8h+var_90]
0x140040697  add     rbp, [rsi+8]
0x14004069b  jmp     loc_1400404E7
0x1400406a0  cmp     [rsi], bpl
0x1400406a3  jz      short loc_1400406B6
0x1400406a5  mov     rbp, [rsp+0D8h+var_90]
0x1400406aa  add     rbp, [rsi+90h]
0x1400406b1  jmp     loc_1400404E7
0x1400406b6  mov     rbp, [rsp+0D8h+var_90]
0x1400406bb  jmp     loc_1400404E7
0x1400406c0  mov     rbx, [rsp+0D8h+var_98]
0x1400406c5  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1400406c9  lea     r12, [r14+10h]
0x1400406cd  jnz     short loc_1400406ED
0x1400406cf  mov     dword ptr [r13+0], 3
0x1400406d7  mov     rax, [rsp+0D8h+var_90]
0x1400406dc  mov     [r14+8], rax
0x1400406e0  mov     qword ptr [r12], 1
0x1400406e8  jmp     loc_1400404FB
0x1400406ed  mov     dword ptr [r13+0], 0
0x1400406f5  mov     qword ptr [r14+8], 0
0x1400406fd  mov     rax, [rsi+78h]
0x140040701  mov     [r12], rax
  ... truncated ...
```
