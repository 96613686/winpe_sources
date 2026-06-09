# _DualEngineBrokerCallAsfwAndWait(ulong)

- ea: `0x180881070`
- end: `0x180881367`
- name: `?_DualEngineBrokerCallAsfwAndWait@@YA_NK@Z`
- size: `759`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1808814f0`

## callees

- `0x18028ecdc`
- `0x180881070`
- `0x180881370`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18088109a`
- `KERNEL32!GetCurrentThreadId` at `0x18088109a`
- `KERNEL32!CloseHandle` at `0x180881334`
- `KERNEL32!CloseHandle` at `0x180881334`
- `USER32!AllowSetForegroundWindow` at `0x180881136`
- `USER32!AllowSetForegroundWindow` at `0x180881249`
- `USER32!AllowSetForegroundWindow` at `0x180881136`
- `USER32!AllowSetForegroundWindow` at `0x180881249`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808810ff`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180881212`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808810ff`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180881212`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x18088132a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x18088132a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808811b7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808812c6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808811b7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808812c6`

## pseudocode

```c
__int64 __fastcall _DualEngineBrokerCallAsfwAndWait(unsigned int a1)
{
  unsigned __int8 v2; // di
  DWORD CurrentThreadId; // eax
  DWORD v4; // ecx
  int v5; // ebx
  void (__fastcall *v6)(__int64, __int128 *); // rbx
  int v7; // ebx
  void (*v8)(void); // rax
  DWORD v9; // ecx
  int v10; // ebx
  void (__fastcall *v11)(__int64, __int128 *); // rbx
  DWORD dwProcessId; // [rsp+30h] [rbp-79h] BYREF
  __int64 v14; // [rsp+38h] [rbp-71h] BYREF
  struct IEUserBroker *v15; // [rsp+40h] [rbp-69h] BYREF
  DWORD dwindex; // [rsp+48h] [rbp-61h] BYREF
  __int128 v17; // [rsp+50h] [rbp-59h] BYREF
  HANDLE pHandles; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 v19[64]; // [rsp+70h] [rbp-39h] BYREF

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)StringCchPrintfW(v19, 0x40u, L"_%d", CurrentThreadId) >= 0 )
  {
    pHandles = _DualEngineCreateWaitEvent(a1, 1, v19);
    if ( pHandles )
    {
      dwindex = 0;
      if ( a1 == 5153 )
      {
        v14 = 0;
        v15 = 0;
        if ( (int)CoCreateUserBroker(&v15) < 0 )
          goto LABEL_21;
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          0,
          &dwProcessId);
        v4 = -1;
        if ( dwProcessId )
          v4 = dwProcessId;
        AllowSetForegroundWindow(v4);
        *(_QWORD *)&v17 = 0;
        v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
               v15,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v17);
        if ( v5 >= 0 )
        {
          v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v17)(
                 v17,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 &v14);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v5 < 0 )
          goto LABEL_21;
        v6 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 56LL);
        v17 = *(_OWORD *)GlobalThreadState();
        v6(v14, &v17);
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v14 + 80LL))(v14, v19);
        v8 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
      }
      else
      {
        if ( a1 != 5154 )
          goto LABEL_21;
        v14 = 0;
        v15 = 0;
        if ( (int)CoCreateUserBroker(&v15) < 0 )
          goto LABEL_21;
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          0,
          &dwProcessId);
        v9 = -1;
        if ( dwProcessId )
          v9 = dwProcessId;
        AllowSetForegroundWindow(v9);
        *(_QWORD *)&v17 = 0;
        v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
                v15,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v17);
        if ( v10 >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v17)(
                  v17,
                  &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                  &v14);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v10 < 0 )
          goto LABEL_21;
        v11 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 56LL);
        v17 = *(_OWORD *)GlobalThreadState();
        v11(v14, &v17);
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v14 + 88LL))(v14, v19);
        v8 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
      }
      v8();
      if ( v7 >= 0 )
      {
        v2 = 1;
        CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      }
LABEL_21:
      CloseHandle(pHandles);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180881070  mov     [rsp-8+arg_10], rbx
