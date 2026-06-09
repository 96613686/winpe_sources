# CInkTree::SetupDCompInputVisual(IDCompositionDesktopDevice *,Windows::Foundation::Size)

- ea: `0x1800e10b4`
- end: `0x1800e13a8`
- name: `?SetupDCompInputVisual@CInkTree@@IEAAJPEAUIDCompositionDesktopDevice@@USize@Foundation@Windows@@@Z`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e13b0`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x180005a50`
- `0x1800101bc`
- `0x180019248`
- `0x1800e10b4`
- `0x1800fb010`

## string_xrefs

- `0x1800e12e7`: `CInkTree::SetupDCompInputVisual[Exit]`
- `0x1800e1345`: `CInkTree::SetupDCompInputVisual[Exit]`
- `0x1800e117d`: `Input surface already created`
- `0x1800e1118`: `CInkTree::SetupDCompInputVisual`
- `0x1800e118f`: `CInkTree::SetupDCompInputVisual`
- `0x1800e11ea`: `CInkTree::SetupDCompInputVisual`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkTree::SetupDCompInputVisual(__int64 a1, __int64 a2, __int64 a3)
{
  float v5; // xmm6_4
  int v6; // ecx
  int v7; // r9d
  const wchar_t **v8; // rax
  const wchar_t **v9; // rdi
  int v10; // ebx
  int v11; // ecx
  int v12; // r9d
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD, __int64, _DWORD, const wchar_t **); // rbx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  const wchar_t **v18; // rax
  __int16 *v19; // rdx
  const wchar_t **v21; // [rsp+30h] [rbp-40h]
  const wchar_t **v22; // [rsp+30h] [rbp-40h]
  const wchar_t **v23; // [rsp+38h] [rbp-38h]
  const wchar_t *v24; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v25; // [rsp+48h] [rbp-28h] BYREF
  __int64 v26; // [rsp+50h] [rbp-20h]
  const wchar_t *v27; // [rsp+58h] [rbp-18h] BYREF
  int v28; // [rsp+A0h] [rbp+30h] BYREF
  const wchar_t *v29; // [rsp+B8h] [rbp+48h] BYREF

  v5 = *(float *)&a3;
  v26 = a3;
  if ( !*(_BYTE *)(a1 + 16) )
  {
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, a3) )
      goto LABEL_15;
    v24 = L"Not initialized";
    v25 = L"CInkTree::SetupDCompInputVisual";
    v21 = &v24;
    v8 = &v25;
LABEL_14:
    v28 = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v6,
      (unsigned int)word_18013780A,
      a3,
      v7,
      (__int64)v8,
      (__int64)&v28,
      (__int64)v21);
LABEL_15:
    v9 = (const wchar_t **)(a1 + 32);
LABEL_16:
    v10 = -2147418113;
    goto LABEL_17;
  }
  if ( !*(_QWORD *)(a1 + 240) )
  {
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, a3) )
      goto LABEL_15;
    v25 = L"No wet branch";
    v24 = L"CInkTree::SetupDCompInputVisual";
    v21 = &v25;
    v8 = &v24;
    goto LABEL_14;
  }
  v9 = (const wchar_t **)(a1 + 32);
  if ( *(_QWORD *)(a1 + 32) )
  {
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, a3) )
    {
      v25 = L"Input surface already created";
      v28 = -2147418113;
      v24 = L"CInkTree::SetupDCompInputVisual";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v11,
        (unsigned int)word_18013780A,
        a3,
        v12,
        (__int64)&v24,
        (__int64)&v28,
        (__int64)&v25);
    }
    goto LABEL_16;
  }
  v10 = 0;
LABEL_17:
  v29 = 0;
  if ( v10 < 0 )
    goto LABEL_30;
  v13 = *(_QWORD *)(a1 + 240);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(v13 + 8);
  v29 = *(const wchar_t **)(v13 + 8);
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, const wchar_t **))(*(_QWORD *)a2 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v9);
  v10 = v14(a2, (unsigned int)(int)v5, (unsigned int)(int)*((float *)&v26 + 1), 87, 0, v9);
  if ( v10 < 0
    || (v10 = (*(__int64 (__fastcall **)(const wchar_t *, const wchar_t *))(*(_QWORD *)v29 + 120LL))(v29, *v9), v10 < 0) )
  {
LABEL_30:
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 512, a3) )
    {
      v27 = *v9;
      v25 = v29;
      v24 = L"CInkTree::SetupDCompInputVisual[Exit]";
      v23 = &v27;
      v22 = &v25;
      v18 = &v24;
      v19 = &word_1801454CE;
      goto LABEL_26;
    }
  }
  else if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 512, a3) )
  {
    v25 = *v9;
    v24 = v29;
    v27 = L"CInkTree::SetupDCompInputVisual[Exit]";
    v23 = &v25;
    v22 = &v24;
    v18 = &v27;
    v19 = (__int16 *)&dword_18014545C;
LABEL_26:
    v28 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v15,
      (_DWORD)v19,
      v16,
      v17,
      (__int64)v18,
      (__int64)&v28,
      (__int64)v22,
      (__int64)v23);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800e10b4  mov     [rsp-28h+arg_8], rbx
