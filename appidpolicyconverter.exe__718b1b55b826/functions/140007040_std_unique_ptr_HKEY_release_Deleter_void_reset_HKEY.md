# std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY__ *)

- ea: `0x140007040`
- end: `0x140007071`
- name: `?reset@?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAAXPEAUHKEY__@@@Z`
- size: `49`
- prototype: `LSTATUS __fastcall(HKEY *, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400030a0`
- `0x140003330`

## callees

- `0x140007040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000705d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000705d`

## pseudocode

```c
LSTATUS __fastcall std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY *a1, HKEY a2)
{
  HKEY v4; // rcx
  LSTATUS result; // eax

  v4 = *a1;
  if ( a2 != v4 )
  {
    if ( v4 )
      result = RegCloseKey(v4);
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x140007040  mov     [rsp+arg_0], rbx
0x140007045  push    rdi
0x140007046  sub     rsp, 20h
0x14000704a  mov     rbx, rdx
0x14000704d  mov     rdi, rcx
0x140007050  mov     rcx, [rcx]; hKey
0x140007053  cmp     rdx, rcx
0x140007056  jz      short loc_140007066
0x140007058  test    rcx, rcx
0x14000705b  jz      short loc_140007063
0x14000705d  call    cs:__imp_RegCloseKey
0x140007063  mov     [rdi], rbx
0x140007066  mov     rbx, [rsp+28h+arg_0]
0x14000706b  add     rsp, 20h
0x14000706f  pop     rdi
0x140007070  retn
```
