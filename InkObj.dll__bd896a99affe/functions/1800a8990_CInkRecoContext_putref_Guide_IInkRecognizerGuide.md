# CInkRecoContext::putref_Guide(IInkRecognizerGuide *)

- ea: `0x1800a8990`
- end: `0x1800a8cec`
- name: `?putref_Guide@CInkRecoContext@@UEAAJPEAUIInkRecognizerGuide@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CInkRecoContext *__hidden this, struct IInkRecognizerGuide *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800365f8`
- `0x180036824`
- `0x180084fac`
- `0x1800a8990`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8a5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8a51`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8a51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a8aa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a8aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8c88`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8c55`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8c55`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkRecoContext::putref_Guide(CInkRecoContext *this, struct IInkRecognizerGuide *a2)
{
  __int64 v4; // rdx
  int Instance; // ebx
  _QWORD *v7; // r14
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // rsi
  int (*v11)(int, unsigned __int8 *); // r9
  unsigned int v12; // r8d
  unsigned int v13; // eax
  struct IUnknown *ppv; // [rsp+30h] [rbp-A8h] BYREF
  DWORD dwindex; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v16[44]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-68h] BYREF
  __int128 v18; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v19[7]; // [rsp+90h] [rbp-48h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v17, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  ppv = 0;
  if ( !a2 )
  {
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
    return 2147500035LL;
  }
  Instance = 0;
  if ( *((_QWORD *)this + 33) )
  {
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
    return 2147746359LL;
  }
  try
  {
    if ( *((_QWORD *)this + 12) )
      goto LABEL_8;
    LOBYTE(v4) = 1;
    Instance = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v4);
    if ( Instance >= 0 )
    {
      if ( !*((_QWORD *)this + 12) )
      {
LABEL_7:
        Instance = -2147418113;
        goto LABEL_39;
      }
LABEL_8:
      v7 = (_QWORD *)((char *)this + 160);
      if ( !*((_QWORD *)this + 20) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *v7 = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          Instance = LastError;
          if ( LastError > 0 )
            Instance = (unsigned __int16)LastError | 0x80070000;
        }
        if ( Instance < 0 )
          goto LABEL_39;
      }
      if ( !ppv )
        Instance = CoCreateInstance(
                     &CLSID_InkRecognizerGuide,
                     0,
                     7u,
                     &GUID_d934be07_7b84_4208_9136_83c20994e905,
                     (LPVOID *)&ppv);
      if ( Instance < 0 )
        goto LABEL_39;
      v18 = 0;
      memset(v19, 0, sizeof(v19));
      Instance = ((__int64 (__fastcall *)(struct IInkRecognizerGuide *, __int128 *))a2->lpVtbl->get_GuideData)(a2, &v18);
      if ( Instance >= 0 )
      {
        *(_OWORD *)v16 = v18;
        *(_OWORD *)&v16[16] = *(_OWORD *)v19;
        *(_OWORD *)&v16[28] = *(_OWORD *)&v19[3];
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, _BYTE *))ppv->lpVtbl[6].QueryInterface)(ppv, v16);
      }
      if ( Instance < 0 )
        goto LABEL_39;
      v10 = CoTaskMemAlloc(8u);
      v18 = 0;
      memset(v19, 0, sizeof(v19));
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *))ppv->lpVtbl[5].Release)(ppv, &v18);
      if ( Instance >= 0 )
      {
        v12 = 0;
        *(_DWORD *)&v16[20] = 0;
        *(_DWORD *)&v16[32] = 0;
        *(_QWORD *)v16 = v18;
        *(_DWORD *)&v16[8] = DWORD2(v18) - v18;
        *(_QWORD *)&v16[12] = (unsigned int)(HIDWORD(v18) - DWORD1(v18));
        if ( (v19[0] & 0x80000000) == 0 )
          v12 = v19[0];
        *(_DWORD *)&v16[16] = v12;
        v13 = *(_DWORD *)&v16[20];
        if ( (v19[3] & 0x80000000) == 0 )
          v13 = v19[3];
        *(_DWORD *)&v16[20] = v13;
        *(_DWORD *)&v16[24] = v19[5];
        *(_DWORD *)&v16[28] = v19[4];
        if ( (v19[6] & 0x80000000) == 0 )
          *(_DWORD *)&v16[32] = v19[3] - v19[6];
        if ( !v10 )
          goto LABEL_29;
        *v10 = v7;
        Instance = BackgroundSetGuide(
                     *(HRECOCONTEXT *)(*((_QWORD *)this + 12) + 16LL),
                     (const struct tagRECO_GUIDE *)v16,
                     v12,
                     v11,
                     v10);
      }
      if ( Instance < 0 )
      {
        if ( v10 )
          CoTaskMemFree(v10);
        goto LABEL_39;
      }
