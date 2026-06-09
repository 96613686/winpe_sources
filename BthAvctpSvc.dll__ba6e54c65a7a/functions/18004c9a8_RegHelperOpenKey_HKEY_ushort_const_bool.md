# RegHelperOpenKey(HKEY__ *,ushort const *,bool)

- ea: `0x18004c9a8`
- end: `0x18004c9f6`
- name: `?RegHelperOpenKey@@YAPEAUHKEY__@@PEAU1@PEBG_N@Z`
- size: `78`
- prototype: `HKEY __fastcall(HKEY, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800269f4`
- `0x18004c698`

## callees

- `0x18004c9a8`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004c9d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004c9d5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18004c9df`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18004c9df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c9c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c9c8`

## pseudocode

```c
HKEY __fastcall RegHelperOpenKey(HKEY a1, const unsigned __int16 *a2)
{
  HKEY phkResult; // [rsp+58h] [rbp+20h] BYREF

  phkResult = 0;
  if ( (RegOpenKeyExW(a1, a2, 0, 0x20019u, &phkResult) & 0xFFFFFFFD) != 0 )
  {
    if ( !IsDebuggerPresent() )
      __fastfail(7u);
    DebugBreak();
  }
  return phkResult;
}

```

## disassembly

```asm
0x18004c9a8  sub     rsp, 38h
0x18004c9ac  lea     rax, [rsp+38h+arg_18]
0x18004c9b1  mov     [rsp+38h+arg_18], 0
0x18004c9ba  mov     r9d, 20019h; samDesired
0x18004c9c0  mov     [rsp+38h+phkResult], rax; phkResult
0x18004c9c5  xor     r8d, r8d; ulOptions
0x18004c9c8  call    cs:__imp_RegOpenKeyExW
0x18004c9ce  test    eax, 0FFFFFFFDh
0x18004c9d3  jz      short loc_18004C9E5
0x18004c9d5  call    cs:__imp_IsDebuggerPresent
0x18004c9db  test    eax, eax
0x18004c9dd  jz      short loc_18004C9EF
0x18004c9df  call    cs:__imp_DebugBreak
0x18004c9e5  mov     rax, [rsp+38h+arg_18]
0x18004c9ea  add     rsp, 38h
0x18004c9ee  retn
0x18004c9ef  mov     ecx, 7
0x18004c9f4  int     29h; Win8: RtlFailFast(ecx)
```
