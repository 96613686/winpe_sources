# BackgroundExecutionSessionClient::OnBgSessionCallbackStatic(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x1800020d0`
- end: `0x18000242b`
- name: `?OnBgSessionCallbackStatic@BackgroundExecutionSessionClient@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `859`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, char *, struct _ODB_LEGACY_TASKID_ENTRY *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800020d0`
- `0x180002440`
- `0x18000630c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000218f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000218f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002394`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002246`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002246`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023c9`

## pseudocode

```c
__int64 __fastcall BackgroundExecutionSessionClient::OnBgSessionCallbackStatic(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        char *a4,
        struct _ODB_LEGACY_TASKID_ENTRY *a5)
{
  struct _ODB_LEGACY_TASKID_ENTRY *v5; // rax
  int *v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rcx
  char *v10; // rbx
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  int v19; // ecx
  _BYTE *v20; // rcx
  int *v21; // rax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  int v31; // eax
  struct _ODB_LEGACY_TASKID_ENTRY *v32; // rdx
  __int64 v33; // r8
  struct _ODB_LEGACY_TASKID_ENTRY *v34; // rdx
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 *v39; // rcx
  __int64 v40; // rax
  __int64 *v41; // rcx
  __int64 v42; // rax
  struct _GUID v43; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE v44[20]; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v45[131]; // [rsp+4Ch] [rbp-BCh] BYREF
  int v46; // [rsp+258h] [rbp+150h] BYREF
  struct _GUID v47; // [rsp+25Ch] [rbp+154h]

