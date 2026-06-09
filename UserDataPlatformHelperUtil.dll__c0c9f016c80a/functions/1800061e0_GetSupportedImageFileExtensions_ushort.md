# GetSupportedImageFileExtensions(ushort * *)

- ea: `0x1800061e0`
- end: `0x18000677e`
- name: `?GetSupportedImageFileExtensions@@YAJPEAPEAG@Z`
- size: `1438`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006790`

## callees

- `0x18000116c`
- `0x180001178`
- `0x18000504c`
- `0x1800061e0`
- `0x180007344`
- `0x1800073f0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000666d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000666d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000621a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000621a`

## pseudocode

```c
__int64 __fastcall GetSupportedImageFileExtensions(unsigned __int16 **a1)
{
  HRESULT v2; // eax
  LPVOID v3; // rcx
  int v4; // ebx
  int v6; // eax
  __int64 v7; // rcx
  void (*v8)(void); // rax
  int v9; // eax
  unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // rbx
  unsigned int v13; // edi
  int v14; // edi
  __int64 v15; // rdx
  char v16; // al
  _WORD *v17; // rcx
  void (*v18)(void); // rax
  unsigned __int64 v19; // rbx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *v23; // r8
  unsigned __int16 *v24; // rdx
  _WORD *v25; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  __int64 v28; // [rsp+40h] [rbp-30h] BYREF
  void *Block; // [rsp+48h] [rbp-28h] BYREF
  char *v30; // [rsp+50h] [rbp-20h]
  _WORD v31[12]; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v32; // [rsp+A8h] [rbp+38h] BYREF
  int v33; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+48h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  v3 = ppv;
  v4 = v2;
  if ( v2 < 0 )
  {
    if ( !ppv )
      return (unsigned int)v4;
LABEL_3:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(v3);
    return (unsigned int)v4;
  }
  v34 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 184LL))(ppv, 1, 0, &v34);
  v7 = v34;
  v4 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 40LL))(v34);
  if ( v4 < 0 )
  {
    v7 = v34;
LABEL_6:
    if ( !v7 )
      goto LABEL_9;
    v8 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
    goto LABEL_8;
  }
  v31[0] = 0;
  Block = v31;
  v30 = (char *)v31;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(
          (__int64)&Block,
          260) )
  {
LABEL_43:
    v17 = Block;
    goto LABEL_44;
  }
  while ( 1 )
  {
    v27 = 0;
    v33 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v34 + 24LL))(v34, 1, &v27, &v33);
    v4 = v9;
    if ( v9 < 0 )
      goto LABEL_65;
    if ( v9 == 1 || !v33 )
    {
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v17 = Block;
      v19 = ((v30 - (_BYTE *)Block) >> 1) + 1;
      if ( (v30 - (_BYTE *)Block) >> 1 != -1 )
      {
        v20 = (unsigned __int16 *)LocalAlloc(0, 2 * v19);
        if ( !v20 )
          goto LABEL_43;
        if ( v19 <= 0x7FFFFFFF )
        {
          v21 = (unsigned __int16 *)Block;
          v22 = 2147483646;
          v23 = v20;
          do
          {
            if ( !v22 )
              break;
            if ( !*v21 )
              break;
            *v23++ = *v21++;
            --v22;
            --v19;
          }
          while ( v19 );
          v24 = v23 - 1;
          v13 = v19 == 0 ? 0x8007007A : 0;
          if ( v19 )
            v24 = v23;
          *v24 = 0;
          if ( v19 )
          {
            v25 = Block;
            *a1 = v20;
            if ( v25 != v31 )
              operator delete(v25);
            if ( v34 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            return 0;
          }
        }
        else
        {
          *v20 = 0;
          v13 = -2147024809;
        }
        LocalFree(v20);
        if ( Block != v31 )
          operator delete(Block);
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        if ( ppv )
        {
          v18 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_61:
          v18();
        }
        return v13;
      }
LABEL_44:
      if ( v17 != v31 )
        operator delete(v17);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 2147942414LL;
    }
    v28 = 0;
    if ( !v27 )
      goto LABEL_73;
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v27)(v27, &GUID_e87a44c4_b76e_4c47_8b09_298eb12a2714, &v28);
    if ( !v28 )
      break;
    v32 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v28 + 136LL))(v28, 0, 0, &v32);
    if ( v4 < 0 )
    {
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_65:
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( Block != v31 )
        operator delete(Block);
      if ( !v34 )
      {
LABEL_9:
        v3 = ppv;
        if ( !ppv )
          return (unsigned int)v4;
        goto LABEL_3;
      }
      v8 = *(void (**)(void))(*(_QWORD *)v34 + 16LL);
LABEL_8:
      v8();
      goto LABEL_9;
    }
    v10 = (unsigned __int16 *)operator new[](saturated_mul(v32, 2u));
    v11 = v28;
    v12 = v10;
    if ( !v10 )
      goto LABEL_39;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *))(*(_QWORD *)v28 + 136LL))(
            v28,
            v32,
            v10,
            &v32);
    if ( (v13 & 0x80000000) != 0 )
    {
      operator delete(v12);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( Block != v31 )
        operator delete(Block);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( ppv )
      {
        v18 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
        goto LABEL_61;
      }
      return v13;
    }
    if ( Block != v30
      && *((_WORD *)Block + ((v30 - (_BYTE *)Block) >> 1) - 1) != 59
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                             &Block,
                             59) )
    {
LABEL_38:
      operator delete(v12);
      v11 = v28;
LABEL_39:
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_43;
    }
    v14 = 0;
    if ( v32 )
    {
      while ( 1 )
      {
        v15 = v12[v14];
        if ( !(_WORD)v15 )
          goto LABEL_34;
        if ( (_WORD)v15 == 44 )
          break;
        if ( (_WORD)v15 != 46 )
          goto LABEL_31;
        v16 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                &Block,
                L"*.");
LABEL_32:
        if ( !v16 )
          goto LABEL_38;
        if ( ++v14 >= v32 )
          goto LABEL_34;
      }
      v15 = 59;
