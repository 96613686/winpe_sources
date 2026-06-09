# RegisterRPCInterfaceGroup(SmsRouterRpcInterface * const,ulong,void * *)

- ea: `0x18000becc`
- end: `0x18000c421`
- name: `?RegisterRPCInterfaceGroup@@YAJQEAUSmsRouterRpcInterface@@KPEAPEAX@Z`
- size: `1365`
- prototype: `__int64 __fastcall(struct SmsRouterRpcInterface *const, __int64, void **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c694`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x180003f8c`
- `0x180004974`
- `0x18000498c`
- `0x180004998`
- `0x18000659c`
- `0x1800069f0`
- `0x18000ae8c`
- `0x18000aeec`
- `0x18000b07c`
- `0x18000b264`
- `0x18000b460`
- `0x18000b7d0`
- `0x18000b868`
- `0x18000b9cc`
- `0x18000ba3c`
- `0x18000bac4`
- `0x18000bb50`
- `0x18000becc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c3c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c3c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2e4`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000c341`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000c341`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000bf5b`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000c3a6`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000bf5b`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000c3a6`
- `RPCRT4!RpcObjectSetType` at `0x18000c050`
- `RPCRT4!RpcObjectSetType` at `0x18000c050`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000c361`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000c361`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000bfcd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000bfcd`

## pseudocode

