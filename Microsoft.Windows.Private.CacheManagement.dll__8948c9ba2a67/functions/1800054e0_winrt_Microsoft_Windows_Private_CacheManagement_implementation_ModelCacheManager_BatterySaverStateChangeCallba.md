# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::BatterySaverStateChangeCallback(void *,ulong,void *)

- ea: `0x1800054e0`
- end: `0x180005546`
- name: `?BatterySaverStateChangeCallback@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SAKPEAXK0@Z`
- size: `102`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800054e0`
- `0x180012a40`

## string_xrefs

- `0x18000552e`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::BatterySaverStateChangeCallback(
        _BYTE *a1,
        __int64 a2,
        _DWORD *a3)
{
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_QWORD *)a3 == *(_QWORD *)&GUID_POWER_SAVING_STATUS.Data1
    && *((_QWORD *)a3 + 1) == *(_QWORD *)GUID_POWER_SAVING_STATUS.Data4 )
  {
    if ( a1 )
    {
      a1[280] = a3[5] != 0;
      return 0;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x89,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
      (const char *)0x8000FFFFLL,
      (int)"BatterySaverStateChangeCallback context is null.",
      v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800054e0  sub     rsp, 38h
0x1800054e4  mov     rax, [r8]
0x1800054e7  cmp     rax, qword ptr cs:GUID_POWER_SAVING_STATUS.Data1
0x1800054ee  jnz     short loc_18000553F
0x1800054f0  mov     rax, [r8+8]
0x1800054f4  cmp     rax, qword ptr cs:GUID_POWER_SAVING_STATUS.Data4
0x1800054fb  jnz     short loc_18000553F
0x1800054fd  test    rcx, rcx
0x180005500  jz      short loc_180005517
0x180005502  cmp     dword ptr [r8+14h], 0
0x180005507  setnbe  al
0x18000550a  mov     [rcx+118h], al
0x180005510  xor     eax, eax
0x180005512  add     rsp, 38h
0x180005516  retn
0x180005517  mov     rcx, [rsp+38h]; this
0x18000551c  lea     rax, aBatterysaverst; "BatterySaverStateChangeCallback context"...
0x180005523  mov     r9d, 8000FFFFh; char *
0x180005529  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000552e  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180005535  mov     edx, 89h; void *
0x18000553a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000553f  xor     eax, eax
0x180005541  add     rsp, 38h
0x180005545  retn
```
