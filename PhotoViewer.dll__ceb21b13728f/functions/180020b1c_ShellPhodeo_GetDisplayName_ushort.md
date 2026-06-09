# ShellPhodeo::GetDisplayName(ushort * *)

- ea: `0x180020b1c`
- end: `0x180020bfe`
- name: `?GetDisplayName@ShellPhodeo@@IEAAJPEAPEAG@Z`
- size: `226`
- prototype: `__int64 __fastcall(ShellPhodeo *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020ac0`
- `0x180020af0`

## callees

- `0x18000cb74`
- `0x180020b1c`
- `0x180080010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180020b99`
- `OLEAUT32!__imp_SysAllocString` at `0x180020b99`
- `ole32!CoTaskMemFree` at `0x180020ba7`
- `ole32!CoTaskMemFree` at `0x180020bd6`
- `ole32!CoTaskMemFree` at `0x180020ba7`
- `ole32!CoTaskMemFree` at `0x180020bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ShellPhodeo::GetDisplayName(ShellPhodeo *this, unsigned __int16 **a2)
{
  int v3; // ebx
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v6; // [rsp+40h] [rbp+8h]
  OLECHAR *psz; // [rsp+50h] [rbp+18h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD **))(**((_QWORD **)this + 13) + 24LL))(
         *((_QWORD *)this + 13),
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v8);
  if ( v3 >= 0 )
  {
    try
    {
      psz = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD, OLECHAR **))(*v8 + 40LL))(v8, 0, &psz);
      *a2 = SysAllocString(psz);
      CoTaskMemFree(psz);
    }
    catch ( Base::Exception v5 )
    {
      v6 = Base::Exception::operator long(v5);
      Base::Exception::~Exception((Base::Exception *)v5);
      CoTaskMemFree(psz);
      psz = 0;
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v8);
      return v6;
    }
    psz = 0;
    if ( v8 )
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    return 0;
  }
  else
  {
    if ( v8 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v8 + 16LL))(v8, *v8);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x180020b1c  mov     [rsp+arg_8], rbx
0x180020b21  push    rdi
0x180020b22  sub     rsp, 30h
0x180020b26  mov     rdi, rdx
0x180020b29  mov     [rsp+38h+arg_18], 0
0x180020b32  mov     rcx, [rcx+68h]
0x180020b36  mov     rax, [rcx]
0x180020b39  lea     r8, [rsp+38h+arg_18]
0x180020b3e  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180020b45  mov     rax, [rax+18h]
0x180020b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b4e  mov     ebx, eax
0x180020b50  test    eax, eax
0x180020b52  jns     short loc_180020B72
0x180020b54  mov     rcx, [rsp+38h+arg_18]
0x180020b59  test    rcx, rcx
0x180020b5c  jz      short loc_180020B6B
0x180020b5e  mov     rdx, [rcx]
0x180020b61  mov     rax, [rdx+10h]
0x180020b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6a  nop
0x180020b6b  mov     eax, ebx
0x180020b6d  jmp     loc_180020BF3
0x180020b72  mov     [rsp+38h+psz], 0
0x180020b7b  mov     rcx, [rsp+38h+arg_18]
0x180020b80  mov     rax, [rcx]
0x180020b83  lea     r8, [rsp+38h+psz]
0x180020b88  xor     edx, edx
0x180020b8a  mov     rax, [rax+28h]
0x180020b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b93  nop
0x180020b94  mov     rcx, [rsp+38h+psz]; psz
0x180020b99  call    cs:__imp_SysAllocString
0x180020b9f  mov     [rdi], rax
0x180020ba2  mov     rcx, [rsp+38h+psz]; pv
0x180020ba7  call    cs:__imp_CoTaskMemFree
0x180020bad  mov     [rsp+38h+psz], 0
0x180020bb6  mov     rcx, [rsp+38h+arg_18]
0x180020bbb  test    rcx, rcx
0x180020bbe  jz      short loc_180020BCD
0x180020bc0  mov     rax, [rcx]
0x180020bc3  mov     rax, [rax+10h]
0x180020bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bcc  nop
0x180020bcd  xor     eax, eax
0x180020bcf  jmp     short loc_180020BF3
0x180020bd1  mov     rcx, [rsp+38h+psz]; pv
0x180020bd6  call    cs:__imp_CoTaskMemFree
0x180020bdc  mov     [rsp+38h+psz], 0
0x180020be5  lea     rcx, [rsp+38h+arg_18]
0x180020bea  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180020bef  mov     eax, [rsp+38h+arg_0]
0x180020bf3  mov     rbx, [rsp+38h+arg_8]
0x180020bf8  add     rsp, 30h
0x180020bfc  pop     rdi
0x180020bfd  retn
```
