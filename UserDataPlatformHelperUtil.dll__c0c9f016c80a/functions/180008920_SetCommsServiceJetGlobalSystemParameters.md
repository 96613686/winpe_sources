# SetCommsServiceJetGlobalSystemParameters

- ea: `0x180008920`
- end: `0x180008970`
- name: `SetCommsServiceJetGlobalSystemParameters`
- size: `80`
- prototype: `signed int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000894c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000894c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008942`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008942`

## pseudocode

```c
signed int SetCommsServiceJetGlobalSystemParameters()
{
  signed int result; // eax
  int Parameter; // [rsp+30h] [rbp+8h] BYREF

  Parameter = 0;
  if ( InitOnceExecuteOnce(&InitOnce, SetParametersInitOnce, &Parameter, 0) )
  {
    result = 0;
    if ( Parameter < 0 )
      return Parameter;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008920  sub     rsp, 28h
0x180008924  xor     r9d, r9d; Context
0x180008927  mov     [rsp+28h+Parameter], 0
0x18000892f  lea     r8, [rsp+28h+Parameter]; Parameter
0x180008934  lea     rdx, ?SetParametersInitOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000893b  lea     rcx, InitOnce; InitOnce
0x180008942  call    cs:__imp_InitOnceExecuteOnce
0x180008948  test    eax, eax
0x18000894a  jnz     short loc_180008960
0x18000894c  call    cs:__imp_GetLastError
0x180008952  test    eax, eax
0x180008954  jle     short loc_18000896B
0x180008956  movzx   eax, ax
0x180008959  or      eax, 80070000h
0x18000895e  jmp     short loc_18000896B
0x180008960  mov     ecx, [rsp+28h+Parameter]
0x180008964  xor     eax, eax
0x180008966  test    ecx, ecx
0x180008968  cmovs   eax, ecx
0x18000896b  add     rsp, 28h
0x18000896f  retn
```
