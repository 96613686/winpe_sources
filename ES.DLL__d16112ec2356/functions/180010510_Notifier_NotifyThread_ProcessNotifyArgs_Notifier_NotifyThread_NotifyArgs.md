# Notifier::NotifyThread::ProcessNotifyArgs(Notifier::NotifyThread::NotifyArgs *)

- ea: `0x180010510`
- end: `0x180010a01`
- name: `?ProcessNotifyArgs@NotifyThread@Notifier@@AEAAJPEAUNotifyArgs@12@@Z`
- size: `1265`
- prototype: `__int64 __fastcall(struct IEventObjectChange **this, struct Notifier::NotifyThread::NotifyArgs *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001023c`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180010510`
- `0x180010a08`
- `0x180012654`
- `0x180027ea0`
- `0x1800354b0`
- `0x1800354d0`
- `0x1800434c6`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800109be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043ec9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800109be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043ed3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043ed3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001071d`
- `OLEAUT32!__imp_SysAllocString` at `0x180010730`
- `OLEAUT32!__imp_SysAllocString` at `0x180010743`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001071d`
- `OLEAUT32!__imp_SysAllocString` at `0x180010730`
- `OLEAUT32!__imp_SysAllocString` at `0x180010743`
- `OLEAUT32!__imp_SysFreeString` at `0x18001098e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010999`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109af`
- `OLEAUT32!__imp_SysFreeString` at `0x180043e96`
- `OLEAUT32!__imp_SysFreeString` at `0x180043ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x180043eaa`
- `OLEAUT32!__imp_SysFreeString` at `0x180043eb4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001098e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010999`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109af`
- `OLEAUT32!__imp_SysFreeString` at `0x180043e96`
- `OLEAUT32!__imp_SysFreeString` at `0x180043ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x180043eaa`
- `OLEAUT32!__imp_SysFreeString` at `0x180043eb4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010675`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001068f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010675`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001068f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180010628`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001080d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001088d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180010628`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001080d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001088d`

## string_xrefs

- `0x180010643`: `com\complus\src\events\tier2\notify.cpp`
- `0x180010783`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800108ae`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800108d1`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800108f0`: `com\complus\src\events\tier2\notify.cpp`
- `0x18001090f`: `com\complus\src\events\tier2\notify.cpp`
- `0x18001095a`: `com\complus\src\events\tier2\notify.cpp`
- `0x180010931`: `com\complus\src\events\shared\espartitionutil.cpp`

## pseudocode

