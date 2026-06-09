# RegUtils::SetMapsPersistedRegString(MapsRegKeys,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800211f4`
- end: `0x1800212d8`
- name: `?SetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `228`
- prototype: `int __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c418`
- `0x18000c598`
- `0x1800109f0`
- `0x180015b40`
- `0x18001bc60`
- `0x18001dee8`
- `0x18001e664`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180008110`
- `0x180020abc`
- `0x1800211f4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800212a3`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800212a3`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180021248`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180021248`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021280`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021280`

## pseudocode

```c
int __fastcall RegUtils::SetMapsPersistedRegString(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 v5; // rcx
  int PersistedRegistryLocation; // eax
  __int64 v7; // rdx
  int v8; // r8d
  const void *lpData; // rax
  int v11; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v5, SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v8 = 607;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegString", v8);
  }
  lpData = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v7);
  v11 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, a2, 1u, lpData, 2 * *(_DWORD *)(a3 + 16) + 2);
  if ( v11 )
  {
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    PersistedRegistryLocation = ZTraceReportOriginationNoThis(v11, "RegUtils::SetRegString", 93);
    if ( PersistedRegistryLocation < 0 )
    {
      v8 = 612;
      return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegString", v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800211f4  mov     [rsp+arg_0], rbx
0x1800211f9  push    rdi
0x1800211fa  sub     rsp, 250h
0x180021201  mov     rax, cs:__security_cookie
0x180021208  xor     rax, rsp
0x18002120b  mov     [rsp+258h+var_18], rax
0x180021213  mov     rbx, r8
0x180021216  lea     rcx, [rsp+258h+SubKey]; void *
0x18002121b  mov     rdi, rdx
0x18002121e  mov     r8d, 208h; Size
0x180021224  xor     edx, edx; Val
0x180021226  call    memset_0
0x18002122b  lea     rdx, [rsp+258h+SubKey]
0x180021230  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180021235  test    eax, eax
0x180021237  jns     short loc_180021250
0x180021239  mov     r8d, 25Fh
0x18002123f  lea     rdx, aRegutilsSetmap; "RegUtils::SetMapsPersistedRegString"
0x180021246  mov     ecx, eax
0x180021248  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18002124e  jmp     short loc_1800212B7
0x180021250  mov     rcx, rbx
0x180021253  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021258  mov     ecx, [rbx+10h]
0x18002125b  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180021260  mov     r9d, 1; dwType
0x180021266  mov     r8, rdi; lpValueName
0x180021269  lea     ecx, ds:2[rcx*2]
0x180021270  mov     [rsp+258h+cbData], ecx; cbData
0x180021274  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002127b  mov     [rsp+258h+lpData], rax; lpData
0x180021280  call    cs:__imp_RegSetKeyValueW
0x180021286  test    eax, eax
0x180021288  jz      short loc_1800212B5
0x18002128a  jle     short loc_180021294
0x18002128c  movzx   eax, ax
0x18002128f  or      eax, 80070000h
0x180021294  mov     r8d, 5Dh ; ']'
0x18002129a  lea     rdx, aRegutilsSetreg; "RegUtils::SetRegString"
0x1800212a1  mov     ecx, eax
0x1800212a3  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800212a9  test    eax, eax
0x1800212ab  jns     short loc_1800212B5
0x1800212ad  mov     r8d, 264h
0x1800212b3  jmp     short loc_18002123F
0x1800212b5  xor     eax, eax
0x1800212b7  mov     rcx, [rsp+258h+var_18]
0x1800212bf  xor     rcx, rsp; StackCookie
0x1800212c2  call    __security_check_cookie
0x1800212c7  mov     rbx, [rsp+258h+arg_0]
0x1800212cf  add     rsp, 250h
0x1800212d6  pop     rdi
0x1800212d7  retn
```
