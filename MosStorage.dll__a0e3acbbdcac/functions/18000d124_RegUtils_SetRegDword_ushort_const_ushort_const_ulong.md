# RegUtils::SetRegDword(ushort const *,ushort const *,ulong)

- ea: `0x18000d124`
- end: `0x18000d180`
- name: `?SetRegDword@RegUtils@@SAJPEBG0K@Z`
- size: `92`
- prototype: `int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009ae0`

## callees

- `0x18000d124`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d171`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d171`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000d14e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000d14e`

## pseudocode

```c
int __fastcall RegUtils::SetRegDword(LPCWSTR lpSubKey, LPCWSTR lpValueName, int a3)
{
  int v3; // eax
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  v3 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName, 4u, &v5, 4u);
  if ( !v3 )
    return 0;
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  return ZTraceReportOriginationNoThis(v3, "RegUtils::SetRegDword", 286);
}

```

## disassembly

```asm
0x18000d124  mov     r11, rsp
0x18000d127  mov     [r11+18h], r8d
0x18000d12b  sub     rsp, 38h
0x18000d12f  mov     r9d, 4; dwType
0x18000d135  lea     rax, [r11+18h]
0x18000d139  mov     r8, rdx; lpValueName
0x18000d13c  mov     [r11-10h], r9d
0x18000d140  mov     rdx, rcx; lpSubKey
0x18000d143  mov     [r11-18h], rax
0x18000d147  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d14e  call    cs:__imp_RegSetKeyValueW
0x18000d154  test    eax, eax
0x18000d156  jz      short loc_18000D179
0x18000d158  jle     short loc_18000D162
0x18000d15a  movzx   eax, ax
0x18000d15d  or      eax, 80070000h
0x18000d162  mov     r8d, 11Eh
0x18000d168  lea     rdx, aRegutilsSetreg_0; "RegUtils::SetRegDword"
0x18000d16f  mov     ecx, eax
0x18000d171  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000d177  jmp     short loc_18000D17B
0x18000d179  xor     eax, eax
0x18000d17b  add     rsp, 38h
0x18000d17f  retn
```
