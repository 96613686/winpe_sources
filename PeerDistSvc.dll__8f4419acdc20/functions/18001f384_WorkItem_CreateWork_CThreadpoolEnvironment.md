# WorkItem::CreateWork(CThreadpoolEnvironment *)

- ea: `0x18001f384`
- end: `0x18001f405`
- name: `?CreateWork@WorkItem@@QEAAXPEAVCThreadpoolEnvironment@@@Z`
- size: `129`
- prototype: `void __fastcall(PVOID pv, struct CThreadpoolEnvironment *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001ed30`
- `0x180099ba4`
- `0x18009b230`
- `0x18010d7d0`
- `0x18010e6e8`
- `0x180112930`

## callees

- `0x180018d3c`
- `0x18001f384`
- `0x180020058`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001f3ab`
- `ntdll!EtwEventActivityIdControl` at `0x18001f3ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f3cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f3cc`

## string_xrefs

- `0x18001f3db`: `WorkItem - CreateThreadpoolWork`
- `0x18001f3ed`: `WorkItem - CreateWork() called on a WorkItem which had already been initialized`

## pseudocode

```c
void __fastcall WorkItem::CreateWork(char *pv, struct CThreadpoolEnvironment *a2)
{
  PTP_WORK ThreadpoolWork; // rax

  if ( *(_OWORD *)(pv + 24) != 0 )
    ApplicationError::Throw(
      L"WorkItem - CreateWork() called on a WorkItem which had already been initialized",
      -2147023649);
  EtwEventActivityIdControl(1, pv + 8);
  *((_QWORD *)pv + 4) = a2;
  ThreadpoolWork = CreateThreadpoolWork(
                     WorkItem::StartRoutine,
                     pv,
                     (PTP_CALLBACK_ENVIRON)(((unsigned __int64)a2 + 16) & -(__int64)(a2 != 0)));
  *((_QWORD *)pv + 3) = ThreadpoolWork;
  if ( !ThreadpoolWork )
    SystemError::Throw(L"WorkItem - CreateThreadpoolWork");
}

```

## disassembly

```asm
0x18001f384  mov     [rsp+arg_0], rbx
0x18001f389  push    rdi
0x18001f38a  sub     rsp, 20h
0x18001f38e  cmp     qword ptr [rcx+20h], 0
0x18001f393  mov     rdi, rdx
0x18001f396  mov     rbx, rcx
0x18001f399  jnz     short loc_18001F3E8
0x18001f39b  cmp     qword ptr [rcx+18h], 0
0x18001f3a0  jnz     short loc_18001F3E8
0x18001f3a2  lea     rdx, [rcx+8]
0x18001f3a6  mov     ecx, 1
0x18001f3ab  call    cs:__imp_EtwEventActivityIdControl
0x18001f3b1  lea     rax, [rdi+10h]
0x18001f3b5  mov     [rbx+20h], rdi
0x18001f3b9  neg     rdi
0x18001f3bc  lea     rcx, ?StartRoutine@WorkItem@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAV1@PEAU_TP_WORK@@@Z; pfnwk
0x18001f3c3  mov     rdx, rbx; pv
0x18001f3c6  sbb     r8, r8
0x18001f3c9  and     r8, rax; pcbe
0x18001f3cc  call    cs:__imp_CreateThreadpoolWork
0x18001f3d2  mov     [rbx+18h], rax
0x18001f3d6  test    rax, rax
0x18001f3d9  jnz     short loc_18001F3FA
0x18001f3db  lea     rcx, aWorkitemCreate_0; "WorkItem - CreateThreadpoolWork"
0x18001f3e2  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001f3e8  mov     edx, 800704DFh; int
0x18001f3ed  lea     rcx, aWorkitemCreate; "WorkItem - CreateWork() called on a Wor"...
0x18001f3f4  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x18001f3fa  mov     rbx, [rsp+28h+arg_0]
0x18001f3ff  add     rsp, 20h
0x18001f403  pop     rdi
0x18001f404  retn
```
