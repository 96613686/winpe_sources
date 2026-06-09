# _com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>(NLG::EnumVARIANTByRef<long,CArrayAllocator_malloc> * const &)

- ea: `0x18004d354`
- end: `0x18004d3d3`
- name: `??$?0PEAV?$EnumVARIANTByRef@JVCArrayAllocator_malloc@@@NLG@@@?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBQEAV?$EnumVARIANTByRef@JVCArrayAllocator_malloc@@@NLG@@@Z`
- size: `127`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004efa0`
- `0x18004f040`
- `0x18004f0e0`
- `0x18004f180`
- `0x18004f220`
- `0x18004f2c0`
- `0x18004f360`
- `0x18004f500`
- `0x18004f5a0`
- `0x18004f640`
- `0x18004f8c0`
- `0x180055c30`
- `0x180059600`

## callees

- `0x180003894`
- `0x180005160`
- `0x18004d354`
- `0x1800b0010`

## pseudocode

```c
_QWORD *__fastcall _com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *))
{
  __int64 v2; // rsi
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v5; // edi
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  *a1 = 0;
  v4 = *a2;
  if ( *a2 )
  {
    v7 = 0;
    v5 = (**v4)(v4, &GUID_00020404_0000_0000_c000_000000000046, &v7);
    if ( v5 >= 0 )
      v2 = v7;
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(a1);
    *a1 = v2;
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147467262 )
      _com_issue_error(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18004d354  mov     r11, rsp
0x18004d357  mov     [r11+10h], rbx
0x18004d35b  mov     [r11+18h], rsi
0x18004d35f  push    rdi
0x18004d360  sub     rsp, 20h
0x18004d364  xor     esi, esi
0x18004d366  mov     rbx, rcx
0x18004d369  mov     [rcx], rsi
0x18004d36c  mov     rcx, [rdx]
0x18004d36f  test    rcx, rcx
0x18004d372  jz      short loc_18004D3C0
0x18004d374  mov     [r11+8], rsi
0x18004d378  lea     r8, [r11+8]
0x18004d37c  mov     rax, [rcx]
0x18004d37f  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x18004d386  mov     rax, [rax]
0x18004d389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d38e  mov     edi, eax
0x18004d390  test    eax, eax
0x18004d392  js      short loc_18004D399
0x18004d394  mov     rsi, [rsp+28h+arg_0]
0x18004d399  mov     rcx, rbx
0x18004d39c  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18004d3a1  mov     ecx, 80000000h
0x18004d3a6  mov     [rbx], rsi
0x18004d3a9  lea     eax, [rdi+rcx]
0x18004d3ac  test    ecx, eax
0x18004d3ae  jnz     short loc_18004D3C0
0x18004d3b0  cmp     edi, 80004002h
0x18004d3b6  jz      short loc_18004D3C0
0x18004d3b8  mov     ecx, edi; int
0x18004d3ba  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004d3c0  mov     rsi, [rsp+28h+arg_10]
0x18004d3c5  mov     rax, rbx
0x18004d3c8  mov     rbx, [rsp+28h+arg_8]
0x18004d3cd  add     rsp, 20h
0x18004d3d1  pop     rdi
0x18004d3d2  retn
```
