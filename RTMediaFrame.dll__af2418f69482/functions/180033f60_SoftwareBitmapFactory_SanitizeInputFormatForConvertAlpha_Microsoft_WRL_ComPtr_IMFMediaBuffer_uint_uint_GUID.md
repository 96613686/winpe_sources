# SoftwareBitmapFactory::_SanitizeInputFormatForConvertAlpha(Microsoft::WRL::ComPtr<IMFMediaBuffer> &,uint,uint,_GUID &)

- ea: `0x180033f60`
- end: `0x180034291`
- name: `?_SanitizeInputFormatForConvertAlpha@SoftwareBitmapFactory@@AEAAXAEAV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@IIAEAU_GUID@@@Z`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180002940`

## callees

- `0x180001008`
- `0x1800019c0`
- `0x180003fcc`
- `0x180005cd0`
- `0x180006e40`
- `0x18001b790`
- `0x180021b44`
- `0x180023968`
- `0x180026920`
- `0x18002749c`
- `0x1800319a4`
- `0x1800319f8`
- `0x180032178`
- `0x180033f60`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreate2DMediaBuffer` at `0x1800340c6`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1800340c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SoftwareBitmapFactory::_SanitizeInputFormatForConvertAlpha(
        __int64 a1,
        _QWORD *a2,
        struct IErrorInfo *a3,
        unsigned int a4,
        __int64 a5)
{
  DWORD v6; // r15d
  __int64 MFVideoFormat; // rax
  int v9; // r12d
  int v10; // r13d
  __int64 v11; // xmm6_8
  unsigned int v12; // eax
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  int v17; // edx
  __int64 v18; // r8
  int v19; // edx
  __int64 i; // r9
  __int64 v21; // rdi
  __int64 v22; // r10
  DWORD v23; // r11d
  char v24; // dl
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // rcx
  int v29; // [rsp+48h] [rbp-91h] BYREF
  int v30; // [rsp+4Ch] [rbp-8Dh] BYREF
  unsigned int v31; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-85h] BYREF
  DWORD v33; // [rsp+58h] [rbp-81h]
  IMFMediaBuffer *ppBuffer; // [rsp+60h] [rbp-79h] BYREF
  __int64 v35; // [rsp+68h] [rbp-71h] BYREF
  __int64 v36; // [rsp+70h] [rbp-69h] BYREF
  __int64 v37; // [rsp+78h] [rbp-61h] BYREF
  __int64 v38; // [rsp+80h] [rbp-59h] BYREF
  __int64 v39; // [rsp+88h] [rbp-51h] BYREF
  __int64 v40; // [rsp+90h] [rbp-49h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+98h] [rbp-41h] BYREF
  __int64 *v42; // [rsp+A0h] [rbp-39h]
  _BYTE v43[8]; // [rsp+B8h] [rbp-21h] BYREF
  __int64 *v44; // [rsp+C0h] [rbp-19h]

  v6 = (unsigned int)a3;
  if ( !*a2 )
  {
    _com_error::_com_error((_com_error *)pExceptionObject, -2147467261, a3, a4);
    throw (_com_error *)pExceptionObject;
  }
  if ( (unsigned int)dword_1800710A0 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      byte_18006586B);
  if ( *(_QWORD *)a5 == *(_QWORD *)&MFVideoFormat_L8.Data1 && *(_QWORD *)(a5 + 8) == *(_QWORD *)MFVideoFormat_L8.Data4 )
  {
    MFVideoFormat = MediaFrameHelpers::GetMFVideoFormat(pExceptionObject, 87, 2);
    v9 = 1;
  }
  else
  {
    if ( *(_QWORD *)a5 != *(_QWORD *)&MFVideoFormat_L16.Data1
      || *(_QWORD *)(a5 + 8) != *(_QWORD *)MFVideoFormat_L16.Data4 )
    {
      MF::ThrowOriginateError<15>(a1, L"Invalid format");
    }
    MFVideoFormat = MediaFrameHelpers::GetMFVideoFormat(pExceptionObject, 87, 2);
    v9 = 2;
  }
  v10 = *(_DWORD *)(MFVideoFormat + 12);
  v11 = *(_QWORD *)(MFVideoFormat + 4);
  v33 = *(_DWORD *)MFVideoFormat;
  MF::As<IMF2DBuffer2,IMFMediaBuffer>(&v36, a2);
  v31 = 0;
  v37 = 0;
  v29 = 0;
  v39 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *, __int64 *, unsigned int *))(*(_QWORD *)v36 + 80LL))(
          v36,
          1,
          &v39,
          &v29,
          &v37,
          &v31);
  MF::ThrowIfFailed((MF *)v12, v13);
  pExceptionObject[0] = 0;
  v42 = &v36;
  if ( v31 < a4 * v29 )
    MF::ThrowOriginateError<36>();
  ppBuffer = 0;
  v14 = MFCreate2DMediaBuffer(v6, a4, v33, 0, &ppBuffer);
  MF::ThrowIfFailed((MF *)v14, v15);
  MF::As<IMF2DBuffer2,IMFMediaBuffer>(&v35, &ppBuffer);
  v38 = 0;
  v32 = 0;
  v30 = 0;
  v40 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *, __int64 *, unsigned int *))(*(_QWORD *)v35 + 80LL))(
          v35,
          2,
          &v40,
          &v30,
          &v38,
          &v32);
  MF::ThrowIfFailed((MF *)v16, v17);
  v43[0] = 0;
  v44 = &v35;
  v19 = v30;
  if ( v32 < a4 * v30 )
    MF::ThrowOriginateError<41>();
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    v21 = v37 + (unsigned int)(v29 * i);
    v22 = v38 + (unsigned int)(v19 * i);
    v23 = 0;
    if ( v6 )
    {
      do
      {
        v18 = 4 * v23;
        v24 = *(_BYTE *)(v9 * (v23 + 1) - 1 + v21);
        *(_BYTE *)((unsigned int)(v18 + 2) + v22) = v24;
        *(_BYTE *)((unsigned int)(v18 + 1) + v22) = v24;
        *(_BYTE *)(v18 + v22) = v24;
        *(_BYTE *)((unsigned int)(v18 + 3) + v22) = -1;
        ++v23;
      }
      while ( v23 < v6 );
      v19 = v30;
    }
  }
  v25 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD, __int64, __int64))ppBuffer->lpVtbl->SetCurrentLength)(
          ppBuffer,
          a4 * v19,
          v18,
          i);
  MF::ThrowIfFailed((MF *)v25, v26);
  Microsoft::WRL::ComPtr<IMFMediaBuffer>::operator=(a2, &ppBuffer);
  *(_DWORD *)a5 = v33;
  *(_QWORD *)(a5 + 4) = v11;
  *(_DWORD *)(a5 + 12) = v10;
  if ( (unsigned int)dword_1800710A0 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v27,
      byte_180065829);
  ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___::_ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___(v43);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
  ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___::_ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___(pExceptionObject);
  return Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v36);
}

