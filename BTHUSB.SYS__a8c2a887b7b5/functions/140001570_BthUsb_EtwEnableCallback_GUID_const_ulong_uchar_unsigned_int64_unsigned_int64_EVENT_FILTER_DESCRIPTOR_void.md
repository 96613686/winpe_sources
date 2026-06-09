# BthUsb_EtwEnableCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140001570`
- end: `0x1400015e6`
- name: `?BthUsb_EtwEnableCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `118`
- prototype: `ETWENABLECALLBACK`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001570`
- `0x1400015ec`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400015c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400015c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000158a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000158a`

## pseudocode

```c
void __fastcall BthUsb_EtwEnableCallback(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword)
{
  KIRQL v4; // al
  struct _LIST_ENTRY *v5; // rbx
  KIRQL v6; // di

  if ( ControlCode )
  {
    v4 = KeAcquireSpinLockRaiseToDpc(SpinLock);
    v5 = g_PdoLockedList;
    v6 = v4;
    while ( v5 != (struct _LIST_ENTRY *)&g_PdoLockedList && BthUsb_ProcessPdoEtwRundown(0, v5) )
      v5 = v5->Flink;
    KeReleaseSpinLock(SpinLock, v6);
  }
}

```

## disassembly

```asm
0x140001570  test    edx, edx
0x140001572  jz      short locret_1400015E4
0x140001574  mov     [rsp+arg_0], rbx
0x140001579  mov     [rsp+arg_8], rsi
0x14000157e  push    rdi
0x14000157f  sub     rsp, 20h
0x140001583  mov     rcx, cs:SpinLock; SpinLock
0x14000158a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001591  nop     dword ptr [rax+rax+00h]
0x140001596  mov     rbx, cs:?g_PdoLockedList@@3U_LOCKED_LIST@@A; _LOCKED_LIST g_PdoLockedList
0x14000159d  lea     rsi, ?g_PdoLockedList@@3U_LOCKED_LIST@@A; _LOCKED_LIST g_PdoLockedList
0x1400015a4  mov     dil, al
0x1400015a7  jmp     short loc_1400015BA
0x1400015a9  mov     rdx, rbx; struct _LIST_ENTRY *
0x1400015ac  xor     ecx, ecx; void *
0x1400015ae  call    ?BthUsb_ProcessPdoEtwRundown@@YAEPEAXPEAU_LIST_ENTRY@@@Z; BthUsb_ProcessPdoEtwRundown(void *,_LIST_ENTRY *)
0x1400015b3  test    al, al
0x1400015b5  jz      short loc_1400015BF
0x1400015b7  mov     rbx, [rbx]
0x1400015ba  cmp     rbx, rsi
0x1400015bd  jnz     short loc_1400015A9
0x1400015bf  mov     rcx, cs:SpinLock; SpinLock
0x1400015c6  mov     dl, dil; NewIrql
0x1400015c9  call    cs:__imp_KeReleaseSpinLock
0x1400015d0  nop     dword ptr [rax+rax+00h]
0x1400015d5  mov     rbx, [rsp+28h+arg_0]
0x1400015da  mov     rsi, [rsp+28h+arg_8]
0x1400015df  add     rsp, 20h
0x1400015e3  pop     rdi
0x1400015e4  retn
```
