# CMidi2UMP2BSMidiTransform::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18000caf0`
- end: `0x18000d1f8`
- name: `?SendMidiMessage@CMidi2UMP2BSMidiTransform@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `1800`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update`

## callees

- `0x18000163c`
- `0x180001ef0`
- `0x180002964`
- `0x180007744`
- `0x1800095b8`
- `0x18000a4f0`
- `0x18000a890`
- `0x18000a8ec`
- `0x18000aad4`
- `0x18000caf0`
- `0x18000d2f0`
- `0x18000dd78`
- `0x18000e1ec`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d059`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d059`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ad`

## pseudocode

```c
__int64 __fastcall CMidi2UMP2BSMidiTransform::SendMidiMessage(
        __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned __int64 v5; // rdi
  _DWORD *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdi
  __int64 v14; // rdx
  char v15; // r15
  __int64 v16; // r14
  unsigned __int8 v17; // dl
  char v18; // cl
  int v19; // edi
  __int64 v20; // rax
  unsigned __int8 v21; // di
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned __int8 v28; // al
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  int v34; // edx
  __int64 v35; // rcx
  unsigned __int8 v36; // r8
  unsigned __int8 v37; // al
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rcx
  unsigned int v50; // edi
  unsigned int i; // r15d
  __int64 v52; // rcx
  unsigned __int8 v53; // r8
  __int64 v54; // rdx
  int v55; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v56[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v57; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h]
  int v59; // [rsp+60h] [rbp-A0h] BYREF
  int v60; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v64[20]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = a4;
  v9 = (_DWORD *)*((_QWORD *)MidiUMP2BSTransformTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v64[18] = &v63;
    v63 = a5;
    v64[16] = &v59;
    v59 = v5;
    v64[14] = v64;
    v64[0] = a3;
    v64[12] = &v60;
    v60 = a2;
    v64[10] = L"Translating UMP to MIDI 1.0 bytes";
    v64[8] = &v61;
    v64[6] = "CMidi2UMP2BSMidiTransform::SendMidiMessage";
    v55 = 9;
    v61 = a1;
    v64[19] = 8;
    v64[17] = 4;
    v64[15] = 8;
    v64[13] = 4;
    v64[11] = 68;
    v64[9] = 8;
    v64[7] = 43;
    tlgWriteTransfer_EventWriteTransfer(v9, &word_180012076, 0, 0);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)v5 < 4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"avcore\\midi2\\transform\\umptobytestream\\midi2.ump2bsmiditransform.cpp",
        (const char *)0x80070057LL,
        v55);
      return 2147942487LL;
    }
    v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v58 = 0;
    v12 = v5;
    v57 = 0;
    v13 = a3 + 4 * (v5 >> 2);
    v61 = v13;
    std::vector<unsigned char>::reserve(&v57, v12);
    v15 = 127;
    pExceptionObject[1] = a3;
    pExceptionObject[2] = v13;
    while ( 1 )
    {
      pExceptionObject[0] = a3;
      if ( a3 >= v13 )
        break;
      v16 = (__int64)(v13 - a3) >> 2;
      if ( (unsigned int)v16 < WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject) )
      {
        v43 = 0;
        *(_QWORD *)(a1 + 105) = 0;
        *(_DWORD *)(a1 + 113) = 0;
        *(_BYTE *)(a1 + 104) = 0;
        *(_QWORD *)(a1 + 120) = 0;
        *(_DWORD *)(a1 + 128) = 0;
        *(_BYTE *)(a1 + 132) = -1;
        do
        {
          *(_BYTE *)(a1 + v43 + 133) = -1;
          *(_BYTE *)(a1 + v43 + 149) = -1;
          *(_BYTE *)(a1 + v43 + 165) = -1;
          *(_BYTE *)(a1 + v43++ + 181) = -1;
        }
        while ( v43 != 16 );
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"avcore\\midi2\\transform\\umptobytestream\\midi2.ump2bsmiditransform.cpp",
          (const char *)0x80070057LL,
          v55);
        std::vector<unsigned char>::~vector<unsigned char>(&v57, v44, v45, v46);
        if ( a1 != -16 )
          LeaveCriticalSection(v11);
        return 2147942487LL;
      }
      v17 = WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject);
      v18 = *(_BYTE *)(a3 + 3) & 0xF;
      v56[0] = v17;
      if ( v18 != v15 )
      {
        if ( *((_QWORD *)&v57 + 1) != (_QWORD)v57 )
        {
          v55 = a5;
          v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 88) + 24LL))(
                  *(_QWORD *)(a1 + 88),
                  a2 | 2u,
                  v57,
                  *((_QWORD *)&v57 + 1) - v57);
          if ( v19 < 0 )
          {
            *(_QWORD *)(a1 + 105) = 0;
            v38 = 0;
            *(_DWORD *)(a1 + 113) = 0;
            *(_BYTE *)(a1 + 104) = 0;
            *(_QWORD *)(a1 + 120) = 0;
            *(_DWORD *)(a1 + 128) = 0;
            *(_BYTE *)(a1 + 132) = -1;
            do
            {
              *(_BYTE *)(a1 + v38 + 133) = -1;
              *(_BYTE *)(a1 + v38 + 149) = -1;
              *(_BYTE *)(a1 + v38 + 165) = -1;
              *(_BYTE *)(a1 + v38++ + 181) = -1;
            }
            while ( v38 != 16 );
            v39 = 129;
            goto LABEL_51;
          }
          v17 = v56[0];
          if ( (_QWORD)v57 != *((_QWORD *)&v57 + 1) )
            *((_QWORD *)&v57 + 1) = v57;
        }
        *(_QWORD *)(a1 + 105) = 0;
        v20 = 0;
        *(_DWORD *)(a1 + 113) = 0;
        *(_BYTE *)(a1 + 104) = 0;
        *(_QWORD *)(a1 + 120) = 0;
        *(_DWORD *)(a1 + 128) = 0;
        *(_BYTE *)(a1 + 132) = -1;
        do
        {
          *(_BYTE *)(a1 + v20 + 133) = -1;
          *(_BYTE *)(a1 + v20 + 149) = -1;
          *(_BYTE *)(a1 + v20 + 165) = -1;
          *(_BYTE *)(a1 + v20++ + 181) = -1;
        }
        while ( v20 != 16 );
        v15 = *(_BYTE *)(a3 + 3) & 0xF;
      }
      v21 = 0;
      if ( v17 )
      {
        while ( 1 )
        {
          if ( (unsigned int)v16 < WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject) )
          {
LABEL_80:
            std::runtime_error::runtime_error(
              (std::runtime_error *)pExceptionObject,
              "Word index out of range for this message.");
            throw (std::runtime_error *)pExceptionObject;
          }
          v22 = *(_DWORD *)a3 >> 28;
          if ( v22 > 8 )
            break;
          if ( v22 == 8 )
            goto LABEL_38;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                v25 = v24 - 1;
                if ( !v25 )
                  goto LABEL_38;
                v26 = v25 - 1;
                if ( !v26 )
                  goto LABEL_38;
                v27 = v26 - 1;
                if ( !v27 )
                  goto LABEL_36;
                if ( v27 - 1 > 1 )
                  goto LABEL_80;
              }
            }
          }
          v28 = 1;
