# ATL::CAtlModuleT<CMidi2SchedulerTransformModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180009080`
- end: `0x1800090a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2SchedulerTransformModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2SchedulerTransformModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}");
}

```

## disassembly

```asm
0x180009080  sub     rsp, 28h
0x180009084  mov     rcx, rdx
0x180009087  mov     rax, [rdx]
0x18000908a  lea     r8, a2ac669ca18ca4e; "{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}"
0x180009091  lea     rdx, aAppid; "APPID"
0x180009098  mov     rax, [rax+18h]
0x18000909c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a1  nop
0x1800090a2  add     rsp, 28h
0x1800090a6  retn
```
