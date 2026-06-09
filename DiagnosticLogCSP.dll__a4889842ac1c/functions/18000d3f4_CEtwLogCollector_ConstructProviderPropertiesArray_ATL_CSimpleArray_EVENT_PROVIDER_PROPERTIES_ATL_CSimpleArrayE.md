# CEtwLogCollector::ConstructProviderPropertiesArray(ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)

- ea: `0x18000d3f4`
- end: `0x18000d709`
- name: `?ConstructProviderPropertiesArray@CEtwLogCollector@@AEAAJAEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CEtwLogCollector *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e7e8`

## callees

- `0x180001b60`
- `0x180002b88`
- `0x180006518`
- `0x1800073e0`
- `0x18000967c`
- `0x18000d3f4`
- `0x18000d920`
- `0x18000d9e0`
- `0x18000dc40`
- `0x18000df44`
- `0x180010ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d614`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000d614`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d67e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d69a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d67e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d69a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d5d0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d5d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d497`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d497`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d669`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d669`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::ConstructProviderPropertiesArray(CEtwLogCollector *a1, __int64 a2)
{
  LPCWSTR *v3; // rdi
  int v4; // r14d
  __int64 v5; // rcx
  HRESULT IsProviderEnabled; // ebx
  LPCWSTR *v7; // rsi
  int v8; // r12d
  __int64 v9; // r15
  CEtwLogCollector *v10; // r14
  int i; // r15d
  __int64 j; // rsi
  CEtwLogCollector *v13; // r15
  GUID *v14; // rax
  GUID *v15; // r15
  unsigned __int8 v16; // cl
  int v17; // r12d
  unsigned int v18; // r12d
  bool v19; // sf
  __int64 v20; // rax
  GUID **v21; // rdx
  int k; // esi
  int v24; // [rsp+20h] [rbp-79h] BYREF
  void *Block; // [rsp+28h] [rbp-71h] BYREF
  __int64 v26; // [rsp+30h] [rbp-69h]
  LPCWSTR *v27; // [rsp+38h] [rbp-61h] BYREF
  __int64 v28; // [rsp+40h] [rbp-59h]
  CEtwLogCollector *v29; // [rsp+48h] [rbp-51h]
  BYTE Data[16]; // [rsp+50h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-39h] BYREF

  v29 = a1;
  v3 = 0;
  v27 = 0;
  v4 = 0;
  v28 = 0;
  v24 = 0;
  *(_QWORD *)Data = 0;
  Block = 0;
  v26 = 0;
  IsProviderEnabled = CRegUtils::EnumChildKeys(a1, &Block);
  v7 = (LPCWSTR *)Block;
  v8 = v26;
  if ( IsProviderEnabled >= 0 )
  {
    v9 = 0;
    if ( (int)v26 > 0 )
    {
      v10 = v29;
      do
      {
        LODWORD(Block) = 0;
        if ( (int)v9 >= v8 )
        {
          ATL::_AtlRaiseException(0xC000008C);
          __debugbreak();
        }
        IsProviderEnabled = CEtwLogCollector::IsProviderEnabled(v10, v7[v9], (int *)&Block);
        if ( IsProviderEnabled < 0 )
          break;
        if ( (_DWORD)Block )
        {
          Block = SysAllocString(v7[v9]);
          if ( !Block )
          {
            IsProviderEnabled = -2147024882;
            break;
          }
          ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(&v27, &Block);
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (int)v9 < v8 );
      v4 = v28;
      v3 = v27;
    }
  }
  for ( i = 0; i < (unsigned int)v8; ++i )
  {
    if ( i < 0 || i >= v8 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      JUMPOUT(0x18000D708LL);
    }
    SysFreeString((BSTR)v7[i]);
  }
  if ( v7 )
    free(v7);
  if ( IsProviderEnabled >= 0 )
  {
    for ( j = 0; (int)j < v4; j = (unsigned int)(j + 1) )
    {
      v13 = v29;
      IsProviderEnabled = CEtwLogCollector::GetTraceLevel(v29, v3[j], &v24);
      if ( IsProviderEnabled < 0 )
        break;
      IsProviderEnabled = CEtwLogCollector::GetKeywords(v13, v3[j], Data);
      if ( IsProviderEnabled < 0 )
        break;
      v14 = (GUID *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( !v14 )
      {
        IsProviderEnabled = -2147024882;
        break;
      }
      v16 = v24;
      *v14 = 0;
      v14[1] = 0;
      v14[1].Data4[0] = v16;
      *(_DWORD *)&v14[1].Data4[4] = 1;
      *(_QWORD *)&v14[1].Data1 = *(_QWORD *)Data;
      IsProviderEnabled = StringCchPrintfW(sz, 0x27u, L"{%s}", v3[j]);
      if ( IsProviderEnabled < 0 )
        break;
      IsProviderEnabled = CLSIDFromString(sz, v15);
      if ( IsProviderEnabled < 0 )
      {
        IsProviderEnabled = -2147024809;
        break;
      }
      v17 = *(_DWORD *)(a2 + 8);
      if ( v17 != *(_DWORD *)(a2 + 12) )
        goto LABEL_33;
      if ( *(_DWORD *)(a2 + 12) )
      {
        v19 = (v17 & 0x40000000) != 0;
        v18 = 2 * v17;
        if ( v19 )
          continue;
      }
      else
      {
        v18 = 1;
      }
      if ( v18 <= 0xFFFFFFFuLL )
      {
        v20 = _o__recalloc(*(_QWORD *)a2, v18, 8);
        if ( v20 )
        {
          *(_DWORD *)(a2 + 12) = v18;
          *(_QWORD *)a2 = v20;
LABEL_33:
          v5 = *(int *)(a2 + 8);
          v21 = (GUID **)(*(_QWORD *)a2 + 8 * v5);
          if ( v21 )
            *v21 = v15;
          ++*(_DWORD *)(a2 + 8);
        }
      }
    }
  }
  for ( k = 0; k < (unsigned int)v4; ++k )
  {
    if ( k < 0 || k >= v4 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    SysFreeString((BSTR)v3[k]);
  }
  if ( v3 )
    free(v3);
  if ( IsProviderEnabled < 0 )
    CEtwLogCollector::FreeProviderPropertiesArray(v5, a2);
  return (unsigned int)IsProviderEnabled;
}

```

