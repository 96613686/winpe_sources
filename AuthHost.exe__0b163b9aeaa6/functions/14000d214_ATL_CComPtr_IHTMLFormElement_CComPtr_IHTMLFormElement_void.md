# ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)

- ea: `0x14000d214`
- end: `0x14000d232`
- name: `??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d288`
- `0x14000d538`
- `0x14000d8d8`
- `0x14000dab4`
- `0x14000de20`
- `0x14000e190`
- `0x14000e2e0`
- `0x14000ea68`
- `0x1400127b0`
- `0x1400128d4`
- `0x14001348d`
- `0x1400134a3`
- `0x1400134b9`
- `0x140013525`
- `0x140013549`
- `0x14001355b`
- `0x14001356d`
- `0x1400135fd`
- `0x14001360f`
- `0x140013621`
- `0x140013633`
- `0x140013645`
- `0x140013657`
- `0x140013669`
- `0x14001367b`
- `0x14001369f`

## callees

- `0x14000d214`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x14000d214  sub     rsp, 28h
0x14000d218  mov     rcx, [rcx]
0x14000d21b  test    rcx, rcx
0x14000d21e  jz      short loc_14000D22D
0x14000d220  mov     rax, [rcx]
0x14000d223  mov     rax, [rax+10h]
0x14000d227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d22c  nop
0x14000d22d  add     rsp, 28h
0x14000d231  retn
```
