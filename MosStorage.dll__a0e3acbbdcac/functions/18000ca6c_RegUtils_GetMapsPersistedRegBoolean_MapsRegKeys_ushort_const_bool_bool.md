# RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)

- ea: `0x18000ca6c`
- end: `0x18000cb14`
- name: `?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z`
- size: `168`
- prototype: `int __fastcall(int, const WCHAR *, __int64, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000832c`
- `0x180008a20`
- `0x18000d6c4`

## callees

- `0x180001c80`
- `0x180002802`
- `0x18000ca6c`
- `0x18000cc50`
- `0x18000cd68`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000cac9`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000cac9`

## pseudocode

```c
int __fastcall RegUtils::GetMapsPersistedRegBoolean(int a1, const WCHAR *a2, __int64 a3, bool *a4)
{
  int PersistedRegistryLocation; // eax
  bool v8; // r8
  int v9; // r8d
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(a1, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v9 = 539;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegBoolean", v9);
  }
  PersistedRegistryLocation = RegUtils::GetRegBoolean(SubKey, a2, v8, a4);
  if ( PersistedRegistryLocation < 0 )
  {
    v9 = 545;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegBoolean", v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ca6c  mov     [rsp+arg_0], rbx
0x18000ca71  mov     [rsp+arg_10], rsi
0x18000ca76  push    rdi
0x18000ca77  sub     rsp, 240h
0x18000ca7e  mov     rax, cs:__security_cookie
0x18000ca85  xor     rax, rsp
0x18000ca88  mov     [rsp+248h+var_18], rax
0x18000ca90  mov     rdi, rdx
0x18000ca93  mov     ebx, ecx
0x18000ca95  xor     edx, edx; Val
0x18000ca97  lea     rcx, [rsp+248h+SubKey]; void *
0x18000ca9c  mov     r8d, 208h; Size
0x18000caa2  mov     rsi, r9
0x18000caa5  call    memset_0
0x18000caaa  lea     rdx, [rsp+248h+SubKey]
0x18000caaf  mov     ecx, ebx
0x18000cab1  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000cab6  test    eax, eax
0x18000cab8  jns     short loc_18000CAD1
0x18000caba  mov     r8d, 21Bh
0x18000cac0  lea     rdx, aRegutilsGetmap_1; "RegUtils::GetMapsPersistedRegBoolean"
0x18000cac7  mov     ecx, eax
0x18000cac9  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000cacf  jmp     short loc_18000CAEF
0x18000cad1  mov     r9, rsi; bool *
0x18000cad4  lea     rcx, [rsp+248h+SubKey]; lpSubKey
0x18000cad9  mov     rdx, rdi; lpValue
0x18000cadc  call    ?GetRegBoolean@RegUtils@@SAJPEBG0_NPEA_N@Z; RegUtils::GetRegBoolean(ushort const *,ushort const *,bool,bool *)
0x18000cae1  test    eax, eax
0x18000cae3  jns     short loc_18000CAED
0x18000cae5  mov     r8d, 221h
0x18000caeb  jmp     short loc_18000CAC0
0x18000caed  xor     eax, eax
0x18000caef  mov     rcx, [rsp+248h+var_18]
0x18000caf7  xor     rcx, rsp; StackCookie
0x18000cafa  call    __security_check_cookie
0x18000caff  lea     r11, [rsp+248h+var_8]
0x18000cb07  mov     rbx, [r11+10h]
0x18000cb0b  mov     rsi, [r11+20h]
0x18000cb0f  mov     rsp, r11
0x18000cb12  pop     rdi
0x18000cb13  retn
```
