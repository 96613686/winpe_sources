# CCbsTiPackage::GetUpdate(wchar_t const *,ICbsUpdate * *)

- ea: `0x140013974`
- end: `0x1400139c5`
- name: `?GetUpdate@CCbsTiPackage@@UEAAJPEB_WPEAPEAUICbsUpdate@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(CCbsTiPackage *__hidden this, const wchar_t *, struct ICbsUpdate **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140013960`

## callees

- `0x140013974`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x140013984`: `No update result specified`

## pseudocode

```c
__int64 __fastcall CCbsTiPackage::GetUpdate(CCbsTiPackage *this, const wchar_t *a2, struct ICbsUpdate **a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx

  if ( a3 )
  {
    v4 = *((_QWORD *)this - 2);
    if ( v4 )
      return (*(unsigned int (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 48LL))(v4, a2);
    else
      return (unsigned int)-2147467263;
  }
  else
  {
    v3 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "No update result specified");
  }
  return v3;
}

```

## disassembly

```asm
0x140013974  push    rbx
0x140013976  sub     rsp, 20h
0x14001397a  test    r8, r8
0x14001397d  jnz     short loc_14001399F
0x14001397f  mov     ebx, 80004003h
0x140013984  lea     r9, aNoUpdateResult; "No update result specified"
0x14001398b  mov     edx, ebx
0x14001398d  mov     r8d, 1
0x140013993  mov     ecx, 4000000h
0x140013998  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001399d  jmp     short loc_1400139BD
0x14001399f  mov     rcx, [rcx-10h]
0x1400139a3  test    rcx, rcx
0x1400139a6  jz      short loc_1400139B8
0x1400139a8  mov     rax, [rcx]
0x1400139ab  mov     rax, [rax+30h]
0x1400139af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139b4  mov     ebx, eax
0x1400139b6  jmp     short loc_1400139BD
0x1400139b8  mov     ebx, 80004001h
0x1400139bd  mov     eax, ebx
0x1400139bf  add     rsp, 20h
0x1400139c3  pop     rbx
0x1400139c4  retn
```
