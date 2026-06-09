# Windows::Storage::StateABIHelpers::Logging::GetPublisherCacheFolderPathString(ushort const *,void * const,uint,ushort *)

- ea: `0x180040978`
- end: `0x1800409c9`
- name: `?GetPublisherCacheFolderPathString@Logging@StateABIHelpers@Storage@Windows@@CAJPEBGQEAXIPEAG@Z`
- size: `81`
- prototype: `int __fastcall(const wchar_t *folderName, void *const applicationStateHandle, unsigned int folderPath, wchar_t *folderName)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180040d44`

## callees

- `0x180021fc4`
- `0x180040978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409b6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x1800409ac`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x1800409ac`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::Logging::GetPublisherCacheFolderPathString(
        HSTRING__ *folderName,
        Windows::Storage::IApplicationData3 *applicationStateHandle,
        unsigned int folderPath,
        Windows::Storage::IStorageFolder **a4)
{
  unsigned int v4; // ebx

  v4 = 0;
  if ( !applicationStateHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs(folderName);
  if ( !GetPublisherCacheFolder(applicationStateHandle, folderName, a4) )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x180040978  push    rbx
0x18004097a  push    rbp
0x18004097b  push    rsi
0x18004097c  push    rdi
0x18004097d  sub     rsp, 38h
0x180040981  xor     ebx, ebx
0x180040983  mov     [rsp+58h+folderPathCch], 105h
0x18004098b  mov     rsi, folderPath
0x18004098e  mov     rdi, applicationStateHandle
0x180040991  mov     rbp, folderName
0x180040994  test    applicationStateHandle, applicationStateHandle
0x180040997  jnz     short loc_18004099E
0x180040999  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "applicationStateHandle != INVALID_STATE_HANDLE")
0x18004099e  lea     folderPath, [rsp+58h+folderPathCch]
0x1800409a3  mov     r8, rsi; Windows::Storage::IStorageFolder **
0x1800409a6  mov     applicationStateHandle, rbp; HSTRING__ *
0x1800409a9  mov     folderName, rdi; this
0x1800409ac  call    cs:__imp_GetPublisherCacheFolder
0x1800409b2  test    eax, eax
0x1800409b4  jnz     short loc_1800409BE
0x1800409b6  call    cs:__imp_GetLastError
0x1800409bc  mov     ebx, eax
0x1800409be  mov     eax, ebx
0x1800409c0  add     rsp, 38h
0x1800409c4  pop     rdi
0x1800409c5  pop     rsi
0x1800409c6  pop     rbp
0x1800409c7  pop     rbx
0x1800409c8  retn
```