  v5 = a5;
  if ( a5 )
  {
    v7 = &v46;
    v8 = 4;
    v9 = 4;
    v10 = 0;
    do
    {
      v7 += 32;
      v11 = *(_OWORD *)v5;
      v12 = *((_OWORD *)v5 + 1);
      v5 = (struct _ODB_LEGACY_TASKID_ENTRY *)((char *)v5 + 128);
      *((_OWORD *)v7 - 8) = v11;
      v13 = *((_OWORD *)v5 - 6);
      *((_OWORD *)v7 - 7) = v12;
      v14 = *((_OWORD *)v5 - 5);
      *((_OWORD *)v7 - 6) = v13;
      v15 = *((_OWORD *)v5 - 4);
      *((_OWORD *)v7 - 5) = v14;
      v16 = *((_OWORD *)v5 - 3);
      *((_OWORD *)v7 - 4) = v15;
      v17 = *((_OWORD *)v5 - 2);
      *((_OWORD *)v7 - 3) = v16;
      v18 = *((_OWORD *)v5 - 1);
      *((_OWORD *)v7 - 2) = v17;
      *((_OWORD *)v7 - 1) = v18;
      --v9;
    }
    while ( v9 );
    v19 = *((_DWORD *)v5 + 4);
    *(_OWORD *)v7 = *(_OWORD *)v5;
    v7[4] = v19;
    if ( a4 )
    {
      (*(void (__fastcall **)(char *, int *, struct _WNF_TYPE_ID *))(*(_QWORD *)a4 + 8LL))(a4, v7, a3);
      v10 = a4;
    }
    *((_DWORD *)v10 + 24) = GetCurrentThreadId();
    v20 = v44;
    v21 = &v46;
    do
    {
      v20 += 128;
      v22 = *(_OWORD *)v21;
      v23 = *((_OWORD *)v21 + 1);
      v21 += 32;
      *((_OWORD *)v20 - 8) = v22;
      v24 = *((_OWORD *)v21 - 6);
      *((_OWORD *)v20 - 7) = v23;
      v25 = *((_OWORD *)v21 - 5);
      *((_OWORD *)v20 - 6) = v24;
      v26 = *((_OWORD *)v21 - 4);
      *((_OWORD *)v20 - 5) = v25;
      v27 = *((_OWORD *)v21 - 3);
      *((_OWORD *)v20 - 4) = v26;
      v28 = *((_OWORD *)v21 - 2);
      *((_OWORD *)v20 - 3) = v27;
      v29 = *((_OWORD *)v21 - 1);
      *((_OWORD *)v20 - 2) = v28;
      *((_OWORD *)v20 - 1) = v29;
      --v8;
    }
    while ( v8 );
    v30 = *(_OWORD *)v21;
    v31 = v21[4];
    *(_OWORD *)v20 = v30;
    *((_DWORD *)v20 + 4) = v31;
    a5 = 0;
    if ( v46 )
    {
      if ( v46 == 1 )
      {
        if ( BackgroundExecutionSessionClient::IsLegacy((BackgroundExecutionSessionClient *)v10) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
          v43 = *(struct _GUID *)&v44[4];
          if ( (int)BackgroundExecutionSessionClient::GetEntryByForWorkItem(
                      (BackgroundExecutionSessionClient *)v10,
                      &v43,
                      &a5) < 0 )
            goto LABEL_22;
          v33 = v45[0];
          v32 = a5;
LABEL_21:
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v10 + 13) + 32LL))(
            *((_QWORD *)v10 + 13),
            *((unsigned int *)v32 + 8),
            v33);
LABEL_22:
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
          goto LABEL_20;
        }
        v35 = (__int64 *)*((_QWORD *)v10 + 14);
        v36 = *v35;
        v43 = v47;
        (*(void (__fastcall **)(__int64 *, struct _GUID *))(v36 + 32))(v35, &v43);
      }
      else if ( v46 == 2 )
      {
        if ( (unsigned int)(*((_DWORD *)v10 + 19) - 705) > 6 )
        {
          v39 = (__int64 *)*((_QWORD *)v10 + 14);
          v40 = *v39;
          v43 = v47;
          (*(void (__fastcall **)(__int64 *, struct _GUID *))(v40 + 40))(v39, &v43);
          goto LABEL_20;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
        v43 = *(struct _GUID *)&v44[4];
        if ( (int)BackgroundExecutionSessionClient::GetEntryByForWorkItem(
                    (BackgroundExecutionSessionClient *)v10,
                    &v43,
                    &a5) < 0 )
          goto LABEL_22;
        v32 = a5;
        if ( *((_DWORD *)a5 + 9) )
          goto LABEL_22;
        v33 = 2147500036LL;
        goto LABEL_21;
      }
    }
    else
    {
      if ( (unsigned int)(*((_DWORD *)v10 + 19) - 705) > 6 )
      {
        v41 = (__int64 *)*((_QWORD *)v10 + 14);
        v42 = *v41;
        v43 = v47;
        (*(void (__fastcall **)(__int64 *, struct _GUID *, _DWORD *))(v42 + 24))(v41, &v43, v45);
        goto LABEL_20;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
      v43 = *(struct _GUID *)&v44[4];
      if ( (int)BackgroundExecutionSessionClient::GetEntryByForWorkItem(
                  (BackgroundExecutionSessionClient *)v10,
                  &v43,
                  &a5) < 0 )
        goto LABEL_22;
      v34 = a5;
      *((_DWORD *)a5 + 9) = 1;
      (*(void (__fastcall **)(_QWORD, _QWORD, _DWORD *))(**((_QWORD **)v10 + 13) + 24LL))(
        *((_QWORD *)v10 + 13),
        *((unsigned int *)v34 + 8),
        v45);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
    }
LABEL_20:
    v37 = *(_QWORD *)v10;
    *((_DWORD *)v10 + 24) = 0;
    (*(void (__fastcall **)(char *))(v37 + 16))(v10);
    return 0;
  }
  return 3221226528LL;
}

