# CInkRecoContext::put_Factoid(ushort *)

- ea: `0x1800a8170`
- end: `0x1800a83f2`
- name: `?put_Factoid@CInkRecoContext@@UEAAJPEAG@Z`
- size: `642`
- prototype: `int(CInkRecoContext *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180084e64`
- `0x1800a32a4`
- `0x1800a32e8`
- `0x1800a8170`
- `0x180104ef2`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a820e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a820e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8200`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8200`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a81cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a8292`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a8380`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a83b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a83c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a81cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a8292`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a8380`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a83b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a83c7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8278`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8285`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a82d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8366`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8373`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8278`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8285`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a82d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8366`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a82ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a82ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a839b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a839b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8325`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8325`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CInkRecoContext::put_Factoid(CInkRecoContext *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // esi
  _QWORD *v8; // r15
  HANDLE EventW; // rax
  signed int LastError; // eax
  OLECHAR *v11; // rbx
  _QWORD *v12; // rax
  void *v13; // r14
  UINT v14; // eax
  int (*v15)(int, unsigned __int8 *); // r9
  char *v16; // rcx
  _BYTE v17[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp+10h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v17, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  pbstr = 0;
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 )
    {
      v6 = 0;
      if ( *((_QWORD *)this + 33) )
      {
        SysFreeString(0);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
        return 2147746359LL;
      }
      v8 = (_QWORD *)((char *)this + 160);
      if ( *((_QWORD *)this + 20) )
        goto LABEL_36;
      EventW = CreateEventW(0, 0, 0, 0);
      *v8 = EventW;
      if ( EventW )
        goto LABEL_36;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_36:
        if ( !*((_QWORD *)this + 12) )
        {
          LOBYTE(v4) = 1;
          v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v4);
        }
      }
      if ( !wcscmp_0(L"DEFAULT", a2) )
      {
        ATL::CComBSTR::operator=(&pbstr, 0);
        v11 = pbstr;
      }
      else
      {
        ATL::CComBSTR::operator=(&pbstr, a2);
        v11 = pbstr;
        if ( !SysStringLen(pbstr) && SysStringLen(a2) )
          goto LABEL_18;
      }
      if ( v6 < 0 )
      {
LABEL_32:
        SysFreeString(v11);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
        return (unsigned int)v6;
      }
      v12 = CoTaskMemAlloc(8u);
      v13 = v12;
      if ( !v12 )
      {
        v6 = -2147024882;
        goto LABEL_32;
      }
      *v12 = v8;
      v14 = SysStringLen(v11);
      v6 = BackgroundSetFactoidOrConstraint(*(_QWORD **)(*((_QWORD *)this + 12) + 16LL), v14, v11, v15, v13, 1);
      if ( v6 < 0 )
      {
        CoTaskMemFree(v13);
        goto LABEL_32;
      }
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex) < 0 )
      {
        v6 = -2147418113;
        goto LABEL_32;
      }
      v6 = *((_DWORD *)this + 47);
      if ( v6 < 0 )
        goto LABEL_32;
      v16 = (char *)this + 144;
      if ( !v11 )
      {
        ATL::CComBSTR::operator=(v16, 0);
        goto LABEL_32;
      }
      ATL::CComBSTR::operator=(v16, &pbstr);
      if ( SysStringLen(*((BSTR *)this + 18)) || !SysStringLen(v11) )
        goto LABEL_32;
LABEL_18:
      SysFreeString(v11);
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
      return 2147942414LL;
    }
  }
  SysFreeString(0);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a8170  mov     [rsp+arg_10], rbx
0x1800a8175  push    rsi
0x1800a8176  push    rdi
0x1800a8177  push    r12
0x1800a8179  push    r14
0x1800a817b  push    r15
0x1800a817d  sub     rsp, 40h
0x1800a8181  mov     r14, rdx
0x1800a8184  mov     rdi, rcx
0x1800a8187  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a818e  lea     rcx, [rsp+68h+var_38]; this
0x1800a8193  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a8198  nop
0x1800a8199  xor     r12d, r12d
0x1800a819c  mov     [rsp+68h+pbstr], r12
0x1800a81a1  test    r14, r14
0x1800a81a4  jz      loc_1800A83C5
0x1800a81aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a81ae  inc     rax
0x1800a81b1  cmp     [r14+rax*2], r12w
0x1800a81b6  jnz     short loc_1800A81AE
0x1800a81b8  test    rax, rax
0x1800a81bb  jz      loc_1800A83C5
0x1800a81c1  mov     esi, r12d
0x1800a81c4  cmp     [rdi+108h], r12
0x1800a81cb  jz      short loc_1800A81EA
0x1800a81cd  xor     ecx, ecx; bstrString
0x1800a81cf  call    cs:__imp_SysFreeString
0x1800a81d5  nop
0x1800a81d6  lea     rcx, [rsp+68h+var_38]; this
0x1800a81db  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a81e0  mov     eax, 80040237h
0x1800a81e5  jmp     loc_1800A83DD
0x1800a81ea  lea     r15, [rdi+0A0h]
0x1800a81f1  cmp     [r15], r12
0x1800a81f4  jnz     short loc_1800A8227
0x1800a81f6  xor     r9d, r9d; lpName
0x1800a81f9  xor     r8d, r8d; bInitialState
0x1800a81fc  xor     edx, edx; bManualReset
0x1800a81fe  xor     ecx, ecx; lpEventAttributes
0x1800a8200  call    cs:__imp_CreateEventW
0x1800a8206  mov     [r15], rax
0x1800a8209  test    rax, rax
0x1800a820c  jnz     short loc_1800A8227
0x1800a820e  call    cs:__imp_GetLastError
0x1800a8214  mov     esi, eax
0x1800a8216  test    eax, eax
0x1800a8218  jle     short loc_1800A8223
0x1800a821a  movzx   esi, ax
0x1800a821d  or      esi, 80070000h
0x1800a8223  test    esi, esi
0x1800a8225  js      short loc_1800A8242
0x1800a8227  cmp     [rdi+60h], r12
0x1800a822b  jnz     short loc_1800A8242
0x1800a822d  mov     rax, [rdi-10h]
0x1800a8231  mov     dl, 1
0x1800a8233  lea     rcx, [rdi-10h]
0x1800a8237  mov     rax, [rax+48h]
0x1800a823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8240  mov     esi, eax
0x1800a8242  mov     rdx, r14; String2
0x1800a8245  lea     rcx, aDefault; "DEFAULT"
0x1800a824c  call    wcscmp_0
0x1800a8251  lea     rcx, [rsp+68h+pbstr]
0x1800a8256  test    eax, eax
0x1800a8258  jnz     short loc_1800A8268
0x1800a825a  xor     edx, edx
0x1800a825c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a8261  mov     rbx, [rsp+68h+pbstr]
0x1800a8266  jmp     short loc_1800A82AD
0x1800a8268  mov     rdx, r14
0x1800a826b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a8270  mov     rbx, [rsp+68h+pbstr]
0x1800a8275  mov     rcx, rbx; pbstr
0x1800a8278  call    cs:__imp_SysStringLen
0x1800a827e  test    eax, eax
0x1800a8280  jnz     short loc_1800A82AD
0x1800a8282  mov     rcx, r14; pbstr
0x1800a8285  call    cs:__imp_SysStringLen
0x1800a828b  test    eax, eax
0x1800a828d  jz      short loc_1800A82AD
0x1800a828f  mov     rcx, rbx; bstrString
0x1800a8292  call    cs:__imp_SysFreeString
0x1800a8298  nop
0x1800a8299  lea     rcx, [rsp+68h+var_38]; this
0x1800a829e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a82a3  mov     eax, 8007000Eh
0x1800a82a8  jmp     loc_1800A83DD
0x1800a82ad  test    esi, esi
0x1800a82af  js      loc_1800A83A2
0x1800a82b5  mov     ecx, 8; cb
0x1800a82ba  call    cs:__imp_CoTaskMemAlloc
0x1800a82c0  mov     r14, rax
0x1800a82c3  test    rax, rax
0x1800a82c6  jnz     short loc_1800A82D2
0x1800a82c8  mov     esi, 8007000Eh
0x1800a82cd  jmp     loc_1800A83A2
0x1800a82d2  mov     [rax], r15
0x1800a82d5  mov     rcx, rbx; pbstr
0x1800a82d8  call    cs:__imp_SysStringLen
0x1800a82de  mov     rcx, [rdi+60h]
0x1800a82e2  mov     [rsp+68h+var_40], 1; bool
0x1800a82e7  mov     [rsp+68h+lpdwindex], r14; void *
0x1800a82ec  mov     r8, rbx; unsigned __int16 *
0x1800a82ef  mov     edx, eax; unsigned int
0x1800a82f1  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a82f5  call    ?BackgroundSetFactoidOrConstraint@@YAJPEAUHRECOCONTEXT__@@KPEBGP6AJJPEAE@ZPEAX_N@Z; BackgroundSetFactoidOrConstraint(HRECOCONTEXT__ *,ulong,ushort const *,long (*)(long,uchar *),void *,bool)
0x1800a82fa  mov     esi, eax
0x1800a82fc  test    eax, eax
0x1800a82fe  js      loc_1800A8398
0x1800a8304  mov     [rsp+68h+dwindex], r12d
0x1800a8309  lea     r9, [rdi+0A0h]; pHandles
0x1800a8310  lea     rax, [rsp+68h+dwindex]
0x1800a8315  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800a831a  mov     edx, 493E0h; dwTimeout
0x1800a831f  xor     ecx, ecx; dwFlags
0x1800a8321  lea     r8d, [rcx+1]; cHandles
0x1800a8325  call    cs:__imp_CoWaitForMultipleHandles
0x1800a832b  test    eax, eax
0x1800a832d  jns     short loc_1800A8336
0x1800a832f  mov     esi, 8000FFFFh
0x1800a8334  jmp     short loc_1800A83A2
0x1800a8336  mov     esi, [rdi+0BCh]
0x1800a833c  test    esi, esi
0x1800a833e  js      short loc_1800A83A2
0x1800a8340  lea     rcx, [rdi+90h]
0x1800a8347  test    rbx, rbx
0x1800a834a  jnz     short loc_1800A8355
0x1800a834c  xor     edx, edx
0x1800a834e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a8353  jmp     short loc_1800A83A2
0x1800a8355  lea     rdx, [rsp+68h+pbstr]
0x1800a835a  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800a835f  mov     rcx, [rdi+90h]; pbstr
0x1800a8366  call    cs:__imp_SysStringLen
0x1800a836c  test    eax, eax
0x1800a836e  jnz     short loc_1800A83A2
0x1800a8370  mov     rcx, rbx; pbstr
0x1800a8373  call    cs:__imp_SysStringLen
0x1800a8379  test    eax, eax
0x1800a837b  jz      short loc_1800A83A2
0x1800a837d  mov     rcx, rbx; bstrString
0x1800a8380  call    cs:__imp_SysFreeString
0x1800a8386  nop
0x1800a8387  lea     rcx, [rsp+68h+var_38]; this
0x1800a838c  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8391  mov     eax, 8007000Eh
0x1800a8396  jmp     short loc_1800A83DD
0x1800a8398  mov     rcx, r14; pv
0x1800a839b  call    cs:__imp_CoTaskMemFree
0x1800a83a1  nop
0x1800a83a2  jmp     short loc_1800A83AD
0x1800a83a4  mov     rbx, [rsp+68h+pbstr]
0x1800a83a9  mov     esi, [rsp+68h+dwindex]
0x1800a83ad  mov     rcx, rbx; bstrString
0x1800a83b0  call    cs:__imp_SysFreeString
0x1800a83b6  nop
0x1800a83b7  lea     rcx, [rsp+68h+var_38]; this
0x1800a83bc  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a83c1  mov     eax, esi
0x1800a83c3  jmp     short loc_1800A83DD
0x1800a83c5  xor     ecx, ecx; bstrString
0x1800a83c7  call    cs:__imp_SysFreeString
0x1800a83cd  nop
0x1800a83ce  lea     rcx, [rsp+68h+var_38]; this
0x1800a83d3  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a83d8  mov     eax, 80070057h
0x1800a83dd  mov     rbx, [rsp+68h+arg_10]
0x1800a83e5  add     rsp, 40h
0x1800a83e9  pop     r15
0x1800a83eb  pop     r14
0x1800a83ed  pop     r12
0x1800a83ef  pop     rdi
0x1800a83f0  pop     rsi
0x1800a83f1  retn
```
