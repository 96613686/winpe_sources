# CPolicyChannelNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x18000c410`
- end: `0x18000c85f`
- name: `?GetChildNodeNames@CPolicyChannelNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1103`
- prototype: `__int64 __fastcall(CPolicyChannelNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180001b84`
- `0x18000bbd8`
- `0x18000c410`
- `0x180012440`
- `0x180012b8c`
- `0x180012e74`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c83d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c83d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c743`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c57d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c719`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c57d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c719`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c598`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c734`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c598`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c52d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c64a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c52d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c5c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c64a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
__int64 __fastcall CPolicyChannelNode::GetChildNodeNames(__int64 this, unsigned int *a2, unsigned __int16 ***a3)
{
  CPolicyChannelNode *v5; // r9
  void *v6; // rbx
  int RegisteredChannels; // esi
  _QWORD *v8; // rax
  _BYTE *v9; // rax
  _QWORD *v10; // r12
  __int64 i; // rcx
  int v12; // r14d
  __int64 *v13; // rbx
  const OLECHAR *v14; // rcx
  BSTR v15; // rax
  __int64 **v16; // rax
  __int64 *j; // rax
  __int64 *k; // rcx
  _QWORD *v19; // rax
  unsigned __int16 **v20; // rax
  unsigned __int16 **v21; // r12
  __int64 m; // rcx
  int v23; // r14d
  __int64 *v24; // rbx
  const OLECHAR *v25; // rcx
  BSTR v26; // rax
  __int64 **v27; // rax
  __int64 *n; // rax
  __int64 *ii; // rcx
  int v30; // eax
  __int64 **v32; // [rsp+30h] [rbp-68h] BYREF
  __int64 v33; // [rsp+38h] [rbp-60h]
  void *v34; // [rsp+40h] [rbp-58h]
  __int64 v35; // [rsp+48h] [rbp-50h]
  HKEY hKey[4]; // [rsp+50h] [rbp-48h] BYREF
  unsigned int *v37; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int16 *v38; // [rsp+B8h] [rbp+20h] BYREF

  v37 = a2;
  v5 = (CPolicyChannelNode *)this;
  v6 = 0;
  v34 = 0;
  v35 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    this = (unsigned int)(*(_DWORD *)(this + 44) - 33);
    if ( (_DWORD)this )
    {
      if ( (_DWORD)this == 1 )
      {
        this = *((_QWORD *)v5 + 3);
        if ( this )
        {
          v38 = 0;
          RegisteredChannels = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
                                 this,
                                 3,
                                 &v38);
          if ( RegisteredChannels >= 0 )
          {
            CPolicyChannel::CPolicyChannel((CPolicyChannel *)hKey, v38);
            v33 = 0;
            v8 = operator new(0x40u);
            *v8 = v8;
            v8[1] = v8;
            v8[2] = v8;
            *((_WORD *)v8 + 12) = 257;
            v32 = (__int64 **)v8;
            CPolicyChannel::GetValueNames(hKey, &v32);
            v9 = CoTaskMemAlloc(8 * v33);
            v10 = v9;
            if ( v9 )
            {
              for ( i = 8 * v33; i; --i )
                *v9++ = 0;
              v12 = 0;
              v13 = *v32;
              while ( !*((_BYTE *)v13 + 25) )
              {
                v14 = (const OLECHAR *)(v13 + 4);
                if ( (unsigned __int64)v13[7] > 7 )
                  v14 = *(const OLECHAR **)v14;
                v15 = SysAllocString(v14);
                v10[v12] = v15;
                if ( !v15 )
                {
                  while ( --v12 >= 0 )
                    SysFreeString((BSTR)v10[v12]);
                  CoTaskMemFree(v10);
                  RegisteredChannels = -2147024882;
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
                  this = (__int64)hKey[0];
                  if ( hKey[0] )
                    RegCloseKey(hKey[0]);
                  v6 = v34;
                  goto LABEL_63;
                }
                ++v12;
                v16 = (__int64 **)v13[2];
                if ( *((_BYTE *)v16 + 25) )
                {
                  for ( j = (__int64 *)v13[1]; !*((_BYTE *)j + 25) && v13 == (__int64 *)j[2]; j = (__int64 *)j[1] )
                    v13 = j;
                  v13 = j;
                }
                else
                {
                  v13 = (__int64 *)v13[2];
                  for ( k = *v16; !*((_BYTE *)k + 25); k = (__int64 *)*k )
                    v13 = k;
                }
              }
              *a3 = (unsigned __int16 **)v10;
              *a2 = v33;
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
              this = (__int64)hKey[0];
              if ( hKey[0] )
                RegCloseKey(hKey[0]);
LABEL_61:
              v6 = v34;
            }
            else
            {
              RegisteredChannels = -2147024882;
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
              this = (__int64)hKey[0];
              if ( hKey[0] )
                RegCloseKey(hKey[0]);
            }
          }
        }
        else
        {
          RegisteredChannels = -2147024809;
        }
      }
      else
      {
        *a2 = 0;
        *a3 = 0;
        RegisteredChannels = -2046820335;
      }
    }
    else
    {
      v33 = 0;
      v19 = operator new(0x40u);
      *v19 = v19;
      v19[1] = v19;
      v19[2] = v19;
      *((_WORD *)v19 + 12) = 257;
      v32 = (__int64 **)v19;
      RegisteredChannels = CPolicyChannel::GetRegisteredChannels(&v32);
      if ( RegisteredChannels >= 0 )
      {
        v20 = (unsigned __int16 **)CoTaskMemAlloc(8 * v33);
        v21 = v20;
        if ( v20 )
        {
          for ( m = 8 * v33; m; --m )
          {
            *(_BYTE *)v20 = 0;
            v20 = (unsigned __int16 **)((char *)v20 + 1);
          }
          v23 = 0;
          v24 = *v32;
          while ( 1 )
          {
            if ( *((_BYTE *)v24 + 25) )
            {
              *a3 = v21;
              *a2 = v33;
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
              goto LABEL_61;
            }
            v25 = (const OLECHAR *)(v24 + 4);
            if ( (unsigned __int64)v24[7] > 7 )
              v25 = *(const OLECHAR **)v25;
            v26 = SysAllocString(v25);
            v21[v23] = v26;
            if ( !v26 )
              break;
            ++v23;
            v27 = (__int64 **)v24[2];
            if ( *((_BYTE *)v27 + 25) )
            {
              for ( n = (__int64 *)v24[1]; !*((_BYTE *)n + 25) && v24 == (__int64 *)n[2]; n = (__int64 *)n[1] )
                v24 = n;
              v24 = n;
            }
            else
            {
              v24 = (__int64 *)v24[2];
              for ( ii = *v27; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
                v24 = ii;
            }
          }
          while ( --v23 >= 0 )
            SysFreeString(v21[v23]);
          CoTaskMemFree(v21);
          RegisteredChannels = -2147024882;
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
          v6 = v34;
        }
        else
        {
          RegisteredChannels = -2147024882;
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
        }
      }
      else
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
      }
    }
  }
  else
  {
    RegisteredChannels = -2147024809;
  }
