# CApplicationFrameTelemetry::MoveSizeLoop::Stop(ushort const *,HWND__ *,tagSIZE,TITLE_BAR_HIDE_OPTIONS)

- ea: `0x1800524b4`
- end: `0x18005283c`
- name: `?Stop@MoveSizeLoop@CApplicationFrameTelemetry@@QEAAXPEBGPEAUHWND__@@UtagSIZE@@W4TITLE_BAR_HIDE_OPTIONS@@@Z`
- size: `904`
- prototype: `void __high(const unsigned __int16 *, HWND, struct tagSIZE, enum TITLE_BAR_HIDE_OPTIONS)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180013430`

## callees

- `0x180002748`
- `0x180002ae0`
- `0x180030190`
- `0x1800304f0`
- `0x18003505c`
- `0x180039fec`
- `0x180043c30`
- `0x1800524b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005277c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005277c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800524f8`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800524f8`

## pseudocode

```c
__int64 __fastcall CApplicationFrameTelemetry::MoveSizeLoop::Stop(
        __int64 a1,
        __int64 a2,
        HWND a3,
        unsigned __int64 a4,
        int a5)
{
  unsigned __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rsi
  int v10; // eax
  int *v11; // rsi
  _DWORD *v12; // r9
  int v13; // r9d
  __int64 v14; // r8
  _DWORD *v15; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  int v18; // r9d
  LONG right; // [rsp+E0h] [rbp-80h] BYREF
  LONG top; // [rsp+E4h] [rbp-7Ch] BYREF
  struct tagRECT v22; // [rsp+E8h] [rbp-78h] BYREF
  int v23; // [rsp+F8h] [rbp-68h] BYREF
  int v24; // [rsp+FCh] [rbp-64h] BYREF
  int v25; // [rsp+100h] [rbp-60h] BYREF
  int v26; // [rsp+104h] [rbp-5Ch] BYREF
  int v27; // [rsp+108h] [rbp-58h] BYREF
  int v28; // [rsp+10Ch] [rbp-54h] BYREF
  LONG bottom; // [rsp+110h] [rbp-50h] BYREF
  __int64 v30; // [rsp+118h] [rbp-48h] BYREF
  __int64 v31; // [rsp+120h] [rbp-40h] BYREF
  __int64 v32; // [rsp+128h] [rbp-38h] BYREF
  __int64 v33; // [rsp+130h] [rbp-30h] BYREF
  __int64 v34; // [rsp+138h] [rbp-28h] BYREF
  __int64 v35; // [rsp+140h] [rbp-20h] BYREF
  __int64 v36; // [rsp+148h] [rbp-18h] BYREF
  __int64 v37; // [rsp+150h] [rbp-10h] BYREF
  __int64 v38; // [rsp+158h] [rbp-8h] BYREF
  __int64 v39; // [rsp+160h] [rbp+0h] BYREF
  __int64 v40; // [rsp+168h] [rbp+8h] BYREF
  struct tagRECT Rect; // [rsp+170h] [rbp+10h] BYREF

  v7 = HIDWORD(a4);
  v8 = a4;
  Rect = 0;
  GetWindowRect(a3, &Rect);
  v9 = *(_QWORD *)(a1 + 272);
  v10 = *(_DWORD *)(v9 + 72);
  if ( v10 < 0 && (v11 = (int *)(v9 + 80), v10 == v11[2]) && v11 )
  {
    wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
    v12 = (_DWORD *)*((_QWORD *)CApplicationFrameLogging::Instance() + 1);
    if ( *v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v26 = a5;
      bottom = Rect.bottom;
      right = Rect.right;
      top = Rect.top;
      v22.left = Rect.left;
      v33 = *((_QWORD *)v11 + 15);
      v14 = *(_QWORD *)(a1 + 272);
      v34 = *((_QWORD *)v11 + 14);
      v22.top = v11[26];
      v35 = *((_QWORD *)v11 + 12);
      v36 = *((_QWORD *)v11 + 11);
      v22.right = v11[20];
      v37 = *((_QWORD *)v11 + 9);
      v22.bottom = v11[8];
      v38 = *((_QWORD *)v11 + 3);
      v23 = *v11;
      v39 = *((_QWORD *)v11 + 16);
      v24 = v11[16];
      v40 = *((_QWORD *)v11 + 7);
      v25 = v11[2];
      v27 = v7;
      v28 = v8;
      v32 = a2;
      v30 = 0x1000000;
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&unk_18007F630,
        v14 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v40,
        (__int64)&v24,
        (__int64)&v39,
        (__int64)&v23,
        (__int64)&v38,
        (__int64)&v22.bottom,
        (__int64)&v37,
        (__int64)&v22.right,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v22.top,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&top,
        (__int64)&right,
        (__int64)&bottom,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  else
  {
    wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
    v15 = (_DWORD *)*((_QWORD *)CApplicationFrameLogging::Instance() + 1);
    if ( *v15 > 5u && (unsigned __int8)tlgKeywordOn(v15, 0x400000000000LL) )
    {
      v25 = a5;
      v22 = Rect;
      v24 = v7;
      v23 = v8;
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *(_QWORD *)(a1 + 272);
      top = CurrentThreadId;
      right = *(_DWORD *)(v17 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)byte_18007F7D5,
        v17 + 8,
        v18,
        (__int64)&v30,
        (__int64)&right,
        (__int64)&top,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v22.top,
        (__int64)&v22.right,
        (__int64)&v22.bottom,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25);
    }
  }
  return wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800524b4  mov     [rsp-8+arg_8], rbx
0x1800524b9  push    rbp
0x1800524ba  push    rsi
0x1800524bb  push    rdi
0x1800524bc  push    r14
0x1800524be  push    r15
0x1800524c0  lea     rbp, [rsp-30h]
0x1800524c5  sub     rsp, 190h
0x1800524cc  mov     rax, cs:__security_cookie
0x1800524d3  xor     rax, rsp
0x1800524d6  mov     [rbp+50h+var_30], rax
0x1800524da  mov     r15, rdx
0x1800524dd  mov     rdi, rcx
0x1800524e0  mov     r14, r9
0x1800524e3  lea     rdx, [rbp+50h+Rect]; lpRect
0x1800524e7  xorps   xmm0, xmm0
0x1800524ea  shr     r14, 20h
0x1800524ee  mov     rcx, r8; hWnd
0x1800524f1  mov     rbx, r9
0x1800524f4  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x1800524f8  call    cs:__imp_GetWindowRect
0x1800524fe  mov     rsi, [rdi+110h]
0x180052505  mov     eax, [rsi+48h]
0x180052508  test    eax, eax
0x18005250a  jns     loc_18005271A
0x180052510  add     rsi, 50h ; 'P'
0x180052514  cmp     eax, [rsi+8]
0x180052517  jnz     loc_18005271A
0x18005251d  test    rsi, rsi
0x180052520  jz      loc_18005271A
0x180052526  mov     rcx, rdi
0x180052529  call    ?zInternalStop@?$ActivityBase@VCApplicationFrameLogging@@$0A@$00$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18005252e  call    ?Instance@CApplicationFrameLogging@@KAPEAV1@XZ; CApplicationFrameLogging::Instance(void)
0x180052533  mov     r9, [rax+8]
0x180052537  mov     eax, [r9]
0x18005253a  cmp     eax, 5
0x18005253d  jbe     loc_180052811
0x180052543  mov     rdx, 400000000000h
0x18005254d  mov     rcx, r9
0x180052550  call    _tlgKeywordOn
0x180052555  test    al, al
0x180052557  jz      loc_180052811
0x18005255d  mov     eax, [rbp+50h+arg_20]
0x180052563  mov     [rbp+50h+var_AC], eax
0x180052566  mov     eax, [rbp+50h+Rect.bottom]
0x180052569  mov     [rbp+50h+var_A0], eax
0x18005256c  mov     eax, [rbp+50h+Rect.right]
0x18005256f  mov     [rbp+50h+var_D0], eax
0x180052572  mov     eax, [rbp+50h+Rect.top]
0x180052575  mov     [rbp+50h+var_CC], eax
0x180052578  mov     eax, [rbp+50h+Rect.left]
0x18005257b  mov     dword ptr [rbp+50h+var_C8], eax
0x18005257e  mov     rax, [rsi+78h]
0x180052582  mov     [rbp+50h+var_80], rax
0x180052586  mov     rax, [rsi+70h]
0x18005258a  mov     r8, [rdi+110h]
0x180052591  mov     [rbp+50h+var_78], rax
0x180052595  add     r8, 8
0x180052599  mov     eax, [rsi+68h]
0x18005259c  mov     dword ptr [rbp+50h+var_C8+4], eax
0x18005259f  mov     rax, [rsi+60h]
0x1800525a3  mov     [rbp+50h+var_70], rax
0x1800525a7  mov     rax, [rsi+58h]
0x1800525ab  mov     [rbp+50h+var_68], rax
0x1800525af  mov     eax, [rsi+50h]
0x1800525b2  mov     [rbp+50h+var_C0], eax
0x1800525b5  mov     rax, [rsi+48h]
0x1800525b9  mov     [rbp+50h+var_60], rax
0x1800525bd  mov     eax, [rsi+20h]
0x1800525c0  mov     [rbp+50h+var_BC], eax
0x1800525c3  mov     rax, [rsi+18h]
0x1800525c7  mov     [rbp+50h+var_58], rax
0x1800525cb  mov     eax, [rsi]
0x1800525cd  mov     [rbp+50h+var_B8], eax
0x1800525d0  mov     rax, [rsi+80h]
0x1800525d7  mov     [rbp+50h+var_50], rax
0x1800525db  mov     eax, [rsi+40h]
0x1800525de  mov     [rbp+50h+var_B4], eax
0x1800525e1  mov     rax, [rsi+38h]
0x1800525e5  mov     [rbp+50h+var_48], rax
0x1800525e9  mov     eax, [rsi+8]
0x1800525ec  mov     [rbp+50h+var_B0], eax
0x1800525ef  lea     rax, [rbp+50h+var_AC]
0x1800525f3  mov     [rsp+1B0h+var_D8], rax
0x1800525fb  lea     rax, [rbp+50h+var_A8]
0x1800525ff  mov     [rsp+1B0h+var_E0], rax
0x180052607  lea     rax, [rbp+50h+var_A4]
0x18005260b  mov     [rsp+1B0h+var_E8], rax
0x180052613  lea     rax, [rbp+50h+var_A0]
0x180052617  mov     [rsp+1B0h+var_F0], rax
0x18005261f  lea     rax, [rbp+50h+var_D0]
0x180052623  mov     [rsp+1B0h+var_F8], rax
0x18005262b  lea     rax, [rbp+50h+var_CC]
0x18005262f  mov     [rsp+1B0h+var_100], rax
0x180052637  lea     rax, [rbp+50h+var_C8]
0x18005263b  mov     [rsp+1B0h+var_108], rax
0x180052643  lea     rax, [rbp+50h+var_88]
0x180052647  mov     [rsp+1B0h+var_110], rax
0x18005264f  lea     rax, [rbp+50h+var_80]
0x180052653  mov     [rsp+1B0h+var_118], rax
0x18005265b  lea     rax, [rbp+50h+var_78]
0x18005265f  mov     [rsp+1B0h+var_120], rax
0x180052667  lea     rax, [rbp+50h+var_C8+4]
0x18005266b  mov     [rsp+1B0h+var_128], rax
0x180052673  lea     rax, [rbp+50h+var_70]
0x180052677  mov     [rsp+1B0h+var_130], rax
0x18005267f  lea     rax, [rbp+50h+var_68]
0x180052683  mov     [rsp+1B0h+var_138], rax
0x180052688  lea     rax, [rbp+50h+var_C0]
0x18005268c  mov     [rsp+1B0h+var_140], rax
0x180052691  lea     rax, [rbp+50h+var_60]
0x180052695  mov     [rsp+1B0h+var_148], rax
0x18005269a  lea     rax, [rbp+50h+var_BC]
0x18005269e  mov     [rsp+1B0h+var_150], rax
0x1800526a3  lea     rax, [rbp+50h+var_58]
0x1800526a7  mov     [rsp+1B0h+var_158], rax
0x1800526ac  lea     rax, [rbp+50h+var_B8]
0x1800526b0  mov     [rsp+1B0h+var_160], rax
0x1800526b5  mov     [rbp+50h+var_A8], r14d
0x1800526b9  mov     [rbp+50h+var_A4], ebx
0x1800526bc  mov     [rbp+50h+var_88], r15
0x1800526c0  mov     [rbp+50h+var_98], 1000000h
0x1800526c8  mov     [rbp+50h+var_90], 0
0x1800526d0  lea     rax, [rbp+50h+var_50]
0x1800526d4  mov     rcx, r9
0x1800526d7  mov     [rsp+1B0h+var_168], rax
0x1800526dc  lea     rdx, unk_18007F630
0x1800526e3  lea     rax, [rbp+50h+var_B4]
0x1800526e7  mov     [rsp+1B0h+var_170], rax
0x1800526ec  lea     rax, [rbp+50h+var_48]
0x1800526f0  mov     [rsp+1B0h+var_178], rax
0x1800526f5  lea     rax, [rbp+50h+var_B0]
0x1800526f9  mov     [rsp+1B0h+var_180], rax
0x1800526fe  lea     rax, [rbp+50h+var_98]
0x180052702  mov     [rsp+1B0h+var_188], rax
0x180052707  lea     rax, [rbp+50h+var_90]
0x18005270b  mov     [rsp+1B0h+var_190], rax
0x180052710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052715  jmp     loc_180052811
0x18005271a  mov     rcx, rdi
0x18005271d  call    ?zInternalStop@?$ActivityBase@VCApplicationFrameLogging@@$0A@$00$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180052722  call    ?Instance@CApplicationFrameLogging@@KAPEAV1@XZ; CApplicationFrameLogging::Instance(void)
0x180052727  mov     rsi, [rax+8]
0x18005272b  mov     eax, [rsi]
0x18005272d  cmp     eax, 5
0x180052730  jbe     loc_180052811
0x180052736  mov     rdx, 400000000000h
0x180052740  mov     rcx, rsi
0x180052743  call    _tlgKeywordOn
0x180052748  test    al, al
0x18005274a  jz      loc_180052811
0x180052750  mov     eax, [rbp+50h+arg_20]
0x180052756  mov     [rbp+50h+var_B0], eax
0x180052759  mov     eax, [rbp+50h+Rect.bottom]
0x18005275c  mov     [rbp+50h+var_BC], eax
0x18005275f  mov     eax, [rbp+50h+Rect.right]
0x180052762  mov     [rbp+50h+var_C0], eax
0x180052765  mov     eax, [rbp+50h+Rect.top]
0x180052768  mov     dword ptr [rbp+50h+var_C8+4], eax
0x18005276b  mov     eax, [rbp+50h+Rect.left]
0x18005276e  mov     dword ptr [rbp+50h+var_C8], eax
0x180052771  mov     [rbp+50h+var_B4], r14d
0x180052775  mov     [rbp+50h+var_B8], ebx
0x180052778  mov     [rbp+50h+var_90], r15
0x18005277c  call    cs:__imp_GetCurrentThreadId
0x180052782  mov     r8, [rdi+110h]
0x180052789  lea     rdx, byte_18007F7D5
0x180052790  mov     [rbp+50h+var_CC], eax
0x180052793  mov     rcx, rsi
0x180052796  mov     eax, [r8+48h]
0x18005279a  add     r8, 8
0x18005279e  mov     [rbp+50h+var_D0], eax
0x1800527a1  lea     rax, [rbp+50h+var_B0]
0x1800527a5  mov     [rsp+1B0h+var_140], rax
0x1800527aa  lea     rax, [rbp+50h+var_B4]
0x1800527ae  mov     [rsp+1B0h+var_148], rax
0x1800527b3  lea     rax, [rbp+50h+var_B8]
0x1800527b7  mov     [rsp+1B0h+var_150], rax
0x1800527bc  lea     rax, [rbp+50h+var_BC]
0x1800527c0  mov     [rsp+1B0h+var_158], rax
0x1800527c5  lea     rax, [rbp+50h+var_C0]
0x1800527c9  mov     [rsp+1B0h+var_160], rax
0x1800527ce  lea     rax, [rbp+50h+var_C8+4]
0x1800527d2  mov     [rsp+1B0h+var_168], rax
0x1800527d7  lea     rax, [rbp+50h+var_C8]
0x1800527db  mov     [rsp+1B0h+var_170], rax
0x1800527e0  lea     rax, [rbp+50h+var_90]
0x1800527e4  mov     [rsp+1B0h+var_178], rax
0x1800527e9  lea     rax, [rbp+50h+var_CC]
0x1800527ed  mov     [rsp+1B0h+var_180], rax
0x1800527f2  lea     rax, [rbp+50h+var_D0]
0x1800527f6  mov     [rsp+1B0h+var_188], rax
0x1800527fb  lea     rax, [rbp+50h+var_98]
0x1800527ff  mov     [rsp+1B0h+var_190], rax
0x180052804  mov     [rbp+50h+var_98], 0
0x18005280c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052811  mov     rcx, rdi
0x180052814  call    ?IgnoreCurrentThread@?$ActivityBase@VCApplicationFrameLogging@@$0A@$00$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180052819  mov     rcx, [rbp+50h+var_30]
0x18005281d  xor     rcx, rsp; StackCookie
0x180052820  call    __security_check_cookie
0x180052825  mov     rbx, [rsp+1B0h+arg_8]
0x18005282d  add     rsp, 190h
0x180052834  pop     r15
0x180052836  pop     r14
0x180052838  pop     rdi
0x180052839  pop     rsi
0x18005283a  pop     rbp
0x18005283b  retn
```
