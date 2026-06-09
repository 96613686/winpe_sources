# TiSFPRepairFinalize

- ea: `0x1400076d4`
- end: `0x140007750`
- name: `TiSFPRepairFinalize`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140006d68`

## callees

- `0x1400076d4`
- `0x14000e328`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400076ef`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400076ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400076fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400076fa`

## pseudocode

```c
__int64 TiSFPRepairFinalize()
{
  signed int v0; // ebx
  __int64 (*ProcAddress)(void); // rax
  signed int LastError; // eax
  const char *v3; // r9
  int v4; // edx
  int v5; // eax

  v0 = 0;
  if ( vhSfpModule )
  {
    ProcAddress = GetProcAddress(vhSfpModule, "SfpFinalize");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v3 = "Failed to get proc address on SfpFinalize";
      if ( v0 >= 0 )
        v0 = -2147467259;
      v4 = v0;
      goto LABEL_10;
    }
    v5 = ProcAddress();
    v0 = v5;
    if ( v5 < 0 )
    {
      v3 = "Failed to call SfpFinalize";
      v4 = v5;
LABEL_10:
      CBSWdsLog(0x4000000u, v4, (size_t *)1, v3);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400076d4  push    rbx
0x1400076d6  sub     rsp, 20h
0x1400076da  mov     rcx, cs:?vhSfpModule@@3PEAUHINSTANCE__@@EA; hModule
0x1400076e1  xor     ebx, ebx
0x1400076e3  test    rcx, rcx
0x1400076e6  jz      short loc_140007748
0x1400076e8  lea     rdx, aSfpfinalize; "SfpFinalize"
0x1400076ef  call    cs:__imp_GetProcAddress
0x1400076f5  test    rax, rax
0x1400076f8  jnz     short loc_140007724
0x1400076fa  call    cs:__imp_GetLastError
0x140007700  mov     ebx, eax
0x140007702  test    eax, eax
0x140007704  jle     short loc_14000770F
0x140007706  movzx   ebx, ax
0x140007709  or      ebx, 80070000h
0x14000770f  test    ebx, ebx
0x140007711  lea     r9, aFailedToGetPro_5; "Failed to get proc address on SfpFinali"...
0x140007718  mov     eax, 80004005h
0x14000771d  cmovns  ebx, eax
0x140007720  mov     edx, ebx
0x140007722  jmp     short loc_140007738
0x140007724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007729  mov     ebx, eax
0x14000772b  test    eax, eax
0x14000772d  jns     short loc_140007748
0x14000772f  lea     r9, aFailedToCallSf; "Failed to call SfpFinalize"
0x140007736  mov     edx, eax
0x140007738  mov     r8d, 1
0x14000773e  mov     ecx, 4000000h
0x140007743  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007748  mov     eax, ebx
0x14000774a  add     rsp, 20h
0x14000774e  pop     rbx
0x14000774f  retn
```
