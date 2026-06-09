# SetEvalStateEx

- ea: `0x18004bdc8`
- end: `0x18004bf6b`
- name: `SetEvalStateEx`
- size: `419`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004508c`
- `0x180045568`
- `0x18004654c`
- `0x180048950`
- `0x180048d54`
- `0x18004b4c0`
- `0x18004b8d0`

## callees

- `0x18004bdc8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bf13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bf13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004be50`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004be50`

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
           qword_18008EC70,
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
                   qword_18008EC70,
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
0x18004bdc8  mov     [rsp-18h+arg_8], rbx
0x18004bdcd  push    rbp
0x18004bdce  push    rsi
0x18004bdcf  push    rdi
0x18004bdd0  mov     rbp, rsp
0x18004bdd3  sub     rsp, 60h
0x18004bdd7  mov     rax, [rcx]
0x18004bdda  mov     edi, r8d
0x18004bddd  mov     rsi, rdx
0x18004bde0  mov     [rbp+arg_18], 0
0x18004bde8  lea     r8, [rbp+arg_18]
0x18004bdec  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x18004bdf3  mov     rax, [rax]
0x18004bdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdfb  mov     ebx, eax
0x18004bdfd  test    eax, eax
0x18004bdff  js      loc_18004BF59
0x18004be05  mov     rcx, [rbp+arg_18]
0x18004be09  lea     r9, [rbp+arg_0]
0x18004be0d  mov     [rbp+arg_0], 0
0x18004be15  lea     r8, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x18004be1c  lea     rdx, qword_18008EC70
0x18004be23  mov     rax, [rcx]
0x18004be26  mov     rax, [rax+20h]
0x18004be2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be2f  test    eax, eax
0x18004be31  jns     short loc_18004BE60
0x18004be33  xor     edx, edx; pUnkOuter
0x18004be35  lea     rax, [rbp+arg_0]
0x18004be39  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a; riid
0x18004be40  mov     [rsp+60h+ppv], rax; ppv
0x18004be45  lea     rcx, _GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8; rclsid
0x18004be4c  lea     r8d, [rdx+1]; dwClsContext
0x18004be50  call    cs:__imp_CoCreateInstance
0x18004be56  mov     ebx, eax
0x18004be58  test    eax, eax
0x18004be5a  js      loc_18004BF49
0x18004be60  mov     rcx, [rbp+arg_0]
0x18004be64  lea     r8, [rbp+var_28]
0x18004be68  mov     [rbp+var_28], 0
0x18004be70  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x18004be77  mov     rax, [rcx]
0x18004be7a  mov     rax, [rax]
0x18004be7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be82  mov     ebx, eax
0x18004be84  test    eax, eax
0x18004be86  js      loc_18004BF39
0x18004be8c  mov     rcx, [rbp+var_28]
0x18004be90  lea     r9, [rbp+var_30]
0x18004be94  mov     [rbp+var_30], 0
0x18004be9c  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18004bea3  lea     rdx, OID_PropertyStore
0x18004beaa  mov     rax, [rcx]
0x18004bead  mov     rax, [rax+18h]
0x18004beb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beb6  mov     ebx, eax
0x18004beb8  test    eax, eax
0x18004beba  js      short loc_18004BF29
0x18004bebc  mov     rcx, [rbp+var_30]
0x18004bec0  lea     r8, [rbp+pvar]
0x18004bec4  xor     eax, eax
0x18004bec6  xorps   xmm0, xmm0
0x18004bec9  mov     [rbp+var_10], rax
0x18004becd  mov     rdx, rsi
0x18004bed0  movups  xmmword ptr [rbp+pvar], xmm0
0x18004bed4  mov     eax, 3
0x18004bed9  mov     dword ptr [rbp+pvar+8], edi
0x18004bedc  mov     word ptr [rbp+pvar], ax
0x18004bee0  mov     rax, [rcx]
0x18004bee3  mov     rax, [rax+20h]
0x18004bee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beec  mov     ebx, eax
0x18004beee  test    eax, eax
0x18004bef0  js      short loc_18004BF0F
0x18004bef2  mov     rcx, [rbp+arg_18]
0x18004bef6  lea     rdx, qword_18008EC70
0x18004befd  mov     r8, [rbp+arg_0]
0x18004bf01  mov     rax, [rcx]
0x18004bf04  mov     rax, [rax+18h]
0x18004bf08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf0d  mov     ebx, eax
0x18004bf0f  lea     rcx, [rbp+pvar]; pvar
0x18004bf13  call    cs:__imp_PropVariantClear
0x18004bf19  mov     rcx, [rbp+var_30]
0x18004bf1d  mov     rax, [rcx]
0x18004bf20  mov     rax, [rax+10h]
0x18004bf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf29  mov     rcx, [rbp+var_28]
0x18004bf2d  mov     rax, [rcx]
0x18004bf30  mov     rax, [rax+10h]
0x18004bf34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf39  mov     rcx, [rbp+arg_0]
0x18004bf3d  mov     rax, [rcx]
0x18004bf40  mov     rax, [rax+10h]
0x18004bf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf49  mov     rcx, [rbp+arg_18]
0x18004bf4d  mov     rax, [rcx]
0x18004bf50  mov     rax, [rax+10h]
0x18004bf54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf59  mov     eax, ebx
0x18004bf5b  mov     rbx, [rsp+60h+arg_8]
0x18004bf63  add     rsp, 60h
0x18004bf67  pop     rdi
0x18004bf68  pop     rsi
0x18004bf69  pop     rbp
0x18004bf6a  retn
```
