# CActiveScriptEngine::GetItemInfo(ushort const *,ulong,IUnknown * *,ITypeInfo * *)

- ea: `0x18000a530`
- end: `0x18000a6c4`
- name: `?GetItemInfo@CActiveScriptEngine@@UEAAJPEBGKPEAPEAUIUnknown@@PEAPEAUITypeInfo@@@Z`
- size: `404`
- prototype: `int(CActiveScriptEngine *__hidden this, const unsigned __int16 *, unsigned int, struct IUnknown **, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a530`
- `0x18000e090`
- `0x180037db0`
- `0x1800463ec`
- `0x1800556a8`
- `0x180062f8c`
- `0x180064010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a5f7`
- `msvcrt!_wcsicmp` at `0x18000a615`
- `msvcrt!_wcsicmp` at `0x18000a693`
- `msvcrt!_wcsicmp` at `0x180027429`
- `msvcrt!_wcsicmp` at `0x180027457`
- `msvcrt!_wcsicmp` at `0x180027485`
- `msvcrt!_wcsicmp` at `0x1800274aa`
- `msvcrt!_wcsicmp` at `0x1800274cf`
- `msvcrt!_wcsicmp` at `0x180027564`
- `msvcrt!_wcsicmp` at `0x18000a5f7`
- `msvcrt!_wcsicmp` at `0x18000a615`
- `msvcrt!_wcsicmp` at `0x18000a693`
- `msvcrt!_wcsicmp` at `0x180027429`
- `msvcrt!_wcsicmp` at `0x180027457`
- `msvcrt!_wcsicmp` at `0x180027485`
- `msvcrt!_wcsicmp` at `0x1800274aa`
- `msvcrt!_wcsicmp` at `0x1800274cf`
- `msvcrt!_wcsicmp` at `0x180027564`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180027548`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180027548`
- `KERNEL32!HeapAlloc` at `0x18002750e`
- `KERNEL32!HeapAlloc` at `0x18002750e`

## pseudocode

