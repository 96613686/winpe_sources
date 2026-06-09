# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x18000b0a4`
- end: `0x18000b0c7`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d78`
- `0x180008e40`
- `0x180008eb4`
- `0x180008f28`
- `0x180008ffc`
- `0x18000c978`
- `0x18000ca40`

## callees

- `0x18000b0a4`
- `0x180018010`

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
0x18000b0a4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b0ab  test    rax, rax
0x18000b0ae  jz      short loc_18000B0BA
0x18000b0b0  mov     edx, 3
0x18000b0b5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b0c1  test    rax, rax
0x18000b0c4  jnz     short loc_18000B0B0
0x18000b0c6  retn
```
