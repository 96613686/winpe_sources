# SiPerformParallelOperation2(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)

- ea: `0x1801a1278`
- end: `0x1801a13db`
- name: `?SiPerformParallelOperation2@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801a2270`

## callees

- `0x1801a1278`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801a1359`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801a1359`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a132f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a132f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801a1373`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801a1373`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801a1382`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801a1382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a12f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a12f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a130f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a13aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a130f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a13aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a12e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a12e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a12c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a12c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a13c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a13c1`

## pseudocode

```c
__int64 __fastcall SiPerformParallelOperation2(int a1, void **a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned int v6; // ebx
  BOOL v8; // esi
  HANDLE CurrentThread; // rax
  struct _TP_WORK *v10; // r14
  void **v11; // rbx
  void **i; // rax
  DWORD v13; // ecx
  int pv; // [rsp+20h] [rbp-40h] BYREF
  void **v16; // [rsp+28h] [rbp-38h]
  __int64 v17; // [rsp+30h] [rbp-30h]
  __int64 v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h]
  __int64 v20; // [rsp+48h] [rbp-18h]
  void *TokenHandle[2]; // [rsp+50h] [rbp-10h] BYREF

  v19 = a5;
  v6 = 1;
  v20 = a6;
  v8 = 1;
  *(_OWORD *)TokenHandle = 0;
  pv = a1;
  v16 = a2;
  v17 = a3;
  v18 = a4;
  if ( !a2 )
    goto LABEL_10;
  if ( *a2 != a2 )
  {
    CurrentThread = GetCurrentThread();
    v8 = OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle[1]);
    if ( v8 )
    {
LABEL_6:
      v10 = CreateThreadpoolWork(SI_DISPATCH::Callback, &pv, &ThreadpoolEnv);
      if ( !v10 )
      {
LABEL_17:
        v6 = 0;
        goto LABEL_18;
      }
      TokenHandle[0] = *v16;
      v11 = (void **)*v16;
      if ( *v16 != v16 )
      {
        do
        {
          SubmitThreadpoolWork(v10);
          v11 = (void **)*v11;
        }
        while ( v11 != v16 );
      }
      WaitForThreadpoolWorkCallbacks(v10, 0);
      CloseThreadpoolWork(v10);
      goto LABEL_10;
    }
    if ( GetLastError() == 1008 )
    {
      SetLastError(0);
      v8 = 1;
      goto LABEL_6;
    }
LABEL_10:
    v6 = v8;
    if ( !v8 )
      goto LABEL_18;
  }
  for ( i = (void **)*a2; i != a2; i = (void **)*i )
  {
    v13 = *((_DWORD *)i + 4);
    if ( v13 )
    {
      SetLastError(v13);
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( TokenHandle[1] )
    CloseHandle(TokenHandle[1]);
  return v6;
}

```

## disassembly