LABEL_39:
          if ( v21 >= v28 )
            goto LABEL_80;
          umpToBytestream::UMPStreamParse((umpToBytestream *)(a1 + 96), *(_DWORD *)(a3 + 4LL * v21++));
          if ( v21 >= v56[0] )
            goto LABEL_41;
        }
        v29 = v22 - 9;
        if ( !v29 || (v30 = v29 - 1) == 0 )
        {
LABEL_38:
          v28 = 2;
          goto LABEL_39;
        }
        v31 = v30 - 1;
        if ( !v31 || (v32 = v31 - 1) == 0 )
        {
          v28 = 3;
          goto LABEL_39;
        }
        v33 = v32 - 1;
        if ( v33 && v33 - 1 > 1 )
          goto LABEL_80;
LABEL_36:
        v28 = 4;
        goto LABEL_39;
      }
LABEL_41:
      while ( 1 )
      {
        v34 = *(_DWORD *)(a1 + 128);
        if ( !v34 )
          break;
        v35 = *(int *)(a1 + 120);
        v36 = *(_BYTE *)(v35 + a1 + 105);
        *(_DWORD *)(a1 + 128) = v34 - 1;
        *(_DWORD *)(a1 + 120) = v35 + 1;
        if ( (_DWORD)v35 == 11 )
          *(_DWORD *)(a1 + 120) = 0;
        v56[0] = v36;
        if ( *((_QWORD *)&v57 + 1) == v58 )
        {
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(&v57, *((_QWORD *)&v57 + 1), v56);
        }
        else
        {
          **((_BYTE **)&v57 + 1) = v36;
          ++*((_QWORD *)&v57 + 1);
        }
      }
      v37 = WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject);
      v13 = v61;
      a3 += 4LL * v37;
    }
    v47 = v57;
    v48 = *((_QWORD *)&v57 + 1) - v57;
    if ( *((_QWORD *)&v57 + 1) != (_QWORD)v57 )
    {
      v55 = a5;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 88) + 24LL))(
              *(_QWORD *)(a1 + 88),
              a2 | 2u,
              v57,
              v48);
      if ( v19 < 0 )
      {
        v49 = 0;
        *(_QWORD *)(a1 + 105) = 0;
        *(_DWORD *)(a1 + 113) = 0;
        *(_BYTE *)(a1 + 104) = 0;
        *(_QWORD *)(a1 + 120) = 0;
        *(_DWORD *)(a1 + 128) = 0;
        *(_BYTE *)(a1 + 132) = -1;
        do
        {
          *(_BYTE *)(v49 + a1 + 133) = -1;
          *(_BYTE *)(v49 + a1 + 149) = -1;
          *(_BYTE *)(v49 + a1 + 165) = -1;
          *(_BYTE *)(v49 + a1 + 181) = -1;
          ++v49;
        }
        while ( v49 != 16 );
        v39 = 182;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"avcore\\midi2\\transform\\umptobytestream\\midi2.ump2bsmiditransform.cpp",
          (const char *)(unsigned int)v19,
          v55);
        std::vector<unsigned char>::~vector<unsigned char>(&v57, v40, v41, v42);
        if ( v11 )
          LeaveCriticalSection(v11);
        return (unsigned int)v19;
      }
    }
  }
  else
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v58 = 0;
    v57 = 0;
    std::vector<unsigned char>::reserve(&v57, v5);
    v50 = (unsigned int)v5 >> 2;
    for ( i = 0; i < v50; ++i )
    {
      umpToBytestream::UMPStreamParse((umpToBytestream *)(a1 + 96), *(_DWORD *)(a3 + 4LL * i));
      while ( 1 )
      {
        v14 = *(unsigned int *)(a1 + 128);
        if ( !(_DWORD)v14 )
          break;
        v52 = *(int *)(a1 + 120);
        v53 = *(_BYTE *)(v52 + a1 + 105);
        *(_DWORD *)(a1 + 128) = v14 - 1;
        *(_DWORD *)(a1 + 120) = v52 + 1;
        if ( (_DWORD)v52 == 11 )
          *(_DWORD *)(a1 + 120) = 0;
        v56[0] = v53;
        if ( *((_QWORD *)&v57 + 1) == v58 )
        {
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(&v57, *((_QWORD *)&v57 + 1), v56);
        }
        else
        {
          **((_BYTE **)&v57 + 1) = v53;
          ++*((_QWORD *)&v57 + 1);
        }
      }
    }
    v47 = v57;
    v48 = *((_QWORD *)&v57 + 1) - v57;
    if ( *((_QWORD *)&v57 + 1) != (_QWORD)v57 )
    {
      v55 = a5;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 88) + 24LL))(
              *(_QWORD *)(a1 + 88),
              a2 | 2u,
              v57,
              v48);
      if ( v19 < 0 )
      {
        v54 = 0;
        *(_QWORD *)(a1 + 105) = 0;
        *(_DWORD *)(a1 + 113) = 0;
        *(_BYTE *)(a1 + 104) = 0;
        *(_QWORD *)(a1 + 120) = 0;
        *(_DWORD *)(a1 + 128) = 0;
        *(_BYTE *)(a1 + 132) = -1;
        do
        {
          *(_BYTE *)(v54 + a1 + 133) = -1;
          *(_BYTE *)(v54 + a1 + 149) = -1;
          *(_BYTE *)(v54 + a1 + 165) = -1;
          *(_BYTE *)(v54 + a1 + 181) = -1;
          ++v54;
        }
        while ( v54 != 16 );
        v39 = 224;
        goto LABEL_51;
      }
    }
  }
  std::vector<unsigned char>::~vector<unsigned char>(&v57, v14, v47, v48);
  if ( v11 )
    LeaveCriticalSection(v11);
  return 0;
}

