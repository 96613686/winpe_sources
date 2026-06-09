# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x18000474c`
- end: `0x180004766`
- name: `?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000476c`
- `0x1800070ec`
- `0x18000765c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
        __int64 a1,
        unsigned int *a2,
        __int64 a3)
{
  int v3; // ecx
  __int64 result; // rax

  v3 = *a2;
  *(GUID *)(a3 + 16LL * *a2) = GUID_00000038_0000_0000_c000_000000000046;
  result = (unsigned int)(v3 + 1);
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18000474c  mov     ecx, [rdx]
0x18000474e  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180004755  mov     eax, ecx
0x180004757  add     rax, rax
0x18000475a  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180004760  lea     eax, [rcx+1]
0x180004763  mov     [rdx], eax
0x180004765  retn
```
