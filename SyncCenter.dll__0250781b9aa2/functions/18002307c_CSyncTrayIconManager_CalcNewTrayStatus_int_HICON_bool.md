# CSyncTrayIconManager::_CalcNewTrayStatus(int *,HICON__ * *,bool *)

- ea: `0x18002307c`
- end: `0x1800232b2`
- name: `?_CalcNewTrayStatus@CSyncTrayIconManager@@AEAAXPEAHPEAPEAUHICON__@@PEA_N@Z`
- size: `566`
- prototype: `void __fastcall(CSyncTrayIconManager *__hidden this, int *, HICON *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800235e8`

## callees

- `0x18002307c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800230c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800230c4`
- `USER32!KillTimer` at `0x180023255`
- `USER32!KillTimer` at `0x180023255`
- `USER32!SetTimer` at `0x1800231ed`
- `USER32!SetTimer` at `0x1800231ed`

## pseudocode

```c
void __fastcall CSyncTrayIconManager::_CalcNewTrayStatus(CSyncTrayIconManager *this, int *a2, HICON *a3, bool *a4)
{
  _QWORD *v4; // r14
  HRESULT Instance; // esi
  int *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edi
  int v15; // ecx
  int v16; // eax

  v4 = (_QWORD *)((char *)this + 56);
  Instance = 0;
  *a4 = 0;
  if ( !*((_QWORD *)this + 7) )
  {
    Instance = CoCreateInstance(
                 &CLSID_SyncMgrAggregateStatus,
                 0,
                 0x15u,
                 &GUID_f566e43e_7497_4102_94ef_5f16500b2ef5,
                 (LPVOID *)this + 7);
    if ( Instance < 0 )
      goto LABEL_18;
    if ( !*((_DWORD *)this + 8) )
      (*(void (__fastcall **)(_QWORD, CSyncTrayIconManager *, __int64))(*(_QWORD *)*v4 + 64LL))(*v4, this, 1);
  }
  if ( *((_BYTE *)this + 37) == 1 || !*((_BYTE *)this + 36) )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 24LL))(*v4, &dword_18007017C);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 32LL))(*v4, &dword_180070DCC);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 40LL))(*v4, &dword_180070DC8);
    }
  }
  v10 = (int *)((char *)this + 44);
  if ( Instance == -2147023174 )
  {
    v11 = 1;
    dword_18007017C = 1;
LABEL_15:
    if ( *v10 != v11 )
      *a4 = 1;
    goto LABEL_17;
  }
  v11 = dword_18007017C;
  if ( *v10 != dword_18007017C )
  {
    if ( dword_18007017C == 14 )
    {
      (*(void (__fastcall **)(_QWORD, HICON *))(*(_QWORD *)*v4 + 56LL))(*v4, a3);
      v11 = dword_18007017C;
    }
    goto LABEL_15;
  }
LABEL_17:
  *v10 = v11;
LABEL_18:
  if ( dword_18007017C >= 2 )
  {
    *((_BYTE *)this + 38) = 1;
  }
  else
  {
    v12 = *v4;
    *((_BYTE *)this + 38) = 0;
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      *v4 = 0;
    }
  }
  v13 = dword_18007017C;
  if ( dword_18007017C < 10 || dword_18007017C == 14 )
  {
    if ( *((_BYTE *)this + 36) == 1 )
    {
      KillTimer(*((HWND *)this + 3), 3u);
      *((_BYTE *)this + 36) = 0;
      v13 = dword_18007017C;
    }
    if ( dword_180070DC8 )
    {
      v15 = 1240;
    }
    else if ( dword_180070DCC )
    {
      v15 = 1260;
    }
    else
    {
      v15 = 1220;
      if ( v13 == 5 )
        v15 = 1229;
    }
  }
  else
  {
    v14 = *((_DWORD *)this + 10);
    if ( !*((_BYTE *)this + 36) )
    {
      SetTimer(*((HWND *)this + 3), 3u, 0x1F4u, 0);
      *((_BYTE *)this + 36) = 1;
    }
    v15 = v14 + 1;
    if ( dword_180070DC8 )
    {
      if ( (unsigned int)(v14 - 1240) > 7 )
        v15 = 1241;
    }
    else if ( dword_180070DCC )
    {
      if ( (unsigned int)(v14 - 1260) > 7 )
        v15 = 1261;
    }
    else if ( (unsigned int)(v14 - 1220) > 7 )
    {
      v15 = 1221;
    }
  }
  v16 = 0;
  if ( !*a3 )
    v16 = v15;
  *a2 = v16;
}

```

