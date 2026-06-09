# CNetworkItemFactory::GetNetworkItem(ushort const *,INetworkItem * *)

- ea: `0x180003470`
- end: `0x1800035c0`
- name: `?GetNetworkItem@CNetworkItemFactory@@UEAAJPEBGPEAPEAUINetworkItem@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, const unsigned __int16 *, struct INetworkItem **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180003470`
- `0x18000488c`
- `0x180004ca0`
- `0x1800070f4`
- `0x180008354`
- `0x18000b010`

## import_xrefs

- `ole32!CoGetInterfaceAndReleaseStream` at `0x180003566`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x180003566`
- `ole32!CoTaskMemFree` at `0x1800034fd`
- `ole32!CoTaskMemFree` at `0x1800034fd`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000353e`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000353e`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::GetNetworkItem(
        CNetworkItemFactory *this,
        const unsigned __int16 *a2,
        struct INetworkItem **a3)
{
  HRESULT InterfaceAndReleaseStream; // ebx
  LPVOID v7; // rdi
  struct INetworkItem *v8; // rcx
  const unsigned __int16 *pData; // [rsp+20h] [rbp-20h] BYREF
  int v11; // [rsp+28h] [rbp-18h]
  int v12; // [rsp+2Ch] [rbp-14h]
  LPSTREAM pStm; // [rsp+30h] [rbp-10h]
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  InterfaceAndReleaseStream = CNetworkItemFactory::_InitializeHashtable(this);
  if ( InterfaceAndReleaseStream >= 0 )
  {
    ppv = 0;
    if ( (unsigned int)LKRhash::CLKRHashTable::FindKey(*((_QWORD *)this + 10), a2, &ppv) )
    {
      pData = a2;
      InterfaceAndReleaseStream = -2147467259;
      v11 = -2147467259;
      v12 = 0;
      pStm = 0;
      if ( SHCreateThread(CFDListener::OnError, &pData, 0x1200u, GetFunctionInstanceThreadProc) )
      {
        InterfaceAndReleaseStream = v11;
        if ( v11 >= 0 )
        {
          ppv = 0;
          InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                        pStm,
                                        &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
                                        &ppv);
          if ( InterfaceAndReleaseStream >= 0 )
          {
            InterfaceAndReleaseStream = CNetworkItemFactory::_HandleDeviceAdd(this, (struct IFunctionInstance *)ppv);
            if ( InterfaceAndReleaseStream >= 0 )
              InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(CNetworkItemFactory *, const unsigned __int16 *, struct INetworkItem **))(*(_QWORD *)this + 72LL))(
                                            this,
                                            a2,
                                            a3);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
      }
    }
    else
    {
      v7 = ppv;
      InterfaceAndReleaseStream = 0;
      v8 = (struct INetworkItem *)*((_QWORD *)ppv + 1);
      *a3 = v8;
      (*(void (__fastcall **)(struct INetworkItem *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 1) + 16LL))(*((_QWORD *)v7 + 1));
        CoTaskMemFree(*(LPVOID *)v7);
        operator delete(v7);
      }
    }
  }
  return (unsigned int)InterfaceAndReleaseStream;
}

```

## disassembly

