# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x140010220`
- end: `0x140010294`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140010220`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140010282`
- `KERNEL32!FreeLibrary` at `0x140010282`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(
        __int64 a1)
{
  HMODULE v2; // rcx
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
  {
    *(_BYTE *)(a1 + 32) = 0;
    off_14001B010 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B020 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B008 = CommonUtil::VerQueryValueWNotInitialized;
    off_14001B018 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    off_14001B000 = CommonUtil::GetFileVersionInfoExWDownlevel;
    v2 = *(HMODULE *)(a1 - 8);
    if ( v2 )
      FreeLibrary(v2);
    result = 0;
    *(_QWORD *)(a1 - 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140010220  push    rbx
0x140010222  sub     rsp, 20h
0x140010226  cmp     byte ptr [rcx+20h], 0
0x14001022a  mov     rbx, rcx
0x14001022d  jz      short loc_14001028E
0x14001022f  mov     byte ptr [rcx+20h], 0
0x140010233  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x14001023a  mov     cs:off_14001B010, rax
0x140010241  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x140010248  mov     cs:off_14001B020, rax
0x14001024f  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x140010256  mov     cs:off_14001B008, rax
0x14001025d  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x140010264  mov     cs:off_14001B018, rax
0x14001026b  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x140010272  mov     cs:off_14001B000, rax
0x140010279  mov     rcx, [rcx-8]; hLibModule
0x14001027d  test    rcx, rcx
0x140010280  jz      short loc_140010288
0x140010282  call    cs:__imp_FreeLibrary
0x140010288  xor     eax, eax
0x14001028a  mov     [rbx-8], rax
0x14001028e  add     rsp, 20h
0x140010292  pop     rbx
0x140010293  retn
```