LABEL_29:
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex) >= 0 )
      {
        Instance = *((_DWORD *)this + 47);
        if ( Instance >= 0 )
          ATL::AtlComPtrAssign((struct IUnknown **)this + 34, ppv);
        goto LABEL_39;
      }
      goto LABEL_7;
    }
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    Instance = dwindex;
  }
LABEL_39:
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800a8990  mov     [rsp+arg_10], rbx
0x1800a8995  push    rsi
0x1800a8996  push    rdi
0x1800a8997  push    r14
0x1800a8999  sub     rsp, 0C0h
0x1800a89a0  mov     rax, cs:__security_cookie
0x1800a89a7  xor     rax, rsp
0x1800a89aa  mov     [rsp+0D8h+var_28], rax
0x1800a89b2  mov     rsi, rdx
0x1800a89b5  mov     rdi, rcx
0x1800a89b8  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a89bf  lea     rcx, [rsp+0D8h+var_68]; this
0x1800a89c4  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a89c9  nop
0x1800a89ca  mov     [rsp+0D8h+var_A8], 0
0x1800a89d3  test    rsi, rsi
0x1800a89d6  jz      loc_1800A8CAE
0x1800a89dc  xor     ebx, ebx
0x1800a89de  lea     rcx, [rdi-10h]
0x1800a89e2  cmp     [rcx+118h], rbx
0x1800a89e9  jz      short loc_1800A8A0A
0x1800a89eb  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800a89f0  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a89f5  nop
0x1800a89f6  lea     rcx, [rsp+0D8h+var_68]; this
0x1800a89fb  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8a00  mov     eax, 80040237h
0x1800a8a05  jmp     loc_1800A8CC8
0x1800a8a0a  cmp     qword ptr [rdi+60h], 0
0x1800a8a0f  jnz     short loc_1800A8A3A
0x1800a8a11  mov     rax, [rcx]
0x1800a8a14  mov     dl, 1
0x1800a8a16  mov     rax, [rax+48h]
0x1800a8a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a1f  mov     ebx, eax
0x1800a8a21  test    eax, eax
0x1800a8a23  js      loc_1800A8C8F
0x1800a8a29  cmp     qword ptr [rdi+60h], 0
0x1800a8a2e  jnz     short loc_1800A8A3A
0x1800a8a30  mov     ebx, 8000FFFFh
0x1800a8a35  jmp     loc_1800A8C8F
0x1800a8a3a  lea     r14, [rdi+0A0h]
0x1800a8a41  cmp     qword ptr [r14], 0
0x1800a8a45  jnz     short loc_1800A8A7C
0x1800a8a47  xor     r9d, r9d; lpName
0x1800a8a4a  xor     r8d, r8d; bInitialState
0x1800a8a4d  xor     edx, edx; bManualReset
0x1800a8a4f  xor     ecx, ecx; lpEventAttributes
0x1800a8a51  call    cs:__imp_CreateEventW
0x1800a8a57  mov     [r14], rax
0x1800a8a5a  test    rax, rax
0x1800a8a5d  jnz     short loc_1800A8A74
0x1800a8a5f  call    cs:__imp_GetLastError
0x1800a8a65  mov     ebx, eax
0x1800a8a67  test    eax, eax
0x1800a8a69  jle     short loc_1800A8A74
0x1800a8a6b  movzx   ebx, ax
0x1800a8a6e  or      ebx, 80070000h
0x1800a8a74  test    ebx, ebx
0x1800a8a76  js      loc_1800A8C8F
0x1800a8a7c  cmp     [rsp+0D8h+var_A8], 0
0x1800a8a82  jnz     short loc_1800A8AAA
0x1800a8a84  lea     rax, [rsp+0D8h+var_A8]
0x1800a8a89  mov     [rsp+0D8h+ppv], rax; ppv
0x1800a8a8e  lea     r9, _GUID_d934be07_7b84_4208_9136_83c20994e905; riid
0x1800a8a95  xor     edx, edx; pUnkOuter
0x1800a8a97  lea     r8d, [rdx+7]; dwClsContext
0x1800a8a9b  lea     rcx, CLSID_InkRecognizerGuide; rclsid
0x1800a8aa2  call    cs:__imp_CoCreateInstance
0x1800a8aa8  mov     ebx, eax
0x1800a8aaa  test    ebx, ebx
0x1800a8aac  js      loc_1800A8C8F
0x1800a8ab2  xorps   xmm0, xmm0
0x1800a8ab5  movups  [rsp+0D8h+var_58], xmm0
0x1800a8abd  movups  xmmword ptr [rsp+0D8h+var_48], xmm0
0x1800a8ac5  movups  xmmword ptr [rsp+0D8h+var_48+0Ch], xmm0
0x1800a8acd  mov     rax, [rsi]
0x1800a8ad0  lea     rdx, [rsp+0D8h+var_58]
0x1800a8ad8  mov     rcx, rsi
0x1800a8adb  mov     rax, [rax+88h]
0x1800a8ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8ae7  mov     ebx, eax
0x1800a8ae9  test    eax, eax
0x1800a8aeb  js      short loc_1800A8B2F
0x1800a8aed  mov     rcx, [rsp+0D8h+var_A8]
0x1800a8af2  movups  xmm0, [rsp+0D8h+var_58]
0x1800a8afa  movaps  xmmword ptr [rsp+0D8h+var_98.xOrigin], xmm0
0x1800a8aff  movups  xmm1, xmmword ptr [rsp+0D8h+var_48]
0x1800a8b07  movaps  xmmword ptr [rsp+0D8h+var_98.cxBase], xmm1
0x1800a8b0c  movups  xmm0, xmmword ptr [rsp+0D8h+var_48+0Ch]
0x1800a8b14  movups  xmmword ptr [rsp+0D8h+var_98.cVertBox], xmm0
0x1800a8b19  mov     rax, [rcx]
0x1800a8b1c  lea     rdx, [rsp+0D8h+var_98]
0x1800a8b21  mov     rax, [rax+90h]
0x1800a8b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8b2d  mov     ebx, eax
0x1800a8b2f  test    ebx, ebx
0x1800a8b31  js      loc_1800A8C8F
0x1800a8b37  mov     ecx, 8; cb
0x1800a8b3c  call    cs:__imp_CoTaskMemAlloc
0x1800a8b42  mov     rsi, rax
0x1800a8b45  xorps   xmm0, xmm0
0x1800a8b48  movups  [rsp+0D8h+var_58], xmm0
0x1800a8b50  movups  xmmword ptr [rsp+0D8h+var_48], xmm0
0x1800a8b58  movups  xmmword ptr [rsp+0D8h+var_48+0Ch], xmm0
0x1800a8b60  mov     rcx, [rsp+0D8h+var_A8]
0x1800a8b65  mov     rdx, [rcx]
0x1800a8b68  mov     rax, [rdx+88h]
0x1800a8b6f  lea     rdx, [rsp+0D8h+var_58]
0x1800a8b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8b7c  mov     ebx, eax
0x1800a8b7e  test    eax, eax
0x1800a8b80  js      loc_1800A8C31
0x1800a8b86  xor     r8d, r8d
0x1800a8b89  mov     qword ptr [rsp+0D8h+var_98.cxBase], r8
0x1800a8b8e  mov     [rsp+0D8h+var_98.cyMid], r8d
0x1800a8b93  mov     ecx, dword ptr [rsp+0D8h+var_58]
0x1800a8b9a  mov     [rsp+0D8h+var_98.xOrigin], ecx
0x1800a8b9e  mov     edx, dword ptr [rsp+0D8h+var_58+4]
0x1800a8ba5  mov     [rsp+0D8h+var_98.yOrigin], edx
0x1800a8ba9  mov     eax, dword ptr [rsp+0D8h+var_58+8]
0x1800a8bb0  sub     eax, ecx
0x1800a8bb2  mov     [rsp+0D8h+var_98.cxBox], eax
0x1800a8bb6  mov     eax, dword ptr [rsp+0D8h+var_58+0Ch]
0x1800a8bbd  sub     eax, edx
0x1800a8bbf  mov     [rsp+0D8h+var_98.cyBox], eax
0x1800a8bc3  mov     eax, [rsp+0D8h+var_48]
0x1800a8bca  test    eax, eax
0x1800a8bcc  cmovns  r8d, eax; unsigned int
0x1800a8bd0  mov     [rsp+0D8h+var_98.cxBase], r8d
0x1800a8bd5  mov     eax, [rsp+0D8h+var_98.cyBase]
0x1800a8bd9  mov     ecx, [rsp+0D8h+var_48+0Ch]
0x1800a8be0  test    ecx, ecx
0x1800a8be2  cmovns  eax, ecx
0x1800a8be5  mov     [rsp+0D8h+var_98.cyBase], eax
0x1800a8be9  mov     eax, [rsp+0D8h+var_34]
0x1800a8bf0  mov     [rsp+0D8h+var_98.cHorzBox], eax
0x1800a8bf4  mov     eax, [rsp+0D8h+var_38]
0x1800a8bfb  mov     [rsp+0D8h+var_98.cVertBox], eax
0x1800a8bff  mov     eax, [rsp+0D8h+var_30]
0x1800a8c06  test    eax, eax
0x1800a8c08  js      short loc_1800A8C10
0x1800a8c0a  sub     ecx, eax
0x1800a8c0c  mov     [rsp+0D8h+var_98.cyMid], ecx
0x1800a8c10  test    rsi, rsi
0x1800a8c13  jz      short loc_1800A8C35
0x1800a8c15  mov     [rsi], r14
0x1800a8c18  mov     rcx, [rdi+60h]
0x1800a8c1c  mov     [rsp+0D8h+ppv], rsi; void *
0x1800a8c21  lea     rdx, [rsp+0D8h+var_98]; struct tagRECO_GUIDE *
0x1800a8c26  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a8c2a  call    ?BackgroundSetGuide@@YAJPEAUHRECOCONTEXT__@@PEBUtagRECO_GUIDE@@KP6AJJPEAE@ZPEAX@Z; BackgroundSetGuide(HRECOCONTEXT__ *,tagRECO_GUIDE const *,ulong,long (*)(long,uchar *),void *)
0x1800a8c2f  mov     ebx, eax
0x1800a8c31  test    ebx, ebx
0x1800a8c33  js      short loc_1800A8C80
0x1800a8c35  mov     [rsp+0D8h+dwindex], 0
0x1800a8c3d  lea     rax, [rsp+0D8h+dwindex]
0x1800a8c42  mov     [rsp+0D8h+ppv], rax; lpdwindex
0x1800a8c47  mov     r9, r14; pHandles
0x1800a8c4a  mov     edx, 493E0h; dwTimeout
0x1800a8c4f  xor     ecx, ecx; dwFlags
0x1800a8c51  lea     r8d, [rcx+1]; cHandles
0x1800a8c55  call    cs:__imp_CoWaitForMultipleHandles
0x1800a8c5b  test    eax, eax
0x1800a8c5d  js      loc_1800A8A30
0x1800a8c63  mov     ebx, [rdi+0BCh]
0x1800a8c69  test    ebx, ebx
0x1800a8c6b  js      short loc_1800A8C8F
0x1800a8c6d  lea     rcx, [rdi+110h]; struct IUnknown **
0x1800a8c74  mov     rdx, [rsp+0D8h+var_A8]; struct IUnknown *
0x1800a8c79  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800a8c7e  jmp     short loc_1800A8C8F
0x1800a8c80  test    rsi, rsi
0x1800a8c83  jz      short loc_1800A8C8F
0x1800a8c85  mov     rcx, rsi; pv
0x1800a8c88  call    cs:__imp_CoTaskMemFree
0x1800a8c8e  nop
0x1800a8c8f  jmp     short loc_1800A8C95
0x1800a8c91  mov     ebx, [rsp+0D8h+dwindex]
0x1800a8c95  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800a8c9a  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a8c9f  nop
0x1800a8ca0  lea     rcx, [rsp+0D8h+var_68]; this
0x1800a8ca5  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8caa  mov     eax, ebx
0x1800a8cac  jmp     short loc_1800A8CC8
0x1800a8cae  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800a8cb3  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a8cb8  nop
0x1800a8cb9  lea     rcx, [rsp+0D8h+var_68]; this
0x1800a8cbe  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8cc3  mov     eax, 80004003h
0x1800a8cc8  mov     rcx, [rsp+0D8h+var_28]
0x1800a8cd0  xor     rcx, rsp; StackCookie
0x1800a8cd3  call    __security_check_cookie
0x1800a8cd8  mov     rbx, [rsp+0D8h+arg_10]
0x1800a8ce0  add     rsp, 0C0h
0x1800a8ce7  pop     r14
0x1800a8ce9  pop     rdi
0x1800a8cea  pop     rsi
0x1800a8ceb  retn
```
