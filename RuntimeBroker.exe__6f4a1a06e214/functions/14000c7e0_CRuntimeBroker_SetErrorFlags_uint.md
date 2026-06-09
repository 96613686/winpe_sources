# CRuntimeBroker::SetErrorFlags(uint)

- ea: `0x14000c7e0`
- end: `0x14000c81b`
- name: `?SetErrorFlags@CRuntimeBroker@@UEAAJI@Z`
- size: `59`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000aef0`
- `0x14000c7e0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoSetErrorReportingFlags` at `0x14000c80f`
- `api-ms-win-core-winrt-error-l1-1-0!RoSetErrorReportingFlags` at `0x14000c80f`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::SetErrorFlags(CRuntimeBroker *this, unsigned int a2)
{
  __int64 result; // rax
  bool v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = CRuntimeBroker::CheckClient(this, &v4);
  if ( (int)result >= 0 )
  {
    if ( v4 )
      return RoSetErrorReportingFlags(a2);
    else
      return 2147942405LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000c7e0  push    rbx
0x14000c7e2  sub     rsp, 20h
0x14000c7e6  mov     ebx, edx
0x14000c7e8  mov     [rsp+28h+arg_10], 0
0x14000c7ed  lea     rdx, [rsp+28h+arg_10]; bool *
0x14000c7f2  call    ?CheckClient@CRuntimeBroker@@AEAAJPEA_N@Z; CRuntimeBroker::CheckClient(bool *)
0x14000c7f7  test    eax, eax
0x14000c7f9  js      short loc_14000C815
0x14000c7fb  cmp     [rsp+28h+arg_10], 0
0x14000c800  jnz     short loc_14000C80D
0x14000c802  mov     eax, 80070005h
0x14000c807  add     rsp, 20h
0x14000c80b  pop     rbx
0x14000c80c  retn
0x14000c80d  mov     ecx, ebx
0x14000c80f  call    cs:__imp_RoSetErrorReportingFlags
0x14000c815  add     rsp, 20h
0x14000c819  pop     rbx
0x14000c81a  retn
```
