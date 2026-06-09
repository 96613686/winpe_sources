# RegFlush(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180086728`
- end: `0x1800867c5`
- name: `?RegFlush@@YAKPEAUHKEY__@@PEBG1@Z`
- size: `157`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800919a4`

## callees

- `0x180086728`
- `0x1800867cc`
- `0x18008aa28`
- `0x18008afb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086757`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086757`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800867ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800867ad`

## string_xrefs

- `0x180086766`: `RegOpenKeyExW`
- `0x180086781`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegFlush(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a1, a2, 0, 1u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    Logger::WriteRegistryFailureEvent(v5, L"RegOpenKeyExW", a3);
    Logger::TraceError(L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.", L"RegFlush", a3, v6);
  }
  else
  {
    v6 = RegFlush(hKey, a3);
  }
  if ( hKey && hKey != a1 )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180086728  mov     r11, rsp
0x18008672b  mov     [r11+8], rbx
0x18008672f  mov     [r11+10h], rsi
0x180086733  push    rdi
0x180086734  sub     rsp, 30h
0x180086738  mov     rdi, r8
0x18008673b  mov     qword ptr [r11+20h], 0
0x180086743  lea     rax, [r11+20h]
0x180086747  xor     r8d, r8d; ulOptions
0x18008674a  mov     r9d, 1; samDesired
0x180086750  mov     [r11-18h], rax
0x180086754  mov     rsi, rcx
0x180086757  call    cs:__imp_RegOpenKeyExW
0x18008675d  mov     ebx, eax
0x18008675f  test    eax, eax
0x180086761  jz      short loc_18008678F
0x180086763  mov     r8, rdi; unsigned __int16 *
0x180086766  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18008676d  mov     ecx, eax; unsigned int
0x18008676f  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180086774  mov     r9d, ebx
0x180086777  lea     rdx, aRegflush; "RegFlush"
0x18008677e  mov     r8, rdi
0x180086781  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x180086788  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008678d  jmp     short loc_18008679E
0x18008678f  mov     rcx, [rsp+38h+hKey]; HKEY
0x180086794  mov     rdx, rdi; unsigned __int16 *
0x180086797  call    ?RegFlush@@YAKPEAUHKEY__@@PEBG@Z; RegFlush(HKEY__ *,ushort const *)
0x18008679c  mov     ebx, eax
0x18008679e  mov     rcx, [rsp+38h+hKey]; hKey
0x1800867a3  test    rcx, rcx
0x1800867a6  jz      short loc_1800867B3
0x1800867a8  cmp     rcx, rsi
0x1800867ab  jz      short loc_1800867B3
0x1800867ad  call    cs:__imp_RegCloseKey
0x1800867b3  mov     rsi, [rsp+38h+arg_8]
0x1800867b8  mov     eax, ebx
0x1800867ba  mov     rbx, [rsp+38h+arg_0]
0x1800867bf  add     rsp, 30h
0x1800867c3  pop     rdi
0x1800867c4  retn
```
