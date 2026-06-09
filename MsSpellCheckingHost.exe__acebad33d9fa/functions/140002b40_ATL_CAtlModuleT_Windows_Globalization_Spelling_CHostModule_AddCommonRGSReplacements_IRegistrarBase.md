# ATL::CAtlModuleT<Windows::Globalization::Spelling::CHostModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140002b40`
- end: `0x140002b67`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<Windows::Globalization::Spelling::CHostModule>::AddCommonRGSReplacements(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{F1425A67-1545-44A2-AB59-8DF1020452D9}");
}

```

## disassembly

```asm
0x140002b40  sub     rsp, 28h
0x140002b44  mov     rcx, rdx
0x140002b47  mov     rax, [rdx]
0x140002b4a  lea     r8, aF1425a67154544; "{F1425A67-1545-44A2-AB59-8DF1020452D9}"
0x140002b51  lea     rdx, aAppid; "APPID"
0x140002b58  mov     rax, [rax+18h]
0x140002b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b61  nop
0x140002b62  add     rsp, 28h
0x140002b66  retn
```
