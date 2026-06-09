# RoutingLegacyUiccDialog::CreateActionDialog(void)

- ea: `0x180040d78`
- end: `0x180040f31`
- name: `?CreateActionDialog@RoutingLegacyUiccDialog@@AEAAJXZ`
- size: `441`
- prototype: `__int64 __fastcall(RoutingLegacyUiccDialog *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030a40`

## callees

- `0x18000584c`
- `0x180013014`
- `0x180040d78`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RoutingLegacyUiccDialog::CreateActionDialog(RoutingLegacyUiccDialog *this)
{
  int v2; // r15d
  __int64 v3; // r8
  void *v4; // r9
  char **v5; // rcx
  unsigned __int64 v6; // rdx
  char *v7; // r12
  __int64 v8; // rbx
  __int64 v9; // r8
  void *v10; // r9
  char **v11; // rcx
  unsigned __int64 v12; // rdx
  char *v13; // r12
  __int64 v14; // rbx
  __int64 v15; // r8
  void *v16; // r9
  char *v17; // rcx
  unsigned __int64 v18; // rsi
  char *v19; // r14
  void *pv; // [rsp+68h] [rbp+10h] BYREF
  void *v22; // [rsp+70h] [rbp+18h] BYREF
  void *Src; // [rsp+78h] [rbp+20h] BYREF

  Src = 0;
  v22 = 0;
  pv = 0;
  v2 = (*(__int64 (__fastcall **)(RoutingLegacyUiccDialog *, __int64, void **))(*(_QWORD *)this + 40LL))(
         this,
         120,
         &Src);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(RoutingLegacyUiccDialog *, __int64, void **))(*(_QWORD *)this + 40LL))(
           this,
           121,
           &v22);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(RoutingLegacyUiccDialog *, __int64, void **))(*(_QWORD *)this + 40LL))(
             this,
             119,
             &pv);
      if ( v2 >= 0 )
      {
        try
        {
          v4 = Src;
          v5 = (char **)((char *)this + 8);
          v18 = -1;
          v6 = -1;
          do
            ++v6;
          while ( *((_WORD *)Src + v6) );
          if ( v6 > *((_QWORD *)this + 4) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              v5,
              v6,
              v3,
              Src);
          }
          else
          {
            if ( *((_QWORD *)this + 4) <= 7u )
              v7 = (char *)this + 8;
            else
              v7 = *v5;
            *((_QWORD *)this + 3) = v6;
            v8 = 2 * v6;
            memmove_0(v7, v4, 2 * v6);
            *(_WORD *)&v7[v8] = 0;
          }
          v10 = v22;
          v11 = (char **)((char *)this + 40);
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)v22 + v12) );
          if ( v12 > *((_QWORD *)this + 8) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              v11,
              v12,
              v9,
              v22);
          }
          else
          {
            if ( *((_QWORD *)this + 8) <= 7u )
              v13 = (char *)this + 40;
            else
              v13 = *v11;
            *((_QWORD *)this + 7) = v12;
            v14 = 2 * v12;
            memmove_0(v13, v10, 2 * v12);
            *(_WORD *)&v13[v14] = 0;
          }
          v16 = pv;
          v17 = (char *)this + 72;
          do
            ++v18;
          while ( *((_WORD *)pv + v18) );
          if ( v18 > *((_QWORD *)this + 12) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              v17,
              v18,
              v15,
              pv);
          }
          else
          {
            if ( *((_QWORD *)this + 12) <= 7u )
              v19 = (char *)this + 72;
            else
              v19 = *(char **)v17;
            *((_QWORD *)v17 + 2) = v18;
            memmove_0(v19, v16, 2 * v18);
            *(_WORD *)&v19[2 * v18] = 0;
          }
        }
        catch ( std::bad_alloc )
        {
          v2 = -2147024882;
        }
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v22 )
    CoTaskMemFree(v22);
  if ( Src )
    CoTaskMemFree(Src);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180040d78  mov     r11, rsp
