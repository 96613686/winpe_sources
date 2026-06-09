# Apx::ApfCircuitFactory_IpcReadyProcess::Process(Apx::ApfWorkItemQueue *)

- ea: `0x180011910`
- end: `0x180011ab2`
- name: `?Process@ApfCircuitFactory_IpcReadyProcess@Apx@@UEAAXPEAVApfWorkItemQueue@2@@Z`
- size: `418`
- prototype: `void __fastcall(Apx::ApfCircuitFactory_IpcReadyProcess *__hidden this, struct Apx::ApfWorkItemQueue *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x180010a84`
- `0x180010f8c`
- `0x180011910`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011961`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011961`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a4c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011a99`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011a99`

## pseudocode

```c
void __fastcall Apx::ApfCircuitFactory_IpcReadyProcess::Process(
        Apx::ApfCircuitFactory_IpcReadyProcess *this,
        struct Apx::ApfWorkItemQueue *a2)
{
  __int64 v2; // rbx
  char v4; // bp
  __int64 v5; // rax
  void (__fastcall *v6)(__int64); // rax
  __int64 v7; // rax
  void (__fastcall *v8)(__int64); // rax
  void *v9; // rcx

  v2 = *((_QWORD *)this + 1);
  v4 = *((_BYTE *)this + 16);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  if ( *(_DWORD *)(v2 + 20) == 3 )
  {
    if ( v4 )
    {
      v7 = *(unsigned int *)(v2 + 56);
      *(_DWORD *)(v2 + 20) = 4;
      *(_DWORD *)(v2 + 4 * v7 + 24) = 4;
      if ( ++*(_DWORD *)(v2 + 56) >= 8u )
        *(_DWORD *)(v2 + 56) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
      v8 = *(void (__fastcall **)(__int64))(v2 + 152);
      if ( v8 )
        v8(~v2);
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
      Apx::ApfCircuitFactory::ActivateCircuitsLocked((Apx::ApfCircuitFactory *)v2);
    }
  }
  else if ( *(_DWORD *)(v2 + 20) == 4 && !v4 )
  {
    v5 = *(unsigned int *)(v2 + 56);
    *(_DWORD *)(v2 + 20) = 3;
    *(_DWORD *)(v2 + 4 * v5 + 24) = 3;
    if ( ++*(_DWORD *)(v2 + 56) >= 8u )
      *(_DWORD *)(v2 + 56) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
    v6 = *(void (__fastcall **)(__int64))(v2 + 160);
    if ( v6 )
      v6(~v2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
    Apx::ApfCircuitFactory::DeactivateCircuitsLocked((Apx::ApfCircuitFactory *)v2);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  v9 = (void *)*((_QWORD *)this + 3);
  if ( v9 )
  {
    SetEvent(v9);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180011910  push    rbx
0x180011912  push    rbp
0x180011913  push    rsi
0x180011914  push    rdi
0x180011915  push    r12
0x180011917  sub     rsp, 20h
0x18001191b  mov     rbx, [rcx+8]
0x18001191f  mov     rsi, rcx
0x180011922  movzx   ebp, byte ptr [rcx+10h]
0x180011926  mov     rcx, cs:WPP_GLOBAL_Control
0x18001192d  lea     r12, WPP_GLOBAL_Control
0x180011934  cmp     rcx, r12
0x180011937  jz      short loc_18001195A
0x180011939  test    byte ptr [rcx+1Ch], 1
0x18001193d  jz      short loc_18001195A
0x18001193f  cmp     byte ptr [rcx+19h], 5
0x180011943  jb      short loc_18001195A
0x180011945  mov     rcx, [rcx+10h]
0x180011949  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011950  mov     edx, 32h ; '2'
0x180011955  call    WPP_SF_
0x18001195a  lea     rdi, [rbx+40h]
0x18001195e  mov     rcx, rdi; lpCriticalSection
0x180011961  call    cs:__imp_EnterCriticalSection
0x180011967  mov     rcx, cs:WPP_GLOBAL_Control
0x18001196e  cmp     rcx, r12
0x180011971  jz      short loc_180011997
0x180011973  test    byte ptr [rcx+1Ch], 80h
0x180011977  jz      short loc_180011997
0x180011979  cmp     byte ptr [rcx+19h], 4
0x18001197d  jb      short loc_180011997
0x18001197f  mov     rcx, [rcx+10h]
0x180011983  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x18001198a  mov     r9d, ebp
0x18001198d  mov     edx, 33h ; '3'
0x180011992  call    WPP_SF_d
0x180011997  mov     ecx, [rbx+14h]
0x18001199a  mov     edx, 3
0x18001199f  sub     ecx, edx
0x1800119a1  jz      short loc_180011A02
0x1800119a3  cmp     ecx, 1
0x1800119a6  jnz     loc_180011A5A
0x1800119ac  test    bpl, bpl
0x1800119af  jnz     loc_180011A5A
0x1800119b5  mov     eax, [rbx+38h]
0x1800119b8  mov     [rbx+14h], edx
0x1800119bb  mov     [rbx+rax*4+18h], edx
0x1800119bf  inc     dword ptr [rbx+38h]
0x1800119c2  cmp     dword ptr [rbx+38h], 8
0x1800119c6  jb      short loc_1800119CF
0x1800119c8  mov     dword ptr [rbx+38h], 0
0x1800119cf  mov     rcx, rdi; lpCriticalSection
0x1800119d2  call    cs:__imp_LeaveCriticalSection
0x1800119d8  mov     rax, [rbx+0A0h]
0x1800119df  test    rax, rax
0x1800119e2  jz      short loc_1800119EF
0x1800119e4  mov     rcx, rbx
0x1800119e7  not     rcx
0x1800119ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ef  mov     rcx, rdi; lpCriticalSection
0x1800119f2  call    cs:__imp_EnterCriticalSection
0x1800119f8  mov     rcx, rbx; this
0x1800119fb  call    ?DeactivateCircuitsLocked@ApfCircuitFactory@Apx@@AEAAXXZ; Apx::ApfCircuitFactory::DeactivateCircuitsLocked(void)
0x180011a00  jmp     short loc_180011A5A
0x180011a02  test    bpl, bpl
0x180011a05  jz      short loc_180011A5A
0x180011a07  mov     eax, [rbx+38h]
0x180011a0a  mov     dword ptr [rbx+14h], 4
0x180011a11  mov     dword ptr [rbx+rax*4+18h], 4
0x180011a19  inc     dword ptr [rbx+38h]
0x180011a1c  cmp     dword ptr [rbx+38h], 8
0x180011a20  jb      short loc_180011A29
0x180011a22  mov     dword ptr [rbx+38h], 0
0x180011a29  mov     rcx, rdi; lpCriticalSection
0x180011a2c  call    cs:__imp_LeaveCriticalSection
0x180011a32  mov     rax, [rbx+98h]
0x180011a39  test    rax, rax
0x180011a3c  jz      short loc_180011A49
0x180011a3e  mov     rcx, rbx
0x180011a41  not     rcx
0x180011a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a49  mov     rcx, rdi; lpCriticalSection
0x180011a4c  call    cs:__imp_EnterCriticalSection
0x180011a52  mov     rcx, rbx; this
0x180011a55  call    ?ActivateCircuitsLocked@ApfCircuitFactory@Apx@@AEAAXXZ; Apx::ApfCircuitFactory::ActivateCircuitsLocked(void)
0x180011a5a  mov     rcx, rdi; lpCriticalSection
0x180011a5d  call    cs:__imp_LeaveCriticalSection
0x180011a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a6a  cmp     rcx, r12
0x180011a6d  jz      short loc_180011A90
0x180011a6f  test    byte ptr [rcx+1Ch], 1
0x180011a73  jz      short loc_180011A90
0x180011a75  cmp     byte ptr [rcx+19h], 5
0x180011a79  jb      short loc_180011A90
0x180011a7b  mov     rcx, [rcx+10h]
0x180011a7f  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011a86  mov     edx, 34h ; '4'
0x180011a8b  call    WPP_SF_
0x180011a90  mov     rcx, [rsi+18h]; hEvent
0x180011a94  test    rcx, rcx
0x180011a97  jz      short loc_180011AA7
0x180011a99  call    cs:__imp_SetEvent
0x180011a9f  mov     qword ptr [rsi+18h], 0
0x180011aa7  add     rsp, 20h
0x180011aab  pop     r12
0x180011aad  pop     rdi
0x180011aae  pop     rsi
0x180011aaf  pop     rbp
0x180011ab0  pop     rbx
0x180011ab1  retn
```