## disassembly

```asm
0x18000d3f4  mov     [rsp-8+arg_10], rbx
0x18000d3f9  push    rbp
0x18000d3fa  push    rsi
0x18000d3fb  push    rdi
0x18000d3fc  push    r12
0x18000d3fe  push    r13
0x18000d400  push    r14
0x18000d402  push    r15
0x18000d404  lea     rbp, [rsp-27h]
0x18000d409  sub     rsp, 0C0h
0x18000d410  mov     rax, cs:__security_cookie
0x18000d417  xor     rax, rsp
0x18000d41a  mov     [rbp+57h+var_40], rax
0x18000d41e  mov     rax, rcx
0x18000d421  mov     [rbp+57h+var_A8], rcx
0x18000d425  xor     ecx, ecx
0x18000d427  mov     r13, rdx
0x18000d42a  mov     edi, ecx
0x18000d42c  mov     [rbp+57h+var_B8], rcx
0x18000d430  mov     r14d, ecx
0x18000d433  mov     [rbp+57h+var_B0], rcx
0x18000d437  mov     [rbp+57h+var_D0], ecx
0x18000d43a  lea     rdx, [rbp+57h+Block]
0x18000d43e  mov     qword ptr [rbp+57h+Data], rcx
0x18000d442  mov     [rbp+57h+Block], rcx
0x18000d446  mov     [rbp+57h+var_C0], rcx
0x18000d44a  mov     rcx, rax
0x18000d44d  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000d452  mov     ebx, eax
0x18000d454  mov     rsi, [rbp+57h+Block]
0x18000d458  mov     r12d, dword ptr [rbp+57h+var_C0]
0x18000d45c  test    eax, eax
0x18000d45e  js      short loc_18000D4CA
0x18000d460  xor     r15d, r15d
0x18000d463  test    r12d, r12d
0x18000d466  jle     short loc_18000D4CA
0x18000d468  mov     r14, [rbp+57h+var_A8]
0x18000d46c  mov     dword ptr [rbp+57h+Block], edi
0x18000d46f  cmp     r15d, r12d
0x18000d472  jge     loc_18000D6F3
0x18000d478  mov     rdx, [rsi+r15*8]; lpSubKey
0x18000d47c  lea     r8, [rbp+57h+Block]; int *
0x18000d480  mov     rcx, r14; this
0x18000d483  call    ?IsProviderEnabled@CEtwLogCollector@@QEAAJPEBGAEAH@Z; CEtwLogCollector::IsProviderEnabled(ushort const *,int &)
0x18000d488  mov     ebx, eax
0x18000d48a  test    eax, eax
0x18000d48c  js      short loc_18000D4C2
0x18000d48e  cmp     dword ptr [rbp+57h+Block], edi
0x18000d491  jz      short loc_18000D4B3
0x18000d493  mov     rcx, [rsi+r15*8]; psz
0x18000d497  call    cs:__imp_SysAllocString
0x18000d49d  mov     [rbp+57h+Block], rax
0x18000d4a1  test    rax, rax
0x18000d4a4  jz      short loc_18000D4BD
0x18000d4a6  lea     rdx, [rbp+57h+Block]
0x18000d4aa  lea     rcx, [rbp+57h+var_B8]
0x18000d4ae  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x18000d4b3  inc     r15d
0x18000d4b6  cmp     r15d, r12d
0x18000d4b9  jl      short loc_18000D46C
0x18000d4bb  jmp     short loc_18000D4C2
0x18000d4bd  mov     ebx, 8007000Eh
0x18000d4c2  mov     r14d, dword ptr [rbp+57h+var_B0]
0x18000d4c6  mov     rdi, [rbp+57h+var_B8]
0x18000d4ca  xor     r15d, r15d
0x18000d4cd  test    r12d, r12d
0x18000d4d0  jz      short loc_18000D4F9
0x18000d4d2  test    r15d, r15d
0x18000d4d5  js      loc_18000D6FE
0x18000d4db  cmp     r15d, r12d
0x18000d4de  jge     loc_18000D6FE
0x18000d4e4  movsxd  rcx, r15d
0x18000d4e7  mov     rcx, [rsi+rcx*8]; bstrString
0x18000d4eb  call    cs:__imp_SysFreeString
0x18000d4f1  inc     r15d
0x18000d4f4  cmp     r15d, r12d
0x18000d4f7  jb      short loc_18000D4D2
0x18000d4f9  test    rsi, rsi
0x18000d4fc  jz      short loc_18000D516
0x18000d4fe  mov     rcx, rsi; Block
0x18000d501  call    cs:__imp_free
0x18000d507  xor     esi, esi
0x18000d509  test    rsi, rsi
0x18000d50c  jz      short loc_18000D516
0x18000d50e  mov     ecx, esi; Block
0x18000d510  call    cs:__imp_free
0x18000d516  test    ebx, ebx
0x18000d518  js      loc_18000D64A
0x18000d51e  xor     esi, esi
0x18000d520  test    r14d, r14d
0x18000d523  jle     loc_18000D64A
0x18000d529  cmp     esi, r14d
0x18000d52c  jge     loc_18000D6DD
0x18000d532  mov     r15, [rbp+57h+var_A8]
0x18000d536  lea     r8, [rbp+57h+var_D0]; int *
0x18000d53a  mov     rdx, [rdi+rsi*8]; lpSubKey
0x18000d53e  mov     rcx, r15; this
0x18000d541  call    ?GetTraceLevel@CEtwLogCollector@@QEAAJPEBGAEAJ@Z; CEtwLogCollector::GetTraceLevel(ushort const *,long &)
0x18000d546  mov     ebx, eax
0x18000d548  test    eax, eax
0x18000d54a  js      loc_18000D64A
0x18000d550  mov     rdx, [rdi+rsi*8]; lpSubKey
0x18000d554  lea     r8, [rbp+57h+Data]; lpData
0x18000d558  mov     rcx, r15; this
0x18000d55b  call    ?GetKeywords@CEtwLogCollector@@QEAAJPEBGAEA_K@Z; CEtwLogCollector::GetKeywords(ushort const *,unsigned __int64 &)
0x18000d560  mov     ebx, eax
0x18000d562  test    eax, eax
0x18000d564  js      loc_18000D64A
0x18000d56a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d571  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d576  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d57b  mov     r15, rax
0x18000d57e  test    rax, rax
0x18000d581  jz      loc_18000D6D3
0x18000d587  mov     cl, byte ptr [rbp+57h+var_D0]
0x18000d58a  lea     r8, aS; "{%s}"
0x18000d591  xorps   xmm0, xmm0
0x18000d594  mov     edx, 27h ; '''; unsigned __int64
0x18000d599  movups  xmmword ptr [rax], xmm0
0x18000d59c  movups  xmmword ptr [rax+10h], xmm0
0x18000d5a0  mov     [rax+18h], cl
0x18000d5a3  mov     dword ptr [rax+1Ch], 1
0x18000d5aa  mov     rcx, qword ptr [rbp+57h+Data]
0x18000d5ae  mov     [rax+10h], rcx
0x18000d5b2  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18000d5b6  mov     r9, [rdi+rsi*8]
0x18000d5ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d5bf  mov     ebx, eax
0x18000d5c1  test    eax, eax
0x18000d5c3  js      loc_18000D64A
0x18000d5c9  mov     rdx, r15; pclsid
0x18000d5cc  lea     rcx, [rbp+57h+sz]; lpsz
0x18000d5d0  call    cs:__imp_CLSIDFromString
0x18000d5d6  mov     ebx, eax
0x18000d5d8  test    eax, eax
0x18000d5da  js      loc_18000D6C9
0x18000d5e0  mov     r12d, [r13+8]
0x18000d5e4  cmp     r12d, [r13+0Ch]
0x18000d5e8  jnz     short loc_18000D627
0x18000d5ea  cmp     dword ptr [r13+0Ch], 0
0x18000d5ef  jnz     short loc_18000D5F9
0x18000d5f1  mov     r12d, 1
0x18000d5f7  jmp     short loc_18000D5FE
0x18000d5f9  add     r12d, r12d
0x18000d5fc  js      short loc_18000D63F
0x18000d5fe  mov     edx, r12d
0x18000d601  cmp     rdx, 0FFFFFFFh
0x18000d608  ja      short loc_18000D63F
0x18000d60a  mov     rcx, [r13+0]
0x18000d60e  mov     r8d, 8
0x18000d614  call    cs:__imp__o__recalloc
0x18000d61a  test    rax, rax
0x18000d61d  jz      short loc_18000D63F
0x18000d61f  mov     [r13+0Ch], r12d
0x18000d623  mov     [r13+0], rax
0x18000d627  movsxd  rcx, dword ptr [r13+8]
0x18000d62b  mov     rax, [r13+0]
0x18000d62f  lea     rdx, [rax+rcx*8]; unsigned int
0x18000d633  test    rdx, rdx
0x18000d636  jz      short loc_18000D63B
0x18000d638  mov     [rdx], r15
0x18000d63b  inc     dword ptr [r13+8]
0x18000d63f  inc     esi
0x18000d641  cmp     esi, r14d
0x18000d644  jl      loc_18000D532
0x18000d64a  xor     esi, esi
0x18000d64c  test    r14d, r14d
0x18000d64f  jz      short loc_18000D676
0x18000d651  test    esi, esi
0x18000d653  js      loc_18000D6E8
0x18000d659  cmp     esi, r14d
0x18000d65c  jge     loc_18000D6E8
0x18000d662  movsxd  rcx, esi
0x18000d665  mov     rcx, [rdi+rcx*8]; bstrString
0x18000d669  call    cs:__imp_SysFreeString
0x18000d66f  inc     esi
0x18000d671  cmp     esi, r14d
0x18000d674  jb      short loc_18000D651
0x18000d676  test    rdi, rdi
0x18000d679  jz      short loc_18000D686
0x18000d67b  mov     rcx, rdi; Block
0x18000d67e  call    cs:__imp_free
0x18000d684  xor     edi, edi
0x18000d686  test    ebx, ebx
0x18000d688  jns     short loc_18000D692
0x18000d68a  mov     rdx, r13
0x18000d68d  call    ?FreeProviderPropertiesArray@CEtwLogCollector@@AEAAXAEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z; CEtwLogCollector::FreeProviderPropertiesArray(ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)
0x18000d692  test    rdi, rdi
0x18000d695  jz      short loc_18000D6A0
0x18000d697  mov     rcx, rdi; Block
0x18000d69a  call    cs:__imp_free
0x18000d6a0  mov     eax, ebx
0x18000d6a2  mov     rcx, [rbp+57h+var_40]
0x18000d6a6  xor     rcx, rsp; StackCookie
0x18000d6a9  call    __security_check_cookie
0x18000d6ae  mov     rbx, [rsp+0F0h+arg_10]
0x18000d6b6  add     rsp, 0C0h
0x18000d6bd  pop     r15
0x18000d6bf  pop     r14
0x18000d6c1  pop     r13
0x18000d6c3  pop     r12
0x18000d6c5  pop     rdi
0x18000d6c6  pop     rsi
0x18000d6c7  pop     rbp
0x18000d6c8  retn
0x18000d6c9  mov     ebx, 80070057h
0x18000d6ce  jmp     loc_18000D64A
0x18000d6d3  mov     ebx, 8007000Eh
0x18000d6d8  jmp     loc_18000D64A
0x18000d6dd  mov     ecx, 0C000008Ch; unsigned int
0x18000d6e2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000d6e7  int     3; Trap to Debugger
0x18000d6e8  mov     ecx, 0C000008Ch; unsigned int
0x18000d6ed  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000d6f2  int     3; Trap to Debugger
0x18000d6f3  mov     ecx, 0C000008Ch; unsigned int
0x18000d6f8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000d6fd  int     3; Trap to Debugger
0x18000d6fe  mov     ecx, 0C000008Ch; unsigned int
0x18000d703  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
