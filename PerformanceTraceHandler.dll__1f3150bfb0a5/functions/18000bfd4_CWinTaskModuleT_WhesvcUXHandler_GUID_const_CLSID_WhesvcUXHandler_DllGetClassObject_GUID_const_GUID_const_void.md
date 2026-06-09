# CWinTaskModuleT<WhesvcUXHandler,&_GUID const CLSID_WhesvcUXHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000bfd4`
- end: `0x18000c080`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VWhesvcUXHandler@@$1?CLSID_WhesvcUXHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e980`

## callees

- `0x18000300c`
- `0x18000bfd4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<WhesvcUXHandler,&_GUID const CLSID_WhesvcUXHandler>::DllGetClassObject(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rax
  unsigned int v8; // edi
  _DWORD *v9; // [rsp+30h] [rbp+8h]

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v7 = *(_QWORD *)&CLSID_WhesvcUXHandler.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_WhesvcUXHandler.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_WhesvcUXHandler.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vftable';
    v9[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v8 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18000bfd4  mov     [rsp+arg_8], rbx
0x18000bfd9  mov     [rsp+arg_10], rsi
0x18000bfde  push    rdi
0x18000bfdf  sub     rsp, 20h
0x18000bfe3  mov     rdi, r9
0x18000bfe6  mov     rsi, r8
0x18000bfe9  test    r9, r9
0x18000bfec  jnz     short loc_18000BFF5
0x18000bfee  mov     eax, 80070057h
0x18000bff3  jmp     short loc_18000C070
0x18000bff5  mov     qword ptr [r9], 0
0x18000bffc  mov     rax, qword ptr cs:CLSID_WhesvcUXHandler.Data1
0x18000c003  sub     rax, [rdx]
0x18000c006  jnz     short loc_18000C013
0x18000c008  mov     rax, qword ptr cs:CLSID_WhesvcUXHandler.Data4
0x18000c00f  sub     rax, [rdx+8]
0x18000c013  test    rax, rax
0x18000c016  jz      short loc_18000C01F
0x18000c018  mov     edi, 80040111h
0x18000c01d  jmp     short loc_18000C06E
0x18000c01f  mov     ecx, 10h; Size
0x18000c024  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c029  mov     rbx, rax
0x18000c02c  mov     [rsp+28h+arg_0], rax
0x18000c031  lea     rax, ??_7?$CWinTaskClassFactoryT@VWhesvcUXHandler@@$00@@6B@; const CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vftable'
0x18000c038  mov     [rbx], rax
0x18000c03b  mov     dword ptr [rbx+8], 1
0x18000c042  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c049  mov     rax, [rbx]
0x18000c04c  mov     r8, rdi
0x18000c04f  mov     rdx, rsi
0x18000c052  mov     rcx, rbx
0x18000c055  mov     rax, [rax]
0x18000c058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c05d  mov     edi, eax
0x18000c05f  mov     rcx, [rbx]
0x18000c062  mov     rax, [rcx+10h]
0x18000c066  mov     rcx, rbx
0x18000c069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06e  mov     eax, edi
0x18000c070  mov     rbx, [rsp+28h+arg_8]
0x18000c075  mov     rsi, [rsp+28h+arg_10]
0x18000c07a  add     rsp, 20h
0x18000c07e  pop     rdi
0x18000c07f  retn
```
