# RefreshCachedInstalledLanguages(void)

- ea: `0x180061dcc`
- end: `0x180061e36`
- name: `?RefreshCachedInstalledLanguages@@YAXXZ`
- size: `106`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001ff6c`
- `0x18003cf04`
- `0x18003f570`

## callees

- `0x180061dcc`
- `0x180061e3c`

## import_xrefs

- `ntdll!NtGetMUIRegistryInfo` at `0x180061dd8`
- `ntdll!NtGetMUIRegistryInfo` at `0x180061dd8`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180061e15`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180061e15`

## pseudocode

```c
void RefreshCachedInstalledLanguages(void)
{
  int MUIRegistryInfo; // eax
  unsigned int v1; // r8d
  int ThreadPreferredUILanguages; // eax
  unsigned int v3; // r8d
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v6; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+38h] [rbp+10h] BYREF

  MUIRegistryInfo = NtGetMUIRegistryInfo(10, 0, 0);
  if ( MUIRegistryInfo < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0xAA, v1, (const char *)(unsigned int)MUIRegistryInfo, v4);
  v6 = 0;
  v7 = 0;
  ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(48, &v7, 0, &v6);
  if ( ThreadPreferredUILanguages < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0xAF,
      v3,
      (const char *)(unsigned int)ThreadPreferredUILanguages,
      v4);
}

```

## disassembly

```asm
0x180061dcc  sub     rsp, 28h
0x180061dd0  xor     edx, edx
0x180061dd2  xor     r8d, r8d
0x180061dd5  lea     ecx, [rdx+0Ah]
0x180061dd8  call    cs:__imp_NtGetMUIRegistryInfo
0x180061dde  test    eax, eax
0x180061de0  jns     short loc_180061DF4
0x180061de2  mov     rcx, [rsp+28h]; this
0x180061de7  mov     r9d, eax; char *
0x180061dea  mov     edx, 0AAh; void *
0x180061def  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180061df4  xor     r8d, r8d
0x180061df7  mov     [rsp+28h+arg_0], 0
0x180061dff  lea     r9, [rsp+28h+arg_0]
0x180061e04  mov     [rsp+28h+arg_8], 0
0x180061e0c  lea     rdx, [rsp+28h+arg_8]
0x180061e11  lea     ecx, [r8+30h]
0x180061e15  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180061e1b  test    eax, eax
0x180061e1d  jns     short loc_180061E31
0x180061e1f  mov     rcx, [rsp+28h]; this
0x180061e24  mov     r9d, eax; char *
0x180061e27  mov     edx, 0AFh; void *
0x180061e2c  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180061e31  add     rsp, 28h
0x180061e35  retn
```
