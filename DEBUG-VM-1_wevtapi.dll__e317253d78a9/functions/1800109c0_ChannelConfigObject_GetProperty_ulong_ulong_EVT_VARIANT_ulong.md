# ChannelConfigObject::GetProperty(ulong,ulong,_EVT_VARIANT *,ulong &)

- ea: `0x1800109c0`
- end: `0x180010c0e`
- name: `?GetProperty@ChannelConfigObject@@UEAAKKKPEAU_EVT_VARIANT@@AEAK@Z`
- size: `590`
- prototype: `unsigned int __fastcall(ChannelConfigObject *__hidden this, unsigned int, unsigned int, struct _EVT_VARIANT *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800106b0`

## callees

- `0x18000a724`
- `0x18000c374`
- `0x1800109c0`
- `0x180010c20`
- `0x18001e4f4`
- `0x180023548`
- `0x180023ac8`
- `0x18002780c`
- `0x180028310`
- `0x180038fb4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010a50`
- `RPCRT4!NdrClientCall3` at `0x180010a50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall ChannelConfigObject::GetProperty(
        ChannelConfigObject *this,
        unsigned int a2,
        unsigned int a3,
        struct _EVT_VARIANT *a4,
        unsigned int *a5)
{
  unsigned int Pointer; // ebx
  __int64 v10; // rdx
  unsigned int v11; // ecx
  unsigned int i; // r14d
  __int64 v13; // r8
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // r15
  char v19; // bl
  __int64 v20; // [rsp+40h] [rbp-51h] BYREF
  __int64 v21; // [rsp+50h] [rbp-41h] BYREF
  __int64 v22; // [rsp+58h] [rbp-39h]
  __int64 v23; // [rsp+60h] [rbp-31h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-29h]
  int v25; // [rsp+6Ch] [rbp-25h]
  char v26; // [rsp+70h] [rbp-21h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-19h] BYREF
  __int64 v28; // [rsp+88h] [rbp-9h]
  int v29; // [rsp+90h] [rbp-1h]
  int v30; // [rsp+94h] [rbp+3h]
  int v31; // [rsp+98h] [rbp+7h]
  unsigned int v32; // [rsp+F8h] [rbp+67h] BYREF

  if ( a2 != 19 )
    return MetadataObject::GetProperty(this, a2, a3, a4, a5);
  if ( *((_BYTE *)this + 116) )
    goto LABEL_30;
  v20 = 0;
  v32 = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x17u,
                            0,
                            *(_QWORD *)(*((_QWORD *)this + 6) + 72LL),
                            *((_QWORD *)this + 7),
                            0,
                            &v32,
                            &v20).Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, Pointer);
    }
    return Pointer;
  }
  v10 = v20;
  v11 = v32;
  v23 = v20;
  v24 = v32;
  v25 = HIDWORD(v22);
  v26 = 1;
  for ( i = 0; i < v11; ++i )
  {
    v13 = *(_QWORD *)(v10 + 8LL * i);
    if ( !v13 )
      continue;
    v14 = (__int64 *)((char *)this + 88);
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v13 + 2 * v15) );
    v21 = *(_QWORD *)(v10 + 8LL * i);
    v22 = v15;
    v16 = MakeOrThrowOOM(&pExceptionObject, &v21);
    v17 = *((_QWORD *)this + 12);
    if ( v17 != *((_QWORD *)this + 13) )
      goto LABEL_20;
    v18 = *v14;
    if ( (unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow((char *)this + 88) )
    {
      v17 = *((_QWORD *)this + 12);
      if ( v16 - v18 < (unsigned __int64)(v17 - *((_QWORD *)this + 11)) )
        v16 = v16 - v18 + *v14;
LABEL_20:
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        v17,
        v16);
      *((_QWORD *)this + 12) += 32LL;
      v19 = 0;
      goto LABEL_21;
    }
    v19 = 1;
LABEL_21:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, 14);
      }
      pExceptionObject = 0;
      v28 = 0;
      v29 = 14;
      v30 = -1;
      v31 = 61;
      throw (EvtException *)&pExceptionObject;
    }
    v10 = v20;
    v11 = v32;
  }
  *((_BYTE *)this + 116) = 1;
  tlx::_UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___::__UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___(&v23);
LABEL_30:
  v21 = *((_QWORD *)this + 11);
  v22 = (*((_QWORD *)this + 12) - v21) >> 5;
  return MakeStringArrayVariant(&v21, a3, a4, a5);
}

```

