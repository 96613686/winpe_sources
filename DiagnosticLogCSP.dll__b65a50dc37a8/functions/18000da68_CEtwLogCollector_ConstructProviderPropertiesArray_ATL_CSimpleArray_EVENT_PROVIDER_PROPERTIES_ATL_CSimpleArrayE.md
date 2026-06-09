# CEtwLogCollector::ConstructProviderPropertiesArray(ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)

- ea: `0x18000da68`
- end: `0x18000ddb4`
- name: `?ConstructProviderPropertiesArray@CEtwLogCollector@@AEAAJAEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ef14`

## callees

- `0x180001b90`
- `0x180002bb8`
- `0x180006498`
- `0x180007530`
- `0x18000990c`
- `0x18000da68`
- `0x18000dfd8`
- `0x18000e09c`
- `0x18000e314`
- `0x18000e628`
- `0x180011770`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000dca6`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000dca6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db81`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db96`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dd1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dd3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db81`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db96`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dd1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dd3e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000dc5c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000dc5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000db0b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000db0b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db65`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd01`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db65`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd01`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::ConstructProviderPropertiesArray(CEtwLogCollector *a1, __int64 a2)
{
  LPCWSTR *v3; // rdi
  int v4; // r14d
  GUID **v5; // rdx
  __int64 v6; // rcx
  HRESULT IsProviderEnabled; // ebx
  LPCWSTR *v8; // rsi
  int v9; // r12d
  __int64 v10; // r15
  CEtwLogCollector *v11; // r14
  int i; // r15d
  __int64 j; // rsi
  CEtwLogCollector *v14; // r15
  GUID *v15; // rax
  GUID *v16; // r15
  unsigned __int8 v17; // cl
  int v18; // r12d
  unsigned int v19; // r12d
  bool v20; // sf
  __int64 v21; // rax
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
  v8 = (LPCWSTR *)Block;
  v9 = v26;
  if ( IsProviderEnabled >= 0 )
  {
    v10 = 0;
    if ( (int)v26 > 0 )
    {
      v11 = v29;
      do
      {
        LODWORD(Block) = 0;
        if ( (int)v10 >= v9 )
        {
          ATL::_AtlRaiseException(0xC000008C, (unsigned int)v5);
          __debugbreak();
        }
        IsProviderEnabled = CEtwLogCollector::IsProviderEnabled(v11, v8[v10], (int *)&Block);
        if ( IsProviderEnabled < 0 )
          break;
        if ( (_DWORD)Block )
        {
          Block = SysAllocString(v8[v10]);
          if ( !Block )
          {
            IsProviderEnabled = -2147024882;
            break;
          }
          ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(&v27, &Block);
        }
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (int)v10 < v9 );
      v4 = v28;
      v3 = v27;
    }
  }
  for ( i = 0; i < (unsigned int)v9; ++i )
  {
    if ( i < 0 || i >= v9 )
    {
      ATL::_AtlRaiseException(0xC000008C, (unsigned int)v5);
      JUMPOUT(0x18000DDB3LL);
    }
    SysFreeString((BSTR)v8[i]);
  }
  if ( v8 )
    free(v8);
  if ( IsProviderEnabled >= 0 )
  {
    for ( j = 0; (int)j < v4; j = (unsigned int)(j + 1) )
    {
      v14 = v29;
      IsProviderEnabled = CEtwLogCollector::GetTraceLevel(v29, v3[j], &v24);
      if ( IsProviderEnabled < 0 )
        break;
      IsProviderEnabled = CEtwLogCollector::GetKeywords(v14, v3[j], Data);
      if ( IsProviderEnabled < 0 )
        break;
      v15 = (GUID *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      if ( !v15 )
      {
        IsProviderEnabled = -2147024882;
        break;
      }
      v17 = v24;
      *v15 = 0;
      v15[1] = 0;
      v15[1].Data4[0] = v17;
      *(_DWORD *)&v15[1].Data4[4] = 1;
      *(_QWORD *)&v15[1].Data1 = *(_QWORD *)Data;
      IsProviderEnabled = StringCchPrintfW(sz, 0x27u, L"{%s}", v3[j]);
      if ( IsProviderEnabled < 0 )
        break;
      IsProviderEnabled = CLSIDFromString(sz, v16);
      if ( IsProviderEnabled < 0 )
      {
        IsProviderEnabled = -2147024809;
        break;
      }
      v18 = *(_DWORD *)(a2 + 8);
      if ( v18 != *(_DWORD *)(a2 + 12) )
        goto LABEL_33;
      if ( *(_DWORD *)(a2 + 12) )
      {
        v20 = (v18 & 0x40000000) != 0;
        v19 = 2 * v18;
        if ( v20 )
          continue;
      }
      else
      {
        v19 = 1;
      }
      LODWORD(v5) = v19;
      if ( v19 <= 0xFFFFFFFuLL )
      {
        v21 = _o__recalloc(*(_QWORD *)a2, v19, 8);
        if ( v21 )
        {
          *(_DWORD *)(a2 + 12) = v19;
          *(_QWORD *)a2 = v21;
LABEL_33:
          v6 = *(int *)(a2 + 8);
          v5 = (GUID **)(*(_QWORD *)a2 + 8 * v6);
          if ( v5 )
            *v5 = v16;
          ++*(_DWORD *)(a2 + 8);
        }
      }
    }
  }
  for ( k = 0; k < (unsigned int)v4; ++k )
  {
    if ( k < 0 || k >= v4 )
    {
      ATL::_AtlRaiseException(0xC000008C, (unsigned int)v5);
      __debugbreak();
    }
    SysFreeString((BSTR)v3[k]);
  }
  if ( v3 )
    free(v3);
  if ( IsProviderEnabled < 0 )
    CEtwLogCollector::FreeProviderPropertiesArray(v6, a2);
  return (unsigned int)IsProviderEnabled;
}

```

