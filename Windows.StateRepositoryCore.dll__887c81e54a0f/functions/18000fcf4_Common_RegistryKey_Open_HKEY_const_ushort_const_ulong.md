# Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)

- ea: `0x18000fcf4`
- end: `0x18000fd49`
- name: `?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z`
- size: `85`
- prototype: `LSTATUS __fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *, REGSAM)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d560`

## callees

- `0x18000be00`
- `0x18000fcf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd2c`

## string_xrefs

- `0x18000fd1e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::Open(PHKEY phkResult, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  LSTATUS result; // eax

  Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
  *phkResult = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache",
             0,
             a4,
             phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fcf4  mov     [rsp+arg_0], rbx
0x18000fcf9  push    rdi
0x18000fcfa  sub     rsp, 30h
0x18000fcfe  mov     rbx, rcx
0x18000fd01  mov     edi, r9d
0x18000fd04  mov     rcx, [rcx]
0x18000fd07  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000fd0c  mov     r9d, edi; samDesired
0x18000fd0f  mov     qword ptr [rbx], 0
0x18000fd16  xor     r8d, r8d; ulOptions
0x18000fd19  mov     [rsp+38h+phkResult], rbx; phkResult
0x18000fd1e  lea     rdx, ?RootSubkey@Constants@Cache@StateRepository@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000fd25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fd2c  call    cs:__imp_RegOpenKeyExW
0x18000fd32  test    eax, eax
0x18000fd34  jle     short loc_18000FD3E
0x18000fd36  movzx   eax, ax
0x18000fd39  or      eax, 80070000h
0x18000fd3e  mov     rbx, [rsp+38h+arg_0]
0x18000fd43  add     rsp, 30h
0x18000fd47  pop     rdi
0x18000fd48  retn
```