```asm
0x180003470  mov     [rsp-18h+arg_0], rbx
0x180003475  mov     [rsp-18h+arg_8], rsi
0x18000347a  push    rbp
0x18000347b  push    rdi
0x18000347c  push    r14
0x18000347e  mov     rbp, rsp
0x180003481  sub     rsp, 40h
0x180003485  mov     r14, r8
0x180003488  mov     rsi, rdx
0x18000348b  mov     rdi, rcx
0x18000348e  mov     qword ptr [r8], 0
0x180003495  call    ?_InitializeHashtable@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_InitializeHashtable(void)
0x18000349a  mov     ebx, eax
0x18000349c  test    eax, eax
0x18000349e  js      loc_1800035AB
0x1800034a4  mov     [rbp+ppv], 0
0x1800034ac  lea     r8, [rbp+ppv]
0x1800034b0  mov     rdx, rsi
0x1800034b3  mov     rcx, [rdi+50h]
0x1800034b7  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800034bc  test    eax, eax
0x1800034be  jnz     short loc_180003511
0x1800034c0  mov     rdi, [rbp+ppv]
0x1800034c4  xor     ebx, ebx
0x1800034c6  mov     rcx, [rdi+8]
0x1800034ca  mov     [r14], rcx
0x1800034cd  mov     rax, [rcx]
0x1800034d0  mov     rax, [rax+8]
0x1800034d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d9  or      eax, 0FFFFFFFFh
0x1800034dc  lock xadd [rdi+10h], eax
0x1800034e1  cmp     eax, 1
0x1800034e4  jnz     loc_1800035AB
0x1800034ea  mov     rcx, [rdi+8]
0x1800034ee  mov     rax, [rcx]
0x1800034f1  mov     rax, [rax+10h]
0x1800034f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034fa  mov     rcx, [rdi]; pv
0x1800034fd  call    cs:__imp_CoTaskMemFree
0x180003503  nop
0x180003504  mov     rcx, rdi; lpMem
0x180003507  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000350c  jmp     loc_1800035AB
0x180003511  mov     [rbp+pData], rsi
0x180003515  mov     ebx, 80004005h
0x18000351a  mov     [rbp+var_18], ebx
0x18000351d  xor     eax, eax
0x18000351f  mov     [rbp+var_14], eax
0x180003522  mov     [rbp+pStm], rax
0x180003526  lea     r9, ?GetFunctionInstanceThreadProc@@YAKPEAX@Z; pfnCallback
0x18000352d  mov     r8d, 1200h; flags
0x180003533  lea     rdx, [rbp+pData]; pData
0x180003537  lea     rcx, ?OnError@CFDListener@@UEAAJJ_KPEBG@Z; pfnThreadProc
0x18000353e  call    cs:__imp_SHCreateThread
0x180003544  test    eax, eax
0x180003546  jz      short loc_1800035AB
0x180003548  mov     ebx, [rbp+var_18]
0x18000354b  test    ebx, ebx
0x18000354d  js      short loc_1800035AB
0x18000354f  mov     [rbp+ppv], 0
0x180003557  lea     r8, [rbp+ppv]; ppv
0x18000355b  lea     rdx, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9; iid
0x180003562  mov     rcx, [rbp+pStm]; pStm
0x180003566  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18000356c  mov     ebx, eax
0x18000356e  test    eax, eax
0x180003570  js      short loc_1800035AB
0x180003572  mov     rdx, [rbp+ppv]; struct IFunctionInstance *
0x180003576  mov     rcx, rdi; this
0x180003579  call    ?_HandleDeviceAdd@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@@Z; CNetworkItemFactory::_HandleDeviceAdd(IFunctionInstance *)
0x18000357e  mov     ebx, eax
0x180003580  test    eax, eax
0x180003582  js      short loc_18000359B
0x180003584  mov     rax, [rdi]
0x180003587  mov     r8, r14
0x18000358a  mov     rdx, rsi
0x18000358d  mov     rcx, rdi
0x180003590  mov     rax, [rax+48h]
0x180003594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003599  mov     ebx, eax
0x18000359b  mov     rcx, [rbp+ppv]
0x18000359f  mov     rax, [rcx]
0x1800035a2  mov     rax, [rax+10h]
0x1800035a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ab  mov     eax, ebx
0x1800035ad  mov     rbx, [rsp+40h+arg_0]
0x1800035b2  mov     rsi, [rsp+40h+arg_8]
0x1800035b7  add     rsp, 40h
0x1800035bb  pop     r14
0x1800035bd  pop     rdi
0x1800035be  pop     rbp
0x1800035bf  retn
```
