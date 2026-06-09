# RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000cb1c`
- end: `0x18000cbb1`
- name: `?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `149`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000733c`
- `0x180008550`
- `0x180008920`
- `0x180008ac0`
- `0x180009590`
- `0x180009650`

## callees

- `0x180001c80`
- `0x180002802`
- `0x18000cb1c`
- `0x18000cc50`
- `0x18000cea0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000cb6e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000cb6e`

## pseudocode

```c
int __fastcall RegUtils::GetMapsPersistedRegString(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int PersistedRegistryLocation; // eax
  __int64 v6; // r8
  int v7; // r8d
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(1, SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v7 = 587;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegString", v7);
  }
  PersistedRegistryLocation = RegUtils::GetRegString(SubKey, L"MapsPreferredDeviceGuid", v6, a4);
  if ( PersistedRegistryLocation < 0 )
  {
    v7 = 593;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegString", v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb1c  push    rbx
0x18000cb1e  sub     rsp, 240h
0x18000cb25  mov     rax, cs:__security_cookie
0x18000cb2c  xor     rax, rsp
0x18000cb2f  mov     [rsp+248h+var_18], rax
0x18000cb37  xor     edx, edx; Val
0x18000cb39  lea     rcx, [rsp+248h+SubKey]; void *
0x18000cb3e  mov     r8d, 208h; Size
0x18000cb44  mov     rbx, r9
0x18000cb47  call    memset_0
0x18000cb4c  lea     rdx, [rsp+248h+SubKey]
0x18000cb51  mov     ecx, 1
0x18000cb56  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000cb5b  test    eax, eax
0x18000cb5d  jns     short loc_18000CB76
0x18000cb5f  mov     r8d, 24Bh
0x18000cb65  lea     rdx, aRegutilsGetmap_2; "RegUtils::GetMapsPersistedRegString"
0x18000cb6c  mov     ecx, eax
0x18000cb6e  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000cb74  jmp     short loc_18000CB98
0x18000cb76  mov     r9, rbx
0x18000cb79  lea     rdx, ValueName; "MapsPreferredDeviceGuid"
0x18000cb80  lea     rcx, [rsp+248h+SubKey]; lpSubKey
0x18000cb85  call    ?GetRegString@RegUtils@@SAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetRegString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18000cb8a  test    eax, eax
0x18000cb8c  jns     short loc_18000CB96
0x18000cb8e  mov     r8d, 251h
0x18000cb94  jmp     short loc_18000CB65
0x18000cb96  xor     eax, eax
0x18000cb98  mov     rcx, [rsp+248h+var_18]
0x18000cba0  xor     rcx, rsp; StackCookie
0x18000cba3  call    __security_check_cookie
0x18000cba8  add     rsp, 240h
0x18000cbaf  pop     rbx
0x18000cbb0  retn
```
