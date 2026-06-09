# UbpmpDecrementRefAndDelete

- ea: `0x180004c30`
- end: `0x180005188`
- name: `UbpmpDecrementRefAndDelete`
- size: `1368`
- prototype: ``
- caller_count: `14`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180003438`
- `0x180004640`
- `0x18000480c`
- `0x180004840`
- `0x1800048b0`
- `0x180005190`
- `0x180008430`
- `0x180009a30`
- `0x18000a230`
- `0x180010220`
- `0x180010450`
- `0x180010730`
- `0x180011a90`
- `0x18001da20`

## callees

- `0x18000467c`
- `0x180004c30`
- `0x18000fbf0`
- `0x18001131c`
- `0x180032f78`
- `0x18003819c`
- `0x18003edd8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004e4e`
- `ntdll!RtlFreeHeap` at `0x180004e75`
- `ntdll!RtlFreeHeap` at `0x180004eca`
- `ntdll!RtlFreeHeap` at `0x180004ef1`
- `ntdll!RtlFreeHeap` at `0x180004f18`
- `ntdll!RtlFreeHeap` at `0x180004f3f`
- `ntdll!RtlFreeHeap` at `0x180004f66`
- `ntdll!RtlFreeHeap` at `0x180004f8d`
- `ntdll!RtlFreeHeap` at `0x180004fb4`
- `ntdll!RtlFreeHeap` at `0x180004fd2`
- `ntdll!RtlFreeHeap` at `0x180004e4e`
- `ntdll!RtlFreeHeap` at `0x180004e75`
- `ntdll!RtlFreeHeap` at `0x180004eca`
- `ntdll!RtlFreeHeap` at `0x180004ef1`
- `ntdll!RtlFreeHeap` at `0x180004f18`
- `ntdll!RtlFreeHeap` at `0x180004f3f`
- `ntdll!RtlFreeHeap` at `0x180004f66`
- `ntdll!RtlFreeHeap` at `0x180004f8d`
- `ntdll!RtlFreeHeap` at `0x180004fb4`
- `ntdll!RtlFreeHeap` at `0x180004fd2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004c4d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004db0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004c4d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004db0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004ca2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004d1e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004de6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004ca2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004d1e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004de6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180004d68`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180004d68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000516d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000516d`
- `profapi!__imp_UnloadProfileBasic` at `0x180005122`
- `profapi!__imp_UnloadProfileBasic` at `0x180005122`

## pseudocode