```c
__int64 __fastcall CActiveScriptEngine::GetItemInfo(
        CActiveScriptEngine *this,
        wchar_t *a2,
        char a3,
        struct IUnknown **a4,
        struct ITypeInfo **a5)
{
  CActiveScriptEngine *v5; // r13
  struct ITypeInfo **v10; // rbp
  __int64 v11; // rax
  unsigned int v13; // r15d
  int v14; // ecx
  struct IASPObjectContext *lpVtbl; // rdi
  BOOL v16; // esi
  unsigned int (__fastcall *v17)(CResponse *__hidden); // rax
  int v19; // eax
  int v20; // eax
  LPVOID v21; // rax
  int v22; // eax
  int Component; // edi

  v5 = (CActiveScriptEngine *)((char *)this - 8);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 1) + 136LL))((char *)this - 8);
  if ( a5 )
    *a5 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = (struct ITypeInfo **)*((_QWORD *)this + 6);
  a5 = v10;
  if ( !v10 )
  {
    ViperGetHitObjFromContext((struct CHitObj **)&a5);
    v10 = a5;
    if ( !a5 )
      return 2147647531LL;
  }
  if ( a2 )
  {
    v11 = -1;
    while ( a2[++v11] != 0 )
      ;
    v13 = 2 * v11;
  }
  else
  {
    v13 = 0;
  }
  v14 = dword_18006AAB0[((unsigned __int8)*a2 - (_BYTE)v13) & 0x1F];
  switch ( v14 )
  {
    case 0:
      goto LABEL_56;
    case 6:
      if ( _wcsicmp(a2, L"Response") )
        goto LABEL_56;
      if ( ((_DWORD)v10[1] & 0x200) != 0 )
        return 2147647531LL;
      lpVtbl = (struct IASPObjectContext *)v10[4];
      goto LABEL_18;
    case 2:
      if ( _wcsicmp(a2, L"ScriptingNamespace") )
        goto LABEL_56;
      lpVtbl = (struct IASPObjectContext *)v10[9];
      goto LABEL_18;
    case 9:
      if ( _wcsicmp(a2, L"ASPGLOBALTLB") )
        goto LABEL_56;
      lpVtbl = (struct IASPObjectContext *)v10[3][42].lpVtbl;
LABEL_18:
      v16 = 1;
      goto LABEL_19;
  }
  lpVtbl = 0;
  switch ( v14 )
  {
    case 1:
      if ( _wcsicmp(a2, L"ObjectContext") )
        goto LABEL_56;
      lpVtbl = (struct IASPObjectContext *)v10[7];
      v16 = 1;
      if ( lpVtbl )
        goto LABEL_20;
      lpVtbl = g_pIASPDummyObjectContext;
      if ( g_pIASPDummyObjectContext )
        goto LABEL_20;
      v21 = HeapAlloc(g_hDenaliHeap, 0, 0x30u);
      lpVtbl = (struct IASPObjectContext *)v21;
      if ( !v21 )
        goto LABEL_56;
      *((_QWORD *)v21 + 3) = 0;
      *((_QWORD *)v21 + 2) = 0;
      *((_QWORD *)v21 + 1) = 0;
      *(_QWORD *)v21 = &CASPDummyObjectContext::`vftable';
      *((_DWORD *)v21 + 8) = 1;
      CoCreateFreeThreadedMarshaler((LPUNKNOWN)v21, (LPUNKNOWN *)v21 + 5);
      g_pIASPDummyObjectContext = lpVtbl;
      break;
    case 3:
      v20 = _wcsicmp(a2, L"Application");
      if ( !v20 )
        lpVtbl = (struct IASPObjectContext *)v10[3];
      v16 = v20 == 0;
      break;
    case 4:
      if ( _wcsicmp(a2, L"Session") )
        goto LABEL_56;
      if ( ((_DWORD)v10[1] & 0x400) != 0 )
        return 2147647531LL;
      lpVtbl = (struct IASPObjectContext *)v10[2];
      goto LABEL_18;
    case 5:
      if ( _wcsicmp(a2, L"Request") )
        goto LABEL_56;
      if ( ((_DWORD)v10[1] & 0x200) != 0 )
        return 2147647531LL;
      lpVtbl = (struct IASPObjectContext *)v10[5];
      goto LABEL_18;
    case 7:
      v19 = _wcsicmp(a2, L"Server");
      if ( !v19 )
        lpVtbl = (struct IASPObjectContext *)v10[6];
      v16 = v19 == 0;
      break;
    case 8:
      v22 = _wcsicmp(a2, L"ASPPAGETLB");
      if ( !v22 )
        lpVtbl = (struct IASPObjectContext *)v10[23];
      v16 = v22 == 0;
      break;
    default:
      goto LABEL_56;
  }
LABEL_19:
  if ( lpVtbl )
  {
LABEL_20:
    if ( (a3 & 1) != 0 )
    {
      v17 = *(unsigned int (__fastcall **)(CResponse *__hidden))(*(_QWORD *)lpVtbl + 8LL);
      if ( v17 == CResponse::AddRef )
        CResponse::AddRef(lpVtbl);
      else
        v17(lpVtbl);
      *a4 = (struct IUnknown *)lpVtbl;
    }
    return 0;
  }
  if ( v16 )
    return 2147647531LL;
