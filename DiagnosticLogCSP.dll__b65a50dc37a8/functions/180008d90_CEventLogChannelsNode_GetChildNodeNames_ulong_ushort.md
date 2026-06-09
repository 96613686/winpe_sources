# CEventLogChannelsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180008d90`
- end: `0x180008fe4`
- name: `?GetChildNodeNames@CEventLogChannelsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `596`
- prototype: `__int64 __fastcall(CEventLogChannelsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180007530`
- `0x18000774c`
- `0x180008d90`
- `0x18000f8cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008f3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008f3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e40`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e40`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e71`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f23`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f78`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e71`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f23`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f78`

## pseudocode

```c
__int64 __fastcall CEventLogChannelsNode::GetChildNodeNames(
        CEventLogChannelsNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        int a4)
{
  OLECHAR *v4; // rdi
  int v5; // r13d
  int RegisteredChannels; // ebx
  __int64 v9; // rbx
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // r15
  __int64 v12; // rsi
  BSTR v13; // rax
  __int64 i; // rbx
  int v15; // eax
  int j; // esi
  BSTR *v17; // rsi
  unsigned int v18; // r13d
  __int64 k; // r15
  OLECHAR *psz; // [rsp+30h] [rbp-20h] BYREF
  const unsigned __int16 *v22; // [rsp+38h] [rbp-18h]
  const unsigned __int16 *v23; // [rsp+40h] [rbp-10h]
  int v24; // [rsp+98h] [rbp+48h] BYREF
  int v25; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  psz = 0;
  v22 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    LODWORD(this) = *((_DWORD *)this + 11) - 13;
    if ( (_DWORD)this )
    {
      if ( (_DWORD)this == 1 )
      {
        v9 = 24;
        psz = L"Export";
        v22 = L"Filter";
        v23 = L"State";
        v10 = (unsigned __int16 **)CoTaskMemAlloc(0x18u);
        v11 = v10;
        if ( v10 )
        {
          v12 = 0;
          do
          {
            *(_BYTE *)v10 = 0;
            v10 = (unsigned __int16 **)((char *)v10 + 1);
            --v9;
          }
          while ( v9 );
          while ( 1 )
          {
            v13 = SysAllocString((&psz)[v12]);
            v11[v12] = v13;
            if ( !v13 )
              break;
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= 3 )
            {
              *a3 = v11;
              RegisteredChannels = 0;
              *a2 = v12;
              goto LABEL_20;
            }
          }
          for ( i = 0; (unsigned int)i < (unsigned int)v12; i = (unsigned int)(i + 1) )
            SysFreeString(v11[i]);
          CoTaskMemFree(v11);
        }
        RegisteredChannels = -2147024882;
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
      RegisteredChannels = CEventLogChannel::GetRegisteredChannels(&psz);
      if ( RegisteredChannels >= 0 )
        RegisteredChannels = ConstructBSTRArray(a3, a2, &psz);
      v5 = (int)v22;
      v4 = psz;
    }
  }
  else
  {
    RegisteredChannels = -2147024809;
  }
LABEL_20:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v24 = RegisteredChannels;
    if ( a2 )
      v15 = *a2;
    else
      v15 = -1;
    v25 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_180040B53,
      (_DWORD)a3,
      a4,
      (__int64)&v25,
      (__int64)&v24);
  }
  for ( j = 0; j < (unsigned int)v5; ++j )
  {
    if ( j < 0 || j >= v5 )
    {
      ATL::_AtlRaiseException(0xC000008C, (unsigned int)a2);
      JUMPOUT(0x180008FE3LL);
    }
    SysFreeString(*(BSTR *)&v4[4 * j]);
  }
  if ( v4 )
    free(v4);
  if ( (int)(RegisteredChannels + 0x80000000) >= 0 && RegisteredChannels != -2147024809 )
  {
    v17 = *a3;
    if ( *a3 )
    {
      v18 = *a2;
      for ( k = 0; (unsigned int)k < v18; k = (unsigned int)(k + 1) )
        SysFreeString(v17[k]);
      CoTaskMemFree(v17);
    }
    *a3 = 0;
    *a2 = 0;
  }
  return (unsigned int)RegisteredChannels;
}

```

## disassembly

```asm
0x180008d90  mov     [rsp-38h+arg_0], rbx
0x180008d95  push    rbp
0x180008d96  push    rsi
0x180008d97  push    rdi
0x180008d98  push    r12
0x180008d9a  push    r13
0x180008d9c  push    r14
0x180008d9e  push    r15
0x180008da0  mov     rbp, rsp
0x180008da3  sub     rsp, 50h
0x180008da7  xor     edi, edi
0x180008da9  xor     r13d, r13d
0x180008dac  mov     [rbp+psz], rdi
0x180008db0  mov     r12, r8
0x180008db3  mov     [rbp+var_18], r13
0x180008db7  mov     r14, rdx
0x180008dba  test    rdx, rdx
0x180008dbd  jz      loc_180008EC3
0x180008dc3  test    r8, r8
0x180008dc6  jz      loc_180008EC3
0x180008dcc  mov     [rdx], edi
0x180008dce  mov     [r8], rdi
0x180008dd1  mov     ecx, [rcx+2Ch]
0x180008dd4  sub     ecx, 0Dh
0x180008dd7  jz      loc_180008E99
0x180008ddd  cmp     ecx, 1
0x180008de0  jz      short loc_180008DF1
0x180008de2  mov     [rdx], edi
0x180008de4  mov     [r8], rdi
0x180008de7  mov     ebx, 86000011h
0x180008dec  jmp     loc_180008EC8
0x180008df1  lea     rax, aExport; "Export"
0x180008df8  mov     ebx, 18h
0x180008dfd  mov     [rbp+psz], rax
0x180008e01  mov     ecx, ebx; cb
0x180008e03  lea     rax, aFilter; "Filter"
0x180008e0a  mov     [rbp+var_18], rax
0x180008e0e  lea     rax, aState; "State"
0x180008e15  mov     [rbp+var_10], rax
0x180008e19  call    cs:__imp_CoTaskMemAlloc
0x180008e20  nop     dword ptr [rax+rax+00h]
0x180008e25  mov     r15, rax
0x180008e28  test    rax, rax
0x180008e2b  jz      short loc_180008E92
0x180008e2d  xor     esi, esi
0x180008e2f  mov     [rax], sil
0x180008e32  inc     rax
0x180008e35  sub     rbx, 1
0x180008e39  jnz     short loc_180008E2F
0x180008e3b  mov     rcx, [rbp+rsi*8+psz]; psz
0x180008e40  call    cs:__imp_SysAllocString
0x180008e47  nop     dword ptr [rax+rax+00h]
0x180008e4c  mov     [r15+rsi*8], rax
0x180008e50  test    rax, rax
0x180008e53  jz      short loc_180008E67
0x180008e55  inc     esi
0x180008e57  cmp     esi, 3
0x180008e5a  jb      short loc_180008E3B
0x180008e5c  mov     [r12], r15
0x180008e60  xor     ebx, ebx
0x180008e62  mov     [r14], esi
0x180008e65  jmp     short loc_180008EC8
0x180008e67  xor     ebx, ebx
0x180008e69  test    esi, esi
0x180008e6b  jz      short loc_180008E83
0x180008e6d  mov     rcx, [r15+rbx*8]; bstrString
0x180008e71  call    cs:__imp_SysFreeString
0x180008e78  nop     dword ptr [rax+rax+00h]
0x180008e7d  inc     ebx
0x180008e7f  cmp     ebx, esi
0x180008e81  jb      short loc_180008E6D
0x180008e83  mov     rcx, r15; pv
0x180008e86  call    cs:__imp_CoTaskMemFree
0x180008e8d  nop     dword ptr [rax+rax+00h]
0x180008e92  mov     ebx, 8007000Eh
0x180008e97  jmp     short loc_180008EC8
0x180008e99  lea     rcx, [rbp+psz]
0x180008e9d  call    ?GetRegisteredChannels@CEventLogChannel@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEventLogChannel::GetRegisteredChannels(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180008ea2  mov     ebx, eax
0x180008ea4  test    eax, eax
0x180008ea6  js      short loc_180008EB9
0x180008ea8  lea     r8, [rbp+psz]
0x180008eac  mov     rdx, r14
0x180008eaf  mov     rcx, r12
0x180008eb2  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180008eb7  mov     ebx, eax
0x180008eb9  mov     r13d, dword ptr [rbp+var_18]
0x180008ebd  mov     rdi, [rbp+psz]
0x180008ec1  jmp     short loc_180008EC8
0x180008ec3  mov     ebx, 80070057h
0x180008ec8  mov     eax, cs:dword_18004AE90
0x180008ece  cmp     eax, 5
0x180008ed1  jbe     short loc_180008F04
0x180008ed3  mov     [rbp+arg_8], ebx
0x180008ed6  test    r14, r14
0x180008ed9  jz      short loc_180008EE0
0x180008edb  mov     eax, [r14]
0x180008ede  jmp     short loc_180008EE3
0x180008ee0  or      eax, 0FFFFFFFFh
0x180008ee3  mov     [rbp+arg_18], eax
0x180008ee6  lea     rdx, byte_180040B53
0x180008eed  lea     rax, [rbp+arg_8]
0x180008ef1  mov     [rsp+50h+var_28], rax
0x180008ef6  lea     rax, [rbp+arg_18]
0x180008efa  mov     [rsp+50h+var_30], rax
0x180008eff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008f04  xor     esi, esi
0x180008f06  test    r13d, r13d
0x180008f09  jz      short loc_180008F36
0x180008f0b  test    esi, esi
0x180008f0d  js      loc_180008FD9
0x180008f13  cmp     esi, r13d
0x180008f16  jge     loc_180008FD9
0x180008f1c  movsxd  rcx, esi
0x180008f1f  mov     rcx, [rdi+rcx*8]; bstrString
0x180008f23  call    cs:__imp_SysFreeString
0x180008f2a  nop     dword ptr [rax+rax+00h]
0x180008f2f  inc     esi
0x180008f31  cmp     esi, r13d
0x180008f34  jb      short loc_180008F0B
0x180008f36  test    rdi, rdi
0x180008f39  jz      short loc_180008F4C
0x180008f3b  mov     rcx, rdi; Block
0x180008f3e  call    cs:__imp_free
0x180008f45  nop     dword ptr [rax+rax+00h]
0x180008f4a  xor     edi, edi
0x180008f4c  mov     ecx, 80000000h
0x180008f51  lea     eax, [rbx+rcx]
0x180008f54  test    ecx, eax
0x180008f56  jnz     short loc_180008FAA
0x180008f58  cmp     ebx, 80070057h
0x180008f5e  jz      short loc_180008FAA
0x180008f60  mov     rsi, [r12]
0x180008f64  test    rsi, rsi
0x180008f67  jz      short loc_180008F9B
0x180008f69  mov     r13d, [r14]
0x180008f6c  xor     r15d, r15d
0x180008f6f  test    r13d, r13d
0x180008f72  jz      short loc_180008F8C
0x180008f74  mov     rcx, [rsi+r15*8]; bstrString
0x180008f78  call    cs:__imp_SysFreeString
0x180008f7f  nop     dword ptr [rax+rax+00h]
0x180008f84  inc     r15d
0x180008f87  cmp     r15d, r13d
0x180008f8a  jb      short loc_180008F74
0x180008f8c  mov     rcx, rsi; pv
0x180008f8f  call    cs:__imp_CoTaskMemFree
0x180008f96  nop     dword ptr [rax+rax+00h]
0x180008f9b  mov     qword ptr [r12], 0
0x180008fa3  mov     dword ptr [r14], 0
0x180008faa  test    rdi, rdi
0x180008fad  jz      short loc_180008FBE
0x180008faf  mov     rcx, rdi; Block
0x180008fb2  call    cs:__imp_free
0x180008fb9  nop     dword ptr [rax+rax+00h]
0x180008fbe  mov     eax, ebx
0x180008fc0  mov     rbx, [rsp+50h+arg_0]
0x180008fc8  add     rsp, 50h
0x180008fcc  pop     r15
0x180008fce  pop     r14
0x180008fd0  pop     r13
0x180008fd2  pop     r12
0x180008fd4  pop     rdi
0x180008fd5  pop     rsi
0x180008fd6  pop     rbp
0x180008fd7  retn
0x180008fd9  mov     ecx, 0C000008Ch; unsigned int
0x180008fde  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
