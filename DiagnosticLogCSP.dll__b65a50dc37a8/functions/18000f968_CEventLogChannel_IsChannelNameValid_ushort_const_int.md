# CEventLogChannel::IsChannelNameValid(ushort const *,int &)

- ea: `0x18000f968`
- end: `0x18000f9f3`
- name: `?IsChannelNameValid@CEventLogChannel@@SAJPEBGAEAH@Z`
- size: `139`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e858`
- `0x18000fd38`

## callees

- `0x180002674`
- `0x18000f968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9c8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f9ba`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f9ba`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f9a0`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f9a0`

## pseudocode

```c
__int64 __fastcall CEventLogChannel::IsChannelNameValid(LPCWSTR ChannelPath, int *a2)
{
  unsigned int v4; // ebx
  EVT_HANDLE v5; // rax

  if ( ChannelPath )
  {
    v4 = 0;
    if ( (unsigned __int8)IsEvtExportLogPresent() )
    {
      v5 = EvtOpenChannelConfig(0, ChannelPath, 0);
      if ( v5 )
      {
        *a2 = 1;
        EvtClose(v5);
        return v4;
      }
      if ( GetLastError() != 15007 )
        return (unsigned int)-2147467259;
    }
    *a2 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000f968  mov     [rsp+arg_0], rbx
0x18000f96d  mov     [rsp+arg_8], rsi
0x18000f972  push    rdi
0x18000f973  sub     rsp, 20h
0x18000f977  mov     rdi, rdx
0x18000f97a  mov     rsi, rcx
0x18000f97d  test    rcx, rcx
0x18000f980  jnz     short loc_18000F989
0x18000f982  mov     ebx, 80070057h
0x18000f987  jmp     short loc_18000F9E0
0x18000f989  xor     ebx, ebx
0x18000f98b  call    IsEvtExportLogPresent
0x18000f990  test    al, al
0x18000f992  jnz     short loc_18000F998
0x18000f994  mov     [rdi], ebx
0x18000f996  jmp     short loc_18000F9E0
0x18000f998  xor     r8d, r8d; Flags
0x18000f99b  mov     rdx, rsi; ChannelPath
0x18000f99e  xor     ecx, ecx; Session
0x18000f9a0  call    cs:__imp_EvtOpenChannelConfig
0x18000f9a7  nop     dword ptr [rax+rax+00h]
0x18000f9ac  test    rax, rax
0x18000f9af  jz      short loc_18000F9C8
0x18000f9b1  mov     rcx, rax; Object
0x18000f9b4  mov     dword ptr [rdi], 1
0x18000f9ba  call    cs:__imp_EvtClose
0x18000f9c1  nop     dword ptr [rax+rax+00h]
0x18000f9c6  jmp     short loc_18000F9E0
0x18000f9c8  call    cs:__imp_GetLastError
0x18000f9cf  nop     dword ptr [rax+rax+00h]
0x18000f9d4  cmp     eax, 3A9Fh
0x18000f9d9  jz      short loc_18000F994
0x18000f9db  mov     ebx, 80004005h
0x18000f9e0  mov     rsi, [rsp+28h+arg_8]
0x18000f9e5  mov     eax, ebx
0x18000f9e7  mov     rbx, [rsp+28h+arg_0]
0x18000f9ec  add     rsp, 20h
0x18000f9f0  pop     rdi
0x18000f9f1  retn
```
