# AiLicReadIntegerValue

- ea: `0x180008838`
- end: `0x18000888e`
- name: `AiLicReadIntegerValue`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003940`
- `0x180003c80`

## callees

- `0x180008838`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x18000886c`
- `ntdll!NtQueryLicenseValue` at `0x18000886c`

## pseudocode

```c
__int64 __fastcall AiLicReadIntegerValue(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v3; // [rsp+48h] [rbp+10h] BYREF
  int v4; // [rsp+4Ch] [rbp+14h]
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v4 = HIDWORD(a2);
  v3 = 0;
  v5 = 4;
  result = NtQueryLicenseValue(a1, &v3, &AiSvcpSrpEnabled, 4, &v5);
  if ( (int)result >= 0 && (v3 != 4 || v5 != 4) )
    return 3221225473LL;
  return result;
}

```

## disassembly

```asm
0x180008838  mov     rax, rsp
0x18000883b  mov     [rax+10h], rdx
0x18000883f  sub     rsp, 38h
0x180008843  mov     dword ptr [rax+10h], 0
0x18000884a  mov     r9d, 4
0x180008850  mov     dword ptr [rax+18h], 4
0x180008857  lea     rax, [rax+18h]
0x18000885b  lea     r8, ?AiSvcpSrpEnabled@@3KA; ulong AiSvcpSrpEnabled
0x180008862  mov     [rsp+38h+var_18], rax
0x180008867  lea     rdx, [rsp+38h+arg_8]
0x18000886c  call    cs:__imp_NtQueryLicenseValue
0x180008872  test    eax, eax
0x180008874  js      short loc_180008889
0x180008876  cmp     [rsp+38h+arg_8], 4
0x18000887b  jnz     short loc_180008884
0x18000887d  cmp     [rsp+38h+arg_10], 4
0x180008882  jz      short loc_180008889
0x180008884  mov     eax, 0C0000001h
0x180008889  add     rsp, 38h
0x18000888d  retn
```
