# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180004490`
- end: `0x1800044b7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18000D264);
}

```

## disassembly

```asm
0x180004490  sub     rsp, 28h
0x180004494  mov     rcx, rdx
0x180004497  mov     rax, [rdx]
0x18000449a  lea     r8, dword_18000D264
0x1800044a1  lea     rdx, aAppid; "APPID"
0x1800044a8  mov     rax, [rax+18h]
0x1800044ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b1  nop
0x1800044b2  add     rsp, 28h
0x1800044b6  retn
```
