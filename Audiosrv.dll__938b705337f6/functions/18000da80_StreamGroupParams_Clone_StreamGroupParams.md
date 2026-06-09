# StreamGroupParams::Clone(StreamGroupParams * *)

- ea: `0x18000da80`
- end: `0x18000ddfe`
- name: `?Clone@StreamGroupParams@@QEBAJPEAPEAU1@@Z`
- size: `894`
- prototype: `__int64 __fastcall(StreamGroupParams *__hidden this, struct StreamGroupParams **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d570`

## callees

- `0x18000af70`
- `0x18000da80`
- `0x18000de04`
- `0x18000e134`
- `0x18000e154`
- `0x18000e324`
- `0x1800126bc`
- `0x1800512b8`
- `0x18005286c`
- `0x1800551a8`
- `0x1800a93a4`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d0758`
- `0x1800d0764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dde0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dde0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x18000da80  mov     [rsp+arg_8], rdx
0x18000da85  push    rbx
0x18000da86  push    rsi
0x18000da87  push    rdi
0x18000da88  push    r12
0x18000da8a  push    r13
0x18000da8c  push    r14
0x18000da8e  push    r15
0x18000da90  sub     rsp, 30h
0x18000da94  mov     r13, rdx
0x18000da97  mov     r12, rcx
0x18000da9a  xor     r15d, r15d
0x18000da9d  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18000daa1  mov     rdx, [rcx]; unsigned __int16 *
0x18000daa4  lea     rcx, [rsp+68h+pv]; this
0x18000daa9  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18000daae  nop
0x18000daaf  mov     rsi, [rsp+68h+pv]
0x18000dab4  test    rsi, rsi
0x18000dab7  jz      short loc_18000DB07
0x18000dab9  mov     rax, [r12+10h]
0x18000dabe  movzx   ebx, word ptr [rax+10h]
0x18000dac2  lea     rcx, [rbx+12h]; cb
0x18000dac6  call    cs:__imp_CoTaskMemAlloc
0x18000dacc  mov     rdi, rax
0x18000dacf  test    rax, rax
0x18000dad2  jnz     loc_18000DC58
0x18000dad8  mov     rcx, [rsp+68h]; this
0x18000dadd  mov     ebx, 8007000Eh
0x18000dae2  mov     r9d, ebx; char *
0x18000dae5  lea     r8, aAvcoreAudiocor_46; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000daec  mov     edx, 0BAh; void *
0x18000daf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000daf6  nop
0x18000daf7  mov     rcx, rsi; pv
0x18000dafa  call    cs:__imp_CoTaskMemFree
0x18000db00  mov     eax, ebx
0x18000db02  jmp     loc_18000DC48
0x18000db07  mov     rcx, [rsp+68h]; this
0x18000db0c  mov     ebx, 8007000Eh
0x18000db11  mov     r9d, ebx; char *
0x18000db14  lea     r8, aAvcoreAudiocor_46; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000db1b  mov     edx, 0B6h; void *
0x18000db20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db25  nop
0x18000db26  mov     eax, ebx
0x18000db28  jmp     loc_18000DC48
0x18000db2d  mov     [rsp+68h+pv], r15
0x18000db32  mov     rcx, [r14]; pv
0x18000db35  call    cs:__imp_CoTaskMemFree
0x18000db3b  mov     [r14], rsi
0x18000db3e  mov     al, [r12+31h]
0x18000db43  mov     [r14+31h], al
0x18000db47  mov     qword ptr [rsp+68h+var_48], r15
0x18000db4c  mov     rcx, [r14+10h]; pv
0x18000db50  call    cs:__imp_CoTaskMemFree
0x18000db56  mov     [r14+10h], rdi
0x18000db5a  mov     rax, [r12+18h]
0x18000db5f  mov     [r14+18h], rax
0x18000db63  movups  xmm0, xmmword ptr [r12+20h]
0x18000db69  movdqu  xmmword ptr [r14+20h], xmm0
0x18000db6f  mov     al, [r12+30h]
0x18000db74  mov     [r14+30h], al
0x18000db78  mov     al, [r12+32h]
0x18000db7d  mov     [r14+32h], al
0x18000db81  mov     eax, [r12+8]
0x18000db86  mov     [r14+8], eax
0x18000db8a  lea     rbx, [r12+38h]
0x18000db8f  lea     r15, [r14+38h]
0x18000db93  cmp     r15, rbx
0x18000db96  jz      short loc_18000DC16
0x18000db98  mov     rcx, [rbx]
0x18000db9b  mov     [rsp+68h+Src], rcx
0x18000dba3  mov     rbx, [rbx+8]
0x18000dba7  sub     rbx, rcx
0x18000dbaa  sar     rbx, 2
0x18000dbae  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18000dbb8  imul    rbx, rdx
0x18000dbbc  mov     rdi, [r15]
0x18000dbbf  mov     rax, [r15+10h]
0x18000dbc3  sub     rax, rdi
0x18000dbc6  sar     rax, 2
0x18000dbca  imul    rax, rdx
0x18000dbce  cmp     rbx, rax
0x18000dbd1  ja      loc_18000DD0E
0x18000dbd7  mov     r13, [r15+8]
0x18000dbdb  sub     r13, rdi
0x18000dbde  sar     r13, 2
0x18000dbe2  imul    r13, rdx
0x18000dbe6  mov     rdx, rcx; Src
0x18000dbe9  mov     rcx, rdi; void *
0x18000dbec  cmp     rbx, r13
0x18000dbef  ja      loc_18000DD86
0x18000dbf5  lea     rax, [rbx+rbx*4]
0x18000dbf9  lea     rbx, ds:0[rax*4]
0x18000dc01  mov     r8, rbx; Size
0x18000dc04  call    memmove_0
0x18000dc09  lea     rax, [rdi+rbx]
0x18000dc0d  mov     r13, [rsp+68h+arg_8]
0x18000dc12  mov     [r15+8], rax
0x18000dc16  mov     al, [r12+58h]
0x18000dc1b  mov     [r15+20h], al
0x18000dc1f  mov     rdx, [r12+50h]
0x18000dc24  test    rdx, rdx
0x18000dc27  jnz     loc_18000DD44
0x18000dc2d  mov     rbx, [r15+18h]
0x18000dc31  test    rbx, rbx
0x18000dc34  jnz     loc_18000DDD3
0x18000dc3a  mov     qword ptr [r15+18h], 0
0x18000dc42  mov     [r13+0], r14
0x18000dc46  xor     eax, eax
0x18000dc48  add     rsp, 30h
0x18000dc4c  pop     r15
0x18000dc4e  pop     r14
0x18000dc50  pop     r13
0x18000dc52  pop     r12
0x18000dc54  pop     rdi
0x18000dc55  pop     rsi
0x18000dc56  pop     rbx
0x18000dc57  retn
0x18000dc58  lea     r8, [rbx+12h]; Size
0x18000dc5c  mov     rdx, [r12+10h]; Src
0x18000dc61  mov     rcx, rdi; void *
0x18000dc64  call    memcpy_0
0x18000dc69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dc70  mov     ebx, 60h ; '`'
0x18000dc75  mov     ecx, ebx; unsigned __int64
0x18000dc77  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000dc7c  mov     r14, rax
0x18000dc7f  mov     [rsp+68h+Src], rax
0x18000dc87  test    rax, rax
0x18000dc8a  jz      loc_18000DD7E
0x18000dc90  mov     r8d, ebx; Size
0x18000dc93  xor     edx, edx; Val
0x18000dc95  mov     rcx, rax; void *
0x18000dc98  call    memset_0
0x18000dc9d  mov     [r14], r15
0x18000dca0  mov     [r14+10h], r15
0x18000dca4  lea     rcx, [r14+38h]; void *
0x18000dca8  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18000dcad  mov     [rcx+18h], r15
0x18000dcb1  mov     [rcx+20h], r15b
0x18000dcb5  mov     [rsp+68h+arg_18], r14
0x18000dcbd  test    r14, r14
0x18000dcc0  jnz     loc_18000DB2D
0x18000dcc6  mov     rcx, [rsp+68h]; this
0x18000dccb  mov     ebx, 8007000Eh
0x18000dcd0  mov     r9d, ebx; char *
0x18000dcd3  lea     r8, aAvcoreAudiocor_46; "avcore\\audiocore\\server\\AudioSrv\\in"...
0x18000dcda  mov     edx, 0BEh; void *
0x18000dcdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dce4  nop
0x18000dce5  lea     rcx, [rsp+68h+arg_18]
0x18000dced  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x18000dcf2  nop
0x18000dcf3  mov     rcx, rdi; pv
0x18000dcf6  call    cs:__imp_CoTaskMemFree
0x18000dcfc  nop
0x18000dcfd  lea     rcx, [rsp+68h+pv]
0x18000dd02  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000dd07  mov     eax, ebx
0x18000dd09  jmp     loc_18000DC48
0x18000dd0e  mov     rdx, rbx
0x18000dd11  mov     rcx, r15
0x18000dd14  call    ?_Clear_and_reserve_geometric@?$vector@UAudioEffectState@CProcessingModeParameters@@V?$allocator@UAudioEffectState@CProcessingModeParameters@@@std@@@std@@AEAAX_K@Z; std::vector<CProcessingModeParameters::AudioEffectState>::_Clear_and_reserve_geometric(unsigned __int64)
0x18000dd19  mov     rdi, [r15]
0x18000dd1c  lea     rax, [rbx+rbx*4]
0x18000dd20  lea     rbx, ds:0[rax*4]
0x18000dd28  mov     r8, rbx; Size
0x18000dd2b  mov     rdx, [rsp+68h+Src]; Src
0x18000dd33  mov     rcx, rdi; void *
0x18000dd36  call    memmove_0
0x18000dd3b  lea     rax, [rbx+rdi]
0x18000dd3f  jmp     loc_18000DC12
0x18000dd44  lea     rcx, [rsp+68h+Src]
0x18000dd4c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000dd51  lea     rcx, [r15+18h]
0x18000dd55  lea     rdx, [rsp+68h+Src]
0x18000dd5d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000dd62  mov     rcx, [rsp+68h+Src]; pv
0x18000dd6a  test    rcx, rcx
0x18000dd6d  jz      loc_18000DC42
0x18000dd73  call    cs:__imp_CoTaskMemFree
0x18000dd79  jmp     loc_18000DC42
0x18000dd7e  mov     r14, r15
0x18000dd81  jmp     loc_18000DCB5
0x18000dd86  lea     rax, ds:0[r13*4]
0x18000dd8e  add     rax, r13
0x18000dd91  lea     rsi, ds:0[rax*4]
0x18000dd99  mov     r8, rsi; Size
0x18000dd9c  call    memmove_0
0x18000dda1  mov     rdi, [r15+8]
0x18000dda5  sub     rbx, r13
0x18000dda8  lea     rax, [rbx+rbx*4]
0x18000ddac  lea     rbx, ds:0[rax*4]
0x18000ddb4  mov     rdx, [rsp+68h+Src]
0x18000ddbc  add     rdx, rsi; Src
0x18000ddbf  mov     r8, rbx; Size
0x18000ddc2  mov     rcx, rdi; void *
0x18000ddc5  call    memmove_0
0x18000ddca  lea     rax, [rbx+rdi]
0x18000ddce  jmp     loc_18000DC0D
0x18000ddd3  lea     rcx, [rsp+68h+pv]; this
0x18000ddd8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dddd  mov     rcx, rbx; pv
0x18000dde0  call    cs:__imp_CoTaskMemFree
0x18000dde6  lea     rcx, [rsp+68h+pv]; this
0x18000ddeb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ddf0  jmp     loc_18000DC3A
0x18000ddf5  mov     eax, dword ptr [rsp+68h+pv]
0x18000ddf9  jmp     loc_18000DC48
```
