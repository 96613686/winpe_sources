# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010c0`
- end: `0x180001115`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800010c0`
- `0x18000d420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800010da`
- `KERNEL32!GetLastError` at `0x1800010da`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800010d0`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800010d0`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  signed int LastError; // eax
  signed int v1; // ecx

  if ( InitializeCriticalSectionEx(&stru_180018220, 0, 0) )
    goto LABEL_6;
  LastError = GetLastError();
  v1 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v1 = LastError;
  if ( v1 >= 0 )
LABEL_6:
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010c0  sub     rsp, 28h
0x1800010c4  xor     r8d, r8d; Flags
0x1800010c7  lea     rcx, stru_180018220; lpCriticalSection
0x1800010ce  xor     edx, edx; dwSpinCount
0x1800010d0  call    cs:__imp_InitializeCriticalSectionEx
0x1800010d6  test    eax, eax
0x1800010d8  jnz     short loc_1800010FB
0x1800010da  call    cs:__imp_GetLastError
0x1800010e0  movzx   ecx, ax
0x1800010e3  or      ecx, 80070000h
0x1800010e9  test    eax, eax
0x1800010eb  cmovle  ecx, eax
0x1800010ee  test    ecx, ecx
0x1800010f0  jns     short loc_1800010FB
0x1800010f2  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800010f9  jmp     short loc_180001105
0x1800010fb  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001105  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000110c  add     rsp, 28h
0x180001110  jmp     atexit
```