LABEL_56:
  a5 = 0;
  Component = CHitObj::GetComponent((CHitObj *)v10, 0, a2, v13, (struct CComponentObject **)&a5);
  if ( Component
    || (a3 & 1) != 0 && (Component = CComponentObject::GetAddRefdIUnknown((CComponentObject *)a5, a4), Component < 0) )
  {
    CActiveScriptEngine::HandleItemNotFound(v5, a2);
    return (unsigned int)Component;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a530  mov     [rsp+arg_10], rbx
0x18000a535  push    rbp
0x18000a536  push    rdi
0x18000a537  push    r12
0x18000a539  push    r13
0x18000a53b  push    r14
0x18000a53d  sub     rsp, 30h
0x18000a541  mov     rax, [rcx-8]
0x18000a545  lea     r13, [rcx-8]
0x18000a549  mov     rdi, rcx
0x18000a54c  mov     r14, r9
0x18000a54f  mov     rcx, r13
0x18000a552  mov     r12d, r8d
0x18000a555  mov     rbx, rdx
0x18000a558  mov     rax, [rax+88h]
0x18000a55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a564  mov     rax, [rsp+58h+arg_20]
0x18000a56c  test    rax, rax
0x18000a56f  jnz     loc_1800273CC
0x18000a575  test    r14, r14
0x18000a578  jz      short loc_18000A581
0x18000a57a  mov     qword ptr [r14], 0
0x18000a581  mov     rbp, [rdi+30h]
0x18000a585  mov     [rsp+58h+arg_0], rsi
0x18000a58a  mov     [rsp+58h+arg_8], r15
0x18000a58f  mov     [rsp+58h+arg_20], rbp
0x18000a597  test    rbp, rbp
0x18000a59a  jz      loc_1800273D8
0x18000a5a0  test    rbx, rbx
0x18000a5a3  jz      loc_1800273FB
0x18000a5a9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a5b0  cmp     word ptr [rbx+rax*2+2], 0
0x18000a5b6  lea     rax, [rax+1]
0x18000a5ba  jnz     short loc_18000A5B0
0x18000a5bc  lea     r15d, [rax+rax]
0x18000a5c0  movzx   eax, word ptr [rbx]
0x18000a5c3  lea     rdx, cs:180000000h
0x18000a5ca  sub     eax, r15d
0x18000a5cd  and     eax, 1Fh
0x18000a5d0  mov     ecx, ds:rva dword_18006AAB0[rdx+rax*4]
0x18000a5d7  test    ecx, ecx
0x18000a5d9  jz      def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18000a5df  cmp     ecx, 6
0x18000a5e2  jz      short loc_18000A60B
0x18000a5e4  cmp     ecx, 2
0x18000a5e7  jnz     loc_18000A680
0x18000a5ed  lea     rdx, aScriptingnames; "ScriptingNamespace"
0x18000a5f4  mov     rcx, rbx; String1
0x18000a5f7  call    cs:__imp__wcsicmp
0x18000a5fd  test    eax, eax
0x18000a5ff  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18000a605  mov     rdi, [rbp+48h]
0x18000a609  jmp     short loc_18000A634
0x18000a60b  lea     rdx, aResponse; "Response"
0x18000a612  mov     rcx, rbx; String1
0x18000a615  call    cs:__imp__wcsicmp
0x18000a61b  test    eax, eax
0x18000a61d  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18000a623  test    dword ptr [rbp+8], 200h
0x18000a62a  jnz     loc_18000A6B6
0x18000a630  mov     rdi, [rbp+20h]
0x18000a634  mov     esi, 1
0x18000a639  test    rdi, rdi
0x18000a63c  jz      short loc_18000A6AE
0x18000a63e  test    r12b, 1
0x18000a642  jz      short loc_18000A662
0x18000a644  mov     rax, [rdi]
0x18000a647  lea     rcx, ?AddRef@CResponse@@UEAAKXZ; CResponse::AddRef(void)
0x18000a64e  mov     rax, [rax+8]
0x18000a652  cmp     rax, rcx
0x18000a655  mov     rcx, rdi; this
0x18000a658  jnz     short loc_18000A6BD
0x18000a65a  call    ?AddRef@CResponse@@UEAAKXZ; CResponse::AddRef(void)
0x18000a65f  mov     [r14], rdi
0x18000a662  xor     eax, eax
0x18000a664  mov     r15, [rsp+58h+arg_8]
0x18000a669  mov     rsi, [rsp+58h+arg_0]
0x18000a66e  mov     rbx, [rsp+58h+arg_10]
0x18000a673  add     rsp, 30h
0x18000a677  pop     r14
0x18000a679  pop     r13
0x18000a67b  pop     r12
0x18000a67d  pop     rdi
0x18000a67e  pop     rbp
0x18000a67f  retn
0x18000a680  cmp     ecx, 9
0x18000a683  jnz     loc_180027403
0x18000a689  lea     rdx, aAspglobaltlb; "ASPGLOBALTLB"
0x18000a690  mov     rcx, rbx; String1
0x18000a693  call    cs:__imp__wcsicmp
0x18000a699  test    eax, eax
0x18000a69b  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18000a6a1  mov     rax, [rbp+18h]
0x18000a6a5  mov     rdi, [rax+150h]
0x18000a6ac  jmp     short loc_18000A634
0x18000a6ae  test    esi, esi
0x18000a6b0  jz      def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18000a6b6  mov     eax, 8002802Bh
0x18000a6bb  jmp     short loc_18000A664
0x18000a6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c2  jmp     short loc_18000A65F
0x1800273cc  mov     qword ptr [rax], 0
0x1800273d3  jmp     loc_18000A575
0x1800273d8  lea     rcx, [rsp+58h+arg_20]; struct CHitObj **
0x1800273e0  call    ?ViperGetHitObjFromContext@@YAJPEAPEAVCHitObj@@@Z; ViperGetHitObjFromContext(CHitObj * *)
0x1800273e5  mov     rbp, [rsp+58h+arg_20]
0x1800273ed  test    rbp, rbp
0x1800273f0  jz      loc_18000A6B6
0x1800273f6  jmp     loc_18000A5A0
0x1800273fb  xor     r15d, r15d
0x1800273fe  jmp     loc_18000A5C0
0x180027403  dec     ecx; switch 8 cases
0x180027405  cmp     ecx, 7
0x180027408  ja      def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18002740e  movsxd  rax, ecx
0x180027411  xor     edi, edi
0x180027413  mov     ecx, ds:(jpt_18002741D - 180000000h)[rdx+rax*4]
0x18002741a  add     rcx, rdx
0x18002741d  jmp     rcx; switch jump
0x18002741f  lea     rdx, aRequest; jumptable 000000018002741D case 5
0x180027426  mov     rcx, rbx; String1
0x180027429  call    cs:__imp__wcsicmp
0x18002742f  test    eax, eax
0x180027431  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x180027437  test    dword ptr [rbp+8], 200h
0x18002743e  jnz     loc_18000A6B6
0x180027444  mov     rdi, [rbp+28h]
0x180027448  jmp     loc_18000A634
0x18002744d  lea     rdx, aSession; jumptable 000000018002741D case 4
0x180027454  mov     rcx, rbx; String1
0x180027457  call    cs:__imp__wcsicmp
0x18002745d  test    eax, eax
0x18002745f  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x180027465  test    dword ptr [rbp+8], 400h
0x18002746c  jnz     loc_18000A6B6
0x180027472  mov     rdi, [rbp+10h]
0x180027476  jmp     loc_18000A634
0x18002747b  lea     rdx, aServer_0; jumptable 000000018002741D case 7
0x180027482  mov     rcx, rbx; String1
0x180027485  call    cs:__imp__wcsicmp
0x18002748b  test    eax, eax
0x18002748d  jnz     short loc_180027493
0x18002748f  mov     rdi, [rbp+30h]
0x180027493  xor     esi, esi
0x180027495  test    eax, eax
0x180027497  setz    sil
0x18002749b  jmp     loc_18000A639
0x1800274a0  lea     rdx, aApplication_0; jumptable 000000018002741D case 3
0x1800274a7  mov     rcx, rbx; String1
0x1800274aa  call    cs:__imp__wcsicmp
0x1800274b0  test    eax, eax
0x1800274b2  jnz     short loc_1800274B8
0x1800274b4  mov     rdi, [rbp+18h]
0x1800274b8  xor     esi, esi
0x1800274ba  test    eax, eax
0x1800274bc  setz    sil
0x1800274c0  jmp     loc_18000A639
0x1800274c5  lea     rdx, aObjectcontext; jumptable 000000018002741D case 1
0x1800274cc  mov     rcx, rbx; String1
0x1800274cf  call    cs:__imp__wcsicmp
0x1800274d5  test    eax, eax
0x1800274d7  jnz     def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x1800274dd  mov     rdi, [rbp+38h]
0x1800274e1  mov     esi, 1
0x1800274e6  test    rdi, rdi
0x1800274e9  jnz     loc_18000A63E
0x1800274ef  mov     rdi, cs:?g_pIASPDummyObjectContext@@3PEAUIASPObjectContext@@EA; IASPObjectContext * g_pIASPDummyObjectContext
0x1800274f6  test    rdi, rdi
0x1800274f9  jnz     loc_18000A63E
0x1800274ff  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180027506  xor     edx, edx; dwFlags
0x180027508  mov     r8d, 30h ; '0'; dwBytes
0x18002750e  call    cs:__imp_HeapAlloc
0x180027514  mov     rdi, rax
0x180027517  test    rax, rax
0x18002751a  jz      short def_18002741D; jumptable 000000018002741D default case, cases 2,6
0x18002751c  mov     qword ptr [rax+18h], 0
0x180027524  lea     rdx, [rdi+28h]; ppunkMarshal
0x180027528  mov     qword ptr [rax+10h], 0
0x180027530  mov     rcx, rdi; punkOuter
0x180027533  mov     qword ptr [rax+8], 0
0x18002753b  lea     rax, ??_7CASPDummyObjectContext@@6B@; const CASPDummyObjectContext::`vftable'
0x180027542  mov     [rdi], rax
0x180027545  mov     [rdi+20h], esi
0x180027548  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002754e  mov     cs:?g_pIASPDummyObjectContext@@3PEAUIASPObjectContext@@EA, rdi; IASPObjectContext * g_pIASPDummyObjectContext
0x180027555  jmp     loc_18000A639
0x18002755a  lea     rdx, aAsppagetlb; jumptable 000000018002741D case 8
0x180027561  mov     rcx, rbx; String1
0x180027564  call    cs:__imp__wcsicmp
0x18002756a  test    eax, eax
0x18002756c  jnz     short loc_180027575
0x18002756e  mov     rdi, [rbp+0B8h]
0x180027575  xor     esi, esi
0x180027577  test    eax, eax
0x180027579  setz    sil
0x18002757d  jmp     loc_18000A639
0x180027582  lea     rax, [rsp+58h+arg_20]; jumptable 000000018002741D default case, cases 2,6
0x18002758a  mov     [rsp+58h+arg_20], 0
0x180027596  mov     r9d, r15d; unsigned int
0x180027599  mov     [rsp+58h+var_38], rax; struct CComponentObject **
0x18002759e  mov     r8, rbx; unsigned __int16 *
0x1800275a1  xor     edx, edx; unsigned int
0x1800275a3  mov     rcx, rbp; this
0x1800275a6  call    ?GetComponent@CHitObj@@QEAAJKPEAGKPEAPEAVCComponentObject@@@Z; CHitObj::GetComponent(ulong,ushort *,ulong,CComponentObject * *)
0x1800275ab  mov     edi, eax
0x1800275ad  test    eax, eax
0x1800275af  jnz     short loc_1800275D5
0x1800275b1  test    r12b, 1
0x1800275b5  jz      loc_18000A662
0x1800275bb  mov     rcx, [rsp+58h+arg_20]; this
0x1800275c3  mov     rdx, r14; struct IUnknown **
0x1800275c6  call    ?GetAddRefdIUnknown@CComponentObject@@QEAAJPEAPEAUIUnknown@@@Z; CComponentObject::GetAddRefdIUnknown(IUnknown * *)
0x1800275cb  mov     edi, eax
0x1800275cd  test    eax, eax
0x1800275cf  jns     loc_18000A662
0x1800275d5  mov     rdx, rbx; unsigned __int16 *
0x1800275d8  mov     rcx, r13; this
0x1800275db  call    ?HandleItemNotFound@CActiveScriptEngine@@AEAAXPEBG@Z; CActiveScriptEngine::HandleItemNotFound(ushort const *)
0x1800275e0  mov     eax, edi
0x1800275e2  jmp     loc_18000A664
```