```c
char __fastcall UbpmpDecrementRefAndDelete(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  int v5; // edi
  signed __int64 v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rdx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  DWORD LastError; // eax
  _DWORD *v15; // r14
  bool v16; // zf
  void *v17; // rcx
  void *v18; // rcx
  PSID v19; // r8
  void *v20; // r8
  _QWORD *v21; // r15
  _QWORD *v22; // r15
  void *v23; // r8
  void *v24; // r8
  void *v25; // r8
  void *v26; // r8
  void *v27; // r8
  void *v28; // r8
  void *v29; // r8
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rdx
  _QWORD *v33; // r8
  _QWORD *v34; // rax
  _QWORD *v35; // rbp
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rcx
  int v47; // eax
  DWORD v49; // [rsp+20h] [rbp-38h]
  _QWORD *v50; // [rsp+60h] [rbp+8h] BYREF

  v4 = *a1;
  v5 = a2;
  if ( a2 )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    dword_180050018 = GetCurrentThreadId();
  }
  v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 96), 0xFFFFFFFFFFFFFFFFuLL);
  if ( v7 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v4);
    v8 = *(_QWORD *)(v4 + 8);
    v9 = (_QWORD *)(v4 + 8);
    if ( *(_QWORD *)(v8 + 8) == v4 + 8 )
    {
      v10 = *(_QWORD **)(v4 + 16);
      if ( (_QWORD *)*v10 == v9 )
      {
        *v10 = v8;
        *(_QWORD *)(v8 + 8) = v10;
        *(_QWORD *)(v4 + 16) = v4 + 8;
        *v9 = v9;
        if ( v5 )
        {
          dword_180050018 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
          v5 = 0;
        }
        v11 = *(void **)(v4 + 48);
        if ( v11 )
          CloseHandle(v11);
        v12 = *(void **)(v4 + 232);
        if ( v12 )
          CloseHandle(v12);
        v13 = *(void **)(v4 + 24);
        if ( v13 )
        {
          if ( !TerminateProcess(v13, 0x42Bu) )
          {
            LastError = GetLastError();
            if ( LastError != 5
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v49 = LastError;
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                *(unsigned int *)(v4 + 32));
            }
          }
          CloseHandle(*(HANDLE *)(v4 + 24));
        }
        v15 = *(_DWORD **)(v4 + 416);
        if ( v15 )
        {
          RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
          dword_180050080 = GetCurrentThreadId();
          v16 = (*v15)-- == 1;
          if ( v16 && !v15[1] )
            DestroyJobObjectContext(v15);
          dword_180050080 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
        }
        if ( *(_QWORD *)(v4 + 240) )
        {
          v46 = *(_QWORD *)(v4 + 248);
          if ( v46 )
          {
            v47 = UnloadProfileBasic(v46);
            if ( v47 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_L(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                81,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                (unsigned int)v47,
                v49);
          }
        }
        v17 = *(void **)(v4 + 256);
        if ( v17 )
          CloseHandle(v17);
        v18 = *(void **)(v4 + 248);
        if ( v18 )
          CloseHandle(v18);
        v19 = *(PSID *)(v4 + 176);
        if ( v19 != pSid && v19 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
        v20 = *(void **)(v4 + 184);
        if ( v20 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        *(_WORD *)(v4 + 196) = 0;
        v21 = *(_QWORD **)(v4 + 216);
        if ( v21 == (_QWORD *)(v4 + 216) )
        {
LABEL_34:
          v22 = *(_QWORD **)(v4 + 200);
          while ( v22 != (_QWORD *)(v4 + 200) )
          {
            v30 = v22 - 2;
            v22 = (_QWORD *)*v22;
            v50 = v30;
            UbpmpDecrementTaskRefAndDelete(&v50);
          }
          v23 = *(void **)(v4 + 360);
          if ( v23 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
          v24 = *(void **)(v4 + 376);
          if ( v24 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
          v25 = *(void **)(v4 + 344);
          if ( v25 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
          v26 = *(void **)(v4 + 144);
          if ( v26 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
          v27 = *(void **)(v4 + 152);
          if ( v27 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
          v28 = *(void **)(v4 + 160);
          if ( v28 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
          v29 = *(void **)(v4 + 400);
          if ( v29 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
          LOBYTE(v7) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v4);
          *a1 = 0;
          goto LABEL_4;
        }
        while ( 1 )
        {
          v31 = (_QWORD *)*v21;
          if ( *(_QWORD **)(*v21 + 8LL) != v21 )
            break;
          v32 = (_QWORD *)v21[1];
          v33 = v21 + 1;
          if ( (_QWORD *)*v32 != v21 )
            break;
          v34 = v21;
          *v32 = v31;
          v31[1] = v32;
          v35 = v21;
          v21 = v31;
          *v33 = v34;
          *v34 = v34;
          v36 = v34[2];
          if ( v36 )
          {
            UBPM_MIDL_user_free(*(_QWORD *)(v36 + 16), v32, v33, a4);
            UBPM_MIDL_user_free(*(_QWORD *)(v35[2] + 24LL), v37, v38, v39);
            UBPM_MIDL_user_free(*(_QWORD *)(v35[2] + 8LL), v40, v41, v42);
            UBPM_MIDL_user_free(v35[2], v43, v44, v45);
          }
          if ( v35[3] )
            UbpmpDecrementTaskRefAndDelete(v35 + 3);
          UBPM_MIDL_user_free(v35, v32, v33, a4);
          if ( v21 == (_QWORD *)(v4 + 216) )
            goto LABEL_34;
        }
      }
    }
    __fastfail(3u);
  }
LABEL_4:
  if ( v5 )
  {
    dword_180050018 = 0;
    LOBYTE(v7) = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  }
  return v7;
}

```