```

## disassembly

```asm
0x180033f60  mov     rax, rsp
0x180033f63  push    rbp
0x180033f64  push    rbx
0x180033f65  push    rsi
0x180033f66  push    rdi
0x180033f67  push    r12
0x180033f69  push    r13
0x180033f6b  push    r14
0x180033f6d  push    r15
0x180033f6f  lea     rbp, [rax-57h]
0x180033f73  sub     rsp, 0E8h
0x180033f7a  movaps  xmmword ptr [rax-58h], xmm6
0x180033f7e  mov     rax, cs:__security_cookie
0x180033f85  xor     rax, rsp
0x180033f88  mov     [rbp+4Fh+var_60], rax
0x180033f8c  mov     esi, r9d
0x180033f8f  mov     r15d, r8d
0x180033f92  mov     r14, rdx
0x180033f95  cmp     qword ptr [rdx], 0
0x180033f99  jz      loc_18003426C
0x180033f9f  mov     eax, cs:dword_1800710A0
0x180033fa5  cmp     eax, 5
0x180033fa8  jbe     short loc_180033FB6
0x180033faa  lea     rdx, byte_18006586B
0x180033fb1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180033fb6  mov     rbx, [rbp+4Fh+arg_20]
0x180033fba  mov     rax, [rbx]
0x180033fbd  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data1
0x180033fc4  jnz     short loc_180033FED
0x180033fc6  mov     rax, [rbx+8]
0x180033fca  cmp     rax, qword ptr cs:MFVideoFormat_L8.Data4
0x180033fd1  jnz     short loc_180033FED
0x180033fd3  mov     edi, 2
0x180033fd8  mov     r8d, edi
0x180033fdb  lea     edx, [rdi+55h]
0x180033fde  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180033fe2  call    ?GetMFVideoFormat@MediaFrameHelpers@@SA?AU_GUID@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@W4BitmapAlphaMode@456@@Z; MediaFrameHelpers::GetMFVideoFormat(Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode)
0x180033fe7  lea     r12d, [rdi-1]
0x180033feb  jmp     short loc_180034025
0x180033fed  mov     rax, [rbx]
0x180033ff0  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data1
0x180033ff7  jnz     loc_18003425F
0x180033ffd  mov     rax, [rbx+8]
0x180034001  cmp     rax, qword ptr cs:MFVideoFormat_L16.Data4
0x180034008  jnz     loc_18003425F
0x18003400e  mov     edi, 2
0x180034013  mov     r8d, edi
0x180034016  lea     edx, [rdi+55h]
0x180034019  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003401d  call    ?GetMFVideoFormat@MediaFrameHelpers@@SA?AU_GUID@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@W4BitmapAlphaMode@456@@Z; MediaFrameHelpers::GetMFVideoFormat(Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode)
0x180034022  mov     r12d, edi
0x180034025  mov     r13d, [rax+0Ch]
0x180034029  movsd   xmm6, qword ptr [rax+4]
0x18003402e  mov     eax, [rax]
0x180034030  mov     [rsp+120h+var_D0], eax
0x180034034  mov     rdx, r14
0x180034037  lea     rcx, [rbp+4Fh+var_B8]
0x18003403b  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x180034040  nop
0x180034041  xor     eax, eax
0x180034043  mov     [rsp+120h+var_D8], eax
0x180034047  mov     [rbp+4Fh+var_B0], rax
0x18003404b  mov     [rsp+120h+var_E0], eax
0x18003404f  mov     [rbp+4Fh+var_A0], rax
0x180034053  mov     rcx, [rbp+4Fh+var_B8]
0x180034057  mov     rax, [rcx]
0x18003405a  lea     rdx, [rsp+120h+var_D8]
0x18003405f  mov     [rsp+28h], rdx
0x180034064  lea     rdx, [rbp+4Fh+var_B0]
0x180034068  mov     [rsp+120h+ppBuffer], rdx
0x18003406d  lea     r9, [rsp+120h+var_E0]
0x180034072  lea     r8, [rbp+4Fh+var_A0]
0x180034076  mov     edx, 1
0x18003407b  mov     rax, [rax+50h]
0x18003407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034084  mov     ecx, eax; this
0x180034086  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18003408b  mov     [rbp+4Fh+pExceptionObject], 0
0x18003408f  lea     rax, [rbp+4Fh+var_B8]
0x180034093  mov     [rbp+4Fh+var_88], rax
0x180034097  mov     eax, [rsp+120h+var_E0]
0x18003409b  imul    eax, esi
0x18003409e  cmp     [rsp+120h+var_D8], eax
0x1800340a2  jb      loc_18003428B
0x1800340a8  mov     [rbp+4Fh+var_C8], 0
0x1800340b0  lea     rax, [rbp+4Fh+var_C8]
0x1800340b4  mov     [rsp+120h+ppBuffer], rax; ppBuffer
0x1800340b9  xor     r9d, r9d; fBottomUp
0x1800340bc  mov     r8d, [rsp+120h+var_D0]; dwFourCC
0x1800340c1  mov     edx, esi; dwHeight
0x1800340c3  mov     ecx, r15d; dwWidth
0x1800340c6  call    cs:__imp_MFCreate2DMediaBuffer
0x1800340cc  mov     ecx, eax; this
0x1800340ce  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800340d3  lea     rdx, [rbp+4Fh+var_C8]
0x1800340d7  lea     rcx, [rbp+4Fh+var_C0]
0x1800340db  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x1800340e0  nop
0x1800340e1  xor     eax, eax
0x1800340e3  mov     [rbp+4Fh+var_A8], rax
0x1800340e7  mov     [rsp+120h+var_D4], eax
0x1800340eb  mov     [rsp+120h+var_DC], eax
0x1800340ef  mov     [rbp+4Fh+var_98], rax
0x1800340f3  mov     rcx, [rbp+4Fh+var_C0]
0x1800340f7  mov     rax, [rcx]
0x1800340fa  lea     rdx, [rsp+120h+var_D4]
0x1800340ff  mov     [rsp+28h], rdx
0x180034104  lea     rdx, [rbp+4Fh+var_A8]
0x180034108  mov     [rsp+120h+ppBuffer], rdx
0x18003410d  lea     r9, [rsp+120h+var_DC]
0x180034112  lea     r8, [rbp+4Fh+var_98]
0x180034116  mov     edx, edi
0x180034118  mov     rax, [rax+50h]
0x18003411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034121  mov     ecx, eax; this
0x180034123  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180034128  mov     [rbp+4Fh+var_70], 0
0x18003412c  lea     rax, [rbp+4Fh+var_C0]
0x180034130  mov     [rbp+4Fh+var_68], rax
0x180034134  mov     edx, [rsp+120h+var_DC]
0x180034138  mov     eax, edx
0x18003413a  imul    eax, esi
0x18003413d  cmp     [rsp+120h+var_D4], eax
0x180034141  jb      loc_180034259
0x180034147  xor     r9d, r9d
0x18003414a  test    esi, esi
0x18003414c  jz      short loc_1800341B3
0x18003414e  mov     edi, r9d
0x180034151  imul    edi, [rsp+120h+var_E0]
0x180034156  add     rdi, [rbp+4Fh+var_B0]
0x18003415a  mov     r10d, r9d
0x18003415d  imul    r10d, edx
0x180034161  add     r10, [rbp+4Fh+var_A8]
0x180034165  xor     r11d, r11d
0x180034168  test    r15d, r15d
0x18003416b  jz      short loc_1800341AB
0x18003416d  lea     r8d, ds:0[r11*4]
0x180034175  lea     eax, [r11+1]
0x180034179  imul    eax, r12d
0x18003417d  dec     eax
0x18003417f  mov     dl, [rax+rdi]
0x180034182  lea     eax, [r8+2]
0x180034186  mov     [rax+r10], dl
0x18003418a  lea     eax, [r8+1]
0x18003418e  mov     [rax+r10], dl
0x180034192  mov     [r8+r10], dl
0x180034196  lea     eax, [r8+3]
0x18003419a  mov     byte ptr [rax+r10], 0FFh
0x18003419f  inc     r11d
0x1800341a2  cmp     r11d, r15d
0x1800341a5  jb      short loc_18003416D
0x1800341a7  mov     edx, [rsp+120h+var_DC]
0x1800341ab  inc     r9d
0x1800341ae  cmp     r9d, esi
0x1800341b1  jb      short loc_18003414E
0x1800341b3  mov     rcx, [rbp+4Fh+var_C8]
0x1800341b7  mov     rax, [rcx]
0x1800341ba  imul    edx, esi
0x1800341bd  mov     rax, [rax+30h]
0x1800341c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341c6  mov     ecx, eax; this
0x1800341c8  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800341cd  lea     rdx, [rbp+4Fh+var_C8]
0x1800341d1  mov     rcx, r14
0x1800341d4  call    ??4?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMFMediaBuffer>::operator=(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x1800341d9  mov     eax, [rsp+120h+var_D0]
0x1800341dd  mov     [rbx], eax
0x1800341df  movsd   qword ptr [rbx+4], xmm6
0x1800341e4  mov     [rbx+0Ch], r13d
0x1800341e8  mov     eax, cs:dword_1800710A0
0x1800341ee  cmp     eax, 5
0x1800341f1  jbe     short loc_180034200
0x1800341f3  lea     rdx, byte_180065829
0x1800341fa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800341ff  nop
0x180034200  lea     rcx, [rbp+4Fh+var_70]
0x180034204  call    ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd______ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___
0x180034209  nop
0x18003420a  lea     rcx, [rbp+4Fh+var_C0]
0x18003420e  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180034213  nop
0x180034214  lea     rcx, [rbp+4Fh+var_C8]
0x180034218  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18003421d  nop
0x18003421e  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180034222  call    ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd______ScopeGuardImpl0__lambda_a0dd83f300b5142fae4bba733946d2bd___
0x180034227  nop
0x180034228  lea     rcx, [rbp+4Fh+var_B8]
0x18003422c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180034231  mov     rcx, [rbp+4Fh+var_60]
0x180034235  xor     rcx, rsp; StackCookie
0x180034238  call    __security_check_cookie
0x18003423d  movaps  xmm6, [rsp+120h+var_58+8]
0x180034245  add     rsp, 0E8h
0x18003424c  pop     r15
0x18003424e  pop     r14
0x180034250  pop     r13
0x180034252  pop     r12
0x180034254  pop     rdi
0x180034255  pop     rsi
0x180034256  pop     rbx
0x180034257  pop     rbp
0x180034258  retn
0x180034259  call    ??$ThrowOriginateError@$0CJ@@MF@@YAXJAEAY0CJ@$$CBG@Z; MF::ThrowOriginateError<41>(long,ushort const (&)[41])
0x18003425f  lea     rdx, aInvalidFormat; "Invalid format"
0x180034266  call    ??$ThrowOriginateError@$0P@@MF@@YAXJAEAY0P@$$CBG@Z; MF::ThrowOriginateError<15>(long,ushort const (&)[15])
0x18003426c  mov     edx, 80004003h; int
0x180034271  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180034275  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18003427a  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180034281  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180034285  call    _CxxThrowException_0
0x18003428b  call    ??$ThrowOriginateError@$0CE@@MF@@YAXJAEAY0CE@$$CBG@Z; MF::ThrowOriginateError<36>(long,ushort const (&)[36])
```