## disassembly

```asm
0x18000da68  mov     [rsp-8+arg_10], rbx
0x18000da6d  push    rbp
0x18000da6e  push    rsi
0x18000da6f  push    rdi
0x18000da70  push    r12
0x18000da72  push    r13
0x18000da74  push    r14
0x18000da76  push    r15
0x18000da78  lea     rbp, [rsp-27h]
0x18000da7d  sub     rsp, 0C0h
0x18000da84  mov     rax, cs:__security_cookie
0x18000da8b  xor     rax, rsp
0x18000da8e  mov     [rbp+57h+var_40], rax
0x18000da92  mov     rax, rcx
0x18000da95  mov     [rbp+57h+var_A8], rcx
0x18000da99  xor     ecx, ecx
0x18000da9b  mov     r13, rdx
0x18000da9e  mov     edi, ecx
0x18000daa0  mov     [rbp+57h+var_B8], rcx
0x18000daa4  mov     r14d, ecx
0x18000daa7  mov     [rbp+57h+var_B0], rcx
0x18000daab  mov     [rbp+57h+var_D0], ecx
0x18000daae  lea     rdx, [rbp+57h+Block]
0x18000dab2  mov     qword ptr [rbp+57h+Data], rcx
0x18000dab6  mov     [rbp+57h+Block], rcx
0x18000daba  mov     [rbp+57h+var_C0], rcx
0x18000dabe  mov     rcx, rax
0x18000dac1  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000dac6  mov     ebx, eax
0x18000dac8  mov     rsi, [rbp+57h+Block]
0x18000dacc  mov     r12d, dword ptr [rbp+57h+var_C0]
0x18000dad0  test    eax, eax
0x18000dad2  js      short loc_18000DB44
0x18000dad4  xor     r15d, r15d
0x18000dad7  test    r12d, r12d
0x18000dada  jle     short loc_18000DB44
0x18000dadc  mov     r14, [rbp+57h+var_A8]
0x18000dae0  mov     dword ptr [rbp+57h+Block], edi
0x18000dae3  cmp     r15d, r12d
0x18000dae6  jge     loc_18000DD9E
0x18000daec  mov     rdx, [rsi+r15*8]; lpSubKey
0x18000daf0  lea     r8, [rbp+57h+Block]; int *
0x18000daf4  mov     rcx, r14; this
0x18000daf7  call    ?IsProviderEnabled@CEtwLogCollector@@QEAAJPEBGAEAH@Z; CEtwLogCollector::IsProviderEnabled(ushort const *,int &)
0x18000dafc  mov     ebx, eax
0x18000dafe  test    eax, eax
0x18000db00  js      short loc_18000DB3C
0x18000db02  cmp     dword ptr [rbp+57h+Block], edi
0x18000db05  jz      short loc_18000DB2D
0x18000db07  mov     rcx, [rsi+r15*8]; psz
0x18000db0b  call    cs:__imp_SysAllocString
0x18000db12  nop     dword ptr [rax+rax+00h]
0x18000db17  mov     [rbp+57h+Block], rax
0x18000db1b  test    rax, rax
0x18000db1e  jz      short loc_18000DB37
0x18000db20  lea     rdx, [rbp+57h+Block]
0x18000db24  lea     rcx, [rbp+57h+var_B8]
0x18000db28  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x18000db2d  inc     r15d
0x18000db30  cmp     r15d, r12d
0x18000db33  jl      short loc_18000DAE0
0x18000db35  jmp     short loc_18000DB3C
0x18000db37  mov     ebx, 8007000Eh
0x18000db3c  mov     r14d, dword ptr [rbp+57h+var_B0]
0x18000db40  mov     rdi, [rbp+57h+var_B8]
0x18000db44  xor     r15d, r15d
0x18000db47  test    r12d, r12d
0x18000db4a  jz      short loc_18000DB79
0x18000db4c  test    r15d, r15d
0x18000db4f  js      loc_18000DDA9
0x18000db55  cmp     r15d, r12d
0x18000db58  jge     loc_18000DDA9
0x18000db5e  movsxd  rcx, r15d
0x18000db61  mov     rcx, [rsi+rcx*8]; bstrString
0x18000db65  call    cs:__imp_SysFreeString
0x18000db6c  nop     dword ptr [rax+rax+00h]
0x18000db71  inc     r15d
0x18000db74  cmp     r15d, r12d
0x18000db77  jb      short loc_18000DB4C
0x18000db79  test    rsi, rsi
0x18000db7c  jz      short loc_18000DBA2
0x18000db7e  mov     rcx, rsi; Block
0x18000db81  call    cs:__imp_free
0x18000db88  nop     dword ptr [rax+rax+00h]
0x18000db8d  xor     esi, esi
0x18000db8f  test    rsi, rsi
0x18000db92  jz      short loc_18000DBA2
0x18000db94  mov     ecx, esi; Block
0x18000db96  call    cs:__imp_free
0x18000db9d  nop     dword ptr [rax+rax+00h]
0x18000dba2  test    ebx, ebx
0x18000dba4  js      loc_18000DCE2
0x18000dbaa  xor     esi, esi
0x18000dbac  test    r14d, r14d
0x18000dbaf  jle     loc_18000DCE2
0x18000dbb5  cmp     esi, r14d
0x18000dbb8  jge     loc_18000DD88
0x18000dbbe  mov     r15, [rbp+57h+var_A8]
0x18000dbc2  lea     r8, [rbp+57h+var_D0]; int *
0x18000dbc6  mov     rdx, [rdi+rsi*8]; lpSubKey
0x18000dbca  mov     rcx, r15; this
0x18000dbcd  call    ?GetTraceLevel@CEtwLogCollector@@QEAAJPEBGAEAJ@Z; CEtwLogCollector::GetTraceLevel(ushort const *,long &)
0x18000dbd2  mov     ebx, eax
0x18000dbd4  test    eax, eax
0x18000dbd6  js      loc_18000DCE2
0x18000dbdc  mov     rdx, [rdi+rsi*8]; lpSubKey
0x18000dbe0  lea     r8, [rbp+57h+Data]; lpData
0x18000dbe4  mov     rcx, r15; this
0x18000dbe7  call    ?GetKeywords@CEtwLogCollector@@QEAAJPEBGAEA_K@Z; CEtwLogCollector::GetKeywords(ushort const *,unsigned __int64 &)
0x18000dbec  mov     ebx, eax
0x18000dbee  test    eax, eax
0x18000dbf0  js      loc_18000DCE2
0x18000dbf6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dbfd  mov     ecx, 20h ; ' '; unsigned __int64
0x18000dc02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dc07  mov     r15, rax
0x18000dc0a  test    rax, rax
0x18000dc0d  jz      loc_18000DD7E
0x18000dc13  mov     cl, byte ptr [rbp+57h+var_D0]
0x18000dc16  lea     r8, aS; "{%s}"
0x18000dc1d  xorps   xmm0, xmm0
0x18000dc20  mov     edx, 27h ; '''; unsigned __int64
0x18000dc25  movups  xmmword ptr [rax], xmm0
0x18000dc28  movups  xmmword ptr [rax+10h], xmm0
0x18000dc2c  mov     [rax+18h], cl
0x18000dc2f  mov     dword ptr [rax+1Ch], 1
0x18000dc36  mov     rcx, qword ptr [rbp+57h+Data]
0x18000dc3a  mov     [rax+10h], rcx
0x18000dc3e  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18000dc42  mov     r9, [rdi+rsi*8]
0x18000dc46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dc4b  mov     ebx, eax
0x18000dc4d  test    eax, eax
0x18000dc4f  js      loc_18000DCE2
0x18000dc55  mov     rdx, r15; pclsid
0x18000dc58  lea     rcx, [rbp+57h+sz]; lpsz
0x18000dc5c  call    cs:__imp_CLSIDFromString
0x18000dc63  nop     dword ptr [rax+rax+00h]
0x18000dc68  mov     ebx, eax
0x18000dc6a  test    eax, eax
0x18000dc6c  js      loc_18000DD74
0x18000dc72  mov     r12d, [r13+8]
0x18000dc76  cmp     r12d, [r13+0Ch]
0x18000dc7a  jnz     short loc_18000DCBF
0x18000dc7c  cmp     dword ptr [r13+0Ch], 0
0x18000dc81  jnz     short loc_18000DC8B
0x18000dc83  mov     r12d, 1
0x18000dc89  jmp     short loc_18000DC90
0x18000dc8b  add     r12d, r12d
0x18000dc8e  js      short loc_18000DCD7
0x18000dc90  mov     edx, r12d
0x18000dc93  cmp     rdx, 0FFFFFFFh
0x18000dc9a  ja      short loc_18000DCD7
0x18000dc9c  mov     rcx, [r13+0]
0x18000dca0  mov     r8d, 8
0x18000dca6  call    cs:__imp__o__recalloc
0x18000dcad  nop     dword ptr [rax+rax+00h]
0x18000dcb2  test    rax, rax
0x18000dcb5  jz      short loc_18000DCD7
0x18000dcb7  mov     [r13+0Ch], r12d
0x18000dcbb  mov     [r13+0], rax
0x18000dcbf  movsxd  rcx, dword ptr [r13+8]
0x18000dcc3  mov     rax, [r13+0]
0x18000dcc7  lea     rdx, [rax+rcx*8]; unsigned int
0x18000dccb  test    rdx, rdx
0x18000dcce  jz      short loc_18000DCD3
0x18000dcd0  mov     [rdx], r15
0x18000dcd3  inc     dword ptr [r13+8]
0x18000dcd7  inc     esi
0x18000dcd9  cmp     esi, r14d
0x18000dcdc  jl      loc_18000DBBE
0x18000dce2  xor     esi, esi
0x18000dce4  test    r14d, r14d
0x18000dce7  jz      short loc_18000DD14
0x18000dce9  test    esi, esi
0x18000dceb  js      loc_18000DD93
0x18000dcf1  cmp     esi, r14d
0x18000dcf4  jge     loc_18000DD93
0x18000dcfa  movsxd  rcx, esi
0x18000dcfd  mov     rcx, [rdi+rcx*8]; bstrString
0x18000dd01  call    cs:__imp_SysFreeString
0x18000dd08  nop     dword ptr [rax+rax+00h]
0x18000dd0d  inc     esi
0x18000dd0f  cmp     esi, r14d
0x18000dd12  jb      short loc_18000DCE9
0x18000dd14  test    rdi, rdi
0x18000dd17  jz      short loc_18000DD2A
0x18000dd19  mov     rcx, rdi; Block
0x18000dd1c  call    cs:__imp_free
0x18000dd23  nop     dword ptr [rax+rax+00h]
0x18000dd28  xor     edi, edi
0x18000dd2a  test    ebx, ebx
0x18000dd2c  jns     short loc_18000DD36
0x18000dd2e  mov     rdx, r13
0x18000dd31  call    ?FreeProviderPropertiesArray@CEtwLogCollector@@AEAAXAEAV?$CSimpleArray@PEAU_EVENT_PROVIDER_PROPERTIES@@V?$CSimpleArrayEqualHelper@PEAU_EVENT_PROVIDER_PROPERTIES@@@ATL@@@ATL@@@Z; CEtwLogCollector::FreeProviderPropertiesArray(ATL::CSimpleArray<_EVENT_PROVIDER_PROPERTIES *,ATL::CSimpleArrayEqualHelper<_EVENT_PROVIDER_PROPERTIES *>> &)
0x18000dd36  test    rdi, rdi
0x18000dd39  jz      short loc_18000DD4A
0x18000dd3b  mov     rcx, rdi; Block
0x18000dd3e  call    cs:__imp_free
0x18000dd45  nop     dword ptr [rax+rax+00h]
0x18000dd4a  mov     eax, ebx
0x18000dd4c  mov     rcx, [rbp+57h+var_40]
0x18000dd50  xor     rcx, rsp; StackCookie
0x18000dd53  call    __security_check_cookie
0x18000dd58  mov     rbx, [rsp+0F0h+arg_10]
0x18000dd60  add     rsp, 0C0h
0x18000dd67  pop     r15
0x18000dd69  pop     r14
0x18000dd6b  pop     r13
0x18000dd6d  pop     r12
0x18000dd6f  pop     rdi
0x18000dd70  pop     rsi
0x18000dd71  pop     rbp
0x18000dd72  retn
0x18000dd74  mov     ebx, 80070057h
0x18000dd79  jmp     loc_18000DCE2
0x18000dd7e  mov     ebx, 8007000Eh
0x18000dd83  jmp     loc_18000DCE2
0x18000dd88  mov     ecx, 0C000008Ch; unsigned int
0x18000dd8d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000dd92  int     3; Trap to Debugger
0x18000dd93  mov     ecx, 0C000008Ch; unsigned int
0x18000dd98  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000dd9d  int     3; Trap to Debugger
0x18000dd9e  mov     ecx, 0C000008Ch; unsigned int
0x18000dda3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000dda8  int     3; Trap to Debugger
0x18000dda9  mov     ecx, 0C000008Ch; unsigned int
0x18000ddae  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
