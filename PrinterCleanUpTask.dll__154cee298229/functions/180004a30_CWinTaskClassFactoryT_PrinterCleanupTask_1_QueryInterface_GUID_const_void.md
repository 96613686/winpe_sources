# CWinTaskClassFactoryT<PrinterCleanupTask,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004a30`
- end: `0x180004a9c`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180004a30`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PrinterCleanupTask,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *a2 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v4 = a2[1] - *(_QWORD *)IID_IClassFactory.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *a2 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = a2[1] - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x180004a30  sub     rsp, 28h
0x180004a34  test    r8, r8
0x180004a37  jnz     short loc_180004A40
0x180004a39  mov     eax, 80070057h
0x180004a3e  jmp     short loc_180004A97
0x180004a40  mov     rax, [rdx]
0x180004a43  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180004a4a  jnz     short loc_180004A57
0x180004a4c  mov     rax, [rdx+8]
0x180004a50  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180004a57  test    rax, rax
0x180004a5a  jz      short loc_180004A86
0x180004a5c  mov     rax, [rdx]
0x180004a5f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180004a66  jnz     short loc_180004A73
0x180004a68  mov     rax, [rdx+8]
0x180004a6c  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180004a73  test    rax, rax
0x180004a76  jz      short loc_180004A86
0x180004a78  mov     qword ptr [r8], 0
0x180004a7f  mov     eax, 80004002h
0x180004a84  jmp     short loc_180004A97
0x180004a86  mov     [r8], rcx
0x180004a89  mov     rax, [rcx]
0x180004a8c  mov     rax, [rax+8]
0x180004a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a95  xor     eax, eax
0x180004a97  add     rsp, 28h
0x180004a9b  retn
```
