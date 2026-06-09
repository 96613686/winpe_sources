# CCommandHandler::EnumSubCommands(IEnumExplorerCommand * *)

- ea: `0x18000a890`
- end: `0x18000a981`
- name: `?EnumSubCommands@CCommandHandler@@UEAAJPEAPEAUIEnumExplorerCommand@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, struct IEnumExplorerCommand **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000453c`
- `0x1800056c0`
- `0x180005b60`
- `0x18000a474`
- `0x18000a890`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CCommandHandler::EnumSubCommands(CCommandHandler *this, struct IEnumExplorerCommand **a2)
{
  int v3; // edi
  __int64 i; // rsi
  unsigned int v6; // [rsp+50h] [rbp+28h] BYREF
  __int64 v7; // [rsp+58h] [rbp+30h] BYREF
  struct CEnumSubCommands *v8; // [rsp+60h] [rbp+38h] BYREF
  struct IObjectArray *v9; // [rsp+68h] [rbp+40h] BYREF

  *a2 = 0;
  v7 = 0;
  v6 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 5) + 64LL))(
         *((_QWORD *)this + 5),
         &v7,
         &v6);
  if ( v3 >= 0 )
  {
    v9 = 0;
    v3 = CObjectArray::Create<IEnhancedStorageSilo>(v7, v6, &v9);
    v8 = 0;
    if ( v3 >= 0 )
    {
      v3 = CEnumSubCommands::Create(v9, &v8);
      if ( v3 >= 0 )
        v3 = (**(__int64 (__fastcall ***)(struct CEnumSubCommands *, GUID *, struct IEnumExplorerCommand **))v8)(
               v8,
               &GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8,
               a2);
    }
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 8 * i) + 16LL))(*(_QWORD *)(v7 + 8 * i));
      *(_QWORD *)(v7 + 8 * i) = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a890  push    rbp
0x18000a892  push    rbx
0x18000a893  push    rsi
0x18000a894  push    rdi
0x18000a895  mov     rbp, rsp
0x18000a898  sub     rsp, 28h
0x18000a89c  mov     rbx, rdx
0x18000a89f  mov     qword ptr [rdx], 0
0x18000a8a6  mov     [rbp+arg_8], 0
0x18000a8ae  mov     [rbp+arg_0], 0
0x18000a8b5  mov     rcx, [rcx+28h]
0x18000a8b9  mov     rax, [rcx]
0x18000a8bc  lea     r8, [rbp+arg_0]
0x18000a8c0  lea     rdx, [rbp+arg_8]
0x18000a8c4  mov     rax, [rax+40h]
0x18000a8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8cd  mov     edi, eax
0x18000a8cf  test    eax, eax
0x18000a8d1  js      loc_18000A96D
0x18000a8d7  mov     [rbp+arg_18], 0
0x18000a8df  lea     r8, [rbp+arg_18]
0x18000a8e3  mov     edx, [rbp+arg_0]
0x18000a8e6  mov     rcx, [rbp+arg_8]
0x18000a8ea  call    ??$Create@UIEnhancedStorageSilo@@@CObjectArray@@SAJPEAPEAUIEnhancedStorageSilo@@KPEAPEAUIObjectArray@@@Z; CObjectArray::Create<IEnhancedStorageSilo>(IEnhancedStorageSilo * *,ulong,IObjectArray * *)
0x18000a8ef  mov     edi, eax
0x18000a8f1  mov     [rbp+arg_10], 0
0x18000a8f9  test    eax, eax
0x18000a8fb  js      short loc_18000A92B
0x18000a8fd  lea     rdx, [rbp+arg_10]; struct CEnumSubCommands **
0x18000a901  mov     rcx, [rbp+arg_18]; struct IObjectArray *
0x18000a905  call    ?Create@CEnumSubCommands@@SAJPEAUIObjectArray@@PEAPEAV1@@Z; CEnumSubCommands::Create(IObjectArray *,CEnumSubCommands * *)
0x18000a90a  mov     edi, eax
0x18000a90c  test    eax, eax
0x18000a90e  js      short loc_18000A92B
0x18000a910  mov     rcx, [rbp+arg_10]
0x18000a914  mov     rax, [rcx]
0x18000a917  mov     r8, rbx
0x18000a91a  lea     rdx, _GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8
0x18000a921  mov     rax, [rax]
0x18000a924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a929  mov     edi, eax
0x18000a92b  xor     esi, esi
0x18000a92d  cmp     [rbp+arg_0], esi
0x18000a930  jbe     short loc_18000A959
0x18000a932  mov     rax, [rbp+arg_8]
0x18000a936  mov     rcx, [rax+rsi*8]
0x18000a93a  mov     rax, [rcx]
0x18000a93d  mov     rax, [rax+10h]
0x18000a941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a946  mov     rax, [rbp+arg_8]
0x18000a94a  mov     qword ptr [rax+rsi*8], 0
0x18000a952  inc     esi
0x18000a954  cmp     esi, [rbp+arg_0]
0x18000a957  jb      short loc_18000A932
0x18000a959  lea     rcx, [rbp+arg_10]
0x18000a95d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a962  nop
0x18000a963  lea     rcx, [rbp+arg_18]
0x18000a967  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a96c  nop
0x18000a96d  lea     rcx, [rbp+arg_8]
0x18000a971  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000a976  mov     eax, edi
0x18000a978  add     rsp, 28h
0x18000a97c  pop     rdi
0x18000a97d  pop     rsi
0x18000a97e  pop     rbx
0x18000a97f  pop     rbp
0x18000a980  retn
```