```c
__int64 __fastcall Notifier::NotifyThread::ProcessNotifyArgs(
        struct IEventObjectChange **this,
        struct Notifier::NotifyThread::NotifyArgs *a2)
{
  struct IEventObjectChange **v4; // r12
  _OWORD *v5; // rbx
  unsigned __int64 v6; // rsi
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 (__fastcall *v9)(); // rbx
  __int64 (__fastcall *v10)(); // rsi
  int v11; // eax
  OLECHAR *v12; // r13
  int v13; // eax
  unsigned int v14; // ebx
  void *v15; // rcx
  _DWORD v17[2]; // [rsp+30h] [rbp-218h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-210h]
  BSTR v19; // [rsp+40h] [rbp-208h]
  BSTR v20; // [rsp+48h] [rbp-200h]
  GUID iid; // [rsp+F0h] [rbp-158h] BYREF
  GUID v22; // [rsp+100h] [rbp-148h] BYREF
  GUID pclsid; // [rsp+110h] [rbp-138h] BYREF
  OLECHAR sz[8]; // [rsp+120h] [rbp-128h] BYREF
  __int128 v25; // [rsp+130h] [rbp-118h]
  __int128 v26; // [rsp+140h] [rbp-108h]
  _BYTE v27[28]; // [rsp+150h] [rbp-F8h]
  __int16 v28; // [rsp+16Ch] [rbp-DCh]
  OLECHAR psz[8]; // [rsp+170h] [rbp-D8h] BYREF
  __int128 v30; // [rsp+180h] [rbp-C8h]
  __int128 v31; // [rsp+190h] [rbp-B8h]
  _BYTE v32[28]; // [rsp+1A0h] [rbp-A8h]
  __int16 v33; // [rsp+1BCh] [rbp-8Ch]
  OLECHAR v34[8]; // [rsp+1C0h] [rbp-88h] BYREF
  __int128 v35; // [rsp+1D0h] [rbp-78h]
  __int128 v36; // [rsp+1E0h] [rbp-68h]
  _BYTE v37[28]; // [rsp+1F0h] [rbp-58h]
  __int16 v38; // [rsp+20Ch] [rbp-3Ch]

  pclsid = GUID_NULL;
  v22 = GUID_NULL;
  memset_0(v17, 0, 0xC0u);
  v4 = this + 1;
  if ( *this )
  {
    if ( !*v4 )
      InternalAssert(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2BEu, 0x14u, L"0 != m_eventClass2");
  }
  else
  {
    if ( *v4 )
      InternalAssert(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2B6u, 0x14u, L"0 == m_eventClass2");
    Notifier::NotifyThread::CreateEventClasses((struct CEventSystem2 **)this, (LPVOID *)this, (LPVOID *)this + 1);
  }
  v5 = (_OWORD *)*((_QWORD *)a2 + 2);
  if ( !v5 )
    InternalError(L"com\\complus\\src\\events\\shared\\espartitionutil.cpp", 0xA3u, 0x80001203, 0x10u);
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)v5 + v6) );
  sz[0] = 0;
  psz[0] = 0;
  v34[0] = 0;
  if ( v6 < 0x26 )
    goto LABEL_10;
  *(_OWORD *)sz = *v5;
  v25 = v5[1];
  v26 = v5[2];
  *(_OWORD *)v27 = v5[3];
  *(_OWORD *)&v27[12] = *(_OWORD *)((char *)v5 + 60);
  v28 = 0;
  iid = 0;
  if ( IIDFromString(sz, &iid) < 0 )
    goto LABEL_10;
  if ( v6 > 0x26 )
  {
    if ( v6 < 0x4D )
      goto LABEL_10;
    *(_OWORD *)psz = *(_OWORD *)((char *)v5 + 78);
    v30 = *(_OWORD *)((char *)v5 + 94);
    v31 = *(_OWORD *)((char *)v5 + 110);
    *(_OWORD *)v32 = *(_OWORD *)((char *)v5 + 126);
    *(_OWORD *)&v32[12] = *(_OWORD *)((char *)v5 + 138);
    v33 = 0;
    iid = 0;
    if ( IIDFromString(psz, &iid) < 0 )
      goto LABEL_10;
  }
  if ( v6 > 0x4D )
  {
    if ( v6 < 0x74
      || (*(_OWORD *)v34 = *(_OWORD *)((char *)v5 + 156),
          v35 = *(_OWORD *)((char *)v5 + 172),
          v36 = *(_OWORD *)((char *)v5 + 188),
          *(_OWORD *)v37 = *(_OWORD *)((char *)v5 + 204),
          *(_OWORD *)&v37[12] = *(_OWORD *)((char *)v5 + 216),
          v38 = 0,
          iid = 0,
          IIDFromString(v34, &iid) < 0) )
    {
LABEL_10:
      InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2CDu, 0x14u, -2147024809);
    }
  }
  v7 = CLSIDFromString(psz, &pclsid);
  if ( v7 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2CFu, 0x14u, v7);
  v8 = CLSIDFromString(*((LPCOLESTR *)a2 + 5), &v22);
  if ( v8 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2D2u, 0x14u, v8);
  v9 = funcs_180010700[*((int *)a2 + 6)];
  v10 = v9;
  v11 = ObjectChangeFilter::SwitchSubscriptionCollection(
          (ObjectChangeFilter *)this[4],
          (struct IMultiInterfaceEventControl *)this[2],
          &pclsid,
          &v22);
  if ( v11 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2D9u, 0x14u, v11);
  v12 = SysAllocString(sz);
  ((void (__fastcall *)(_QWORD, _QWORD, OLECHAR *))v9)(*this, *((unsigned int *)a2 + 2), v12);
  v17[0] = 192;
  v17[1] = *((_DWORD *)a2 + 2);
  bstrString = SysAllocString(sz);
  v19 = SysAllocString(psz);
  v20 = SysAllocString(v34);
  v13 = ObjectChangeFilter::SwitchSubscriptionCollection(
          (ObjectChangeFilter *)this[5],
          (struct IMultiInterfaceEventControl *)this[3],
          &pclsid,
          &v22);
  v14 = v13;
  if ( v13 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x2E8u, 0x14u, v13);
  ((void (__fastcall *)(struct IEventObjectChange *, _DWORD *))v10)(*v4, v17);
  SysFreeString(v12);
  SysFreeString(bstrString);
  SysFreeString(v19);
  SysFreeString(v20);
  v15 = (void *)*((_QWORD *)a2 + 4);
  if ( v15 )
  {
    SetEvent(v15);
    CloseHandle(*((HANDLE *)a2 + 4));
    *((_QWORD *)a2 + 4) = 0;
  }
  return v14;
}

```

