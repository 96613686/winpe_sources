# CInkRecoContext::IsStringSupported(ushort *,short *)

- ea: `0x1800a6160`
- end: `0x1800a6330`
- name: `?IsStringSupported@CInkRecoContext@@UEAAJPEAGPEAF@Z`
- size: `464`
- prototype: `int(CInkRecoContext *__hidden this, unsigned __int16 *, __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180083ff4`
- `0x180086540`
- `0x1800a6160`
- `0x1800c4560`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a628a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a628a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a61ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a61ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a623a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a6263`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a623a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a6263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a621c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a621c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a62ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a62ec`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a62be`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a62be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::IsStringSupported(CInkRecoContext *this, unsigned __int16 *a2, __int16 *a3)
{
  __int64 v6; // rdx
  int IsStringSupported; // ebx
  HANDLE *v9; // r14
  HANDLE EventW; // rax
  _QWORD *v11; // rax
  void *v12; // rsi
  UINT v13; // eax
  int (*v14)(int, unsigned __int8 *); // r9
  ULONG v15; // eax
  HRESULT v16; // eax
  _BYTE v17[16]; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v17, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  if ( !a3 )
  {
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
    return 2147942487LL;
  }
  try
  {
    IsStringSupported = 0;
    if ( !*((_QWORD *)this + 12) )
    {
      LOBYTE(v6) = 1;
      IsStringSupported = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))(
                            (char *)this - 16,
                            v6);
    }
    v9 = (HANDLE *)((char *)this + 160);
    if ( *((_QWORD *)this + 20) || (EventW = CreateEventW(0, 0, 0, 0), (*v9 = EventW) != 0) )
    {
      if ( IsStringSupported < 0 )
        goto LABEL_26;
      CInkRecognizer::InternalUpdateUserDict(*((CInkRecognizer **)this + 13), 0);
      v11 = CoTaskMemAlloc(8u);
      v12 = v11;
      if ( !v11 )
      {
        IsStringSupported = -2147024882;
        goto LABEL_26;
      }
      *v11 = v9;
      v13 = SysStringLen(a2);
      IsStringSupported = BackgroundIsStringSupported(*(_QWORD **)(*((_QWORD *)this + 12) + 16LL), v13, a2, v14, v12);
      if ( IsStringSupported == -2147220940 )
      {
        v15 = SysStringLen(a2);
        v16 = ::IsStringSupported(*(HRECOCONTEXT *)(*((_QWORD *)this + 12) + 16LL), v15, a2);
        IsStringSupported = v16;
        if ( v16 >= 0 )
        {
          *((_DWORD *)this + 47) = v16;
          SetEvent(*v9);
        }
        CoTaskMemFree(v12);
        v12 = 0;
      }
      if ( IsStringSupported < 0 )
      {
        if ( v12 )
          CoTaskMemFree(v12);
        goto LABEL_26;
      }
      dwindex = 0;
      IsStringSupported = CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex);
      if ( IsStringSupported >= 0 )
      {
        *a3 = (*((_DWORD *)this + 47) != 0) - 1;
        goto LABEL_26;
      }
    }
    IsStringSupported = -2147418113;
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    IsStringSupported = dwindex;
  }
LABEL_26:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v17);
  return (unsigned int)IsStringSupported;
}

```

## disassembly