```

## disassembly

```asm
0x1800020d0  mov     r11, rsp
0x1800020d3  mov     [r11+20h], rdi
0x1800020d7  push    rbp
0x1800020d8  lea     rbp, [r11-378h]
0x1800020df  sub     rsp, 470h
0x1800020e6  mov     rax, [rbp+370h+arg_20]
0x1800020ed  mov     rdi, r9
0x1800020f0  test    rax, rax
0x1800020f3  jz      loc_180002421
0x1800020f9  mov     [r11+8], rbx
0x1800020fd  lea     rdx, [rbp+370h+var_220]
0x180002104  mov     [r11+10h], rsi
0x180002108  mov     esi, 4
0x18000210d  mov     [r11+18h], r14
0x180002111  mov     ecx, esi
0x180002113  xor     r14d, r14d
0x180002116  mov     ebx, r14d
0x180002119  lea     rdx, [rdx+80h]
0x180002120  movups  xmm0, xmmword ptr [rax]
0x180002123  movups  xmm1, xmmword ptr [rax+10h]
0x180002127  lea     rax, [rax+80h]
0x18000212e  movups  xmmword ptr [rdx-80h], xmm0
0x180002132  movups  xmm0, xmmword ptr [rax-60h]
0x180002136  movups  xmmword ptr [rdx-70h], xmm1
0x18000213a  movups  xmm1, xmmword ptr [rax-50h]
0x18000213e  movups  xmmword ptr [rdx-60h], xmm0
0x180002142  movups  xmm0, xmmword ptr [rax-40h]
0x180002146  movups  xmmword ptr [rdx-50h], xmm1
0x18000214a  movups  xmm1, xmmword ptr [rax-30h]
0x18000214e  movups  xmmword ptr [rdx-40h], xmm0
0x180002152  movups  xmm0, xmmword ptr [rax-20h]
0x180002156  movups  xmmword ptr [rdx-30h], xmm1
0x18000215a  movups  xmm1, xmmword ptr [rax-10h]
0x18000215e  movups  xmmword ptr [rdx-20h], xmm0
0x180002162  movups  xmmword ptr [rdx-10h], xmm1
0x180002166  sub     rcx, 1
0x18000216a  jnz     short loc_180002119
0x18000216c  mov     ecx, [rax+10h]
0x18000216f  movups  xmm0, xmmword ptr [rax]
0x180002172  movups  xmmword ptr [rdx], xmm0
0x180002175  mov     [rdx+10h], ecx
0x180002178  test    rdi, rdi
0x18000217b  jz      short loc_18000218F
0x18000217d  mov     rax, [r9]
0x180002180  mov     rcx, rdi
0x180002183  mov     rax, [rax+8]
0x180002187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000218c  mov     rbx, rdi
0x18000218f  call    cs:__imp_GetCurrentThreadId
0x180002195  mov     [rbx+60h], eax
0x180002198  lea     rcx, [rsp+470h+var_444+4]
0x18000219d  lea     rax, [rbp+370h+var_220]
0x1800021a4  lea     rcx, [rcx+80h]
0x1800021ab  movups  xmm0, xmmword ptr [rax]
0x1800021ae  movups  xmm1, xmmword ptr [rax+10h]
0x1800021b2  lea     rax, [rax+80h]
0x1800021b9  movups  xmmword ptr [rcx-80h], xmm0
0x1800021bd  movups  xmm0, xmmword ptr [rax-60h]
0x1800021c1  movups  xmmword ptr [rcx-70h], xmm1
0x1800021c5  movups  xmm1, xmmword ptr [rax-50h]
0x1800021c9  movups  xmmword ptr [rcx-60h], xmm0
0x1800021cd  movups  xmm0, xmmword ptr [rax-40h]
0x1800021d1  movups  xmmword ptr [rcx-50h], xmm1
0x1800021d5  movups  xmm1, xmmword ptr [rax-30h]
0x1800021d9  movups  xmmword ptr [rcx-40h], xmm0
0x1800021dd  movups  xmm0, xmmword ptr [rax-20h]
0x1800021e1  movups  xmmword ptr [rcx-30h], xmm1
0x1800021e5  movups  xmm1, xmmword ptr [rax-10h]
0x1800021e9  movups  xmmword ptr [rcx-20h], xmm0
0x1800021ed  movups  xmmword ptr [rcx-10h], xmm1
0x1800021f1  sub     rsi, 1
0x1800021f5  jnz     short loc_1800021A4
0x1800021f7  movups  xmm0, xmmword ptr [rax]
0x1800021fa  mov     eax, [rax+10h]
0x1800021fd  mov     rsi, [rsp+470h+arg_8]
0x180002205  movups  xmmword ptr [rcx], xmm0
0x180002208  mov     [rcx+10h], eax
0x18000220b  mov     ecx, [rbp+370h+var_220]
0x180002211  mov     [rbp+370h+arg_20], r14
0x180002218  test    ecx, ecx
0x18000221a  jz      short loc_18000228E
0x18000221c  sub     ecx, 1
0x18000221f  jz      loc_180002307
0x180002225  cmp     ecx, 1
0x180002228  jnz     loc_180002338
0x18000222e  mov     eax, [rbx+4Ch]
0x180002231  sub     eax, 2C1h
0x180002236  cmp     eax, 6
0x180002239  ja      loc_18000239C
0x18000223f  lea     rcx, [rbx+88h]; lpCriticalSection
0x180002246  call    cs:__imp_EnterCriticalSection
0x18000224c  movups  xmm0, xmmword ptr [rsp+470h+var_444+8]
0x180002251  lea     r8, [rbp+370h+arg_20]; struct _ODB_LEGACY_TASKID_ENTRY **
0x180002258  mov     rcx, rbx; this
0x18000225b  lea     rdx, [rsp+470h+var_458.Data4]; struct _GUID
0x180002260  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x180002265  call    ?GetEntryByForWorkItem@BackgroundExecutionSessionClient@@QEAAJU_GUID@@PEAPEAU_ODB_LEGACY_TASKID_ENTRY@@@Z; BackgroundExecutionSessionClient::GetEntryByForWorkItem(_GUID,_ODB_LEGACY_TASKID_ENTRY * *)
0x18000226a  test    eax, eax
0x18000226c  js      loc_18000238D
0x180002272  mov     rdx, [rbp+370h+arg_20]
0x180002279  cmp     [rdx+24h], r14d
0x18000227d  jnz     loc_18000238D
0x180002283  mov     r8d, 80004004h
0x180002289  jmp     loc_18000237A
0x18000228e  mov     eax, [rbx+4Ch]
0x180002291  sub     eax, 2C1h
0x180002296  cmp     eax, 6
0x180002299  ja      loc_1800023F6
0x18000229f  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800022a6  call    cs:__imp_EnterCriticalSection
0x1800022ac  movups  xmm0, xmmword ptr [rsp+470h+var_444+8]
0x1800022b1  lea     r8, [rbp+370h+arg_20]; struct _ODB_LEGACY_TASKID_ENTRY **
0x1800022b8  mov     rcx, rbx; this
0x1800022bb  lea     rdx, [rsp+470h+var_458.Data4]; struct _GUID
0x1800022c0  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x1800022c5  call    ?GetEntryByForWorkItem@BackgroundExecutionSessionClient@@QEAAJU_GUID@@PEAPEAU_ODB_LEGACY_TASKID_ENTRY@@@Z; BackgroundExecutionSessionClient::GetEntryByForWorkItem(_GUID,_ODB_LEGACY_TASKID_ENTRY * *)
0x1800022ca  test    eax, eax
0x1800022cc  js      loc_18000238D
0x1800022d2  mov     rdx, [rbp+370h+arg_20]
0x1800022d9  lea     r8, [rsp+470h+var_42C]
0x1800022de  mov     dword ptr [rdx+24h], 1
0x1800022e5  mov     rcx, [rbx+68h]
0x1800022e9  mov     edx, [rdx+20h]
0x1800022ec  mov     rax, [rcx]
0x1800022ef  mov     rax, [rax+18h]
0x1800022f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f8  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800022ff  call    cs:__imp_LeaveCriticalSection
0x180002305  jmp     short loc_180002338
0x180002307  mov     rcx, rbx; this
0x18000230a  call    ?IsLegacy@BackgroundExecutionSessionClient@@AEAA_NXZ; BackgroundExecutionSessionClient::IsLegacy(void)
0x18000230f  test    al, al
0x180002311  jnz     loc_1800023C2
0x180002317  mov     rcx, [rbx+70h]
0x18000231b  lea     rdx, [rsp+470h+var_458.Data4]
0x180002320  movups  xmm0, [rbp+370h+var_21C]
0x180002327  mov     rax, [rcx]
0x18000232a  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x18000232f  mov     rax, [rax+20h]
0x180002333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002338  mov     rax, [rbx]
0x18000233b  mov     rcx, rbx
0x18000233e  mov     [rbx+60h], r14d
0x180002342  mov     rax, [rax+10h]
0x180002346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000234b  mov     r14, [rsp+470h+arg_10]
0x180002353  xor     eax, eax
0x180002355  mov     rbx, [rsp+470h+arg_0]
0x18000235d  mov     rdi, [rsp+470h+arg_18]
0x180002365  add     rsp, 470h
0x18000236c  pop     rbp
0x18000236d  retn
0x18000236e  mov     r8d, [rsp+470h+var_42C]
0x180002373  mov     rdx, [rbp+370h+arg_20]
0x18000237a  mov     rcx, [rbx+68h]
0x18000237e  mov     edx, [rdx+20h]
0x180002381  mov     rax, [rcx]
0x180002384  mov     rax, [rax+20h]
0x180002388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000238d  lea     rcx, [rbx+88h]; lpCriticalSection
0x180002394  call    cs:__imp_LeaveCriticalSection
0x18000239a  jmp     short loc_180002338
0x18000239c  mov     rcx, [rbx+70h]
0x1800023a0  lea     rdx, [rsp+470h+var_458.Data4]
0x1800023a5  movups  xmm0, [rbp+370h+var_21C]
0x1800023ac  mov     rax, [rcx]
0x1800023af  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x1800023b4  mov     rax, [rax+28h]
0x1800023b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023bd  jmp     loc_180002338
0x1800023c2  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800023c9  call    cs:__imp_EnterCriticalSection
0x1800023cf  movups  xmm0, xmmword ptr [rsp+470h+var_444+8]
0x1800023d4  lea     r8, [rbp+370h+arg_20]; struct _ODB_LEGACY_TASKID_ENTRY **
0x1800023db  mov     rcx, rbx; this
0x1800023de  lea     rdx, [rsp+470h+var_458.Data4]; struct _GUID
0x1800023e3  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x1800023e8  call    ?GetEntryByForWorkItem@BackgroundExecutionSessionClient@@QEAAJU_GUID@@PEAPEAU_ODB_LEGACY_TASKID_ENTRY@@@Z; BackgroundExecutionSessionClient::GetEntryByForWorkItem(_GUID,_ODB_LEGACY_TASKID_ENTRY * *)
0x1800023ed  test    eax, eax
0x1800023ef  js      short loc_18000238D
0x1800023f1  jmp     loc_18000236E
0x1800023f6  mov     rcx, [rbx+70h]
0x1800023fa  lea     r8, [rsp+470h+var_42C]
0x1800023ff  movups  xmm0, [rbp+370h+var_21C]
0x180002406  lea     rdx, [rsp+470h+var_458.Data4]
0x18000240b  mov     rax, [rcx]
0x18000240e  movaps  xmmword ptr [rsp+470h+var_458.Data4], xmm0
0x180002413  mov     rax, [rax+18h]
0x180002417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000241c  jmp     loc_180002338
0x180002421  mov     eax, 0C0000420h
0x180002426  jmp     loc_18000235D
```
