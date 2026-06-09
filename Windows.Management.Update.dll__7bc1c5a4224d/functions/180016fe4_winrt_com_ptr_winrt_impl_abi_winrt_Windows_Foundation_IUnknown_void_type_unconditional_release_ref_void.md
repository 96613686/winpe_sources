# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180016fe4`
- end: `0x180016ffd`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `67`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010918`
- `0x180010acc`
- `0x180010de4`
- `0x180010f4c`
- `0x1800110c0`
- `0x180011234`
- `0x180011644`
- `0x18001177c`
- `0x1800118d0`
- `0x180011940`
- `0x1800119f0`
- `0x180011a58`
- `0x180011b44`
- `0x180011cb0`
- `0x180011d80`
- `0x180011e40`
- `0x180011f30`
- `0x180012000`
- `0x180012fc0`
- `0x180014a80`
- `0x1800165c0`
- `0x1800167d0`
- `0x180016840`
- `0x1800168e0`
- `0x180016a80`
- `0x180016c20`
- `0x180016ec0`
- `0x180017e7c`
- `0x180018440`
- `0x18001bf00`
- `0x18001db50`
- `0x18001dd28`
- `0x18001e128`
- `0x18001e414`
- `0x18001e730`
- `0x18001e75c`
- `0x18001e808`
- `0x18001eb10`
- `0x18001eb80`
- `0x18001ed90`
- `0x18001eeb0`
- `0x18001f178`
- `0x18001f430`
- `0x18001f580`
- `0x18001f690`
- `0x18001f890`
- `0x18001f9b0`
- `0x18001faf4`
- `0x1800200cc`
- `0x180021e90`

## callees

- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180016fe4  mov     rdx, [rcx]
0x180016fe7  mov     qword ptr [rcx], 0
0x180016fee  mov     rcx, rdx
0x180016ff1  mov     rax, [rdx]
0x180016ff4  mov     rax, [rax+10h]
0x180016ff8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