0x180040d7b  push    rbx
0x180040d7c  push    rsi
0x180040d7d  push    rdi
0x180040d7e  push    r12
0x180040d80  push    r14
0x180040d82  push    r15
0x180040d84  sub     rsp, 28h
0x180040d88  mov     r14, rcx
0x180040d8b  xor     edi, edi
0x180040d8d  mov     [r11+20h], rdi
0x180040d91  mov     [r11+18h], rdi
0x180040d95  mov     [r11+10h], rdi
0x180040d99  mov     rax, [rcx]
0x180040d9c  lea     r8, [r11+20h]
0x180040da0  lea     edx, [rdi+78h]
0x180040da3  mov     rax, [rax+28h]
0x180040da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dac  mov     r15d, eax
0x180040daf  test    eax, eax
0x180040db1  js      loc_180040EEE
0x180040db7  mov     rax, [r14]
0x180040dba  lea     r8, [rsp+58h+arg_10]
0x180040dbf  lea     edx, [rdi+79h]
0x180040dc2  mov     rcx, r14
0x180040dc5  mov     rax, [rax+28h]
0x180040dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dce  mov     r15d, eax
0x180040dd1  test    eax, eax
0x180040dd3  js      loc_180040EEE
0x180040dd9  mov     rax, [r14]
0x180040ddc  lea     r8, [rsp+58h+pv]
0x180040de1  lea     edx, [rdi+77h]
0x180040de4  mov     rcx, r14
0x180040de7  mov     rax, [rax+28h]
0x180040deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040df0  mov     r15d, eax
0x180040df3  test    eax, eax
0x180040df5  js      loc_180040EEE
0x180040dfb  mov     r9, [rsp+58h+Src]
0x180040e00  lea     rcx, [r14+8]
0x180040e04  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180040e08  mov     rdx, rsi
0x180040e0b  inc     rdx
0x180040e0e  cmp     [r9+rdx*2], di
0x180040e13  jnz     short loc_180040E0B
0x180040e15  cmp     rdx, [rcx+18h]
0x180040e19  ja      short loc_180040E47
0x180040e1b  cmp     qword ptr [rcx+18h], 7
0x180040e20  jbe     short loc_180040E27
0x180040e22  mov     r12, [rcx]
0x180040e25  jmp     short loc_180040E2A
0x180040e27  mov     r12, rcx
0x180040e2a  mov     [rcx+10h], rdx
0x180040e2e  lea     rbx, [rdx+rdx]
0x180040e32  mov     r8, rbx; Size
0x180040e35  mov     rdx, r9; Src
0x180040e38  mov     rcx, r12; void *
0x180040e3b  call    memmove_0
0x180040e40  mov     [rbx+r12], di
0x180040e45  jmp     short loc_180040E4C
0x180040e47  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180040e4c  mov     r9, [rsp+58h+arg_10]
0x180040e51  lea     rcx, [r14+28h]
0x180040e55  mov     rdx, rsi
0x180040e58  inc     rdx
0x180040e5b  cmp     [r9+rdx*2], di
0x180040e60  jnz     short loc_180040E58
0x180040e62  cmp     rdx, [rcx+18h]
0x180040e66  ja      short loc_180040E94
0x180040e68  cmp     qword ptr [rcx+18h], 7
0x180040e6d  jbe     short loc_180040E74
0x180040e6f  mov     r12, [rcx]
0x180040e72  jmp     short loc_180040E77
0x180040e74  mov     r12, rcx
0x180040e77  mov     [rcx+10h], rdx
0x180040e7b  lea     rbx, [rdx+rdx]
0x180040e7f  mov     r8, rbx; Size
0x180040e82  mov     rdx, r9; Src
0x180040e85  mov     rcx, r12; void *
0x180040e88  call    memmove_0
0x180040e8d  mov     [rbx+r12], di
0x180040e92  jmp     short loc_180040E99
0x180040e94  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180040e99  mov     r9, [rsp+58h+pv]
0x180040e9e  lea     rcx, [r14+48h]
0x180040ea2  inc     rsi
0x180040ea5  cmp     [r9+rsi*2], di
0x180040eaa  jnz     short loc_180040EA2
0x180040eac  cmp     rsi, [rcx+18h]
0x180040eb0  ja      short loc_180040EDE
0x180040eb2  cmp     qword ptr [rcx+18h], 7
0x180040eb7  jbe     short loc_180040EBE
0x180040eb9  mov     r14, [rcx]
0x180040ebc  jmp     short loc_180040EC1
0x180040ebe  mov     r14, rcx
0x180040ec1  mov     [rcx+10h], rsi
0x180040ec5  lea     rbx, [rsi+rsi]
0x180040ec9  mov     r8, rbx; Size
0x180040ecc  mov     rdx, r9; Src
0x180040ecf  mov     rcx, r14; void *
0x180040ed2  call    memmove_0
0x180040ed7  mov     [rbx+r14], di
0x180040edc  jmp     short loc_180040EE7
0x180040ede  mov     rdx, rsi
0x180040ee1  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180040ee6  nop
0x180040ee7  jmp     short loc_180040EEE
0x180040ee9  mov     r15d, [rsp+58h+arg_0]
0x180040eee  mov     rcx, [rsp+58h+pv]; pv
0x180040ef3  test    rcx, rcx
0x180040ef6  jz      short loc_180040EFF
0x180040ef8  call    cs:__imp_CoTaskMemFree
0x180040efe  nop
0x180040eff  mov     rcx, [rsp+58h+arg_10]; pv
0x180040f04  test    rcx, rcx
0x180040f07  jz      short loc_180040F10
0x180040f09  call    cs:__imp_CoTaskMemFree
0x180040f0f  nop
0x180040f10  mov     rcx, [rsp+58h+Src]; pv
0x180040f15  test    rcx, rcx
0x180040f18  jz      short loc_180040F20
0x180040f1a  call    cs:__imp_CoTaskMemFree
0x180040f20  mov     eax, r15d
0x180040f23  add     rsp, 28h
0x180040f27  pop     r15
0x180040f29  pop     r14
0x180040f2b  pop     r12
0x180040f2d  pop     rdi
0x180040f2e  pop     rsi
0x180040f2f  pop     rbx
0x180040f30  retn
```