```asm
0x1800a6160  mov     [rsp+arg_8], rbx
0x1800a6165  mov     [rsp+arg_10], rsi
0x1800a616a  push    rdi
0x1800a616b  push    r12
0x1800a616d  push    r13
0x1800a616f  push    r14
0x1800a6171  push    r15
0x1800a6173  sub     rsp, 40h
0x1800a6177  mov     r13, r8
0x1800a617a  mov     r12, rdx
0x1800a617d  mov     rdi, rcx
0x1800a6180  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a6187  lea     rcx, [rsp+68h+var_38]; this
0x1800a618c  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a6191  nop
0x1800a6192  test    r13, r13
0x1800a6195  jz      loc_1800A6307
0x1800a619b  test    r12, r12
0x1800a619e  jnz     short loc_1800A61B4
0x1800a61a0  lea     rcx, [rsp+68h+var_38]; this
0x1800a61a5  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a61aa  mov     eax, 80070057h
0x1800a61af  jmp     loc_1800A6316
0x1800a61b4  xor     ebx, ebx
0x1800a61b6  lea     rcx, [rdi-10h]
0x1800a61ba  lea     r15d, [rbx+1]
0x1800a61be  cmp     [rcx+70h], rbx
0x1800a61c2  jnz     short loc_1800A61D5
0x1800a61c4  mov     rax, [rcx]
0x1800a61c7  mov     dl, r15b
0x1800a61ca  mov     rax, [rax+48h]
0x1800a61ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a61d3  mov     ebx, eax
0x1800a61d5  lea     r14, [rdi+0A0h]
0x1800a61dc  cmp     qword ptr [r14], 0
0x1800a61e0  jnz     short loc_1800A6204
0x1800a61e2  xor     r9d, r9d; lpName
0x1800a61e5  xor     r8d, r8d; bInitialState
0x1800a61e8  xor     edx, edx; bManualReset
0x1800a61ea  xor     ecx, ecx; lpEventAttributes
0x1800a61ec  call    cs:__imp_CreateEventW
0x1800a61f2  mov     [r14], rax
0x1800a61f5  test    rax, rax
0x1800a61f8  jnz     short loc_1800A6204
0x1800a61fa  mov     ebx, 8000FFFFh
0x1800a61ff  jmp     loc_1800A62F3
0x1800a6204  test    ebx, ebx
0x1800a6206  js      loc_1800A62F3
0x1800a620c  xor     edx, edx; bool
0x1800a620e  mov     rcx, [rdi+68h]; this
0x1800a6212  call    ?InternalUpdateUserDict@CInkRecognizer@@IEAAJ_N@Z; CInkRecognizer::InternalUpdateUserDict(bool)
0x1800a6217  mov     ecx, 8; cb
0x1800a621c  call    cs:__imp_CoTaskMemAlloc
0x1800a6222  mov     rsi, rax
0x1800a6225  test    rax, rax
0x1800a6228  jnz     short loc_1800A6234
0x1800a622a  mov     ebx, 8007000Eh
0x1800a622f  jmp     loc_1800A62F3
0x1800a6234  mov     [rax], r14
0x1800a6237  mov     rcx, r12; pbstr
0x1800a623a  call    cs:__imp_SysStringLen
0x1800a6240  mov     rcx, [rdi+60h]
0x1800a6244  mov     [rsp+68h+lpdwindex], rsi; void *
0x1800a6249  mov     r8, r12; unsigned __int16 *
0x1800a624c  mov     edx, eax; unsigned int
0x1800a624e  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a6252  call    ?BackgroundIsStringSupported@@YAJPEAUHRECOCONTEXT__@@KPEBGP6AJJPEAE@ZPEAX@Z; BackgroundIsStringSupported(HRECOCONTEXT__ *,ulong,ushort const *,long (*)(long,uchar *),void *)
0x1800a6257  mov     ebx, eax
0x1800a6259  cmp     eax, 80040234h
0x1800a625e  jnz     short loc_1800A629B
0x1800a6260  mov     rcx, r12; pbstr
0x1800a6263  call    cs:__imp_SysStringLen
0x1800a6269  mov     rcx, [rdi+60h]
0x1800a626d  mov     r8, r12; pwcString
0x1800a6270  mov     edx, eax; wcString
0x1800a6272  mov     rcx, [rcx+10h]; hrc
0x1800a6276  call    IsStringSupported
0x1800a627b  mov     ebx, eax
0x1800a627d  test    eax, eax
0x1800a627f  js      short loc_1800A6290
0x1800a6281  mov     [rdi+0BCh], eax
0x1800a6287  mov     rcx, [r14]; hEvent
0x1800a628a  call    cs:__imp_SetEvent
0x1800a6290  mov     rcx, rsi; pv
0x1800a6293  call    cs:__imp_CoTaskMemFree
0x1800a6299  xor     esi, esi
0x1800a629b  test    ebx, ebx
0x1800a629d  js      short loc_1800A62E4
0x1800a629f  mov     [rsp+68h+dwindex], 0
0x1800a62a7  lea     rax, [rsp+68h+dwindex]
0x1800a62ac  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800a62b1  mov     r9, r14; pHandles
0x1800a62b4  mov     r8d, r15d; cHandles
0x1800a62b7  mov     edx, 493E0h; dwTimeout
0x1800a62bc  xor     ecx, ecx; dwFlags
0x1800a62be  call    cs:__imp_CoWaitForMultipleHandles
0x1800a62c4  mov     ebx, eax
0x1800a62c6  test    eax, eax
0x1800a62c8  js      loc_1800A61FA
0x1800a62ce  xor     eax, eax
0x1800a62d0  cmp     [rdi+0BCh], eax
0x1800a62d6  setnz   al
0x1800a62d9  sub     ax, r15w
0x1800a62dd  mov     [r13+0], ax
0x1800a62e2  jmp     short loc_1800A62F3
0x1800a62e4  test    rsi, rsi
0x1800a62e7  jz      short loc_1800A62F3
0x1800a62e9  mov     rcx, rsi; pv
0x1800a62ec  call    cs:__imp_CoTaskMemFree
0x1800a62f2  nop
0x1800a62f3  jmp     short loc_1800A62F9
0x1800a62f5  mov     ebx, [rsp+68h+dwindex]
0x1800a62f9  lea     rcx, [rsp+68h+var_38]; this
0x1800a62fe  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a6303  mov     eax, ebx
0x1800a6305  jmp     short loc_1800A6316
0x1800a6307  lea     rcx, [rsp+68h+var_38]; this
0x1800a630c  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a6311  mov     eax, 80004003h
0x1800a6316  lea     r11, [rsp+68h+var_28]
0x1800a631b  mov     rbx, [r11+38h]
0x1800a631f  mov     rsi, [r11+40h]
0x1800a6323  mov     rsp, r11
0x1800a6326  pop     r15
0x1800a6328  pop     r14
0x1800a632a  pop     r13
0x1800a632c  pop     r12
0x1800a632e  pop     rdi
0x1800a632f  retn
```
