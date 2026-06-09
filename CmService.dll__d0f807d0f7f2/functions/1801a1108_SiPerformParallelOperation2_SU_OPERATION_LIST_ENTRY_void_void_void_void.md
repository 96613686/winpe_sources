# SiPerformParallelOperation2(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)

- ea: `0x1801a1108`
- end: `0x1801a126b`
- name: `?SiPerformParallelOperation2@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801a2100`

## callees

- `0x1801a1108`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801a11e9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801a11e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a11bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a11bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801a1203`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801a1203`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801a1212`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801a1212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1186`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a119f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a123a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a119f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a123a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a1174`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a1174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a1159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a1159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a1251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a1251`

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
0x1801a1108  push    rbp
0x1801a110a  push    rbx
0x1801a110b  push    rsi
0x1801a110c  push    rdi
0x1801a110d  push    r14
0x1801a110f  mov     rbp, rsp
0x1801a1112  sub     rsp, 60h
0x1801a1116  mov     rax, [rbp+arg_20]
0x1801a111a  xorps   xmm0, xmm0
0x1801a111d  mov     [rbp+var_20], rax
0x1801a1121  mov     ebx, 1
0x1801a1126  mov     rax, [rbp+arg_28]
0x1801a112a  mov     rdi, rdx
0x1801a112d  mov     [rbp+var_18], rax
0x1801a1131  mov     esi, ebx
0x1801a1133  movdqa  xmmword ptr [rbp+TokenHandle], xmm0
0x1801a1138  mov     [rbp+pv], ecx
0x1801a113b  mov     [rbp+var_38], rdx
0x1801a113f  mov     [rbp+var_30], r8
0x1801a1143  mov     [rbp+var_28], r9
0x1801a1147  test    rdx, rdx
0x1801a114a  jz      loc_1801A121E
0x1801a1150  cmp     [rdx], rdx
0x1801a1153  jz      loc_1801A1224
0x1801a1159  call    cs:__imp_GetCurrentThread
0x1801a1160  nop     dword ptr [rax+rax+00h]
0x1801a1165  lea     r9, [rbp+TokenHandle+8]; TokenHandle
0x1801a1169  xor     r8d, r8d; OpenAsSelf
0x1801a116c  mov     rcx, rax; ThreadHandle
0x1801a116f  mov     edx, 2000Ch; DesiredAccess
0x1801a1174  call    cs:__imp_OpenThreadToken
0x1801a117b  nop     dword ptr [rax+rax+00h]
0x1801a1180  mov     esi, eax
0x1801a1182  test    eax, eax
0x1801a1184  jnz     short loc_1801A11AD
0x1801a1186  call    cs:__imp_GetLastError
0x1801a118d  nop     dword ptr [rax+rax+00h]
0x1801a1192  cmp     eax, 3F0h
0x1801a1197  jnz     loc_1801A121E
0x1801a119d  xor     ecx, ecx; dwErrCode
0x1801a119f  call    cs:__imp_SetLastError
0x1801a11a6  nop     dword ptr [rax+rax+00h]
0x1801a11ab  mov     esi, ebx
0x1801a11ad  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801a11b4  lea     rdx, [rbp+pv]; pv
0x1801a11b8  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801a11bf  call    cs:__imp_CreateThreadpoolWork
0x1801a11c6  nop     dword ptr [rax+rax+00h]
0x1801a11cb  mov     r14, rax
0x1801a11ce  test    rax, rax
0x1801a11d1  jz      short loc_1801A1246
0x1801a11d3  mov     rcx, [rbp+var_38]
0x1801a11d7  mov     rax, [rcx]
0x1801a11da  mov     [rbp+TokenHandle], rax
0x1801a11de  mov     rbx, [rcx]
0x1801a11e1  cmp     rbx, rcx
0x1801a11e4  jz      short loc_1801A11FE
0x1801a11e6  mov     rcx, r14; pwk
0x1801a11e9  call    cs:__imp_SubmitThreadpoolWork
0x1801a11f0  nop     dword ptr [rax+rax+00h]
0x1801a11f5  mov     rbx, [rbx]
0x1801a11f8  cmp     rbx, [rbp+var_38]
0x1801a11fc  jnz     short loc_1801A11E6
0x1801a11fe  xor     edx, edx; fCancelPendingCallbacks
0x1801a1200  mov     rcx, r14; pwk
0x1801a1203  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801a120a  nop     dword ptr [rax+rax+00h]
0x1801a120f  mov     rcx, r14; pwk
0x1801a1212  call    cs:__imp_CloseThreadpoolWork
0x1801a1219  nop     dword ptr [rax+rax+00h]
0x1801a121e  mov     ebx, esi
0x1801a1220  test    esi, esi
0x1801a1222  jz      short loc_1801A1248
0x1801a1224  mov     rax, [rdi]
0x1801a1227  jmp     short loc_1801A1233
0x1801a1229  mov     ecx, [rax+10h]; dwErrCode
0x1801a122c  test    ecx, ecx
0x1801a122e  jnz     short loc_1801A123A
0x1801a1230  mov     rax, [rax]
0x1801a1233  cmp     rax, rdi
0x1801a1236  jnz     short loc_1801A1229
0x1801a1238  jmp     short loc_1801A1248
0x1801a123a  call    cs:__imp_SetLastError
0x1801a1241  nop     dword ptr [rax+rax+00h]
0x1801a1246  xor     ebx, ebx
0x1801a1248  mov     rcx, [rbp+TokenHandle+8]; hObject
0x1801a124c  test    rcx, rcx
0x1801a124f  jz      short loc_1801A125D
0x1801a1251  call    cs:__imp_CloseHandle
0x1801a1258  nop     dword ptr [rax+rax+00h]
0x1801a125d  mov     eax, ebx
0x1801a125f  add     rsp, 60h
0x1801a1263  pop     r14
0x1801a1265  pop     rdi
0x1801a1266  pop     rsi
0x1801a1267  pop     rbx
0x1801a1268  pop     rbp
0x1801a1269  retn
```
