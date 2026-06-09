# UpdateEpMapperPortsIfNecessary

- ea: `0x180002798`
- end: `0x180002843`
- name: `UpdateEpMapperPortsIfNecessary`
- size: `171`
- prototype: `__int64 __fastcall(char *String1, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800014b0`
- `0x1800018a0`
- `0x180002714`

## callees

- `0x1800010b0`
- `0x180002798`
- `0x180005c9c`
- `0x1800063a8`
- `0x18000804c`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x1800027ad`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x1800027c8`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x1800027ad`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x1800027c8`
- `ext-ms-win-rpc-firewallportuse-l1-1-0!ResetIndicatedPortsInUse` at `0x18000280c`
- `ext-ms-win-rpc-firewallportuse-l1-1-0!ResetIndicatedPortsInUse` at `0x18000280c`

## pseudocode

```c
__int64 __fastcall UpdateEpMapperPortsIfNecessary(char *String1, unsigned int a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v7; // eax
  __int16 v8; // cx

  if ( !_stricmp(String1, "ncacn_ip_tcp") )
  {
    v4 = 1;
    goto LABEL_3;
  }
  v4 = 0;
  if ( !_stricmp(String1, "ncacn_http") )
  {
LABEL_3:
    if ( !_InterlockedCompareExchange(&FWResetHappened, 1, 0) && IsIndicatePortInUsePresent() )
    {
      v7 = ResetIndicatedPortsInUse();
      RPC_STATUSFromHRESULT(v7);
    }
    if ( v4 )
    {
      v5 = RpcExtFWIndicatePortInUse(135, a2);
      v4 = v5;
      if ( !v5 )
        return v4;
      v8 = 21;
    }
    else
    {
      v5 = RpcExtFWIndicatePortInUse(593, a2);
      v4 = v5;
      if ( !v5 )
        return v4;
      v8 = 22;
    }
    LogEpmapDebugEvent(v8, v5, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x180002798  push    rbx
0x18000279a  push    rbp
0x18000279b  push    rsi
0x18000279c  push    rdi
0x18000279d  sub     rsp, 28h
0x1800027a1  mov     edi, edx
0x1800027a3  mov     rsi, rcx
0x1800027a6  lea     rdx, String2; "ncacn_ip_tcp"
0x1800027ad  call    cs:__imp__stricmp
0x1800027b3  mov     ebp, 1
0x1800027b8  test    eax, eax
0x1800027ba  jz      short loc_1800027FF
0x1800027bc  lea     rdx, aNcacnHttp; "ncacn_http"
0x1800027c3  mov     rcx, rsi; String1
0x1800027c6  xor     ebx, ebx
0x1800027c8  call    cs:__imp__stricmp
0x1800027ce  test    eax, eax
0x1800027d0  jnz     short loc_1800027F4
0x1800027d2  xor     eax, eax
0x1800027d4  lock cmpxchg cs:FWResetHappened, ebp
0x1800027dc  jz      short loc_180002803
0x1800027de  mov     edx, edi
0x1800027e0  test    ebx, ebx
0x1800027e2  jnz     short loc_18000281B
0x1800027e4  mov     ecx, 251h
0x1800027e9  call    RpcExtFWIndicatePortInUse
0x1800027ee  mov     ebx, eax
0x1800027f0  test    eax, eax
0x1800027f2  jnz     short loc_180002832
0x1800027f4  mov     eax, ebx
0x1800027f6  add     rsp, 28h
0x1800027fa  pop     rdi
0x1800027fb  pop     rsi
0x1800027fc  pop     rbp
0x1800027fd  pop     rbx
0x1800027fe  retn
0x1800027ff  mov     ebx, ebp
0x180002801  jmp     short loc_1800027D2
0x180002803  call    IsIndicatePortInUsePresent
0x180002808  test    al, al
0x18000280a  jz      short loc_1800027DE
0x18000280c  call    cs:__imp_ResetIndicatedPortsInUse
0x180002812  mov     ecx, eax; int
0x180002814  call    ?RPC_STATUSFromHRESULT@@YAJJ@Z; RPC_STATUSFromHRESULT(long)
0x180002819  jmp     short loc_1800027DE
0x18000281b  mov     ecx, 87h
0x180002820  call    RpcExtFWIndicatePortInUse
0x180002825  mov     ebx, eax
0x180002827  test    eax, eax
0x180002829  jz      short loc_1800027F4
0x18000282b  mov     ecx, 15h
0x180002830  jmp     short loc_180002837
0x180002832  mov     ecx, 16h
0x180002837  xor     r8d, r8d
0x18000283a  mov     edx, eax
0x18000283c  call    LogEpmapDebugEvent
0x180002841  jmp     short loc_1800027F4
```
