# CMigrationPlugin::raw_PreGather(IMigrationContext *)

- ea: `0x180014c50`
- end: `0x180014c81`
- name: `?raw_PreGather@CMigrationPlugin@@UEAAJPEAUIMigrationContext@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(CMigrationPlugin *__hidden this, struct IMigrationContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000dfe8`
- `0x1800105b4`
- `0x1800109a8`
- `0x180014c50`

## pseudocode

```c
__int64 __fastcall CMigrationPlugin::raw_PreGather(CMigrationPlugin *this, struct IMigrationContext *a2)
{
  if ( !(unsigned __int8)IsInUpgrade(a2) || !(unsigned __int8)IsDataMigrationEligible(a2) )
    EnsureICVMigration(a2);
  return 0;
}

```

## disassembly

```asm
0x180014c50  push    rbx
0x180014c52  sub     rsp, 20h
0x180014c56  mov     rcx, rdx
0x180014c59  mov     rbx, rdx
0x180014c5c  call    IsInUpgrade
0x180014c61  test    al, al
0x180014c63  jz      short loc_180014C71
0x180014c65  mov     rcx, rbx
0x180014c68  call    IsDataMigrationEligible
0x180014c6d  test    al, al
0x180014c6f  jnz     short loc_180014C79
0x180014c71  mov     rcx, rbx
0x180014c74  call    EnsureICVMigration
0x180014c79  xor     eax, eax
0x180014c7b  add     rsp, 20h
0x180014c7f  pop     rbx
0x180014c80  retn
```
