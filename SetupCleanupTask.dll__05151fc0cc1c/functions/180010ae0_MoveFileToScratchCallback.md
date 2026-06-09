# MoveFileToScratchCallback

- ea: `0x180010ae0`
- end: `0x180010bb8`
- name: `MoveFileToScratchCallback`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x18000638c`
- `0x180010ae0`
- `0x180010c98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ba0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b26`
- `WDSCORE!CurrentIP` at `0x180010b2e`
- `WDSCORE!CurrentIP` at `0x180010b2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010b98`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010b98`

## string_xrefs

- `0x180010b81`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180010b57`: `MoveFileToScratchCallback`
- `0x180010b38`: `MoveFileToScratchCallback: Failed to move %s to Scratch Reserve. hr = 0x%08X`

## pseudocode

```c
__int64 __fastcall MoveFileToScratchCallback(__int64 a1, __int64 *a2)
{
  const char *v3; // rcx
  __int64 v4; // rdx
  signed int v5; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax

  if ( !a2 )
    return 0;
  if ( !a1 )
    return 0;
  v3 = *(const char **)(a1 + 40);
  if ( !v3 )
    return 0;
  v4 = *a2;
  if ( !v4 )
    return 0;
  v5 = MoveToScratch(v3, v4);
  if ( v5 < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           50331648,
           "MoveFileToScratchCallback: Failed to move %s to Scratch Reserve. hr = 0x%08X",
           *(const char **)(a1 + 40),
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      715,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"MoveFileToScratchCallback",
      v7,
      LastError,
      0,
      0);
    SetLastError(v5);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180010ae0  push    rbx
0x180010ae2  push    rbp
0x180010ae3  push    rsi
0x180010ae4  push    rdi
0x180010ae5  sub     rsp, 68h
0x180010ae9  mov     rsi, rcx
0x180010aec  test    rdx, rdx
0x180010aef  jz      loc_180010BA6
0x180010af5  test    rcx, rcx
0x180010af8  jz      loc_180010BA6
0x180010afe  mov     rcx, [rcx+28h]
0x180010b02  test    rcx, rcx
0x180010b05  jz      loc_180010BA6
0x180010b0b  mov     rdx, [rdx]
0x180010b0e  test    rdx, rdx
0x180010b11  jz      loc_180010BA6
0x180010b17  call    MoveToScratch
0x180010b1c  mov     ebp, eax
0x180010b1e  test    eax, eax
0x180010b20  jns     loc_180010BB1
0x180010b26  call    cs:__imp_GetLastError
0x180010b2c  mov     edi, eax
0x180010b2e  call    cs:__imp_CurrentIP
0x180010b34  mov     r8, [rsi+28h]
0x180010b38  lea     rdx, aMovefiletoscra_0; "MoveFileToScratchCallback: Failed to mo"...
0x180010b3f  mov     r9d, ebp
0x180010b42  mov     ecx, 3000000h; unsigned int
0x180010b47  mov     rbx, rax
0x180010b4a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180010b4f  mov     [rsp+88h+var_38], 0
0x180010b57  lea     rcx, aMovefiletoscra; "MoveFileToScratchCallback"
0x180010b5e  mov     [rsp+88h+var_40], 0
0x180010b67  lea     r8, aD_0; "D"
0x180010b6e  mov     [rsp+88h+var_48], edi
0x180010b72  xor     r9d, r9d
0x180010b75  mov     [rsp+88h+var_50], rbx
0x180010b7a  xor     edx, edx
0x180010b7c  mov     [rsp+88h+var_58], rcx
0x180010b81  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180010b88  mov     [rsp+88h+var_60], rcx
0x180010b8d  mov     rcx, rax
0x180010b90  mov     [rsp+88h+var_68], 2CBh
0x180010b98  call    cs:__imp_WdsSetupLogMessageW
0x180010b9e  mov     ecx, ebp; dwErrCode
0x180010ba0  call    cs:__imp_SetLastError
0x180010ba6  xor     eax, eax
0x180010ba8  add     rsp, 68h
0x180010bac  pop     rdi
0x180010bad  pop     rsi
0x180010bae  pop     rbp
0x180010baf  pop     rbx
0x180010bb0  retn
0x180010bb1  mov     eax, 1
0x180010bb6  jmp     short loc_180010BA8
```
