# CreateMidiPortForKsPin(IPart *,ushort const *,ulong,ushort const *,uint,ushort const *,uint *)

- ea: `0x18003868c`
- end: `0x180038a08`
- name: `?CreateMidiPortForKsPin@@YAXPEAUIPart@@PEBGK1I1PEAI@Z`
- size: `892`
- prototype: `void __fastcall(struct IPart *, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800381a8`

## callees

- `0x180001734`
- `0x180006b0c`
- `0x180010dd0`
- `0x18001f374`
- `0x180024208`
- `0x18003868c`
- `0x18003e920`
- `0x180049040`
- `0x18004986c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800388b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003894f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003899a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800388b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003894f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003899a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389a8`

## string_xrefs

- `0x180038873`: `CreateMidiPortForKsPin`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CreateMidiPortForKsPin(
        struct IPart *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int *a7)
{
  int MidiPort; // edi
  unsigned int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rsi
  int v13; // eax
  unsigned __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rdx
  const struct _tlgProvider_t *v18; // rax
  int v19; // r8d
  int v20; // r9d
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rbx
  unsigned __int16 *v25; // rdi
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v26[2]; // [rsp+20h] [rbp-C1h]
  unsigned __int16 *v27; // [rsp+40h] [rbp-A1h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-99h] BYREF
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v29; // [rsp+50h] [rbp-91h] BYREF
  unsigned int v30; // [rsp+54h] [rbp-8Dh] BYREF
  int v31; // [rsp+58h] [rbp-89h] BYREF
  __int64 v32; // [rsp+60h] [rbp-81h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int16 v34[8]; // [rsp+70h] [rbp-71h] BYREF
  _OWORD v35[2]; // [rsp+80h] [rbp-61h]
  unsigned __int16 v36[8]; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-31h]
  __int128 v38; // [rsp+C0h] [rbp-21h]

  v33 = a4;
  v30 = a3;
  v32 = 0;
  v31 = 0;
  pv = 0;
  v27 = 0;
  *(_OWORD *)v34 = *(_OWORD *)L"MIDII_12345678.P1234";
  v35[0] = *(_OWORD *)L"345678.P1234";
  *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)L".P1234";
  *(_OWORD *)v36 = *(_OWORD *)L"MIDII_%08I32X.P_%04I32X";
  v37 = *(_OWORD *)L"8I32X.P_%04I32X";
  v38 = *(_OWORD *)L"%04I32X";
  v29 = In;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, int *))a1->lpVtbl->GetLocalId)(a1, &v31);
  if ( MidiPort < 0 )
    goto LABEL_22;
  v10 = (unsigned __int16)v31;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_9c2c4058_23f5_41de_877a_df3af236a09e,
               &v32);
  if ( MidiPort < 0 )
    goto LABEL_22;
  MidiPort = (*(__int64 (__fastcall **)(__int64, enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 *))(*(_QWORD *)v32 + 32LL))(
               v32,
               &v29);
  if ( MidiPort < 0 )
    goto LABEL_22;
  v29 = v29 != Out;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, LPVOID *))a1->lpVtbl->GetName)(a1, &pv);
  if ( MidiPort < 0 )
    goto LABEL_22;
  if ( !pv )
    goto LABEL_13;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  if ( v11 )
  {
    v12 = 0x7FFFFFFF;
    v13 = StringCchLengthW((const unsigned __int16 *)pv, 0x7FFFFFFFu, (unsigned __int64 *)&v27);
    MidiPort = v13;
    if ( v13 == -2147024809 )
    {
      v14 = 0x7FFFFFFF;
    }
    else
    {
      if ( v13 < 0 )
        goto LABEL_22;
      v14 = (unsigned __int64)v27;
    }
  }
  else
  {
LABEL_13:
    v12 = 0x7FFFFFFF;
    v15 = StringCchLengthW(a6, 0x7FFFFFFFu, (unsigned __int64 *)&v27);
    MidiPort = v15;
    if ( v15 == -2147024809 )
    {
      v16 = 0x7FFFFFFF;
    }
    else
    {
      if ( v15 < 0 )
        goto LABEL_22;
      v16 = (__int64)v27;
    }
    v14 = v16 + 7;
    if ( v14 <= 0x7FFFFFFF )
    {
      v17 = v14;
    }
    else
    {
      v14 = 0x7FFFFFFF;
      v17 = 0x7FFFFFFF;
    }
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(&pv, 2 * v17) )
    {
      MidiPort = -2147024882;
      goto LABEL_22;
    }
    MidiPort = StringCchPrintfW((unsigned __int16 *)pv, v14, L"%s [%d]", a6, *a7);
    if ( MidiPort < 0 )
      goto LABEL_22;
  }
  if ( a5 > 1 )
  {
    v21 = v14 + 7;
    if ( v21 <= 0x7FFFFFFF )
      v12 = v21;
    else
      v21 = 0x7FFFFFFF;
    v27 = 0;
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(&v27, 2 * v12) )
    {
      MidiPort = -2147024882;
      v22 = v27;
LABEL_32:
      CoTaskMemFree(v22);
      goto LABEL_22;
    }
    v23 = v21;
    v24 = v27;
    MidiPort = StringCchPrintfW(v27, v23, L"%d - %s", a5, pv);
    if ( MidiPort < 0 )
    {
      v22 = v24;
      goto LABEL_32;
    }
    if ( pv != v24 )
    {
      v25 = v24;
      v24 = 0;
      CoTaskMemFree(pv);
      pv = v25;
    }
    CoTaskMemFree(v24);
  }
  v26[0] = v10;
  StringCchPrintfW(v34, 0x16u, v36, v30, *(_QWORD *)v26);
  MidiPort = CreateMidiPort(v33, a2, v34, (const unsigned __int16 *)pv, v29, v10, 0);
  if ( MidiPort >= 0 )
  {
    ++*a7;
    goto LABEL_24;
  }
