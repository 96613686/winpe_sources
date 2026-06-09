# CWinTaskModuleT<PerformanceTraceHandler,&_GUID const CLSID_PerformanceTraceHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000be6c`
- end: `0x18000bf18`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VPerformanceTraceHandler@@$1?CLSID_PerformanceTraceHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e980`

## callees

- `0x18000300c`
- `0x18000be6c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<PerformanceTraceHandler,&_GUID const CLSID_PerformanceTraceHandler>::DllGetClassObject(
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
  v7 = *(_QWORD *)&CLSID_PerformanceTraceHandler.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_PerformanceTraceHandler.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_PerformanceTraceHandler.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vftable';
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
0x18000be6c  mov     [rsp+arg_8], rbx
0x18000be71  mov     [rsp+arg_10], rsi
0x18000be76  push    rdi
0x18000be77  sub     rsp, 20h
0x18000be7b  mov     rdi, r9
0x18000be7e  mov     rsi, r8
0x18000be81  test    r9, r9
0x18000be84  jnz     short loc_18000BE8D
0x18000be86  mov     eax, 80070057h
0x18000be8b  jmp     short loc_18000BF08
0x18000be8d  mov     qword ptr [r9], 0
0x18000be94  mov     rax, qword ptr cs:CLSID_PerformanceTraceHandler.Data1
0x18000be9b  sub     rax, [rdx]
0x18000be9e  jnz     short loc_18000BEAB
0x18000bea0  mov     rax, qword ptr cs:CLSID_PerformanceTraceHandler.Data4
0x18000bea7  sub     rax, [rdx+8]
0x18000beab  test    rax, rax
0x18000beae  jz      short loc_18000BEB7
0x18000beb0  mov     edi, 80040111h
0x18000beb5  jmp     short loc_18000BF06
0x18000beb7  mov     ecx, 10h; Size
0x18000bebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bec1  mov     rbx, rax
0x18000bec4  mov     [rsp+28h+arg_0], rax
0x18000bec9  lea     rax, ??_7?$CWinTaskClassFactoryT@VPerformanceTraceHandler@@$00@@6B@; const CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vftable'
0x18000bed0  mov     [rbx], rax
0x18000bed3  mov     dword ptr [rbx+8], 1
0x18000beda  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000bee1  mov     rax, [rbx]
0x18000bee4  mov     r8, rdi
0x18000bee7  mov     rdx, rsi
0x18000beea  mov     rcx, rbx
0x18000beed  mov     rax, [rax]
0x18000bef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bef5  mov     edi, eax
0x18000bef7  mov     rcx, [rbx]
0x18000befa  mov     rax, [rcx+10h]
0x18000befe  mov     rcx, rbx
0x18000bf01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf06  mov     eax, edi
0x18000bf08  mov     rbx, [rsp+28h+arg_8]
0x18000bf0d  mov     rsi, [rsp+28h+arg_10]
0x18000bf12  add     rsp, 20h
0x18000bf16  pop     rdi
0x18000bf17  retn
```
