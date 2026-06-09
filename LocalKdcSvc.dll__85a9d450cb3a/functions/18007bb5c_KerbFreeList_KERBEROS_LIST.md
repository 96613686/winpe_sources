# KerbFreeList(_KERBEROS_LIST *)

- ea: `0x18007bb5c`
- end: `0x18007bb82`
- name: `?KerbFreeList@@YAXPEAU_KERBEROS_LIST@@@Z`
- size: `38`
- prototype: `void __fastcall(struct _KERBEROS_LIST *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180079ee4`
- `0x18007a5cc`

## callees

- `0x18007bb5c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18007bb77`
- `ntdll!RtlDeleteCriticalSection` at `0x18007bb77`

## pseudocode

```c
void __fastcall KerbFreeList(struct _KERBEROS_LIST *a1)
{
  if ( KerbFsoCache == (struct _KERB_FSO_CACHE_ENTRY *)&KerbFsoCache )
    RtlDeleteCriticalSection(&stru_1800B2CE8);
}

```

## disassembly

```asm
0x18007bb5c  sub     rsp, 28h
0x18007bb60  lea     rax, ?KerbFsoCache@@3U_KERBEROS_LIST@@A; _KERBEROS_LIST KerbFsoCache
0x18007bb67  cmp     cs:?KerbFsoCache@@3U_KERBEROS_LIST@@A, rax; _KERBEROS_LIST KerbFsoCache
0x18007bb6e  jnz     short loc_18007BB7D
0x18007bb70  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007bb77  call    cs:__imp_RtlDeleteCriticalSection
0x18007bb7d  add     rsp, 28h
0x18007bb81  retn
```
