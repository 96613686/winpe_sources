# LocalKdcSamBackend::RegisterWaiter(void)

- ea: `0x18006d260`
- end: `0x18006d2cf`
- name: `?RegisterWaiter@LocalKdcSamBackend@@UEAA_NXZ`
- size: `111`
- prototype: `bool __fastcall(LocalKdcSamBackend *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800101ec`
- `0x180037d1c`
- `0x18006d260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29a`

## string_xrefs

- `0x18006d266`: `\Security\KdcKerbReadyEvent`

## pseudocode

```c
char __fastcall LocalKdcSamBackend::RegisterWaiter(LocalKdcSamBackend *this, __int64 a2)
{
  DWORD LastError; // eax

  hKdcKerbReadyEvent = KdcOpenEvent((__int64)this, a2, L"\\Security\\KdcKerbReadyEvent");
  if ( hKdcKerbReadyEvent )
  {
    *((_BYTE *)this + 9) = 1;
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids, LastError);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18006d260  push    rbx
0x18006d262  sub     rsp, 20h
0x18006d266  lea     r8, aSecurityKdcker; "\\Security\\KdcKerbReadyEvent"
0x18006d26d  mov     rbx, rcx
0x18006d270  call    ?KdcOpenEvent@@YAPEAXKHPEAG@Z; KdcOpenEvent(ulong,int,ushort *)
0x18006d275  mov     cs:?hKdcKerbReadyEvent@@3PEAXEA, rax; void * hKdcKerbReadyEvent
0x18006d27c  test    rax, rax
0x18006d27f  jnz     short loc_18006D2C3
0x18006d281  mov     rax, cs:WPP_GLOBAL_Control
0x18006d288  lea     rcx, WPP_GLOBAL_Control
0x18006d28f  cmp     rax, rcx
0x18006d292  jz      short loc_18006D2BF
0x18006d294  test    byte ptr [rax+1Ch], 1
0x18006d298  jz      short loc_18006D2BF
0x18006d29a  call    cs:__imp_GetLastError
0x18006d2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d2a7  lea     r8, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids
0x18006d2ae  mov     edx, 11h
0x18006d2b3  mov     r9d, eax
0x18006d2b6  mov     rcx, [rcx+10h]
0x18006d2ba  call    WPP_SF_d
0x18006d2bf  xor     al, al
0x18006d2c1  jmp     short loc_18006D2C9
0x18006d2c3  mov     byte ptr [rbx+9], 1
0x18006d2c7  mov     al, 1
0x18006d2c9  add     rsp, 20h
0x18006d2cd  pop     rbx
0x18006d2ce  retn
```