## disassembly

```asm
0x180004c30  push    rbx
0x180004c32  push    rsi
0x180004c33  push    rdi
0x180004c34  push    r12
0x180004c36  sub     rsp, 38h
0x180004c3a  mov     rbx, [rcx]
0x180004c3d  mov     edi, edx
0x180004c3f  mov     rsi, rcx
0x180004c42  test    edx, edx
0x180004c44  jz      short loc_180004C6B
0x180004c46  lea     rcx, g_TaskHostContextListLock
0x180004c4d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004c54  nop     dword ptr [rax+rax+00h]
0x180004c59  call    cs:__imp_GetCurrentThreadId
0x180004c60  nop     dword ptr [rax+rax+00h]
0x180004c65  mov     cs:dword_180050018, eax
0x180004c6b  mov     [rsp+58h+arg_10], rbp
0x180004c70  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004c77  mov     [rsp+58h+arg_18], r14
0x180004c7c  mov     [rsp+58h+var_28], r15
0x180004c81  lock xadd [rbx+60h], rax
0x180004c87  xor     r12d, r12d
0x180004c8a  cmp     rax, 1
0x180004c8e  jz      short loc_180004CC8
0x180004c90  test    edi, edi
0x180004c92  jz      short loc_180004CAE
0x180004c94  lea     rcx, g_TaskHostContextListLock
0x180004c9b  mov     cs:dword_180050018, r12d
0x180004ca2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004ca9  nop     dword ptr [rax+rax+00h]
0x180004cae  mov     r15, [rsp+58h+var_28]
0x180004cb3  mov     r14, [rsp+58h+arg_18]
0x180004cb8  mov     rbp, [rsp+58h+arg_10]
0x180004cbd  add     rsp, 38h
0x180004cc1  pop     r12
0x180004cc3  pop     rdi
0x180004cc4  pop     rsi
0x180004cc5  pop     rbx
0x180004cc6  retn
0x180004cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ccf  lea     rbp, WPP_GLOBAL_Control
0x180004cd6  cmp     rcx, rbp
0x180004cd9  jnz     loc_180004FE6
0x180004cdf  mov     rcx, [rbx+8]
0x180004ce3  lea     rax, [rbx+8]
0x180004ce7  cmp     [rcx+8], rax
0x180004ceb  jnz     loc_180005024
0x180004cf1  mov     rdx, [rax+8]
0x180004cf5  cmp     [rdx], rax
0x180004cf8  jnz     loc_180005024
0x180004cfe  mov     [rdx], rcx
0x180004d01  mov     [rcx+8], rdx
0x180004d05  mov     [rax+8], rax
0x180004d09  mov     [rax], rax
0x180004d0c  test    edi, edi
0x180004d0e  jz      short loc_180004D2D
0x180004d10  lea     rcx, g_TaskHostContextListLock
0x180004d17  mov     cs:dword_180050018, r12d
0x180004d1e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004d25  nop     dword ptr [rax+rax+00h]
0x180004d2a  mov     edi, r12d
0x180004d2d  mov     rcx, [rbx+30h]; hObject
0x180004d31  test    rcx, rcx
0x180004d34  jz      short loc_180004D42
0x180004d36  call    cs:__imp_CloseHandle
0x180004d3d  nop     dword ptr [rax+rax+00h]
0x180004d42  mov     rcx, [rbx+0E8h]; hObject
0x180004d49  test    rcx, rcx
0x180004d4c  jz      short loc_180004D5A
0x180004d4e  call    cs:__imp_CloseHandle
0x180004d55  nop     dword ptr [rax+rax+00h]
0x180004d5a  mov     rcx, [rbx+18h]; hProcess
0x180004d5e  test    rcx, rcx
0x180004d61  jz      short loc_180004D9D
0x180004d63  mov     edx, 42Bh; uExitCode
0x180004d68  call    cs:__imp_TerminateProcess
0x180004d6f  nop     dword ptr [rax+rax+00h]
0x180004d74  test    eax, eax
0x180004d76  jnz     short loc_180004D8D
0x180004d78  call    cs:__imp_GetLastError
0x180004d7f  nop     dword ptr [rax+rax+00h]
0x180004d84  cmp     eax, 5
0x180004d87  jnz     loc_1800050D6
0x180004d8d  mov     rcx, [rbx+18h]; hObject
0x180004d91  call    cs:__imp_CloseHandle
0x180004d98  nop     dword ptr [rax+rax+00h]
0x180004d9d  mov     r14, [rbx+1A0h]
0x180004da4  test    r14, r14
0x180004da7  jz      short loc_180004DF2
0x180004da9  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x180004db0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004db7  nop     dword ptr [rax+rax+00h]
0x180004dbc  call    cs:__imp_GetCurrentThreadId
0x180004dc3  nop     dword ptr [rax+rax+00h]
0x180004dc8  mov     cs:dword_180050080, eax
0x180004dce  sub     dword ptr [r14], 1
0x180004dd2  jz      loc_18000500D
0x180004dd8  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x180004ddf  mov     cs:dword_180050080, r12d
0x180004de6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004ded  nop     dword ptr [rax+rax+00h]
0x180004df2  mov     rdx, [rbx+0F0h]
0x180004df9  test    rdx, rdx
0x180004dfc  jnz     loc_180005112
0x180004e02  mov     rcx, [rbx+100h]; hObject
0x180004e09  test    rcx, rcx
0x180004e0c  jz      short loc_180004E1A
0x180004e0e  call    cs:__imp_CloseHandle
0x180004e15  nop     dword ptr [rax+rax+00h]
0x180004e1a  mov     rcx, [rbx+0F8h]; hObject
0x180004e21  test    rcx, rcx
0x180004e24  jnz     loc_18000516D
0x180004e2a  mov     r8, [rbx+0B0h]; P
0x180004e31  cmp     r8, cs:pSid
0x180004e38  jz      short loc_180004E5A
0x180004e3a  test    r8, r8
0x180004e3d  jz      short loc_180004E5A
0x180004e3f  mov     rcx, gs:60h
0x180004e48  xor     edx, edx; Flags
0x180004e4a  mov     rcx, [rcx+30h]; HeapHandle
0x180004e4e  call    cs:__imp_RtlFreeHeap
0x180004e55  nop     dword ptr [rax+rax+00h]
0x180004e5a  mov     r8, [rbx+0B8h]; P
0x180004e61  test    r8, r8
0x180004e64  jz      short loc_180004E81
0x180004e66  mov     rcx, gs:60h
0x180004e6f  xor     edx, edx; Flags
0x180004e71  mov     rcx, [rcx+30h]; HeapHandle
0x180004e75  call    cs:__imp_RtlFreeHeap
0x180004e7c  nop     dword ptr [rax+rax+00h]
0x180004e81  lea     r14, [rbx+0D8h]
0x180004e88  mov     [rbx+0C4h], r12w
0x180004e90  mov     r15, [r14]
0x180004e93  cmp     r15, r14
0x180004e96  jnz     loc_180005051
0x180004e9c  lea     r14, [rbx+0C8h]
0x180004ea3  mov     r15, [r14]
0x180004ea6  cmp     r15, r14
0x180004ea9  jnz     loc_180005030
0x180004eaf  mov     r8, [rbx+168h]; P
0x180004eb6  test    r8, r8
0x180004eb9  jz      short loc_180004ED6
0x180004ebb  mov     rcx, gs:60h
0x180004ec4  xor     edx, edx; Flags
0x180004ec6  mov     rcx, [rcx+30h]; HeapHandle
0x180004eca  call    cs:__imp_RtlFreeHeap
0x180004ed1  nop     dword ptr [rax+rax+00h]
0x180004ed6  mov     r8, [rbx+178h]; P
0x180004edd  test    r8, r8
0x180004ee0  jz      short loc_180004EFD
0x180004ee2  mov     rcx, gs:60h
0x180004eeb  xor     edx, edx; Flags
0x180004eed  mov     rcx, [rcx+30h]; HeapHandle
0x180004ef1  call    cs:__imp_RtlFreeHeap
0x180004ef8  nop     dword ptr [rax+rax+00h]
0x180004efd  mov     r8, [rbx+158h]; P
0x180004f04  test    r8, r8
0x180004f07  jz      short loc_180004F24
0x180004f09  mov     rcx, gs:60h
0x180004f12  xor     edx, edx; Flags
0x180004f14  mov     rcx, [rcx+30h]; HeapHandle
0x180004f18  call    cs:__imp_RtlFreeHeap
0x180004f1f  nop     dword ptr [rax+rax+00h]
0x180004f24  mov     r8, [rbx+90h]; P
0x180004f2b  test    r8, r8
0x180004f2e  jz      short loc_180004F4B
0x180004f30  mov     rcx, gs:60h
0x180004f39  xor     edx, edx; Flags
0x180004f3b  mov     rcx, [rcx+30h]; HeapHandle
0x180004f3f  call    cs:__imp_RtlFreeHeap
0x180004f46  nop     dword ptr [rax+rax+00h]
0x180004f4b  mov     r8, [rbx+98h]; P
0x180004f52  test    r8, r8
0x180004f55  jz      short loc_180004F72
0x180004f57  mov     rcx, gs:60h
0x180004f60  xor     edx, edx; Flags
0x180004f62  mov     rcx, [rcx+30h]; HeapHandle
0x180004f66  call    cs:__imp_RtlFreeHeap
0x180004f6d  nop     dword ptr [rax+rax+00h]
0x180004f72  mov     r8, [rbx+0A0h]; P
0x180004f79  test    r8, r8
0x180004f7c  jz      short loc_180004F99
0x180004f7e  mov     rcx, gs:60h
0x180004f87  xor     edx, edx; Flags
0x180004f89  mov     rcx, [rcx+30h]; HeapHandle
0x180004f8d  call    cs:__imp_RtlFreeHeap
0x180004f94  nop     dword ptr [rax+rax+00h]
0x180004f99  mov     r8, [rbx+190h]; P
0x180004fa0  test    r8, r8
0x180004fa3  jz      short loc_180004FC0
0x180004fa5  mov     rcx, gs:60h
0x180004fae  xor     edx, edx; Flags
0x180004fb0  mov     rcx, [rcx+30h]; HeapHandle
0x180004fb4  call    cs:__imp_RtlFreeHeap
0x180004fbb  nop     dword ptr [rax+rax+00h]
0x180004fc0  mov     rcx, gs:60h
0x180004fc9  mov     r8, rbx; P
0x180004fcc  xor     edx, edx; Flags
0x180004fce  mov     rcx, [rcx+30h]; HeapHandle
0x180004fd2  call    cs:__imp_RtlFreeHeap
0x180004fd9  nop     dword ptr [rax+rax+00h]
0x180004fde  mov     [rsi], r12
0x180004fe1  jmp     loc_180004C90
0x180004fe6  test    byte ptr [rcx+1Ch], 80h
0x180004fea  jz      loc_180004CDF
0x180004ff0  mov     rcx, [rcx+10h]
0x180004ff4  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180004ffb  mov     edx, 4Fh ; 'O'
0x180005000  mov     r9, rbx
0x180005003  call    WPP_SF_q
0x180005008  jmp     loc_180004CDF
0x18000500d  cmp     [r14+4], r12d
0x180005011  jnz     loc_180004DD8
0x180005017  mov     rcx, r14
0x18000501a  call    DestroyJobObjectContext
0x18000501f  jmp     loc_180004DD8
0x180005024  mov     ecx, 3
0x180005029  int     29h; Win8: RtlFailFast(ecx)
0x180005030  lea     rax, [r15-10h]
0x180005034  mov     r15, [r15]
0x180005037  lea     rcx, [rsp+58h+arg_0]
0x18000503c  mov     [rsp+58h+arg_0], rax
0x180005041  call    UbpmpDecrementTaskRefAndDelete
0x180005046  cmp     r15, r14
0x180005049  jz      loc_180004EAF
0x18000504f  jmp     short loc_180005030
0x180005051  mov     rcx, [r15]
0x180005054  cmp     [rcx+8], r15
0x180005058  jnz     short loc_180005024
0x18000505a  mov     rdx, [r15+8]
0x18000505e  lea     r8, [r15+8]
0x180005062  cmp     [rdx], r15
0x180005065  jnz     short loc_180005024
0x180005067  mov     rax, r15
0x18000506a  mov     [rdx], rcx
0x18000506d  mov     [rcx+8], rdx
0x180005071  mov     rbp, r15
0x180005074  mov     r15, rcx
0x180005077  mov     [r8], rax
0x18000507a  mov     [rax], rax
0x18000507d  mov     rcx, [rax+10h]
0x180005081  test    rcx, rcx
0x180005084  jz      short loc_1800050B2
0x180005086  mov     rcx, [rcx+10h]
0x18000508a  call    UBPM_MIDL_user_free
0x18000508f  mov     rcx, [rbp+10h]
0x180005093  mov     rcx, [rcx+18h]
0x180005097  call    UBPM_MIDL_user_free
0x18000509c  mov     rcx, [rbp+10h]
0x1800050a0  mov     rcx, [rcx+8]
0x1800050a4  call    UBPM_MIDL_user_free
0x1800050a9  mov     rcx, [rbp+10h]
0x1800050ad  call    UBPM_MIDL_user_free
0x1800050b2  cmp     [rbp+18h], r12
0x1800050b6  lea     rcx, [rbp+18h]
0x1800050ba  jnz     loc_18000517E
0x1800050c0  mov     rcx, rbp
0x1800050c3  call    UBPM_MIDL_user_free
0x1800050c8  cmp     r15, r14
0x1800050cb  jz      loc_180004E9C
0x1800050d1  jmp     loc_180005051
0x1800050d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050dd  cmp     rcx, rbp
0x1800050e0  jz      loc_180004D8D
0x1800050e6  test    byte ptr [rcx+1Ch], 2
0x1800050ea  jz      loc_180004D8D
0x1800050f0  mov     r9d, [rbx+20h]
0x1800050f4  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800050fb  mov     rcx, [rcx+10h]
0x1800050ff  mov     edx, 50h ; 'P'
0x180005104  mov     [rsp+58h+var_38], eax
0x180005108  call    WPP_SF_dd
0x18000510d  jmp     loc_180004D8D
0x180005112  mov     rcx, [rbx+0F8h]
0x180005119  test    rcx, rcx
0x18000511c  jz      loc_180004E02
0x180005122  call    cs:__imp_UnloadProfileBasic
0x180005129  nop     dword ptr [rax+rax+00h]
0x18000512e  test    eax, eax
0x180005130  jns     loc_180004E02
0x180005136  mov     rcx, cs:WPP_GLOBAL_Control
0x18000513d  cmp     rcx, rbp
0x180005140  jz      loc_180004E02
0x180005146  test    byte ptr [rcx+1Ch], 1
0x18000514a  jz      loc_180004E02
0x180005150  mov     rcx, [rcx+10h]
0x180005154  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000515b  mov     edx, 51h ; 'Q'
0x180005160  mov     r9d, eax
0x180005163  call    WPP_SF_L
0x180005168  jmp     loc_180004E02
0x18000516d  call    cs:__imp_CloseHandle
0x180005174  nop     dword ptr [rax+rax+00h]
0x180005179  jmp     loc_180004E2A
0x18000517e  call    UbpmpDecrementTaskRefAndDelete
0x180005183  jmp     loc_1800050C0
```
