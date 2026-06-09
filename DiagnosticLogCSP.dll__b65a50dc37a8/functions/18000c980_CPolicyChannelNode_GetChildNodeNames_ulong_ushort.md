# CPolicyChannelNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x18000c980`
- end: `0x18000ce18`
- name: `?GetChildNodeNames@CPolicyChannelNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1176`
- prototype: `__int64 __fastcall(CPolicyChannelNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180001bb4`
- `0x18000c120`
- `0x18000c980`
- `0x180012e00`
- `0x180013570`
- `0x180013870`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cdef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000caf9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ccb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000caf9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ccb9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccda`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
__int64 __fastcall CPolicyChannelNode::GetChildNodeNames(
        CPolicyChannelNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
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
  v5 = this;
  v6 = 0;
  v34 = 0;
  v35 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    LODWORD(this) = *((_DWORD *)this + 11) - 33;
    if ( (_DWORD)this )
    {
      if ( (_DWORD)this == 1 )
      {
        this = (CPolicyChannelNode *)*((_QWORD *)v5 + 3);
        if ( this )
        {
          v38 = 0;
          RegisteredChannels = (*(__int64 (__fastcall **)(CPolicyChannelNode *, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
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
                  LODWORD(this) = hKey[0];
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
              LODWORD(this) = hKey[0];
              if ( hKey[0] )
                RegCloseKey(hKey[0]);
LABEL_61:
              v6 = v34;
            }
            else
            {
              RegisteredChannels = -2147024882;
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v32);
              LODWORD(this) = hKey[0];
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v37) = RegisteredChannels;
    if ( a2 )
      v30 = *a2;
    else
      v30 = -1;
    LODWORD(v38) = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_1800411C9,
      (_DWORD)a3,
      (_DWORD)v5,
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
0x18000c980  mov     rax, rsp
0x18000c983  mov     [rax+8], rbx
0x18000c987  mov     [rax+18h], rsi
0x18000c98b  mov     [rax+10h], rdx
0x18000c98f  push    rdi
0x18000c990  push    r12
0x18000c992  push    r13
0x18000c994  push    r14
0x18000c996  push    r15
0x18000c998  sub     rsp, 70h
0x18000c99c  mov     r13, r8
0x18000c99f  mov     r15, rdx
0x18000c9a2  mov     r9, rcx
0x18000c9a5  xor     edi, edi
0x18000c9a7  mov     ebx, edi
0x18000c9a9  mov     [rax-58h], rbx
0x18000c9ad  mov     [rax-50h], rdi
0x18000c9b1  test    rdx, rdx
0x18000c9b4  jz      loc_18000CD95
0x18000c9ba  test    r8, r8
0x18000c9bd  jz      loc_18000CD95
0x18000c9c3  mov     [rdx], edi
0x18000c9c5  mov     [r8], rdi
0x18000c9c8  mov     ecx, [rcx+2Ch]
0x18000c9cb  sub     ecx, 21h ; '!'
0x18000c9ce  jz      loc_18000CBF9
0x18000c9d4  cmp     ecx, 1
0x18000c9d7  jz      short loc_18000C9E8
0x18000c9d9  mov     [rdx], edi
0x18000c9db  mov     [r8], rdi
0x18000c9de  mov     esi, 86000011h
0x18000c9e3  jmp     loc_18000CD9A
0x18000c9e8  mov     rcx, [r9+18h]
0x18000c9ec  test    rcx, rcx
0x18000c9ef  jz      loc_18000CBEF
0x18000c9f5  mov     [rsp+98h+arg_18], rdi
0x18000c9fd  mov     rax, [rcx]
0x18000ca00  lea     r8, [rsp+98h+arg_18]
0x18000ca08  mov     edx, 3
0x18000ca0d  mov     rax, [rax+58h]
0x18000ca11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca16  mov     esi, eax
0x18000ca18  test    eax, eax
0x18000ca1a  js      loc_18000CBF4
0x18000ca20  mov     rdx, [rsp+98h+arg_18]; unsigned __int16 *
0x18000ca28  lea     rcx, [rsp+98h+hKey]; this
0x18000ca2d  call    ??0CPolicyChannel@@QEAA@PEBG@Z; CPolicyChannel::CPolicyChannel(ushort const *)
0x18000ca32  nop
0x18000ca33  mov     [rsp+98h+var_68], rdi
0x18000ca38  mov     [rsp+98h+var_60], rdi
0x18000ca3d  mov     ecx, 40h ; '@'; Size
0x18000ca42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca47  mov     [rax], rax
0x18000ca4a  mov     [rax+8], rax
0x18000ca4e  mov     [rax+10h], rax
0x18000ca52  mov     word ptr [rax+18h], 101h
0x18000ca58  mov     [rsp+98h+var_68], rax
0x18000ca5d  lea     rdx, [rsp+98h+var_68]
0x18000ca62  lea     rcx, [rsp+98h+hKey]
0x18000ca67  call    ?GetValueNames@CPolicyChannel@@QEAAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CPolicyChannel::GetValueNames(std::set<std::wstring> &)
0x18000ca6c  mov     rcx, [rsp+98h+var_60]
0x18000ca71  shl     rcx, 3; cb
0x18000ca75  call    cs:__imp_CoTaskMemAlloc
0x18000ca7c  nop     dword ptr [rax+rax+00h]
0x18000ca81  mov     r12, rax
0x18000ca84  test    rax, rax
0x18000ca87  jnz     short loc_18000CAB5
0x18000ca89  mov     esi, 8007000Eh
0x18000ca8e  lea     rcx, [rsp+98h+var_68]
0x18000ca93  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000ca98  nop
0x18000ca99  mov     rcx, [rsp+98h+hKey]; hKey
0x18000ca9e  test    rcx, rcx
0x18000caa1  jz      short loc_18000CAB0
0x18000caa3  call    cs:__imp_RegCloseKey
0x18000caaa  nop     dword ptr [rax+rax+00h]
0x18000caaf  nop
0x18000cab0  jmp     loc_18000CD9A
0x18000cab5  mov     rax, [rsp+98h+var_60]
0x18000caba  lea     rcx, ds:0[rax*8]
0x18000cac2  mov     rax, r12
0x18000cac5  test    rcx, rcx
0x18000cac8  jz      short loc_18000CAD6
0x18000caca  mov     [rax], dil
0x18000cacd  inc     rax
0x18000cad0  sub     rcx, 1
0x18000cad4  jnz     short loc_18000CACA
0x18000cad6  mov     r14d, edi
0x18000cad9  mov     rbx, [rsp+98h+var_68]
0x18000cade  mov     rbx, [rbx]
0x18000cae1  cmp     [rbx+19h], dil
0x18000cae5  jnz     loc_18000CBBE
0x18000caeb  lea     rcx, [rbx+20h]
0x18000caef  cmp     qword ptr [rcx+18h], 7
0x18000caf4  jbe     short loc_18000CAF9
0x18000caf6  mov     rcx, [rcx]; psz
0x18000caf9  call    cs:__imp_SysAllocString
0x18000cb00  nop     dword ptr [rax+rax+00h]
0x18000cb05  mov     rcx, rax
0x18000cb08  movsxd  rax, r14d
0x18000cb0b  mov     [r12+rax*8], rcx
0x18000cb0f  test    rcx, rcx
0x18000cb12  jnz     short loc_18000CB6C
0x18000cb14  jmp     short loc_18000CB26
0x18000cb16  mov     rcx, [r12+r14*8]; bstrString
0x18000cb1a  call    cs:__imp_SysFreeString
0x18000cb21  nop     dword ptr [rax+rax+00h]
0x18000cb26  sub     r14d, 1
0x18000cb2a  jns     short loc_18000CB16
0x18000cb2c  mov     rcx, r12; pv
0x18000cb2f  call    cs:__imp_CoTaskMemFree
0x18000cb36  nop     dword ptr [rax+rax+00h]
0x18000cb3b  mov     esi, 8007000Eh
0x18000cb40  lea     rcx, [rsp+98h+var_68]
0x18000cb45  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cb4a  nop
0x18000cb4b  mov     rcx, [rsp+98h+hKey]; hKey
0x18000cb50  test    rcx, rcx
0x18000cb53  jz      short loc_18000CB62
0x18000cb55  call    cs:__imp_RegCloseKey
0x18000cb5c  nop     dword ptr [rax+rax+00h]
0x18000cb61  nop
0x18000cb62  mov     rbx, [rsp+98h+var_58]
0x18000cb67  jmp     loc_18000CD9A
0x18000cb6c  inc     r14d
0x18000cb6f  mov     rax, [rbx+10h]
0x18000cb73  cmp     [rax+19h], dil
0x18000cb77  jz      short loc_18000CB9A
0x18000cb79  mov     rax, [rbx+8]
0x18000cb7d  jmp     short loc_18000CB8C
0x18000cb7f  cmp     rbx, [rax+10h]
0x18000cb83  jnz     short loc_18000CB92
0x18000cb85  mov     rbx, rax
0x18000cb88  mov     rax, [rax+8]
0x18000cb8c  cmp     [rax+19h], dil
0x18000cb90  jz      short loc_18000CB7F
0x18000cb92  mov     rbx, rax
0x18000cb95  jmp     loc_18000CAE1
0x18000cb9a  mov     rbx, rax
0x18000cb9d  mov     rcx, [rax]
0x18000cba0  cmp     [rcx+19h], dil
0x18000cba4  jnz     loc_18000CAE1
0x18000cbaa  mov     rbx, rcx
0x18000cbad  mov     rax, [rcx]
0x18000cbb0  mov     rcx, rax
0x18000cbb3  cmp     [rax+19h], dil
0x18000cbb7  jz      short loc_18000CBAA
0x18000cbb9  jmp     loc_18000CAE1
0x18000cbbe  mov     [r13+0], r12
0x18000cbc2  mov     eax, dword ptr [rsp+98h+var_60]
0x18000cbc6  mov     [r15], eax
0x18000cbc9  lea     rcx, [rsp+98h+var_68]
0x18000cbce  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cbd3  nop
0x18000cbd4  mov     rcx, [rsp+98h+hKey]; hKey
0x18000cbd9  test    rcx, rcx
0x18000cbdc  jz      short loc_18000CBEA
0x18000cbde  call    cs:__imp_RegCloseKey
0x18000cbe5  nop     dword ptr [rax+rax+00h]
0x18000cbea  jmp     loc_18000CD7D
0x18000cbef  mov     esi, 80070057h
0x18000cbf4  jmp     loc_18000CD9A
0x18000cbf9  mov     [rsp+98h+var_68], rdi
0x18000cbfe  mov     [rsp+98h+var_60], rdi
0x18000cc03  mov     ecx, 40h ; '@'; Size
0x18000cc08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cc0d  mov     [rax], rax
0x18000cc10  mov     [rax+8], rax
0x18000cc14  mov     [rax+10h], rax
0x18000cc18  mov     word ptr [rax+18h], 101h
0x18000cc1e  mov     [rsp+98h+var_68], rax
0x18000cc23  lea     rcx, [rsp+98h+var_68]
0x18000cc28  call    ?GetRegisteredChannels@CPolicyChannel@@SAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CPolicyChannel::GetRegisteredChannels(std::set<std::wstring> &)
0x18000cc2d  mov     esi, eax
0x18000cc2f  test    eax, eax
0x18000cc31  jns     short loc_18000CC43
0x18000cc33  lea     rcx, [rsp+98h+var_68]
0x18000cc38  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cc3d  nop
0x18000cc3e  jmp     loc_18000CD9A
0x18000cc43  mov     rcx, [rsp+98h+var_60]
0x18000cc48  shl     rcx, 3; cb
0x18000cc4c  call    cs:__imp_CoTaskMemAlloc
0x18000cc53  nop     dword ptr [rax+rax+00h]
0x18000cc58  mov     r12, rax
0x18000cc5b  test    rax, rax
0x18000cc5e  jnz     short loc_18000CC75
0x18000cc60  mov     esi, 8007000Eh
0x18000cc65  lea     rcx, [rsp+98h+var_68]
0x18000cc6a  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cc6f  nop
0x18000cc70  jmp     loc_18000CD9A
0x18000cc75  mov     rax, [rsp+98h+var_60]
0x18000cc7a  lea     rcx, ds:0[rax*8]
0x18000cc82  mov     rax, r12
0x18000cc85  test    rcx, rcx
0x18000cc88  jz      short loc_18000CC96
0x18000cc8a  mov     [rax], dil
0x18000cc8d  inc     rax
0x18000cc90  sub     rcx, 1
0x18000cc94  jnz     short loc_18000CC8A
0x18000cc96  mov     r14d, edi
0x18000cc99  mov     rbx, [rsp+98h+var_68]
0x18000cc9e  mov     rbx, [rbx]
0x18000cca1  cmp     [rbx+19h], dil
0x18000cca5  jnz     loc_18000CD67
0x18000ccab  lea     rcx, [rbx+20h]
0x18000ccaf  cmp     qword ptr [rcx+18h], 7
0x18000ccb4  jbe     short loc_18000CCB9
0x18000ccb6  mov     rcx, [rcx]; psz
0x18000ccb9  call    cs:__imp_SysAllocString
0x18000ccc0  nop     dword ptr [rax+rax+00h]
0x18000ccc5  mov     rcx, rax
0x18000ccc8  movsxd  rax, r14d
0x18000cccb  mov     [r12+rax*8], rcx
0x18000cccf  test    rcx, rcx
0x18000ccd2  jnz     short loc_18000CD15
0x18000ccd4  jmp     short loc_18000CCE6
0x18000ccd6  mov     rcx, [r12+r14*8]; bstrString
0x18000ccda  call    cs:__imp_SysFreeString
0x18000cce1  nop     dword ptr [rax+rax+00h]
0x18000cce6  sub     r14d, 1
0x18000ccea  jns     short loc_18000CCD6
0x18000ccec  mov     rcx, r12; pv
0x18000ccef  call    cs:__imp_CoTaskMemFree
0x18000ccf6  nop     dword ptr [rax+rax+00h]
0x18000ccfb  mov     esi, 8007000Eh
0x18000cd00  lea     rcx, [rsp+98h+var_68]
0x18000cd05  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cd0a  nop
0x18000cd0b  mov     rbx, [rsp+98h+var_58]
0x18000cd10  jmp     loc_18000CD9A
0x18000cd15  inc     r14d
0x18000cd18  mov     rax, [rbx+10h]
0x18000cd1c  cmp     [rax+19h], dil
0x18000cd20  jz      short loc_18000CD43
0x18000cd22  mov     rax, [rbx+8]
0x18000cd26  jmp     short loc_18000CD35
0x18000cd28  cmp     rbx, [rax+10h]
0x18000cd2c  jnz     short loc_18000CD3B
0x18000cd2e  mov     rbx, rax
0x18000cd31  mov     rax, [rax+8]
0x18000cd35  cmp     [rax+19h], dil
0x18000cd39  jz      short loc_18000CD28
0x18000cd3b  mov     rbx, rax
0x18000cd3e  jmp     loc_18000CCA1
0x18000cd43  mov     rbx, rax
0x18000cd46  mov     rcx, [rax]
0x18000cd49  cmp     [rcx+19h], dil
0x18000cd4d  jnz     loc_18000CCA1
0x18000cd53  mov     rbx, rcx
0x18000cd56  mov     rax, [rcx]
0x18000cd59  mov     rcx, rax
0x18000cd5c  cmp     [rax+19h], dil
0x18000cd60  jz      short loc_18000CD53
0x18000cd62  jmp     loc_18000CCA1
0x18000cd67  mov     [r13+0], r12
0x18000cd6b  mov     eax, dword ptr [rsp+98h+var_60]
0x18000cd6f  mov     [r15], eax
0x18000cd72  lea     rcx, [rsp+98h+var_68]
0x18000cd77  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cd7c  nop
0x18000cd7d  jmp     short loc_18000CD8E
0x18000cd7f  mov     r15, [rsp+98h+arg_8]
0x18000cd87  mov     esi, dword ptr [rsp+98h+arg_18]
0x18000cd8e  mov     rbx, [rsp+98h+var_58]
0x18000cd93  jmp     short loc_18000CD9A
0x18000cd95  mov     esi, 80070057h
0x18000cd9a  mov     eax, cs:dword_18004AE90
0x18000cda0  cmp     eax, 5
0x18000cda3  jbe     short loc_18000CDE7
0x18000cda5  mov     dword ptr [rsp+98h+arg_8], esi
0x18000cdac  test    r15, r15
0x18000cdaf  jz      short loc_18000CDB6
0x18000cdb1  mov     eax, [r15]
0x18000cdb4  jmp     short loc_18000CDB9
0x18000cdb6  or      eax, 0FFFFFFFFh
0x18000cdb9  mov     dword ptr [rsp+98h+arg_18], eax
0x18000cdc0  lea     rax, [rsp+98h+arg_8]
0x18000cdc8  mov     [rsp+98h+var_70], rax
0x18000cdcd  lea     rax, [rsp+98h+arg_18]
0x18000cdd5  mov     [rsp+98h+var_78], rax
0x18000cdda  lea     rdx, byte_1800411C9
0x18000cde1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cde6  nop
0x18000cde7  test    rbx, rbx
0x18000cdea  jz      short loc_18000CDFB
0x18000cdec  mov     rcx, rbx; Block
0x18000cdef  call    cs:__imp_free
0x18000cdf6  nop     dword ptr [rax+rax+00h]
0x18000cdfb  mov     eax, esi
0x18000cdfd  lea     r11, [rsp+98h+var_28]
0x18000ce02  mov     rbx, [r11+30h]
0x18000ce06  mov     rsi, [r11+40h]
0x18000ce0a  mov     rsp, r11
0x18000ce0d  pop     r15
0x18000ce0f  pop     r14
0x18000ce11  pop     r13
0x18000ce13  pop     r12
0x18000ce15  pop     rdi
  ... truncated ...
```