LABEL_63:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v37) = RegisteredChannels;
    if ( a2 )
      v30 = *a2;
    else
      v30 = -1;
    LODWORD(v38) = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)byte_18003F1C9,
      (__int64)a3,
      (__int64)v5,
      (__int64)&v38,
      (__int64)&v37);
  }
  if ( v6 )
    free(v6);
  return (unsigned int)RegisteredChannels;
}

```

## disassembly

```asm
0x18000c410  mov     rax, rsp
0x18000c413  mov     [rax+8], rbx
0x18000c417  mov     [rax+18h], rsi
0x18000c41b  mov     [rax+10h], rdx
0x18000c41f  push    rdi
0x18000c420  push    r12
0x18000c422  push    r13
0x18000c424  push    r14
0x18000c426  push    r15
0x18000c428  sub     rsp, 70h
0x18000c42c  mov     r13, r8
0x18000c42f  mov     r15, rdx
0x18000c432  mov     r9, rcx
0x18000c435  xor     edi, edi
0x18000c437  mov     ebx, edi
0x18000c439  mov     [rax-58h], rbx
0x18000c43d  mov     [rax-50h], rdi
0x18000c441  test    rdx, rdx
0x18000c444  jz      loc_18000C7E3
0x18000c44a  test    r8, r8
0x18000c44d  jz      loc_18000C7E3
0x18000c453  mov     [rdx], edi
0x18000c455  mov     [r8], rdi
0x18000c458  mov     ecx, [rcx+2Ch]
0x18000c45b  sub     ecx, 21h ; '!'
0x18000c45e  jz      loc_18000C65F
0x18000c464  cmp     ecx, 1
0x18000c467  jz      short loc_18000C478
0x18000c469  mov     [rdx], edi
0x18000c46b  mov     [r8], rdi
0x18000c46e  mov     esi, 86000011h
0x18000c473  jmp     loc_18000C7E8
0x18000c478  mov     rcx, [r9+18h]
0x18000c47c  test    rcx, rcx
0x18000c47f  jz      loc_18000C655
0x18000c485  mov     [rsp+98h+arg_18], rdi
0x18000c48d  mov     rax, [rcx]
0x18000c490  lea     r8, [rsp+98h+arg_18]
0x18000c498  mov     edx, 3
0x18000c49d  mov     rax, [rax+58h]
0x18000c4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4a6  mov     esi, eax
0x18000c4a8  test    eax, eax
0x18000c4aa  js      loc_18000C65A
0x18000c4b0  mov     rdx, [rsp+98h+arg_18]; unsigned __int16 *
0x18000c4b8  lea     rcx, [rsp+98h+hKey]; this
0x18000c4bd  call    ??0CPolicyChannel@@QEAA@PEBG@Z; CPolicyChannel::CPolicyChannel(ushort const *)
0x18000c4c2  nop
0x18000c4c3  mov     [rsp+98h+var_68], rdi
0x18000c4c8  mov     [rsp+98h+var_60], rdi
0x18000c4cd  mov     ecx, 40h ; '@'; Size
0x18000c4d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4d7  mov     [rax], rax
0x18000c4da  mov     [rax+8], rax
0x18000c4de  mov     [rax+10h], rax
0x18000c4e2  mov     word ptr [rax+18h], 101h
0x18000c4e8  mov     [rsp+98h+var_68], rax
0x18000c4ed  lea     rdx, [rsp+98h+var_68]
0x18000c4f2  lea     rcx, [rsp+98h+hKey]
0x18000c4f7  call    ?GetValueNames@CPolicyChannel@@QEAAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CPolicyChannel::GetValueNames(std::set<std::wstring> &)
0x18000c4fc  mov     rcx, [rsp+98h+var_60]
0x18000c501  shl     rcx, 3; cb
0x18000c505  call    cs:__imp_CoTaskMemAlloc
0x18000c50b  mov     r12, rax
0x18000c50e  test    rax, rax
0x18000c511  jnz     short loc_18000C539
0x18000c513  mov     esi, 8007000Eh
0x18000c518  lea     rcx, [rsp+98h+var_68]
0x18000c51d  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c522  nop
0x18000c523  mov     rcx, [rsp+98h+hKey]; hKey
0x18000c528  test    rcx, rcx
0x18000c52b  jz      short loc_18000C534
0x18000c52d  call    cs:__imp_RegCloseKey
0x18000c533  nop
0x18000c534  jmp     loc_18000C7E8
0x18000c539  mov     rax, [rsp+98h+var_60]
0x18000c53e  lea     rcx, ds:0[rax*8]
0x18000c546  mov     rax, r12
0x18000c549  test    rcx, rcx
0x18000c54c  jz      short loc_18000C55A
0x18000c54e  mov     [rax], dil
0x18000c551  inc     rax
0x18000c554  sub     rcx, 1
0x18000c558  jnz     short loc_18000C54E
0x18000c55a  mov     r14d, edi
0x18000c55d  mov     rbx, [rsp+98h+var_68]
0x18000c562  mov     rbx, [rbx]
0x18000c565  cmp     [rbx+19h], dil
0x18000c569  jnz     loc_18000C62A
0x18000c56f  lea     rcx, [rbx+20h]
0x18000c573  cmp     qword ptr [rcx+18h], 7
0x18000c578  jbe     short loc_18000C57D
0x18000c57a  mov     rcx, [rcx]; psz
0x18000c57d  call    cs:__imp_SysAllocString
0x18000c583  mov     rcx, rax
0x18000c586  movsxd  rax, r14d
0x18000c589  mov     [r12+rax*8], rcx
0x18000c58d  test    rcx, rcx
0x18000c590  jnz     short loc_18000C5D8
0x18000c592  jmp     short loc_18000C59E
0x18000c594  mov     rcx, [r12+r14*8]; bstrString
0x18000c598  call    cs:__imp_SysFreeString
0x18000c59e  sub     r14d, 1
0x18000c5a2  jns     short loc_18000C594
0x18000c5a4  mov     rcx, r12; pv
0x18000c5a7  call    cs:__imp_CoTaskMemFree
0x18000c5ad  mov     esi, 8007000Eh
0x18000c5b2  lea     rcx, [rsp+98h+var_68]
0x18000c5b7  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c5bc  nop
0x18000c5bd  mov     rcx, [rsp+98h+hKey]; hKey
0x18000c5c2  test    rcx, rcx
0x18000c5c5  jz      short loc_18000C5CE
0x18000c5c7  call    cs:__imp_RegCloseKey
0x18000c5cd  nop
0x18000c5ce  mov     rbx, [rsp+98h+var_58]
0x18000c5d3  jmp     loc_18000C7E8
0x18000c5d8  inc     r14d
0x18000c5db  mov     rax, [rbx+10h]
0x18000c5df  cmp     [rax+19h], dil
0x18000c5e3  jz      short loc_18000C606
0x18000c5e5  mov     rax, [rbx+8]
0x18000c5e9  jmp     short loc_18000C5F8
0x18000c5eb  cmp     rbx, [rax+10h]
0x18000c5ef  jnz     short loc_18000C5FE
0x18000c5f1  mov     rbx, rax
0x18000c5f4  mov     rax, [rax+8]
0x18000c5f8  cmp     [rax+19h], dil
0x18000c5fc  jz      short loc_18000C5EB
0x18000c5fe  mov     rbx, rax
0x18000c601  jmp     loc_18000C565
0x18000c606  mov     rbx, rax
0x18000c609  mov     rcx, [rax]
0x18000c60c  cmp     [rcx+19h], dil
0x18000c610  jnz     loc_18000C565
0x18000c616  mov     rbx, rcx
0x18000c619  mov     rax, [rcx]
0x18000c61c  mov     rcx, rax
0x18000c61f  cmp     [rax+19h], dil
0x18000c623  jz      short loc_18000C616
0x18000c625  jmp     loc_18000C565
0x18000c62a  mov     [r13+0], r12
0x18000c62e  mov     eax, dword ptr [rsp+98h+var_60]
0x18000c632  mov     [r15], eax
0x18000c635  lea     rcx, [rsp+98h+var_68]
0x18000c63a  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c63f  nop
0x18000c640  mov     rcx, [rsp+98h+hKey]; hKey
0x18000c645  test    rcx, rcx
0x18000c648  jz      short loc_18000C650
0x18000c64a  call    cs:__imp_RegCloseKey
0x18000c650  jmp     loc_18000C7CB
0x18000c655  mov     esi, 80070057h
0x18000c65a  jmp     loc_18000C7E8
0x18000c65f  mov     [rsp+98h+var_68], rdi
0x18000c664  mov     [rsp+98h+var_60], rdi
0x18000c669  mov     ecx, 40h ; '@'; Size
0x18000c66e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c673  mov     [rax], rax
0x18000c676  mov     [rax+8], rax
0x18000c67a  mov     [rax+10h], rax
0x18000c67e  mov     word ptr [rax+18h], 101h
0x18000c684  mov     [rsp+98h+var_68], rax
0x18000c689  lea     rcx, [rsp+98h+var_68]
0x18000c68e  call    ?GetRegisteredChannels@CPolicyChannel@@SAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CPolicyChannel::GetRegisteredChannels(std::set<std::wstring> &)
0x18000c693  mov     esi, eax
0x18000c695  test    eax, eax
0x18000c697  jns     short loc_18000C6A9
0x18000c699  lea     rcx, [rsp+98h+var_68]
0x18000c69e  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c6a3  nop
0x18000c6a4  jmp     loc_18000C7E8
0x18000c6a9  mov     rcx, [rsp+98h+var_60]
0x18000c6ae  shl     rcx, 3; cb
0x18000c6b2  call    cs:__imp_CoTaskMemAlloc
0x18000c6b8  mov     r12, rax
0x18000c6bb  test    rax, rax
0x18000c6be  jnz     short loc_18000C6D5
0x18000c6c0  mov     esi, 8007000Eh
0x18000c6c5  lea     rcx, [rsp+98h+var_68]
0x18000c6ca  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c6cf  nop
0x18000c6d0  jmp     loc_18000C7E8
0x18000c6d5  mov     rax, [rsp+98h+var_60]
0x18000c6da  lea     rcx, ds:0[rax*8]
0x18000c6e2  mov     rax, r12
0x18000c6e5  test    rcx, rcx
0x18000c6e8  jz      short loc_18000C6F6
0x18000c6ea  mov     [rax], dil
0x18000c6ed  inc     rax
0x18000c6f0  sub     rcx, 1
0x18000c6f4  jnz     short loc_18000C6EA
0x18000c6f6  mov     r14d, edi
0x18000c6f9  mov     rbx, [rsp+98h+var_68]
0x18000c6fe  mov     rbx, [rbx]
0x18000c701  cmp     [rbx+19h], dil
0x18000c705  jnz     loc_18000C7B5
0x18000c70b  lea     rcx, [rbx+20h]
0x18000c70f  cmp     qword ptr [rcx+18h], 7
0x18000c714  jbe     short loc_18000C719
0x18000c716  mov     rcx, [rcx]; psz
0x18000c719  call    cs:__imp_SysAllocString
0x18000c71f  mov     rcx, rax
0x18000c722  movsxd  rax, r14d
0x18000c725  mov     [r12+rax*8], rcx
0x18000c729  test    rcx, rcx
0x18000c72c  jnz     short loc_18000C763
0x18000c72e  jmp     short loc_18000C73A
0x18000c730  mov     rcx, [r12+r14*8]; bstrString
0x18000c734  call    cs:__imp_SysFreeString
0x18000c73a  sub     r14d, 1
0x18000c73e  jns     short loc_18000C730
0x18000c740  mov     rcx, r12; pv
0x18000c743  call    cs:__imp_CoTaskMemFree
0x18000c749  mov     esi, 8007000Eh
0x18000c74e  lea     rcx, [rsp+98h+var_68]
0x18000c753  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c758  nop
0x18000c759  mov     rbx, [rsp+98h+var_58]
0x18000c75e  jmp     loc_18000C7E8
0x18000c763  inc     r14d
0x18000c766  mov     rax, [rbx+10h]
0x18000c76a  cmp     [rax+19h], dil
0x18000c76e  jz      short loc_18000C791
0x18000c770  mov     rax, [rbx+8]
0x18000c774  jmp     short loc_18000C783
0x18000c776  cmp     rbx, [rax+10h]
0x18000c77a  jnz     short loc_18000C789
0x18000c77c  mov     rbx, rax
0x18000c77f  mov     rax, [rax+8]
0x18000c783  cmp     [rax+19h], dil
0x18000c787  jz      short loc_18000C776
0x18000c789  mov     rbx, rax
0x18000c78c  jmp     loc_18000C701
0x18000c791  mov     rbx, rax
0x18000c794  mov     rcx, [rax]
0x18000c797  cmp     [rcx+19h], dil
0x18000c79b  jnz     loc_18000C701
0x18000c7a1  mov     rbx, rcx
0x18000c7a4  mov     rax, [rcx]
0x18000c7a7  mov     rcx, rax
0x18000c7aa  cmp     [rax+19h], dil
0x18000c7ae  jz      short loc_18000C7A1
0x18000c7b0  jmp     loc_18000C701
0x18000c7b5  mov     [r13+0], r12
0x18000c7b9  mov     eax, dword ptr [rsp+98h+var_60]
0x18000c7bd  mov     [r15], eax
0x18000c7c0  lea     rcx, [rsp+98h+var_68]
0x18000c7c5  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000c7ca  nop
0x18000c7cb  jmp     short loc_18000C7DC
0x18000c7cd  mov     r15, [rsp+98h+arg_8]
0x18000c7d5  mov     esi, dword ptr [rsp+98h+arg_18]
0x18000c7dc  mov     rbx, [rsp+98h+var_58]
0x18000c7e1  jmp     short loc_18000C7E8
0x18000c7e3  mov     esi, 80070057h
0x18000c7e8  mov     eax, cs:dword_180048E90
0x18000c7ee  cmp     eax, 5
0x18000c7f1  jbe     short loc_18000C835
0x18000c7f3  mov     dword ptr [rsp+98h+arg_8], esi
0x18000c7fa  test    r15, r15
0x18000c7fd  jz      short loc_18000C804
0x18000c7ff  mov     eax, [r15]
0x18000c802  jmp     short loc_18000C807
0x18000c804  or      eax, 0FFFFFFFFh
0x18000c807  mov     dword ptr [rsp+98h+arg_18], eax
0x18000c80e  lea     rax, [rsp+98h+arg_8]
0x18000c816  mov     [rsp+98h+var_70], rax
0x18000c81b  lea     rax, [rsp+98h+arg_18]
0x18000c823  mov     [rsp+98h+var_78], rax
0x18000c828  lea     rdx, byte_18003F1C9
0x18000c82f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c834  nop
0x18000c835  test    rbx, rbx
0x18000c838  jz      short loc_18000C843
0x18000c83a  mov     rcx, rbx; Block
0x18000c83d  call    cs:__imp_free
0x18000c843  mov     eax, esi
0x18000c845  lea     r11, [rsp+98h+var_28]
0x18000c84a  mov     rbx, [r11+30h]
0x18000c84e  mov     rsi, [r11+40h]
0x18000c852  mov     rsp, r11
0x18000c855  pop     r15
0x18000c857  pop     r14
0x18000c859  pop     r13
0x18000c85b  pop     r12
0x18000c85d  pop     rdi
0x18000c85e  retn
```
