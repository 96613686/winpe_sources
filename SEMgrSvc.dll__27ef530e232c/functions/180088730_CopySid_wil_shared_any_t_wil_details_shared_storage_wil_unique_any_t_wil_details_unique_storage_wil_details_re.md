# CopySid<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(void *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> *)

- ea: `0x180088730`
- end: `0x18008895d`
- name: `??$CopySid@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@@YAJPEAXPEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800889c4`

## callees

- `0x180004ec0`
- `0x18000c944`
- `0x18000c964`
- `0x180088730`
- `0x18009d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180088743`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180088743`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180088773`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180088773`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180088800`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180088800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180088783`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180088783`

## string_xrefs

- `0x18008875a`: `onecoreuap\ds\nfc\Product\Payment\common\inc\SidUtils.h`
- `0x18008880f`: `onecoreuap\ds\nfc\Product\Payment\common\inc\SidUtils.h`
- `0x180088902`: `onecoreuap\ds\nfc\Product\Payment\common\inc\SidUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CopySid<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
        PSID pSourceSid,
        __int64 a2)
{
  SIZE_T LengthSid; // r15
  HLOCAL v6; // rbp
  char *v7; // rbx
  PSID *v8; // rsi
  const char *v9; // r9
  unsigned int LastError; // esi
  char *v11; // rax
  volatile signed __int32 *v12; // rsi
  int v13[4]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !IsValidSid(pSourceSid) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA,
      (unsigned int)"onecoreuap\\ds\\nfc\\Product\\Payment\\common\\inc\\SidUtils.h",
      (const char *)0x80070057LL,
      v13[0]);
    return 2147942487LL;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v6 = LocalAlloc(0x40u, LengthSid);
  *(_OWORD *)v13 = 0;
  if ( v6 )
  {
    v7 = (char *)operator new(0x18u);
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::`vftable';
    v8 = (PSID *)(v7 + 16);
    *((_QWORD *)v7 + 2) = v6;
  }
  else
  {
    v7 = *(char **)&v13[2];
    v8 = *(PSID **)v13;
  }
  if ( !v8 || !*v8 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecoreuap\\ds\\nfc\\Product\\Payment\\common\\inc\\SidUtils.h",
      (const char *)0x8007000ELL,
      v13[0]);
    if ( !v7 )
      return LastError;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) != 1 )
      return LastError;
    (**(void (__fastcall ***)(void *))v7)(v7);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) != 1 )
      return LastError;
