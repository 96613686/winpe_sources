# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180025efc`
- end: `0x180025f89`
- name: `?GetPersistedRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c894`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x18000c3ac`
- `0x180025e9c`
- `0x180025efc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180025f4d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180025f4d`

## string_xrefs

- `0x180025f44`: `RegUtils::GetPersistedRegistryLocation`

## pseudocode

```c
__int64 __fastcall RegUtils::GetPersistedRegistryLocation(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int PersistedRegistryLocation; // eax
  unsigned int v5; // ebx
  _BYTE v7[528]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(v7, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v3, (__int64)v7);
  if ( PersistedRegistryLocation >= 0 )
  {
    v5 = 0;
    std::wstring::assign(a2, v7);
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(
                           PersistedRegistryLocation,
                           "RegUtils::GetPersistedRegistryLocation",
                           788);
  }
  return v5;
}

```

## disassembly

```asm
0x180025efc  mov     [rsp+arg_0], rbx
0x180025f01  push    rdi
0x180025f02  sub     rsp, 240h
0x180025f09  mov     rax, cs:__security_cookie
0x180025f10  xor     rax, rsp
0x180025f13  mov     [rsp+248h+var_18], rax
0x180025f1b  mov     rdi, rdx
0x180025f1e  lea     rcx, [rsp+248h+var_228]; void *
0x180025f23  xor     edx, edx; Val
0x180025f25  mov     r8d, 208h; Size
0x180025f2b  call    memset_0
0x180025f30  lea     rdx, [rsp+248h+var_228]
0x180025f35  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180025f3a  test    eax, eax
0x180025f3c  jns     short loc_180025F57
0x180025f3e  mov     r8d, 314h
0x180025f44  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x180025f4b  mov     ecx, eax
0x180025f4d  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180025f53  mov     ebx, eax
0x180025f55  jmp     short loc_180025F66
0x180025f57  xor     ebx, ebx
0x180025f59  lea     rdx, [rsp+248h+var_228]
0x180025f5e  mov     rcx, rdi
0x180025f61  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180025f66  mov     eax, ebx
0x180025f68  mov     rcx, [rsp+248h+var_18]
0x180025f70  xor     rcx, rsp; StackCookie
0x180025f73  call    __security_check_cookie
0x180025f78  mov     rbx, [rsp+248h+arg_0]
0x180025f80  add     rsp, 240h
0x180025f87  pop     rdi
0x180025f88  retn
```
