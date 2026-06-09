# AutoTimeUpdate::Run(std::shared_ptr<Settings> const &)

- ea: `0x18000c3c8`
- end: `0x18000c449`
- name: `?Run@AutoTimeUpdate@@SA?AW4SyncResult@@AEBV?$shared_ptr@VSettings@@@std@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180006350`
- `0x18000ca60`

## callees

- `0x18000c300`
- `0x18000c3c8`
- `0x18000c450`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoTimeUpdate::Run(__int64 a1)
{
  unsigned int updated; // eax
  volatile signed __int32 *v3; // rbx
  unsigned int v4; // edi
  _DWORD v5[4]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v6; // [rsp+30h] [rbp-18h]

  if ( !*(_BYTE *)(*(_QWORD *)a1 + 4LL) )
    return 3;
  AutoTimeUpdate::AutoTimeUpdate(v5);
  updated = AutoTimeUpdate::UpdateTime(v5);
  v3 = v6;
  v4 = updated;
  if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x18000c3c8  mov     [rsp+arg_0], rbx
0x18000c3cd  push    rdi
0x18000c3ce  sub     rsp, 40h
0x18000c3d2  mov     rax, [rcx]
0x18000c3d5  cmp     byte ptr [rax+4], 0
0x18000c3d9  jnz     short loc_18000C3E2
0x18000c3db  mov     eax, 3
0x18000c3e0  jmp     short loc_18000C43E
0x18000c3e2  mov     rdx, rcx
0x18000c3e5  lea     rcx, [rsp+48h+var_28]
0x18000c3ea  call    ??0AutoTimeUpdate@@AEAA@AEBV?$shared_ptr@VSettings@@@std@@@Z; AutoTimeUpdate::AutoTimeUpdate(std::shared_ptr<Settings> const &)
0x18000c3ef  lea     rcx, [rsp+48h+var_28]
0x18000c3f4  call    ?UpdateTime@AutoTimeUpdate@@AEAA?AW4SyncResult@@XZ; AutoTimeUpdate::UpdateTime(void)
0x18000c3f9  mov     rbx, [rsp+48h+var_18]
0x18000c3fe  mov     edi, eax
0x18000c400  test    rbx, rbx
0x18000c403  jz      short loc_18000C43C
0x18000c405  or      ecx, 0FFFFFFFFh
0x18000c408  lock xadd [rbx+8], ecx
0x18000c40d  cmp     ecx, 1
0x18000c410  jnz     short loc_18000C43C
0x18000c412  mov     rdx, [rbx]
0x18000c415  mov     rcx, rbx
0x18000c418  mov     rax, [rdx]
0x18000c41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c420  or      eax, 0FFFFFFFFh
0x18000c423  lock xadd [rbx+0Ch], eax
0x18000c428  cmp     eax, 1
0x18000c42b  jnz     short loc_18000C43C
0x18000c42d  mov     rax, [rbx]
0x18000c430  mov     rcx, rbx
0x18000c433  mov     rax, [rax+8]
0x18000c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c43c  mov     eax, edi
0x18000c43e  mov     rbx, [rsp+48h+arg_0]
0x18000c443  add     rsp, 40h
0x18000c447  pop     rdi
0x18000c448  retn
```
