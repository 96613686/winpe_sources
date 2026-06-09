# Tracker::CreateManagedRuntime(void)

- ea: `0x140002d20`
- end: `0x140002d6c`
- name: `?CreateManagedRuntime@Tracker@@CAJXZ`
- size: `76`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003260`

## callees

- `0x140002c50`
- `0x140002d20`
- `0x140005594`

## import_xrefs

- `ole32!CoUninitialize` at `0x140002d5e`
- `ole32!CoUninitialize` at `0x140002d5e`

## pseudocode

```c
__int64 Tracker::CreateManagedRuntime(void)
{
  unsigned int ManagedInstance; // ebx
  void **v1; // r9
  int v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  ManagedInstance = EnsureCoInitialized(&v3);
  if ( !ManagedInstance )
    ManagedInstance = LegacyActivationShim::ClrCreateManagedInstance(
                        (LegacyActivationShim *)L"System.Web.SessionState.StateRuntime,System.Web,version=4.0.0.0",
                        (const unsigned __int16 *)&GUID_7297744b_e188_40bf_b7e9_56698d25cf44,
                        &Tracker::s_pManagedRuntime,
                        v1);
  if ( v3 )
    CoUninitialize();
  return ManagedInstance;
}

```

## disassembly

```asm
0x140002d20  push    rbx
0x140002d22  sub     rsp, 20h
0x140002d26  and     [rsp+28h+arg_0], 0
0x140002d2b  lea     rcx, [rsp+28h+arg_0]; int *
0x140002d30  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x140002d35  mov     ebx, eax
0x140002d37  test    eax, eax
0x140002d39  jnz     short loc_140002D57
0x140002d3b  lea     r8, ?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA; struct _GUID *
0x140002d42  lea     rdx, _GUID_7297744b_e188_40bf_b7e9_56698d25cf44; unsigned __int16 *
0x140002d49  lea     rcx, aSystemWebSessi; "System.Web.SessionState.StateRuntime,Sy"...
0x140002d50  call    ?ClrCreateManagedInstance@LegacyActivationShim@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; LegacyActivationShim::ClrCreateManagedInstance(ushort const *,_GUID const &,void * *)
0x140002d55  mov     ebx, eax
0x140002d57  cmp     [rsp+28h+arg_0], 0
0x140002d5c  jz      short loc_140002D64
0x140002d5e  call    cs:__imp_CoUninitialize
0x140002d64  mov     eax, ebx
0x140002d66  add     rsp, 20h
0x140002d6a  pop     rbx
0x140002d6b  retn
```
