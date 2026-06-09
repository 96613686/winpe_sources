# BackgroundExecutionSessionClient::GetEntryByForWorkItem(_GUID,_ODB_LEGACY_TASKID_ENTRY * *)

- ea: `0x18000630c`
- end: `0x180006346`
- name: `?GetEntryByForWorkItem@BackgroundExecutionSessionClient@@QEAAJU_GUID@@PEAPEAU_ODB_LEGACY_TASKID_ENTRY@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(BackgroundExecutionSessionClient *__hidden this, struct _GUID *__struct_ptr, struct _ODB_LEGACY_TASKID_ENTRY **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800020d0`

## callees

- `0x18000630c`

## pseudocode

```c
__int64 __fastcall BackgroundExecutionSessionClient::GetEntryByForWorkItem(
        BackgroundExecutionSessionClient *this,
        struct _GUID *a2,
        struct _ODB_LEGACY_TASKID_ENTRY **a3)
{
  char *v3; // r9
  char *i; // rax
  __int64 v5; // rcx

  v3 = (char *)this + 120;
  *a3 = 0;
  for ( i = (char *)*((_QWORD *)this + 15); i != v3; i = *(char **)i )
  {
    v5 = *((_QWORD *)i + 2) - *(_QWORD *)&a2->Data1;
    if ( !v5 )
      v5 = *((_QWORD *)i + 3) - *(_QWORD *)a2->Data4;
    if ( !v5 )
    {
      *a3 = (struct _ODB_LEGACY_TASKID_ENTRY *)i;
      return 0;
    }
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x18000630c  lea     r9, [rcx+78h]
0x180006310  mov     qword ptr [r8], 0
0x180006317  mov     rax, [r9]
0x18000631a  cmp     rax, r9
0x18000631d  jz      short loc_180006340
0x18000631f  mov     rcx, [rax+10h]
0x180006323  sub     rcx, [rdx]
0x180006326  jnz     short loc_180006330
0x180006328  mov     rcx, [rax+18h]
0x18000632c  sub     rcx, [rdx+8]
0x180006330  test    rcx, rcx
0x180006333  jz      short loc_18000633A
0x180006335  mov     rax, [rax]
0x180006338  jmp     short loc_18000631A
0x18000633a  mov     [r8], rax
0x18000633d  xor     eax, eax
0x18000633f  retn
0x180006340  mov     eax, 80070490h
0x180006345  retn
```
