# ProcessEndXmlElement(IXmlReader *,MasterDatastoreContext *,std::shared_ptr<CConfigSource> &)

- ea: `0x18000b6d8`
- end: `0x18000b8f2`
- name: `?ProcessEndXmlElement@@YAJPEAUIXmlReader@@PEAUMasterDatastoreContext@@AEAV?$shared_ptr@VCConfigSource@@@std@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b31c`

## callees

- `0x180001118`
- `0x180009068`
- `0x18000a94c`
- `0x18000b6d8`
- `0x180010d44`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ProcessEndXmlElement(__int64 a1, __int64 a2, __int64 *a3)
{
  volatile signed __int32 *v6; // rdi
  __int64 *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rdi
  unsigned int v12; // esi
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int128 v18; // [rsp+30h] [rbp-10h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF
  int *v20; // [rsp+80h] [rbp+40h] BYREF
  int *v21; // [rsp+88h] [rbp+48h] BYREF

  v20 = 0;
  v6 = (volatile signed __int32 *)a3[1];
  a3[1] = 0;
  *a3 = 0;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  if ( *(_DWORD *)(a2 + 8) == 1 )
    return 0;
  if ( *(_DWORD *)(a2 + 8) == 2 )
  {
    *(_DWORD *)(a2 + 8) = 1;
    return 0;
  }
  if ( *(_DWORD *)(a2 + 8) != 3 )
  {
    if ( *(_DWORD *)(a2 + 8) == 4 )
      *(_DWORD *)(a2 + 8) = 3;
    else
      MicrosoftTelemetryAssertTriggeredNoArgs((unsigned int)(*(_DWORD *)(a2 + 8) - 3));
    return 0;
  }
  v7 = (__int64 *)(a2 + 16);
  v8 = *(_QWORD *)(a2 + 16);
  v18 = 0;
  if ( *(_DWORD *)(v8 + 1160) )
  {
    v9 = a3[1];
    a3[1] = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(a2 + 24) = v9;
    v10 = *a3;
    *a3 = *v7;
    *v7 = v10;
    std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(&v18);
    std::shared_ptr<CConfigSet>::operator=((_QWORD *)(a2 + 16), (__int64 *)&v18);
    v11 = (volatile signed __int32 *)*((_QWORD *)&v18 + 1);
    if ( *((_QWORD *)&v18 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v18 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    *(_DWORD *)(a2 + 8) = 2;
    ++*(_DWORD *)(a2 + 4);
    return 0;
  }
  v12 = -2147024809;
  std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(&v18);
  std::shared_ptr<CConfigSet>::operator=((_QWORD *)(a2 + 16), (__int64 *)&v18);
  v13 = (volatile signed __int32 *)*((_QWORD *)&v18 + 1);
  if ( *((_QWORD *)&v18 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v18 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  if ( (*(int (__fastcall **)(__int64, int **, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, &v20, 0) < 0 )
    v20 = (int *)L"Unknown";
  if ( (unsigned int)dword_180019000 > 2 )
  {
    v21 = v20;
    v19 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v14,
      (__int64)word_1800155E2,
      v15,
      v16,
      (__int64)&v19,
      &v21);
  }
  return v12;
}

```

## disassembly

```asm
0x18000b6d8  mov     [rsp-28h+arg_0], rbx
0x18000b6dd  push    rbp
0x18000b6de  push    rsi
0x18000b6df  push    rdi
0x18000b6e0  push    r14
0x18000b6e2  push    r15
0x18000b6e4  mov     rbp, rsp
0x18000b6e7  sub     rsp, 40h
0x18000b6eb  mov     rsi, r8
0x18000b6ee  mov     rbx, rdx
0x18000b6f1  mov     r14, rcx
0x18000b6f4  mov     [rbp+arg_10], 0
0x18000b6fc  mov     rdi, [r8+8]
0x18000b700  mov     qword ptr [r8+8], 0
0x18000b708  mov     qword ptr [r8], 0
0x18000b70f  or      r15d, 0FFFFFFFFh
0x18000b713  test    rdi, rdi
0x18000b716  jz      short loc_18000B750
0x18000b718  mov     eax, r15d
0x18000b71b  lock xadd [rdi+8], eax
0x18000b720  add     eax, r15d
0x18000b723  jnz     short loc_18000B750
0x18000b725  mov     rax, [rdi]
0x18000b728  mov     rcx, rdi
0x18000b72b  mov     rax, [rax]
0x18000b72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b733  mov     eax, r15d
0x18000b736  lock xadd [rdi+0Ch], eax
0x18000b73b  add     eax, r15d
0x18000b73e  jnz     short loc_18000B750
0x18000b740  mov     rax, [rdi]
0x18000b743  mov     rcx, rdi
0x18000b746  mov     rax, [rax+8]
0x18000b74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b74f  nop
0x18000b750  mov     ecx, [rbx+8]
0x18000b753  sub     ecx, 1
0x18000b756  jz      loc_18000B8DD
0x18000b75c  sub     ecx, 1
0x18000b75f  jz      loc_18000B8D6
0x18000b765  sub     ecx, 1
0x18000b768  jz      short loc_18000B785
0x18000b76a  cmp     ecx, 1
0x18000b76d  jz      short loc_18000B779
0x18000b76f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b774  jmp     loc_18000B8DD
0x18000b779  mov     dword ptr [rbx+8], 3
0x18000b780  jmp     loc_18000B8DD
0x18000b785  lea     rdi, [rbx+10h]
0x18000b789  mov     rax, [rdi]
0x18000b78c  xorps   xmm0, xmm0
0x18000b78f  lea     rcx, [rbp+var_10]
0x18000b793  movdqu  [rbp+var_10], xmm0
0x18000b798  cmp     dword ptr [rax+488h], 0
0x18000b79f  jz      short loc_18000B81F
0x18000b7a1  mov     rdx, [rsi+8]
0x18000b7a5  mov     rax, [rdi+8]
0x18000b7a9  mov     [rsi+8], rax
0x18000b7ad  mov     [rdi+8], rdx
0x18000b7b1  mov     rdx, [rsi]
0x18000b7b4  mov     rax, [rdi]
0x18000b7b7  mov     [rsi], rax
0x18000b7ba  mov     [rdi], rdx
0x18000b7bd  call    ??$_Resetp@VCConfigSource@@@?$shared_ptr@VCConfigSource@@@std@@AEAAXPEAVCConfigSource@@@Z; std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(CConfigSource *)
0x18000b7c2  lea     rdx, [rbp+var_10]
0x18000b7c6  mov     rcx, rdi
0x18000b7c9  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000b7ce  nop
0x18000b7cf  mov     rdi, qword ptr [rbp+var_10+8]
0x18000b7d3  test    rdi, rdi
0x18000b7d6  jz      short loc_18000B810
0x18000b7d8  mov     eax, r15d
0x18000b7db  lock xadd [rdi+8], eax
0x18000b7e0  add     eax, r15d
0x18000b7e3  jnz     short loc_18000B810
0x18000b7e5  mov     rax, [rdi]
0x18000b7e8  mov     rcx, rdi
0x18000b7eb  mov     rax, [rax]
0x18000b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f3  mov     eax, r15d
0x18000b7f6  lock xadd [rdi+0Ch], eax
0x18000b7fb  add     eax, r15d
0x18000b7fe  jnz     short loc_18000B810
0x18000b800  mov     rax, [rdi]
0x18000b803  mov     rcx, rdi
0x18000b806  mov     rax, [rax+8]
0x18000b80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b80f  nop
0x18000b810  mov     dword ptr [rbx+8], 2
0x18000b817  inc     dword ptr [rbx+4]
0x18000b81a  jmp     loc_18000B8DD
0x18000b81f  mov     esi, 80070057h
0x18000b824  call    ??$_Resetp@VCConfigSource@@@?$shared_ptr@VCConfigSource@@@std@@AEAAXPEAVCConfigSource@@@Z; std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(CConfigSource *)
0x18000b829  lea     rdx, [rbp+var_10]
0x18000b82d  mov     rcx, rdi
0x18000b830  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000b835  nop
0x18000b836  mov     rbx, qword ptr [rbp+var_10+8]
0x18000b83a  test    rbx, rbx
0x18000b83d  jz      short loc_18000B877
0x18000b83f  mov     eax, r15d
0x18000b842  lock xadd [rbx+8], eax
0x18000b847  add     eax, r15d
0x18000b84a  jnz     short loc_18000B877
0x18000b84c  mov     rax, [rbx]
0x18000b84f  mov     rcx, rbx
0x18000b852  mov     rax, [rax]
0x18000b855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b85a  mov     eax, r15d
0x18000b85d  lock xadd [rbx+0Ch], eax
0x18000b862  add     eax, r15d
0x18000b865  jnz     short loc_18000B877
0x18000b867  mov     rax, [rbx]
0x18000b86a  mov     rcx, rbx
0x18000b86d  mov     rax, [rax+8]
0x18000b871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b876  nop
0x18000b877  mov     rax, [r14]
0x18000b87a  xor     r8d, r8d
0x18000b87d  lea     rdx, [rbp+arg_10]
0x18000b881  mov     rcx, r14
0x18000b884  mov     rax, [rax+70h]
0x18000b888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b88d  test    eax, eax
0x18000b88f  jns     short loc_18000B89C
0x18000b891  lea     rax, aUnknown; "Unknown"
0x18000b898  mov     [rbp+arg_10], rax
0x18000b89c  mov     eax, cs:dword_180019000
0x18000b8a2  cmp     eax, 2
0x18000b8a5  jbe     short loc_18000B8DF
0x18000b8a7  mov     rax, [rbp+arg_10]
0x18000b8ab  mov     [rbp+arg_18], rax
0x18000b8af  mov     [rbp+arg_8], 80070057h
0x18000b8b6  lea     rax, [rbp+arg_18]
0x18000b8ba  mov     [rsp+40h+var_18], rax
0x18000b8bf  lea     rax, [rbp+arg_8]
0x18000b8c3  mov     [rsp+40h+var_20], rax
0x18000b8c8  lea     rdx, word_1800155E2
0x18000b8cf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000b8d4  jmp     short loc_18000B8DF
0x18000b8d6  mov     dword ptr [rbx+8], 1
0x18000b8dd  xor     esi, esi
0x18000b8df  mov     eax, esi
0x18000b8e1  mov     rbx, [rsp+40h+arg_0]
0x18000b8e6  add     rsp, 40h
0x18000b8ea  pop     r15
0x18000b8ec  pop     r14
0x18000b8ee  pop     rdi
0x18000b8ef  pop     rsi
0x18000b8f0  pop     rbp
0x18000b8f1  retn
```
