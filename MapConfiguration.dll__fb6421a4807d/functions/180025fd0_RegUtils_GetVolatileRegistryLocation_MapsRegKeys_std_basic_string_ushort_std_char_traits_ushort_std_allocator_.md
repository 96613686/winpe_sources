# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180025fd0`
- end: `0x18002605d`
- name: `?GetVolatileRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180025f90`
- `0x180025fd0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180026021`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180026021`

## string_xrefs

- `0x180026018`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
__int64 __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int VolatileRegistryLocation; // eax
  unsigned int v5; // ebx
  unsigned __int16 v7[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(v7, 0, 0x208u);
  VolatileRegistryLocation = RegUtils::GetVolatileRegistryLocation(v3, v7);
  if ( VolatileRegistryLocation >= 0 )
  {
    v5 = 0;
    std::wstring::assign(a2, v7);
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(
                           VolatileRegistryLocation,
                           "RegUtils::GetVolatileRegistryLocation",
                           948);
  }
  return v5;
}

```

## disassembly

```asm
0x180025fd0  mov     [rsp+arg_0], rbx
0x180025fd5  push    rdi
0x180025fd6  sub     rsp, 240h
0x180025fdd  mov     rax, cs:__security_cookie
0x180025fe4  xor     rax, rsp
0x180025fe7  mov     [rsp+248h+var_18], rax
0x180025fef  mov     rdi, rdx
0x180025ff2  lea     rcx, [rsp+248h+var_228]; void *
0x180025ff7  xor     edx, edx; Val
0x180025ff9  mov     r8d, 208h; Size
0x180025fff  call    memset_0
0x180026004  lea     rdx, [rsp+248h+var_228]
0x180026009  call    ?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18002600e  test    eax, eax
0x180026010  jns     short loc_18002602B
0x180026012  mov     r8d, 3B4h
0x180026018  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x18002601f  mov     ecx, eax
0x180026021  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180026027  mov     ebx, eax
0x180026029  jmp     short loc_18002603A
0x18002602b  xor     ebx, ebx
0x18002602d  lea     rdx, [rsp+248h+var_228]
0x180026032  mov     rcx, rdi
0x180026035  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002603a  mov     eax, ebx
0x18002603c  mov     rcx, [rsp+248h+var_18]
0x180026044  xor     rcx, rsp; StackCookie
0x180026047  call    __security_check_cookie
0x18002604c  mov     rbx, [rsp+248h+arg_0]
0x180026054  add     rsp, 240h
0x18002605b  pop     rdi
0x18002605c  retn
```
