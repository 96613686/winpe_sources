# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x18000a544`
- end: `0x18000a567`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c8c`
- `0x180005d00`
- `0x180005d74`
- `0x180005de8`
- `0x180005e5c`
- `0x180005ed0`
- `0x180005f98`
- `0x18000607c`
- `0x180006160`
- `0x180006244`
- `0x180006328`
- `0x1800063fc`

## callees

- `0x18000a544`
- `0x180011010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::WilApi_GetFeatureEnabledState(
        wil::details *this,
        __int64 a2,
        __int64 a3,
        int *a4))(wil::details *, __int64, __int64, int *)
{
  __int64 (__fastcall *result)(wil::details *, __int64, __int64, int *); // rax

  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
  if ( g_wil_details_apiGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18000a544  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a54b  test    rax, rax
0x18000a54e  jz      short loc_18000A55A
0x18000a550  mov     edx, 3
0x18000a555  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a55a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a561  test    rax, rax
0x18000a564  jnz     short loc_18000A550
0x18000a566  retn
```
