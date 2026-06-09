# SpatialAudioDevicePropertyWriter::RuntimeClassInitialize(ushort const *,IPropertyStore *)

- ea: `0x1801388c4`
- end: `0x180138c3f`
- name: `?RuntimeClassInitialize@SpatialAudioDevicePropertyWriter@@QEAAJPEBGPEAUIPropertyStore@@@Z`
- size: `891`
- prototype: `int(SpatialAudioDevicePropertyWriter *__hidden this, const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801380c0`

## callees

- `0x18001d788`
- `0x180037824`
- `0x180042aa0`
- `0x18004f6d0`
- `0x1800621e0`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1801388c4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180138a59`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180138a59`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180138986`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180138986`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801389fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138bb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801389fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138af0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138af0`

## string_xrefs

- `0x1801389ab`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`
- `0x180138a20`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`
- `0x180138bd8`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpatialAudioDevicePropertyWriter::RuntimeClassInitialize(
        SpatialAudioDevicePropertyWriter *this,
        const unsigned __int16 *a2,
        struct IPropertyStore *a3)
{
  char v6; // al
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // rcx
  HRESULT Instance; // ebx
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  LPVOID *p_pv; // rax
  void *v17; // rdx
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, _QWORD, __int64, __int64 *); // rbx
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, _QWORD, char *); // rdi
  int v25; // [rsp+40h] [rbp-59h] BYREF
  int v26; // [rsp+44h] [rbp-55h] BYREF
  __int64 v27; // [rsp+48h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-41h] BYREF
  const char *v30; // [rsp+60h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF

  *((_BYTE *)this + 101) = 0;
  v6 = byte_1801D3338;
  *((_BYTE *)this + 100) = byte_1801D3338;
  byte_1801D3338 = v6 - 4;
  *((_DWORD *)this + 24) = 0;
  v7 = (unsigned __int16 *)((char *)this + 112);
  v8 = (unsigned __int16 *)((char *)this + 112);
  if ( a2 )
    StringCchCopyW(v8, 0x104u, a2);
  else
    memset_0(v8, 0, 0x208u);
  if ( !a3 )
  {
    ppv = 0;
    v27 = 0;
    memset_0(sz, 0, 0x4Eu);
    v10 = StringFromGUID2(&DEVINTERFACE_AUDIO_RENDER, sz, 39);
    Instance = v10;
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_1801D12E8 > 2 )
      {
        v25 = v10;
        v26 = 141;
        pv = "SpatialAudioDevicePropertyWriter::RuntimeClassInitialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          dword_1801D12E8,
          (unsigned int)&unk_1801A8524,
          v11,
          v12,
          (__int64)&pv,
          (__int64)&v26,
          (__int64)&v25);
      }
      goto LABEL_29;
    }
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&ppv);
    Instance = CoCreateInstance(&CLSID_MMDeviceEnumerator, 0, 0x17u, &GUID_a95664d2_9614_4f35_a746_de8db63617e6, &ppv);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_1801D12E8 > 2 )
      {
        v25 = 144;
        pv = "SpatialAudioDevicePropertyWriter::RuntimeClassInitialize";
        p_pv = &pv;
        v17 = &unk_1801A84F2;
LABEL_28:
        v26 = Instance;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)p_pv,
          (__int64)&v25,
          (__int64)&v26);
      }
LABEL_29:
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&ppv);
      return (unsigned int)Instance;
    }
    if ( !a2 || !(unsigned int)_o__wcsicmp(a2, sz) )
    {
      v18 = ppv;
      v19 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)ppv + 32LL);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
      Instance = v19(v18, 0, 1, &v27);
      if ( Instance < 0 )
      {
        if ( (unsigned int)dword_1801D12E8 <= 2 )
          goto LABEL_29;
        v25 = 149;
        v17 = &unk_1801A84C0;
LABEL_27:
        v30 = "SpatialAudioDevicePropertyWriter::RuntimeClassInitialize";
        p_pv = (LPVOID *)&v30;
        goto LABEL_28;
      }
      pv = 0;
      (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v27 + 40LL))(v27, &pv);
      StringCbPrintfW(v7, 0x104u, L"%s", pv);
      CoTaskMemFree(pv);
    }
    v20 = ppv;
    v21 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 40LL);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    Instance = v21(v20, v7, &v27);
    if ( Instance >= 0 )
    {
      v22 = v27;
      v23 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v27 + 32LL);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 88);
      Instance = v23(v22, 0, (char *)this + 88);
      if ( Instance >= 0 )
      {
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 104);
        Instance = CoCreateInstance(
                     &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
                     0,
                     1u,
                     &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
                     (LPVOID *)this + 13);
        if ( Instance >= 0 || (unsigned int)dword_1801D12E8 <= 2 )
          goto LABEL_29;
        v25 = 165;
        v17 = &unk_1801A83B5;
      }
      else
      {
        if ( (unsigned int)dword_1801D12E8 <= 2 )
          goto LABEL_29;
        v25 = 162;
        v17 = &unk_1801A848E;
      }
    }
    else
    {
      if ( (unsigned int)dword_1801D12E8 <= 2 )
        goto LABEL_29;
      v25 = 159;
      v17 = &unk_1801A845C;
    }
    goto LABEL_27;
  }
  Instance = 0;
  Microsoft::WRL::ComPtr<ISaDeviceProxy>::operator=((char *)this + 88, a3);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 104);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801388c4  mov     [rsp-8+arg_18], rbx
0x1801388c9  push    rbp
0x1801388ca  push    rsi
0x1801388cb  push    rdi
0x1801388cc  push    r14
0x1801388ce  push    r15
0x1801388d0  lea     rbp, [rsp-37h]
0x1801388d5  sub     rsp, 0D0h
0x1801388dc  mov     rax, cs:__security_cookie
0x1801388e3  xor     rax, rsp
0x1801388e6  mov     [rbp+57h+var_30], rax
0x1801388ea  mov     rsi, r8
0x1801388ed  mov     rdi, rdx
0x1801388f0  mov     r14, rcx
0x1801388f3  mov     byte ptr [rcx+65h], 0
0x1801388f7  mov     al, cs:byte_1801D3338
0x1801388fd  mov     [rcx+64h], al
0x180138900  add     al, 0FCh
0x180138902  mov     cs:byte_1801D3338, al
0x180138908  mov     dword ptr [rcx+60h], 0
0x18013890f  lea     r15, [rcx+70h]
0x180138913  mov     rcx, r15; unsigned __int16 *
0x180138916  test    rdx, rdx
0x180138919  jz      short loc_18013892A
0x18013891b  mov     r8, rdx; unsigned __int16 *
0x18013891e  mov     edx, 104h; unsigned __int64
0x180138923  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180138928  jmp     short loc_180138935
0x18013892a  mov     r8d, 208h; Size
0x180138930  call    memset_0
0x180138935  test    rsi, rsi
0x180138938  jz      short loc_180138956
0x18013893a  xor     ebx, ebx
0x18013893c  lea     rcx, [r14+58h]
0x180138940  mov     rdx, rsi
0x180138943  call    ??4?$ComPtr@UISaDeviceProxy@@@WRL@Microsoft@@QEAAAEAV012@PEAUISaDeviceProxy@@@Z; Microsoft::WRL::ComPtr<ISaDeviceProxy>::operator=(ISaDeviceProxy *)
0x180138948  lea     rcx, [r14+68h]
0x18013894c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138951  jmp     loc_180138C1A
0x180138956  mov     [rbp+57h+var_A0], 0
0x18013895e  mov     [rbp+57h+var_A8], 0
0x180138966  xor     edx, edx; Val
0x180138968  lea     r8d, [rdx+4Eh]; Size
0x18013896c  lea     rcx, [rbp+57h+sz]; void *
0x180138970  call    memset_0
0x180138975  mov     r8d, 27h ; '''; cchMax
0x18013897b  lea     rdx, [rbp+57h+sz]; lpsz
0x18013897f  lea     rcx, DEVINTERFACE_AUDIO_RENDER; rguid
0x180138986  call    cs:__imp_StringFromGUID2
0x18013898c  mov     ebx, eax
0x18013898e  test    eax, eax
0x180138990  jns     short loc_1801389D8
0x180138992  mov     ecx, cs:dword_1801D12E8
0x180138998  cmp     ecx, 2
0x18013899b  jbe     loc_180138C07
0x1801389a1  mov     [rbp+57h+var_B0], eax
0x1801389a4  mov     [rbp+57h+var_AC], 8Dh
0x1801389ab  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x1801389b2  mov     [rbp+57h+pv], rax
0x1801389b6  lea     rax, [rbp+57h+var_B0]
0x1801389ba  mov     [rsp+0F0h+var_C0], rax
0x1801389bf  lea     rax, [rbp+57h+var_AC]
0x1801389c3  mov     [rsp+0F0h+var_C8], rax
0x1801389c8  lea     rax, [rbp+57h+pv]
0x1801389cc  lea     rdx, unk_1801A8524
0x1801389d3  jmp     loc_180138BFC
0x1801389d8  lea     rcx, [rbp+57h+var_A0]
0x1801389dc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1801389e1  lea     rax, [rbp+57h+var_A0]
0x1801389e5  mov     [rsp+0F0h+ppv], rax; ppv
0x1801389ea  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1801389f1  xor     edx, edx; pUnkOuter
0x1801389f3  lea     r8d, [rdx+17h]; dwClsContext
0x1801389f7  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x1801389fe  call    cs:__imp_CoCreateInstance
0x180138a04  mov     ebx, eax
0x180138a06  test    eax, eax
0x180138a08  jns     short loc_180138A4D
0x180138a0a  mov     eax, cs:dword_1801D12E8
0x180138a10  cmp     eax, 2
0x180138a13  jbe     loc_180138C07
0x180138a19  mov     [rbp+57h+var_B0], 90h
0x180138a20  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x180138a27  mov     [rbp+57h+pv], rax
0x180138a2b  lea     rax, [rbp+57h+var_AC]
0x180138a2f  mov     [rsp+0F0h+var_C0], rax
0x180138a34  lea     rax, [rbp+57h+var_B0]
0x180138a38  mov     [rsp+0F0h+var_C8], rax
0x180138a3d  lea     rax, [rbp+57h+pv]
0x180138a41  lea     rdx, unk_1801A84F2
0x180138a48  jmp     loc_180138BF9
0x180138a4d  test    rdi, rdi
0x180138a50  jz      short loc_180138A67
0x180138a52  lea     rdx, [rbp+57h+sz]
0x180138a56  mov     rcx, rdi
0x180138a59  call    cs:__imp__o__wcsicmp
0x180138a5f  test    eax, eax
0x180138a61  jnz     loc_180138AF6
0x180138a67  mov     rdi, [rbp+57h+var_A0]
0x180138a6b  mov     rax, [rdi]
0x180138a6e  mov     rbx, [rax+20h]
0x180138a72  lea     rcx, [rbp+57h+var_A8]
0x180138a76  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138a7b  lea     r9, [rbp+57h+var_A8]
0x180138a7f  xor     edx, edx
0x180138a81  lea     r8d, [rdx+1]
0x180138a85  mov     rcx, rdi
0x180138a88  mov     rax, rbx
0x180138a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138a90  mov     ebx, eax
0x180138a92  test    eax, eax
0x180138a94  jns     short loc_180138AB8
0x180138a96  mov     eax, cs:dword_1801D12E8
0x180138a9c  cmp     eax, 2
0x180138a9f  jbe     loc_180138C07
0x180138aa5  mov     [rbp+57h+var_B0], 95h
0x180138aac  lea     rdx, unk_1801A84C0
0x180138ab3  jmp     loc_180138BD8
0x180138ab8  mov     [rbp+57h+pv], 0
0x180138ac0  mov     rcx, [rbp+57h+var_A8]
0x180138ac4  mov     rax, [rcx]
0x180138ac7  lea     rdx, [rbp+57h+pv]
0x180138acb  mov     rax, [rax+28h]
0x180138acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138ad4  mov     r9, [rbp+57h+pv]
0x180138ad8  lea     r8, aS_0; "%s"
0x180138adf  mov     edx, 104h; unsigned __int64
0x180138ae4  mov     rcx, r15; unsigned __int16 *
0x180138ae7  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180138aec  mov     rcx, [rbp+57h+pv]; pv
0x180138af0  call    cs:__imp_CoTaskMemFree
0x180138af6  mov     rdi, [rbp+57h+var_A0]
0x180138afa  mov     rax, [rdi]
0x180138afd  mov     rbx, [rax+28h]
0x180138b01  lea     rcx, [rbp+57h+var_A8]
0x180138b05  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138b0a  lea     r8, [rbp+57h+var_A8]
0x180138b0e  mov     rdx, r15
0x180138b11  mov     rcx, rdi
0x180138b14  mov     rax, rbx
0x180138b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138b1c  mov     ebx, eax
0x180138b1e  test    eax, eax
0x180138b20  jns     short loc_180138B44
0x180138b22  mov     eax, cs:dword_1801D12E8
0x180138b28  cmp     eax, 2
0x180138b2b  jbe     loc_180138C07
0x180138b31  mov     [rbp+57h+var_B0], 9Fh
0x180138b38  lea     rdx, unk_1801A845C
0x180138b3f  jmp     loc_180138BD8
0x180138b44  mov     rsi, [rbp+57h+var_A8]
0x180138b48  mov     rax, [rsi]
0x180138b4b  mov     rdi, [rax+20h]
0x180138b4f  lea     rcx, [r14+58h]
0x180138b53  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138b58  lea     r8, [r14+58h]
0x180138b5c  xor     edx, edx
0x180138b5e  mov     rcx, rsi
0x180138b61  mov     rax, rdi
0x180138b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138b69  mov     ebx, eax
0x180138b6b  test    eax, eax
0x180138b6d  jns     short loc_180138B8E
0x180138b6f  mov     eax, cs:dword_1801D12E8
0x180138b75  cmp     eax, 2
0x180138b78  jbe     loc_180138C07
0x180138b7e  mov     [rbp+57h+var_B0], 0A2h
0x180138b85  lea     rdx, unk_1801A848E
0x180138b8c  jmp     short loc_180138BD8
0x180138b8e  lea     rbx, [r14+68h]
0x180138b92  mov     rcx, rbx
0x180138b95  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138b9a  mov     [rsp+0F0h+ppv], rbx; ppv
0x180138b9f  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180138ba6  xor     edx, edx; pUnkOuter
0x180138ba8  lea     r8d, [rdx+1]; dwClsContext
0x180138bac  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180138bb3  call    cs:__imp_CoCreateInstance
0x180138bb9  mov     ebx, eax
0x180138bbb  test    eax, eax
0x180138bbd  jns     short loc_180138C07
0x180138bbf  mov     eax, cs:dword_1801D12E8
0x180138bc5  cmp     eax, 2
0x180138bc8  jbe     short loc_180138C07
0x180138bca  mov     [rbp+57h+var_B0], 0A5h
0x180138bd1  lea     rdx, unk_1801A83B5
0x180138bd8  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x180138bdf  mov     [rbp+57h+var_90], rax
0x180138be3  lea     rax, [rbp+57h+var_AC]
0x180138be7  mov     [rsp+0F0h+var_C0], rax
0x180138bec  lea     rax, [rbp+57h+var_B0]
0x180138bf0  mov     [rsp+0F0h+var_C8], rax
0x180138bf5  lea     rax, [rbp+57h+var_90]
0x180138bf9  mov     [rbp+57h+var_AC], ebx
0x180138bfc  mov     [rsp+0F0h+ppv], rax
0x180138c01  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180138c06  nop
0x180138c07  lea     rcx, [rbp+57h+var_A8]
0x180138c0b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138c10  nop
0x180138c11  lea     rcx, [rbp+57h+var_A0]
0x180138c15  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138c1a  mov     eax, ebx
0x180138c1c  mov     rcx, [rbp+57h+var_30]
0x180138c20  xor     rcx, rsp; StackCookie
0x180138c23  call    __security_check_cookie
0x180138c28  mov     rbx, [rsp+0F0h+arg_18]
0x180138c30  add     rsp, 0D0h
0x180138c37  pop     r15
0x180138c39  pop     r14
0x180138c3b  pop     rdi
0x180138c3c  pop     rsi
0x180138c3d  pop     rbp
0x180138c3e  retn
```
