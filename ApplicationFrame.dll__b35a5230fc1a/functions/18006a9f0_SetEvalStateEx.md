# SetEvalStateEx

- ea: `0x18006a9f0`
- end: `0x18006ab93`
- name: `SetEvalStateEx`
- size: `419`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063f7c`
- `0x180064458`
- `0x1800652b0`
- `0x180067650`
- `0x180067a54`
- `0x18006a090`
- `0x18006a4a0`

## callees

- `0x18006a9f0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006aa78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006aa78`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ab3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ab3b`

## pseudocode

```c
__int64 __fastcall SetEvalStateEx(__int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *), __int64 a2, int a3)
{
  __int64 (__fastcall **v3)(_QWORD, GUID *, __int64 *); // rax
  HRESULT v6; // ebx
  __int64 v8; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+50h] [rbp-10h]
  LPVOID ppv; // [rsp+80h] [rbp+20h] BYREF
  __int64 v13; // [rsp+98h] [rbp+38h] BYREF

  v3 = *a1;
  v13 = 0;
  v6 = (*v3)(a1, &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43, &v13);
  if ( v6 >= 0 )
  {
    ppv = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *, GUID *, LPVOID *))(*(_QWORD *)v13 + 32LL))(
           v13,
           qword_18007CAC0,
           &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
           &ppv) >= 0
      || (v6 = CoCreateInstance(
                 &GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8,
                 0,
                 1u,
                 &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                 &ppv),
          v6 >= 0) )
    {
      v9 = 0;
      v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
             &v9);
      if ( v6 >= 0 )
      {
        v8 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v9 + 24LL))(
               v9,
               OID_PropertyStore,
               &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
               &v8);
        if ( v6 >= 0 )
        {
          v11 = 0;
          *(_OWORD *)pvar = 0;
          LODWORD(pvar[1]) = a3;
          LOWORD(pvar[0]) = 3;
          v6 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v8 + 32LL))(v8, a2, pvar);
          if ( v6 >= 0 )
            v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, LPVOID))(*(_QWORD *)v13 + 24LL))(
                   v13,
                   qword_18007CAC0,
                   ppv);
          PropVariantClear(pvar);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006a9f0  mov     [rsp-18h+arg_8], rbx
0x18006a9f5  push    rbp
0x18006a9f6  push    rsi
0x18006a9f7  push    rdi
0x18006a9f8  mov     rbp, rsp
0x18006a9fb  sub     rsp, 60h
0x18006a9ff  mov     rax, [rcx]
0x18006aa02  mov     edi, r8d
0x18006aa05  mov     rsi, rdx
0x18006aa08  mov     [rbp+arg_18], 0
0x18006aa10  lea     r8, [rbp+arg_18]
0x18006aa14  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x18006aa1b  mov     rax, [rax]
0x18006aa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa23  mov     ebx, eax
0x18006aa25  test    eax, eax
0x18006aa27  js      loc_18006AB81
0x18006aa2d  mov     rcx, [rbp+arg_18]
0x18006aa31  lea     r9, [rbp+arg_0]
0x18006aa35  mov     [rbp+arg_0], 0
0x18006aa3d  lea     r8, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x18006aa44  lea     rdx, qword_18007CAC0
0x18006aa4b  mov     rax, [rcx]
0x18006aa4e  mov     rax, [rax+20h]
0x18006aa52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa57  test    eax, eax
0x18006aa59  jns     short loc_18006AA88
0x18006aa5b  xor     edx, edx; pUnkOuter
0x18006aa5d  lea     rax, [rbp+arg_0]
0x18006aa61  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a; riid
0x18006aa68  mov     [rsp+60h+ppv], rax; ppv
0x18006aa6d  lea     rcx, _GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8; rclsid
0x18006aa74  lea     r8d, [rdx+1]; dwClsContext
0x18006aa78  call    cs:__imp_CoCreateInstance
0x18006aa7e  mov     ebx, eax
0x18006aa80  test    eax, eax
0x18006aa82  js      loc_18006AB71
0x18006aa88  mov     rcx, [rbp+arg_0]
0x18006aa8c  lea     r8, [rbp+var_28]
0x18006aa90  mov     [rbp+var_28], 0
0x18006aa98  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x18006aa9f  mov     rax, [rcx]
0x18006aaa2  mov     rax, [rax]
0x18006aaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaaa  mov     ebx, eax
0x18006aaac  test    eax, eax
0x18006aaae  js      loc_18006AB61
0x18006aab4  mov     rcx, [rbp+var_28]
0x18006aab8  lea     r9, [rbp+var_30]
0x18006aabc  mov     [rbp+var_30], 0
0x18006aac4  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18006aacb  lea     rdx, OID_PropertyStore
0x18006aad2  mov     rax, [rcx]
0x18006aad5  mov     rax, [rax+18h]
0x18006aad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aade  mov     ebx, eax
0x18006aae0  test    eax, eax
0x18006aae2  js      short loc_18006AB51
0x18006aae4  mov     rcx, [rbp+var_30]
0x18006aae8  lea     r8, [rbp+pvar]
0x18006aaec  xor     eax, eax
0x18006aaee  xorps   xmm0, xmm0
0x18006aaf1  mov     [rbp+var_10], rax
0x18006aaf5  mov     rdx, rsi
0x18006aaf8  movups  xmmword ptr [rbp+pvar], xmm0
0x18006aafc  mov     eax, 3
0x18006ab01  mov     dword ptr [rbp+pvar+8], edi
0x18006ab04  mov     word ptr [rbp+pvar], ax
0x18006ab08  mov     rax, [rcx]
0x18006ab0b  mov     rax, [rax+20h]
0x18006ab0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab14  mov     ebx, eax
0x18006ab16  test    eax, eax
0x18006ab18  js      short loc_18006AB37
0x18006ab1a  mov     rcx, [rbp+arg_18]
0x18006ab1e  lea     rdx, qword_18007CAC0
0x18006ab25  mov     r8, [rbp+arg_0]
0x18006ab29  mov     rax, [rcx]
0x18006ab2c  mov     rax, [rax+18h]
0x18006ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab35  mov     ebx, eax
0x18006ab37  lea     rcx, [rbp+pvar]; pvar
0x18006ab3b  call    cs:__imp_PropVariantClear
0x18006ab41  mov     rcx, [rbp+var_30]
0x18006ab45  mov     rax, [rcx]
0x18006ab48  mov     rax, [rax+10h]
0x18006ab4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab51  mov     rcx, [rbp+var_28]
0x18006ab55  mov     rax, [rcx]
0x18006ab58  mov     rax, [rax+10h]
0x18006ab5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab61  mov     rcx, [rbp+arg_0]
0x18006ab65  mov     rax, [rcx]
0x18006ab68  mov     rax, [rax+10h]
0x18006ab6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab71  mov     rcx, [rbp+arg_18]
0x18006ab75  mov     rax, [rcx]
0x18006ab78  mov     rax, [rax+10h]
0x18006ab7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab81  mov     eax, ebx
0x18006ab83  mov     rbx, [rsp+60h+arg_8]
0x18006ab8b  add     rsp, 60h
0x18006ab8f  pop     rdi
0x18006ab90  pop     rsi
0x18006ab91  pop     rbp
0x18006ab92  retn
```