```asm
0x1801a1278  push    rbp
0x1801a127a  push    rbx
0x1801a127b  push    rsi
0x1801a127c  push    rdi
0x1801a127d  push    r14
0x1801a127f  mov     rbp, rsp
0x1801a1282  sub     rsp, 60h
0x1801a1286  mov     rax, [rbp+arg_20]
0x1801a128a  xorps   xmm0, xmm0
0x1801a128d  mov     [rbp+var_20], rax
0x1801a1291  mov     ebx, 1
0x1801a1296  mov     rax, [rbp+arg_28]
0x1801a129a  mov     rdi, rdx
0x1801a129d  mov     [rbp+var_18], rax
0x1801a12a1  mov     esi, ebx
0x1801a12a3  movdqa  xmmword ptr [rbp+TokenHandle], xmm0
0x1801a12a8  mov     [rbp+pv], ecx
0x1801a12ab  mov     [rbp+var_38], rdx
0x1801a12af  mov     [rbp+var_30], r8
0x1801a12b3  mov     [rbp+var_28], r9
0x1801a12b7  test    rdx, rdx
0x1801a12ba  jz      loc_1801A138E
0x1801a12c0  cmp     [rdx], rdx
0x1801a12c3  jz      loc_1801A1394
0x1801a12c9  call    cs:__imp_GetCurrentThread
0x1801a12d0  nop     dword ptr [rax+rax+00h]
0x1801a12d5  lea     r9, [rbp+TokenHandle+8]; TokenHandle
0x1801a12d9  xor     r8d, r8d; OpenAsSelf
0x1801a12dc  mov     rcx, rax; ThreadHandle
0x1801a12df  mov     edx, 2000Ch; DesiredAccess
0x1801a12e4  call    cs:__imp_OpenThreadToken
0x1801a12eb  nop     dword ptr [rax+rax+00h]
0x1801a12f0  mov     esi, eax
0x1801a12f2  test    eax, eax
0x1801a12f4  jnz     short loc_1801A131D
0x1801a12f6  call    cs:__imp_GetLastError
0x1801a12fd  nop     dword ptr [rax+rax+00h]
0x1801a1302  cmp     eax, 3F0h
0x1801a1307  jnz     loc_1801A138E
0x1801a130d  xor     ecx, ecx; dwErrCode
0x1801a130f  call    cs:__imp_SetLastError
0x1801a1316  nop     dword ptr [rax+rax+00h]
0x1801a131b  mov     esi, ebx
0x1801a131d  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801a1324  lea     rdx, [rbp+pv]; pv
0x1801a1328  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801a132f  call    cs:__imp_CreateThreadpoolWork
0x1801a1336  nop     dword ptr [rax+rax+00h]
0x1801a133b  mov     r14, rax
0x1801a133e  test    rax, rax
0x1801a1341  jz      short loc_1801A13B6
0x1801a1343  mov     rcx, [rbp+var_38]
0x1801a1347  mov     rax, [rcx]
0x1801a134a  mov     [rbp+TokenHandle], rax
0x1801a134e  mov     rbx, [rcx]
0x1801a1351  cmp     rbx, rcx
0x1801a1354  jz      short loc_1801A136E
0x1801a1356  mov     rcx, r14; pwk
0x1801a1359  call    cs:__imp_SubmitThreadpoolWork
0x1801a1360  nop     dword ptr [rax+rax+00h]
0x1801a1365  mov     rbx, [rbx]
0x1801a1368  cmp     rbx, [rbp+var_38]
0x1801a136c  jnz     short loc_1801A1356
0x1801a136e  xor     edx, edx; fCancelPendingCallbacks
0x1801a1370  mov     rcx, r14; pwk
0x1801a1373  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801a137a  nop     dword ptr [rax+rax+00h]
0x1801a137f  mov     rcx, r14; pwk
0x1801a1382  call    cs:__imp_CloseThreadpoolWork
0x1801a1389  nop     dword ptr [rax+rax+00h]
0x1801a138e  mov     ebx, esi
0x1801a1390  test    esi, esi
0x1801a1392  jz      short loc_1801A13B8
0x1801a1394  mov     rax, [rdi]
0x1801a1397  jmp     short loc_1801A13A3
0x1801a1399  mov     ecx, [rax+10h]; dwErrCode
0x1801a139c  test    ecx, ecx
0x1801a139e  jnz     short loc_1801A13AA
0x1801a13a0  mov     rax, [rax]
0x1801a13a3  cmp     rax, rdi
0x1801a13a6  jnz     short loc_1801A1399
0x1801a13a8  jmp     short loc_1801A13B8
0x1801a13aa  call    cs:__imp_SetLastError
0x1801a13b1  nop     dword ptr [rax+rax+00h]
0x1801a13b6  xor     ebx, ebx
0x1801a13b8  mov     rcx, [rbp+TokenHandle+8]; hObject
0x1801a13bc  test    rcx, rcx
0x1801a13bf  jz      short loc_1801A13CD
0x1801a13c1  call    cs:__imp_CloseHandle
0x1801a13c8  nop     dword ptr [rax+rax+00h]
0x1801a13cd  mov     eax, ebx
0x1801a13cf  add     rsp, 60h
0x1801a13d3  pop     r14
0x1801a13d5  pop     rdi
0x1801a13d6  pop     rsi
0x1801a13d7  pop     rbx
0x1801a13d8  pop     rbp
0x1801a13d9  retn
```
