# CInkRecoContext::put_PrefixText(ushort *)

- ea: `0x1800a8400`
- end: `0x1800a85c8`
- name: `?put_PrefixText@CInkRecoContext@@UEAAJPEAG@Z`
- size: `456`
- prototype: `int(CInkRecoContext *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180085060`
- `0x1800a32e8`
- `0x1800a8400`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a84d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a84d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a84c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a84c2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8482`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a848f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8517`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8530`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8482`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a848f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8517`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a84f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a84f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a859e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a859e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8585`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8585`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::put_PrefixText(CInkRecoContext *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  BSTR *v6; // r12
  _QWORD *v7; // r14
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // rax
  void *v11; // rsi
  const unsigned __int16 *v12; // r14
  UINT v13; // r15d
  const unsigned __int16 *v14; // rbx
  UINT v15; // eax
  int (*v17)(int, unsigned __int8 *); // [rsp+28h] [rbp-60h]
  _BYTE v18[72]; // [rsp+40h] [rbp-48h] BYREF
  DWORD dwindex; // [rsp+90h] [rbp+8h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v18, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  if ( *((_QWORD *)this + 33) )
  {
    v5 = -2147220937;
    goto LABEL_30;
  }
  try
  {
    if ( !*((_QWORD *)this + 12) )
    {
      LOBYTE(v4) = 1;
      v5 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v4);
      if ( v5 < 0 )
        goto LABEL_30;
      if ( !*((_QWORD *)this + 12) )
        goto LABEL_6;
    }
    v6 = (BSTR *)((char *)this + 120);
    ATL::CComBSTR::operator=((char *)this + 120, a2);
    if ( !SysStringLen(*((BSTR *)this + 15)) && SysStringLen(a2) )
      goto LABEL_9;
    v7 = (_QWORD *)((char *)this + 160);
    if ( !*((_QWORD *)this + 20) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *v7 = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_30;
      }
    }
    v10 = CoTaskMemAlloc(8u);
    v11 = v10;
    if ( v10 )
    {
      *v10 = v7;
      v12 = (const unsigned __int16 *)*((_QWORD *)this + 16);
      if ( v12 )
        v13 = SysStringLen(*((BSTR *)this + 16));
      else
        v13 = 0;
      v14 = *v6;
      if ( *v6 )
        v15 = SysStringLen(*v6);
      else
        v15 = 0;
      v5 = BackgroundSetTextContext(*(_QWORD **)(*((_QWORD *)this + 12) + 16LL), v15, v14, v13, v12, v17, v11);
      if ( v5 < 0 )
      {
        CoTaskMemFree(v11);
      }
      else
      {
        dwindex = 0;
        if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex) < 0 )
        {
LABEL_6:
          v5 = -2147418113;
          goto LABEL_30;
        }
        v5 = *((_DWORD *)this + 47);
      }
    }
    else
    {
LABEL_9:
      v5 = -2147024882;
    }
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    v5 = dwindex;
  }
LABEL_30:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a8400  push    rbx
0x1800a8402  push    rsi
0x1800a8403  push    rdi
0x1800a8404  push    r12
0x1800a8406  push    r14
0x1800a8408  push    r15
0x1800a840a  sub     rsp, 58h
0x1800a840e  mov     rsi, rdx
0x1800a8411  mov     rdi, rcx
0x1800a8414  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a841b  lea     rcx, [rsp+88h+var_48]; this
0x1800a8420  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a8425  nop
0x1800a8426  xor     ebx, ebx
0x1800a8428  lea     rcx, [rdi-10h]
0x1800a842c  cmp     [rcx+118h], rbx
0x1800a8433  jz      short loc_1800A843F
0x1800a8435  mov     ebx, 80040237h
0x1800a843a  jmp     loc_1800A85AE
0x1800a843f  cmp     qword ptr [rdi+60h], 0
0x1800a8444  jnz     short loc_1800A846F
0x1800a8446  mov     rax, [rcx]
0x1800a8449  mov     dl, 1
0x1800a844b  mov     rax, [rax+48h]
0x1800a844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8454  mov     ebx, eax
0x1800a8456  test    eax, eax
0x1800a8458  js      loc_1800A85A5
0x1800a845e  cmp     qword ptr [rdi+60h], 0
0x1800a8463  jnz     short loc_1800A846F
0x1800a8465  mov     ebx, 8000FFFFh
0x1800a846a  jmp     loc_1800A85A5
0x1800a846f  lea     r12, [rdi+78h]
0x1800a8473  mov     rdx, rsi
0x1800a8476  mov     rcx, r12
0x1800a8479  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a847e  mov     rcx, [r12]; pbstr
0x1800a8482  call    cs:__imp_SysStringLen
0x1800a8488  test    eax, eax
0x1800a848a  jnz     short loc_1800A84AB
0x1800a848c  mov     rcx, rsi; pbstr
0x1800a848f  call    cs:__imp_SysStringLen
0x1800a8495  test    eax, eax
0x1800a8497  jz      short loc_1800A84A3
0x1800a8499  mov     ebx, 8007000Eh
0x1800a849e  jmp     loc_1800A85A5
0x1800a84a3  test    ebx, ebx
0x1800a84a5  js      loc_1800A85A5
0x1800a84ab  lea     r14, [rdi+0A0h]
0x1800a84b2  cmp     qword ptr [r14], 0
0x1800a84b6  jnz     short loc_1800A84ED
0x1800a84b8  xor     r9d, r9d; lpName
0x1800a84bb  xor     r8d, r8d; bInitialState
0x1800a84be  xor     edx, edx; bManualReset
0x1800a84c0  xor     ecx, ecx; lpEventAttributes
0x1800a84c2  call    cs:__imp_CreateEventW
0x1800a84c8  mov     [r14], rax
0x1800a84cb  test    rax, rax
0x1800a84ce  jnz     short loc_1800A84ED
0x1800a84d0  call    cs:__imp_GetLastError
0x1800a84d6  mov     ebx, eax
0x1800a84d8  test    eax, eax
0x1800a84da  jle     short loc_1800A84E5
0x1800a84dc  movzx   ebx, ax
0x1800a84df  or      ebx, 80070000h
0x1800a84e5  test    ebx, ebx
0x1800a84e7  js      loc_1800A85A5
0x1800a84ed  mov     ecx, 8; cb
0x1800a84f2  call    cs:__imp_CoTaskMemAlloc
0x1800a84f8  mov     rsi, rax
0x1800a84fb  test    rax, rax
0x1800a84fe  jz      short loc_1800A8499
0x1800a8500  mov     [rax], r14
0x1800a8503  mov     r14, [rdi+80h]
0x1800a850a  test    r14, r14
0x1800a850d  jnz     short loc_1800A8514
0x1800a850f  xor     r15d, r15d
0x1800a8512  jmp     short loc_1800A8520
0x1800a8514  mov     rcx, r14; pbstr
0x1800a8517  call    cs:__imp_SysStringLen
0x1800a851d  mov     r15d, eax
0x1800a8520  mov     rbx, [r12]
0x1800a8524  test    rbx, rbx
0x1800a8527  jnz     short loc_1800A852D
0x1800a8529  xor     eax, eax
0x1800a852b  jmp     short loc_1800A8536
0x1800a852d  mov     rcx, rbx; pbstr
0x1800a8530  call    cs:__imp_SysStringLen
0x1800a8536  mov     rcx, [rdi+60h]
0x1800a853a  mov     [rsp+88h+var_58], rsi; void *
0x1800a853f  mov     [rsp+88h+lpdwindex], r14; unsigned __int16 *
0x1800a8544  mov     r9d, r15d; unsigned int
0x1800a8547  mov     r8, rbx; unsigned __int16 *
0x1800a854a  mov     edx, eax; unsigned int
0x1800a854c  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a8550  call    ?BackgroundSetTextContext@@YAJPEAUHRECOCONTEXT__@@KPEBGK1P6AJJPEAE@ZPEAX@Z; BackgroundSetTextContext(HRECOCONTEXT__ *,ulong,ushort const *,ulong,ushort const *,long (*)(long,uchar *),void *)
0x1800a8555  mov     ebx, eax
0x1800a8557  test    eax, eax
0x1800a8559  js      short loc_1800A859B
0x1800a855b  mov     [rsp+88h+dwindex], 0
0x1800a8566  lea     r9, [rdi+0A0h]; pHandles
0x1800a856d  lea     rax, [rsp+88h+dwindex]
0x1800a8575  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x1800a857a  mov     edx, 493E0h; dwTimeout
0x1800a857f  xor     ecx, ecx; dwFlags
0x1800a8581  lea     r8d, [rcx+1]; cHandles
0x1800a8585  call    cs:__imp_CoWaitForMultipleHandles
0x1800a858b  test    eax, eax
0x1800a858d  js      loc_1800A8465
0x1800a8593  mov     ebx, [rdi+0BCh]
0x1800a8599  jmp     short loc_1800A85A5
0x1800a859b  mov     rcx, rsi; pv
0x1800a859e  call    cs:__imp_CoTaskMemFree
0x1800a85a4  nop
0x1800a85a5  jmp     short loc_1800A85AE
0x1800a85a7  mov     ebx, [rsp+88h+dwindex]
0x1800a85ae  lea     rcx, [rsp+88h+var_48]; this
0x1800a85b3  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a85b8  mov     eax, ebx
0x1800a85ba  add     rsp, 58h
0x1800a85be  pop     r15
0x1800a85c0  pop     r14
0x1800a85c2  pop     r12
0x1800a85c4  pop     rdi
0x1800a85c5  pop     rsi
0x1800a85c6  pop     rbx
0x1800a85c7  retn
```
