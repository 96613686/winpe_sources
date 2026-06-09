# CMidiBuilder::CreateMidiPortForKsPin(IPart *,ushort const *,ulong,ushort const *,uint,ushort const *,uint *)

- ea: `0x18003d314`
- end: `0x18003d69d`
- name: `?CreateMidiPortForKsPin@CMidiBuilder@@AEAAXPEAUIPart@@PEBGK1I1PEAI@Z`
- size: `905`
- prototype: `void __fastcall(CMidiBuilder *this, struct IPart *, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ce28`

## callees

- `0x180001734`
- `0x180006b0c`
- `0x180010dd0`
- `0x18001f374`
- `0x180024208`
- `0x18003d314`
- `0x18003e920`
- `0x180049040`
- `0x18004986c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d63d`

## string_xrefs

- `0x18003d502`: `CMidiBuilder::CreateMidiPortForKsPin`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CMidiBuilder::CreateMidiPortForKsPin(
        CMidiBuilder *this,
        struct IPart *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned int *a8)
{
  int MidiPort; // edi
  unsigned int v11; // r12d
  __int64 v12; // rax
  __int64 v13; // rsi
  int v14; // eax
  unsigned __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rdx
  const struct _tlgProvider_t *v19; // rax
  int v20; // r8d
  int v21; // r9d
  unsigned __int64 v22; // rbx
  unsigned __int16 *v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rbx
  unsigned __int16 *v26; // rdi
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v27[2]; // [rsp+20h] [rbp-B9h]
  unsigned __int16 *v28; // [rsp+40h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-91h] BYREF
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v30; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-85h] BYREF
  int v32; // [rsp+58h] [rbp-81h] BYREF
  __int64 v33; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int16 v35[8]; // [rsp+70h] [rbp-69h] BYREF
  _OWORD v36[2]; // [rsp+80h] [rbp-59h]
  unsigned __int16 v37[8]; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-29h]
  __int128 v39; // [rsp+C0h] [rbp-19h]

  v31 = a4;
  v34 = a5;
  v33 = 0;
  v32 = 0;
  pv = 0;
  v28 = 0;
  *(_OWORD *)v35 = *(_OWORD *)L"MIDII_12345678.P1234";
  v36[0] = *(_OWORD *)L"345678.P1234";
  *(_OWORD *)((char *)v36 + 12) = *(_OWORD *)L".P1234";
  *(_OWORD *)v37 = *(_OWORD *)L"MIDII_%08I32X.P_%04I32X";
  v38 = *(_OWORD *)L"8I32X.P_%04I32X";
  v39 = *(_OWORD *)L"%04I32X";
  v30 = In;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, int *))a2->lpVtbl->GetLocalId)(a2, &v32);
  if ( MidiPort < 0 )
    goto LABEL_22;
  v11 = (unsigned __int16)v32;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &GUID_9c2c4058_23f5_41de_877a_df3af236a09e,
               &v33);
  if ( MidiPort < 0 )
    goto LABEL_22;
  MidiPort = (*(__int64 (__fastcall **)(__int64, enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 *))(*(_QWORD *)v33 + 32LL))(
               v33,
               &v30);
  if ( MidiPort < 0 )
    goto LABEL_22;
  v30 = v30 != Out;
  MidiPort = ((__int64 (__fastcall *)(struct IPart *, LPVOID *))a2->lpVtbl->GetName)(a2, &pv);
  if ( MidiPort < 0 )
    goto LABEL_22;
  if ( !pv )
    goto LABEL_13;
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)pv + v12) );
  if ( v12 )
  {
    v13 = 0x7FFFFFFF;
    v14 = StringCchLengthW((const unsigned __int16 *)pv, 0x7FFFFFFFu, (unsigned __int64 *)&v28);
    MidiPort = v14;
    if ( v14 == -2147024809 )
    {
      v15 = 0x7FFFFFFF;
    }
    else
    {
      if ( v14 < 0 )
        goto LABEL_22;
      v15 = (unsigned __int64)v28;
    }
  }
  else
  {
LABEL_13:
    v13 = 0x7FFFFFFF;
    v16 = StringCchLengthW(a7, 0x7FFFFFFFu, (unsigned __int64 *)&v28);
    MidiPort = v16;
    if ( v16 == -2147024809 )
    {
      v17 = 0x7FFFFFFF;
    }
    else
    {
      if ( v16 < 0 )
        goto LABEL_22;
      v17 = (__int64)v28;
    }
    v15 = v17 + 7;
    if ( v15 <= 0x7FFFFFFF )
    {
      v18 = v15;
    }
    else
    {
      v15 = 0x7FFFFFFF;
      v18 = 0x7FFFFFFF;
    }
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(&pv, 2 * v18) )
    {
      MidiPort = -2147024882;
      goto LABEL_22;
    }
    MidiPort = StringCchPrintfW((unsigned __int16 *)pv, v15, L"%s [%d]", a7, *a8);
    if ( MidiPort < 0 )
      goto LABEL_22;
  }
  if ( a6 > 1 )
  {
    v22 = v15 + 7;
    if ( v22 <= 0x7FFFFFFF )
      v13 = v22;
    else
      v22 = 0x7FFFFFFF;
    v28 = 0;
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(&v28, 2 * v13) )
    {
      MidiPort = -2147024882;
      v23 = v28;
LABEL_32:
      CoTaskMemFree(v23);
      goto LABEL_22;
    }
    v24 = v22;
    v25 = v28;
    MidiPort = StringCchPrintfW(v28, v24, L"%d - %s", a6, pv);
    if ( MidiPort < 0 )
    {
      v23 = v25;
      goto LABEL_32;
    }
    if ( pv != v25 )
    {
      v26 = v25;
      v25 = 0;
      CoTaskMemFree(pv);
      pv = v26;
    }
    CoTaskMemFree(v25);
  }
  v27[0] = v11;
  StringCchPrintfW(v35, 0x16u, v37, v31, *(_QWORD *)v27);
  MidiPort = CreateMidiPort(v34, a3, v35, (const unsigned __int16 *)pv, v30, v11, 0);
  if ( MidiPort >= 0 )
  {
    ++*a8;
    goto LABEL_24;
  }
