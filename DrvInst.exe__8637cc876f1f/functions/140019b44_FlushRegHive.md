# FlushRegHive

- ea: `0x140019b44`
- end: `0x140019c0f`
- name: `FlushRegHive`
- size: `203`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001ae4c`

## callees

- `0x140019b44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140019bf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140019bf2`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x140019b96`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x140019b96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140019b85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140019b85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019bea`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019bbc`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019bda`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019bbc`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019bda`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140019b5f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140019b5f`

## string_xrefs

- `0x140019baa`: `Flushed %ws registry hive.`
- `0x140019bc8`: `Unable to flush %ws registry hive. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall FlushRegHive(LPCWSTR lpSubKey)
{
  __int64 ThreadLogToken; // rsi
  LSTATUS v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2000000u, &hKey);
  if ( !v3 )
  {
    v4 = RegFlushKey(hKey);
    v3 = v4;
    if ( v4 )
      DevRtlWriteTextLog(ThreadLogToken, 1, 65538, "Unable to flush %ws registry hive. Error = 0x%08X", lpSubKey, v4);
    else
      DevRtlWriteTextLog(ThreadLogToken, 1, 65540, "Flushed %ws registry hive.", lpSubKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v3);
  return v3 == 0;
}

```

## disassembly

```asm
0x140019b44  mov     [rsp+arg_0], rbx
0x140019b49  mov     [rsp+arg_10], rsi
0x140019b4e  push    rdi
0x140019b4f  sub     rsp, 30h
0x140019b53  mov     rdi, rcx
0x140019b56  mov     [rsp+38h+hKey], 0
0x140019b5f  call    cs:__imp_DevRtlGetThreadLogToken
0x140019b65  mov     r9d, 2000000h; samDesired
0x140019b6b  xor     r8d, r8d; ulOptions
0x140019b6e  mov     rsi, rax
0x140019b71  mov     rdx, rdi; lpSubKey
0x140019b74  lea     rax, [rsp+38h+hKey]
0x140019b79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140019b80  mov     [rsp+38h+phkResult], rax; phkResult
0x140019b85  call    cs:__imp_RegOpenKeyExW
0x140019b8b  mov     ebx, eax
0x140019b8d  test    eax, eax
0x140019b8f  jnz     short loc_140019BE0
0x140019b91  mov     rcx, [rsp+38h+hKey]; hKey
0x140019b96  call    cs:__imp_RegFlushKey
0x140019b9c  mov     edx, 1
0x140019ba1  mov     rcx, rsi
0x140019ba4  mov     ebx, eax
0x140019ba6  test    eax, eax
0x140019ba8  jnz     short loc_140019BC4
0x140019baa  lea     r9, aFlushedWsRegis; "Flushed %ws registry hive."
0x140019bb1  mov     [rsp+38h+phkResult], rdi
0x140019bb6  mov     r8d, 10004h
0x140019bbc  call    cs:__imp_DevRtlWriteTextLog
0x140019bc2  jmp     short loc_140019BE0
0x140019bc4  mov     [rsp+38h+var_10], eax
0x140019bc8  lea     r9, aUnableToFlushW_0; "Unable to flush %ws registry hive. Erro"...
0x140019bcf  mov     r8d, 10002h
0x140019bd5  mov     [rsp+38h+phkResult], rdi
0x140019bda  call    cs:__imp_DevRtlWriteTextLog
0x140019be0  mov     rcx, [rsp+38h+hKey]; hKey
0x140019be5  test    rcx, rcx
0x140019be8  jz      short loc_140019BF0
0x140019bea  call    cs:__imp_RegCloseKey
0x140019bf0  mov     ecx, ebx; dwErrCode
0x140019bf2  call    cs:__imp_SetLastError
0x140019bf8  mov     rsi, [rsp+38h+arg_10]
0x140019bfd  xor     eax, eax
0x140019bff  test    ebx, ebx
0x140019c01  mov     rbx, [rsp+38h+arg_0]
0x140019c06  setz    al
0x140019c09  add     rsp, 30h
0x140019c0d  pop     rdi
0x140019c0e  retn
```
