# CSettingsManager::ReadOnlyMode(DwmSettingType)

- ea: `0x14000cb30`
- end: `0x14000cb82`
- name: `?ReadOnlyMode@CSettingsManager@@UEAA_NW4DwmSettingType@@@Z`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000cb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000cb48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000cb48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000cb6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000cb6a`

## pseudocode

```c
char __fastcall CSettingsManager::ReadOnlyMode(__int64 a1, unsigned int a2)
{
  __int64 v3; // rbx
  bool v4; // zf
  char v5; // bl

  v3 = a2;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
  if ( (_DWORD)v3 )
    v4 = *(_QWORD *)(a1 + 16) == 0;
  else
    v4 = *(_QWORD *)(a1 + 8) == v3;
  v5 = *(_BYTE *)(a1 + 32) | v4;
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
  return v5;
}

```

## disassembly

```asm
0x14000cb30  mov     [rsp+arg_0], rbx
0x14000cb35  mov     [rsp+arg_8], rsi
0x14000cb3a  push    rdi
0x14000cb3b  sub     rsp, 20h
0x14000cb3f  mov     rdi, rcx
0x14000cb42  mov     ebx, edx
0x14000cb44  add     rcx, 30h ; '0'; SRWLock
0x14000cb48  call    cs:__imp_AcquireSRWLockShared
0x14000cb4e  mov     al, [rdi+20h]
0x14000cb51  test    ebx, ebx
0x14000cb53  jnz     short loc_14000CB5B
0x14000cb55  cmp     [rdi+8], rbx
0x14000cb59  jmp     short loc_14000CB61
0x14000cb5b  xor     ebx, ebx
0x14000cb5d  cmp     [rdi+10h], rbx
0x14000cb61  setz    bl
0x14000cb64  lea     rcx, [rdi+30h]; SRWLock
0x14000cb68  or      bl, al
0x14000cb6a  call    cs:__imp_ReleaseSRWLockShared
0x14000cb70  mov     rsi, [rsp+28h+arg_8]
0x14000cb75  mov     al, bl
0x14000cb77  mov     rbx, [rsp+28h+arg_0]
0x14000cb7c  add     rsp, 20h
0x14000cb80  pop     rdi
0x14000cb81  retn
```
