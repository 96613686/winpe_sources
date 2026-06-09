# ContactsStaticFilter::GetStoreCollection(IPOutlookStoreCollection * *)

- ea: `0x18001e110`
- end: `0x18001e206`
- name: `?GetStoreCollection@ContactsStaticFilter@@MEAAJPEAPEAUIPOutlookStoreCollection@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(ContactsStaticFilter *__hidden this, struct IPOutlookStoreCollection **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x18001e110`
- `0x180022010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18001e139`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18001e139`

## string_xrefs

- `0x18001e16d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e1aa`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`

## pseudocode

```c
__int64 __fastcall ContactsStaticFilter::GetStoreCollection(
        ContactsStaticFilter *this,
        struct IPOutlookStoreCollection **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  int v6; // eax
  __int64 v8[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IPOutlookStoreCollection *v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 v10; // [rsp+68h] [rbp+28h] BYREF

  v8[0] = 0;
  v10 = 0;
  v3 = POutlookAppManager_CreateInstance(&v10);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 263;
LABEL_5:
    Log_HREvent(
      (unsigned int)v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      v5);
    goto LABEL_9;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 32LL))(v10, v8);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 264;
    goto LABEL_5;
  }
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, struct IPOutlookStoreCollection **))(*(_QWORD *)v8[0] + 88LL))(v8[0], &v9);
  v4 = v6;
  if ( v6 >= 0 )
  {
    *a2 = v9;
    v9 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
    v4 = 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      267);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  }
LABEL_9:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v8);
  return v4;
}

```

## disassembly

```asm
0x18001e110  mov     [rsp-8+arg_0], rbx
0x18001e115  mov     [rsp-8+arg_8], rdi
0x18001e11a  push    rbp
0x18001e11b  mov     rbp, rsp
0x18001e11e  sub     rsp, 40h
0x18001e122  lea     rcx, [rbp+arg_18]
0x18001e126  mov     [rbp+var_10], 0
0x18001e12e  mov     rdi, rdx
0x18001e131  mov     [rbp+arg_18], 0
0x18001e139  call    cs:__imp_POutlookAppManager_CreateInstance
0x18001e13f  mov     ebx, eax
0x18001e141  test    eax, eax
0x18001e143  jns     short loc_18001E14D
0x18001e145  mov     r9d, 107h
0x18001e14b  jmp     short loc_18001E16D
0x18001e14d  mov     rcx, [rbp+arg_18]
0x18001e151  lea     rdx, [rbp+var_10]
0x18001e155  mov     rax, [rcx]
0x18001e158  mov     rax, [rax+20h]
0x18001e15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e161  mov     ebx, eax
0x18001e163  test    eax, eax
0x18001e165  jns     short loc_18001E182
0x18001e167  mov     r9d, 108h
0x18001e16d  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e174  mov     edx, 1
0x18001e179  mov     ecx, eax
0x18001e17b  call    Log_HREvent
0x18001e180  jmp     short loc_18001E1E2
0x18001e182  mov     rcx, [rbp+var_10]
0x18001e186  lea     rdx, [rbp+arg_10]
0x18001e18a  mov     [rbp+arg_10], 0
0x18001e192  mov     rax, [rcx]
0x18001e195  mov     rax, [rax+58h]
0x18001e199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e19e  mov     ebx, eax
0x18001e1a0  test    eax, eax
0x18001e1a2  jns     short loc_18001E1C8
0x18001e1a4  mov     r9d, 10Bh
0x18001e1aa  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e1b1  mov     edx, 1
0x18001e1b6  mov     ecx, eax
0x18001e1b8  call    Log_HREvent
0x18001e1bd  lea     rcx, [rbp+arg_10]
0x18001e1c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e1c6  jmp     short loc_18001E1E2
0x18001e1c8  mov     rax, [rbp+arg_10]
0x18001e1cc  lea     rcx, [rbp+arg_10]
0x18001e1d0  mov     [rdi], rax
0x18001e1d3  mov     [rbp+arg_10], 0
0x18001e1db  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e1e0  xor     ebx, ebx
0x18001e1e2  lea     rcx, [rbp+arg_18]
0x18001e1e6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e1eb  lea     rcx, [rbp+var_10]
0x18001e1ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e1f4  mov     rdi, [rsp+40h+arg_8]
0x18001e1f9  mov     eax, ebx
0x18001e1fb  mov     rbx, [rsp+40h+arg_0]
0x18001e200  add     rsp, 40h
0x18001e204  pop     rbp
0x18001e205  retn
```
