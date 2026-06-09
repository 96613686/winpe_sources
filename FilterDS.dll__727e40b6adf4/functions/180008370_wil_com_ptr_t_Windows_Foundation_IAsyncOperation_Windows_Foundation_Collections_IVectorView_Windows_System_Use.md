# wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,wil::err_exception_policy>(void)

- ea: `0x180008370`
- end: `0x18000838e`
- name: `??1?$com_ptr_t@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022132`
- `0x18002217e`
- `0x1800221a2`
- `0x1800221b4`
- `0x180022a3f`
- `0x180022ce0`
- `0x180022cf2`
- `0x180022d04`
- `0x180022d30`
- `0x180022d42`
- `0x180022ea2`
- `0x180022f71`
- `0x180022f83`

## callees

- `0x180008370`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,wil::err_exception_policy>(
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
0x180008370  sub     rsp, 28h
0x180008374  mov     rcx, [rcx]
0x180008377  test    rcx, rcx
0x18000837a  jz      short loc_180008389
0x18000837c  mov     rax, [rcx]
0x18000837f  mov     rax, [rax+10h]
0x180008383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008388  nop
0x180008389  add     rsp, 28h
0x18000838d  retn
```
