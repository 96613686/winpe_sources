# PushButtonReset::WimArchive::SetScratchPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800549c4`
- end: `0x180054a5c`
- name: `?SetScratchPath@WimArchive@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800204b8`

## callees

- `0x180037344`
- `0x1800549c4`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800549f7`
- `KERNEL32!GetLastError` at `0x180054a3e`
- `KERNEL32!GetLastError` at `0x1800549f7`
- `KERNEL32!GetLastError` at `0x180054a3e`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800549ea`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800549ea`

## string_xrefs

- `0x180054a0b`: `Failed to set scratch directory to [%s]`
- `0x180054a30`: `PushButtonReset::WimArchive::SetScratchPath`

## pseudocode

```c
signed int __fastcall PushButtonReset::WimArchive::SetScratchPath(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rax
  __int64 v5; // rbx
  signed int LastError; // eax
  signed int result; // eax

  v2 = *a2;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 8) + 32LL))(a1 + 8);
  if ( (unsigned int)WIMSetTemporaryPath(v4, v2) )
    return 0;
  v5 = *a2;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LastError,
    "PushButtonReset::WimArchive::SetScratchPath",
    "base\\reset\\util\\src\\wim.cpp",
    302,
    L"Failed to set scratch directory to [%s]",
    v5);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800549c4  mov     [rsp+arg_0], rbx
0x1800549c9  push    rdi
0x1800549ca  sub     rsp, 40h
0x1800549ce  mov     rbx, [rdx]
0x1800549d1  add     rcx, 8
0x1800549d5  mov     rdi, rdx
0x1800549d8  mov     rax, [rcx]
0x1800549db  mov     rax, [rax+20h]
0x1800549df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549e4  mov     rdx, rbx
0x1800549e7  mov     rcx, rax
0x1800549ea  call    cs:__imp_WIMSetTemporaryPath
0x1800549f0  test    eax, eax
0x1800549f2  jnz     short loc_180054A4F
0x1800549f4  mov     rbx, [rdi]
0x1800549f7  call    cs:__imp_GetLastError
0x1800549fd  mov     edi, 80070000h
0x180054a02  test    eax, eax
0x180054a04  jle     short loc_180054A0B
0x180054a06  movzx   eax, ax
0x180054a09  or      eax, edi
0x180054a0b  lea     rcx, aFailedToSetScr; "Failed to set scratch directory to [%s]"
0x180054a12  mov     [rsp+48h+var_18], rbx
0x180054a17  mov     [rsp+48h+var_20], rcx
0x180054a1c  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180054a23  mov     ecx, 2
0x180054a28  mov     [rsp+48h+var_28], 12Eh
0x180054a30  lea     r8, aPushbuttonrese_131; "PushButtonReset::WimArchive::SetScratch"...
0x180054a37  mov     edx, eax
0x180054a39  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180054a3e  call    cs:__imp_GetLastError
0x180054a44  test    eax, eax
0x180054a46  jle     short loc_180054A51
0x180054a48  movzx   eax, ax
0x180054a4b  or      eax, edi
0x180054a4d  jmp     short loc_180054A51
0x180054a4f  xor     eax, eax
0x180054a51  mov     rbx, [rsp+48h+arg_0]
0x180054a56  add     rsp, 40h
0x180054a5a  pop     rdi
0x180054a5b  retn
```
