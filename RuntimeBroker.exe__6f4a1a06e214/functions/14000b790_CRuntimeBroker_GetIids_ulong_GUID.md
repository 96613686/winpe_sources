# CRuntimeBroker::GetIids(ulong *,_GUID * *)

- ea: `0x14000b790`
- end: `0x14000b7b8`
- name: `?GetIids@CRuntimeBroker@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b7a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b7a8`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::GetIids(CRuntimeBroker *this, unsigned int *a2, struct _GUID **a3)
{
  *a2 = 0;
  *a3 = 0;
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x14000b790  sub     rsp, 28h
0x14000b794  mov     dword ptr [rdx], 0
0x14000b79a  mov     ecx, 80004001h
0x14000b79f  xor     edx, edx
0x14000b7a1  mov     qword ptr [r8], 0
0x14000b7a8  call    cs:__imp_RoOriginateError
0x14000b7ae  mov     eax, 80004001h
0x14000b7b3  add     rsp, 28h
0x14000b7b7  retn
```
