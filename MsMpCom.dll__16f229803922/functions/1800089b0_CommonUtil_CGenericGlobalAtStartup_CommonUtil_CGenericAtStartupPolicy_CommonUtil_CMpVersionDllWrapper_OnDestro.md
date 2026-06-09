# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x1800089b0`
- end: `0x180008a24`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800089b0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180008a12`
- `KERNEL32!FreeLibrary` at `0x180008a12`

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
    off_180012058[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_180012068 = CommonUtil::VerQueryValueWNotInitialized;
    off_180012050[0] = CommonUtil::VerQueryValueWNotInitialized;
    off_180012060 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    off_180012048 = CommonUtil::GetFileVersionInfoExWDownlevel;
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
0x1800089b0  push    rbx
0x1800089b2  sub     rsp, 20h
0x1800089b6  cmp     byte ptr [rcx+20h], 0
0x1800089ba  mov     rbx, rcx
0x1800089bd  jz      short loc_180008A1E
0x1800089bf  mov     byte ptr [rcx+20h], 0
0x1800089c3  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800089ca  mov     cs:off_180012058, rax
0x1800089d1  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800089d8  mov     cs:off_180012068, rax
0x1800089df  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1800089e6  mov     cs:off_180012050, rax
0x1800089ed  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x1800089f4  mov     cs:off_180012060, rax
0x1800089fb  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x180008a02  mov     cs:off_180012048, rax
0x180008a09  mov     rcx, [rcx-8]; hLibModule
0x180008a0d  test    rcx, rcx
0x180008a10  jz      short loc_180008A18
0x180008a12  call    cs:__imp_FreeLibrary
0x180008a18  xor     eax, eax
0x180008a1a  mov     [rbx-8], rax
0x180008a1e  add     rsp, 20h
0x180008a22  pop     rbx
0x180008a23  retn
```
