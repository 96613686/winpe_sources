# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180006770`
- end: `0x180006821`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006770`
- `0x180006828`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,>(&v12);
  if ( v7 >= 0 )
  {
    v9 = v12;
    v12[5] = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180006770  push    rbx
0x180006772  push    rbp
0x180006773  push    rsi
0x180006774  push    rdi
0x180006775  sub     rsp, 38h
0x180006779  mov     rdi, r9
0x18000677c  mov     rbp, r8
0x18000677f  mov     rsi, rcx
0x180006782  mov     [rsp+58h+var_38], 0
0x18000678b  lea     rcx, [rsp+58h+var_38]
0x180006790  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,>(Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0> * *)
0x180006795  mov     ebx, eax
0x180006797  test    eax, eax
0x180006799  jns     short loc_1800067B6
0x18000679b  mov     rcx, [rsp+58h+var_38]
0x1800067a0  test    rcx, rcx
0x1800067a3  jz      short loc_1800067B2
0x1800067a5  mov     rdx, [rcx]
0x1800067a8  mov     rax, [rdx+10h]
0x1800067ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b1  nop
0x1800067b2  mov     eax, ebx
0x1800067b4  jmp     short loc_180006818
0x1800067b6  mov     rbx, [rsp+58h+var_38]
0x1800067bb  mov     eax, [rsi]
0x1800067bd  mov     [rbx+14h], eax
0x1800067c0  mov     rax, [rbx]
0x1800067c3  mov     r8, rdi
0x1800067c6  mov     rdx, rbp
0x1800067c9  mov     rcx, rbx
0x1800067cc  mov     rax, [rax]
0x1800067cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d4  mov     edi, eax
0x1800067d6  test    byte ptr [rsi], 1
0x1800067d9  jz      short loc_180006801
0x1800067db  test    eax, eax
0x1800067dd  js      short loc_1800067FD
0x1800067df  test    byte ptr [rsi], 4
0x1800067e2  jz      short loc_1800067F9
0x1800067e4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800067eb  mov     rax, [rcx]
0x1800067ee  mov     rax, [rax+8]
0x1800067f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f7  jmp     short loc_180006801
0x1800067f9  xor     ebx, ebx
0x1800067fb  jmp     short loc_180006801
0x1800067fd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180006801  test    rbx, rbx
0x180006804  jz      short loc_180006816
0x180006806  mov     rax, [rbx]
0x180006809  mov     rcx, rbx
0x18000680c  mov     rax, [rax+10h]
0x180006810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006815  nop
0x180006816  mov     eax, edi
0x180006818  add     rsp, 38h
0x18000681c  pop     rdi
0x18000681d  pop     rsi
0x18000681e  pop     rbp
0x18000681f  pop     rbx
0x180006820  retn
```
