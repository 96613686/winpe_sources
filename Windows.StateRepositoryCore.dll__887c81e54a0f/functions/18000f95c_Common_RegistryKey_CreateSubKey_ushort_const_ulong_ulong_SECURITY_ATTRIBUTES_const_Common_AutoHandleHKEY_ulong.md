# Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)

- ea: `0x18000f95c`
- end: `0x18000f9d1`
- name: `?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z`
- size: `117`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, REGSAM, __int64, struct _SECURITY_ATTRIBUTES *const, HKEY *phkResult)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c05c`
- `0x18000cb60`
- `0x18000d560`

## callees

- `0x18000be00`
- `0x18000f95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f9b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f9b5`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::CreateSubKey(
        HKEY *this,
        const unsigned __int16 *a2,
        REGSAM a3,
        __int64 a4,
        struct _SECURITY_ATTRIBUTES *const a5,
        HKEY *phkResult)
{
  LSTATUS result; // eax

  Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
  *phkResult = 0;
  result = RegCreateKeyExW(*this, a2, 0, 0, 1u, a3, 0, phkResult, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f95c  push    rbx
0x18000f95e  push    rsi
0x18000f95f  push    rdi
0x18000f960  push    r14
0x18000f962  sub     rsp, 58h
0x18000f966  mov     rbx, [rsp+78h+arg_28]
0x18000f96e  mov     r14, rcx
0x18000f971  mov     edi, r8d
0x18000f974  mov     rsi, rdx
0x18000f977  mov     rcx, [rbx]
0x18000f97a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000f97f  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18000f988  xor     r9d, r9d; lpClass
0x18000f98b  mov     [rsp+78h+phkResult], rbx; phkResult
0x18000f990  xor     r8d, r8d; Reserved
0x18000f993  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f99c  mov     rdx, rsi; lpSubKey
0x18000f99f  mov     qword ptr [rbx], 0
0x18000f9a6  mov     rcx, [r14]; hKey
0x18000f9a9  mov     [rsp+78h+samDesired], edi; samDesired
0x18000f9ad  mov     [rsp+78h+dwOptions], 1; dwOptions
0x18000f9b5  call    cs:__imp_RegCreateKeyExW
0x18000f9bb  test    eax, eax
0x18000f9bd  jle     short loc_18000F9C7
0x18000f9bf  movzx   eax, ax
0x18000f9c2  or      eax, 80070000h
0x18000f9c7  add     rsp, 58h
0x18000f9cb  pop     r14
0x18000f9cd  pop     rdi
0x18000f9ce  pop     rsi
0x18000f9cf  pop     rbx
0x18000f9d0  retn
```
