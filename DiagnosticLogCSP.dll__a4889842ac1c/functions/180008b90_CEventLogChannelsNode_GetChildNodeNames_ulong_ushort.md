# CEventLogChannelsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180008b90`
- end: `0x180008dad`
- name: `?GetChildNodeNames@CEventLogChannelsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `541`
- prototype: `__int64 __fastcall(CEventLogChannelsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800073e0`
- `0x1800075ec`
- `0x180008b90`
- `0x18000f170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008d20`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008d82`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008d20`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d65`
- `OLEAUT32!__imp_SysAllocString` at `0x180008c3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180008c3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c65`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c65`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d54`

## pseudocode

```c
__int64 __fastcall CEventLogChannelsNode::GetChildNodeNames(
        __int64 this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        __int64 a4)
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
    this = (unsigned int)(*(_DWORD *)(this + 44) - 13);
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
        RegisteredChannels = ConstructBSTRArray(a3, a2, (__int64)&psz);
      v5 = (int)v22;
      v4 = psz;
    }
  }
  else
  {
    RegisteredChannels = -2147024809;
  }
LABEL_20:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v24 = RegisteredChannels;
    if ( a2 )
      v15 = *a2;
    else
      v15 = -1;
    v25 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)byte_18003EB53,
      (__int64)a3,
      a4,
      (__int64)&v25,
      (__int64)&v24);
  }
  for ( j = 0; j < (unsigned int)v5; ++j )
  {
    if ( j < 0 || j >= v5 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      JUMPOUT(0x180008DACLL);
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
0x180008b90  mov     [rsp-38h+arg_0], rbx
0x180008b95  push    rbp
0x180008b96  push    rsi
0x180008b97  push    rdi
0x180008b98  push    r12
0x180008b9a  push    r13
0x180008b9c  push    r14
0x180008b9e  push    r15
0x180008ba0  mov     rbp, rsp
0x180008ba3  sub     rsp, 50h
0x180008ba7  xor     edi, edi
0x180008ba9  xor     r13d, r13d
0x180008bac  mov     [rbp+psz], rdi
0x180008bb0  mov     r12, r8
0x180008bb3  mov     [rbp+var_18], r13
0x180008bb7  mov     r14, rdx
0x180008bba  test    rdx, rdx
0x180008bbd  jz      loc_180008CAB
0x180008bc3  test    r8, r8
0x180008bc6  jz      loc_180008CAB
0x180008bcc  mov     [rdx], edi
0x180008bce  mov     [r8], rdi
0x180008bd1  mov     ecx, [rcx+2Ch]
0x180008bd4  sub     ecx, 0Dh
0x180008bd7  jz      loc_180008C81
0x180008bdd  cmp     ecx, 1
0x180008be0  jz      short loc_180008BF1
0x180008be2  mov     [rdx], edi
0x180008be4  mov     [r8], rdi
0x180008be7  mov     ebx, 86000011h
0x180008bec  jmp     loc_180008CB0
0x180008bf1  lea     rax, aExport; "Export"
0x180008bf8  mov     ebx, 18h
0x180008bfd  mov     [rbp+psz], rax
0x180008c01  mov     ecx, ebx; cb
0x180008c03  lea     rax, aFilter; "Filter"
0x180008c0a  mov     [rbp+var_18], rax
0x180008c0e  lea     rax, aState; "State"
0x180008c15  mov     [rbp+var_10], rax
0x180008c19  call    cs:__imp_CoTaskMemAlloc
0x180008c1f  mov     r15, rax
0x180008c22  test    rax, rax
0x180008c25  jz      short loc_180008C7A
0x180008c27  xor     esi, esi
0x180008c29  mov     [rax], sil
0x180008c2c  inc     rax
0x180008c2f  sub     rbx, 1
0x180008c33  jnz     short loc_180008C29
0x180008c35  mov     rcx, [rbp+rsi*8+psz]; psz
0x180008c3a  call    cs:__imp_SysAllocString
0x180008c40  mov     [r15+rsi*8], rax
0x180008c44  test    rax, rax
0x180008c47  jz      short loc_180008C5B
0x180008c49  inc     esi
0x180008c4b  cmp     esi, 3
0x180008c4e  jb      short loc_180008C35
0x180008c50  mov     [r12], r15
0x180008c54  xor     ebx, ebx
0x180008c56  mov     [r14], esi
0x180008c59  jmp     short loc_180008CB0
0x180008c5b  xor     ebx, ebx
0x180008c5d  test    esi, esi
0x180008c5f  jz      short loc_180008C71
0x180008c61  mov     rcx, [r15+rbx*8]; bstrString
0x180008c65  call    cs:__imp_SysFreeString
0x180008c6b  inc     ebx
0x180008c6d  cmp     ebx, esi
0x180008c6f  jb      short loc_180008C61
0x180008c71  mov     rcx, r15; pv
0x180008c74  call    cs:__imp_CoTaskMemFree
0x180008c7a  mov     ebx, 8007000Eh
0x180008c7f  jmp     short loc_180008CB0
0x180008c81  lea     rcx, [rbp+psz]
0x180008c85  call    ?GetRegisteredChannels@CEventLogChannel@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEventLogChannel::GetRegisteredChannels(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180008c8a  mov     ebx, eax
0x180008c8c  test    eax, eax
0x180008c8e  js      short loc_180008CA1
0x180008c90  lea     r8, [rbp+psz]
0x180008c94  mov     rdx, r14
0x180008c97  mov     rcx, r12
0x180008c9a  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180008c9f  mov     ebx, eax
0x180008ca1  mov     r13d, dword ptr [rbp+var_18]
0x180008ca5  mov     rdi, [rbp+psz]
0x180008ca9  jmp     short loc_180008CB0
0x180008cab  mov     ebx, 80070057h
0x180008cb0  mov     eax, cs:dword_180048E90
0x180008cb6  cmp     eax, 5
0x180008cb9  jbe     short loc_180008CEC
0x180008cbb  mov     [rbp+arg_8], ebx
0x180008cbe  test    r14, r14
0x180008cc1  jz      short loc_180008CC8
0x180008cc3  mov     eax, [r14]
0x180008cc6  jmp     short loc_180008CCB
0x180008cc8  or      eax, 0FFFFFFFFh
0x180008ccb  mov     [rbp+arg_18], eax
0x180008cce  lea     rdx, byte_18003EB53
0x180008cd5  lea     rax, [rbp+arg_8]
0x180008cd9  mov     [rsp+50h+var_28], rax
0x180008cde  lea     rax, [rbp+arg_18]
0x180008ce2  mov     [rsp+50h+var_30], rax
0x180008ce7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008cec  xor     esi, esi
0x180008cee  test    r13d, r13d
0x180008cf1  jz      short loc_180008D18
0x180008cf3  test    esi, esi
0x180008cf5  js      loc_180008DA2
0x180008cfb  cmp     esi, r13d
0x180008cfe  jge     loc_180008DA2
0x180008d04  movsxd  rcx, esi
0x180008d07  mov     rcx, [rdi+rcx*8]; bstrString
0x180008d0b  call    cs:__imp_SysFreeString
0x180008d11  inc     esi
0x180008d13  cmp     esi, r13d
0x180008d16  jb      short loc_180008CF3
0x180008d18  test    rdi, rdi
0x180008d1b  jz      short loc_180008D28
0x180008d1d  mov     rcx, rdi; Block
0x180008d20  call    cs:__imp_free
0x180008d26  xor     edi, edi
0x180008d28  mov     ecx, 80000000h
0x180008d2d  lea     eax, [rbx+rcx]
0x180008d30  test    ecx, eax
0x180008d32  jnz     short loc_180008D7A
0x180008d34  cmp     ebx, 80070057h
0x180008d3a  jz      short loc_180008D7A
0x180008d3c  mov     rsi, [r12]
0x180008d40  test    rsi, rsi
0x180008d43  jz      short loc_180008D6B
0x180008d45  mov     r13d, [r14]
0x180008d48  xor     r15d, r15d
0x180008d4b  test    r13d, r13d
0x180008d4e  jz      short loc_180008D62
0x180008d50  mov     rcx, [rsi+r15*8]; bstrString
0x180008d54  call    cs:__imp_SysFreeString
0x180008d5a  inc     r15d
0x180008d5d  cmp     r15d, r13d
0x180008d60  jb      short loc_180008D50
0x180008d62  mov     rcx, rsi; pv
0x180008d65  call    cs:__imp_CoTaskMemFree
0x180008d6b  mov     qword ptr [r12], 0
0x180008d73  mov     dword ptr [r14], 0
0x180008d7a  test    rdi, rdi
0x180008d7d  jz      short loc_180008D88
0x180008d7f  mov     rcx, rdi; Block
0x180008d82  call    cs:__imp_free
0x180008d88  mov     eax, ebx
0x180008d8a  mov     rbx, [rsp+50h+arg_0]
0x180008d92  add     rsp, 50h
0x180008d96  pop     r15
0x180008d98  pop     r14
0x180008d9a  pop     r13
0x180008d9c  pop     r12
0x180008d9e  pop     rdi
0x180008d9f  pop     rsi
0x180008da0  pop     rbp
0x180008da1  retn
0x180008da2  mov     ecx, 0C000008Ch; unsigned int
0x180008da7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