```

## disassembly

```asm
0x18000caf0  push    rbp
0x18000caf2  push    rbx
0x18000caf3  push    rsi
0x18000caf4  push    rdi
0x18000caf5  push    r12
0x18000caf7  push    r13
0x18000caf9  push    r14
0x18000cafb  push    r15
0x18000cafd  lea     rbp, [rsp-48h]
0x18000cb02  sub     rsp, 148h
0x18000cb09  mov     rax, cs:__security_cookie
0x18000cb10  xor     rax, rsp
0x18000cb13  mov     [rbp+80h+var_50], rax
0x18000cb17  mov     edi, r9d
0x18000cb1a  mov     r12, r8
0x18000cb1d  mov     r13d, edx
0x18000cb20  mov     rbx, rcx
0x18000cb23  call    ?Instance@MidiUMP2BSTransformTelemetryProvider@@KAPEAV1@XZ; MidiUMP2BSTransformTelemetryProvider::Instance(void)
0x18000cb28  xor     r14d, r14d
0x18000cb2b  mov     rcx, [rax+8]
0x18000cb2f  lea     esi, [r14+4]
0x18000cb33  mov     eax, [rcx]
0x18000cb35  cmp     eax, esi
0x18000cb37  jbe     loc_18000CBF1
0x18000cb3d  mov     r14, qword ptr [rbp+80h+arg_20]
0x18000cb44  lea     rax, [rbp+80h+var_F8]
0x18000cb48  mov     [rbp+80h+var_60], rax
0x18000cb4c  lea     rdx, word_180012076
0x18000cb53  lea     rax, [rsp+180h+var_120]
0x18000cb58  mov     [rbp+80h+var_F8], r14
0x18000cb5c  mov     [rbp+80h+var_70], rax
0x18000cb60  xor     r14d, r14d
0x18000cb63  lea     rax, [rbp+80h+var_F0]
0x18000cb67  mov     [rsp+180h+var_120], edi
0x18000cb6b  mov     [rbp+80h+var_80], rax
0x18000cb6f  xor     r9d, r9d
0x18000cb72  lea     rax, [rsp+180h+var_11C]
0x18000cb77  mov     [rbp+80h+var_F0], r12
0x18000cb7b  mov     [rbp+80h+var_90], rax
0x18000cb7f  xor     r8d, r8d
0x18000cb82  lea     rax, aTranslatingUmp; "Translating UMP to MIDI 1.0 bytes"
0x18000cb89  mov     [rsp+180h+var_11C], r13d
0x18000cb8e  mov     [rbp+80h+var_A0], rax
0x18000cb92  lea     rax, [rsp+180h+var_118]
0x18000cb97  mov     [rbp+80h+var_B0], rax
0x18000cb9b  lea     rax, aCmidi2ump2bsmi_0; "CMidi2UMP2BSMidiTransform::SendMidiMess"...
0x18000cba2  mov     [rbp+80h+var_C0], rax
0x18000cba6  lea     rax, [rbp+80h+var_E0]
0x18000cbaa  mov     [rsp+180h+var_158], rax
0x18000cbaf  mov     [rsp+180h+var_160], 9; int
0x18000cbb7  mov     [rsp+180h+var_118], rbx
0x18000cbbc  mov     [rbp+80h+var_58], 8
0x18000cbc4  mov     [rbp+80h+var_68], rsi
0x18000cbc8  mov     [rbp+80h+var_78], 8
0x18000cbd0  mov     [rbp+80h+var_88], rsi
0x18000cbd4  mov     [rbp+80h+var_98], 44h ; 'D'
0x18000cbdc  mov     [rbp+80h+var_A8], 8
0x18000cbe4  mov     [rbp+80h+var_B8], 2Bh ; '+'
0x18000cbec  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cbf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::GetImpl(void)'::`2'::impl
0x18000cbf8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::__private_IsEnabled(void)
0x18000cbfd  test    al, al
0x18000cbff  jz      loc_18000D052
0x18000cc05  cmp     edi, esi
0x18000cc07  jnb     short loc_18000CC30
0x18000cc09  mov     rcx, [rbp+88h]; this
0x18000cc10  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umptobytestre"...
0x18000cc17  mov     ebx, 80070057h
0x18000cc1c  mov     edx, 5Ch ; '\'; void *
0x18000cc21  mov     r9d, ebx; char *
0x18000cc24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc29  mov     eax, ebx
0x18000cc2b  jmp     loc_18000D1B5
0x18000cc30  lea     rsi, [rbx+10h]
0x18000cc34  mov     rcx, rsi; lpCriticalSection
0x18000cc37  call    cs:__imp_EnterCriticalSection
0x18000cc3d  mov     rax, rdi
0x18000cc40  mov     [rsp+180h+var_128], r14
0x18000cc45  shr     rax, 2
0x18000cc49  lea     rcx, [rsp+180h+var_138]
0x18000cc4e  mov     rdx, rdi
0x18000cc51  xorps   xmm0, xmm0
0x18000cc54  movdqu  [rsp+180h+var_138], xmm0
0x18000cc5a  lea     rdi, [r12+rax*4]
0x18000cc5e  mov     [rsp+180h+var_118], rdi
0x18000cc63  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x18000cc68  mov     r15b, 7Fh
0x18000cc6b  mov     [rsp+180h+var_108], r12
0x18000cc70  mov     [rbp+80h+var_100], rdi
0x18000cc74  mov     [rsp+180h+pExceptionObject], r12
0x18000cc79  cmp     r12, rdi
0x18000cc7c  jnb     loc_18000CFAF
0x18000cc82  mov     r14, rdi
0x18000cc85  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000cc8a  sub     r14, r12
0x18000cc8d  sar     r14, 2
0x18000cc91  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000cc96  movzx   eax, al
0x18000cc99  cmp     r14d, eax
0x18000cc9c  jb      loc_18000CF25
0x18000cca2  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000cca7  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000ccac  mov     cl, [r12+3]
0x18000ccb1  mov     dl, al
0x18000ccb3  and     cl, 0Fh
0x18000ccb6  mov     [rsp+180h+var_140], al
0x18000ccba  cmp     cl, r15b
0x18000ccbd  jz      loc_18000CD78
0x18000ccc3  mov     r8, qword ptr [rsp+180h+var_138]
0x18000ccc8  mov     r9, qword ptr [rsp+180h+var_138+8]
0x18000cccd  sub     r9, r8
0x18000ccd0  jz      short loc_18000CD20
0x18000ccd2  mov     rcx, [rbx+58h]
0x18000ccd6  mov     edx, r13d
0x18000ccd9  mov     rax, qword ptr [rbp+80h+arg_20]
0x18000cce0  or      edx, 2
0x18000cce3  movzx   r11d, r15b
0x18000cce7  mov     [rsp+180h+var_158], r11
0x18000ccec  mov     r10, [rcx]
0x18000ccef  mov     qword ptr [rsp+180h+var_160], rax; int
0x18000ccf4  mov     rax, [r10+18h]
0x18000ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccfd  xor     ecx, ecx
0x18000ccff  mov     edi, eax
0x18000cd01  test    eax, eax
0x18000cd03  js      loc_18000CEA6
0x18000cd09  mov     rax, qword ptr [rsp+180h+var_138]
0x18000cd0e  mov     dl, [rsp+180h+var_140]
0x18000cd12  cmp     rax, qword ptr [rsp+180h+var_138+8]
0x18000cd17  jz      short loc_18000CD22
0x18000cd19  mov     qword ptr [rsp+180h+var_138+8], rax
0x18000cd1e  jmp     short loc_18000CD22
0x18000cd20  xor     ecx, ecx
0x18000cd22  mov     [rbx+69h], rcx
0x18000cd26  mov     rax, rcx
0x18000cd29  mov     [rbx+71h], ecx
0x18000cd2c  mov     [rbx+68h], cl
0x18000cd2f  mov     qword ptr [rbx+78h], 0
0x18000cd37  mov     [rbx+80h], ecx
0x18000cd3d  mov     byte ptr [rbx+84h], 0FFh
0x18000cd44  mov     byte ptr [rbx+rax+85h], 0FFh
0x18000cd4c  mov     byte ptr [rbx+rax+95h], 0FFh
0x18000cd54  mov     byte ptr [rbx+rax+0A5h], 0FFh
0x18000cd5c  mov     byte ptr [rbx+rax+0B5h], 0FFh
0x18000cd64  inc     rax
0x18000cd67  cmp     rax, 10h
0x18000cd6b  jnz     short loc_18000CD44
0x18000cd6d  mov     r15b, [r12+3]
0x18000cd72  and     r15b, 0Fh
0x18000cd76  jmp     short loc_18000CD7A
0x18000cd78  xor     ecx, ecx
0x18000cd7a  mov     dil, cl
0x18000cd7d  test    dl, dl
0x18000cd7f  jz      loc_18000CE31
0x18000cd85  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000cd8a  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000cd8f  movzx   eax, al
0x18000cd92  cmp     r14d, eax
0x18000cd95  jb      loc_18000D1D5
0x18000cd9b  mov     ecx, [r12]
0x18000cd9f  shr     ecx, 1Ch
0x18000cda2  cmp     ecx, 8
0x18000cda5  ja      short loc_18000CDD8
0x18000cda7  jz      short loc_18000CE07
0x18000cda9  test    ecx, ecx
0x18000cdab  jz      short loc_18000CDD4
0x18000cdad  sub     ecx, 1
0x18000cdb0  jz      short loc_18000CDD4
0x18000cdb2  sub     ecx, 1
0x18000cdb5  jz      short loc_18000CDD4
0x18000cdb7  sub     ecx, 1
0x18000cdba  jz      short loc_18000CE07
0x18000cdbc  sub     ecx, 1
0x18000cdbf  jz      short loc_18000CE07
0x18000cdc1  sub     ecx, 1
0x18000cdc4  jz      short loc_18000CDFF
0x18000cdc6  sub     ecx, 1
0x18000cdc9  jz      short loc_18000CDD4
0x18000cdcb  cmp     ecx, 1
0x18000cdce  jnz     loc_18000D1D5
0x18000cdd4  mov     al, 1
0x18000cdd6  jmp     short loc_18000CE09
0x18000cdd8  sub     ecx, 9
0x18000cddb  jz      short loc_18000CE07
0x18000cddd  sub     ecx, 1
0x18000cde0  jz      short loc_18000CE07
0x18000cde2  sub     ecx, 1
0x18000cde5  jz      short loc_18000CE03
0x18000cde7  sub     ecx, 1
0x18000cdea  jz      short loc_18000CE03
0x18000cdec  sub     ecx, 1
0x18000cdef  jz      short loc_18000CDFF
0x18000cdf1  sub     ecx, 1
0x18000cdf4  jz      short loc_18000CDFF
0x18000cdf6  cmp     ecx, 1
0x18000cdf9  jnz     loc_18000D1D5
0x18000cdff  mov     al, 4
0x18000ce01  jmp     short loc_18000CE09
0x18000ce03  mov     al, 3
0x18000ce05  jmp     short loc_18000CE09
0x18000ce07  mov     al, 2
0x18000ce09  cmp     dil, al
0x18000ce0c  jnb     loc_18000D1D5
0x18000ce12  movzx   edx, dil
0x18000ce16  lea     rcx, [rbx+60h]; this
0x18000ce1a  mov     edx, [r12+rdx*4]; unsigned int
0x18000ce1e  call    ?UMPStreamParse@umpToBytestream@@QEAAXI@Z; umpToBytestream::UMPStreamParse(uint)
0x18000ce23  inc     dil
0x18000ce26  cmp     dil, [rsp+180h+var_140]
0x18000ce2b  jb      loc_18000CD85
0x18000ce31  xor     r14d, r14d
0x18000ce34  mov     edx, [rbx+80h]
0x18000ce3a  test    edx, edx
0x18000ce3c  jz      short loc_18000CE8B
0x18000ce3e  movsxd  rcx, dword ptr [rbx+78h]
0x18000ce42  lea     eax, [rdx-1]
0x18000ce45  mov     r8b, [rcx+rbx+69h]
0x18000ce4a  mov     [rbx+80h], eax
0x18000ce50  lea     eax, [rcx+1]
0x18000ce53  mov     [rbx+78h], eax
0x18000ce56  cmp     eax, 0Ch
0x18000ce59  jnz     short loc_18000CE5F
0x18000ce5b  mov     [rbx+78h], r14d
0x18000ce5f  mov     rdx, qword ptr [rsp+180h+var_138+8]
0x18000ce64  mov     [rsp+180h+var_140], r8b
0x18000ce69  cmp     rdx, [rsp+180h+var_128]
0x18000ce6e  jz      short loc_18000CE7A
0x18000ce70  mov     [rdx], r8b
0x18000ce73  inc     qword ptr [rsp+180h+var_138+8]
0x18000ce78  jmp     short loc_18000CE34
0x18000ce7a  lea     r8, [rsp+180h+var_140]
0x18000ce7f  lea     rcx, [rsp+180h+var_138]
0x18000ce84  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x18000ce89  jmp     short loc_18000CE34
0x18000ce8b  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000ce90  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000ce95  mov     rdi, [rsp+180h+var_118]
0x18000ce9a  movzx   eax, al
0x18000ce9d  lea     r12, [r12+rax*4]
0x18000cea1  jmp     loc_18000CC74
0x18000cea6  mov     [rbx+69h], rcx
0x18000ceaa  mov     rax, rcx
0x18000cead  mov     [rbx+71h], ecx
0x18000ceb0  mov     [rbx+68h], cl
0x18000ceb3  mov     [rbx+78h], rcx
0x18000ceb7  mov     [rbx+80h], ecx
0x18000cebd  mov     byte ptr [rbx+84h], 0FFh
0x18000cec4  mov     byte ptr [rbx+rax+85h], 0FFh
0x18000cecc  mov     byte ptr [rbx+rax+95h], 0FFh
0x18000ced4  mov     byte ptr [rbx+rax+0A5h], 0FFh
0x18000cedc  mov     byte ptr [rbx+rax+0B5h], 0FFh
0x18000cee4  inc     rax
0x18000cee7  cmp     rax, 10h
0x18000ceeb  jnz     short loc_18000CEC4
0x18000ceed  lea     edx, [rax+71h]; void *
0x18000cef0  mov     rcx, [rbp+88h]; this
0x18000cef7  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umptobytestre"...
0x18000cefe  mov     r9d, edi; char *
0x18000cf01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf06  lea     rcx, [rsp+180h+var_138]
0x18000cf0b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000cf10  test    rsi, rsi
0x18000cf13  jz      short loc_18000CF1E
0x18000cf15  mov     rcx, rsi; lpCriticalSection
0x18000cf18  call    cs:__imp_LeaveCriticalSection
0x18000cf1e  mov     eax, edi
0x18000cf20  jmp     loc_18000D1B5
0x18000cf25  xor     edi, edi
0x18000cf27  mov     eax, edi
0x18000cf29  mov     [rbx+69h], rax
0x18000cf2d  mov     [rbx+71h], eax
0x18000cf30  mov     [rbx+68h], dil
0x18000cf34  mov     [rbx+78h], rdi
0x18000cf38  mov     [rbx+80h], edi
0x18000cf3e  mov     byte ptr [rbx+84h], 0FFh
0x18000cf45  mov     byte ptr [rbx+rax+85h], 0FFh
0x18000cf4d  mov     byte ptr [rbx+rax+95h], 0FFh
0x18000cf55  mov     byte ptr [rbx+rax+0A5h], 0FFh
0x18000cf5d  mov     byte ptr [rbx+rax+0B5h], 0FFh
0x18000cf65  inc     rax
0x18000cf68  cmp     rax, 10h
0x18000cf6c  jnz     short loc_18000CF45
0x18000cf6e  mov     rcx, [rbp+88h]; this
0x18000cf75  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umptobytestre"...
0x18000cf7c  mov     ebx, 80070057h
0x18000cf81  mov     edx, 0A0h; void *
0x18000cf86  mov     r9d, ebx; char *
0x18000cf89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf8e  lea     rcx, [rsp+180h+var_138]
0x18000cf93  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000cf98  test    rsi, rsi
0x18000cf9b  jz      loc_18000CC29
0x18000cfa1  mov     rcx, rsi; lpCriticalSection
0x18000cfa4  call    cs:__imp_LeaveCriticalSection
0x18000cfaa  jmp     loc_18000CC29
0x18000cfaf  mov     r8, qword ptr [rsp+180h+var_138]
0x18000cfb4  mov     r9, qword ptr [rsp+180h+var_138+8]
0x18000cfb9  sub     r9, r8
0x18000cfbc  jz      loc_18000D19B
0x18000cfc2  movzx   edx, byte ptr [rbx+0C5h]
  ... truncated ...
```