## disassembly

```asm
0x180010510  mov     [rsp+arg_10], rbx
0x180010515  push    rsi
0x180010516  push    r12
0x180010518  push    r13
0x18001051a  push    r14
0x18001051c  push    r15
0x18001051e  sub     rsp, 220h
0x180010525  mov     rax, cs:__security_cookie
0x18001052c  xor     rax, rsp
0x18001052f  mov     [rsp+248h+var_38], rax
0x180010537  mov     r14, rdx
0x18001053a  mov     r15, rcx
0x18001053d  mov     [rsp+248h+var_220], rdx
0x180010542  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010549  movdqu  xmmword ptr [rsp+248h+pclsid.Data1], xmm0
0x180010552  movdqu  xmmword ptr [rsp+248h+var_148.Data1], xmm0
0x18001055b  xor     r13d, r13d
0x18001055e  mov     [rsp+248h+var_228], r13
0x180010563  xor     edx, edx; Val
0x180010565  mov     r8d, 0C0h; Size
0x18001056b  lea     rcx, [rsp+248h+var_218]; void *
0x180010570  call    memset_0
0x180010575  nop
0x180010576  lea     r12, [r15+8]
0x18001057a  cmp     [r15], r13
0x18001057d  jz      loc_180010942
0x180010583  cmp     [r12], r13
0x180010587  jz      loc_1800108BF
0x18001058d  mov     rbx, [r14+10h]
0x180010591  test    rbx, rbx
0x180010594  jz      loc_180010920
0x18001059a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001059e  inc     rsi
0x1800105a1  cmp     [rbx+rsi*2], r13w
0x1800105a6  jnz     short loc_18001059E
0x1800105a8  mov     [rsp+248h+sz], r13w
0x1800105b1  mov     [rsp+248h+psz], r13w
0x1800105ba  mov     [rsp+248h+var_88], r13w
0x1800105c3  cmp     rsi, 26h ; '&'
0x1800105c7  jb      short loc_180010632
0x1800105c9  movups  xmm0, xmmword ptr [rbx]
0x1800105cc  movaps  xmmword ptr [rsp+248h+sz], xmm0
0x1800105d4  movups  xmm1, xmmword ptr [rbx+10h]
0x1800105d8  movaps  [rsp+248h+var_118], xmm1
0x1800105e0  movups  xmm0, xmmword ptr [rbx+20h]
0x1800105e4  movaps  [rsp+248h+var_108], xmm0
0x1800105ec  movups  xmm1, xmmword ptr [rbx+30h]
0x1800105f0  movaps  xmmword ptr [rsp+248h+var_F8], xmm1
0x1800105f8  movups  xmm0, xmmword ptr [rbx+3Ch]
0x1800105fc  movups  xmmword ptr [rsp+248h+var_F8+0Ch], xmm0
0x180010604  mov     [rsp+248h+var_DC], r13w
0x18001060d  xorps   xmm0, xmm0
0x180010610  movups  xmmword ptr [rsp+248h+iid.Data1], xmm0
0x180010618  lea     rdx, [rsp+248h+iid]; lpiid
0x180010620  lea     rcx, [rsp+248h+sz]; lpsz
0x180010628  call    cs:__imp_IIDFromString
0x18001062e  test    eax, eax
0x180010630  jns     short loc_180010651
0x180010632  mov     edx, 2CDh; unsigned int
0x180010637  mov     r8d, 14h; unsigned __int16
0x18001063d  mov     r9d, 80070057h; int
0x180010643  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18001064a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001064f  jmp     short loc_180010665
0x180010651  cmp     rsi, 26h ; '&'
0x180010655  ja      loc_180010820
0x18001065b  cmp     rsi, 4Dh ; 'M'
0x18001065f  ja      loc_180010794
0x180010665  lea     rdx, [rsp+248h+pclsid]; pclsid
0x18001066d  lea     rcx, [rsp+248h+psz]; lpsz
0x180010675  call    cs:__imp_CLSIDFromString
0x18001067b  test    eax, eax
0x18001067d  js      loc_1800108A0
0x180010683  lea     rdx, [rsp+248h+var_148]; pclsid
0x18001068b  mov     rcx, [r14+28h]; lpsz
0x18001068f  call    cs:__imp_CLSIDFromString
0x180010695  test    eax, eax
0x180010697  js      loc_1800108E2
0x18001069d  movsxd  rax, dword ptr [r14+18h]
0x1800106a1  lea     rsi, __ImageBase
0x1800106a8  mov     rbx, ds:(funcs_180010700 - 180000000h)[rsi+rax*8]
0x1800106b0  mov     rsi, ds:(funcs_180010700 - 180000000h)[rsi+rax*8]
0x1800106b8  lea     r9, [rsp+248h+var_148]; struct _GUID *
0x1800106c0  lea     r8, [rsp+248h+pclsid]; struct _GUID *
0x1800106c8  mov     rdx, [r15+10h]; struct IMultiInterfaceEventControl *
0x1800106cc  mov     rcx, [r15+20h]; this
0x1800106d0  call    ?SwitchSubscriptionCollection@ObjectChangeFilter@@QEAAJPEAUIMultiInterfaceEventControl@@AEBU_GUID@@1@Z; ObjectChangeFilter::SwitchSubscriptionCollection(IMultiInterfaceEventControl *,_GUID const &,_GUID const &)
0x1800106d5  test    eax, eax
0x1800106d7  js      loc_180010901
0x1800106dd  lea     rcx, [rsp+248h+sz]; psz
0x1800106e5  call    cs:__imp_SysAllocString
0x1800106eb  mov     r13, rax
0x1800106ee  mov     [rsp+248h+var_228], rax
0x1800106f3  mov     r8, rax
0x1800106f6  mov     edx, [r14+8]
0x1800106fa  mov     rcx, [r15]
0x1800106fd  mov     rax, rbx
0x180010700  call    _guard_dispatch_icall$thunk$10345483385596137414; [thunk]: IEventObjectChange2::`vcall'{24,{flat}}
0x180010705  mov     [rsp+248h+var_218], 0C0h
0x18001070d  mov     edx, [r14+8]
0x180010711  mov     [rsp+248h+var_214], edx
0x180010715  lea     rcx, [rsp+248h+sz]; psz
0x18001071d  call    cs:__imp_SysAllocString
0x180010723  mov     [rsp+248h+bstrString], rax
0x180010728  lea     rcx, [rsp+248h+psz]; psz
0x180010730  call    cs:__imp_SysAllocString
0x180010736  mov     [rsp+248h+var_208], rax
0x18001073b  lea     rcx, [rsp+248h+var_88]; psz
0x180010743  call    cs:__imp_SysAllocString
0x180010749  mov     [rsp+248h+var_200], rax
0x18001074e  lea     r9, [rsp+248h+var_148]; struct _GUID *
0x180010756  lea     r8, [rsp+248h+pclsid]; struct _GUID *
0x18001075e  mov     rdx, [r15+18h]; struct IMultiInterfaceEventControl *
0x180010762  mov     rcx, [r15+28h]; this
0x180010766  call    ?SwitchSubscriptionCollection@ObjectChangeFilter@@QEAAJPEAUIMultiInterfaceEventControl@@AEBU_GUID@@1@Z; ObjectChangeFilter::SwitchSubscriptionCollection(IMultiInterfaceEventControl *,_GUID const &,_GUID const &)
0x18001076b  mov     ebx, eax
0x18001076d  test    eax, eax
0x18001076f  jns     loc_180010979
0x180010775  mov     r8d, 14h; unsigned __int16
0x18001077b  mov     r9d, eax; int
0x18001077e  mov     edx, 2E8h; unsigned int
0x180010783  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18001078a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001078f  jmp     loc_180010979
0x180010794  cmp     rsi, 74h ; 't'
0x180010798  jb      loc_180010632
0x18001079e  movups  xmm0, xmmword ptr [rbx+9Ch]
0x1800107a5  movaps  xmmword ptr [rsp+248h+var_88], xmm0
0x1800107ad  movups  xmm1, xmmword ptr [rbx+0ACh]
0x1800107b4  movaps  [rsp+248h+var_78], xmm1
0x1800107bc  movups  xmm0, xmmword ptr [rbx+0BCh]
0x1800107c3  movaps  [rsp+248h+var_68], xmm0
0x1800107cb  movups  xmm1, xmmword ptr [rbx+0CCh]
0x1800107d2  movaps  xmmword ptr [rsp+248h+var_58], xmm1
0x1800107da  movups  xmm0, xmmword ptr [rbx+0D8h]
0x1800107e1  movups  xmmword ptr [rsp+248h+var_58+0Ch], xmm0
0x1800107e9  mov     [rsp+248h+var_3C], r13w
0x1800107f2  xorps   xmm0, xmm0
0x1800107f5  movups  xmmword ptr [rsp+248h+iid.Data1], xmm0
0x1800107fd  lea     rdx, [rsp+248h+iid]; lpiid
0x180010805  lea     rcx, [rsp+248h+var_88]; lpsz
0x18001080d  call    cs:__imp_IIDFromString
0x180010813  test    eax, eax
0x180010815  jns     loc_180010665
0x18001081b  jmp     loc_180010632
0x180010820  cmp     rsi, 4Dh ; 'M'
0x180010824  jb      loc_180010632
0x18001082a  movups  xmm0, xmmword ptr [rbx+4Eh]
0x18001082e  movaps  xmmword ptr [rsp+248h+psz], xmm0
0x180010836  movups  xmm1, xmmword ptr [rbx+5Eh]
0x18001083a  movaps  [rsp+248h+var_C8], xmm1
0x180010842  movups  xmm0, xmmword ptr [rbx+6Eh]
0x180010846  movaps  [rsp+248h+var_B8], xmm0
0x18001084e  movups  xmm1, xmmword ptr [rbx+7Eh]
0x180010852  movaps  xmmword ptr [rsp+248h+var_A8], xmm1
0x18001085a  movups  xmm0, xmmword ptr [rbx+8Ah]
0x180010861  movups  xmmword ptr [rsp+248h+var_A8+0Ch], xmm0
0x180010869  mov     [rsp+248h+var_8C], r13w
0x180010872  xorps   xmm0, xmm0
0x180010875  movups  xmmword ptr [rsp+248h+iid.Data1], xmm0
0x18001087d  lea     rdx, [rsp+248h+iid]; lpiid
0x180010885  lea     rcx, [rsp+248h+psz]; lpsz
0x18001088d  call    cs:__imp_IIDFromString
0x180010893  test    eax, eax
0x180010895  js      loc_180010632
0x18001089b  jmp     loc_18001065B
0x1800108a0  mov     r8d, 14h; unsigned __int16
0x1800108a6  mov     r9d, eax; int
0x1800108a9  mov     edx, 2CFh; unsigned int
0x1800108ae  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x1800108b5  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800108ba  jmp     loc_180010683
0x1800108bf  mov     r8d, 14h; unsigned __int16
0x1800108c5  lea     r9, a0MEventclass2; "0 != m_eventClass2"
0x1800108cc  mov     edx, 2BEh; unsigned int
0x1800108d1  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x1800108d8  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800108dd  jmp     loc_18001058D
0x1800108e2  mov     r8d, 14h; unsigned __int16
0x1800108e8  mov     r9d, eax; int
0x1800108eb  mov     edx, 2D2h; unsigned int
0x1800108f0  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x1800108f7  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800108fc  jmp     loc_18001069D
0x180010901  mov     r8d, 14h; unsigned __int16
0x180010907  mov     r9d, eax; int
0x18001090a  mov     edx, 2D9h; unsigned int
0x18001090f  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180010916  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001091b  jmp     loc_1800106DD
0x180010920  mov     edx, 0A3h; unsigned int
0x180010925  mov     r9d, 10h; unsigned __int16
0x18001092b  mov     r8d, 80001203h; unsigned int
0x180010931  lea     rcx, aComComplusSrcE_11; "com\\complus\\src\\events\\shared\\espa"...
0x180010938  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001093d  jmp     loc_18001059A
0x180010942  cmp     [r12], r13
0x180010946  jz      short loc_180010966
0x180010948  mov     r8d, 14h; unsigned __int16
0x18001094e  lea     r9, a0MEventclass2_0; "0 == m_eventClass2"
0x180010955  mov     edx, 2B6h; unsigned int
0x18001095a  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180010961  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180010966  mov     r8, r12; struct IEventObjectChange2 **
0x180010969  mov     rdx, r15; struct IEventObjectChange **
0x18001096c  mov     rcx, r15; this
0x18001096f  call    ?CreateEventClasses@NotifyThread@Notifier@@AEAAXPEAPEAUIEventObjectChange@@PEAPEAUIEventObjectChange2@@@Z; Notifier::NotifyThread::CreateEventClasses(IEventObjectChange * *,IEventObjectChange2 * *)
0x180010974  jmp     loc_18001058D
0x180010979  lea     rdx, [rsp+248h+var_218]
0x18001097e  mov     rcx, [r12]
0x180010982  mov     rax, rsi
0x180010985  call    _guard_dispatch_icall$thunk$10345483385596137414; [thunk]: IEventObjectChange2::`vcall'{24,{flat}}
0x18001098a  nop
0x18001098b  mov     rcx, r13; bstrString
0x18001098e  call    cs:__imp_SysFreeString
0x180010994  mov     rcx, [rsp+248h+bstrString]; bstrString
0x180010999  call    cs:__imp_SysFreeString
0x18001099f  mov     rcx, [rsp+248h+var_208]; bstrString
0x1800109a4  call    cs:__imp_SysFreeString
0x1800109aa  mov     rcx, [rsp+248h+var_200]; bstrString
0x1800109af  call    cs:__imp_SysFreeString
0x1800109b5  mov     rcx, [r14+20h]; hEvent
0x1800109b9  test    rcx, rcx
0x1800109bc  jz      short loc_1800109D6
0x1800109be  call    cs:__imp_SetEvent
0x1800109c4  mov     rcx, [r14+20h]; hObject
0x1800109c8  call    cs:__imp_CloseHandle
0x1800109ce  mov     qword ptr [r14+20h], 0
0x1800109d6  mov     eax, ebx
0x1800109d8  mov     rcx, [rsp+248h+var_38]
0x1800109e0  xor     rcx, rsp; StackCookie
0x1800109e3  call    __security_check_cookie
0x1800109e8  mov     rbx, [rsp+248h+arg_10]
0x1800109f0  add     rsp, 220h
0x1800109f7  pop     r15
0x1800109f9  pop     r14
0x1800109fb  pop     r13
0x1800109fd  pop     r12
0x1800109ff  pop     rsi
0x180010a00  retn
0x180043e88  push    rbx
0x180043e8a  push    rbp
0x180043e8b  sub     rsp, 28h
0x180043e8f  mov     rbp, rdx
0x180043e92  mov     rcx, [rbp+20h]; bstrString
0x180043e96  call    cs:__imp_SysFreeString
0x180043e9c  mov     rcx, [rbp+38h]; bstrString
0x180043ea0  call    cs:__imp_SysFreeString
0x180043ea6  mov     rcx, [rbp+40h]; bstrString
0x180043eaa  call    cs:__imp_SysFreeString
0x180043eb0  mov     rcx, [rbp+48h]; bstrString
0x180043eb4  call    cs:__imp_SysFreeString
0x180043eba  mov     rbx, [rbp+28h]
0x180043ebe  cmp     qword ptr [rbx+20h], 0
0x180043ec3  jz      short loc_180043EE1
0x180043ec5  mov     rcx, [rbx+20h]; hEvent
0x180043ec9  call    cs:__imp_SetEvent
0x180043ecf  mov     rcx, [rbx+20h]; hObject
0x180043ed3  call    cs:__imp_CloseHandle
0x180043ed9  mov     qword ptr [rbx+20h], 0
0x180043ee1  add     rsp, 28h
0x180043ee5  pop     rbp
0x180043ee6  pop     rbx
0x180043ee7  retn
```
