# _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)

- ea: `0x180005160`
- end: `0x180005187`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `194`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800035c4`
- `0x180003d9c`
- `0x180003e28`
- `0x180003f0c`
- `0x180003fe8`
- `0x180004220`
- `0x1800051bc`
- `0x180005380`
- `0x180005b50`
- `0x180007a20`
- `0x18000e520`
- `0x180010b80`
- `0x180015c90`
- `0x180015ed8`
- `0x180016474`
- `0x180016540`
- `0x18001681c`
- `0x180019e90`
- `0x18002c684`
- `0x18002cb78`
- `0x18002d468`
- `0x18002d6c0`
- `0x18002e1b0`
- `0x1800336b8`
- `0x180036734`
- `0x180036940`
- `0x1800375a0`
- `0x18003a6c4`
- `0x18003b120`
- `0x18003b8d0`
- `0x18003c460`
- `0x18003d1f4`
- `0x18004d354`
- `0x18004d4b4`
- `0x18004d594`
- `0x18004d624`
- `0x18004d6d0`
- `0x18004d77c`
- `0x18004dfac`
- `0x18004e214`
- `0x18004e450`
- `0x18004ea14`
- `0x18004ee74`
- `0x18004efa0`
- `0x18004f040`
- `0x18004f0e0`
- `0x18004f180`
- `0x18004f220`
- `0x18004f2c0`
- `0x18004f360`

## callees

- `0x180005160`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(
        __int64 *a1)
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
0x180005160  sub     rsp, 38h
0x180005164  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000516d  mov     rcx, [rcx]
0x180005170  test    rcx, rcx
0x180005173  jz      short loc_180005182
0x180005175  mov     rax, [rcx]
0x180005178  mov     rax, [rax+10h]
0x18000517c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005181  nop
0x180005182  add     rsp, 38h
0x180005186  retn
```
