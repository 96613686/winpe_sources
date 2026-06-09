# TiCoreSetTiDemandStart

- ea: `0x14000d420`
- end: `0x14000d4ca`
- name: `TiCoreSetTiDemandStart`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000d23c`
- `0x14000d5c8`
- `0x140015b90`

## callees

- `0x14000d420`
- `0x140017658`
- `0x140019828`
- `0x14001acbc`
- `0x14001e19c`
- `0x14001e32c`

## string_xrefs

- `0x14000d48a`: `Failed to open TrustedInstaller service to query and change config.`
- `0x14000d451`: `SYSTEM\CurrentControlSet\Services\TrustedInstaller`
- `0x14000d463`: `Failed to change Trusted Installer to demand-start service via the registry.`
- `0x14000d4a9`: `Failed to change the Trusted Installer to a demand start service via SvcChangeConfig.`

## pseudocode

```c
__int64 TiCoreSetTiDemandStart()
{
  HKEY v0; // rcx
  int v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  SC_HANDLE v7; // [rsp+70h] [rbp+8h] BYREF

  LODWORD(v7) = 0;
  WdsOobeInProgress((unsigned int *)&v7);
  if ( (_DWORD)v7 )
  {
    v1 = CbsRegSetDWORDValue(v0, L"SYSTEM\\CurrentControlSet\\Services\\TrustedInstaller", 0, L"Start", 3u);
    v2 = v1;
    if ( v1 < 0 )
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)v1,
        (size_t *)1,
        "Failed to change Trusted Installer to demand-start service via the registry.");
  }
  else
  {
    v7 = 0;
    v3 = SvcOpen((__int64)v0, 3u, &v7);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v5 = SvcChangeConfig(v7, v4, 3u);
      v2 = v5;
      if ( v5 < 0 )
        CBSWdsLogLight(
          0x4000000u,
          (unsigned int)v5,
          (size_t *)1,
          "Failed to change the Trusted Installer to a demand start service via SvcChangeConfig.");
    }
    else
    {
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)v3,
        (size_t *)1,
        "Failed to open TrustedInstaller service to query and change config.");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000d420  push    rbx
0x14000d422  sub     rsp, 60h
0x14000d426  lea     rcx, [rsp+68h+arg_0]; unsigned int *
0x14000d42b  mov     dword ptr [rsp+68h+arg_0], 0
0x14000d433  call    ?WdsOobeInProgress@@YAJPEAK@Z; WdsOobeInProgress(ulong *)
0x14000d438  cmp     dword ptr [rsp+68h+arg_0], 0
0x14000d43d  jz      short loc_14000D46C
0x14000d43f  lea     r9, aStart; "Start"
0x14000d446  mov     [rsp+68h+var_48], 3; unsigned int
0x14000d44e  xor     r8d, r8d; unsigned int
0x14000d451  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Tr"...
0x14000d458  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x14000d45d  mov     ebx, eax
0x14000d45f  test    eax, eax
0x14000d461  jns     short loc_14000D4C2
0x14000d463  lea     r9, aFailedToChange_0; "Failed to change Trusted Installer to d"...
0x14000d46a  jmp     short loc_14000D4B0
0x14000d46c  lea     r8, [rsp+68h+arg_0]
0x14000d471  mov     [rsp+68h+arg_0], 0
0x14000d47a  mov     edx, 3
0x14000d47f  call    SvcOpen
0x14000d484  mov     ebx, eax
0x14000d486  test    eax, eax
0x14000d488  jns     short loc_14000D493
0x14000d48a  lea     r9, aFailedToOpenTr_0; "Failed to open TrustedInstaller service"...
0x14000d491  jmp     short loc_14000D4B0
0x14000d493  mov     rcx, [rsp+68h+arg_0]
0x14000d498  mov     r8d, 3
0x14000d49e  call    SvcChangeConfig
0x14000d4a3  mov     ebx, eax
0x14000d4a5  test    eax, eax
0x14000d4a7  jns     short loc_14000D4C2
0x14000d4a9  lea     r9, aFailedToChange_1; "Failed to change the Trusted Installer "...
0x14000d4b0  mov     r8d, 1
0x14000d4b6  mov     edx, eax
0x14000d4b8  mov     ecx, 4000000h
0x14000d4bd  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d4c2  mov     eax, ebx
0x14000d4c4  add     rsp, 60h
0x14000d4c8  pop     rbx
0x14000d4c9  retn
```
