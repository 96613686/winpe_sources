# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180076558`
- end: `0x1800765e5`
- name: `?GetPersistedRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180011ea0`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x18001d108`
- `0x1800764f8`
- `0x180076558`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800765a9`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800765a9`

## string_xrefs

- `0x1800765a0`: `RegUtils::GetPersistedRegistryLocation`

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
0x180076558  mov     [rsp+arg_0], rbx
0x18007655d  push    rdi
0x18007655e  sub     rsp, 240h
0x180076565  mov     rax, cs:__security_cookie
0x18007656c  xor     rax, rsp
0x18007656f  mov     [rsp+248h+var_18], rax
0x180076577  mov     rdi, rdx
0x18007657a  lea     rcx, [rsp+248h+var_228]; void *
0x18007657f  xor     edx, edx; Val
0x180076581  mov     r8d, 208h; Size
0x180076587  call    memset_0
0x18007658c  lea     rdx, [rsp+248h+var_228]
0x180076591  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180076596  test    eax, eax
0x180076598  jns     short loc_1800765B3
0x18007659a  mov     r8d, 314h
0x1800765a0  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x1800765a7  mov     ecx, eax
0x1800765a9  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800765af  mov     ebx, eax
0x1800765b1  jmp     short loc_1800765C2
0x1800765b3  xor     ebx, ebx
0x1800765b5  lea     rdx, [rsp+248h+var_228]
0x1800765ba  mov     rcx, rdi
0x1800765bd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800765c2  mov     eax, ebx
0x1800765c4  mov     rcx, [rsp+248h+var_18]
0x1800765cc  xor     rcx, rsp; StackCookie
0x1800765cf  call    __security_check_cookie
0x1800765d4  mov     rbx, [rsp+248h+arg_0]
0x1800765dc  add     rsp, 240h
0x1800765e3  pop     rdi
0x1800765e4  retn
```
