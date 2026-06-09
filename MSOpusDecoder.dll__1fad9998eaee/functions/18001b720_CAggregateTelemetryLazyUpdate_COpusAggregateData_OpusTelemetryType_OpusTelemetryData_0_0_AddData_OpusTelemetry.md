# CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::AddData(OpusTelemetryType,OpusTelemetryData,bool,bool)

- ea: `0x18001b720`
- end: `0x18001b79f`
- name: `?AddData@?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAXW4OpusTelemetryType@@TOpusTelemetryData@@_N2@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18001b720`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b741`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b741`

## pseudocode

```c
void __fastcall CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::AddData(
        __int64 a1,
        int a2,
        __int64 a3,
        char a4,
        char a5)
{
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // esi

  if ( a4 )
  {
    if ( *(_BYTE *)(a1 + 16) )
    {
      v8 = *(_QWORD *)(a1 + 40);
      if ( GetTickCount64() - v8 > *(_QWORD *)(a1 + 32) )
      {
        if ( *(_QWORD *)(a1 + 32) )
        {
          LOBYTE(v9) = a5;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v9);
        }
      }
    }
  }
  v10 = *(_QWORD *)(a1 + 8);
  if ( v10 )
  {
    if ( a2 )
    {
      v11 = a2 - 1;
      if ( v11 )
      {
        if ( v11 == 1 )
          ++*(_WORD *)(v10 + 24);
      }
      else
      {
        *(_QWORD *)(v10 + 32) = a3;
      }
    }
    else
    {
      *(_DWORD *)(v10 + 28) = a3;
    }
    *(_BYTE *)(a1 + 16) = 1;
  }
}

```

## disassembly

```asm
0x18001b720  push    rbx
0x18001b722  push    rsi
0x18001b723  push    rdi
0x18001b724  push    r14
0x18001b726  sub     rsp, 28h
0x18001b72a  mov     rbx, r8
0x18001b72d  mov     esi, edx
0x18001b72f  mov     r14, rcx
0x18001b732  test    r9b, r9b
0x18001b735  jz      short loc_18001B76A
0x18001b737  cmp     byte ptr [rcx+10h], 0
0x18001b73b  jz      short loc_18001B76A
0x18001b73d  mov     rdi, [rcx+28h]
0x18001b741  call    cs:__imp_GetTickCount64
0x18001b747  sub     rax, rdi
0x18001b74a  cmp     rax, [r14+20h]
0x18001b74e  jbe     short loc_18001B76A
0x18001b750  cmp     qword ptr [r14+20h], 0
0x18001b755  jz      short loc_18001B76A
0x18001b757  mov     rax, [r14]
0x18001b75a  mov     rcx, r14
0x18001b75d  mov     dl, [rsp+48h+arg_20]
0x18001b761  mov     rax, [rax+8]
0x18001b765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b76a  mov     rcx, [r14+8]
0x18001b76e  test    rcx, rcx
0x18001b771  jz      short loc_18001B795
0x18001b773  test    esi, esi
0x18001b775  jz      short loc_18001B78D
0x18001b777  sub     esi, 1
0x18001b77a  jz      short loc_18001B787
0x18001b77c  cmp     esi, 1
0x18001b77f  jnz     short loc_18001B790
0x18001b781  inc     word ptr [rcx+18h]
0x18001b785  jmp     short loc_18001B790
0x18001b787  mov     [rcx+20h], rbx
0x18001b78b  jmp     short loc_18001B790
0x18001b78d  mov     [rcx+1Ch], ebx
0x18001b790  mov     byte ptr [r14+10h], 1
0x18001b795  add     rsp, 28h
0x18001b799  pop     r14
0x18001b79b  pop     rdi
0x18001b79c  pop     rsi
0x18001b79d  pop     rbx
0x18001b79e  retn
```
