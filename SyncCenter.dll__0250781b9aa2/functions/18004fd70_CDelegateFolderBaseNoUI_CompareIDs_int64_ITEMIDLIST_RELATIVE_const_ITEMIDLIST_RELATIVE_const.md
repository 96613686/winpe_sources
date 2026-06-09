# CDelegateFolderBaseNoUI::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18004fd70`
- end: `0x18004ff9b`
- name: `?CompareIDs@CDelegateFolderBaseNoUI@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `555`
- prototype: `int(CDelegateFolderBaseNoUI *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800325e4`
- `0x18004f070`
- `0x18004fd70`
- `0x180051080`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff19`
- `PROPSYS!PropVariantCompareEx` at `0x18004ff03`
- `PROPSYS!PropVariantCompareEx` at `0x18004ff03`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ff23`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ff23`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::CompareIDs(
        unsigned __int64 this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  struct IShellFolder2 *v7; // r13
  int v8; // eax
  __int64 v9; // r14
  unsigned int v10; // esi
  int PropertyStorageFromIDList; // ebx
  CDelegateFolderBaseNoUI *v12; // rcx
  int v13; // edi
  bool v14; // sf
  void *v16; // [rsp+20h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-48h] BYREF
  void *v18; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h]
  PROPVARIANT propvar1[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h]
  unsigned int v23; // [rsp+B0h] [rbp+40h] BYREF
  int v24; // [rsp+B8h] [rbp+48h] BYREF

  v7 = (struct IShellFolder2 *)(this & -(__int64)(this != 8));
  v8 = CompareIDsImpl(v7, a2, a3, a4);
  v9 = a2 | 0x80000000LL;
  if ( v8 != -2147467263 )
    v9 = a2;
  v10 = 0;
  PropertyStorageFromIDList = 0;
  if ( v8 != -2147467263 )
    PropertyStorageFromIDList = v8;
  if ( !PropertyStorageFromIDList && (v9 & 0x80000000) != 0 )
  {
    v16 = 0;
    PropertyStorageFromIDList = CDelegateFolderBaseNoUI::_GetPropertyStorageFromIDList(
                                  (CDelegateFolderBaseNoUI *)0x80004001LL,
                                  a3,
                                  &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                                  &v16);
    if ( PropertyStorageFromIDList >= 0 )
    {
      v18 = 0;
      PropertyStorageFromIDList = CDelegateFolderBaseNoUI::_GetPropertyStorageFromIDList(
                                    v12,
                                    a4,
                                    &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                                    &v18);
      if ( PropertyStorageFromIDList >= 0 )
      {
        v23 = 0;
        PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v16 + 40LL))(
                                      v16,
                                      &v23);
        if ( PropertyStorageFromIDList >= 0 )
        {
          v24 = 0;
          v13 = 0;
          PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v18 + 40LL))(v18, &v24);
          if ( PropertyStorageFromIDList >= 0 )
            v13 = v24 - v23;
          if ( v23 )
          {
            while ( PropertyStorageFromIDList >= 0 )
            {
              v14 = v13 < 0;
              if ( v13 )
                goto LABEL_25;
              bstrString = 0;
              PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, _QWORD, BSTR *))(*(_QWORD *)v16 + 48LL))(
                                            v16,
                                            v10,
                                            &bstrString);
              if ( PropertyStorageFromIDList >= 0 )
              {
                v22 = 0;
                *(_OWORD *)propvar1 = 0;
                PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, BSTR, PROPVARIANT *))(*(_QWORD *)v16 + 24LL))(
                                              v16,
                                              bstrString,
                                              propvar1);
                if ( PropertyStorageFromIDList >= 0 )
                {
                  v20 = 0;
                  *(_OWORD *)propvar2 = 0;
                  PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, BSTR, PROPVARIANT *))(*(_QWORD *)v18 + 24LL))(
                                                v18,
                                                bstrString,
                                                propvar2);
                  if ( PropertyStorageFromIDList >= 0 )
                  {
                    v13 = PropVariantCompareEx(propvar1, propvar2, PVCU_DEFAULT, 0);
                    PropVariantClear(propvar2);
                  }
                  PropVariantClear(propvar1);
                }
                SysFreeString(bstrString);
              }
              if ( ++v10 >= v23 )
                goto LABEL_22;
            }
          }
          else
          {
LABEL_22:
            if ( PropertyStorageFromIDList >= 0 )
            {
              v14 = v13 < 0;
              if ( v13 )
              {
LABEL_25:
                if ( v14 )
                  PropertyStorageFromIDList = 0xFFFF;
                else
                  PropertyStorageFromIDList = v13 > 0;
              }
              else
              {
                PropertyStorageFromIDList = ILCompareRelIDs(v7, a3, a4, v9);
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  return (unsigned int)PropertyStorageFromIDList;
}

```

## disassembly

```asm
0x18004fd70  mov     [rsp-38h+arg_10], rbx
0x18004fd75  push    rbp
0x18004fd76  push    rsi
0x18004fd77  push    rdi
0x18004fd78  push    r12
0x18004fd7a  push    r13
0x18004fd7c  push    r14
0x18004fd7e  push    r15
0x18004fd80  mov     rbp, rsp
0x18004fd83  sub     rsp, 70h
0x18004fd87  lea     rax, [rcx-8]
0x18004fd8b  mov     r15, r9
0x18004fd8e  neg     rax
0x18004fd91  mov     r12, r8
0x18004fd94  mov     rbx, rdx
0x18004fd97  sbb     r13, r13
0x18004fd9a  and     r13, rcx
0x18004fd9d  mov     rcx, r13; struct IShellFolder2 *
0x18004fda0  call    ?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z; CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)
0x18004fda5  mov     r14, rbx
0x18004fda8  mov     ecx, 80004001h; this
0x18004fdad  mov     edx, 80000000h
0x18004fdb2  or      r14, rdx
0x18004fdb5  cmp     eax, ecx
0x18004fdb7  cmovnz  r14, rbx
0x18004fdbb  xor     esi, esi
0x18004fdbd  cmp     eax, ecx
0x18004fdbf  mov     ebx, esi
0x18004fdc1  cmovnz  ebx, eax
0x18004fdc4  test    ebx, ebx
0x18004fdc6  jnz     loc_18004FF81
0x18004fdcc  test    rdx, r14
0x18004fdcf  jz      loc_18004FF81
0x18004fdd5  lea     r9, [rbp+var_50]; void **
0x18004fdd9  mov     [rbp+var_50], rsi
0x18004fddd  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; struct _GUID *
0x18004fde4  mov     rdx, r12; struct _ITEMIDLIST_RELATIVE *
0x18004fde7  call    ?_GetPropertyStorageFromIDList@CDelegateFolderBaseNoUI@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CDelegateFolderBaseNoUI::_GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18004fdec  mov     ebx, eax
0x18004fdee  test    eax, eax
0x18004fdf0  js      loc_18004FF81
0x18004fdf6  lea     r9, [rbp+var_40]; void **
0x18004fdfa  mov     [rbp+var_40], rsi
0x18004fdfe  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; struct _GUID *
0x18004fe05  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18004fe08  call    ?_GetPropertyStorageFromIDList@CDelegateFolderBaseNoUI@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CDelegateFolderBaseNoUI::_GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18004fe0d  mov     ebx, eax
0x18004fe0f  test    eax, eax
0x18004fe11  js      loc_18004FF71
0x18004fe17  mov     rcx, [rbp+var_50]
0x18004fe1b  lea     rdx, [rbp+arg_0]
0x18004fe1f  mov     [rbp+arg_0], esi
0x18004fe22  mov     rax, [rcx]
0x18004fe25  mov     rax, [rax+28h]
0x18004fe29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe2e  mov     ebx, eax
0x18004fe30  test    eax, eax
0x18004fe32  js      loc_18004FF61
0x18004fe38  mov     rcx, [rbp+var_40]
0x18004fe3c  lea     rdx, [rbp+arg_8]
0x18004fe40  mov     [rbp+arg_8], esi
0x18004fe43  mov     edi, esi
0x18004fe45  mov     rax, [rcx]
0x18004fe48  mov     rax, [rax+28h]
0x18004fe4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe51  mov     ebx, eax
0x18004fe53  mov     eax, [rbp+arg_0]
0x18004fe56  test    ebx, ebx
0x18004fe58  js      short loc_18004FE5F
0x18004fe5a  mov     edi, [rbp+arg_8]
0x18004fe5d  sub     edi, eax
0x18004fe5f  test    eax, eax
0x18004fe61  jz      loc_18004FF34
0x18004fe67  test    ebx, ebx
0x18004fe69  js      loc_18004FF61
0x18004fe6f  test    edi, edi
0x18004fe71  jnz     loc_18004FF51
0x18004fe77  mov     rcx, [rbp+var_50]
0x18004fe7b  lea     r8, [rbp+bstrString]
0x18004fe7f  mov     [rbp+bstrString], 0
0x18004fe87  mov     edx, esi
0x18004fe89  mov     rax, [rcx]
0x18004fe8c  mov     rax, [rax+30h]
0x18004fe90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe95  mov     ebx, eax
0x18004fe97  test    eax, eax
0x18004fe99  js      loc_18004FF29
0x18004fe9f  mov     rcx, [rbp+var_50]
0x18004fea3  lea     r8, [rbp+propvar1]
0x18004fea7  mov     rdx, [rbp+bstrString]
0x18004feab  xor     eax, eax
0x18004fead  mov     [rbp+var_10], rax
0x18004feb1  xorps   xmm0, xmm0
0x18004feb4  movups  xmmword ptr [rbp+propvar1], xmm0
0x18004feb8  mov     rax, [rcx]
0x18004febb  mov     rax, [rax+18h]
0x18004febf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fec4  mov     ebx, eax
0x18004fec6  test    eax, eax
0x18004fec8  js      short loc_18004FF1F
0x18004feca  mov     rcx, [rbp+var_40]
0x18004fece  lea     r8, [rbp+propvar2]
0x18004fed2  mov     rdx, [rbp+bstrString]
0x18004fed6  xor     eax, eax
0x18004fed8  mov     [rbp+var_28], rax
0x18004fedc  xorps   xmm0, xmm0
0x18004fedf  movups  xmmword ptr [rbp+propvar2], xmm0
0x18004fee3  mov     rax, [rcx]
0x18004fee6  mov     rax, [rax+18h]
0x18004feea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004feef  mov     ebx, eax
0x18004fef1  test    eax, eax
0x18004fef3  js      short loc_18004FF15
0x18004fef5  xor     r9d, r9d; flags
0x18004fef8  lea     rdx, [rbp+propvar2]; propvar2
0x18004fefc  xor     r8d, r8d; unit
0x18004feff  lea     rcx, [rbp+propvar1]; propvar1
0x18004ff03  call    cs:__imp_PropVariantCompareEx
0x18004ff09  lea     rcx, [rbp+propvar2]; pvar
0x18004ff0d  mov     edi, eax
0x18004ff0f  call    cs:__imp_PropVariantClear
0x18004ff15  lea     rcx, [rbp+propvar1]; pvar
0x18004ff19  call    cs:__imp_PropVariantClear
0x18004ff1f  mov     rcx, [rbp+bstrString]; bstrString
0x18004ff23  call    cs:__imp_SysFreeString
0x18004ff29  inc     esi
0x18004ff2b  cmp     esi, [rbp+arg_0]
0x18004ff2e  jb      loc_18004FE67
0x18004ff34  test    ebx, ebx
0x18004ff36  js      short loc_18004FF61
0x18004ff38  test    edi, edi
0x18004ff3a  jnz     short loc_18004FF51
0x18004ff3c  mov     r9, r14
0x18004ff3f  mov     r8, r15
0x18004ff42  mov     rdx, r12
0x18004ff45  mov     rcx, r13
0x18004ff48  call    ILCompareRelIDs
0x18004ff4d  mov     ebx, eax
0x18004ff4f  jmp     short loc_18004FF61
0x18004ff51  jns     short loc_18004FF5A
0x18004ff53  mov     ebx, 0FFFFh
0x18004ff58  jmp     short loc_18004FF61
0x18004ff5a  xor     ebx, ebx
0x18004ff5c  test    edi, edi
0x18004ff5e  setnle  bl
0x18004ff61  mov     rcx, [rbp+var_40]
0x18004ff65  mov     rax, [rcx]
0x18004ff68  mov     rax, [rax+10h]
0x18004ff6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff71  mov     rcx, [rbp+var_50]
0x18004ff75  mov     rax, [rcx]
0x18004ff78  mov     rax, [rax+10h]
0x18004ff7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff81  mov     eax, ebx
0x18004ff83  mov     rbx, [rsp+70h+arg_10]
0x18004ff8b  add     rsp, 70h
0x18004ff8f  pop     r15
0x18004ff91  pop     r14
0x18004ff93  pop     r13
0x18004ff95  pop     r12
0x18004ff97  pop     rdi
0x18004ff98  pop     rsi
0x18004ff99  pop     rbp
0x18004ff9a  retn
```
