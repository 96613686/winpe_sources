# QueryDriverNodeConfiguration

- ea: `0x140020aa8`
- end: `0x140020bb6`
- name: `QueryDriverNodeConfiguration`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001d2c4`

## callees

- `0x1400207cc`
- `0x140020a0c`
- `0x140020aa8`
- `0x140020bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020b9f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b0f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b46`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b81`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b0f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b46`
- `DEVRTL!DevRtlWriteTextLog` at `0x140020b81`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140020ac1`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140020ac1`

## string_xrefs

- `0x140020af8`: `Failed to open driver configuration key for %ws\%ws. Error = 0x%08X`
- `0x140020b34`: `Unable to query included driver configurations. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall QueryDriverNodeConfiguration(__int64 a1, __int64 a2)
{
  __int64 ThreadLogToken; // r14
  DWORD v5; // ebx
  DWORD LastError; // eax
  int v7; // esi
  DWORD v8; // eax
  DWORD v10; // [rsp+30h] [rbp-38h]
  int v11; // [rsp+80h] [rbp+18h] BYREF

  v11 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( (unsigned int)OpenDriverNodeConfiguration(a1, a2) )
  {
    if ( !(unsigned int)QueryIncludedDriverConfigurations(a1, a2) )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(
        ThreadLogToken,
        1,
        2,
        "Unable to query included driver configurations. Error = 0x%08X",
        LastError);
    }
    if ( (unsigned int)QueryDriverConfigurationNeedReboot(*(_QWORD *)(a2 + 3968), &v11) )
    {
      v7 = v11;
    }
    else
    {
      v7 = 0;
      v8 = GetLastError();
      DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to determine if driver needs reboot. Error = 0x%08X", v8);
    }
    v5 = 0;
    if ( v7 )
      *(_DWORD *)(a2 + 3976) |= 2u;
  }
  else
  {
    v10 = GetLastError();
    v5 = v10;
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      1,
      "Failed to open driver configuration key for %ws\\%ws. Error = 0x%08X",
      a2 + 1056,
      a2 + 1576,
      v10);
  }
  SetLastError(v5);
  return v5 == 0;
}

```

## disassembly

```asm
0x140020aa8  mov     rax, rsp
0x140020aab  push    rbx
0x140020aac  push    rsi
0x140020aad  push    rdi
0x140020aae  push    r14
0x140020ab0  sub     rsp, 48h
0x140020ab4  mov     rdi, rdx
0x140020ab7  mov     dword ptr [rax+18h], 0
0x140020abe  mov     rbx, rcx
0x140020ac1  call    cs:__imp_DevRtlGetThreadLogToken
0x140020ac7  mov     rdx, rdi
0x140020aca  mov     rcx, rbx
0x140020acd  mov     r14, rax
0x140020ad0  call    OpenDriverNodeConfiguration
0x140020ad5  test    eax, eax
0x140020ad7  jnz     short loc_140020B1A
0x140020ad9  call    cs:__imp_GetLastError
0x140020adf  mov     [rsp+68h+var_38], eax
0x140020ae3  lea     rdx, [rdi+420h]
0x140020aea  lea     rcx, [rdi+628h]
0x140020af1  mov     ebx, eax
0x140020af3  mov     [rsp+68h+var_40], rcx
0x140020af8  lea     r9, aFailedToOpenDr; "Failed to open driver configuration key"...
0x140020aff  mov     [rsp+68h+var_48], rdx
0x140020b04  mov     rcx, r14
0x140020b07  mov     edx, 1
0x140020b0c  mov     r8d, edx
0x140020b0f  call    cs:__imp_DevRtlWriteTextLog
0x140020b15  jmp     loc_140020B9D
0x140020b1a  mov     rdx, rdi
0x140020b1d  mov     rcx, rbx
0x140020b20  call    QueryIncludedDriverConfigurations
0x140020b25  test    eax, eax
0x140020b27  jnz     short loc_140020B4C
0x140020b29  call    cs:__imp_GetLastError
0x140020b2f  mov     edx, 1
0x140020b34  lea     r9, aUnableToQueryI; "Unable to query included driver configu"...
0x140020b3b  mov     rcx, r14
0x140020b3e  mov     dword ptr [rsp+68h+var_48], eax
0x140020b42  lea     r8d, [rdx+1]
0x140020b46  call    cs:__imp_DevRtlWriteTextLog
0x140020b4c  mov     rcx, [rdi+0F80h]
0x140020b53  lea     rdx, [rsp+68h+arg_10]
0x140020b5b  call    QueryDriverConfigurationNeedReboot
0x140020b60  test    eax, eax
0x140020b62  jnz     short loc_140020B89
0x140020b64  xor     esi, esi
0x140020b66  call    cs:__imp_GetLastError
0x140020b6c  lea     r9, aUnableToDeterm_1; "Unable to determine if driver needs reb"...
0x140020b73  mov     rcx, r14
0x140020b76  lea     edx, [rsi+1]
0x140020b79  mov     dword ptr [rsp+68h+var_48], eax
0x140020b7d  lea     r8d, [rsi+2]
0x140020b81  call    cs:__imp_DevRtlWriteTextLog
0x140020b87  jmp     short loc_140020B90
0x140020b89  mov     esi, [rsp+68h+arg_10]
0x140020b90  xor     ebx, ebx
0x140020b92  test    esi, esi
0x140020b94  jz      short loc_140020B9D
0x140020b96  or      dword ptr [rdi+0F88h], 2
0x140020b9d  mov     ecx, ebx; dwErrCode
0x140020b9f  call    cs:__imp_SetLastError
0x140020ba5  xor     eax, eax
0x140020ba7  test    ebx, ebx
0x140020ba9  setz    al
0x140020bac  add     rsp, 48h
0x140020bb0  pop     r14
0x140020bb2  pop     rdi
0x140020bb3  pop     rsi
0x140020bb4  pop     rbx
0x140020bb5  retn
```
