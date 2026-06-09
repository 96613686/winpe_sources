# CWinSATTaskMangerTask::CommitErrorCount(void)

- ea: `0x1800217fc`
- end: `0x180021891`
- name: `?CommitErrorCount@CWinSATTaskMangerTask@@AEAA_NXZ`
- size: `149`
- prototype: `bool __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x18000f0e8`
- `0x1800217fc`
- `0x180021d84`
- `0x180024248`
- `0x180033010`

## string_xrefs

- `0x180021817`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021857`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002180b`: `The task error count is too high, disabling the task`
- `0x180021862`: `Failed to write the error count to the registry (error count = %u)`
- `0x180021877`: `Incremented TaskErrorCout to %u and sucesfully wrote to the registry`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::CommitErrorCount(CWinSATTaskMangerTask *this)
{
  char v2; // cl
  void (__fastcall *v3)(void *, __int64, __int64); // rax
  char updated; // al
  int v5; // r9d

  if ( *((_DWORD *)this + 27) >= 3u )
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      138,
      "The task error count is too high, disabling the task");
    EnableDisableWinSATTask(v2);
    v3 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
    if ( v3 )
      v3(&unk_18004A8B0, 10270, 1);
  }
  updated = CWinSATTaskMangerTask::UpdateErrorCountRegKey(this, *((_DWORD *)this + 27));
  v5 = *((_DWORD *)this + 27);
  if ( updated )
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      148,
      "Incremented TaskErrorCout to %u and sucesfully wrote to the registry",
      v5);
    return 1;
  }
  else
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      144,
      "Failed to write the error count to the registry (error count = %u)",
      v5);
    return 0;
  }
}

```

## disassembly

```asm
0x1800217fc  push    rbx
0x1800217fe  sub     rsp, 20h
0x180021802  cmp     dword ptr [rcx+6Ch], 3
0x180021806  mov     rbx, rcx
0x180021809  jb      short loc_18002184B
0x18002180b  lea     r8, aTheTaskErrorCo; "The task error count is too high, disab"...
0x180021812  mov     edx, 8Ah
0x180021817  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002181e  call    Log_Text_F
0x180021823  call    ?EnableDisableWinSATTask@@YAJ_N@Z; EnableDisableWinSATTask(bool)
0x180021828  mov     rax, [rbx+88h]
0x18002182f  test    rax, rax
0x180021832  jz      short loc_18002184B
0x180021834  mov     edx, 281Eh
0x180021839  lea     rcx, unk_18004A8B0
0x180021840  mov     r8d, 1
0x180021846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002184b  mov     edx, [rbx+6Ch]; unsigned int
0x18002184e  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x180021853  mov     r9d, [rbx+6Ch]
0x180021857  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002185e  test    al, al
0x180021860  jnz     short loc_180021877
0x180021862  lea     r8, aFailedToWriteT; "Failed to write the error count to the "...
0x180021869  mov     edx, 90h
0x18002186e  call    Log_Text_F
0x180021873  xor     al, al
0x180021875  jmp     short loc_18002188A
0x180021877  lea     r8, aIncrementedTas; "Incremented TaskErrorCout to %u and suc"...
0x18002187e  mov     edx, 94h
0x180021883  call    Log_Text_F
0x180021888  mov     al, 1
0x18002188a  add     rsp, 20h
0x18002188e  pop     rbx
0x18002188f  retn
```
