# Common::RegistryKey::Create(HKEY__ * const,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,ulong *)

- ea: `0x18002c010`
- end: `0x18002c091`
- name: `?Create@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `129`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023110`

## callees

- `0x18000d9a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c074`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c074`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::Create(PHKEY phkResult, HKEY a2, const unsigned __int16 *a3)
{
  LSTATUS result; // eax

  Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
  *phkResult = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  *phkResult = 0;
  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x2011Fu, 0, phkResult, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c010  mov     [rsp+arg_0], rbx
0x18002c015  push    rdi
0x18002c016  sub     rsp, 50h
0x18002c01a  mov     rbx, rcx
0x18002c01d  mov     rdi, r8
0x18002c020  mov     rcx, [rcx]
0x18002c023  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c028  xor     ecx, ecx
0x18002c02a  mov     qword ptr [rbx], 0
0x18002c031  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c036  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002c03f  xor     r9d, r9d; lpClass
0x18002c042  mov     [rsp+58h+phkResult], rbx; phkResult
0x18002c047  xor     r8d, r8d; Reserved
0x18002c04a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002c053  mov     rdx, rdi; lpSubKey
0x18002c056  mov     [rsp+58h+samDesired], 2011Fh; samDesired
0x18002c05e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c065  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002c06d  mov     qword ptr [rbx], 0
0x18002c074  call    cs:__imp_RegCreateKeyExW
0x18002c07a  test    eax, eax
0x18002c07c  jle     short loc_18002C086
0x18002c07e  movzx   eax, ax
0x18002c081  or      eax, 80070000h
0x18002c086  mov     rbx, [rsp+58h+arg_0]
0x18002c08b  add     rsp, 50h
0x18002c08f  pop     rdi
0x18002c090  retn
```
