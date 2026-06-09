# CCbsTiPackage::EnumerateUpdates(_CbsApplicability,_CbsSelectability,IEnumCbsUpdate * *)

- ea: `0x1400133a4`
- end: `0x1400133f5`
- name: `?EnumerateUpdates@CCbsTiPackage@@UEAAJW4_CbsApplicability@@W4_CbsSelectability@@PEAPEAUIEnumCbsUpdate@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140013390`

## callees

- `0x1400133a4`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x1400133b4`: `No update list result specified`

## pseudocode

```c
__int64 __fastcall CCbsTiPackage::EnumerateUpdates(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx

  if ( a4 )
  {
    v5 = *(_QWORD *)(a1 - 16);
    if ( v5 )
      return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 40LL))(v5);
    else
      return (unsigned int)-2147467263;
  }
  else
  {
    v4 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "No update list result specified");
  }
  return v4;
}

```

## disassembly

```asm
0x1400133a4  push    rbx
0x1400133a6  sub     rsp, 30h
0x1400133aa  test    r9, r9
0x1400133ad  jnz     short loc_1400133CF
0x1400133af  mov     ebx, 80004003h
0x1400133b4  lea     r9, aNoUpdateListRe; "No update list result specified"
0x1400133bb  mov     edx, ebx
0x1400133bd  mov     r8d, 1
0x1400133c3  mov     ecx, 4000000h
0x1400133c8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400133cd  jmp     short loc_1400133ED
0x1400133cf  mov     rcx, [rcx-10h]
0x1400133d3  test    rcx, rcx
0x1400133d6  jz      short loc_1400133E8
0x1400133d8  mov     rax, [rcx]
0x1400133db  mov     rax, [rax+28h]
0x1400133df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400133e4  mov     ebx, eax
0x1400133e6  jmp     short loc_1400133ED
0x1400133e8  mov     ebx, 80004001h
0x1400133ed  mov     eax, ebx
0x1400133ef  add     rsp, 30h
0x1400133f3  pop     rbx
0x1400133f4  retn
```
