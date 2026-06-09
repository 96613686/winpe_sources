# SpatialAudioDevicePropertyWriter::RuntimeClassInitialize(ushort const *,IPropertyStore *)

- ea: `0x180138b54`
- end: `0x180138ecf`
- name: `?RuntimeClassInitialize@SpatialAudioDevicePropertyWriter@@QEAAJPEBGPEAUIPropertyStore@@@Z`
- size: `891`
- prototype: `int(SpatialAudioDevicePropertyWriter *__hidden this, const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180138350`

## callees

- `0x18001d8d8`
- `0x180037984`
- `0x180042610`
- `0x18004f240`
- `0x180061d50`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x180138b54`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180138ce9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180138ce9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180138c16`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180138c16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138c8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138e43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138c8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180138e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138d80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138d80`

## string_xrefs

- `0x180138c3b`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`
- `0x180138cb0`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`
- `0x180138e68`: `SpatialAudioDevicePropertyWriter::RuntimeClassInitialize`

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
  char *v17; // rdx
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
  v6 = byte_1801D4378;
  *((_BYTE *)this + 100) = byte_1801D4378;
  byte_1801D4378 = v6 - 4;
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
      if ( (unsigned int)dword_1801D22E8 > 2 )
      {
        v25 = v10;
        v26 = 141;
        pv = "SpatialAudioDevicePropertyWriter::RuntimeClassInitialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          dword_1801D22E8,
          (unsigned int)&byte_1801A9767,
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
      if ( (unsigned int)dword_1801D22E8 > 2 )
      {
        v25 = 144;
        pv = "SpatialAudioDevicePropertyWriter::RuntimeClassInitialize";
        p_pv = &pv;
        v17 = byte_1801A9735;
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
        if ( (unsigned int)dword_1801D22E8 <= 2 )
          goto LABEL_29;
        v25 = 149;
        v17 = byte_1801A9703;
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
        if ( Instance >= 0 || (unsigned int)dword_1801D22E8 <= 2 )
          goto LABEL_29;
        v25 = 165;
        v17 = byte_1801A966D;
      }
      else
      {
        if ( (unsigned int)dword_1801D22E8 <= 2 )
          goto LABEL_29;
        v25 = 162;
        v17 = byte_1801A96D1;
      }
    }
    else
    {
      if ( (unsigned int)dword_1801D22E8 <= 2 )
        goto LABEL_29;
      v25 = 159;
      v17 = &byte_1801A969F;
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
0x180138b54  mov     [rsp-8+arg_18], rbx
0x180138b59  push    rbp
0x180138b5a  push    rsi
0x180138b5b  push    rdi
0x180138b5c  push    r14
0x180138b5e  push    r15
0x180138b60  lea     rbp, [rsp-37h]
0x180138b65  sub     rsp, 0D0h
0x180138b6c  mov     rax, cs:__security_cookie
0x180138b73  xor     rax, rsp
0x180138b76  mov     [rbp+57h+var_30], rax
0x180138b7a  mov     rsi, r8
0x180138b7d  mov     rdi, rdx
0x180138b80  mov     r14, rcx
0x180138b83  mov     byte ptr [rcx+65h], 0
0x180138b87  mov     al, cs:byte_1801D4378
0x180138b8d  mov     [rcx+64h], al
0x180138b90  add     al, 0FCh
0x180138b92  mov     cs:byte_1801D4378, al
0x180138b98  mov     dword ptr [rcx+60h], 0
0x180138b9f  lea     r15, [rcx+70h]
0x180138ba3  mov     rcx, r15; unsigned __int16 *
0x180138ba6  test    rdx, rdx
0x180138ba9  jz      short loc_180138BBA
0x180138bab  mov     r8, rdx; unsigned __int16 *
0x180138bae  mov     edx, 104h; unsigned __int64
0x180138bb3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180138bb8  jmp     short loc_180138BC5
0x180138bba  mov     r8d, 208h; Size
0x180138bc0  call    memset_0
0x180138bc5  test    rsi, rsi
0x180138bc8  jz      short loc_180138BE6
0x180138bca  xor     ebx, ebx
0x180138bcc  lea     rcx, [r14+58h]
0x180138bd0  mov     rdx, rsi
0x180138bd3  call    ??4?$ComPtr@UISaDeviceProxy@@@WRL@Microsoft@@QEAAAEAV012@PEAUISaDeviceProxy@@@Z; Microsoft::WRL::ComPtr<ISaDeviceProxy>::operator=(ISaDeviceProxy *)
0x180138bd8  lea     rcx, [r14+68h]
0x180138bdc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138be1  jmp     loc_180138EAA
0x180138be6  mov     [rbp+57h+var_A0], 0
0x180138bee  mov     [rbp+57h+var_A8], 0
0x180138bf6  xor     edx, edx; Val
0x180138bf8  lea     r8d, [rdx+4Eh]; Size
0x180138bfc  lea     rcx, [rbp+57h+sz]; void *
0x180138c00  call    memset_0
0x180138c05  mov     r8d, 27h ; '''; cchMax
0x180138c0b  lea     rdx, [rbp+57h+sz]; lpsz
0x180138c0f  lea     rcx, DEVINTERFACE_AUDIO_RENDER; rguid
0x180138c16  call    cs:__imp_StringFromGUID2
0x180138c1c  mov     ebx, eax
0x180138c1e  test    eax, eax
0x180138c20  jns     short loc_180138C68
0x180138c22  mov     ecx, cs:dword_1801D22E8
0x180138c28  cmp     ecx, 2
0x180138c2b  jbe     loc_180138E97
0x180138c31  mov     [rbp+57h+var_B0], eax
0x180138c34  mov     [rbp+57h+var_AC], 8Dh
0x180138c3b  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x180138c42  mov     [rbp+57h+pv], rax
0x180138c46  lea     rax, [rbp+57h+var_B0]
0x180138c4a  mov     [rsp+0F0h+var_C0], rax
0x180138c4f  lea     rax, [rbp+57h+var_AC]
0x180138c53  mov     [rsp+0F0h+var_C8], rax
0x180138c58  lea     rax, [rbp+57h+pv]
0x180138c5c  lea     rdx, byte_1801A9767
0x180138c63  jmp     loc_180138E8C
0x180138c68  lea     rcx, [rbp+57h+var_A0]
0x180138c6c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138c71  lea     rax, [rbp+57h+var_A0]
0x180138c75  mov     [rsp+0F0h+ppv], rax; ppv
0x180138c7a  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180138c81  xor     edx, edx; pUnkOuter
0x180138c83  lea     r8d, [rdx+17h]; dwClsContext
0x180138c87  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x180138c8e  call    cs:__imp_CoCreateInstance
0x180138c94  mov     ebx, eax
0x180138c96  test    eax, eax
0x180138c98  jns     short loc_180138CDD
0x180138c9a  mov     eax, cs:dword_1801D22E8
0x180138ca0  cmp     eax, 2
0x180138ca3  jbe     loc_180138E97
0x180138ca9  mov     [rbp+57h+var_B0], 90h
0x180138cb0  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x180138cb7  mov     [rbp+57h+pv], rax
0x180138cbb  lea     rax, [rbp+57h+var_AC]
0x180138cbf  mov     [rsp+0F0h+var_C0], rax
0x180138cc4  lea     rax, [rbp+57h+var_B0]
0x180138cc8  mov     [rsp+0F0h+var_C8], rax
0x180138ccd  lea     rax, [rbp+57h+pv]
0x180138cd1  lea     rdx, byte_1801A9735
0x180138cd8  jmp     loc_180138E89
0x180138cdd  test    rdi, rdi
0x180138ce0  jz      short loc_180138CF7
0x180138ce2  lea     rdx, [rbp+57h+sz]
0x180138ce6  mov     rcx, rdi
0x180138ce9  call    cs:__imp__o__wcsicmp
0x180138cef  test    eax, eax
0x180138cf1  jnz     loc_180138D86
0x180138cf7  mov     rdi, [rbp+57h+var_A0]
0x180138cfb  mov     rax, [rdi]
0x180138cfe  mov     rbx, [rax+20h]
0x180138d02  lea     rcx, [rbp+57h+var_A8]
0x180138d06  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138d0b  lea     r9, [rbp+57h+var_A8]
0x180138d0f  xor     edx, edx
0x180138d11  lea     r8d, [rdx+1]
0x180138d15  mov     rcx, rdi
0x180138d18  mov     rax, rbx
0x180138d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138d20  mov     ebx, eax
0x180138d22  test    eax, eax
0x180138d24  jns     short loc_180138D48
0x180138d26  mov     eax, cs:dword_1801D22E8
0x180138d2c  cmp     eax, 2
0x180138d2f  jbe     loc_180138E97
0x180138d35  mov     [rbp+57h+var_B0], 95h
0x180138d3c  lea     rdx, byte_1801A9703
0x180138d43  jmp     loc_180138E68
0x180138d48  mov     [rbp+57h+pv], 0
0x180138d50  mov     rcx, [rbp+57h+var_A8]
0x180138d54  mov     rax, [rcx]
0x180138d57  lea     rdx, [rbp+57h+pv]
0x180138d5b  mov     rax, [rax+28h]
0x180138d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138d64  mov     r9, [rbp+57h+pv]
0x180138d68  lea     r8, aS_0; "%s"
0x180138d6f  mov     edx, 104h; unsigned __int64
0x180138d74  mov     rcx, r15; unsigned __int16 *
0x180138d77  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180138d7c  mov     rcx, [rbp+57h+pv]; pv
0x180138d80  call    cs:__imp_CoTaskMemFree
0x180138d86  mov     rdi, [rbp+57h+var_A0]
0x180138d8a  mov     rax, [rdi]
0x180138d8d  mov     rbx, [rax+28h]
0x180138d91  lea     rcx, [rbp+57h+var_A8]
0x180138d95  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138d9a  lea     r8, [rbp+57h+var_A8]
0x180138d9e  mov     rdx, r15
0x180138da1  mov     rcx, rdi
0x180138da4  mov     rax, rbx
0x180138da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138dac  mov     ebx, eax
0x180138dae  test    eax, eax
0x180138db0  jns     short loc_180138DD4
0x180138db2  mov     eax, cs:dword_1801D22E8
0x180138db8  cmp     eax, 2
0x180138dbb  jbe     loc_180138E97
0x180138dc1  mov     [rbp+57h+var_B0], 9Fh
0x180138dc8  lea     rdx, byte_1801A969F
0x180138dcf  jmp     loc_180138E68
0x180138dd4  mov     rsi, [rbp+57h+var_A8]
0x180138dd8  mov     rax, [rsi]
0x180138ddb  mov     rdi, [rax+20h]
0x180138ddf  lea     rcx, [r14+58h]
0x180138de3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138de8  lea     r8, [r14+58h]
0x180138dec  xor     edx, edx
0x180138dee  mov     rcx, rsi
0x180138df1  mov     rax, rdi
0x180138df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138df9  mov     ebx, eax
0x180138dfb  test    eax, eax
0x180138dfd  jns     short loc_180138E1E
0x180138dff  mov     eax, cs:dword_1801D22E8
0x180138e05  cmp     eax, 2
0x180138e08  jbe     loc_180138E97
0x180138e0e  mov     [rbp+57h+var_B0], 0A2h
0x180138e15  lea     rdx, byte_1801A96D1
0x180138e1c  jmp     short loc_180138E68
0x180138e1e  lea     rbx, [r14+68h]
0x180138e22  mov     rcx, rbx
0x180138e25  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138e2a  mov     [rsp+0F0h+ppv], rbx; ppv
0x180138e2f  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180138e36  xor     edx, edx; pUnkOuter
0x180138e38  lea     r8d, [rdx+1]; dwClsContext
0x180138e3c  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180138e43  call    cs:__imp_CoCreateInstance
0x180138e49  mov     ebx, eax
0x180138e4b  test    eax, eax
0x180138e4d  jns     short loc_180138E97
0x180138e4f  mov     eax, cs:dword_1801D22E8
0x180138e55  cmp     eax, 2
0x180138e58  jbe     short loc_180138E97
0x180138e5a  mov     [rbp+57h+var_B0], 0A5h
0x180138e61  lea     rdx, byte_1801A966D
0x180138e68  lea     rax, aSpatialaudiode_27; "SpatialAudioDevicePropertyWriter::Runti"...
0x180138e6f  mov     [rbp+57h+var_90], rax
0x180138e73  lea     rax, [rbp+57h+var_AC]
0x180138e77  mov     [rsp+0F0h+var_C0], rax
0x180138e7c  lea     rax, [rbp+57h+var_B0]
0x180138e80  mov     [rsp+0F0h+var_C8], rax
0x180138e85  lea     rax, [rbp+57h+var_90]
0x180138e89  mov     [rbp+57h+var_AC], ebx
0x180138e8c  mov     [rsp+0F0h+ppv], rax
0x180138e91  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180138e96  nop
0x180138e97  lea     rcx, [rbp+57h+var_A8]
0x180138e9b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138ea0  nop
0x180138ea1  lea     rcx, [rbp+57h+var_A0]
0x180138ea5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180138eaa  mov     eax, ebx
0x180138eac  mov     rcx, [rbp+57h+var_30]
0x180138eb0  xor     rcx, rsp; StackCookie
0x180138eb3  call    __security_check_cookie
0x180138eb8  mov     rbx, [rsp+0F0h+arg_18]
0x180138ec0  add     rsp, 0D0h
0x180138ec7  pop     r15
0x180138ec9  pop     r14
0x180138ecb  pop     rdi
0x180138ecc  pop     rsi
0x180138ecd  pop     rbp
0x180138ece  retn
```
