# CCommandHandler::InitializeFromName(ushort const *)

- ea: `0x18000ac54`
- end: `0x18000adab`
- name: `?InitializeFromName@CCommandHandler@@AEAAJPEBG@Z`
- size: `343`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000adb4`

## callees

- `0x18000453c`
- `0x18000a3a8`
- `0x18000ac54`
- `0x18000c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000ac9c`
- `ole32!CoCreateInstance` at `0x18000ac9c`

## pseudocode

```c
__int64 __fastcall CCommandHandler::InitializeFromName(CCommandHandler *this, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v8; // [rsp+70h] [rbp+30h] BYREF
  int v9; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  v6 = 0;
  v4 = CoCreateInstance(
         &GUID_fe841493_835c_4fa3_b6cc_b4b2d4719848,
         0,
         1u,
         &GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7,
         &ppv);
  if ( v4 < 0 )
    goto LABEL_10;
  v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, char *))(*(_QWORD *)ppv + 32LL))(
         ppv,
         a2,
         (char *)this + 56);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids,
      v4,
      (__int64)a2);
  if ( v4 < 0
    || (v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 7))(
               *((_QWORD *)this + 7),
               &GUID_022150a1_113d_11df_bb61_001aa01bbc58,
               &v6),
        v4 < 0)
    || (v9 = 1, v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 104LL))(v6, &v9), v4 < 0)
    || v9 )
  {
LABEL_10:
    v8 = 0;
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7), &v8);
      if ( v4 >= 0 )
        *((_BYTE *)this + 64) = v8 == 1;
    }
  }
  else
  {
    v4 = -2147467259;
    v8 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ac54  mov     [rsp-18h+arg_0], rbx
0x18000ac59  mov     [rsp-18h+arg_8], rsi
0x18000ac5e  push    rbp
0x18000ac5f  push    rdi
0x18000ac60  push    r14
0x18000ac62  mov     rbp, rsp
0x18000ac65  sub     rsp, 40h
0x18000ac69  mov     rsi, rdx
0x18000ac6c  mov     rdi, rcx
0x18000ac6f  mov     [rbp+var_8], 0
0x18000ac77  mov     [rbp+var_10], 0
0x18000ac7f  lea     rax, [rbp+var_8]
0x18000ac83  mov     [rsp+40h+ppv], rax; ppv
0x18000ac88  lea     r9, _GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7; riid
0x18000ac8f  xor     edx, edx; pUnkOuter
0x18000ac91  lea     r8d, [rdx+1]; dwClsContext
0x18000ac95  lea     rcx, _GUID_fe841493_835c_4fa3_b6cc_b4b2d4719848; rclsid
0x18000ac9c  call    cs:__imp_CoCreateInstance
0x18000aca2  mov     ebx, eax
0x18000aca4  test    eax, eax
0x18000aca6  js      loc_18000AD54
0x18000acac  mov     rcx, [rbp+var_8]
0x18000acb0  mov     rax, [rcx]
0x18000acb3  lea     r8, [rdi+38h]
0x18000acb7  mov     rdx, rsi
0x18000acba  mov     rax, [rax+20h]
0x18000acbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc3  mov     ebx, eax
0x18000acc5  lea     rax, WPP_GLOBAL_Control
0x18000accc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acd3  cmp     rcx, rax
0x18000acd6  jz      short loc_18000ACFB
0x18000acd8  test    byte ptr [rcx+1Ch], 20h
0x18000acdc  jz      short loc_18000ACFB
0x18000acde  mov     edx, 0Ah
0x18000ace3  mov     [rsp+40h+ppv], rsi
0x18000ace8  mov     r9d, ebx
0x18000aceb  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x18000acf2  mov     rcx, [rcx+10h]
0x18000acf6  call    WPP_SF_DS
0x18000acfb  test    ebx, ebx
0x18000acfd  js      short loc_18000AD54
0x18000acff  mov     rcx, [rdi+38h]
0x18000ad03  mov     rax, [rcx]
0x18000ad06  lea     r8, [rbp+var_10]
0x18000ad0a  lea     rdx, _GUID_022150a1_113d_11df_bb61_001aa01bbc58
0x18000ad11  mov     rax, [rax]
0x18000ad14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad19  mov     ebx, eax
0x18000ad1b  test    eax, eax
0x18000ad1d  js      short loc_18000AD54
0x18000ad1f  mov     [rbp+arg_18], 1
0x18000ad26  mov     rcx, [rbp+var_10]
0x18000ad2a  mov     rax, [rcx]
0x18000ad2d  lea     rdx, [rbp+arg_18]
0x18000ad31  mov     rax, [rax+68h]
0x18000ad35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad3a  mov     ebx, eax
0x18000ad3c  test    eax, eax
0x18000ad3e  js      short loc_18000AD54
0x18000ad40  cmp     [rbp+arg_18], 0
0x18000ad44  jnz     short loc_18000AD54
0x18000ad46  mov     ebx, 80004005h
0x18000ad4b  mov     [rbp+arg_10], 0
0x18000ad52  jmp     short loc_18000AD83
0x18000ad54  mov     [rbp+arg_10], 0
0x18000ad5b  test    ebx, ebx
0x18000ad5d  js      short loc_18000AD83
0x18000ad5f  mov     rcx, [rdi+38h]
0x18000ad63  mov     rax, [rcx]
0x18000ad66  lea     rdx, [rbp+arg_10]
0x18000ad6a  mov     rax, [rax+28h]
0x18000ad6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad73  mov     ebx, eax
0x18000ad75  test    eax, eax
0x18000ad77  js      short loc_18000AD83
0x18000ad79  cmp     [rbp+arg_10], 1
0x18000ad7d  setz    al
0x18000ad80  mov     [rdi+40h], al
0x18000ad83  lea     rcx, [rbp+var_10]
0x18000ad87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad8c  nop
0x18000ad8d  lea     rcx, [rbp+var_8]
0x18000ad91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad96  mov     eax, ebx
0x18000ad98  mov     rbx, [rsp+40h+arg_0]
0x18000ad9d  mov     rsi, [rsp+40h+arg_8]
0x18000ada2  add     rsp, 40h
0x18000ada6  pop     r14
0x18000ada8  pop     rdi
0x18000ada9  pop     rbp
0x18000adaa  retn
```
