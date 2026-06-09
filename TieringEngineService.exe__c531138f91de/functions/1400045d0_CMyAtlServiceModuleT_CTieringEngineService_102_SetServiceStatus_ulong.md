# CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)

- ea: `0x1400045d0`
- end: `0x14000460d`
- name: `?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z`
- size: `61`
- prototype: `int __fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400037bc`
- `0x140003e38`
- `0x140004440`
- `0x1400046d4`
- `0x1400047e0`
- `0x14003fe6f`

## callees

- `0x1400045d0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140004600`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140004600`

## pseudocode

```c
int __fastcall CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(__int64 a1, int a2)
{
  __int64 v2; // rax
  SERVICE_STATUS_HANDLE v3; // rcx

  v2 = a1;
  if ( a2 == 1 )
    v3 = (SERVICE_STATUS_HANDLE)_InterlockedExchange64((volatile __int64 *)(a1 + 616), 0);
  else
    v3 = *(SERVICE_STATUS_HANDLE *)(a1 + 616);
  *(_DWORD *)(v2 + 628) = a2;
  if ( v3 )
    LODWORD(v2) = SetServiceStatus(v3, (LPSERVICE_STATUS)(v2 + 624));
  return v2;
}

```

## disassembly

```asm
0x1400045d0  sub     rsp, 28h
0x1400045d4  mov     rax, rcx
0x1400045d7  cmp     edx, 1
0x1400045da  jnz     short loc_1400045E7
0x1400045dc  xor     ecx, ecx
0x1400045de  xchg    rcx, [rax+268h]
0x1400045e5  jmp     short loc_1400045EE
0x1400045e7  mov     rcx, [rcx+268h]; hServiceStatus
0x1400045ee  mov     [rax+274h], edx
0x1400045f4  test    rcx, rcx
0x1400045f7  jz      short loc_140004606
0x1400045f9  lea     rdx, [rax+270h]; lpServiceStatus
0x140004600  call    cs:__imp_SetServiceStatus
0x140004606  jmp     short $+2
0x140004608  add     rsp, 28h
0x14000460c  retn
```