0x180881075  mov     [rsp-8+arg_18], rdi
0x18088107a  push    rbp
0x18088107b  lea     rbp, [rsp-57h]
0x180881080  sub     rsp, 100h
0x180881087  mov     rax, cs:__security_cookie
0x18088108e  xor     rax, rsp
0x180881091  mov     [rbp+57h+var_10], rax
0x180881095  mov     ebx, ecx
0x180881097  xor     dil, dil
0x18088109a  call    cs:__imp_GetCurrentThreadId
0x1808810a0  lea     r8, aD_0; "_%d"
0x1808810a7  mov     edx, 40h ; '@'; unsigned __int64
0x1808810ac  mov     r9d, eax
0x1808810af  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x1808810b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808810b8  test    eax, eax
0x1808810ba  js      loc_180881342
0x1808810c0  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1808810c4  mov     dl, 1; bool
0x1808810c6  mov     ecx, ebx; unsigned int
0x1808810c8  call    ?_DualEngineCreateWaitEvent@@YAPEAXK_NPEBG@Z; _DualEngineCreateWaitEvent(ulong,bool,ushort const *)
0x1808810cd  mov     [rbp+57h+pHandles], rax
0x1808810d1  test    rax, rax
0x1808810d4  jz      loc_180881342
0x1808810da  mov     [rsp+100h+arg_8], rsi
0x1808810e2  xor     esi, esi
0x1808810e4  mov     [rbp+57h+dwindex], esi
0x1808810e7  cmp     ebx, 1421h
0x1808810ed  jnz     loc_1808811FA
0x1808810f3  lea     rcx, [rbp+57h+var_C0]
0x1808810f7  mov     [rbp+57h+var_C8], rsi
0x1808810fb  mov     [rbp+57h+var_C0], rsi
0x1808810ff  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180881105  test    eax, eax
0x180881107  js      loc_180881330
0x18088110d  mov     rcx, [rbp+57h+var_C0]
0x180881111  lea     r9, [rbp+57h+dwProcessId]
0x180881115  mov     [rbp+57h+dwProcessId], esi
0x180881118  xor     r8d, r8d
0x18088111b  xor     edx, edx
0x18088111d  mov     rax, [rcx]
0x180881120  mov     rax, [rax+18h]
0x180881124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881129  mov     eax, [rbp+57h+dwProcessId]
0x18088112c  mov     ecx, 0FFFFFFFFh
0x180881131  test    eax, eax
0x180881133  cmovnz  ecx, eax; dwProcessId
0x180881136  call    cs:__imp_AllowSetForegroundWindow
0x18088113c  mov     rcx, [rbp+57h+var_C0]
0x180881140  lea     r9, [rbp+57h+var_B0]
0x180881144  mov     qword ptr [rbp+57h+var_B0], rsi
0x180881148  lea     r8, IID_IUnknown
0x18088114f  lea     rdx, CLSID_CShdocvwBroker
0x180881156  mov     rax, [rcx]
0x180881159  mov     rax, [rax+30h]
0x18088115d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881162  mov     ebx, eax
0x180881164  test    eax, eax
0x180881166  js      short loc_180881194
0x180881168  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18088116c  lea     r8, [rbp+57h+var_C8]
0x180881170  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180881177  mov     rax, [rcx]
0x18088117a  mov     rax, [rax]
0x18088117d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881182  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180881186  mov     ebx, eax
0x180881188  mov     rax, [rcx]
0x18088118b  mov     rax, [rax+10h]
0x18088118f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881194  mov     rcx, [rbp+57h+var_C0]
0x180881198  mov     rax, [rcx]
0x18088119b  mov     rax, [rax+10h]
0x18088119f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808811a4  test    ebx, ebx
0x1808811a6  js      loc_180881330
0x1808811ac  mov     rax, [rbp+57h+var_C8]
0x1808811b0  mov     rcx, [rax]
0x1808811b3  mov     rbx, [rcx+38h]
0x1808811b7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808811bd  mov     rcx, [rbp+57h+var_C8]
0x1808811c1  lea     rdx, [rbp+57h+var_B0]
0x1808811c5  movups  xmm0, xmmword ptr [rax]
0x1808811c8  mov     rax, rbx
0x1808811cb  movaps  [rbp+57h+var_B0], xmm0
0x1808811cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808811d4  mov     rcx, [rbp+57h+var_C8]
0x1808811d8  lea     rdx, [rbp+57h+var_90]
0x1808811dc  mov     rax, [rcx]
0x1808811df  mov     rax, [rax+50h]
0x1808811e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808811e8  mov     rcx, [rbp+57h+var_C8]
0x1808811ec  mov     ebx, eax
0x1808811ee  mov     r8, [rcx]
0x1808811f1  mov     rax, [r8+10h]
0x1808811f5  jmp     loc_180881304
0x1808811fa  cmp     ebx, 1422h
0x180881200  jnz     loc_180881330
0x180881206  lea     rcx, [rbp+57h+var_C0]
0x18088120a  mov     [rbp+57h+var_C8], rsi
0x18088120e  mov     [rbp+57h+var_C0], rsi
0x180881212  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180881218  test    eax, eax
0x18088121a  js      loc_180881330
0x180881220  mov     rcx, [rbp+57h+var_C0]
0x180881224  lea     r9, [rbp+57h+dwProcessId]
0x180881228  mov     [rbp+57h+dwProcessId], esi
0x18088122b  xor     r8d, r8d
0x18088122e  xor     edx, edx
0x180881230  mov     rax, [rcx]
0x180881233  mov     rax, [rax+18h]
0x180881237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18088123c  mov     eax, [rbp+57h+dwProcessId]
0x18088123f  mov     ecx, 0FFFFFFFFh
0x180881244  test    eax, eax
0x180881246  cmovnz  ecx, eax; dwProcessId
0x180881249  call    cs:__imp_AllowSetForegroundWindow
0x18088124f  mov     rcx, [rbp+57h+var_C0]
0x180881253  lea     r9, [rbp+57h+var_B0]
0x180881257  mov     qword ptr [rbp+57h+var_B0], rsi
0x18088125b  lea     r8, IID_IUnknown
0x180881262  lea     rdx, CLSID_CShdocvwBroker
0x180881269  mov     rax, [rcx]
0x18088126c  mov     rax, [rax+30h]
0x180881270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881275  mov     ebx, eax
0x180881277  test    eax, eax
0x180881279  js      short loc_1808812A7
0x18088127b  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18088127f  lea     r8, [rbp+57h+var_C8]
0x180881283  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18088128a  mov     rax, [rcx]
0x18088128d  mov     rax, [rax]
0x180881290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881295  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180881299  mov     ebx, eax
0x18088129b  mov     rax, [rcx]
0x18088129e  mov     rax, [rax+10h]
0x1808812a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808812a7  mov     rcx, [rbp+57h+var_C0]
0x1808812ab  mov     rax, [rcx]
0x1808812ae  mov     rax, [rax+10h]
0x1808812b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808812b7  test    ebx, ebx
0x1808812b9  js      short loc_180881330
0x1808812bb  mov     rax, [rbp+57h+var_C8]
0x1808812bf  mov     rcx, [rax]
0x1808812c2  mov     rbx, [rcx+38h]
0x1808812c6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808812cc  mov     rcx, [rbp+57h+var_C8]
0x1808812d0  lea     rdx, [rbp+57h+var_B0]
0x1808812d4  movups  xmm0, xmmword ptr [rax]
0x1808812d7  mov     rax, rbx
0x1808812da  movaps  [rbp+57h+var_B0], xmm0
0x1808812de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808812e3  mov     rcx, [rbp+57h+var_C8]
0x1808812e7  lea     rdx, [rbp+57h+var_90]
0x1808812eb  mov     rax, [rcx]
0x1808812ee  mov     rax, [rax+58h]
0x1808812f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808812f7  mov     rcx, [rbp+57h+var_C8]
0x1808812fb  mov     ebx, eax
0x1808812fd  mov     rdx, [rcx]
0x180881300  mov     rax, [rdx+10h]
0x180881304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180881309  test    ebx, ebx
0x18088130b  js      short loc_180881330
0x18088130d  lea     rax, [rbp+57h+dwindex]
0x180881311  mov     r8d, 1; cHandles
0x180881317  lea     r9, [rbp+57h+pHandles]; pHandles
0x18088131b  mov     [rsp+100h+lpdwindex], rax; lpdwindex
0x180881320  mov     edx, 0FFFFFFFFh; dwTimeout
0x180881325  xor     ecx, ecx; dwFlags
0x180881327  mov     dil, 1
0x18088132a  call    cs:__imp_CoWaitForMultipleHandles
0x180881330  mov     rcx, [rbp+57h+pHandles]; hObject
0x180881334  call    cs:__imp_CloseHandle
0x18088133a  mov     rsi, [rsp+100h+arg_8]
0x180881342  movzx   eax, dil
0x180881346  mov     rcx, [rbp+57h+var_10]
0x18088134a  xor     rcx, rsp; StackCookie
0x18088134d  call    __security_check_cookie
0x180881352  lea     r11, [rsp+100h+var_s0]
0x18088135a  mov     rbx, [r11+20h]
0x18088135e  mov     rdi, [r11+28h]
0x180881362  mov     rsp, r11
0x180881365  pop     rbp
0x180881366  retn
```
