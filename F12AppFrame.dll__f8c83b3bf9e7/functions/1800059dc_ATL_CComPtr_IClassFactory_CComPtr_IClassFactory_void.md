# ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)

- ea: `0x1800059dc`
- end: `0x1800059fa`
- name: `??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032e33`
- `0x180032e87`
- `0x180032f8f`
- `0x180032fa8`
- `0x180032fd3`
- `0x180032fe5`
- `0x180032ff7`
- `0x180033063`
- `0x180033075`
- `0x1800330f3`
- `0x180033105`
- `0x18003314d`
- `0x18003315f`
- `0x180033171`
- `0x180033183`
- `0x180033195`
- `0x1800331a7`
- `0x1800331cb`
- `0x180033225`
- `0x180033358`
- `0x1800334c0`
- `0x1800338ac`
- `0x1800338c5`
- `0x180033929`
- `0x180033942`
- `0x18003403b`
- `0x1800340ef`
- `0x180034125`
- `0x1800341eb`
- `0x180034221`

## callees

- `0x1800059dc`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(__int64 *a1)
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
0x1800059dc  sub     rsp, 28h
0x1800059e0  mov     rcx, [rcx]
0x1800059e3  test    rcx, rcx
0x1800059e6  jz      short loc_1800059F5
0x1800059e8  mov     rax, [rcx]
0x1800059eb  mov     rax, [rax+10h]
0x1800059ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f4  nop
0x1800059f5  add     rsp, 28h
0x1800059f9  retn
```
