# RetailDemoUserAgent::ConfigureDisplayTopology(ulong,ulong *)

- ea: `0x180039e60`
- end: `0x180039f8d`
- name: `?ConfigureDisplayTopology@RetailDemoUserAgent@@UEAAJKPEAK@Z`
- size: `301`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x18000563c`
- `0x180039e60`
- `0x180040694`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180039f2c`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180039f2c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180039e9e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180039e9e`
- `USER32!SetDisplayConfig` at `0x180039f5a`
- `USER32!SetDisplayConfig` at `0x180039f5a`

## string_xrefs

- `0x180039eb1`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
int __fastcall RetailDemoUserAgent::ConfigureDisplayTopology(
        RetailDemoUserAgent *this,
        int a2,
        DISPLAYCONFIG_TOPOLOGY_ID *a3)
{
  unsigned int DisplayConfigBufferSizes; // eax
  __int64 v6; // rdx
  DISPLAYCONFIG_PATH_INFO *v8; // rbx
  DISPLAYCONFIG_MODE_INFO *v9; // rax
  unsigned int modeInfoArray; // [rsp+20h] [rbp-20h]
  DISPLAYCONFIG_TOPOLOGY_ID currentTopologyId[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  UINT32 numModeInfoArrayElements; // [rsp+70h] [rbp+30h] BYREF
  UINT32 numPathArrayElements; // [rsp+78h] [rbp+38h] BYREF

  if ( a3 )
  {
    numPathArrayElements = 0;
    numModeInfoArrayElements = 0;
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(4u, &numPathArrayElements, &numModeInfoArrayElements);
    if ( DisplayConfigBufferSizes )
    {
      v6 = 2170;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
               (const char *)DisplayConfigBufferSizes,
               modeInfoArray);
    }
    if ( numPathArrayElements && numModeInfoArrayElements )
    {
      v8 = (DISPLAYCONFIG_PATH_INFO *)operator new[](saturated_mul(numPathArrayElements, 0x48u));
      v9 = (DISPLAYCONFIG_MODE_INFO *)operator new[](saturated_mul(numModeInfoArrayElements, 0x40u));
      currentTopologyId[0] = 0;
      DisplayConfigBufferSizes = QueryDisplayConfig(
                                   4u,
                                   &numPathArrayElements,
                                   v8,
                                   &numModeInfoArrayElements,
                                   v9,
                                   currentTopologyId);
      if ( DisplayConfigBufferSizes )
      {
        v6 = 2177;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
                 (const char *)DisplayConfigBufferSizes,
                 modeInfoArray);
      }
      *a3 = currentTopologyId[0];
    }
  }
  DisplayConfigBufferSizes = SetDisplayConfig(0, 0, 0, 0, a2 | 0x8080);
  if ( (a2 != 2 || DisplayConfigBufferSizes != 31) && DisplayConfigBufferSizes )
  {
    v6 = 2185;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
             (const char *)DisplayConfigBufferSizes,
             modeInfoArray);
  }
  return 0;
}

```

## disassembly

```asm
0x180039e60  mov     [rsp-18h+arg_0], rbx
0x180039e65  mov     [rsp-18h+arg_8], rsi
0x180039e6a  push    rbp
0x180039e6b  push    rdi
0x180039e6c  push    r14
0x180039e6e  mov     rbp, rsp
0x180039e71  sub     rsp, 40h
0x180039e75  mov     rdi, r8
0x180039e78  mov     esi, edx
0x180039e7a  test    r8, r8
0x180039e7d  jz      loc_180039F45
0x180039e83  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x180039e87  mov     [rbp+numPathArrayElements], 0
0x180039e8e  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180039e92  mov     [rbp+numModeInfoArrayElements], 0
0x180039e99  mov     ecx, 4; flags
0x180039e9e  call    cs:__imp_GetDisplayConfigBufferSizes
0x180039ea4  test    eax, eax
0x180039ea6  jz      short loc_180039EC5
0x180039ea8  mov     edx, 87Ah; void *
0x180039ead  mov     rcx, [rbp+18h]; this
0x180039eb1  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180039eb8  mov     r9d, eax; char *
0x180039ebb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180039ec0  jmp     loc_180039F7A
0x180039ec5  mov     eax, [rbp+numPathArrayElements]
0x180039ec8  test    eax, eax
0x180039eca  jz      short loc_180039F45
0x180039ecc  cmp     [rbp+numModeInfoArrayElements], 0
0x180039ed0  jz      short loc_180039F45
0x180039ed2  mov     ecx, eax
0x180039ed4  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180039edb  mov     eax, 48h ; 'H'
0x180039ee0  mul     rcx
0x180039ee3  cmovb   rax, r14
0x180039ee7  mov     rcx, rax; unsigned __int64
0x180039eea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039eef  mov     ecx, [rbp+numModeInfoArrayElements]
0x180039ef2  mov     rbx, rax
0x180039ef5  lea     eax, [r14+41h]
0x180039ef9  mul     rcx
0x180039efc  cmovb   rax, r14
0x180039f00  mov     rcx, rax; unsigned __int64
0x180039f03  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039f08  lea     rdx, [rbp+var_10]
0x180039f0c  mov     [rbp+var_10], 0
0x180039f13  mov     [rsp+40h+currentTopologyId], rdx; currentTopologyId
0x180039f18  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x180039f1c  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180039f20  mov     [rsp+40h+modeInfoArray], rax; modeInfoArray
0x180039f25  mov     r8, rbx; pathArray
0x180039f28  lea     ecx, [r14+5]; flags
0x180039f2c  call    cs:__imp_QueryDisplayConfig
0x180039f32  test    eax, eax
0x180039f34  jz      short loc_180039F40
0x180039f36  mov     edx, 881h
0x180039f3b  jmp     loc_180039EAD
0x180039f40  mov     eax, [rbp+var_10]
0x180039f43  mov     [rdi], eax
0x180039f45  mov     eax, esi
0x180039f47  xor     r9d, r9d; modeInfoArray
0x180039f4a  or      eax, 8080h
0x180039f4f  xor     r8d, r8d; numModeInfoArrayElements
0x180039f52  xor     edx, edx; pathArray
0x180039f54  mov     dword ptr [rsp+40h+modeInfoArray], eax; flags
0x180039f58  xor     ecx, ecx; numPathArrayElements
0x180039f5a  call    cs:__imp_SetDisplayConfig
0x180039f60  cmp     esi, 2
0x180039f63  jnz     short loc_180039F6A
0x180039f65  cmp     eax, 1Fh
0x180039f68  jz      short loc_180039F78
0x180039f6a  test    eax, eax
0x180039f6c  jz      short loc_180039F78
0x180039f6e  mov     edx, 889h
0x180039f73  jmp     loc_180039EAD
0x180039f78  xor     eax, eax
0x180039f7a  mov     rbx, [rsp+40h+arg_0]
0x180039f7f  mov     rsi, [rsp+40h+arg_8]
0x180039f84  add     rsp, 40h
0x180039f88  pop     r14
0x180039f8a  pop     rdi
0x180039f8b  pop     rbp
0x180039f8c  retn
```