```c
__int64 __fastcall RegisterRPCInterfaceGroup(struct SmsRouterRpcInterface *const a1, __int64 a2, void **a3)
{
  _QWORD *v3; // rax
  unsigned int v4; // r15d
  unsigned __int64 v5; // r14
  int LastError; // eax
  signed int v7; // edi
  _QWORD *v8; // rbx
  void *v9; // rsi
  _QWORD *v10; // rdx
  _OWORD *v11; // rdx
  _WORD *v12; // r9
  unsigned __int64 v13; // rdx
  void **v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rdx
  signed int v18; // eax
  bool v19; // cc
  HLOCAL *i; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+98h] [rbp-68h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  _QWORD v32[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v36; // [rsp+E8h] [rbp-18h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  __int128 v38; // [rsp+100h] [rbp+0h] BYREF
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int128 v40; // [rsp+120h] [rbp+20h]
  __int128 v41; // [rsp+130h] [rbp+30h]
  __int128 v42; // [rsp+140h] [rbp+40h]
  char v43[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v44; // [rsp+160h] [rbp+60h]
  void *v45[2]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v46; // [rsp+178h] [rbp+78h]
  unsigned __int64 v47; // [rsp+180h] [rbp+80h]

  v33 = 0;
  v34 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  v27 = 0;
  v32[1] = 0;
  v3 = operator new(0x40u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v32[0] = v3;
  SecurityDescriptor = 0;
  if ( gc_InterfaceGroup )
    RpcServerInterfaceGroupClose();
  v4 = 0;
  while ( 1 )
  {
    memset_0(&v38, 0, 0x50u);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v25 = 0;
    *(_OWORD *)v45 = 0;
    v46 = 0;
    v47 = 7;
    LOWORD(v45[0]) = 0;
    v5 = 48LL * v4;
    *((_QWORD *)&v38 + 1) = *(struct SmsRouterRpcInterface near **)((char *)&RpcInterfaceList + v5);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            *(LPCWSTR *)((char *)&RpcInterfaceList + v5 + 32),
            1u,
            &SecurityDescriptor,
            0) )
      break;
    if ( *((_QWORD *)&v30 + 1) == v31 )
    {
      std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(
        &v30,
        *((_QWORD *)&v30 + 1),
        &SecurityDescriptor);
    }
    else
    {
      **((_QWORD **)&v30 + 1) = SecurityDescriptor;
      *((_QWORD *)&v30 + 1) += 8LL;
    }
    *((_QWORD *)&v42 + 1) = SecurityDescriptor;
    *(_QWORD *)&v40 = 0x4D200000029LL;
    if ( !memcmp_0(&xmmword_18008C0C8[v5 / 0x10], &GUID_NULL, 0x10u) )
    {
      v9 = (void *)*((_QWORD *)&v25 + 1);
    }
    else
    {
      *((_QWORD *)&v39 + 1) = *(struct SmsRouterRpcInterface near **)((char *)&RpcInterfaceList + v5 + 40);
      *(_QWORD *)&v39 = &xmmword_18008C0C8[v5 / 0x10];
      LastError = RpcObjectSetType((UUID *)&xmmword_18008C0C8[v5 / 0x10], (UUID *)&xmmword_18008C0C8[v5 / 0x10]);
      v7 = LastError;
      if ( LastError && LastError != 1711 )
        goto LABEL_44;
      v8 = operator new[](0x20u);
      *(_QWORD *)cbData = v8;
      v9 = operator new(0x18u);
      *(_QWORD *)cbData = v9;
      *(_OWORD *)v9 = 0;
      *((_DWORD *)v9 + 2) = 1;
      *((_DWORD *)v9 + 3) = 1;
      *(_QWORD *)v9 = &std::_Ref_count<_UUID_VECTOR>::`vftable';
      *((_QWORD *)v9 + 2) = v8;
      operator delete(0);
      *(_QWORD *)&v25 = v8;
      *((_QWORD *)&v25 + 1) = v9;
      *(_DWORD *)v8 = 1;
      v8[1] = v8 + 2;
      *((_OWORD *)v8 + 1) = *(_OWORD *)((char *)&RpcInterfaceList + v5 + 8);
      v10 = (_QWORD *)*((_QWORD *)&v33 + 1);
      if ( *((_QWORD *)&v33 + 1) == v34 )
      {
        std::vector<std::shared_ptr<_UUID_VECTOR>>::_Emplace_reallocate<std::shared_ptr<_UUID_VECTOR> const &>(
          &v33,
          *((_QWORD *)&v33 + 1),
          &v25);
        v9 = (void *)*((_QWORD *)&v25 + 1);
        v8 = (_QWORD *)v25;
      }
      else
      {
        **((_QWORD **)&v33 + 1) = 0;
        v10[1] = 0;
        _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
        *v10 = v8;
        v10[1] = v9;
        *((_QWORD *)&v33 + 1) += 16LL;
      }
      *((_QWORD *)&v41 + 1) = v8;
    }
    v11 = (_OWORD *)*((_QWORD *)&v28 + 1);
    if ( *((_QWORD *)&v28 + 1) == v29 )
    {
      std::vector<RPC_INTERFACE_TEMPLATEW>::_Emplace_reallocate<RPC_INTERFACE_TEMPLATEW const &>(
        &v28,
        *((_QWORD *)&v28 + 1),
        &v38);
    }
    else
    {
      **((_OWORD **)&v28 + 1) = v38;
      v11[1] = v39;
      v11[2] = v40;
      v11[3] = v41;
      v11[4] = v42;
      *((_QWORD *)&v28 + 1) += 80LL;
    }
    v12 = *(struct SmsRouterRpcInterface near **)((char *)&RpcInterfaceList + v5 + 24);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 > v47 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v45);
      }
      else
      {
        v14 = v45;
        if ( v47 > 7 )
          v14 = (void **)v45[0];
        v46 = v13;
        v15 = 2 * v13;
        memmove_0(v14, v12, 2 * v13);
        *(_WORD *)((char *)v14 + v15) = 0;
      }
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      v32,
      v43,
      v45);
    v16 = v44;
    if ( *(_BYTE *)(v44 + 25) || (unsigned __int8)std::operator<<unsigned short>(v45, v44 + 32) || v16 == v32[0] )
    {
      *(_QWORD *)&v36 = *(struct SmsRouterRpcInterface near **)((char *)&RpcInterfaceList + v5 + 24);
      *((_QWORD *)&v36 + 1) = SecurityDescriptor;
      *((_QWORD *)&v35 + 1) = L"ncalrpc";
      LODWORD(v37) = 10;
      v17 = *((_QWORD *)&v26 + 1);
      if ( *((_QWORD *)&v26 + 1) == v27 )
      {
        std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(&v26, *((_QWORD *)&v26 + 1), &v35);
      }
      else
      {
        **((_OWORD **)&v26 + 1) = v35;
        *(_OWORD *)(v17 + 16) = v36;
        *(_QWORD *)(v17 + 32) = v37;
        *((_QWORD *)&v26 + 1) += 40LL;
      }
    }
    SecurityDescriptor = 0;
    std::wstring::~wstring(v45);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v9)(v9);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    if ( ++v4 >= 2 )
    {
      *(_DWORD *)Data = 120;
      cbData[0] = 4;
      RegQueryValueExW(g_SmsRouterKey, L"RpcIdleTimeout", 0, 0, Data, cbData);
      v18 = RpcServerInterfaceGroupCreateW(
              v28,
              0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 4),
              v26,
              0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v26 + 1) - v26) >> 3),
              *(_DWORD *)Data,
              SmsRouterRpcTimeoutCallback,
              0,
              &gc_InterfaceGroup);
      v7 = v18;
      v19 = v18 <= 0;
      if ( v18 || (v18 = RpcServerInterfaceGroupActivate(gc_InterfaceGroup), v7 = v18, v19 = v18 <= 0, v18) )
      {
        if ( !v19 )
          v7 = (unsigned __int16)v18 | 0x80070000;
      }
      else
      {
        v7 = 0;
      }
      goto LABEL_47;
    }
  }
  LastError = GetLastError();
  v7 = LastError;
