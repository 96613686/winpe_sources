# CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180004444`
- end: `0x1800044f0`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800092f0`

## callees

- `0x180001e24`
- `0x180004444`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllGetClassObject(
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
  v7 = *(_QWORD *)&CLSID_PlutonTasks.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_PlutonTasks.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_PlutonTasks.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`vftable';
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
0x180004444  mov     [rsp+arg_8], rbx
0x180004449  mov     [rsp+arg_10], rsi
0x18000444e  push    rdi
0x18000444f  sub     rsp, 20h
0x180004453  mov     rdi, r9
0x180004456  mov     rsi, r8
0x180004459  test    r9, r9
0x18000445c  jnz     short loc_180004465
0x18000445e  mov     eax, 80070057h
0x180004463  jmp     short loc_1800044E0
0x180004465  mov     qword ptr [r9], 0
0x18000446c  mov     rax, qword ptr cs:CLSID_PlutonTasks.Data1
0x180004473  sub     rax, [rdx]
0x180004476  jnz     short loc_180004483
0x180004478  mov     rax, qword ptr cs:CLSID_PlutonTasks.Data4
0x18000447f  sub     rax, [rdx+8]
0x180004483  test    rax, rax
0x180004486  jz      short loc_18000448F
0x180004488  mov     edi, 80040111h
0x18000448d  jmp     short loc_1800044DE
0x18000448f  mov     ecx, 10h; Size
0x180004494  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004499  mov     rbx, rax
0x18000449c  mov     [rsp+28h+arg_0], rax
0x1800044a1  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`vftable'
0x1800044a8  mov     [rbx], rax
0x1800044ab  mov     dword ptr [rbx+8], 1
0x1800044b2  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800044b9  mov     rax, [rbx]
0x1800044bc  mov     r8, rdi
0x1800044bf  mov     rdx, rsi
0x1800044c2  mov     rcx, rbx
0x1800044c5  mov     rax, [rax]
0x1800044c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cd  mov     edi, eax
0x1800044cf  mov     rcx, [rbx]
0x1800044d2  mov     rax, [rcx+10h]
0x1800044d6  mov     rcx, rbx
0x1800044d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044de  mov     eax, edi
0x1800044e0  mov     rbx, [rsp+28h+arg_8]
0x1800044e5  mov     rsi, [rsp+28h+arg_10]
0x1800044ea  add     rsp, 20h
0x1800044ee  pop     rdi
0x1800044ef  retn
```