0x1800e10b9  push    rbp
0x1800e10ba  push    rsi
0x1800e10bb  push    rdi
0x1800e10bc  push    r12
0x1800e10be  push    r14
0x1800e10c0  mov     rbp, rsp
0x1800e10c3  sub     rsp, 70h
0x1800e10c7  movaps  [rsp+70h+var_10], xmm6
0x1800e10cc  mov     r14, rdx
0x1800e10cf  mov     rsi, rcx
0x1800e10d2  movq    xmm6, r8
0x1800e10d7  movsd   [rbp+var_20], xmm6
0x1800e10dc  lea     r12, dword_18015B128
0x1800e10e3  cmp     byte ptr [rcx+10h], 0
0x1800e10e7  jnz     short loc_1800E113E
0x1800e10e9  mov     eax, cs:dword_18015B128
0x1800e10ef  cmp     eax, 2
0x1800e10f2  jbe     loc_1800E1223
0x1800e10f8  mov     edx, 100h
0x1800e10fd  mov     rcx, r12
0x1800e1100  call    _tlgKeywordOn
0x1800e1105  test    al, al
0x1800e1107  jz      loc_1800E1223
0x1800e110d  lea     rax, aNotInitialized; "Not initialized"
0x1800e1114  mov     [rbp+var_30], rax
0x1800e1118  lea     rax, aCinktreeSetupd_0; "CInkTree::SetupDCompInputVisual"
0x1800e111f  mov     [rbp+var_28], rax
0x1800e1123  lea     rax, [rbp+var_30]
0x1800e1127  mov     [rsp+70h+var_40], rax
0x1800e112c  lea     rax, [rbp+arg_0]
0x1800e1130  mov     [rsp+70h+var_48], rax
0x1800e1135  lea     rax, [rbp+var_28]
0x1800e1139  jmp     loc_1800E120B
0x1800e113e  cmp     qword ptr [rcx+0F0h], 0
0x1800e1146  jz      short loc_1800E11C3
0x1800e1148  lea     rdi, [rcx+20h]
0x1800e114c  cmp     qword ptr [rdi], 0
0x1800e1150  jnz     short loc_1800E1159
0x1800e1152  xor     ebx, ebx
0x1800e1154  jmp     loc_1800E122C
0x1800e1159  mov     eax, cs:dword_18015B128
0x1800e115f  cmp     eax, 2
0x1800e1162  jbe     loc_1800E1227
0x1800e1168  mov     edx, 100h
0x1800e116d  mov     rcx, r12
0x1800e1170  call    _tlgKeywordOn
0x1800e1175  test    al, al
0x1800e1177  jz      loc_1800E1227
0x1800e117d  lea     rax, aInputSurfaceAl; "Input surface already created"
0x1800e1184  mov     [rbp+var_28], rax
0x1800e1188  mov     [rbp+arg_0], 8000FFFFh
0x1800e118f  lea     rax, aCinktreeSetupd_0; "CInkTree::SetupDCompInputVisual"
0x1800e1196  mov     [rbp+var_30], rax
0x1800e119a  lea     rax, [rbp+var_28]
0x1800e119e  mov     [rsp+70h+var_40], rax
0x1800e11a3  lea     rax, [rbp+arg_0]
0x1800e11a7  mov     [rsp+70h+var_48], rax
0x1800e11ac  lea     rax, [rbp+var_30]
0x1800e11b0  mov     [rsp+70h+var_50], rax
0x1800e11b5  lea     rdx, word_18013780A
0x1800e11bc  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800e11c1  jmp     short loc_1800E1227
0x1800e11c3  mov     eax, cs:dword_18015B128
0x1800e11c9  cmp     eax, 2
0x1800e11cc  jbe     short loc_1800E1223
0x1800e11ce  mov     edx, 100h
0x1800e11d3  mov     rcx, r12
0x1800e11d6  call    _tlgKeywordOn
0x1800e11db  test    al, al
0x1800e11dd  jz      short loc_1800E1223
0x1800e11df  lea     rax, aNoWetBranch; "No wet branch"
0x1800e11e6  mov     [rbp+var_28], rax
0x1800e11ea  lea     rax, aCinktreeSetupd_0; "CInkTree::SetupDCompInputVisual"
0x1800e11f1  mov     [rbp+var_30], rax
0x1800e11f5  lea     rax, [rbp+var_28]
0x1800e11f9  mov     [rsp+70h+var_40], rax
0x1800e11fe  lea     rax, [rbp+arg_0]
0x1800e1202  mov     [rsp+70h+var_48], rax
0x1800e1207  lea     rax, [rbp+var_30]
0x1800e120b  mov     [rsp+70h+var_50], rax
0x1800e1210  mov     [rbp+arg_0], 8000FFFFh
0x1800e1217  lea     rdx, word_18013780A
0x1800e121e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800e1223  lea     rdi, [rsi+20h]
0x1800e1227  mov     ebx, 8000FFFFh
0x1800e122c  mov     [rbp+arg_18], 0
0x1800e1234  test    ebx, ebx
0x1800e1236  js      loc_1800E131A
0x1800e123c  mov     rbx, [rsi+0F0h]
0x1800e1243  lea     rcx, [rbp+arg_18]
0x1800e1247  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e124c  lea     rcx, [rbx+8]
0x1800e1250  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800e1255  mov     rax, [rbx+8]
0x1800e1259  mov     [rbp+arg_18], rax
0x1800e125d  mov     rax, [r14]
0x1800e1260  mov     rbx, [rax+48h]
0x1800e1264  mov     rcx, rdi
0x1800e1267  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e126c  cvttss2si r8, dword ptr [rbp+var_20+4]
0x1800e1272  cvttss2si rdx, xmm6
0x1800e1277  mov     [rsp+70h+var_48], rdi
0x1800e127c  mov     dword ptr [rsp+70h+var_50], 0
0x1800e1284  mov     r9d, 57h ; 'W'
0x1800e128a  mov     rcx, r14
0x1800e128d  mov     rax, rbx
0x1800e1290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1295  mov     ebx, eax
0x1800e1297  test    eax, eax
0x1800e1299  js      short loc_1800E131A
0x1800e129b  mov     rcx, [rbp+arg_18]
0x1800e129f  mov     rax, [rcx]
0x1800e12a2  mov     rdx, [rdi]
0x1800e12a5  mov     rax, [rax+78h]
0x1800e12a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e12ae  mov     ebx, eax
0x1800e12b0  test    eax, eax
0x1800e12b2  js      short loc_1800E131A
0x1800e12b4  mov     eax, cs:dword_18015B128
0x1800e12ba  cmp     eax, 4
0x1800e12bd  jbe     loc_1800E1384
0x1800e12c3  mov     edx, 200h
0x1800e12c8  mov     rcx, r12
0x1800e12cb  call    _tlgKeywordOn
0x1800e12d0  test    al, al
0x1800e12d2  jz      loc_1800E1384
0x1800e12d8  mov     rax, [rdi]
0x1800e12db  mov     [rbp+var_28], rax
0x1800e12df  mov     rax, [rbp+arg_18]
0x1800e12e3  mov     [rbp+var_30], rax
0x1800e12e7  lea     rax, aCinktreeSetupd; "CInkTree::SetupDCompInputVisual[Exit]"
0x1800e12ee  mov     [rbp+var_18], rax
0x1800e12f2  lea     rax, [rbp+var_28]
0x1800e12f6  mov     [rsp+70h+var_38], rax
0x1800e12fb  lea     rax, [rbp+var_30]
0x1800e12ff  mov     [rsp+70h+var_40], rax
0x1800e1304  lea     rax, [rbp+arg_0]
0x1800e1308  mov     [rsp+70h+var_48], rax
0x1800e130d  lea     rax, [rbp+var_18]
0x1800e1311  lea     rdx, dword_18014545C
0x1800e1318  jmp     short loc_1800E1376
0x1800e131a  mov     eax, cs:dword_18015B128
0x1800e1320  cmp     eax, 2
0x1800e1323  jbe     short loc_1800E1384
0x1800e1325  mov     edx, 200h
0x1800e132a  mov     rcx, r12
0x1800e132d  call    _tlgKeywordOn
0x1800e1332  test    al, al
0x1800e1334  jz      short loc_1800E1384
0x1800e1336  mov     rax, [rdi]
0x1800e1339  mov     [rbp+var_18], rax
0x1800e133d  mov     rax, [rbp+arg_18]
0x1800e1341  mov     [rbp+var_28], rax
0x1800e1345  lea     rax, aCinktreeSetupd; "CInkTree::SetupDCompInputVisual[Exit]"
0x1800e134c  mov     [rbp+var_30], rax
0x1800e1350  lea     rax, [rbp+var_18]
0x1800e1354  mov     [rsp+70h+var_38], rax
0x1800e1359  lea     rax, [rbp+var_28]
0x1800e135d  mov     [rsp+70h+var_40], rax
0x1800e1362  lea     rax, [rbp+arg_0]
0x1800e1366  mov     [rsp+70h+var_48], rax
0x1800e136b  lea     rax, [rbp+var_30]
0x1800e136f  lea     rdx, word_1801454CE
0x1800e1376  mov     [rsp+70h+var_50], rax
0x1800e137b  mov     [rbp+arg_0], ebx
0x1800e137e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800e1383  nop
0x1800e1384  lea     rcx, [rbp+arg_18]
0x1800e1388  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e138d  mov     eax, ebx
0x1800e138f  mov     rbx, [rsp+70h+arg_8]
0x1800e1397  movaps  xmm6, [rsp+70h+var_10]
0x1800e139c  add     rsp, 70h
0x1800e13a0  pop     r14
0x1800e13a2  pop     r12
0x1800e13a4  pop     rdi
0x1800e13a5  pop     rsi
0x1800e13a6  pop     rbp
0x1800e13a7  retn
```
