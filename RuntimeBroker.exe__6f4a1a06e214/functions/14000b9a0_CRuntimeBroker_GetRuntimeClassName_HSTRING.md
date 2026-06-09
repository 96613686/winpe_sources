# CRuntimeBroker::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14000b9a0`
- end: `0x14000b9c2`
- name: `?GetRuntimeClassName@CRuntimeBroker@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `34`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b9b2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b9b2`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::GetRuntimeClassName(CRuntimeBroker *this, HSTRING *a2)
{
  *a2 = 0;
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x14000b9a0  sub     rsp, 28h
0x14000b9a4  mov     qword ptr [rdx], 0
0x14000b9ab  mov     ecx, 80004001h
0x14000b9b0  xor     edx, edx
0x14000b9b2  call    cs:__imp_RoOriginateError
0x14000b9b8  mov     eax, 80004001h
0x14000b9bd  add     rsp, 28h
0x14000b9c1  retn
```
