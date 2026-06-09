# ProviderConverterRegistration::ConvertToKnowledgeSyncProvider(ISyncProvider *,IKnowledgeSyncProvider * *)

- ea: `0x180081704`
- end: `0x180081971`
- name: `?ConvertToKnowledgeSyncProvider@ProviderConverterRegistration@@QEAAJPEAUISyncProvider@@PEAPEAUIKnowledgeSyncProvider@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(ProviderConverterRegistration *__hidden this, struct ISyncProvider *, struct IKnowledgeSyncProvider **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f834`

## callees

- `0x18001a038`
- `0x180081704`
- `0x180081978`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800817b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081810`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800818b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800817b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081810`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800818b9`

## pseudocode

```c
__int64 __fastcall ProviderConverterRegistration::ConvertToKnowledgeSyncProvider(
        ProviderConverterRegistration *this,
        struct ISyncProvider *a2,
        struct IKnowledgeSyncProvider **a3)
{
  struct ISyncProviderVtbl *lpVtbl; // rax
  HRESULT v7; // eax
  HRESULT ProviderConverterEntries; // ebx
  LPVOID v9; // rcx
  HRESULT v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r12
  int v13; // eax
  _QWORD v15[3]; // [rsp+30h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::ConvertToKnowledgeSyncProvider");
  }
  lpVtbl = a2->lpVtbl;
  v15[0] = 0;
  ppv = 0;
  v7 = ((__int64 (__fastcall *)(struct ISyncProvider *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
         a2,
         &IID_IFullEnumerationSyncProvider,
         v15);
  ProviderConverterEntries = v7;
  if ( v7 )
  {
    if ( v7 == -2147467262 )
      goto LABEL_9;
  }
  else
  {
    ProviderConverterEntries = CoCreateInstance(
                                 &CLSID_FullEnumerationProviderWrapper,
                                 0,
                                 1u,
                                 &IID_IProviderConverter,
                                 &ppv);
  }
  if ( ProviderConverterEntries < 0 )
    goto LABEL_28;
LABEL_9:
  v9 = ppv;
  if ( ppv )
  {
LABEL_26:
    ProviderConverterEntries = (*(__int64 (__fastcall **)(LPVOID, struct ISyncProvider *))(*(_QWORD *)v9 + 24LL))(
                                 v9,
                                 a2);
    if ( ProviderConverterEntries >= 0 )
      ProviderConverterEntries = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IKnowledgeSyncProvider **))ppv)(
                                   ppv,
                                   &GUID_43434a49_8da4_47f2_8172_ad7b8b024978,
                                   a3);
    goto LABEL_28;
  }
  v10 = ((__int64 (__fastcall *)(struct ISyncProvider *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IAnchorSyncProvider,
          v15);
  ProviderConverterEntries = v10;
  if ( !v10 )
  {
    ProviderConverterEntries = CoCreateInstance(
                                 &CLSID_AnchorEnumerationProviderWrapper,
                                 0,
                                 1u,
                                 &IID_IProviderConverter,
                                 &ppv);
    goto LABEL_13;
  }
  if ( v10 != -2147467262 )
  {
LABEL_13:
    if ( ProviderConverterEntries < 0 )
      goto LABEL_28;
  }
  v9 = ppv;
  if ( ppv )
    goto LABEL_26;
  if ( !*((_DWORD *)this + 2) )
  {
    ProviderConverterEntries = ProviderConverterRegistration::ReadProviderConverterEntries(this);
    if ( ProviderConverterEntries < 0 )
      goto LABEL_28;
    v9 = ppv;
  }
  if ( v9 )
    goto LABEL_26;
  ProviderConverterEntries = -2147467262;
  v11 = 0;
  while ( v11 < *((_DWORD *)this + 6) )
  {
    v12 = 32LL * v11;
    v13 = ((__int64 (__fastcall *)(struct ISyncProvider *, __int64, _QWORD *))a2->lpVtbl->QueryInterface)(
            a2,
            v12 + *((_QWORD *)this + 2),
            v15);
    ProviderConverterEntries = v13;
    if ( v13 >= 0 )
    {
      ProviderConverterEntries = CoCreateInstance(
                                   (const IID *const)(v12 + *((_QWORD *)this + 2) + 16),
                                   0,
                                   1u,
                                   &IID_IProviderConverter,
                                   &ppv);
      if ( ProviderConverterEntries < 0 )
        break;
      v9 = ppv;
      goto LABEL_26;
    }
    ++v11;
    if ( v13 != -2147467262 )
      break;
  }
LABEL_28:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v15[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::ConvertToKnowledgeSyncProvider");
  }
  return (unsigned int)ProviderConverterEntries;
}

```

## disassembly

```asm
0x180081704  push    rbp
0x180081706  push    rbx
0x180081707  push    rsi
0x180081708  push    rdi
0x180081709  push    r12
0x18008170b  push    r13
0x18008170d  push    r14
0x18008170f  push    r15
0x180081711  mov     rbp, rsp
0x180081714  sub     rsp, 48h
0x180081718  mov     r13, r8
0x18008171b  mov     r14, rdx
0x18008171e  mov     rsi, rcx
0x180081721  mov     rcx, cs:WPP_GLOBAL_Control
0x180081728  lea     rax, WPP_GLOBAL_Control
0x18008172f  cmp     rcx, rax
0x180081732  jz      short loc_18008175C
0x180081734  test    byte ptr [rcx+1Ch], 4
0x180081738  jz      short loc_18008175C
0x18008173a  cmp     byte ptr [rcx+19h], 5
0x18008173e  jb      short loc_18008175C
0x180081740  mov     rcx, [rcx+10h]
0x180081744  lea     r9, aProviderconver_0; "ProviderConverterRegistration::ConvertT"...
0x18008174b  mov     edx, 10h
0x180081750  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x180081757  call    WPP_SF_s
0x18008175c  mov     rax, [r14]
0x18008175f  lea     r8, [rbp+var_18]
0x180081763  lea     rdx, IID_IFullEnumerationSyncProvider
0x18008176a  mov     [rbp+var_18], 0
0x180081772  mov     rcx, r14
0x180081775  mov     [rbp+arg_18], 0
0x18008177d  mov     rax, [rax]
0x180081780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081785  mov     ebx, eax
0x180081787  mov     edi, 80004002h
0x18008178c  mov     r15d, 1
0x180081792  test    eax, eax
0x180081794  jnz     short loc_1800817BC
0x180081796  lea     rax, [rbp+arg_18]
0x18008179a  mov     r8d, r15d; dwClsContext
0x18008179d  lea     r9, IID_IProviderConverter; riid
0x1800817a4  mov     [rsp+48h+ppv], rax; ppv
0x1800817a9  xor     edx, edx; pUnkOuter
0x1800817ab  lea     rcx, CLSID_FullEnumerationProviderWrapper; rclsid
0x1800817b2  call    cs:__imp_CoCreateInstance
0x1800817b8  mov     ebx, eax
0x1800817ba  jmp     short loc_1800817C0
0x1800817bc  cmp     eax, edi
0x1800817be  jz      short loc_1800817C8
0x1800817c0  test    ebx, ebx
0x1800817c2  js      loc_1800818F9
0x1800817c8  mov     rcx, [rbp+arg_18]
0x1800817cc  test    rcx, rcx
0x1800817cf  jnz     loc_1800818C9
0x1800817d5  mov     rax, [r14]
0x1800817d8  lea     r8, [rbp+var_18]
0x1800817dc  lea     rdx, IID_IAnchorSyncProvider
0x1800817e3  mov     rcx, r14
0x1800817e6  mov     rax, [rax]
0x1800817e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817ee  mov     ebx, eax
0x1800817f0  test    eax, eax
0x1800817f2  jnz     short loc_18008181A
0x1800817f4  lea     rax, [rbp+arg_18]
0x1800817f8  mov     r8d, r15d; dwClsContext
0x1800817fb  lea     r9, IID_IProviderConverter; riid
0x180081802  mov     [rsp+48h+ppv], rax; ppv
0x180081807  xor     edx, edx; pUnkOuter
0x180081809  lea     rcx, CLSID_AnchorEnumerationProviderWrapper; rclsid
0x180081810  call    cs:__imp_CoCreateInstance
0x180081816  mov     ebx, eax
0x180081818  jmp     short loc_18008181E
0x18008181a  cmp     eax, edi
0x18008181c  jz      short loc_180081826
0x18008181e  test    ebx, ebx
0x180081820  js      loc_1800818F9
0x180081826  mov     rcx, [rbp+arg_18]
0x18008182a  test    rcx, rcx
0x18008182d  jnz     loc_1800818C9
0x180081833  cmp     [rsi+8], ecx
0x180081836  jnz     short loc_18008184E
0x180081838  mov     rcx, rsi; this
0x18008183b  call    ?ReadProviderConverterEntries@ProviderConverterRegistration@@AEAAJXZ; ProviderConverterRegistration::ReadProviderConverterEntries(void)
0x180081840  mov     ebx, eax
0x180081842  test    eax, eax
0x180081844  js      loc_1800818F9
0x18008184a  mov     rcx, [rbp+arg_18]
0x18008184e  test    rcx, rcx
0x180081851  jnz     short loc_1800818C9
0x180081853  xor     r15d, r15d
0x180081856  mov     ebx, edi
0x180081858  xor     edi, edi
0x18008185a  cmp     edi, [rsi+18h]
0x18008185d  jnb     loc_1800818F9
0x180081863  mov     rcx, [r14]
0x180081866  lea     r8, [rbp+var_18]
0x18008186a  mov     rdx, [rsi+10h]
0x18008186e  mov     r12d, edi
0x180081871  shl     r12, 5
0x180081875  mov     rax, [rcx]
0x180081878  add     rdx, r12
0x18008187b  mov     rcx, r14
0x18008187e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081883  mov     ebx, eax
0x180081885  test    eax, eax
0x180081887  jns     short loc_180081898
0x180081889  inc     edi
0x18008188b  cmp     eax, 80004002h
0x180081890  jz      short loc_18008185A
0x180081892  test    eax, eax
0x180081894  jns     short loc_18008189F
0x180081896  jmp     short loc_1800818F9
0x180081898  mov     r15, [rsi+10h]
0x18008189c  add     r15, r12
0x18008189f  xor     edx, edx; pUnkOuter
0x1800818a1  lea     rax, [rbp+arg_18]
0x1800818a5  lea     rcx, [r15+10h]; rclsid
0x1800818a9  mov     [rsp+48h+ppv], rax; ppv
0x1800818ae  lea     r9, IID_IProviderConverter; riid
0x1800818b5  lea     r8d, [rdx+1]; dwClsContext
0x1800818b9  call    cs:__imp_CoCreateInstance
0x1800818bf  mov     ebx, eax
0x1800818c1  test    eax, eax
0x1800818c3  js      short loc_1800818F9
0x1800818c5  mov     rcx, [rbp+arg_18]
0x1800818c9  mov     rax, [rcx]
0x1800818cc  mov     rdx, r14
0x1800818cf  mov     rax, [rax+18h]
0x1800818d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818d8  mov     ebx, eax
0x1800818da  test    eax, eax
0x1800818dc  js      short loc_1800818F9
0x1800818de  mov     rcx, [rbp+arg_18]
0x1800818e2  lea     rdx, _GUID_43434a49_8da4_47f2_8172_ad7b8b024978
0x1800818e9  mov     r8, r13
0x1800818ec  mov     rax, [rcx]
0x1800818ef  mov     rax, [rax]
0x1800818f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818f7  mov     ebx, eax
0x1800818f9  mov     rcx, [rbp+arg_18]
0x1800818fd  test    rcx, rcx
0x180081900  jz      short loc_18008190E
0x180081902  mov     rax, [rcx]
0x180081905  mov     rax, [rax+10h]
0x180081909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008190e  mov     rcx, [rbp+var_18]
0x180081912  test    rcx, rcx
0x180081915  jz      short loc_180081923
0x180081917  mov     rax, [rcx]
0x18008191a  mov     rax, [rax+10h]
0x18008191e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081923  mov     rcx, cs:WPP_GLOBAL_Control
0x18008192a  lea     rax, WPP_GLOBAL_Control
0x180081931  cmp     rcx, rax
0x180081934  jz      short loc_18008195E
0x180081936  test    byte ptr [rcx+1Ch], 4
0x18008193a  jz      short loc_18008195E
0x18008193c  cmp     byte ptr [rcx+19h], 5
0x180081940  jb      short loc_18008195E
0x180081942  mov     rcx, [rcx+10h]
0x180081946  lea     r9, aProviderconver_0; "ProviderConverterRegistration::ConvertT"...
0x18008194d  mov     edx, 11h
0x180081952  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x180081959  call    WPP_SF_s
0x18008195e  mov     eax, ebx
0x180081960  add     rsp, 48h
0x180081964  pop     r15
0x180081966  pop     r14
0x180081968  pop     r13
0x18008196a  pop     r12
0x18008196c  pop     rdi
0x18008196d  pop     rsi
0x18008196e  pop     rbx
0x18008196f  pop     rbp
0x180081970  retn
```