LABEL_44:
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  std::wstring::~wstring(v45);
LABEL_47:
  if ( gc_InterfaceGroup && v7 < 0 )
  {
    if ( gc_InterfaceGroup )
      RpcServerInterfaceGroupClose();
    gc_InterfaceGroup = 0;
  }
  for ( i = (HLOCAL *)v30; i != *((HLOCAL **)&v30 + 1); ++i )
    LocalFree(*i);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v32);
  std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(&v26);
  std::vector<RPC_INTERFACE_TEMPLATEW>::~vector<RPC_INTERFACE_TEMPLATEW>(&v28);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,MessageProcessingState>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,MessageProcessingState>>>>>>(&v30);
  std::vector<std::shared_ptr<_UUID_VECTOR>>::~vector<std::shared_ptr<_UUID_VECTOR>>(&v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000becc  push    rbp
0x18000bece  push    rbx
0x18000becf  push    rsi
0x18000bed0  push    rdi
0x18000bed1  push    r12
0x18000bed3  push    r14
0x18000bed5  push    r15
0x18000bed7  lea     rbp, [rsp-90h]
0x18000bedf  sub     rsp, 190h
0x18000bee6  mov     rax, cs:__security_cookie
0x18000beed  xor     rax, rsp
0x18000bef0  mov     [rbp+0C0h+var_38], rax
0x18000bef7  xorps   xmm0, xmm0
0x18000befa  movdqu  [rbp+0C0h+var_100], xmm0
0x18000beff  xor     r12d, r12d
0x18000bf02  mov     [rbp+0C0h+var_F0], r12
0x18000bf06  movdqu  [rbp+0C0h+var_128], xmm0
0x18000bf0b  mov     [rbp+0C0h+var_118], r12
0x18000bf0f  movdqu  [rbp+0C0h+var_140], xmm0
0x18000bf14  mov     [rbp+0C0h+var_130], r12
0x18000bf18  movdqu  [rsp+1C0h+var_158], xmm0
0x18000bf1e  mov     [rsp+1C0h+var_148], r12
0x18000bf23  mov     [rbp+0C0h+var_110], r12
0x18000bf27  mov     [rbp+0C0h+var_108], r12
0x18000bf2b  lea     ecx, [r12+40h]; Size
0x18000bf30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf35  mov     [rax], rax
0x18000bf38  mov     [rax+8], rax
0x18000bf3c  mov     [rax+10h], rax
0x18000bf40  mov     word ptr [rax+18h], 101h
0x18000bf46  mov     [rbp+0C0h+var_110], rax
0x18000bf4a  mov     [rsp+1C0h+SecurityDescriptor], r12
0x18000bf4f  mov     rcx, cs:?gc_InterfaceGroup@@3PEAXEA; void * gc_InterfaceGroup
0x18000bf56  test    rcx, rcx
0x18000bf59  jz      short loc_18000BF61
0x18000bf5b  call    cs:__imp_RpcServerInterfaceGroupClose
0x18000bf61  mov     r15d, r12d
0x18000bf64  lea     rdi, ?RpcInterfaceList@@3PAUSmsRouterRpcInterface@@A; SmsRouterRpcInterface near * RpcInterfaceList
0x18000bf6b  xor     edx, edx; Val
0x18000bf6d  lea     r8d, [rdx+50h]; Size
0x18000bf71  lea     rcx, [rbp+0C0h+var_C0]; void *
0x18000bf75  call    memset_0
0x18000bf7a  xorps   xmm0, xmm0
0x18000bf7d  xor     eax, eax
0x18000bf7f  movups  [rbp+0C0h+var_E8], xmm0
0x18000bf83  movups  [rbp+0C0h+var_D8], xmm0
0x18000bf87  mov     [rbp+0C0h+var_C8], rax
0x18000bf8b  movdqu  [rsp+1C0h+var_168], xmm0
0x18000bf91  movups  xmmword ptr [rbp+0C0h+var_58], xmm0
0x18000bf95  mov     [rbp+0C0h+var_48], r12
0x18000bf99  mov     [rbp+0C0h+var_40], 7
0x18000bfa4  mov     word ptr [rbp+0C0h+var_58], r12w
0x18000bfa9  mov     eax, r15d
0x18000bfac  lea     r14, [rax+rax*2]
0x18000bfb0  shl     r14, 4
0x18000bfb4  mov     rax, [r14+rdi]
0x18000bfb8  mov     qword ptr [rbp+0C0h+var_C0+8], rax
0x18000bfbc  xor     r9d, r9d; SecurityDescriptorSize
0x18000bfbf  lea     r8, [rsp+1C0h+SecurityDescriptor]; SecurityDescriptor
0x18000bfc4  lea     edx, [r9+1]; StringSDRevision
0x18000bfc8  mov     rcx, [r14+rdi+20h]; StringSecurityDescriptor
0x18000bfcd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000bfd3  test    eax, eax
0x18000bfd5  jz      loc_18000C372
0x18000bfdb  mov     rdx, qword ptr [rbp+0C0h+var_128+8]
0x18000bfdf  cmp     rdx, [rbp+0C0h+var_118]
0x18000bfe3  jz      short loc_18000BFF4
0x18000bfe5  mov     rax, [rsp+1C0h+SecurityDescriptor]
0x18000bfea  mov     [rdx], rax
0x18000bfed  add     qword ptr [rbp+0C0h+var_128+8], 8
0x18000bff2  jmp     short loc_18000C002
0x18000bff4  lea     r8, [rsp+1C0h+SecurityDescriptor]
0x18000bff9  lea     rcx, [rbp+0C0h+var_128]
0x18000bffd  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x18000c002  mov     rax, [rsp+1C0h+SecurityDescriptor]
0x18000c007  mov     [rbp+0C0h+var_78], rax
0x18000c00b  mov     dword ptr [rbp+0C0h+var_A0], 29h ; ')'
0x18000c012  mov     dword ptr [rbp+0C0h+var_A0+4], 4D2h
0x18000c019  lea     rbx, [rdi+8]
0x18000c01d  add     rbx, r14
0x18000c020  mov     r8d, 10h; Size
0x18000c026  lea     rdx, GUID_NULL; Buf2
0x18000c02d  mov     rcx, rbx; Buf1
0x18000c030  call    memcmp_0
0x18000c035  test    eax, eax
0x18000c037  jz      loc_18000C11A
0x18000c03d  mov     rax, [r14+rdi+28h]
0x18000c042  mov     qword ptr [rbp+0C0h+var_B0+8], rax
0x18000c046  mov     qword ptr [rbp+0C0h+var_B0], rbx
0x18000c04a  mov     rdx, rbx; TypeUuid
0x18000c04d  mov     rcx, rbx; ObjUuid
0x18000c050  call    cs:__imp_RpcObjectSetType
0x18000c056  mov     edi, eax
0x18000c058  test    eax, eax
0x18000c05a  jz      short loc_18000C067
0x18000c05c  cmp     eax, 6AFh
0x18000c061  jnz     loc_18000C37A
0x18000c067  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c06c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c071  mov     rbx, rax
0x18000c074  mov     qword ptr [rsp+1C0h+cbData], rax
0x18000c079  mov     ecx, 18h; Size
0x18000c07e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c083  mov     rsi, rax
0x18000c086  mov     qword ptr [rsp+1C0h+cbData], rax
0x18000c08b  xorps   xmm0, xmm0
0x18000c08e  movups  xmmword ptr [rax], xmm0
0x18000c091  mov     edi, 1
0x18000c096  mov     [rax+8], edi
0x18000c099  mov     [rax+0Ch], edi
0x18000c09c  lea     rax, ??_7?$_Ref_count@U_UUID_VECTOR@@@std@@6B@; const std::_Ref_count<_UUID_VECTOR>::`vftable'
0x18000c0a3  mov     [rsi], rax
0x18000c0a6  mov     [rsi+10h], rbx
0x18000c0aa  lea     edx, [rdi+0Fh]
0x18000c0ad  xor     ecx, ecx; Block
0x18000c0af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c0b4  mov     qword ptr [rsp+1C0h+var_168], rbx
0x18000c0b9  mov     qword ptr [rsp+1C0h+var_168+8], rsi
0x18000c0be  mov     [rbx], edi
0x18000c0c0  lea     rax, [rbx+10h]
0x18000c0c4  mov     [rbx+8], rax
0x18000c0c8  lea     rdi, ?RpcInterfaceList@@3PAUSmsRouterRpcInterface@@A; SmsRouterRpcInterface near * RpcInterfaceList
0x18000c0cf  movups  xmm0, xmmword ptr [r14+rdi+8]
0x18000c0d5  movdqu  xmmword ptr [rax], xmm0
0x18000c0d9  mov     rdx, qword ptr [rbp+0C0h+var_100+8]
0x18000c0dd  cmp     rdx, [rbp+0C0h+var_F0]
0x18000c0e1  jz      short loc_18000C0FC
0x18000c0e3  mov     [rdx], r12
0x18000c0e6  mov     [rdx+8], r12
0x18000c0ea  lock inc dword ptr [rsi+8]
0x18000c0ee  mov     [rdx], rbx
0x18000c0f1  mov     [rdx+8], rsi
0x18000c0f5  add     qword ptr [rbp+0C0h+var_100+8], 10h
0x18000c0fa  jmp     short loc_18000C114
0x18000c0fc  lea     r8, [rsp+1C0h+var_168]
0x18000c101  lea     rcx, [rbp+0C0h+var_100]
0x18000c105  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@U_UUID_VECTOR@@@std@@@?$vector@V?$shared_ptr@U_UUID_VECTOR@@@std@@V?$allocator@V?$shared_ptr@U_UUID_VECTOR@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@U_UUID_VECTOR@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<_UUID_VECTOR>>::_Emplace_reallocate<std::shared_ptr<_UUID_VECTOR> const &>(std::shared_ptr<_UUID_VECTOR> * const,std::shared_ptr<_UUID_VECTOR> const &)
0x18000c10a  mov     rsi, qword ptr [rsp+1C0h+var_168+8]
0x18000c10f  mov     rbx, qword ptr [rsp+1C0h+var_168]
0x18000c114  mov     [rbp+0C0h+var_88], rbx
0x18000c118  jmp     short loc_18000C11F
0x18000c11a  mov     rsi, qword ptr [rsp+1C0h+var_168+8]
0x18000c11f  mov     rdx, qword ptr [rbp+0C0h+var_140+8]
0x18000c123  cmp     rdx, [rbp+0C0h+var_130]
0x18000c127  jz      short loc_18000C157
0x18000c129  movaps  xmm0, [rbp+0C0h+var_C0]
0x18000c12d  movups  xmmword ptr [rdx], xmm0
0x18000c130  movaps  xmm1, [rbp+0C0h+var_B0]
0x18000c134  movups  xmmword ptr [rdx+10h], xmm1
0x18000c138  movaps  xmm0, [rbp+0C0h+var_A0]
0x18000c13c  movups  xmmword ptr [rdx+20h], xmm0
0x18000c140  movaps  xmm1, xmmword ptr [rbp+30h]
0x18000c144  movups  xmmword ptr [rdx+30h], xmm1
0x18000c148  movaps  xmm0, xmmword ptr [rbp+40h]
0x18000c14c  movups  xmmword ptr [rdx+40h], xmm0
0x18000c150  add     qword ptr [rbp+0C0h+var_140+8], 50h ; 'P'
0x18000c155  jmp     short loc_18000C164
0x18000c157  lea     r8, [rbp+0C0h+var_C0]
0x18000c15b  lea     rcx, [rbp+0C0h+var_140]
0x18000c15f  call    ??$_Emplace_reallocate@AEBURPC_INTERFACE_TEMPLATEW@@@?$vector@URPC_INTERFACE_TEMPLATEW@@V?$allocator@URPC_INTERFACE_TEMPLATEW@@@std@@@std@@AEAAPEAURPC_INTERFACE_TEMPLATEW@@QEAU2@AEBU2@@Z; std::vector<RPC_INTERFACE_TEMPLATEW>::_Emplace_reallocate<RPC_INTERFACE_TEMPLATEW const &>(RPC_INTERFACE_TEMPLATEW * const,RPC_INTERFACE_TEMPLATEW const &)
0x18000c164  mov     r9, [r14+rdi+18h]
0x18000c169  test    r9, r9
0x18000c16c  jz      short loc_18000C1C3
0x18000c16e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c172  inc     rdx
0x18000c175  cmp     [r9+rdx*2], r12w
0x18000c17a  jnz     short loc_18000C172
0x18000c17c  cmp     rdx, [rbp+0C0h+var_40]
0x18000c183  ja      short loc_18000C1BA
0x18000c185  lea     rdi, [rbp+0C0h+var_58]
0x18000c189  cmp     [rbp+0C0h+var_40], 7
0x18000c191  cmova   rdi, [rbp+0C0h+var_58]
0x18000c196  mov     [rbp+0C0h+var_48], rdx
0x18000c19a  lea     rbx, [rdx+rdx]
0x18000c19e  mov     r8, rbx; Size
0x18000c1a1  mov     rdx, r9; Src
0x18000c1a4  mov     rcx, rdi; void *
0x18000c1a7  call    memmove_0
0x18000c1ac  mov     [rbx+rdi], r12w
0x18000c1b1  lea     rdi, ?RpcInterfaceList@@3PAUSmsRouterRpcInterface@@A; SmsRouterRpcInterface near * RpcInterfaceList
0x18000c1b8  jmp     short loc_18000C1C3
0x18000c1ba  lea     rcx, [rbp+0C0h+var_58]
0x18000c1be  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000c1c3  lea     r8, [rbp+0C0h+var_58]
0x18000c1c7  lea     rdx, [rbp+0C0h+var_70]
0x18000c1cb  lea     rcx, [rbp+0C0h+var_110]
0x18000c1cf  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000c1d4  mov     rbx, [rbp+0C0h+var_60]
0x18000c1d8  cmp     [rbx+19h], r12b
0x18000c1dc  jnz     short loc_18000C1F5
0x18000c1de  lea     rdx, [rbx+20h]
0x18000c1e2  lea     rcx, [rbp+0C0h+var_58]
0x18000c1e6  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000c1eb  test    al, al
0x18000c1ed  jnz     short loc_18000C1F5
0x18000c1ef  cmp     rbx, [rbp+0C0h+var_110]
0x18000c1f3  jnz     short loc_18000C254
0x18000c1f5  mov     rax, [r14+rdi+18h]
0x18000c1fa  mov     qword ptr [rbp+0C0h+var_D8], rax
0x18000c1fe  mov     rax, [rsp+1C0h+SecurityDescriptor]
0x18000c203  mov     qword ptr [rbp+0C0h+var_D8+8], rax
0x18000c207  lea     rax, aNcalrpc; "ncalrpc"
0x18000c20e  mov     qword ptr [rbp+0C0h+var_E8+8], rax
0x18000c212  mov     dword ptr [rbp+0C0h+var_C8], 0Ah
0x18000c219  mov     rdx, qword ptr [rsp+1C0h+var_158+8]
0x18000c21e  cmp     rdx, [rsp+1C0h+var_148]
0x18000c223  jz      short loc_18000C246
0x18000c225  movups  xmm0, [rbp+0C0h+var_E8]
0x18000c229  movups  xmmword ptr [rdx], xmm0
0x18000c22c  movups  xmm1, [rbp+0C0h+var_D8]
0x18000c230  movups  xmmword ptr [rdx+10h], xmm1
0x18000c234  movsd   xmm0, [rbp+0C0h+var_C8]
0x18000c239  movsd   qword ptr [rdx+20h], xmm0
0x18000c23e  add     qword ptr [rsp+1C0h+var_158+8], 28h ; '('
0x18000c244  jmp     short loc_18000C254
0x18000c246  lea     r8, [rbp+0C0h+var_E8]
0x18000c24a  lea     rcx, [rsp+1C0h+var_158]
0x18000c24f  call    ??$_Emplace_reallocate@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@AEAAPEAUJET_SETCOLUMN@@QEAU2@AEBU2@@Z; std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(JET_SETCOLUMN * const,JET_SETCOLUMN const &)
0x18000c254  mov     [rsp+1C0h+SecurityDescriptor], r12
0x18000c259  lea     rcx, [rbp+0C0h+var_58]; void *
0x18000c25d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c262  nop
0x18000c263  test    rsi, rsi
0x18000c266  jz      short loc_18000C29F
0x18000c268  or      eax, 0FFFFFFFFh
0x18000c26b  lock xadd [rsi+8], eax
0x18000c270  cmp     eax, 1
0x18000c273  jnz     short loc_18000C29F
0x18000c275  mov     rax, [rsi]
0x18000c278  mov     rcx, rsi
0x18000c27b  mov     rax, [rax]
0x18000c27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c283  or      eax, 0FFFFFFFFh
0x18000c286  lock xadd [rsi+0Ch], eax
0x18000c28b  cmp     eax, 1
0x18000c28e  jnz     short loc_18000C29F
0x18000c290  mov     rax, [rsi]
0x18000c293  mov     rcx, rsi
0x18000c296  mov     rax, [rax+8]
0x18000c29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29f  inc     r15d
0x18000c2a2  cmp     r15d, 2
0x18000c2a6  jb      loc_18000BF6B
0x18000c2ac  mov     dword ptr [rsp+1C0h+Data], 78h ; 'x'
0x18000c2b4  mov     [rsp+1C0h+cbData], 4
0x18000c2bc  lea     rax, [rsp+1C0h+cbData]
0x18000c2c1  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18000c2c6  lea     rax, [rsp+1C0h+Data]
0x18000c2cb  mov     [rsp+1C0h+lpData], rax; lpData
0x18000c2d0  xor     r9d, r9d; lpType
0x18000c2d3  xor     r8d, r8d; lpReserved
0x18000c2d6  lea     rdx, ValueName; "RpcIdleTimeout"
0x18000c2dd  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18000c2e4  call    cs:__imp_RegQueryValueExW
0x18000c2ea  mov     r8, qword ptr [rsp+1C0h+var_158]
0x18000c2ef  mov     rcx, qword ptr [rbp+0C0h+var_140]
0x18000c2f3  mov     r9, qword ptr [rsp+1C0h+var_158+8]
0x18000c2f8  sub     r9, r8
0x18000c2fb  sar     r9, 3
0x18000c2ff  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c309  imul    r9, rax
0x18000c30d  mov     rdx, qword ptr [rbp+0C0h+var_140+8]
0x18000c311  sub     rdx, rcx
0x18000c314  sar     rdx, 4
0x18000c318  imul    rdx, rax
0x18000c31c  lea     rax, ?gc_InterfaceGroup@@3PEAXEA; void * gc_InterfaceGroup
0x18000c323  mov     [rsp+1C0h+var_188], rax
0x18000c328  mov     [rsp+1C0h+var_190], r12
0x18000c32d  lea     rax, ?SmsRouterRpcTimeoutCallback@@YAXPEAX0K@Z; SmsRouterRpcTimeoutCallback(void *,void *,ulong)
0x18000c334  mov     [rsp+1C0h+lpcbData], rax
0x18000c339  mov     eax, dword ptr [rsp+1C0h+Data]
0x18000c33d  mov     dword ptr [rsp+1C0h+lpData], eax
0x18000c341  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000c347  mov     edi, eax
0x18000c349  test    eax, eax
0x18000c34b  jz      short loc_18000C35A
0x18000c34d  jle     short loc_18000C391
0x18000c34f  movzx   edi, ax
0x18000c352  or      edi, 80070000h
0x18000c358  jmp     short loc_18000C391
0x18000c35a  mov     rcx, cs:?gc_InterfaceGroup@@3PEAXEA; void * gc_InterfaceGroup
0x18000c361  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000c367  mov     edi, eax
0x18000c369  test    eax, eax
0x18000c36b  jnz     short loc_18000C34D
0x18000c36d  mov     edi, r12d
0x18000c370  jmp     short loc_18000C391
0x18000c372  call    cs:__imp_GetLastError
0x18000c378  mov     edi, eax
0x18000c37a  test    eax, eax
0x18000c37c  jle     short loc_18000C387
0x18000c37e  movzx   edi, ax
0x18000c381  or      edi, 80070000h
0x18000c387  lea     rcx, [rbp+0C0h+var_58]; void *
0x18000c38b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c390  nop
0x18000c391  mov     rcx, cs:?gc_InterfaceGroup@@3PEAXEA; void * gc_InterfaceGroup
0x18000c398  test    rcx, rcx
0x18000c39b  jz      short loc_18000C3B3
0x18000c39d  test    edi, edi
  ... truncated ...
```