LABEL_22:
  v19 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v19 > 2u )
  {
    v31 = MidiPort;
    LODWORD(v28) = 352;
    v34 = (unsigned __int16 *)"CMidiBuilder::CreateMidiPortForKsPin";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v19,
      (unsigned int)word_180077372,
      v20,
      v21,
      (__int64)&v34,
      (__int64)&v28,
      (__int64)&v31);
  }
LABEL_24:
  CoTaskMemFree(pv);
  pv = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
}

```

## disassembly

```asm
0x18003d314  mov     [rsp-8+arg_0], rbx
0x18003d319  push    rbp
0x18003d31a  push    rsi
0x18003d31b  push    rdi
0x18003d31c  push    r12
0x18003d31e  push    r13
0x18003d320  push    r14
0x18003d322  push    r15
0x18003d324  lea     rbp, [rsp-7]
0x18003d329  sub     rsp, 0E0h
0x18003d330  mov     rax, cs:__security_cookie
0x18003d337  xor     rax, rsp
0x18003d33a  mov     [rbp+37h+var_40], rax
0x18003d33e  mov     [rsp+110h+var_BC], r9d
0x18003d343  mov     r13, r8
0x18003d346  mov     rbx, rdx
0x18003d349  mov     rax, [rbp+37h+arg_20]
0x18003d34d  mov     [rbp+37h+var_A8], rax
0x18003d351  mov     r15, [rbp+37h+arg_30]
0x18003d355  mov     r14, [rbp+37h+arg_38]
0x18003d359  xor     esi, esi
0x18003d35b  mov     [rbp+37h+var_B0], rsi
0x18003d35f  mov     [rsp+110h+var_B8], esi
0x18003d363  mov     [rsp+110h+pv], rsi
0x18003d368  mov     [rsp+110h+var_D0], rsi
0x18003d36d  movups  xmm0, xmmword ptr cs:aMidii12345678P; "MIDII_12345678.P1234"
0x18003d374  movups  xmmword ptr [rbp+37h+var_A0], xmm0
0x18003d378  movups  xmm1, xmmword ptr cs:aMidii12345678P+10h; "345678.P1234"
0x18003d37f  movups  xmmword ptr [rbp+37h+var_90], xmm1
0x18003d383  movups  xmm0, xmmword ptr cs:aMidii12345678P+1Ch; ".P1234"
0x18003d38a  movups  xmmword ptr [rbp+37h+var_90+0Ch], xmm0
0x18003d38e  movups  xmm1, xmmword ptr cs:aMidii08i32xP04; "MIDII_%08I32X.P_%04I32X"
0x18003d395  movups  xmmword ptr [rbp+37h+var_70], xmm1
0x18003d399  movups  xmm0, xmmword ptr cs:aMidii08i32xP04+10h; "8I32X.P_%04I32X"
0x18003d3a0  movups  [rbp+37h+var_60], xmm0
0x18003d3a4  movups  xmm1, xmmword ptr cs:aMidii08i32xP04+20h; "%04I32X"
0x18003d3ab  movups  [rbp+37h+var_50], xmm1
0x18003d3af  mov     [rsp+110h+var_C0], esi
0x18003d3b3  mov     rax, [rdx]
0x18003d3b6  lea     rdx, [rsp+110h+var_B8]
0x18003d3bb  mov     rcx, rbx
0x18003d3be  mov     rax, [rax+20h]
0x18003d3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3c7  mov     edi, eax
0x18003d3c9  test    eax, eax
0x18003d3cb  js      loc_18003D4EA
0x18003d3d1  movzx   r12d, word ptr [rsp+110h+var_B8]
0x18003d3d7  mov     rax, [rbx]
0x18003d3da  lea     r8, [rbp+37h+var_B0]
0x18003d3de  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x18003d3e5  mov     rcx, rbx
0x18003d3e8  mov     rax, [rax]
0x18003d3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3f0  mov     edi, eax
0x18003d3f2  test    eax, eax
0x18003d3f4  js      loc_18003D4EA
0x18003d3fa  mov     rcx, [rbp+37h+var_B0]
0x18003d3fe  mov     rax, [rcx]
0x18003d401  lea     rdx, [rsp+110h+var_C0]
0x18003d406  mov     rax, [rax+20h]
0x18003d40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d40f  mov     edi, eax
0x18003d411  test    eax, eax
0x18003d413  js      loc_18003D4EA
0x18003d419  mov     eax, esi
0x18003d41b  cmp     [rsp+110h+var_C0], 1
0x18003d420  setnz   al
0x18003d423  mov     [rsp+110h+var_C0], eax
0x18003d427  mov     rax, [rbx]
0x18003d42a  lea     rdx, [rsp+110h+pv]
0x18003d42f  mov     rcx, rbx
0x18003d432  mov     rax, [rax+18h]
0x18003d436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d43b  mov     edi, eax
0x18003d43d  test    eax, eax
0x18003d43f  js      loc_18003D4EA
0x18003d445  mov     rcx, [rsp+110h+pv]; unsigned __int16 *
0x18003d44a  test    rcx, rcx
0x18003d44d  jz      short loc_18003D490
0x18003d44f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d453  inc     rax
0x18003d456  cmp     [rcx+rax*2], si
0x18003d45a  jnz     short loc_18003D453
0x18003d45c  test    rax, rax
0x18003d45f  jz      short loc_18003D490
0x18003d461  lea     r8, [rsp+110h+var_D0]; unsigned __int64 *
0x18003d466  mov     esi, 7FFFFFFFh
0x18003d46b  mov     edx, esi; unsigned __int64
0x18003d46d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003d472  mov     edi, eax
0x18003d474  cmp     eax, 80070057h
0x18003d479  jnz     short loc_18003D482
0x18003d47b  mov     ebx, esi
0x18003d47d  jmp     loc_18003D5A2
0x18003d482  test    eax, eax
0x18003d484  js      short loc_18003D4E8
0x18003d486  mov     rbx, [rsp+110h+var_D0]
0x18003d48b  jmp     loc_18003D5A2
0x18003d490  lea     r8, [rsp+110h+var_D0]; unsigned __int64 *
0x18003d495  mov     esi, 7FFFFFFFh
0x18003d49a  mov     edx, esi; unsigned __int64
0x18003d49c  mov     rcx, r15; unsigned __int16 *
0x18003d49f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003d4a4  mov     edi, eax
0x18003d4a6  cmp     eax, 80070057h
0x18003d4ab  jnz     short loc_18003D4B1
0x18003d4ad  mov     ebx, esi
0x18003d4af  jmp     short loc_18003D4BA
0x18003d4b1  test    eax, eax
0x18003d4b3  js      short loc_18003D4E8
0x18003d4b5  mov     rbx, [rsp+110h+var_D0]
0x18003d4ba  add     rbx, 7
0x18003d4be  cmp     rbx, rsi
0x18003d4c1  jbe     short loc_18003D4CB
0x18003d4c3  mov     rbx, rsi
0x18003d4c6  mov     rdx, rsi
0x18003d4c9  jmp     short loc_18003D4CE
0x18003d4cb  mov     rdx, rbx
0x18003d4ce  add     rdx, rdx
0x18003d4d1  lea     rcx, [rsp+110h+pv]
0x18003d4d6  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x18003d4db  test    al, al
0x18003d4dd  jnz     loc_18003D57A
0x18003d4e3  mov     edi, 8007000Eh
0x18003d4e8  xor     esi, esi
0x18003d4ea  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18003d4ef  mov     ecx, [rax]
0x18003d4f1  cmp     ecx, 2
0x18003d4f4  jbe     short loc_18003D53A
0x18003d4f6  mov     [rsp+110h+var_BC], edi
0x18003d4fa  mov     dword ptr [rsp+110h+var_D0], 160h
0x18003d502  lea     rcx, aCmidibuilderCr; "CMidiBuilder::CreateMidiPortForKsPin"
0x18003d509  mov     [rbp+37h+var_A8], rcx
0x18003d50d  lea     rcx, [rsp+110h+var_BC]
0x18003d512  mov     [rsp+110h+var_E0], rcx
0x18003d517  lea     rcx, [rsp+110h+var_D0]
0x18003d51c  mov     qword ptr [rsp+110h+var_E8], rcx
0x18003d521  lea     rcx, [rbp+37h+var_A8]
0x18003d525  mov     qword ptr [rsp+110h+var_F0], rcx
0x18003d52a  lea     rdx, word_180077372
0x18003d531  mov     rcx, rax
0x18003d534  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d539  nop
0x18003d53a  mov     rcx, [rsp+110h+pv]; pv
0x18003d53f  call    cs:__imp_CoTaskMemFree
0x18003d545  mov     [rsp+110h+pv], rsi
0x18003d54a  lea     rcx, [rbp+37h+var_B0]
0x18003d54e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d553  mov     rcx, [rbp+37h+var_40]
0x18003d557  xor     rcx, rsp; StackCookie
0x18003d55a  call    __security_check_cookie
0x18003d55f  mov     rbx, [rsp+110h+arg_0]
0x18003d567  add     rsp, 0E0h
0x18003d56e  pop     r15
0x18003d570  pop     r14
0x18003d572  pop     r13
0x18003d574  pop     r12
0x18003d576  pop     rdi
0x18003d577  pop     rsi
0x18003d578  pop     rbp
0x18003d579  retn
0x18003d57a  mov     eax, [r14]
0x18003d57d  mov     [rsp+110h+var_F0], eax
0x18003d581  mov     r9, r15
0x18003d584  lea     r8, aSD; "%s [%d]"
0x18003d58b  mov     rdx, rbx; unsigned __int64
0x18003d58e  mov     rcx, [rsp+110h+pv]; unsigned __int16 *
0x18003d593  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d598  mov     edi, eax
0x18003d59a  test    eax, eax
0x18003d59c  js      loc_18003D4E8
0x18003d5a2  cmp     [rbp+37h+arg_28], 1
0x18003d5a6  jbe     loc_18003D645
0x18003d5ac  add     rbx, 7
0x18003d5b0  cmp     rbx, rsi
0x18003d5b3  jbe     short loc_18003D5BA
0x18003d5b5  mov     rbx, rsi
0x18003d5b8  jmp     short loc_18003D5BD
0x18003d5ba  mov     rsi, rbx
0x18003d5bd  mov     [rsp+110h+var_D0], 0
0x18003d5c6  lea     rdx, [rsi+rsi]
0x18003d5ca  lea     rcx, [rsp+110h+var_D0]
0x18003d5cf  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x18003d5d4  xor     esi, esi
0x18003d5d6  test    al, al
0x18003d5d8  jnz     short loc_18003D5EF
0x18003d5da  mov     edi, 8007000Eh
0x18003d5df  mov     rcx, [rsp+110h+var_D0]; pv
0x18003d5e4  call    cs:__imp_CoTaskMemFree
0x18003d5ea  jmp     loc_18003D4EA
0x18003d5ef  mov     rax, [rsp+110h+pv]
0x18003d5f4  mov     qword ptr [rsp+110h+var_F0], rax
0x18003d5f9  mov     r9d, [rbp+37h+arg_28]
0x18003d5fd  lea     r8, aDS; "%d - %s"
0x18003d604  mov     rdx, rbx; unsigned __int64
0x18003d607  mov     rbx, [rsp+110h+var_D0]
0x18003d60c  mov     rcx, rbx; unsigned __int16 *
0x18003d60f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d614  mov     edi, eax
0x18003d616  test    eax, eax
0x18003d618  jns     short loc_18003D61F
0x18003d61a  mov     rcx, rbx
0x18003d61d  jmp     short loc_18003D5E4
0x18003d61f  mov     rcx, [rsp+110h+pv]; pv
0x18003d624  cmp     rcx, rbx
0x18003d627  jz      short loc_18003D63A
0x18003d629  mov     rdi, rbx
0x18003d62c  mov     rbx, rsi
0x18003d62f  call    cs:__imp_CoTaskMemFree
0x18003d635  mov     [rsp+110h+pv], rdi
0x18003d63a  mov     rcx, rbx; pv
0x18003d63d  call    cs:__imp_CoTaskMemFree
0x18003d643  jmp     short loc_18003D647
0x18003d645  xor     esi, esi
0x18003d647  mov     [rsp+110h+var_F0], r12d
0x18003d64c  mov     r9d, [rsp+110h+var_BC]
0x18003d651  lea     r8, [rbp+37h+var_70]; unsigned __int16 *
0x18003d655  mov     edx, 16h; unsigned __int64
0x18003d65a  lea     rcx, [rbp+37h+var_A0]; unsigned __int16 *
0x18003d65e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d663  mov     eax, [rsp+110h+var_C0]
0x18003d667  mov     [rsp+110h+var_E0], rsi; unsigned __int64
0x18003d66c  mov     [rsp+110h+var_E8], r12d; unsigned int
0x18003d671  mov     [rsp+110h+var_F0], eax; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x18003d675  mov     r9, [rsp+110h+pv]; unsigned __int16 *
0x18003d67a  lea     r8, [rbp+37h+var_A0]; unsigned __int16 *
0x18003d67e  mov     rdx, r13; unsigned __int16 *
0x18003d681  mov     rcx, [rbp+37h+var_A8]; unsigned __int16 *
0x18003d685  call    ?CreateMidiPort@@YAJPEBG000W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@I_K@Z; CreateMidiPort(ushort const *,ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_devicetopology_0000_0000_0011,uint,unsigned __int64)
0x18003d68a  mov     edi, eax
0x18003d68c  test    eax, eax
0x18003d68e  js      loc_18003D4EA
0x18003d694  inc     dword ptr [r14]
0x18003d697  jmp     loc_18003D53A
```
