# StartDisconnectTimer(void)

- ea: `0x14000a628`
- end: `0x14000a6ad`
- name: `?StartDisconnectTimer@@YAXXZ`
- size: `133`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140006b40`
- `0x140006eb0`
- `0x14000728c`

## callees

- `0x1400076b8`
- `0x14000a628`
- `0x14000bef0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a6a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a6a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000a63a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000a63a`

## pseudocode

```c
void StartDisconnectTimer(void)
{
  __int64 v0; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v0 = *(_QWORD *)&SystemTimeAsFileTime + 5000000LL;
  SystemTimeAsFileTime.dwLowDateTime += 5000000;
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  }
  if ( !KeepTaskRunning() )
    SetThreadpoolTimer(g_pDisconnectTimer, &SystemTimeAsFileTime, 0, 0x64u);
}

```

## disassembly

```asm
0x14000a628  sub     rsp, 28h
0x14000a62c  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000a631  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14000a63a  call    cs:__imp_GetSystemTimeAsFileTime
0x14000a640  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x14000a645  add     rax, 4C4B40h
0x14000a64b  mov     [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], eax
0x14000a64f  shr     rax, 20h
0x14000a653  mov     [rsp+28h+SystemTimeAsFileTime.dwHighDateTime], eax
0x14000a657  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a65e  lea     rax, WPP_GLOBAL_Control
0x14000a665  cmp     rcx, rax
0x14000a668  jz      short loc_14000A684
0x14000a66a  cmp     byte ptr [rcx+19h], 5
0x14000a66e  jb      short loc_14000A684
0x14000a670  test    byte ptr [rcx+1Ch], 1
0x14000a674  jz      short loc_14000A684
0x14000a676  mov     rcx, [rcx+10h]
0x14000a67a  mov     edx, 0Ah
0x14000a67f  call    WPP_SF_
0x14000a684  call    ?KeepTaskRunning@@YA_NXZ; KeepTaskRunning(void)
0x14000a689  test    al, al
0x14000a68b  jnz     short loc_14000A6A8
0x14000a68d  mov     rcx, cs:?g_pDisconnectTimer@@3PEAU_TP_TIMER@@EA; pti
0x14000a694  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; pftDueTime
0x14000a699  mov     r9d, 64h ; 'd'; msWindowLength
0x14000a69f  xor     r8d, r8d; msPeriod
0x14000a6a2  call    cs:__imp_SetThreadpoolTimer
0x14000a6a8  add     rsp, 28h
0x14000a6ac  retn
```
