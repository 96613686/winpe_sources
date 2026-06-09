# _MapPlatformConfig::GetUserRegionInternal_::_1_::catch$5

- ea: `0x18000f084`
- end: `0x18000f0bf`
- name: `_MapPlatformConfig::GetUserRegionInternal_::_1_::catch$5`
- size: `59`
- prototype: `__int64 __fastcall(wil *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d0d8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000f0a5`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000f0a5`

## string_xrefs

- `0x18000f09c`: `MapPlatformConfig::GetUserRegionInternal`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetUserRegionInternal_::_1_::catch_5(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 40) = ZTraceReportOriginationNoThis(v3, "MapPlatformConfig::GetUserRegionInternal", 194);
  return 0;
}

```

## disassembly

```asm
0x18000f084  mov     [rsp+arg_8], rdx
0x18000f089  push    rbp
0x18000f08a  sub     rsp, 20h
0x18000f08e  mov     rbp, rdx
0x18000f091  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000f096  mov     r8d, 0C2h
0x18000f09c  lea     rdx, aMapplatformcon; "MapPlatformConfig::GetUserRegionInterna"...
0x18000f0a3  mov     ecx, eax
0x18000f0a5  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000f0ab  mov     [rbp+28h], eax
0x18000f0ae  mov     rax, 0
0x18000f0b8  add     rsp, 20h
0x18000f0bc  pop     rbp
0x18000f0bd  retn
```
