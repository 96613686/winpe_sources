# pSpSignBuildCatalogFilename

- ea: `0x14002ee88`
- end: `0x14002ef31`
- name: `pSpSignBuildCatalogFilename`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002e91c`
- `0x14002ed80`

## callees

- `0x1400070bc`
- `0x14000bb4c`
- `0x14002ee88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eeb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eeb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002eefc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002eefc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002eeaa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002eeaa`

## string_xrefs

- `0x14002eecb`: `System32\catroot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}`

## pseudocode

```c
_BOOL8 __fastcall pSpSignBuildCatalogFilename(__int64 a1, size_t *a2, unsigned __int16 *a3)
{
  UINT SystemWindowsDirectoryW; // eax
  DWORD LastError; // ebx

  if ( a2 )
  {
    if ( (int)StringCchCopyW(a3, 0x104u, a2) < 0 )
    {
      LastError = 13;
      goto LABEL_8;
    }
  }
  else
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(a3, 0x104u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = GetLastError();
      goto LABEL_8;
    }
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
LABEL_7:
      LastError = 122;
      goto LABEL_8;
    }
  }
  if ( !(unsigned int)pSetupConcatenatePaths(a3, L"System32\\catroot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}", 260) )
    goto LABEL_7;
  LastError = 0;
  if ( !(unsigned int)pSetupConcatenatePaths(a3, a1, 260) )
    goto LABEL_7;
LABEL_8:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14002ee88  mov     [rsp+arg_0], rbx
0x14002ee8d  mov     [rsp+arg_8], rbp
0x14002ee92  push    rsi
0x14002ee93  sub     rsp, 20h
0x14002ee97  mov     rbp, rcx
0x14002ee9a  mov     rcx, r8; unsigned __int16 *
0x14002ee9d  mov     rsi, r8
0x14002eea0  test    rdx, rdx
0x14002eea3  jnz     short loc_14002EF19
0x14002eea5  mov     edx, 104h; uSize
0x14002eeaa  call    cs:__imp_GetSystemWindowsDirectoryW
0x14002eeb0  test    eax, eax
0x14002eeb2  jnz     short loc_14002EEBE
0x14002eeb4  call    cs:__imp_GetLastError
0x14002eeba  mov     ebx, eax
0x14002eebc  jmp     short loc_14002EEFA
0x14002eebe  cmp     eax, 104h
0x14002eec3  jnb     short loc_14002EEF5
0x14002eec5  mov     r8d, 104h
0x14002eecb  lea     rdx, aSystem32Catroo; "System32\\catroot\\{F750E6C3-38EE-11D1-"...
0x14002eed2  mov     rcx, rsi
0x14002eed5  call    pSetupConcatenatePaths
0x14002eeda  test    eax, eax
0x14002eedc  jz      short loc_14002EEF5
0x14002eede  mov     r8d, 104h
0x14002eee4  mov     rdx, rbp
0x14002eee7  mov     rcx, rsi
0x14002eeea  xor     ebx, ebx
0x14002eeec  call    pSetupConcatenatePaths
0x14002eef1  test    eax, eax
0x14002eef3  jnz     short loc_14002EEFA
0x14002eef5  mov     ebx, 7Ah ; 'z'
0x14002eefa  mov     ecx, ebx; dwErrCode
0x14002eefc  call    cs:__imp_SetLastError
0x14002ef02  mov     rbp, [rsp+28h+arg_8]
0x14002ef07  xor     eax, eax
0x14002ef09  test    ebx, ebx
0x14002ef0b  mov     rbx, [rsp+28h+arg_0]
0x14002ef10  setz    al
0x14002ef13  add     rsp, 20h
0x14002ef17  pop     rsi
0x14002ef18  retn
0x14002ef19  mov     r8, rdx; unsigned __int16 *
0x14002ef1c  mov     edx, 104h; unsigned __int64
0x14002ef21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002ef26  test    eax, eax
0x14002ef28  jns     short loc_14002EEC5
0x14002ef2a  mov     ebx, 0Dh
0x14002ef2f  jmp     short loc_14002EEFA
```
