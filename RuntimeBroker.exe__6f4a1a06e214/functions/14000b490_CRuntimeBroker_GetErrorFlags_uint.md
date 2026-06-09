# CRuntimeBroker::GetErrorFlags(uint *)

- ea: `0x14000b490`
- end: `0x14000b4cd`
- name: `?GetErrorFlags@CRuntimeBroker@@UEAAJPEAI@Z`
- size: `61`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000aef0`
- `0x14000b490`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x14000b4c1`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x14000b4c1`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::GetErrorFlags(CRuntimeBroker *this, unsigned int *a2)
{
  __int64 result; // rax
  bool v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = CRuntimeBroker::CheckClient(this, &v4);
  if ( (int)result >= 0 )
  {
    if ( v4 )
      return RoGetErrorReportingFlags(a2);
    else
      return 2147942405LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000b490  push    rbx
0x14000b492  sub     rsp, 20h
0x14000b496  mov     rbx, rdx
0x14000b499  mov     [rsp+28h+arg_10], 0
0x14000b49e  lea     rdx, [rsp+28h+arg_10]; bool *
0x14000b4a3  call    ?CheckClient@CRuntimeBroker@@AEAAJPEA_N@Z; CRuntimeBroker::CheckClient(bool *)
0x14000b4a8  test    eax, eax
0x14000b4aa  js      short loc_14000B4C7
0x14000b4ac  cmp     [rsp+28h+arg_10], 0
0x14000b4b1  jnz     short loc_14000B4BE
0x14000b4b3  mov     eax, 80070005h
0x14000b4b8  add     rsp, 20h
0x14000b4bc  pop     rbx
0x14000b4bd  retn
0x14000b4be  mov     rcx, rbx
0x14000b4c1  call    cs:__imp_RoGetErrorReportingFlags
0x14000b4c7  add     rsp, 20h
0x14000b4cb  pop     rbx
0x14000b4cc  retn
```
