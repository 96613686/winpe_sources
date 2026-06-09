# CInkRecoContext::put_SuffixText(ushort *)

- ea: `0x1800a87c0`
- end: `0x1800a898a`
- name: `?put_SuffixText@CInkRecoContext@@UEAAJPEAG@Z`
- size: `458`
- prototype: `int(CInkRecoContext *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180085060`
- `0x1800a32e8`
- `0x1800a87c0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8897`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8889`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8889`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8849`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8856`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a88da`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a88f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8849`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a8856`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a88da`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a88f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a88b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a88b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a895b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a895b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8942`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8942`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::put_SuffixText(CInkRecoContext *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  BSTR *v6; // r15
  _QWORD *v7; // r14
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // rax
  void *v11; // rsi
  const unsigned __int16 *v12; // r14
  UINT v13; // r15d
  const unsigned __int16 *v14; // rbx
  UINT v15; // eax
  int (*v17)(int, unsigned __int8 *); // [rsp+28h] [rbp-40h]
  _BYTE v18[16]; // [rsp+40h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF

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
    v6 = (BSTR *)((char *)this + 128);
    ATL::CComBSTR::operator=((char *)this + 128, a2);
    if ( !SysStringLen(*((BSTR *)this + 16)) && SysStringLen(a2) )
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
      v12 = *v6;
      if ( *v6 )
        v13 = SysStringLen(*v6);
      else
        v13 = 0;
      v14 = (const unsigned __int16 *)*((_QWORD *)this + 15);
      if ( v14 )
        v15 = SysStringLen(*((BSTR *)this + 15));
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
0x1800a87c0  mov     [rsp+arg_8], rbx
0x1800a87c5  mov     [rsp+arg_10], rsi
0x1800a87ca  push    rdi
0x1800a87cb  push    r14
0x1800a87cd  push    r15
0x1800a87cf  sub     rsp, 50h
0x1800a87d3  mov     rsi, rdx
0x1800a87d6  mov     rdi, rcx
0x1800a87d9  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a87e0  lea     rcx, [rsp+68h+var_28]; this
0x1800a87e5  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a87ea  nop
0x1800a87eb  xor     ebx, ebx
0x1800a87ed  lea     rcx, [rdi-10h]
0x1800a87f1  cmp     [rcx+118h], rbx
0x1800a87f8  jz      short loc_1800A8804
0x1800a87fa  mov     ebx, 80040237h
0x1800a87ff  jmp     loc_1800A8968
0x1800a8804  cmp     qword ptr [rdi+60h], 0
0x1800a8809  jnz     short loc_1800A8834
0x1800a880b  mov     rax, [rcx]
0x1800a880e  mov     dl, 1
0x1800a8810  mov     rax, [rax+48h]
0x1800a8814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8819  mov     ebx, eax
0x1800a881b  test    eax, eax
0x1800a881d  js      loc_1800A8962
0x1800a8823  cmp     qword ptr [rdi+60h], 0
0x1800a8828  jnz     short loc_1800A8834
0x1800a882a  mov     ebx, 8000FFFFh
0x1800a882f  jmp     loc_1800A8962
0x1800a8834  lea     r15, [rdi+80h]
0x1800a883b  mov     rdx, rsi
0x1800a883e  mov     rcx, r15
0x1800a8841  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a8846  mov     rcx, [r15]; pbstr
0x1800a8849  call    cs:__imp_SysStringLen
0x1800a884f  test    eax, eax
0x1800a8851  jnz     short loc_1800A8872
0x1800a8853  mov     rcx, rsi; pbstr
0x1800a8856  call    cs:__imp_SysStringLen
0x1800a885c  test    eax, eax
0x1800a885e  jz      short loc_1800A886A
0x1800a8860  mov     ebx, 8007000Eh
0x1800a8865  jmp     loc_1800A8962
0x1800a886a  test    ebx, ebx
0x1800a886c  js      loc_1800A8962
0x1800a8872  lea     r14, [rdi+0A0h]
0x1800a8879  cmp     qword ptr [r14], 0
0x1800a887d  jnz     short loc_1800A88B4
0x1800a887f  xor     r9d, r9d; lpName
0x1800a8882  xor     r8d, r8d; bInitialState
0x1800a8885  xor     edx, edx; bManualReset
0x1800a8887  xor     ecx, ecx; lpEventAttributes
0x1800a8889  call    cs:__imp_CreateEventW
0x1800a888f  mov     [r14], rax
0x1800a8892  test    rax, rax
0x1800a8895  jnz     short loc_1800A88B4
0x1800a8897  call    cs:__imp_GetLastError
0x1800a889d  mov     ebx, eax
0x1800a889f  test    eax, eax
0x1800a88a1  jle     short loc_1800A88AC
0x1800a88a3  movzx   ebx, ax
0x1800a88a6  or      ebx, 80070000h
0x1800a88ac  test    ebx, ebx
0x1800a88ae  js      loc_1800A8962
0x1800a88b4  mov     ecx, 8; cb
0x1800a88b9  call    cs:__imp_CoTaskMemAlloc
0x1800a88bf  mov     rsi, rax
0x1800a88c2  test    rax, rax
0x1800a88c5  jz      short loc_1800A8860
0x1800a88c7  mov     [rax], r14
0x1800a88ca  mov     r14, [r15]
0x1800a88cd  test    r14, r14
0x1800a88d0  jnz     short loc_1800A88D7
0x1800a88d2  xor     r15d, r15d
0x1800a88d5  jmp     short loc_1800A88E3
0x1800a88d7  mov     rcx, r14; pbstr
0x1800a88da  call    cs:__imp_SysStringLen
0x1800a88e0  mov     r15d, eax
0x1800a88e3  mov     rbx, [rdi+78h]
0x1800a88e7  test    rbx, rbx
0x1800a88ea  jnz     short loc_1800A88F0
0x1800a88ec  xor     eax, eax
0x1800a88ee  jmp     short loc_1800A88F9
0x1800a88f0  mov     rcx, rbx; pbstr
0x1800a88f3  call    cs:__imp_SysStringLen
0x1800a88f9  mov     rcx, [rdi+60h]
0x1800a88fd  mov     [rsp+68h+var_38], rsi; void *
0x1800a8902  mov     [rsp+68h+lpdwindex], r14; unsigned __int16 *
0x1800a8907  mov     r9d, r15d; unsigned int
0x1800a890a  mov     r8, rbx; unsigned __int16 *
0x1800a890d  mov     edx, eax; unsigned int
0x1800a890f  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a8913  call    ?BackgroundSetTextContext@@YAJPEAUHRECOCONTEXT__@@KPEBGK1P6AJJPEAE@ZPEAX@Z; BackgroundSetTextContext(HRECOCONTEXT__ *,ulong,ushort const *,ulong,ushort const *,long (*)(long,uchar *),void *)
0x1800a8918  mov     ebx, eax
0x1800a891a  test    eax, eax
0x1800a891c  js      short loc_1800A8958
0x1800a891e  mov     [rsp+68h+dwindex], 0
0x1800a8926  lea     r9, [rdi+0A0h]; pHandles
0x1800a892d  lea     rax, [rsp+68h+dwindex]
0x1800a8932  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800a8937  mov     edx, 493E0h; dwTimeout
0x1800a893c  xor     ecx, ecx; dwFlags
0x1800a893e  lea     r8d, [rcx+1]; cHandles
0x1800a8942  call    cs:__imp_CoWaitForMultipleHandles
0x1800a8948  test    eax, eax
0x1800a894a  js      loc_1800A882A
0x1800a8950  mov     ebx, [rdi+0BCh]
0x1800a8956  jmp     short loc_1800A8962
0x1800a8958  mov     rcx, rsi; pv
0x1800a895b  call    cs:__imp_CoTaskMemFree
0x1800a8961  nop
0x1800a8962  jmp     short loc_1800A8968
0x1800a8964  mov     ebx, [rsp+68h+dwindex]
0x1800a8968  lea     rcx, [rsp+68h+var_28]; this
0x1800a896d  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8972  mov     eax, ebx
0x1800a8974  lea     r11, [rsp+68h+var_18]
0x1800a8979  mov     rbx, [r11+28h]
0x1800a897d  mov     rsi, [r11+30h]
0x1800a8981  mov     rsp, r11
0x1800a8984  pop     r15
0x1800a8986  pop     r14
0x1800a8988  pop     rdi
0x1800a8989  retn
```
