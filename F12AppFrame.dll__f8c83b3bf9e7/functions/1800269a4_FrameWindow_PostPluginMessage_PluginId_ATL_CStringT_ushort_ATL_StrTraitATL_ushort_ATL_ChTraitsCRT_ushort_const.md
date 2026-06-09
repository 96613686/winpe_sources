# FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>,std::default_delete<std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>>>)

- ea: `0x1800269a4`
- end: `0x180026c33`
- name: `?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022204`
- `0x180023660`
- `0x180024d00`
- `0x180024fa8`
- `0x1800256c0`
- `0x180025cac`
- `0x1800264a8`
- `0x180027df8`
- `0x180028534`
- `0x180029310`

## callees

- `0x180001900`
- `0x18000193c`
- `0x180002d44`
- `0x1800031a4`
- `0x180006a20`
- `0x18001e3f0`
- `0x18001fb24`
- `0x180020528`
- `0x180020628`
- `0x180022f44`
- `0x1800269a4`
- `0x18002c5e0`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void FrameWindow::PostPluginMessage(__int64 a1, unsigned int a2, __int64 *a3, ...)
{
  __int64 *v3; // r15
  _QWORD *v6; // r14
  __int64 v7; // rcx
  void *v8; // rdi
  signed int v9; // edx
  __int64 v10; // rbx
  __int64 *v11; // rax
  __int64 *v12; // r8
  __int64 *v13; // rax
  __int64 *v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  void *v18; // rbx
  _QWORD *v19; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v20; // [rsp+28h] [rbp-48h] BYREF
  void *v21; // [rsp+30h] [rbp-40h]
  __int128 v22; // [rsp+38h] [rbp-38h] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h]
  unsigned int v24; // [rsp+A8h] [rbp+38h] BYREF
  __int64 *v25; // [rsp+B8h] [rbp+48h] BYREF
  va_list va; // [rsp+B8h] [rbp+48h]
  va_list va1; // [rsp+C0h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v25 = va_arg(va1, __int64 *);
  v24 = a2;
  v3 = v25;
  v6 = operator new(0x18u);
  v19 = v6;
  *(_DWORD *)v6 = v24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v6 + 1,
    a3);
  v7 = *v3;
  *v3 = 0;
  v6[2] = v7;
  v8 = operator new(0x18u);
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count<PluginPendingMessage>::`vftable';
  *((_QWORD *)v8 + 2) = v6;
  v20 = v6;
  v21 = v8;
  v19 = 0;
  std::_Temporary_owner<PluginPendingMessage>::~_Temporary_owner<PluginPendingMessage>(&v19);
  if ( (unsigned __int8)FrameWindow::IsPluginLoaded(a1, v24) )
  {
    if ( *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                                 (__int64 *)(a1 + 448),
                                 (int *)&v24)
                  + 24LL) )
    {
      v10 = **(_QWORD **)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                           (__int64 *)(a1 + 448),
                           (int *)&v24);
      v11 = (__int64 *)operator new(0x20u);
      v25 = v11;
      *((_DWORD *)v11 + 2) = 18;
      *((_DWORD *)v11 + 3) = -1;
      *v11 = (__int64)&PluginMessageFireJsonMessageEvent::`vftable';
      v11[2] = 0;
      v11[3] = 0;
      _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
      v11[2] = (__int64)v6;
      v11[3] = (__int64)v8;
      v25 = v11;
      BrowserToolThread::PostPluginMessage(v10, (__int64 **)va);
      if ( v25 )
        (*(void (__fastcall **)(__int64 *, __int64))*v25)(v25, 1);
      goto LABEL_20;
    }
    v9 = v24;
  }
  v12 = *(__int64 **)(a1 + 464);
  v13 = (__int64 *)v12[1];
  v14 = v12;
  while ( !*((_BYTE *)v13 + 25) )
  {
    if ( *((_DWORD *)v13 + 8) >= v9 )
    {
      v14 = v13;
      v13 = (__int64 *)*v13;
    }
    else
    {
      v13 = (__int64 *)v13[2];
    }
  }
  if ( *((_BYTE *)v14 + 25) || v9 < *((_DWORD *)v14 + 8) || v14 == v12 )
  {
    v22 = 0;
    v23 = 0;
    v15 = std::map<enum PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>>::operator[](
            (__int64 *)(a1 + 464),
            &v24);
    if ( (__int128 *)v15 != &v22 )
    {
      std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy((char **)v15);
      *(_QWORD *)v15 = 0;
      *(_QWORD *)(v15 + 8) = 0;
      *(_QWORD *)(v15 + 16) = 0;
      v22 = 0;
      v23 = 0;
    }
    std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy((char **)&v22);
  }
  v16 = std::map<enum PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>>::operator[](
          (__int64 *)(a1 + 464),
          &v24);
  v17 = *(_QWORD *)(v16 + 8);
  if ( v17 == *(_QWORD *)(v16 + 16) )
  {
    std::vector<std::shared_ptr<PluginPendingMessage>>::_Emplace_reallocate<std::shared_ptr<PluginPendingMessage> const &>(
      (char **)v16,
      (char *)v17,
      &v20);
    v8 = v21;
  }
  else
  {
    *(_QWORD *)v17 = 0;
    *(_QWORD *)(v17 + 8) = 0;
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
    *(_QWORD *)v17 = v6;
    *(_QWORD *)(v17 + 8) = v8;
    *(_QWORD *)(v16 + 8) += 16LL;
  }
