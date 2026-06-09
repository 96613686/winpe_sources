# CWinTaskModuleT<ShowFeedbackToastHandler,&_GUID const CLSID_ShowFeedbackToastHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000bf20`
- end: `0x18000bfcc`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VShowFeedbackToastHandler@@$1?CLSID_ShowFeedbackToastHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e980`

## callees

- `0x18000300c`
- `0x18000bf20`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<ShowFeedbackToastHandler,&_GUID const CLSID_ShowFeedbackToastHandler>::DllGetClassObject(
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
  v7 = *(_QWORD *)&CLSID_ShowFeedbackToastHandler.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_ShowFeedbackToastHandler.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_ShowFeedbackToastHandler.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`vftable';
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
0x18000bf20  mov     [rsp+arg_8], rbx
0x18000bf25  mov     [rsp+arg_10], rsi
0x18000bf2a  push    rdi
0x18000bf2b  sub     rsp, 20h
0x18000bf2f  mov     rdi, r9
0x18000bf32  mov     rsi, r8
0x18000bf35  test    r9, r9
0x18000bf38  jnz     short loc_18000BF41
0x18000bf3a  mov     eax, 80070057h
0x18000bf3f  jmp     short loc_18000BFBC
0x18000bf41  mov     qword ptr [r9], 0
0x18000bf48  mov     rax, qword ptr cs:CLSID_ShowFeedbackToastHandler.Data1
0x18000bf4f  sub     rax, [rdx]
0x18000bf52  jnz     short loc_18000BF5F
0x18000bf54  mov     rax, qword ptr cs:CLSID_ShowFeedbackToastHandler.Data4
0x18000bf5b  sub     rax, [rdx+8]
0x18000bf5f  test    rax, rax
0x18000bf62  jz      short loc_18000BF6B
0x18000bf64  mov     edi, 80040111h
0x18000bf69  jmp     short loc_18000BFBA
0x18000bf6b  mov     ecx, 10h; Size
0x18000bf70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf75  mov     rbx, rax
0x18000bf78  mov     [rsp+28h+arg_0], rax
0x18000bf7d  lea     rax, ??_7?$CWinTaskClassFactoryT@VShowFeedbackToastHandler@@$00@@6B@; const CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`vftable'
0x18000bf84  mov     [rbx], rax
0x18000bf87  mov     dword ptr [rbx+8], 1
0x18000bf8e  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000bf95  mov     rax, [rbx]
0x18000bf98  mov     r8, rdi
0x18000bf9b  mov     rdx, rsi
0x18000bf9e  mov     rcx, rbx
0x18000bfa1  mov     rax, [rax]
0x18000bfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa9  mov     edi, eax
0x18000bfab  mov     rcx, [rbx]
0x18000bfae  mov     rax, [rcx+10h]
0x18000bfb2  mov     rcx, rbx
0x18000bfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfba  mov     eax, edi
0x18000bfbc  mov     rbx, [rsp+28h+arg_8]
0x18000bfc1  mov     rsi, [rsp+28h+arg_10]
0x18000bfc6  add     rsp, 20h
0x18000bfca  pop     rdi
0x18000bfcb  retn
```