LABEL_31:
      v16 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
              &Block,
              v15);
      goto LABEL_32;
    }
LABEL_34:
    operator delete(v12);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_73:
  if ( Block != v31 )
    operator delete(Block);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800061e0  mov     [rsp-28h+arg_0], rbx
0x1800061e5  push    rbp
0x1800061e6  push    rsi
0x1800061e7  push    rdi
0x1800061e8  push    r12
0x1800061ea  push    r14
0x1800061ec  mov     rbp, rsp
0x1800061ef  sub     rsp, 70h
0x1800061f3  xor     r14d, r14d
0x1800061f6  lea     rax, [rbp+var_40]
0x1800061fa  mov     rsi, rcx
0x1800061fd  mov     [rbp+var_40], r14
0x180006201  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180006208  mov     [rsp+70h+ppv], rax; ppv
0x18000620d  xor     edx, edx; pUnkOuter
0x18000620f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006216  lea     r8d, [r14+1]; dwClsContext
0x18000621a  call    cs:__imp_CoCreateInstance
0x180006220  mov     rcx, [rbp+var_40]
0x180006224  mov     ebx, eax
0x180006226  test    eax, eax
0x180006228  jns     short loc_180006242
0x18000622a  test    rcx, rcx
0x18000622d  jz      short loc_18000623B
0x18000622f  mov     rdx, [rcx]
0x180006232  mov     rax, [rdx+10h]
0x180006236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623b  mov     eax, ebx
0x18000623d  jmp     loc_1800064EC
0x180006242  mov     [rbp+arg_18], r14
0x180006246  lea     r9, [rbp+arg_18]
0x18000624a  mov     rax, [rcx]
0x18000624d  xor     r8d, r8d
0x180006250  mov     rax, [rax+0B8h]
0x180006257  lea     edx, [r8+1]
0x18000625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006260  mov     rcx, [rbp+arg_18]
0x180006264  mov     ebx, eax
0x180006266  test    eax, eax
0x180006268  jns     short loc_18000628D
0x18000626a  test    rcx, rcx
0x18000626d  jz      short loc_18000627B
0x18000626f  mov     rdx, [rcx]
0x180006272  mov     rax, [rdx+10h]
0x180006276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000627b  mov     rcx, [rbp+var_40]
0x18000627f  test    rcx, rcx
0x180006282  jz      short loc_18000623B
0x180006284  mov     rax, [rcx]
0x180006287  mov     rax, [rax+10h]
0x18000628b  jmp     short loc_180006236
0x18000628d  mov     rax, [rcx]
0x180006290  mov     rax, [rax+28h]
0x180006294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006299  mov     ebx, eax
0x18000629b  test    eax, eax
0x18000629d  jns     short loc_1800062A5
0x18000629f  mov     rcx, [rbp+arg_18]
0x1800062a3  jmp     short loc_18000626A
0x1800062a5  lea     rax, [rbp+var_18]
0x1800062a9  mov     [rbp+var_18], r14w
0x1800062ae  mov     [rbp+Block], rax
0x1800062b2  lea     rcx, [rbp+Block]
0x1800062b6  lea     rax, [rbp+var_18]
0x1800062ba  mov     edx, 104h
0x1800062bf  mov     [rbp+var_20], rax
0x1800062c3  call    ?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)
0x1800062c8  test    al, al
0x1800062ca  jz      loc_1800064A4
0x1800062d0  mov     r12d, 3Bh ; ';'
0x1800062d6  mov     rcx, [rbp+arg_18]
0x1800062da  lea     r9, [rbp+arg_10]
0x1800062de  mov     [rbp+var_38], r14
0x1800062e2  lea     r8, [rbp+var_38]
0x1800062e6  mov     [rbp+arg_10], r14d
0x1800062ea  mov     edx, 1
0x1800062ef  mov     rax, [rcx]
0x1800062f2  mov     rax, [rax+18h]
0x1800062f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fb  mov     ebx, eax
0x1800062fd  test    eax, eax
0x1800062ff  js      loc_180006591
0x180006305  cmp     eax, 1
0x180006308  jz      loc_18000663A
0x18000630e  cmp     [rbp+arg_10], r14d
0x180006312  jbe     loc_18000663A
0x180006318  mov     rcx, [rbp+var_38]
0x18000631c  mov     [rbp+var_30], r14
0x180006320  test    rcx, rcx
0x180006323  jz      loc_1800065ED
0x180006329  mov     rax, [rcx]
0x18000632c  lea     r8, [rbp+var_30]
0x180006330  lea     rdx, _GUID_e87a44c4_b76e_4c47_8b09_298eb12a2714
0x180006337  mov     rax, [rax]
0x18000633a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633f  mov     rcx, [rbp+var_30]
0x180006343  test    rcx, rcx
0x180006346  jz      loc_1800065D8
0x18000634c  mov     [rbp+arg_8], r14d
0x180006350  lea     r9, [rbp+arg_8]
0x180006354  mov     rax, [rcx]
0x180006357  xor     r8d, r8d
0x18000635a  xor     edx, edx
0x18000635c  mov     rax, [rax+88h]
0x180006363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006368  mov     ebx, eax
0x18000636a  test    eax, eax
0x18000636c  js      loc_18000657C
0x180006372  mov     ecx, [rbp+arg_8]
0x180006375  mov     eax, 2
0x18000637a  mul     rcx
0x18000637d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006384  cmovb   rax, rcx
0x180006388  mov     rcx, rax; unsigned __int64
0x18000638b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006390  mov     rcx, [rbp+var_30]
0x180006394  mov     rbx, rax
0x180006397  test    rax, rax
0x18000639a  jz      loc_18000647E
0x1800063a0  mov     rax, [rcx]
0x1800063a3  lea     r9, [rbp+arg_8]
0x1800063a7  mov     edx, [rbp+arg_8]
0x1800063aa  mov     r8, rbx
0x1800063ad  mov     rax, [rax+88h]
0x1800063b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b9  mov     edi, eax
0x1800063bb  test    eax, eax
0x1800063bd  js      loc_180006500
0x1800063c3  mov     rcx, [rbp+Block]
0x1800063c7  mov     rax, [rbp+var_20]
0x1800063cb  cmp     rcx, rax
0x1800063ce  jz      short loc_1800063F2
0x1800063d0  sub     rax, rcx
0x1800063d3  sar     rax, 1
0x1800063d6  cmp     [rcx+rax*2-2], r12w
0x1800063dc  jz      short loc_1800063F2
0x1800063de  mov     edx, r12d
0x1800063e1  lea     rcx, [rbp+Block]
0x1800063e5  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x1800063ea  test    al, al
0x1800063ec  jz      loc_180006472
0x1800063f2  mov     edi, r14d
0x1800063f5  cmp     [rbp+arg_8], r14d
0x1800063f9  jbe     short loc_180006437
0x1800063fb  mov     eax, edi
0x1800063fd  movzx   edx, word ptr [rbx+rax*2]
0x180006401  test    dx, dx
0x180006404  jz      short loc_180006437
0x180006406  lea     rcx, [rbp+Block]
0x18000640a  cmp     dx, 2Ch ; ','
0x18000640e  jz      short loc_180006424
0x180006410  cmp     dx, 2Eh ; '.'
0x180006414  jnz     short loc_180006427
0x180006416  lea     rdx, asc_18000D304; "*."
0x18000641d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180006422  jmp     short loc_18000642C
0x180006424  mov     edx, r12d
0x180006427  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x18000642c  test    al, al
0x18000642e  jz      short loc_180006472
0x180006430  inc     edi
0x180006432  cmp     edi, [rbp+arg_8]
0x180006435  jb      short loc_1800063FB
0x180006437  mov     rcx, rbx; Block
0x18000643a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000643f  mov     rcx, [rbp+var_30]
0x180006443  test    rcx, rcx
0x180006446  jz      short loc_180006454
0x180006448  mov     rax, [rcx]
0x18000644b  mov     rax, [rax+10h]
0x18000644f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006454  mov     rcx, [rbp+var_38]
0x180006458  test    rcx, rcx
0x18000645b  jz      loc_1800062D6
0x180006461  mov     rax, [rcx]
0x180006464  mov     rax, [rax+10h]
0x180006468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646d  jmp     loc_1800062D6
0x180006472  mov     rcx, rbx; Block
0x180006475  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000647a  mov     rcx, [rbp+var_30]
0x18000647e  test    rcx, rcx
0x180006481  jz      short loc_18000648F
0x180006483  mov     rax, [rcx]
0x180006486  mov     rax, [rax+10h]
0x18000648a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648f  mov     rcx, [rbp+var_38]
0x180006493  test    rcx, rcx
0x180006496  jz      short loc_1800064A4
0x180006498  mov     rax, [rcx]
0x18000649b  mov     rax, [rax+10h]
0x18000649f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a4  mov     rcx, [rbp+Block]; Block
0x1800064a8  lea     rax, [rbp+var_18]
0x1800064ac  cmp     rcx, rax
0x1800064af  jz      short loc_1800064BD
0x1800064b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800064b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064bd  mov     rcx, [rbp+arg_18]
0x1800064c1  test    rcx, rcx
0x1800064c4  jz      short loc_1800064D2
0x1800064c6  mov     rax, [rcx]
0x1800064c9  mov     rax, [rax+10h]
0x1800064cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d2  mov     rcx, [rbp+var_40]
0x1800064d6  test    rcx, rcx
0x1800064d9  jz      short loc_1800064E7
0x1800064db  mov     rax, [rcx]
0x1800064de  mov     rax, [rax+10h]
0x1800064e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e7  mov     eax, 8007000Eh
0x1800064ec  mov     rbx, [rsp+70h+arg_0]
0x1800064f4  add     rsp, 70h
0x1800064f8  pop     r14
0x1800064fa  pop     r12
0x1800064fc  pop     rdi
0x1800064fd  pop     rsi
0x1800064fe  pop     rbp
0x1800064ff  retn
0x180006500  mov     rcx, rbx; Block
0x180006503  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006508  mov     rcx, [rbp+var_30]
0x18000650c  test    rcx, rcx
0x18000650f  jz      short loc_18000651D
0x180006511  mov     rax, [rcx]
0x180006514  mov     rax, [rax+10h]
0x180006518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651d  mov     rcx, [rbp+var_38]
0x180006521  test    rcx, rcx
0x180006524  jz      short loc_180006532
0x180006526  mov     rax, [rcx]
0x180006529  mov     rax, [rax+10h]
0x18000652d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006532  mov     rcx, [rbp+Block]; Block
0x180006536  lea     rax, [rbp+var_18]
0x18000653a  cmp     rcx, rax
0x18000653d  jz      short loc_18000654B
0x18000653f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180006546  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000654b  mov     rcx, [rbp+arg_18]
0x18000654f  test    rcx, rcx
0x180006552  jz      short loc_180006560
0x180006554  mov     rax, [rcx]
0x180006557  mov     rax, [rax+10h]
0x18000655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006560  mov     rcx, [rbp+var_40]
0x180006564  test    rcx, rcx
0x180006567  jz      short loc_180006575
0x180006569  mov     rax, [rcx]
0x18000656c  mov     rax, [rax+10h]
0x180006570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006575  mov     eax, edi
0x180006577  jmp     loc_1800064EC
0x18000657c  mov     rcx, [rbp+var_30]
0x180006580  test    rcx, rcx
0x180006583  jz      short loc_180006591
0x180006585  mov     rax, [rcx]
0x180006588  mov     rax, [rax+10h]
0x18000658c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006591  mov     rcx, [rbp+var_38]
0x180006595  test    rcx, rcx
0x180006598  jz      short loc_1800065A6
0x18000659a  mov     rax, [rcx]
0x18000659d  mov     rax, [rax+10h]
0x1800065a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a6  mov     rcx, [rbp+Block]; Block
0x1800065aa  lea     rax, [rbp+var_18]
0x1800065ae  cmp     rcx, rax
0x1800065b1  jz      short loc_1800065BF
0x1800065b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800065ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800065bf  mov     rcx, [rbp+arg_18]
0x1800065c3  test    rcx, rcx
0x1800065c6  jz      loc_18000627B
0x1800065cc  mov     rax, [rcx]
0x1800065cf  mov     rax, [rax+10h]
0x1800065d3  jmp     loc_180006276
0x1800065d8  mov     rcx, [rbp+var_38]
0x1800065dc  test    rcx, rcx
0x1800065df  jz      short loc_1800065ED
0x1800065e1  mov     rax, [rcx]
0x1800065e4  mov     rax, [rax+10h]
0x1800065e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ed  mov     rcx, [rbp+Block]; Block
0x1800065f1  lea     rax, [rbp+var_18]
0x1800065f5  cmp     rcx, rax
0x1800065f8  jz      short loc_180006606
0x1800065fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180006601  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006606  mov     rcx, [rbp+arg_18]
0x18000660a  test    rcx, rcx
0x18000660d  jz      short loc_18000661B
0x18000660f  mov     rax, [rcx]
0x180006612  mov     rax, [rax+10h]
0x180006616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661b  mov     rcx, [rbp+var_40]
0x18000661f  test    rcx, rcx
0x180006622  jz      short loc_180006630
0x180006624  mov     rax, [rcx]
0x180006627  mov     rax, [rax+10h]
  ... truncated ...
```