LABEL_26:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    return LastError;
  }
  if ( !CopySid(LengthSid, *v8, pSourceSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12,
                  (unsigned int)"onecoreuap\\ds\\nfc\\Product\\Payment\\common\\inc\\SidUtils.h",
                  v9);
    if ( !v7 )
      return LastError;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) != 1 )
      return LastError;
    (**(void (__fastcall ***)(void *))v7)(v7);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) != 1 )
      return LastError;
    goto LABEL_26;
  }
  if ( (int *)a2 != v13 )
  {
    v11 = v7;
    v7 = 0;
    *(_QWORD *)a2 = v8;
    v12 = *(volatile signed __int32 **)(a2 + 8);
    *(_QWORD *)(a2 + 8) = v11;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
  }
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v7)(v7);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180088730  push    rbx
0x180088732  push    rbp
0x180088733  push    rsi
0x180088734  push    rdi
0x180088735  push    r14
0x180088737  push    r15
0x180088739  sub     rsp, 38h
0x18008873d  mov     r14, rdx
0x180088740  mov     rdi, rcx
0x180088743  call    cs:__imp_IsValidSid
0x180088749  test    eax, eax
0x18008874b  jnz     short loc_180088770
0x18008874d  mov     rcx, [rsp+68h]; this
0x180088752  mov     ebx, 80070057h
0x180088757  mov     r9d, ebx; char *
0x18008875a  lea     r8, aOnecoreuapDsNf_34; "onecoreuap\\ds\\nfc\\Product\\Payment\\"...
0x180088761  lea     edx, [rax+0Ah]; void *
0x180088764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088769  mov     eax, ebx
0x18008876b  jmp     loc_180088950
0x180088770  mov     rcx, rdi; pSid
0x180088773  call    cs:__imp_GetLengthSid
0x180088779  mov     r15d, eax
0x18008877c  mov     edx, eax; uBytes
0x18008877e  mov     ecx, 40h ; '@'; uFlags
0x180088783  call    cs:__imp_LocalAlloc
0x180088789  mov     rbp, rax
0x18008878c  xorps   xmm0, xmm0
0x18008878f  movdqu  xmmword ptr [rsp+68h+var_48], xmm0; int
0x180088795  test    rax, rax
0x180088798  jz      short loc_1800887DB
0x18008879a  mov     [rsp+68h+arg_10], rax
0x1800887a2  mov     ecx, 18h; Size
0x1800887a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800887ac  mov     rbx, rax
0x1800887af  mov     [rsp+68h+arg_10], rax
0x1800887b7  xorps   xmm0, xmm0
0x1800887ba  movups  xmmword ptr [rax], xmm0
0x1800887bd  mov     eax, 1
0x1800887c2  mov     [rbx+8], eax
0x1800887c5  mov     [rbx+0Ch], eax
0x1800887c8  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::`vftable'
0x1800887cf  mov     [rbx], rax
0x1800887d2  lea     rsi, [rbx+10h]
0x1800887d6  mov     [rsi], rbp
0x1800887d9  jmp     short loc_1800887E5
0x1800887db  mov     rbx, qword ptr [rsp+68h+var_48+8]
0x1800887e0  mov     rsi, qword ptr [rsp+68h+var_48]
0x1800887e5  test    rsi, rsi
0x1800887e8  jz      loc_1800888F5
0x1800887ee  mov     rdx, [rsi]; pDestinationSid
0x1800887f1  test    rdx, rdx
0x1800887f4  jz      loc_1800888F5
0x1800887fa  mov     r8, rdi; pSourceSid
0x1800887fd  mov     ecx, r15d; nDestinationSidLength
0x180088800  call    cs:__imp_CopySid
0x180088806  test    eax, eax
0x180088808  jnz     short loc_180088864
0x18008880a  mov     rcx, [rsp+68h]; this
0x18008880f  lea     r8, aOnecoreuapDsNf_34; "onecoreuap\\ds\\nfc\\Product\\Payment\\"...
0x180088816  lea     edx, [rax+12h]; void *
0x180088819  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008881e  mov     esi, eax
0x180088820  test    rbx, rbx
0x180088823  jz      loc_18008894E
0x180088829  or      edi, 0FFFFFFFFh
0x18008882c  mov     ecx, edi
0x18008882e  lock xadd [rbx+8], ecx
0x180088833  add     ecx, edi
0x180088835  jnz     loc_18008894E
0x18008883b  mov     rcx, [rbx]
0x18008883e  mov     rax, [rcx]
0x180088841  mov     rcx, rbx
0x180088844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088849  mov     eax, edi
0x18008884b  lock xadd [rbx+0Ch], eax
0x180088850  add     eax, edi
0x180088852  jnz     loc_18008894E
0x180088858  mov     rax, [rbx]
0x18008885b  mov     rax, [rax+8]
0x18008885f  jmp     loc_180088946
0x180088864  lea     rax, [rsp+68h+var_48]
0x180088869  or      edi, 0FFFFFFFFh
0x18008886c  cmp     r14, rax
0x18008886f  jz      short loc_1800888B9
0x180088871  mov     rax, rbx
0x180088874  xor     ebx, ebx
0x180088876  mov     [r14], rsi
0x180088879  mov     rsi, [r14+8]
0x18008887d  mov     [r14+8], rax
0x180088881  test    rsi, rsi
0x180088884  jz      short loc_1800888B9
0x180088886  mov     eax, edi
0x180088888  lock xadd [rsi+8], eax
0x18008888d  add     eax, edi
0x18008888f  jnz     short loc_1800888B9
0x180088891  mov     rax, [rsi]
0x180088894  mov     rcx, rsi
0x180088897  mov     rax, [rax]
0x18008889a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008889f  mov     eax, edi
0x1800888a1  lock xadd [rsi+0Ch], eax
0x1800888a6  add     eax, edi
0x1800888a8  jnz     short loc_1800888B9
0x1800888aa  mov     rax, [rsi]
0x1800888ad  mov     rcx, rsi
0x1800888b0  mov     rax, [rax+8]
0x1800888b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800888b9  test    rbx, rbx
0x1800888bc  jz      short loc_1800888F1
0x1800888be  mov     eax, edi
0x1800888c0  lock xadd [rbx+8], eax
0x1800888c5  add     eax, edi
0x1800888c7  jnz     short loc_1800888F1
0x1800888c9  mov     rax, [rbx]
0x1800888cc  mov     rcx, rbx
0x1800888cf  mov     rax, [rax]
0x1800888d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800888d7  mov     eax, edi
0x1800888d9  lock xadd [rbx+0Ch], eax
0x1800888de  add     eax, edi
0x1800888e0  jnz     short loc_1800888F1
0x1800888e2  mov     rax, [rbx]
0x1800888e5  mov     rcx, rbx
0x1800888e8  mov     rax, [rax+8]
0x1800888ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800888f1  xor     eax, eax
0x1800888f3  jmp     short loc_180088950
0x1800888f5  mov     rcx, [rsp+68h]; this
0x1800888fa  mov     esi, 8007000Eh
0x1800888ff  mov     r9d, esi; char *
0x180088902  lea     r8, aOnecoreuapDsNf_34; "onecoreuap\\ds\\nfc\\Product\\Payment\\"...
0x180088909  mov     edx, 0Fh; void *
0x18008890e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088913  test    rbx, rbx
0x180088916  jz      short loc_18008894E
0x180088918  or      edi, 0FFFFFFFFh
0x18008891b  mov     eax, edi
0x18008891d  lock xadd [rbx+8], eax
0x180088922  add     eax, edi
0x180088924  jnz     short loc_18008894E
0x180088926  mov     rax, [rbx]
0x180088929  mov     rcx, rbx
0x18008892c  mov     rax, [rax]
0x18008892f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088934  mov     ecx, edi
0x180088936  lock xadd [rbx+0Ch], ecx
0x18008893b  add     ecx, edi
0x18008893d  jnz     short loc_18008894E
0x18008893f  mov     rcx, [rbx]
0x180088942  mov     rax, [rcx+8]
0x180088946  mov     rcx, rbx
0x180088949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008894e  mov     eax, esi
0x180088950  add     rsp, 38h
0x180088954  pop     r15
0x180088956  pop     r14
0x180088958  pop     rdi
0x180088959  pop     rsi
0x18008895a  pop     rbp
0x18008895b  pop     rbx
0x18008895c  retn
```