LABEL_20:
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v8)(v8);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v18 = (void *)*v3;
  if ( *v3 )
  {
    std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(*v3);
    operator delete(v18);
  }
}

```

## disassembly

```asm
0x1800269a4  mov     rax, rsp
0x1800269a7  mov     [rax+8], rbx
0x1800269ab  mov     [rax+18h], rsi
0x1800269af  mov     [rax+20h], r9
0x1800269b3  mov     [rax+10h], edx
0x1800269b6  push    rbp
0x1800269b7  push    rdi
0x1800269b8  push    r12
0x1800269ba  push    r14
0x1800269bc  push    r15
0x1800269be  mov     rbp, rsp
0x1800269c1  sub     rsp, 70h
0x1800269c5  mov     r15, r9
0x1800269c8  mov     rbx, r8
0x1800269cb  mov     rsi, rcx
0x1800269ce  mov     edi, 18h
0x1800269d3  mov     ecx, edi; Size
0x1800269d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800269da  mov     r14, rax
0x1800269dd  mov     [rbp+var_50], rax
0x1800269e1  mov     edx, [rbp+arg_8]
0x1800269e4  mov     [rax], edx
0x1800269e6  lea     rcx, [rax+8]
0x1800269ea  mov     rdx, rbx
0x1800269ed  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800269f2  mov     rcx, [r15]
0x1800269f5  xor     r12d, r12d
0x1800269f8  mov     [r15], r12
0x1800269fb  mov     [r14+10h], rcx
0x1800269ff  mov     [rbp+var_50], r14
0x180026a03  mov     ecx, edi; Size
0x180026a05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026a0a  mov     rdi, rax
0x180026a0d  mov     [rbp+var_50], rax
0x180026a11  xorps   xmm0, xmm0
0x180026a14  movups  xmmword ptr [rax], xmm0
0x180026a17  lea     eax, [r12+1]
0x180026a1c  mov     [rdi+8], eax
0x180026a1f  mov     [rdi+0Ch], eax
0x180026a22  lea     rax, ??_7?$_Ref_count@UPluginPendingMessage@@@std@@6B@; const std::_Ref_count<PluginPendingMessage>::`vftable'
0x180026a29  mov     [rdi], rax
0x180026a2c  mov     [rdi+10h], r14
0x180026a30  mov     [rbp+var_48], r14
0x180026a34  mov     [rbp+var_40], rdi
0x180026a38  mov     [rbp+var_50], r12
0x180026a3c  lea     rcx, [rbp+var_50]
0x180026a40  call    ??1?$_Temporary_owner@UPluginPendingMessage@@@std@@QEAA@XZ; std::_Temporary_owner<PluginPendingMessage>::~_Temporary_owner<PluginPendingMessage>(void)
0x180026a45  nop
0x180026a46  mov     edx, [rbp+arg_8]
0x180026a49  mov     rcx, rsi
0x180026a4c  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x180026a51  test    al, al
0x180026a53  jz      loc_180026AF6
0x180026a59  lea     rbx, [rsi+1C0h]
0x180026a60  lea     rdx, [rbp+arg_8]
0x180026a64  mov     rcx, rbx
0x180026a67  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180026a6c  mov     rdx, [rax]
0x180026a6f  cmp     [rdx+18h], r12b
0x180026a73  jz      short loc_180026AF3
0x180026a75  lea     rdx, [rbp+arg_8]
0x180026a79  mov     rcx, rbx
0x180026a7c  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180026a81  mov     rcx, [rax]
0x180026a84  mov     rbx, [rcx]
0x180026a87  lea     ecx, [r12+20h]; Size
0x180026a8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026a91  mov     [rbp+arg_18], rax
0x180026a95  mov     dword ptr [rax+8], 12h
0x180026a9c  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x180026aa3  lea     rcx, ??_7PluginMessageFireJsonMessageEvent@@6B@; const PluginMessageFireJsonMessageEvent::`vftable'
0x180026aaa  mov     [rax], rcx
0x180026aad  mov     [rax+10h], r12
0x180026ab1  mov     [rax+18h], r12
0x180026ab5  lock inc dword ptr [rdi+8]
0x180026ab9  mov     [rax+10h], r14
0x180026abd  mov     [rax+18h], rdi
0x180026ac1  mov     [rbp+arg_18], rax
0x180026ac5  lea     rdx, [rbp+arg_18]
0x180026ac9  mov     rcx, rbx
0x180026acc  call    ?PostPluginMessage@BrowserToolThread@@QEBAJ$$QEAV?$unique_ptr@UPluginMessageInfo@@U?$default_delete@UPluginMessageInfo@@@std@@@std@@@Z; BrowserToolThread::PostPluginMessage(std::unique_ptr<PluginMessageInfo> &&)
0x180026ad1  mov     rcx, [rbp+arg_18]
0x180026ad5  test    rcx, rcx
0x180026ad8  jz      loc_180026BC0
0x180026ade  mov     rax, [rcx]
0x180026ae1  lea     edx, [r12+1]
0x180026ae6  mov     rax, [rax]
0x180026ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aee  jmp     loc_180026BC0
0x180026af3  mov     edx, [rbp+arg_8]
0x180026af6  mov     r8, [rsi+1D0h]
0x180026afd  mov     rax, [r8+8]
0x180026b01  mov     rcx, r8
0x180026b04  jmp     short loc_180026B17
0x180026b06  cmp     [rax+20h], edx
0x180026b09  jge     short loc_180026B11
0x180026b0b  mov     rax, [rax+10h]
0x180026b0f  jmp     short loc_180026B17
0x180026b11  mov     rcx, rax
0x180026b14  mov     rax, [rax]
0x180026b17  cmp     [rax+19h], r12b
0x180026b1b  jz      short loc_180026B06
0x180026b1d  cmp     [rcx+19h], r12b
0x180026b21  jnz     short loc_180026B2D
0x180026b23  cmp     edx, [rcx+20h]
0x180026b26  jl      short loc_180026B2D
0x180026b28  cmp     rcx, r8
0x180026b2b  jnz     short loc_180026B7D
0x180026b2d  xorps   xmm0, xmm0
0x180026b30  movdqu  [rbp+var_38], xmm0
0x180026b35  mov     [rbp+var_28], r12
0x180026b39  lea     rdx, [rbp+arg_8]
0x180026b3d  lea     rcx, [rsi+1D0h]
0x180026b44  call    ??A?$map@W4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@3@@std@@QEAAAEAV?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>>::operator[](PluginId const &)
0x180026b49  mov     rbx, rax
0x180026b4c  lea     rax, [rbp+var_38]
0x180026b50  cmp     rbx, rax
0x180026b53  jz      short loc_180026B74
0x180026b55  mov     rcx, rbx
0x180026b58  call    ?_Tidy@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy(void)
0x180026b5d  mov     [rbx], r12
0x180026b60  mov     [rbx+8], r12
0x180026b64  mov     [rbx+10h], r12
0x180026b68  xorps   xmm0, xmm0
0x180026b6b  movdqu  [rbp+var_38], xmm0
0x180026b70  mov     [rbp+var_28], r12
0x180026b74  lea     rcx, [rbp+var_38]
0x180026b78  call    ?_Tidy@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy(void)
0x180026b7d  lea     rdx, [rbp+arg_8]
0x180026b81  lea     rcx, [rsi+1D0h]
0x180026b88  call    ??A?$map@W4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@3@@std@@QEAAAEAV?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::vector<std::shared_ptr<PluginPendingMessage>>>::operator[](PluginId const &)
0x180026b8d  mov     rdx, [rax+8]
0x180026b91  cmp     rdx, [rax+10h]
0x180026b95  jz      short loc_180026BB0
0x180026b97  mov     [rdx], r12
0x180026b9a  mov     [rdx+8], r12
0x180026b9e  lock inc dword ptr [rdi+8]
0x180026ba2  mov     [rdx], r14
0x180026ba5  mov     [rdx+8], rdi
0x180026ba9  add     qword ptr [rax+8], 10h
0x180026bae  jmp     short loc_180026BC0
0x180026bb0  lea     r8, [rbp+var_48]
0x180026bb4  mov     rcx, rax
0x180026bb7  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UPluginPendingMessage@@@std@@@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UPluginPendingMessage@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PluginPendingMessage>>::_Emplace_reallocate<std::shared_ptr<PluginPendingMessage> const &>(std::shared_ptr<PluginPendingMessage> * const,std::shared_ptr<PluginPendingMessage> const &)
0x180026bbc  mov     rdi, [rbp+var_40]
0x180026bc0  test    rdi, rdi
0x180026bc3  jz      short loc_180026BFD
0x180026bc5  or      eax, 0FFFFFFFFh
0x180026bc8  lock xadd [rdi+8], eax
0x180026bcd  cmp     eax, 1
0x180026bd0  jnz     short loc_180026BFD
0x180026bd2  mov     rax, [rdi]
0x180026bd5  mov     rcx, rdi
0x180026bd8  mov     rax, [rax]
0x180026bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026be0  or      eax, 0FFFFFFFFh
0x180026be3  lock xadd [rdi+0Ch], eax
0x180026be8  cmp     eax, 1
0x180026beb  jnz     short loc_180026BFD
0x180026bed  mov     rax, [rdi]
0x180026bf0  mov     rcx, rdi
0x180026bf3  mov     rax, [rax+8]
0x180026bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bfc  nop
0x180026bfd  mov     rbx, [r15]
0x180026c00  test    rbx, rbx
0x180026c03  jz      short loc_180026C1A
0x180026c05  mov     rcx, rbx
0x180026c08  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x180026c0d  mov     edx, 18h
0x180026c12  mov     rcx, rbx; Block
0x180026c15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026c1a  lea     r11, [rsp+70h+var_s0]
0x180026c1f  mov     rbx, [r11+30h]
0x180026c23  mov     rsi, [r11+40h]
0x180026c27  mov     rsp, r11
0x180026c2a  pop     r15
0x180026c2c  pop     r14
0x180026c2e  pop     r12
0x180026c30  pop     rdi
0x180026c31  pop     rbp
0x180026c32  retn
```
