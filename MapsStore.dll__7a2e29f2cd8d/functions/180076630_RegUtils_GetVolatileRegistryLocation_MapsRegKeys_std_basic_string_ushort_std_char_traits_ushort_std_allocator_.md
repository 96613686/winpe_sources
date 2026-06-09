# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180076630`
- end: `0x1800766bd`
- name: `?GetVolatileRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x1800765ec`
- `0x180076630`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180076681`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180076681`

## string_xrefs

- `0x180076678`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
__int64 __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  size_t *v4; // r8
  int VolatileRegistryLocation; // eax
  unsigned int v6; // ebx
  wchar_t v8[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(v8, 0, 0x208u);
  VolatileRegistryLocation = RegUtils::GetVolatileRegistryLocation(v3, v8, v4);
  if ( VolatileRegistryLocation >= 0 )
  {
    v6 = 0;
    std::wstring::assign(a2, v8);
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(
                           VolatileRegistryLocation,
                           "RegUtils::GetVolatileRegistryLocation",
                           948);
  }
  return v6;
}

```

## disassembly

```asm
0x180076630  mov     [rsp+arg_0], rbx
0x180076635  push    rdi
0x180076636  sub     rsp, 240h
0x18007663d  mov     rax, cs:__security_cookie
0x180076644  xor     rax, rsp
0x180076647  mov     [rsp+248h+var_18], rax
0x18007664f  mov     rdi, rdx
0x180076652  lea     rcx, [rsp+248h+var_228]; void *
0x180076657  xor     edx, edx; Val
0x180076659  mov     r8d, 208h; Size
0x18007665f  call    memset_0
0x180076664  lea     rdx, [rsp+248h+var_228]
0x180076669  call    ?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18007666e  test    eax, eax
0x180076670  jns     short loc_18007668B
0x180076672  mov     r8d, 3B4h
0x180076678  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x18007667f  mov     ecx, eax
0x180076681  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180076687  mov     ebx, eax
0x180076689  jmp     short loc_18007669A
0x18007668b  xor     ebx, ebx
0x18007668d  lea     rdx, [rsp+248h+var_228]
0x180076692  mov     rcx, rdi
0x180076695  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18007669a  mov     eax, ebx
0x18007669c  mov     rcx, [rsp+248h+var_18]
0x1800766a4  xor     rcx, rsp; StackCookie
0x1800766a7  call    __security_check_cookie
0x1800766ac  mov     rbx, [rsp+248h+arg_0]
0x1800766b4  add     rsp, 240h
0x1800766bb  pop     rdi
0x1800766bc  retn
```
