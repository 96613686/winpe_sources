# CWMIBroker::ConnectToNamespace(IWbemServices * *)

- ea: `0x1400030f8`
- end: `0x14000331a`
- name: `?ConnectToNamespace@CWMIBroker@@AEAAJPEAPEAUIWbemServices@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(const OLECHAR **this, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000304c`
- `0x1400037f0`

## callees

- `0x140002ee4`
- `0x1400030f8`
- `0x140004c04`
- `0x1400062f8`
- `0x140017010`

## import_xrefs

- `msvcrt!wcsstr` at `0x14000320d`
- `msvcrt!wcsstr` at `0x140003262`
- `msvcrt!wcsstr` at `0x14000320d`
- `msvcrt!wcsstr` at `0x140003262`
- `wbemcomn!GetMemLogObject` at `0x14000321c`
- `wbemcomn!GetMemLogObject` at `0x14000326d`
- `wbemcomn!GetMemLogObject` at `0x14000321c`
- `wbemcomn!GetMemLogObject` at `0x14000326d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003228`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003279`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003228`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003279`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000314d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000314d`
- `OLEAUT32!__imp_SysAllocString` at `0x140003169`
- `OLEAUT32!__imp_SysAllocString` at `0x140003169`

## pseudocode

```c
__int64 __fastcall CWMIBroker::ConnectToNamespace(const OLECHAR **this, struct IUnknown **a2)
{
  HRESULT v5; // eax
  int v6; // edi
  LPVOID v7; // rbx
  const wchar_t *v8; // r14
  unsigned int v9; // edx
  unsigned int v10; // r8d
  unsigned __int16 *v11; // r9
  CMemoryLog *v12; // rax
  int v13; // r8d
  _QWORD *v14; // rcx
  int v15; // edx
  CMemoryLog *MemLogObject; // rax
  struct IUnknown *v17; // [rsp+98h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v19; // [rsp+A8h] [rbp+48h] BYREF

  if ( !a2 )
    return 2147749896LL;
  v17 = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v6 = v5;
  v7 = ppv;
  if ( v5 < 0 )
  {
    (*(void (__fastcall **)(const OLECHAR **, _QWORD))*this)(this, (unsigned int)v5);
    goto LABEL_23;
  }
  v8 = SysAllocString(this[1]);
  if ( !v8 )
    v6 = -2147217402;
  v19 = v8;
  if ( v6 < 0 )
    goto LABEL_20;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v8, 0, 0);
  if ( v6 < 0 )
  {
    if ( wcsstr(v8, L"MS_") )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v15 = 12;
LABEL_19:
      WPP_SF_SD(v14[2], v15, v13, (_DWORD)v8, v6);
      goto LABEL_21;
    }
LABEL_20:
    (*(void (__fastcall **)(const OLECHAR **, _QWORD))*this)(this, (unsigned int)v6);
    goto LABEL_21;
  }
  v6 = WbemSetProxyBlanket(v17, v9, v10, v11, 0, 0, 0, 0, (bool)&v17);
  if ( v6 < 0 )
  {
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
    v17 = 0;
    if ( wcsstr(v8, L"MS_") )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, -1);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v15 = 11;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
LABEL_21:
  CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v19);
LABEL_23:
  *a2 = v17;
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400030f8  mov     [rsp-28h+arg_0], rbx
0x1400030fd  push    rbp
0x1400030fe  push    rsi
0x1400030ff  push    rdi
0x140003100  push    r14
0x140003102  push    r15
0x140003104  mov     rbp, rsp
0x140003107  sub     rsp, 60h
0x14000310b  mov     r15, rdx
0x14000310e  mov     rsi, rcx
0x140003111  test    rdx, rdx
0x140003114  jnz     short loc_140003120
0x140003116  mov     eax, 80041008h
0x14000311b  jmp     loc_140003306
0x140003120  mov     [rbp+arg_8], 0
0x140003128  mov     [rbp+arg_10], 0
0x140003130  lea     rax, [rbp+arg_10]
0x140003134  mov     [rsp+60h+ppv], rax; ppv
0x140003139  lea     r9, IID_IWbemLocator; riid
0x140003140  xor     edx, edx; pUnkOuter
0x140003142  lea     r8d, [rdx+1]; dwClsContext
0x140003146  lea     rcx, CLSID_WbemLocator; rclsid
0x14000314d  call    cs:__imp_CoCreateInstance
0x140003153  mov     edi, eax
0x140003155  mov     rbx, [rbp+arg_10]
0x140003159  mov     [rbp+var_10], rbx
0x14000315d  test    eax, eax
0x14000315f  js      loc_1400032D1
0x140003165  mov     rcx, [rsi+8]; psz
0x140003169  call    cs:__imp_SysAllocString
0x14000316f  mov     r14, rax
0x140003172  mov     eax, 80041006h
0x140003177  test    r14, r14
0x14000317a  cmovz   edi, eax
0x14000317d  mov     [rbp+arg_18], r14
0x140003181  test    edi, edi
0x140003183  js      loc_1400032B5
0x140003189  mov     rcx, [rbp+arg_10]
0x14000318d  mov     rdx, [rcx]
0x140003190  mov     rax, [rdx+18h]
0x140003194  lea     rdx, [rbp+arg_8]
0x140003198  mov     qword ptr [rsp+60h+var_20], rdx; bool
0x14000319d  mov     qword ptr [rsp+60h+var_28], 0; unsigned int
0x1400031a6  mov     [rsp+60h+var_30], 0; void *
0x1400031af  mov     [rsp+60h+var_38], 0; unsigned int
0x1400031b7  mov     [rsp+60h+ppv], 0; unsigned int
0x1400031c0  xor     r9d, r9d
0x1400031c3  xor     r8d, r8d
0x1400031c6  mov     rdx, r14
0x1400031c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031ce  mov     edi, eax
0x1400031d0  test    eax, eax
0x1400031d2  js      loc_140003258
0x1400031d8  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1400031dc  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x1400031e1  mov     edi, eax
0x1400031e3  test    eax, eax
0x1400031e5  jns     loc_1400032C6
0x1400031eb  mov     rcx, [rbp+arg_8]
0x1400031ef  mov     rax, [rcx]
0x1400031f2  mov     rax, [rax+10h]
0x1400031f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031fb  mov     [rbp+arg_8], 0
0x140003203  lea     rdx, aMs; "MS_"
0x14000320a  mov     rcx, r14; Str
0x14000320d  call    cs:__imp_wcsstr
0x140003213  test    rax, rax
0x140003216  jz      loc_1400032B5
0x14000321c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140003222  or      edx, 0FFFFFFFFh
0x140003225  mov     rcx, rax
0x140003228  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000322e  lea     rax, WPP_GLOBAL_Control
0x140003235  mov     rcx, cs:WPP_GLOBAL_Control
0x14000323c  cmp     rcx, rax
0x14000323f  jz      loc_1400032C6
0x140003245  test    byte ptr [rcx+1Ch], 1
0x140003249  jz      short loc_1400032C6
0x14000324b  cmp     byte ptr [rcx+19h], 2
0x14000324f  jb      short loc_1400032C6
0x140003251  mov     edx, 0Bh
0x140003256  jmp     short loc_1400032A3
0x140003258  lea     rdx, aMs; "MS_"
0x14000325f  mov     rcx, r14; Str
0x140003262  call    cs:__imp_wcsstr
0x140003268  test    rax, rax
0x14000326b  jz      short loc_1400032B5
0x14000326d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140003273  or      edx, 0FFFFFFFFh
0x140003276  mov     rcx, rax
0x140003279  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000327f  lea     rax, WPP_GLOBAL_Control
0x140003286  mov     rcx, cs:WPP_GLOBAL_Control
0x14000328d  cmp     rcx, rax
0x140003290  jz      short loc_1400032C6
0x140003292  test    byte ptr [rcx+1Ch], 1
0x140003296  jz      short loc_1400032C6
0x140003298  cmp     byte ptr [rcx+19h], 2
0x14000329c  jb      short loc_1400032C6
0x14000329e  mov     edx, 0Ch
0x1400032a3  mov     dword ptr [rsp+60h+ppv], edi
0x1400032a7  mov     r9, r14
0x1400032aa  mov     rcx, [rcx+10h]
0x1400032ae  call    WPP_SF_SD
0x1400032b3  jmp     short loc_1400032C6
0x1400032b5  mov     rax, [rsi]
0x1400032b8  mov     edx, edi
0x1400032ba  mov     rcx, rsi
0x1400032bd  mov     rax, [rax]
0x1400032c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c5  nop
0x1400032c6  lea     rcx, [rbp+arg_18]; this
0x1400032ca  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1400032cf  jmp     short loc_1400032E1
0x1400032d1  mov     rax, [rsi]
0x1400032d4  mov     edx, edi
0x1400032d6  mov     rcx, rsi
0x1400032d9  mov     rax, [rax]
0x1400032dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032e1  mov     rax, [rbp+arg_8]
0x1400032e5  mov     [r15], rax
0x1400032e8  test    rbx, rbx
0x1400032eb  jz      short loc_1400032FC
0x1400032ed  mov     rax, [rbx]
0x1400032f0  mov     rcx, rbx
0x1400032f3  mov     rax, [rax+10h]
0x1400032f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032fc  mov     [rbp+var_10], 0
0x140003304  mov     eax, edi
0x140003306  mov     rbx, [rsp+60h+arg_0]
0x14000330e  add     rsp, 60h
0x140003312  pop     r15
0x140003314  pop     r14
0x140003316  pop     rdi
0x140003317  pop     rsi
0x140003318  pop     rbp
0x140003319  retn
```
