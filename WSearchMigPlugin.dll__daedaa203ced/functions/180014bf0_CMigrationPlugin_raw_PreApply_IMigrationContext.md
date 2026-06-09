# CMigrationPlugin::raw_PreApply(IMigrationContext *)

- ea: `0x180014bf0`
- end: `0x180014c46`
- name: `?raw_PreApply@CMigrationPlugin@@UEAAJPEAUIMigrationContext@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(CMigrationPlugin *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800128fc`
- `0x180014bf0`
- `0x180015358`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CMigrationPlugin::raw_PreApply(CMigrationPlugin *this, struct IUnknown *a2)
{
  struct IUnknown v2; // rax
  int v4; // eax
  const struct _GUID *v5; // r8
  __int16 v7; // [rsp+38h] [rbp+10h] BYREF

  v2.lpVtbl = a2->lpVtbl;
  v7 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int16 *))v2.lpVtbl[6].AddRef)(a2, &v7);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a2, v5);
  if ( !v7 )
    StopWSearchAndEnsureIdle(a2);
  return 0;
}

```

## disassembly

```asm
0x180014bf0  mov     [rsp+arg_0], rbx
0x180014bf5  push    rdi
0x180014bf6  sub     rsp, 20h
0x180014bfa  mov     rax, [rdx]
0x180014bfd  mov     rbx, rdx
0x180014c00  xor     edi, edi
0x180014c02  lea     rdx, [rsp+28h+arg_8]
0x180014c07  mov     rcx, rbx
0x180014c0a  mov     [rsp+28h+arg_8], di
0x180014c0f  mov     rax, [rax+98h]
0x180014c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c1b  test    eax, eax
0x180014c1d  js      short loc_180014C3B
0x180014c1f  cmp     [rsp+28h+arg_8], di
0x180014c24  jnz     short loc_180014C2E
0x180014c26  mov     rcx, rbx
0x180014c29  call    StopWSearchAndEnsureIdle
0x180014c2e  mov     rbx, [rsp+28h+arg_0]
0x180014c33  xor     eax, eax
0x180014c35  add     rsp, 20h
0x180014c39  pop     rdi
0x180014c3a  retn
0x180014c3b  mov     rdx, rbx; struct IUnknown *
0x180014c3e  mov     ecx, eax; int
0x180014c40  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
