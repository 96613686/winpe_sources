# SetEvalStateEx

- ea: `0x180022104`
- end: `0x1800222a7`
- name: `SetEvalStateEx`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a290`
- `0x18002a824`
- `0x18002d3c0`
- `0x180032f20`
- `0x180033324`
- `0x180035090`
- `0x18003ac60`
- `0x18003b070`

## callees

- `0x180022104`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002224f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002224f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002218c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002218c`

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
           qword_18005AAE8,
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
                   qword_18005AAE8,
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
0x180022104  mov     [rsp-18h+arg_8], rbx
0x180022109  push    rbp
0x18002210a  push    rsi
0x18002210b  push    rdi
0x18002210c  mov     rbp, rsp
0x18002210f  sub     rsp, 60h
0x180022113  mov     rax, [rcx]
0x180022116  mov     edi, r8d
0x180022119  mov     rsi, rdx
0x18002211c  mov     [rbp+arg_18], 0
0x180022124  lea     r8, [rbp+arg_18]
0x180022128  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x18002212f  mov     rax, [rax]
0x180022132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022137  mov     ebx, eax
0x180022139  test    eax, eax
0x18002213b  js      loc_180022295
0x180022141  mov     rcx, [rbp+arg_18]
0x180022145  lea     r9, [rbp+arg_0]
0x180022149  mov     [rbp+arg_0], 0
0x180022151  lea     r8, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x180022158  lea     rdx, qword_18005AAE8
0x18002215f  mov     rax, [rcx]
0x180022162  mov     rax, [rax+20h]
0x180022166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002216b  test    eax, eax
0x18002216d  jns     short loc_18002219C
0x18002216f  xor     edx, edx; pUnkOuter
0x180022171  lea     rax, [rbp+arg_0]
0x180022175  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a; riid
0x18002217c  mov     [rsp+60h+ppv], rax; ppv
0x180022181  lea     rcx, _GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8; rclsid
0x180022188  lea     r8d, [rdx+1]; dwClsContext
0x18002218c  call    cs:__imp_CoCreateInstance
0x180022192  mov     ebx, eax
0x180022194  test    eax, eax
0x180022196  js      loc_180022285
0x18002219c  mov     rcx, [rbp+arg_0]
0x1800221a0  lea     r8, [rbp+var_28]
0x1800221a4  mov     [rbp+var_28], 0
0x1800221ac  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x1800221b3  mov     rax, [rcx]
0x1800221b6  mov     rax, [rax]
0x1800221b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221be  mov     ebx, eax
0x1800221c0  test    eax, eax
0x1800221c2  js      loc_180022275
0x1800221c8  mov     rcx, [rbp+var_28]
0x1800221cc  lea     r9, [rbp+var_30]
0x1800221d0  mov     [rbp+var_30], 0
0x1800221d8  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x1800221df  lea     rdx, OID_PropertyStore
0x1800221e6  mov     rax, [rcx]
0x1800221e9  mov     rax, [rax+18h]
0x1800221ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221f2  mov     ebx, eax
0x1800221f4  test    eax, eax
0x1800221f6  js      short loc_180022265
0x1800221f8  mov     rcx, [rbp+var_30]
0x1800221fc  lea     r8, [rbp+pvar]
0x180022200  xor     eax, eax
0x180022202  xorps   xmm0, xmm0
0x180022205  mov     [rbp+var_10], rax
0x180022209  mov     rdx, rsi
0x18002220c  movups  xmmword ptr [rbp+pvar], xmm0
0x180022210  mov     eax, 3
0x180022215  mov     dword ptr [rbp+pvar+8], edi
0x180022218  mov     word ptr [rbp+pvar], ax
0x18002221c  mov     rax, [rcx]
0x18002221f  mov     rax, [rax+20h]
0x180022223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022228  mov     ebx, eax
0x18002222a  test    eax, eax
0x18002222c  js      short loc_18002224B
0x18002222e  mov     rcx, [rbp+arg_18]
0x180022232  lea     rdx, qword_18005AAE8
0x180022239  mov     r8, [rbp+arg_0]
0x18002223d  mov     rax, [rcx]
0x180022240  mov     rax, [rax+18h]
0x180022244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022249  mov     ebx, eax
0x18002224b  lea     rcx, [rbp+pvar]; pvar
0x18002224f  call    cs:__imp_PropVariantClear
0x180022255  mov     rcx, [rbp+var_30]
0x180022259  mov     rax, [rcx]
0x18002225c  mov     rax, [rax+10h]
0x180022260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022265  mov     rcx, [rbp+var_28]
0x180022269  mov     rax, [rcx]
0x18002226c  mov     rax, [rax+10h]
0x180022270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022275  mov     rcx, [rbp+arg_0]
0x180022279  mov     rax, [rcx]
0x18002227c  mov     rax, [rax+10h]
0x180022280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022285  mov     rcx, [rbp+arg_18]
0x180022289  mov     rax, [rcx]
0x18002228c  mov     rax, [rax+10h]
0x180022290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022295  mov     eax, ebx
0x180022297  mov     rbx, [rsp+60h+arg_8]
0x18002229f  add     rsp, 60h
0x1800222a3  pop     rdi
0x1800222a4  pop     rsi
0x1800222a5  pop     rbp
0x1800222a6  retn
```