## disassembly

```asm
0x1800109c0  push    rbp
0x1800109c2  push    rbx
0x1800109c3  push    rsi
0x1800109c4  push    rdi
0x1800109c5  push    r12
0x1800109c7  push    r13
0x1800109c9  push    r14
0x1800109cb  push    r15
0x1800109cd  lea     rbp, [rsp-17h]
0x1800109d2  sub     rsp, 0A8h
0x1800109d9  mov     r12, r9
0x1800109dc  mov     r13d, r8d
0x1800109df  mov     rdi, rcx
0x1800109e2  cmp     edx, 13h
0x1800109e5  jz      short loc_180010A09
0x1800109e7  mov     rax, [rbp+4Fh+arg_20]
0x1800109eb  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x1800109f0  call    ?GetProperty@MetadataObject@@UEAAKKKPEAU_EVT_VARIANT@@AEAK@Z; MetadataObject::GetProperty(ulong,ulong,_EVT_VARIANT *,ulong &)
0x1800109f5  add     rsp, 0A8h
0x1800109fc  pop     r15
0x1800109fe  pop     r14
0x180010a00  pop     r13
0x180010a02  pop     r12
0x180010a04  pop     rdi
0x180010a05  pop     rsi
0x180010a06  pop     rbx
0x180010a07  pop     rbp
0x180010a08  retn
0x180010a09  xor     esi, esi
0x180010a0b  cmp     [rcx+74h], sil
0x180010a0f  jnz     loc_180010BDF
0x180010a15  mov     [rbp+4Fh+var_A0], rsi
0x180010a19  mov     [rbp+4Fh+arg_8], esi
0x180010a1c  mov     r9, [rcx+30h]
0x180010a20  lea     rax, [rbp+4Fh+var_A0]
0x180010a24  mov     [rsp+0E0h+var_A8], rax
0x180010a29  lea     rax, [rbp+4Fh+arg_8]
0x180010a2d  mov     [rsp+0E0h+var_B0], rax
0x180010a32  mov     [rsp+0E0h+var_B8], esi
0x180010a36  mov     rax, [rcx+38h]
0x180010a3a  mov     [rsp+0E0h+var_C0], rax
0x180010a3f  mov     r9, [r9+48h]
0x180010a43  xor     r8d, r8d; pReturnValue
0x180010a46  lea     edx, [rsi+17h]; nProcNum
0x180010a49  lea     rcx, pProxyInfo; pProxyInfo
0x180010a50  call    cs:__imp_NdrClientCall3
0x180010a56  mov     rbx, rax
0x180010a59  test    eax, eax
0x180010a5b  jz      short loc_180010A9C
0x180010a5d  lea     rax, WPP_GLOBAL_Control
0x180010a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a6b  cmp     rcx, rax
0x180010a6e  jz      short loc_180010A95
0x180010a70  test    dword ptr [rcx+1Ch], 40000h
0x180010a77  jz      short loc_180010A95
0x180010a79  cmp     byte ptr [rcx+19h], 2
0x180010a7d  jb      short loc_180010A95
0x180010a7f  lea     edx, [rsi+0Bh]
0x180010a82  mov     r9d, ebx
0x180010a85  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x180010a8c  mov     rcx, [rcx+10h]
0x180010a90  call    WPP_SF_D
0x180010a95  mov     eax, ebx
0x180010a97  jmp     loc_1800109F5
0x180010a9c  mov     rdx, [rbp+4Fh+var_A0]
0x180010aa0  mov     ecx, [rbp+4Fh+arg_8]
0x180010aa3  mov     [rbp+4Fh+var_80], rdx
0x180010aa7  mov     [rbp+4Fh+var_78], ecx
0x180010aaa  mov     eax, [rbp+4Fh+var_84]
0x180010aad  mov     [rbp+4Fh+var_74], eax
0x180010ab0  mov     [rbp+4Fh+var_70], 1
0x180010ab4  mov     r14d, esi
0x180010ab7  cmp     r14d, ecx
0x180010aba  jnb     loc_180010BD2
0x180010ac0  mov     eax, r14d
0x180010ac3  mov     r8, [rdx+rax*8]
0x180010ac7  test    r8, r8
0x180010aca  jz      loc_180010B5B
0x180010ad0  lea     rbx, [rdi+58h]
0x180010ad4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ad8  inc     rax
0x180010adb  cmp     [r8+rax*2], si
0x180010ae0  jnz     short loc_180010AD8
0x180010ae2  mov     [rbp+4Fh+var_90], r8
0x180010ae6  mov     [rbp-39h], rax
0x180010aea  lea     rdx, [rbp+4Fh+var_90]
0x180010aee  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180010af2  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180010af7  mov     rsi, rax
0x180010afa  mov     rcx, [rbx+8]
0x180010afe  cmp     rcx, [rbx+10h]
0x180010b02  jnz     short loc_180010B35
0x180010b04  mov     r15, [rbx]
0x180010b07  mov     rcx, rbx
0x180010b0a  call    ?_Grow@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(void)
0x180010b0f  test    al, al
0x180010b11  jnz     short loc_180010B19
0x180010b13  mov     bl, 1
0x180010b15  xor     esi, esi
0x180010b17  jmp     short loc_180010B47
0x180010b19  mov     rdx, rsi
0x180010b1c  sub     rdx, r15
0x180010b1f  mov     rcx, [rbx+8]
0x180010b23  mov     r8, [rbx]
0x180010b26  mov     rax, rcx
0x180010b29  sub     rax, r8
0x180010b2c  cmp     rdx, rax
0x180010b2f  jnb     short loc_180010B35
0x180010b31  lea     rsi, [rdx+r8]
0x180010b35  mov     rdx, rsi
0x180010b38  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180010b3d  add     qword ptr [rbx+8], 20h ; ' '
0x180010b42  xor     esi, esi
0x180010b44  mov     bl, sil
0x180010b47  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180010b4b  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180010b50  test    bl, bl
0x180010b52  jnz     short loc_180010B63
0x180010b54  mov     rdx, [rbp+4Fh+var_A0]
0x180010b58  mov     ecx, [rbp+4Fh+arg_8]
0x180010b5b  inc     r14d
0x180010b5e  jmp     loc_180010AB7
0x180010b63  lea     rax, WPP_GLOBAL_Control
0x180010b6a  mov     ebx, 0Eh
0x180010b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b76  cmp     rcx, rax
0x180010b79  jz      short loc_180010BA0
0x180010b7b  test    dword ptr [rcx+1Ch], 40000h
0x180010b82  jz      short loc_180010BA0
0x180010b84  cmp     byte ptr [rcx+19h], 2
0x180010b88  jb      short loc_180010BA0
0x180010b8a  lea     edx, [rbx-2]
0x180010b8d  mov     r9d, ebx
0x180010b90  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x180010b97  mov     rcx, [rcx+10h]
0x180010b9b  call    WPP_SF_D
0x180010ba0  xorps   xmm0, xmm0
0x180010ba3  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x180010ba8  mov     [rbp+4Fh+var_58], 0
0x180010bb0  mov     [rbp+4Fh+var_50], ebx
0x180010bb3  mov     [rbp+4Fh+var_4C], 0FFFFFFFFh
0x180010bba  mov     [rbp+4Fh+var_48], 3Dh ; '='
0x180010bc1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180010bc8  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180010bcc  call    _CxxThrowException_0
0x180010bd2  mov     byte ptr [rdi+74h], 1
0x180010bd6  lea     rcx, [rbp+4Fh+var_80]
0x180010bda  call    tlx___UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1_______UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1___
0x180010bdf  mov     rax, [rdi+58h]
0x180010be3  mov     [rbp+4Fh+var_90], rax
0x180010be7  mov     rcx, [rdi+60h]
0x180010beb  sub     rcx, rax
0x180010bee  sar     rcx, 5
0x180010bf2  mov     [rbp-39h], rcx
0x180010bf6  mov     r9, [rbp+4Fh+arg_20]
0x180010bfa  mov     r8, r12
0x180010bfd  mov     edx, r13d
0x180010c00  lea     rcx, [rbp+4Fh+var_90]
0x180010c04  call    ?MakeStringArrayVariant@@YAKV?$span@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@$0?0@utl@@KPEAU_EVT_VARIANT@@AEAK@Z; MakeStringArrayVariant(utl::span<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,-1>,ulong,_EVT_VARIANT *,ulong &)
0x180010c09  jmp     loc_1800109F5
```
