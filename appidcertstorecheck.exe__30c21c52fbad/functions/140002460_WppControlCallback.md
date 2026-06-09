# WppControlCallback

- ea: `0x140002460`
- end: `0x1400024e2`
- name: `WppControlCallback`
- size: `130`
- prototype: `__int64 __fastcall(int, __int64, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002460`

## import_xrefs

- `ntdll!EtwGetTraceEnableFlags` at `0x1400024ae`
- `ntdll!EtwGetTraceEnableFlags` at `0x1400024ae`
- `ntdll!EtwGetTraceEnableLevel` at `0x1400024a2`
- `ntdll!EtwGetTraceEnableLevel` at `0x1400024a2`
- `ntdll!EtwGetTraceLoggerHandle` at `0x140002496`
- `ntdll!EtwGetTraceLoggerHandle` at `0x140002496`

## pseudocode

```c
__int64 __fastcall WppControlCallback(int a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  int v5; // ecx
  __int64 result; // rax
  __int64 TraceLoggerHandle; // rdi
  int TraceEnableFlags; // eax
  char TraceEnableLevel; // si

  *a3 = 0;
  v5 = a1 - 4;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 87;
    TraceLoggerHandle = 0;
    TraceEnableFlags = 0;
    TraceEnableLevel = 0;
  }
  else
  {
    TraceLoggerHandle = EtwGetTraceLoggerHandle(a4);
    TraceEnableLevel = EtwGetTraceEnableLevel(TraceLoggerHandle);
    TraceEnableFlags = EtwGetTraceEnableFlags(TraceLoggerHandle);
  }
  if ( (*(_BYTE *)(a2 + 26) & 2) != 0 )
  {
    if ( *(_QWORD *)(a2 + 16) )
      a2 = *(_QWORD *)(a2 + 16);
  }
  *(_DWORD *)(a2 + 28) = TraceEnableFlags;
  result = 0;
  *(_QWORD *)(a2 + 16) = TraceLoggerHandle;
  *(_BYTE *)(a2 + 25) = TraceEnableLevel;
  return result;
}

```

## disassembly

```asm
0x140002460  mov     [rsp+arg_0], rbx
0x140002465  mov     [rsp+arg_8], rsi
0x14000246a  push    rdi
0x14000246b  sub     rsp, 20h
0x14000246f  mov     dword ptr [r8], 0
0x140002476  mov     rbx, rdx
0x140002479  sub     ecx, 4
0x14000247c  jz      short loc_140002493
0x14000247e  cmp     ecx, 1
0x140002481  jz      short loc_14000248A
0x140002483  mov     eax, 57h ; 'W'
0x140002488  jmp     short loc_1400024D2
0x14000248a  xor     edi, edi
0x14000248c  xor     eax, eax
0x14000248e  xor     sil, sil
0x140002491  jmp     short loc_1400024B4
0x140002493  mov     rcx, r9
0x140002496  call    cs:__imp_EtwGetTraceLoggerHandle
0x14000249c  mov     rcx, rax
0x14000249f  mov     rdi, rax
0x1400024a2  call    cs:__imp_EtwGetTraceEnableLevel
0x1400024a8  mov     rcx, rdi
0x1400024ab  mov     sil, al
0x1400024ae  call    cs:__imp_EtwGetTraceEnableFlags
0x1400024b4  test    byte ptr [rbx+1Ah], 2
0x1400024b8  jz      short loc_1400024C5
0x1400024ba  mov     rcx, [rbx+10h]
0x1400024be  test    rcx, rcx
0x1400024c1  cmovnz  rbx, rcx
0x1400024c5  mov     [rbx+1Ch], eax
0x1400024c8  xor     eax, eax
0x1400024ca  mov     [rbx+10h], rdi
0x1400024ce  mov     [rbx+19h], sil
0x1400024d2  mov     rbx, [rsp+28h+arg_0]
0x1400024d7  mov     rsi, [rsp+28h+arg_8]
0x1400024dc  add     rsp, 20h
0x1400024e0  pop     rdi
0x1400024e1  retn
```