## disassembly

```asm
0x18002307c  push    rbx
0x18002307e  push    rbp
0x18002307f  push    rsi
0x180023080  push    rdi
0x180023081  push    r12
0x180023083  push    r13
0x180023085  push    r14
0x180023087  push    r15
0x180023089  sub     rsp, 38h
0x18002308d  xor     r13d, r13d
0x180023090  lea     r14, [rcx+38h]
0x180023094  mov     r15, r9
0x180023097  mov     rbp, r8
0x18002309a  mov     r12, rdx
0x18002309d  mov     rbx, rcx
0x1800230a0  mov     esi, r13d
0x1800230a3  mov     [r9], r13b
0x1800230a6  cmp     [r14], r13
0x1800230a9  jnz     short loc_1800230F3
0x1800230ab  lea     r9, _GUID_f566e43e_7497_4102_94ef_5f16500b2ef5; riid
0x1800230b2  mov     [rsp+78h+ppv], r14; ppv
0x1800230b7  xor     edx, edx; pUnkOuter
0x1800230b9  lea     r8d, [r13+15h]; dwClsContext
0x1800230bd  lea     rcx, CLSID_SyncMgrAggregateStatus; rclsid
0x1800230c4  call    cs:__imp_CoCreateInstance
0x1800230ca  mov     esi, eax
0x1800230cc  test    eax, eax
0x1800230ce  js      loc_180023199
0x1800230d4  lea     r9, [rbx+20h]
0x1800230d8  cmp     [r9], r13d
0x1800230db  jnz     short loc_1800230F3
0x1800230dd  mov     rcx, [r14]
0x1800230e0  lea     r8d, [r13+1]
0x1800230e4  mov     rdx, [rcx]
0x1800230e7  mov     rax, [rdx+40h]
0x1800230eb  mov     rdx, rbx
0x1800230ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230f3  cmp     byte ptr [rbx+25h], 1
0x1800230f7  jz      short loc_1800230FF
0x1800230f9  cmp     [rbx+24h], r13b
0x1800230fd  jnz     short loc_18002314F
0x1800230ff  mov     rcx, [r14]
0x180023102  lea     rdx, dword_18007017C
0x180023109  mov     rax, [rcx]
0x18002310c  mov     rax, [rax+18h]
0x180023110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023115  mov     esi, eax
0x180023117  test    eax, eax
0x180023119  js      short loc_18002314F
0x18002311b  mov     rcx, [r14]
0x18002311e  lea     rdx, dword_180070DCC
0x180023125  mov     rax, [rcx]
0x180023128  mov     rax, [rax+20h]
0x18002312c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023131  mov     esi, eax
0x180023133  test    eax, eax
0x180023135  js      short loc_18002314F
0x180023137  mov     rcx, [r14]
0x18002313a  lea     rdx, dword_180070DC8
0x180023141  mov     rax, [rcx]
0x180023144  mov     rax, [rax+28h]
0x180023148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002314d  mov     esi, eax
0x18002314f  lea     rdi, [rbx+2Ch]
0x180023153  cmp     esi, 800706BAh
0x180023159  jnz     short loc_180023168
0x18002315b  mov     eax, 1
0x180023160  mov     cs:dword_18007017C, eax
0x180023166  jmp     short loc_18002318F
0x180023168  mov     eax, cs:dword_18007017C
0x18002316e  cmp     [rdi], eax
0x180023170  jz      short loc_180023197
0x180023172  cmp     eax, 0Eh
0x180023175  jnz     short loc_18002318F
0x180023177  mov     rcx, [r14]
0x18002317a  mov     rdx, rbp
0x18002317d  mov     rax, [rcx]
0x180023180  mov     rax, [rax+38h]
0x180023184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023189  mov     eax, cs:dword_18007017C
0x18002318f  cmp     [rdi], eax
0x180023191  jz      short loc_180023197
0x180023193  mov     byte ptr [r15], 1
0x180023197  mov     [rdi], eax
0x180023199  cmp     cs:dword_18007017C, 2
0x1800231a0  jge     short loc_1800231BF
0x1800231a2  mov     rcx, [r14]
0x1800231a5  mov     [rbx+26h], r13b
0x1800231a9  test    rcx, rcx
0x1800231ac  jz      short loc_1800231C3
0x1800231ae  mov     rax, [rcx]
0x1800231b1  mov     rax, [rax+10h]
0x1800231b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ba  mov     [r14], r13
0x1800231bd  jmp     short loc_1800231C3
0x1800231bf  mov     byte ptr [rbx+26h], 1
0x1800231c3  mov     eax, cs:dword_18007017C
0x1800231c9  cmp     eax, 0Ah
0x1800231cc  jl      short loc_180023246
0x1800231ce  cmp     eax, 0Eh
0x1800231d1  jz      short loc_180023246
0x1800231d3  mov     edi, [rbx+28h]
0x1800231d6  cmp     [rbx+24h], r13b
0x1800231da  jnz     short loc_1800231F7
0x1800231dc  mov     rcx, [rbx+18h]; hWnd
0x1800231e0  xor     r9d, r9d; lpTimerFunc
0x1800231e3  mov     r8d, 1F4h; uElapse
0x1800231e9  lea     edx, [r9+3]; nIDEvent
0x1800231ed  call    cs:__imp_SetTimer
0x1800231f3  mov     byte ptr [rbx+24h], 1
0x1800231f7  cmp     cs:dword_180070DC8, r13d
0x1800231fe  lea     ecx, [rdi+1]
0x180023201  jz      short loc_180023219
0x180023203  lea     eax, [rcx-4D9h]
0x180023209  cmp     eax, 7
0x18002320c  jbe     loc_180023293
0x180023212  mov     ecx, 4D9h
0x180023217  jmp     short loc_180023293
0x180023219  cmp     cs:dword_180070DCC, r13d
0x180023220  jz      short loc_180023234
0x180023222  lea     eax, [rcx-4EDh]
0x180023228  cmp     eax, 7
0x18002322b  jbe     short loc_180023293
0x18002322d  mov     ecx, 4EDh
0x180023232  jmp     short loc_180023293
0x180023234  lea     eax, [rcx-4C5h]
0x18002323a  cmp     eax, 7
0x18002323d  jbe     short loc_180023293
0x18002323f  mov     ecx, 4C5h
0x180023244  jmp     short loc_180023293
0x180023246  cmp     byte ptr [rbx+24h], 1
0x18002324a  jnz     short loc_180023265
0x18002324c  mov     rcx, [rbx+18h]; hWnd
0x180023250  mov     edx, 3; uIDEvent
0x180023255  call    cs:__imp_KillTimer
0x18002325b  mov     [rbx+24h], r13b
0x18002325f  mov     eax, cs:dword_18007017C
0x180023265  cmp     cs:dword_180070DC8, r13d
0x18002326c  jz      short loc_180023275
0x18002326e  mov     ecx, 4D8h
0x180023273  jmp     short loc_180023293
0x180023275  cmp     cs:dword_180070DCC, r13d
0x18002327c  jz      short loc_180023285
0x18002327e  mov     ecx, 4ECh
0x180023283  jmp     short loc_180023293
0x180023285  mov     ecx, 4C4h
0x18002328a  cmp     eax, 5
0x18002328d  lea     edx, [rcx+9]
0x180023290  cmovz   ecx, edx
0x180023293  cmp     [rbp+0], r13
0x180023297  mov     eax, r13d
0x18002329a  cmovz   eax, ecx
0x18002329d  mov     [r12], eax
0x1800232a1  add     rsp, 38h
0x1800232a5  pop     r15
0x1800232a7  pop     r14
0x1800232a9  pop     r13
0x1800232ab  pop     r12
0x1800232ad  pop     rdi
0x1800232ae  pop     rsi
0x1800232af  pop     rbp
0x1800232b0  pop     rbx
0x1800232b1  retn
```
