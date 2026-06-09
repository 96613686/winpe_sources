# StreamGroupParams::Clone(StreamGroupParams * *)

- ea: `0x18000dbd0`
- end: `0x18000df4e`
- name: `?Clone@StreamGroupParams@@QEBAJPEAPEAU1@@Z`
- size: `894`
- prototype: `__int64 __fastcall(StreamGroupParams *__hidden this, struct StreamGroupParams **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d6c0`

## callees

- `0x18000b0c0`
- `0x18000dbd0`
- `0x18000df54`
- `0x18000e284`
- `0x18000e2a4`
- `0x18000e474`
- `0x18001280c`
- `0x180050e28`
- `0x1800523dc`
- `0x180054d18`
- `0x1800a80f4`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800ce768`
- `0x1800ce774`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df30`

## pseudocode

```c
__int64 __fastcall StreamGroupParams::Clone(StreamGroupParams *this, struct StreamGroupParams **a2)
{
  struct StreamGroupParams **v2; // r13
  void *v4; // rsi
  __int64 v5; // rbx
  void *v6; // rax
  void *v7; // rdi
  void **v9; // r15
  void *v10; // rcx
  unsigned __int64 v11; // rbx
  char *v12; // rdi
  unsigned __int64 v13; // r13
  const void *v14; // rdx
  void *v15; // rcx
  size_t v16; // rbx
  char *v17; // rax
  void *v18; // rbx
  char *v19; // rax
  char *v20; // r14
  __int64 v21; // rcx
  char *v22; // rdi
  size_t v23; // rbx
  int v24; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF
  struct StreamGroupParams **v27; // [rsp+78h] [rbp+10h]
  void *Src; // [rsp+80h] [rbp+18h] BYREF
  char *v29; // [rsp+88h] [rbp+20h] BYREF

  v27 = a2;
  v2 = a2;
  wil::make_cotaskmem_string_nothrow((wil *)&pv, *(const unsigned __int16 **)this, 0xFFFFFFFFFFFFFFFFuLL);
  v4 = pv;
  if ( pv )
  {
    v5 = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 16LL);
    v6 = CoTaskMemAlloc(v5 + 18);
    v7 = v6;
    if ( v6 )
    {
      memcpy_0(v6, *((const void **)this + 2), v5 + 18);
      v19 = (char *)operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      Src = v19;
      if ( v19 )
      {
        memset_0(v19, 0, 0x60u);
        *(_QWORD *)v20 = 0;
        *((_QWORD *)v20 + 2) = 0;
        std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(v20 + 56);
        *(_QWORD *)(v21 + 24) = 0;
        *(_BYTE *)(v21 + 32) = 0;
      }
      else
      {
        v20 = 0;
      }
      v29 = v20;
      if ( v20 )
      {
        pv = 0;
        CoTaskMemFree(*(LPVOID *)v20);
        *(_QWORD *)v20 = v4;
        v20[49] = *((_BYTE *)this + 49);
        CoTaskMemFree(*((LPVOID *)v20 + 2));
        *((_QWORD *)v20 + 2) = v7;
        *((_QWORD *)v20 + 3) = *((_QWORD *)this + 3);
        *((_OWORD *)v20 + 2) = *((_OWORD *)this + 2);
        v20[48] = *((_BYTE *)this + 48);
        v20[50] = *((_BYTE *)this + 50);
        *((_DWORD *)v20 + 2) = *((_DWORD *)this + 2);
        v9 = (void **)(v20 + 56);
        if ( v20 + 56 != (char *)this + 56 )
        {
          v10 = (void *)*((_QWORD *)this + 7);
          Src = v10;
          v11 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 8) - (_QWORD)v10) >> 2);
          v12 = (char *)*v9;
          if ( v11 > 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v20 + 9) - *((_QWORD *)v20 + 7)) >> 2) )
          {
            std::vector<CProcessingModeParameters::AudioEffectState>::_Clear_and_reserve_geometric(v20 + 56, v11);
            v22 = (char *)*v9;
            v23 = 20 * v11;
            memmove_0(*v9, Src, v23);
            v17 = &v22[v23];
          }
          else
          {
            v13 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v20 + 8) - (_QWORD)v12) >> 2);
            v14 = v10;
            v15 = *v9;
            if ( v11 > v13 )
            {
              memmove_0(v15, v14, 4 * ((__int64)(*((_QWORD *)v20 + 8) - (_QWORD)v12) >> 2));
              v12 = (char *)*((_QWORD *)v20 + 8);
              v16 = 20 * (v11 - v13);
              memmove_0(v12, (char *)Src + 20 * v13, v16);
            }
            else
            {
              v16 = 20 * v11;
              memmove_0(v15, v14, v16);
            }
            v17 = &v12[v16];
            v2 = v27;
          }
          *((_QWORD *)v20 + 8) = v17;
        }
        v20[88] = *((_BYTE *)this + 88);
        if ( *((_QWORD *)this + 10) )
        {
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&Src);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            v20 + 80,
            &Src);
          if ( Src )
            CoTaskMemFree(Src);
        }
        else
        {
          v18 = (void *)*((_QWORD *)v20 + 10);
          if ( v18 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
            CoTaskMemFree(v18);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
          }
          *((_QWORD *)v20 + 10) = 0;
        }
        *v2 = (struct StreamGroupParams *)v20;
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"avcore\\audiocore\\server\\AudioSrv\\inc\\CoreAudioInterfacesP.h",
          (const char *)0x8007000ELL,
          v24);
        std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v29);
        CoTaskMemFree(v7);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
        return 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"avcore\\audiocore\\server\\AudioSrv\\inc\\CoreAudioInterfacesP.h",
        (const char *)0x8007000ELL,
        v24);
      CoTaskMemFree(v4);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"avcore\\audiocore\\server\\AudioSrv\\inc\\CoreAudioInterfacesP.h",
      (const char *)0x8007000ELL,
      v24);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000dbd0  mov     [rsp+arg_8], rdx
0x18000dbd5  push    rbx
0x18000dbd6  push    rsi
0x18000dbd7  push    rdi
0x18000dbd8  push    r12
0x18000dbda  push    r13
0x18000dbdc  push    r14
0x18000dbde  push    r15
0x18000dbe0  sub     rsp, 30h
0x18000dbe4  mov     r13, rdx
0x18000dbe7  mov     r12, rcx
0x18000dbea  xor     r15d, r15d
0x18000dbed  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18000dbf1  mov     rdx, [rcx]; unsigned __int16 *
0x18000dbf4  lea     rcx, [rsp+68h+pv]; this
0x18000dbf9  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18000dbfe  nop
0x18000dbff  mov     rsi, [rsp+68h+pv]
0x18000dc04  test    rsi, rsi
0x18000dc07  jz      short loc_18000DC57
0x18000dc09  mov     rax, [r12+10h]
0x18000dc0e  movzx   ebx, word ptr [rax+10h]
0x18000dc12  lea     rcx, [rbx+12h]; cb
0x18000dc16  call    cs:__imp_CoTaskMemAlloc
0x18000dc1c  mov     rdi, rax
0x18000dc1f  test    rax, rax
0x18000dc22  jnz     loc_18000DDA8
0x18000dc28  mov     rcx, [rsp+68h]; this
0x18000dc2d  mov     ebx, 8007000Eh
0x18000dc32  mov     r9d, ebx; char *
0x18000dc35  lea     r8, aAvcoreAudiocor_47; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000dc3c  mov     edx, 0BAh; void *
0x18000dc41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc46  nop
0x18000dc47  mov     rcx, rsi; pv
0x18000dc4a  call    cs:__imp_CoTaskMemFree
0x18000dc50  mov     eax, ebx
0x18000dc52  jmp     loc_18000DD98
0x18000dc57  mov     rcx, [rsp+68h]; this
0x18000dc5c  mov     ebx, 8007000Eh
0x18000dc61  mov     r9d, ebx; char *
0x18000dc64  lea     r8, aAvcoreAudiocor_47; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000dc6b  mov     edx, 0B6h; void *
0x18000dc70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc75  nop
0x18000dc76  mov     eax, ebx
0x18000dc78  jmp     loc_18000DD98
0x18000dc7d  mov     [rsp+68h+pv], r15
0x18000dc82  mov     rcx, [r14]; pv
0x18000dc85  call    cs:__imp_CoTaskMemFree
0x18000dc8b  mov     [r14], rsi
0x18000dc8e  mov     al, [r12+31h]
0x18000dc93  mov     [r14+31h], al
0x18000dc97  mov     qword ptr [rsp+68h+var_48], r15
0x18000dc9c  mov     rcx, [r14+10h]; pv
0x18000dca0  call    cs:__imp_CoTaskMemFree
0x18000dca6  mov     [r14+10h], rdi
0x18000dcaa  mov     rax, [r12+18h]
0x18000dcaf  mov     [r14+18h], rax
0x18000dcb3  movups  xmm0, xmmword ptr [r12+20h]
0x18000dcb9  movdqu  xmmword ptr [r14+20h], xmm0
0x18000dcbf  mov     al, [r12+30h]
0x18000dcc4  mov     [r14+30h], al
0x18000dcc8  mov     al, [r12+32h]
0x18000dccd  mov     [r14+32h], al
0x18000dcd1  mov     eax, [r12+8]
0x18000dcd6  mov     [r14+8], eax
0x18000dcda  lea     rbx, [r12+38h]
0x18000dcdf  lea     r15, [r14+38h]
0x18000dce3  cmp     r15, rbx
0x18000dce6  jz      short loc_18000DD66
0x18000dce8  mov     rcx, [rbx]
0x18000dceb  mov     [rsp+68h+Src], rcx
0x18000dcf3  mov     rbx, [rbx+8]
0x18000dcf7  sub     rbx, rcx
0x18000dcfa  sar     rbx, 2
0x18000dcfe  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18000dd08  imul    rbx, rdx
0x18000dd0c  mov     rdi, [r15]
0x18000dd0f  mov     rax, [r15+10h]
0x18000dd13  sub     rax, rdi
0x18000dd16  sar     rax, 2
0x18000dd1a  imul    rax, rdx
0x18000dd1e  cmp     rbx, rax
0x18000dd21  ja      loc_18000DE5E
0x18000dd27  mov     r13, [r15+8]
0x18000dd2b  sub     r13, rdi
0x18000dd2e  sar     r13, 2
0x18000dd32  imul    r13, rdx
0x18000dd36  mov     rdx, rcx; Src
0x18000dd39  mov     rcx, rdi; void *
0x18000dd3c  cmp     rbx, r13
0x18000dd3f  ja      loc_18000DED6
0x18000dd45  lea     rax, [rbx+rbx*4]
0x18000dd49  lea     rbx, ds:0[rax*4]
0x18000dd51  mov     r8, rbx; Size
0x18000dd54  call    memmove_0
0x18000dd59  lea     rax, [rdi+rbx]
0x18000dd5d  mov     r13, [rsp+68h+arg_8]
0x18000dd62  mov     [r15+8], rax
0x18000dd66  mov     al, [r12+58h]
0x18000dd6b  mov     [r15+20h], al
0x18000dd6f  mov     rdx, [r12+50h]
0x18000dd74  test    rdx, rdx
0x18000dd77  jnz     loc_18000DE94
0x18000dd7d  mov     rbx, [r15+18h]
0x18000dd81  test    rbx, rbx
0x18000dd84  jnz     loc_18000DF23
0x18000dd8a  mov     qword ptr [r15+18h], 0
0x18000dd92  mov     [r13+0], r14
0x18000dd96  xor     eax, eax
0x18000dd98  add     rsp, 30h
0x18000dd9c  pop     r15
0x18000dd9e  pop     r14
0x18000dda0  pop     r13
0x18000dda2  pop     r12
0x18000dda4  pop     rdi
0x18000dda5  pop     rsi
0x18000dda6  pop     rbx
0x18000dda7  retn
0x18000dda8  lea     r8, [rbx+12h]; Size
0x18000ddac  mov     rdx, [r12+10h]; Src
0x18000ddb1  mov     rcx, rdi; void *
0x18000ddb4  call    memcpy_0
0x18000ddb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ddc0  mov     ebx, 60h ; '`'
0x18000ddc5  mov     ecx, ebx; unsigned __int64
0x18000ddc7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ddcc  mov     r14, rax
0x18000ddcf  mov     [rsp+68h+Src], rax
0x18000ddd7  test    rax, rax
0x18000ddda  jz      loc_18000DECE
0x18000dde0  mov     r8d, ebx; Size
0x18000dde3  xor     edx, edx; Val
0x18000dde5  mov     rcx, rax; void *
0x18000dde8  call    memset_0
0x18000dded  mov     [r14], r15
0x18000ddf0  mov     [r14+10h], r15
0x18000ddf4  lea     rcx, [r14+38h]; void *
0x18000ddf8  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18000ddfd  mov     [rcx+18h], r15
0x18000de01  mov     [rcx+20h], r15b
0x18000de05  mov     [rsp+68h+arg_18], r14
0x18000de0d  test    r14, r14
0x18000de10  jnz     loc_18000DC7D
0x18000de16  mov     rcx, [rsp+68h]; this
0x18000de1b  mov     ebx, 8007000Eh
0x18000de20  mov     r9d, ebx; char *
0x18000de23  lea     r8, aAvcoreAudiocor_47; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000de2a  mov     edx, 0BEh; void *
0x18000de2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de34  nop
0x18000de35  lea     rcx, [rsp+68h+arg_18]
0x18000de3d  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x18000de42  nop
0x18000de43  mov     rcx, rdi; pv
0x18000de46  call    cs:__imp_CoTaskMemFree
0x18000de4c  nop
0x18000de4d  lea     rcx, [rsp+68h+pv]
0x18000de52  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000de57  mov     eax, ebx
0x18000de59  jmp     loc_18000DD98
0x18000de5e  mov     rdx, rbx
0x18000de61  mov     rcx, r15
0x18000de64  call    ?_Clear_and_reserve_geometric@?$vector@UAudioEffectState@CProcessingModeParameters@@V?$allocator@UAudioEffectState@CProcessingModeParameters@@@std@@@std@@AEAAX_K@Z; std::vector<CProcessingModeParameters::AudioEffectState>::_Clear_and_reserve_geometric(unsigned __int64)
0x18000de69  mov     rdi, [r15]
0x18000de6c  lea     rax, [rbx+rbx*4]
0x18000de70  lea     rbx, ds:0[rax*4]
0x18000de78  mov     r8, rbx; Size
0x18000de7b  mov     rdx, [rsp+68h+Src]; Src
0x18000de83  mov     rcx, rdi; void *
0x18000de86  call    memmove_0
0x18000de8b  lea     rax, [rbx+rdi]
0x18000de8f  jmp     loc_18000DD62
0x18000de94  lea     rcx, [rsp+68h+Src]
0x18000de9c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000dea1  lea     rcx, [r15+18h]
0x18000dea5  lea     rdx, [rsp+68h+Src]
0x18000dead  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000deb2  mov     rcx, [rsp+68h+Src]; pv
0x18000deba  test    rcx, rcx
0x18000debd  jz      loc_18000DD92
0x18000dec3  call    cs:__imp_CoTaskMemFree
0x18000dec9  jmp     loc_18000DD92
0x18000dece  mov     r14, r15
0x18000ded1  jmp     loc_18000DE05
0x18000ded6  lea     rax, ds:0[r13*4]
0x18000dede  add     rax, r13
0x18000dee1  lea     rsi, ds:0[rax*4]
0x18000dee9  mov     r8, rsi; Size
0x18000deec  call    memmove_0
0x18000def1  mov     rdi, [r15+8]
0x18000def5  sub     rbx, r13
0x18000def8  lea     rax, [rbx+rbx*4]
0x18000defc  lea     rbx, ds:0[rax*4]
0x18000df04  mov     rdx, [rsp+68h+Src]
0x18000df0c  add     rdx, rsi; Src
0x18000df0f  mov     r8, rbx; Size
0x18000df12  mov     rcx, rdi; void *
0x18000df15  call    memmove_0
0x18000df1a  lea     rax, [rbx+rdi]
0x18000df1e  jmp     loc_18000DD5D
0x18000df23  lea     rcx, [rsp+68h+pv]; this
0x18000df28  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000df2d  mov     rcx, rbx; pv
0x18000df30  call    cs:__imp_CoTaskMemFree
0x18000df36  lea     rcx, [rsp+68h+pv]; this
0x18000df3b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000df40  jmp     loc_18000DD8A
0x18000df45  mov     eax, dword ptr [rsp+68h+pv]
0x18000df49  jmp     loc_18000DD98
```