LABEL_22:
  v18 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v18 > 2u )
  {
    v30 = MidiPort;
    LODWORD(v27) = 1262;
    v33 = (unsigned __int16 *)"CreateMidiPortForKsPin";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v18,
      (unsigned int)word_180076E9A,
      v19,
      v20,
      (__int64)&v33,
      (__int64)&v27,
      (__int64)&v30);
  }
LABEL_24:
  CoTaskMemFree(pv);
  pv = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
}

```

## disassembly

```asm
0x18003868c  push    rbp
0x18003868e  push    rbx
0x18003868f  push    rsi
0x180038690  push    rdi
0x180038691  push    r12
0x180038693  push    r13
0x180038695  push    r14
0x180038697  push    r15
0x180038699  lea     rbp, [rsp-7]
0x18003869e  sub     rsp, 0E8h
0x1800386a5  mov     rax, cs:__security_cookie
0x1800386ac  xor     rax, rsp
0x1800386af  mov     [rbp+3Fh+var_50], rax
0x1800386b3  mov     [rbp+3Fh+var_B8], r9
0x1800386b7  mov     [rsp+120h+var_CC], r8d
0x1800386bc  mov     r13, rdx
0x1800386bf  mov     rbx, rcx
0x1800386c2  mov     r15, [rbp+3Fh+arg_28]
0x1800386c6  mov     r14, [rbp+3Fh+arg_30]
0x1800386ca  xor     esi, esi
0x1800386cc  mov     [rsp+120h+var_C0], rsi
0x1800386d1  mov     [rsp+120h+var_C8], esi
0x1800386d5  mov     [rsp+120h+pv], rsi
0x1800386da  mov     [rsp+120h+var_E0], rsi
0x1800386df  movups  xmm0, xmmword ptr cs:aMidii12345678P; "MIDII_12345678.P1234"
0x1800386e6  movups  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x1800386ea  movups  xmm1, xmmword ptr cs:aMidii12345678P+10h; "345678.P1234"
0x1800386f1  movups  xmmword ptr [rbp+3Fh+var_A0], xmm1
0x1800386f5  movups  xmm0, xmmword ptr cs:aMidii12345678P+1Ch; ".P1234"
0x1800386fc  movups  xmmword ptr [rbp+3Fh+var_A0+0Ch], xmm0
0x180038700  movups  xmm1, xmmword ptr cs:aMidii08i32xP04; "MIDII_%08I32X.P_%04I32X"
0x180038707  movups  xmmword ptr [rbp+3Fh+var_80], xmm1
0x18003870b  movups  xmm0, xmmword ptr cs:aMidii08i32xP04+10h; "8I32X.P_%04I32X"
0x180038712  movups  [rbp+3Fh+var_70], xmm0
0x180038716  movups  xmm1, xmmword ptr cs:aMidii08i32xP04+20h; "%04I32X"
0x18003871d  movups  [rbp+3Fh+var_60], xmm1
0x180038721  mov     [rsp+120h+var_D0], esi
0x180038725  mov     rax, [rcx]
0x180038728  lea     rdx, [rsp+120h+var_C8]
0x18003872d  mov     rax, [rax+20h]
0x180038731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038736  mov     edi, eax
0x180038738  test    eax, eax
0x18003873a  js      loc_18003885B
0x180038740  movzx   r12d, word ptr [rsp+120h+var_C8]
0x180038746  mov     rax, [rbx]
0x180038749  lea     r8, [rsp+120h+var_C0]
0x18003874e  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x180038755  mov     rcx, rbx
0x180038758  mov     rax, [rax]
0x18003875b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038760  mov     edi, eax
0x180038762  test    eax, eax
0x180038764  js      loc_18003885B
0x18003876a  mov     rcx, [rsp+120h+var_C0]
0x18003876f  mov     rax, [rcx]
0x180038772  lea     rdx, [rsp+120h+var_D0]
0x180038777  mov     rax, [rax+20h]
0x18003877b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038780  mov     edi, eax
0x180038782  test    eax, eax
0x180038784  js      loc_18003885B
0x18003878a  mov     eax, esi
0x18003878c  cmp     [rsp+120h+var_D0], 1
0x180038791  setnz   al
0x180038794  mov     [rsp+120h+var_D0], eax
0x180038798  mov     rax, [rbx]
0x18003879b  lea     rdx, [rsp+120h+pv]
0x1800387a0  mov     rcx, rbx
0x1800387a3  mov     rax, [rax+18h]
0x1800387a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387ac  mov     edi, eax
0x1800387ae  test    eax, eax
0x1800387b0  js      loc_18003885B
0x1800387b6  mov     rcx, [rsp+120h+pv]; unsigned __int16 *
0x1800387bb  test    rcx, rcx
0x1800387be  jz      short loc_180038801
0x1800387c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800387c4  inc     rax
0x1800387c7  cmp     [rcx+rax*2], si
0x1800387cb  jnz     short loc_1800387C4
0x1800387cd  test    rax, rax
0x1800387d0  jz      short loc_180038801
0x1800387d2  lea     r8, [rsp+120h+var_E0]; unsigned __int64 *
0x1800387d7  mov     esi, 7FFFFFFFh
0x1800387dc  mov     edx, esi; unsigned __int64
0x1800387de  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800387e3  mov     edi, eax
0x1800387e5  cmp     eax, 80070057h
0x1800387ea  jnz     short loc_1800387F3
0x1800387ec  mov     ebx, esi
0x1800387ee  jmp     loc_18003890D
0x1800387f3  test    eax, eax
0x1800387f5  js      short loc_180038859
0x1800387f7  mov     rbx, [rsp+120h+var_E0]
0x1800387fc  jmp     loc_18003890D
0x180038801  lea     r8, [rsp+120h+var_E0]; unsigned __int64 *
0x180038806  mov     esi, 7FFFFFFFh
0x18003880b  mov     edx, esi; unsigned __int64
0x18003880d  mov     rcx, r15; unsigned __int16 *
0x180038810  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038815  mov     edi, eax
0x180038817  cmp     eax, 80070057h
0x18003881c  jnz     short loc_180038822
0x18003881e  mov     ebx, esi
0x180038820  jmp     short loc_18003882B
0x180038822  test    eax, eax
0x180038824  js      short loc_180038859
0x180038826  mov     rbx, [rsp+120h+var_E0]
0x18003882b  add     rbx, 7
0x18003882f  cmp     rbx, rsi
0x180038832  jbe     short loc_18003883C
0x180038834  mov     rbx, rsi
0x180038837  mov     rdx, rsi
0x18003883a  jmp     short loc_18003883F
0x18003883c  mov     rdx, rbx
0x18003883f  add     rdx, rdx
0x180038842  lea     rcx, [rsp+120h+pv]
0x180038847  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x18003884c  test    al, al
0x18003884e  jnz     loc_1800388E5
0x180038854  mov     edi, 8007000Eh
0x180038859  xor     esi, esi
0x18003885b  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180038860  mov     ecx, [rax]
0x180038862  cmp     ecx, 2
0x180038865  jbe     short loc_1800388AB
0x180038867  mov     [rsp+120h+var_CC], edi
0x18003886b  mov     dword ptr [rsp+120h+var_E0], 4EEh
0x180038873  lea     rcx, aCreatemidiport; "CreateMidiPortForKsPin"
0x18003887a  mov     [rbp+3Fh+var_B8], rcx
0x18003887e  lea     rcx, [rsp+120h+var_CC]
0x180038883  mov     [rsp+120h+var_F0], rcx
0x180038888  lea     rcx, [rsp+120h+var_E0]
0x18003888d  mov     qword ptr [rsp+120h+var_F8], rcx
0x180038892  lea     rcx, [rbp+3Fh+var_B8]
0x180038896  mov     qword ptr [rsp+120h+var_100], rcx
0x18003889b  lea     rdx, word_180076E9A
0x1800388a2  mov     rcx, rax
0x1800388a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800388aa  nop
0x1800388ab  mov     rcx, [rsp+120h+pv]; pv
0x1800388b0  call    cs:__imp_CoTaskMemFree
0x1800388b6  mov     [rsp+120h+pv], rsi
0x1800388bb  lea     rcx, [rsp+120h+var_C0]
0x1800388c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800388c5  mov     rcx, [rbp+3Fh+var_50]
0x1800388c9  xor     rcx, rsp; StackCookie
0x1800388cc  call    __security_check_cookie
0x1800388d1  add     rsp, 0E8h
0x1800388d8  pop     r15
0x1800388da  pop     r14
0x1800388dc  pop     r13
0x1800388de  pop     r12
0x1800388e0  pop     rdi
0x1800388e1  pop     rsi
0x1800388e2  pop     rbx
0x1800388e3  pop     rbp
0x1800388e4  retn
0x1800388e5  mov     eax, [r14]
0x1800388e8  mov     [rsp+120h+var_100], eax
0x1800388ec  mov     r9, r15
0x1800388ef  lea     r8, aSD; "%s [%d]"
0x1800388f6  mov     rdx, rbx; unsigned __int64
0x1800388f9  mov     rcx, [rsp+120h+pv]; unsigned __int16 *
0x1800388fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038903  mov     edi, eax
0x180038905  test    eax, eax
0x180038907  js      loc_180038859
0x18003890d  cmp     [rbp+3Fh+arg_20], 1
0x180038911  jbe     loc_1800389B0
0x180038917  add     rbx, 7
0x18003891b  cmp     rbx, rsi
0x18003891e  jbe     short loc_180038925
0x180038920  mov     rbx, rsi
0x180038923  jmp     short loc_180038928
0x180038925  mov     rsi, rbx
0x180038928  mov     [rsp+120h+var_E0], 0
0x180038931  lea     rdx, [rsi+rsi]
0x180038935  lea     rcx, [rsp+120h+var_E0]
0x18003893a  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x18003893f  xor     esi, esi
0x180038941  test    al, al
0x180038943  jnz     short loc_18003895A
0x180038945  mov     edi, 8007000Eh
0x18003894a  mov     rcx, [rsp+120h+var_E0]; pv
0x18003894f  call    cs:__imp_CoTaskMemFree
0x180038955  jmp     loc_18003885B
0x18003895a  mov     rax, [rsp+120h+pv]
0x18003895f  mov     qword ptr [rsp+120h+var_100], rax
0x180038964  mov     r9d, [rbp+3Fh+arg_20]
0x180038968  lea     r8, aDS; "%d - %s"
0x18003896f  mov     rdx, rbx; unsigned __int64
0x180038972  mov     rbx, [rsp+120h+var_E0]
0x180038977  mov     rcx, rbx; unsigned __int16 *
0x18003897a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003897f  mov     edi, eax
0x180038981  test    eax, eax
0x180038983  jns     short loc_18003898A
0x180038985  mov     rcx, rbx
0x180038988  jmp     short loc_18003894F
0x18003898a  mov     rcx, [rsp+120h+pv]; pv
0x18003898f  cmp     rcx, rbx
0x180038992  jz      short loc_1800389A5
0x180038994  mov     rdi, rbx
0x180038997  mov     rbx, rsi
0x18003899a  call    cs:__imp_CoTaskMemFree
0x1800389a0  mov     [rsp+120h+pv], rdi
0x1800389a5  mov     rcx, rbx; pv
0x1800389a8  call    cs:__imp_CoTaskMemFree
0x1800389ae  jmp     short loc_1800389B2
0x1800389b0  xor     esi, esi
0x1800389b2  mov     [rsp+120h+var_100], r12d
0x1800389b7  mov     r9d, [rsp+120h+var_CC]
0x1800389bc  lea     r8, [rbp+3Fh+var_80]; unsigned __int16 *
0x1800389c0  mov     edx, 16h; unsigned __int64
0x1800389c5  lea     rcx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x1800389c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800389ce  mov     eax, [rsp+120h+var_D0]
0x1800389d2  mov     [rsp+120h+var_F0], rsi; unsigned __int64
0x1800389d7  mov     [rsp+120h+var_F8], r12d; unsigned int
0x1800389dc  mov     [rsp+120h+var_100], eax; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x1800389e0  mov     r9, [rsp+120h+pv]; unsigned __int16 *
0x1800389e5  lea     r8, [rbp+3Fh+var_B0]; unsigned __int16 *
0x1800389e9  mov     rdx, r13; unsigned __int16 *
0x1800389ec  mov     rcx, [rbp+3Fh+var_B8]; unsigned __int16 *
0x1800389f0  call    ?CreateMidiPort@@YAJPEBG000W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@I_K@Z; CreateMidiPort(ushort const *,ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_devicetopology_0000_0000_0011,uint,unsigned __int64)
0x1800389f5  mov     edi, eax
0x1800389f7  test    eax, eax
0x1800389f9  js      loc_18003885B
0x1800389ff  inc     dword ptr [r14]
0x180038a02  jmp     loc_1800388AB
```
