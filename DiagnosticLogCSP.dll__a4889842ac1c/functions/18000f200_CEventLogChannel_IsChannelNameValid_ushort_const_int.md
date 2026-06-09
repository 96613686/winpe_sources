# CEventLogChannel::IsChannelNameValid(ushort const *,int &)

- ea: `0x18000f200`
- end: `0x18000f278`
- name: `?IsChannelNameValid@CEventLogChannel@@SAJPEBGAEAH@Z`
- size: `120`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e158`
- `0x18000f580`

## callees

- `0x180002644`
- `0x18000f200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f254`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f24c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f24c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f238`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f238`

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
0x18000f200  mov     [rsp+arg_0], rbx
0x18000f205  mov     [rsp+arg_8], rsi
0x18000f20a  push    rdi
0x18000f20b  sub     rsp, 20h
0x18000f20f  mov     rdi, rdx
0x18000f212  mov     rsi, rcx
0x18000f215  test    rcx, rcx
0x18000f218  jnz     short loc_18000F221
0x18000f21a  mov     ebx, 80070057h
0x18000f21f  jmp     short loc_18000F266
0x18000f221  xor     ebx, ebx
0x18000f223  call    IsEvtExportLogPresent
0x18000f228  test    al, al
0x18000f22a  jnz     short loc_18000F230
0x18000f22c  mov     [rdi], ebx
0x18000f22e  jmp     short loc_18000F266
0x18000f230  xor     r8d, r8d; Flags
0x18000f233  mov     rdx, rsi; ChannelPath
0x18000f236  xor     ecx, ecx; Session
0x18000f238  call    cs:__imp_EvtOpenChannelConfig
0x18000f23e  test    rax, rax
0x18000f241  jz      short loc_18000F254
0x18000f243  mov     rcx, rax; Object
0x18000f246  mov     dword ptr [rdi], 1
0x18000f24c  call    cs:__imp_EvtClose
0x18000f252  jmp     short loc_18000F266
0x18000f254  call    cs:__imp_GetLastError
0x18000f25a  cmp     eax, 3A9Fh
0x18000f25f  jz      short loc_18000F22C
0x18000f261  mov     ebx, 80004005h
0x18000f266  mov     rsi, [rsp+28h+arg_8]
0x18000f26b  mov     eax, ebx
0x18000f26d  mov     rbx, [rsp+28h+arg_0]
0x18000f272  add     rsp, 20h
0x18000f276  pop     rdi
0x18000f277  retn
```
