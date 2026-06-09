# CInkRecoContext::put_Constraint(ushort *)

- ea: `0x1800a7c80`
- end: `0x1800a7ebb`
- name: `?put_Constraint@CInkRecoContext@@UEAAJPEAG@Z`
- size: `571`
- prototype: `int(CInkRecoContext *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180084e64`
- `0x1800a32a4`
- `0x1800a32e8`
- `0x1800a7c80`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7d18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7d0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7cde`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7d7c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7e64`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7e94`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7cde`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7d7c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7e64`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7e94`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7cbb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7d62`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7d6f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7dc2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7e4a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7e57`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7cbb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7d62`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7d6f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7dc2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7e4a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7e7f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7e0f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7e0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CInkRecoContext::put_Constraint(CInkRecoContext *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
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
  _BYTE v17[40]; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+60h] [rbp+8h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp+10h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v17, (struct _RTL_CRITICAL_SECTION *)this + 4);
  pbstr = 0;
  if ( !a2 && SysStringLen(0) )
  {
    v5 = -2147024809;
LABEL_6:
    SysFreeString(0);
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
    return v5;
  }
  v6 = 0;
  if ( *((_QWORD *)this + 26) )
  {
    v5 = -2147220937;
    goto LABEL_6;
  }
  v8 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) )
    goto LABEL_33;
  EventW = CreateEventW(0, 0, 0, 0);
  *v8 = EventW;
  if ( EventW )
    goto LABEL_33;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_33:
    if ( !*((_QWORD *)this + 5) )
    {
      LOBYTE(v4) = 1;
      v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 9) + 72LL))((char *)this - 72, v4);
    }
  }
  ATL::CComBSTR::operator=(&pbstr, a2);
  v11 = pbstr;
  if ( !SysStringLen(pbstr) && SysStringLen(a2) )
    goto LABEL_16;
  if ( v6 >= 0 )
  {
    v12 = CoTaskMemAlloc(8u);
    v13 = v12;
    if ( v12 )
    {
      *v12 = v8;
      v14 = SysStringLen(v11);
      v6 = BackgroundSetFactoidOrConstraint(*(_QWORD **)(*((_QWORD *)this + 5) + 16LL), v14, v11, v15, v13, 0);
      if ( v6 < 0 )
      {
        CoTaskMemFree(v13);
      }
      else
      {
        dwindex = 0;
        if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 13, &dwindex) >= 0 )
        {
          v6 = *((_DWORD *)this + 33);
          if ( v6 >= 0 )
          {
            v16 = (char *)this + 96;
            if ( v11 )
            {
              ATL::CComBSTR::operator=(v16, &pbstr);
              if ( !SysStringLen(*((BSTR *)this + 12)) && SysStringLen(v11) )
              {
LABEL_16:
                SysFreeString(v11);
                CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
                return 2147942414LL;
              }
            }
            else
            {
              ATL::CComBSTR::operator=(v16, 0);
            }
          }
        }
        else
        {
          v6 = -2147418113;
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
  SysFreeString(v11);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a7c80  mov     [rsp+arg_10], rbx
0x1800a7c85  mov     [rsp+arg_18], rsi
0x1800a7c8a  push    rdi
0x1800a7c8b  push    r14
0x1800a7c8d  push    r15
0x1800a7c8f  sub     rsp, 40h
0x1800a7c93  mov     r14, rdx
0x1800a7c96  mov     rdi, rcx
0x1800a7c99  lea     rdx, [rcx+0A0h]; struct _RTL_CRITICAL_SECTION *
0x1800a7ca0  lea     rcx, [rsp+58h+var_28]; this
0x1800a7ca5  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a7caa  nop
0x1800a7cab  mov     [rsp+58h+pbstr], 0
0x1800a7cb4  test    r14, r14
0x1800a7cb7  jnz     short loc_1800A7CCC
0x1800a7cb9  xor     ecx, ecx; pbstr
0x1800a7cbb  call    cs:__imp_SysStringLen
0x1800a7cc1  test    eax, eax
0x1800a7cc3  jz      short loc_1800A7CCC
0x1800a7cc5  mov     ebx, 80070057h
0x1800a7cca  jmp     short loc_1800A7CDC
0x1800a7ccc  xor     esi, esi
0x1800a7cce  cmp     [rdi+0D0h], rsi
0x1800a7cd5  jz      short loc_1800A7CF6
0x1800a7cd7  mov     ebx, 80040237h
0x1800a7cdc  xor     ecx, ecx; bstrString
0x1800a7cde  call    cs:__imp_SysFreeString
0x1800a7ce4  nop
0x1800a7ce5  lea     rcx, [rsp+58h+var_28]; this
0x1800a7cea  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7cef  mov     eax, ebx
0x1800a7cf1  jmp     loc_1800A7EA7
0x1800a7cf6  lea     r15, [rdi+68h]
0x1800a7cfa  cmp     qword ptr [r15], 0
0x1800a7cfe  jnz     short loc_1800A7D31
0x1800a7d00  xor     r9d, r9d; lpName
0x1800a7d03  xor     r8d, r8d; bInitialState
0x1800a7d06  xor     edx, edx; bManualReset
0x1800a7d08  xor     ecx, ecx; lpEventAttributes
0x1800a7d0a  call    cs:__imp_CreateEventW
0x1800a7d10  mov     [r15], rax
0x1800a7d13  test    rax, rax
0x1800a7d16  jnz     short loc_1800A7D31
0x1800a7d18  call    cs:__imp_GetLastError
0x1800a7d1e  mov     esi, eax
0x1800a7d20  test    eax, eax
0x1800a7d22  jle     short loc_1800A7D2D
0x1800a7d24  movzx   esi, ax
0x1800a7d27  or      esi, 80070000h
0x1800a7d2d  test    esi, esi
0x1800a7d2f  js      short loc_1800A7D4D
0x1800a7d31  cmp     qword ptr [rdi+28h], 0
0x1800a7d36  jnz     short loc_1800A7D4D
0x1800a7d38  mov     rax, [rdi-48h]
0x1800a7d3c  mov     dl, 1
0x1800a7d3e  lea     rcx, [rdi-48h]
0x1800a7d42  mov     rax, [rax+48h]
0x1800a7d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7d4b  mov     esi, eax
0x1800a7d4d  mov     rdx, r14
0x1800a7d50  lea     rcx, [rsp+58h+pbstr]
0x1800a7d55  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a7d5a  mov     rbx, [rsp+58h+pbstr]
0x1800a7d5f  mov     rcx, rbx; pbstr
0x1800a7d62  call    cs:__imp_SysStringLen
0x1800a7d68  test    eax, eax
0x1800a7d6a  jnz     short loc_1800A7D97
0x1800a7d6c  mov     rcx, r14; pbstr
0x1800a7d6f  call    cs:__imp_SysStringLen
0x1800a7d75  test    eax, eax
0x1800a7d77  jz      short loc_1800A7D97
0x1800a7d79  mov     rcx, rbx; bstrString
0x1800a7d7c  call    cs:__imp_SysFreeString
0x1800a7d82  nop
0x1800a7d83  lea     rcx, [rsp+58h+var_28]; this
0x1800a7d88  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7d8d  mov     eax, 8007000Eh
0x1800a7d92  jmp     loc_1800A7EA7
0x1800a7d97  test    esi, esi
0x1800a7d99  js      loc_1800A7E86
0x1800a7d9f  mov     ecx, 8; cb
0x1800a7da4  call    cs:__imp_CoTaskMemAlloc
0x1800a7daa  mov     r14, rax
0x1800a7dad  test    rax, rax
0x1800a7db0  jnz     short loc_1800A7DBC
0x1800a7db2  mov     esi, 8007000Eh
0x1800a7db7  jmp     loc_1800A7E86
0x1800a7dbc  mov     [rax], r15
0x1800a7dbf  mov     rcx, rbx; pbstr
0x1800a7dc2  call    cs:__imp_SysStringLen
0x1800a7dc8  mov     rcx, [rdi+28h]
0x1800a7dcc  mov     [rsp+58h+var_30], 0; bool
0x1800a7dd1  mov     [rsp+58h+lpdwindex], r14; void *
0x1800a7dd6  mov     r8, rbx; unsigned __int16 *
0x1800a7dd9  mov     edx, eax; unsigned int
0x1800a7ddb  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a7ddf  call    ?BackgroundSetFactoidOrConstraint@@YAJPEAUHRECOCONTEXT__@@KPEBGP6AJJPEAE@ZPEAX_N@Z; BackgroundSetFactoidOrConstraint(HRECOCONTEXT__ *,ulong,ushort const *,long (*)(long,uchar *),void *,bool)
0x1800a7de4  mov     esi, eax
0x1800a7de6  test    eax, eax
0x1800a7de8  js      loc_1800A7E7C
0x1800a7dee  mov     [rsp+58h+dwindex], 0
0x1800a7df6  lea     r9, [rdi+68h]; pHandles
0x1800a7dfa  lea     rax, [rsp+58h+dwindex]
0x1800a7dff  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800a7e04  mov     edx, 493E0h; dwTimeout
0x1800a7e09  xor     ecx, ecx; dwFlags
0x1800a7e0b  lea     r8d, [rcx+1]; cHandles
0x1800a7e0f  call    cs:__imp_CoWaitForMultipleHandles
0x1800a7e15  test    eax, eax
0x1800a7e17  jns     short loc_1800A7E20
0x1800a7e19  mov     esi, 8000FFFFh
0x1800a7e1e  jmp     short loc_1800A7E86
0x1800a7e20  mov     esi, [rdi+84h]
0x1800a7e26  test    esi, esi
0x1800a7e28  js      short loc_1800A7E86
0x1800a7e2a  lea     rcx, [rdi+60h]
0x1800a7e2e  test    rbx, rbx
0x1800a7e31  jnz     short loc_1800A7E3C
0x1800a7e33  xor     edx, edx
0x1800a7e35  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800a7e3a  jmp     short loc_1800A7E86
0x1800a7e3c  lea     rdx, [rsp+58h+pbstr]
0x1800a7e41  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800a7e46  mov     rcx, [rdi+60h]; pbstr
0x1800a7e4a  call    cs:__imp_SysStringLen
0x1800a7e50  test    eax, eax
0x1800a7e52  jnz     short loc_1800A7E86
0x1800a7e54  mov     rcx, rbx; pbstr
0x1800a7e57  call    cs:__imp_SysStringLen
0x1800a7e5d  test    eax, eax
0x1800a7e5f  jz      short loc_1800A7E86
0x1800a7e61  mov     rcx, rbx; bstrString
0x1800a7e64  call    cs:__imp_SysFreeString
0x1800a7e6a  nop
0x1800a7e6b  lea     rcx, [rsp+58h+var_28]; this
0x1800a7e70  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7e75  mov     eax, 8007000Eh
0x1800a7e7a  jmp     short loc_1800A7EA7
0x1800a7e7c  mov     rcx, r14; pv
0x1800a7e7f  call    cs:__imp_CoTaskMemFree
0x1800a7e85  nop
0x1800a7e86  jmp     short loc_1800A7E91
0x1800a7e88  mov     rbx, [rsp+58h+pbstr]
0x1800a7e8d  mov     esi, [rsp+58h+dwindex]
0x1800a7e91  mov     rcx, rbx; bstrString
0x1800a7e94  call    cs:__imp_SysFreeString
0x1800a7e9a  nop
0x1800a7e9b  lea     rcx, [rsp+58h+var_28]; this
0x1800a7ea0  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7ea5  mov     eax, esi
0x1800a7ea7  mov     rbx, [rsp+58h+arg_10]
0x1800a7eac  mov     rsi, [rsp+58h+arg_18]
0x1800a7eb1  add     rsp, 40h
0x1800a7eb5  pop     r15
0x1800a7eb7  pop     r14
0x1800a7eb9  pop     rdi
0x1800a7eba  retn
```
