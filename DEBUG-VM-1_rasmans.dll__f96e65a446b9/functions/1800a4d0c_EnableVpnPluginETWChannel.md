# EnableVpnPluginETWChannel

- ea: `0x1800a4d0c`
- end: `0x1800a4dd8`
- name: `EnableVpnPluginETWChannel`
- size: `204`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180021e70`

## callees

- `0x1800a4d0c`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4dba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a4d31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a4d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a4d31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a4d4d`
- `wevtapi!EvtOpenChannelConfig` at `0x1800a4d63`
- `wevtapi!EvtOpenChannelConfig` at `0x1800a4d63`
- `wevtapi!EvtClose` at `0x1800a4dc5`
- `wevtapi!EvtClose` at `0x1800a4dc5`

## string_xrefs

- `0x1800a4d20`: `EvtSetChannelConfigProperty`
- `0x1800a4d43`: `EvtSaveChannelConfig`

## pseudocode

```c
__int64 __fastcall EnableVpnPluginETWChannel(LPCWSTR ChannelPath, HMODULE hModule)
{
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rbp
  FARPROC v6; // rsi
  EVT_HANDLE v7; // rax
  void *v8; // rdi
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF

  LastError = 0;
  v10 = 0;
  ProcAddress = GetProcAddress(hModule, "EvtSetChannelConfigProperty");
  if ( ProcAddress )
  {
    v6 = GetProcAddress(hModule, "EvtSaveChannelConfig");
    if ( v6 )
    {
      v7 = EvtOpenChannelConfig(0, ChannelPath, 0);
      v8 = v7;
      if ( v7 )
      {
        *(_QWORD *)((char *)&v10 + 4) = 0;
        HIDWORD(v10) = 13;
        LODWORD(v10) = 1;
        if ( !((unsigned int (__fastcall *)(EVT_HANDLE, _QWORD, _QWORD, __int128 *))ProcAddress)(v7, 0, 0, &v10)
          || !((unsigned int (__fastcall *)(void *, _QWORD))v6)(v8, 0) )
        {
          LastError = GetLastError();
        }
        EvtClose(v8);
      }
      else
      {
        return GetLastError();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a4d0c  push    rbx
0x1800a4d0e  push    rbp
0x1800a4d0f  push    rsi
0x1800a4d10  push    rdi
0x1800a4d11  push    r14
0x1800a4d13  sub     rsp, 40h
0x1800a4d17  mov     rdi, rdx
0x1800a4d1a  mov     r14, rcx
0x1800a4d1d  xorps   xmm0, xmm0
0x1800a4d20  lea     rdx, aEvtsetchannelc; "EvtSetChannelConfigProperty"
0x1800a4d27  mov     rcx, rdi; hModule
0x1800a4d2a  xor     ebx, ebx
0x1800a4d2c  movups  [rsp+68h+var_38], xmm0
0x1800a4d31  call    cs:__imp_GetProcAddress
0x1800a4d37  mov     rbp, rax
0x1800a4d3a  test    rax, rax
0x1800a4d3d  jz      loc_1800A4DCB
0x1800a4d43  lea     rdx, aEvtsavechannel; "EvtSaveChannelConfig"
0x1800a4d4a  mov     rcx, rdi; hModule
0x1800a4d4d  call    cs:__imp_GetProcAddress
0x1800a4d53  mov     rsi, rax
0x1800a4d56  test    rax, rax
0x1800a4d59  jz      short loc_1800A4DCB
0x1800a4d5b  xor     r8d, r8d; Flags
0x1800a4d5e  mov     rdx, r14; ChannelPath
0x1800a4d61  xor     ecx, ecx; Session
0x1800a4d63  call    cs:__imp_EvtOpenChannelConfig
0x1800a4d69  mov     rdi, rax
0x1800a4d6c  test    rax, rax
0x1800a4d6f  jnz     short loc_1800A4D7B
0x1800a4d71  call    cs:__imp_GetLastError
0x1800a4d77  mov     ebx, eax
0x1800a4d79  jmp     short loc_1800A4DCB
0x1800a4d7b  lea     r9, [rsp+68h+var_38]
0x1800a4d80  mov     qword ptr [rsp+68h+var_38+4], rbx
0x1800a4d85  xor     r8d, r8d
0x1800a4d88  mov     dword ptr [rsp+68h+var_38+0Ch], 0Dh
0x1800a4d90  xor     edx, edx
0x1800a4d92  mov     dword ptr [rsp+68h+var_38], 1
0x1800a4d9a  mov     rcx, rdi
0x1800a4d9d  mov     rax, rbp
0x1800a4da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4da5  test    eax, eax
0x1800a4da7  jz      short loc_1800A4DBA
0x1800a4da9  xor     edx, edx
0x1800a4dab  mov     rcx, rdi
0x1800a4dae  mov     rax, rsi
0x1800a4db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4db6  test    eax, eax
0x1800a4db8  jnz     short loc_1800A4DC2
0x1800a4dba  call    cs:__imp_GetLastError
0x1800a4dc0  mov     ebx, eax
0x1800a4dc2  mov     rcx, rdi; Object
0x1800a4dc5  call    cs:__imp_EvtClose
0x1800a4dcb  mov     eax, ebx
0x1800a4dcd  add     rsp, 40h
0x1800a4dd1  pop     r14
0x1800a4dd3  pop     rdi
0x1800a4dd4  pop     rsi
0x1800a4dd5  pop     rbp
0x1800a4dd6  pop     rbx
0x1800a4dd7  retn
```
