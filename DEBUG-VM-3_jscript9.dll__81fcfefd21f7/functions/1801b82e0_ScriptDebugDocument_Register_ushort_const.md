# ScriptDebugDocument::Register(ushort const *)

- ea: `0x1801b82e0`
- end: `0x1801b86be`
- name: `?Register@ScriptDebugDocument@@QEAAJPEBG@Z`
- size: `990`
- prototype: `__int64 __fastcall(ScriptDebugDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801b9d64`

## callees

- `0x180111564`
- `0x180174cb8`
- `0x1801a00c8`
- `0x1801aa3a4`
- `0x1801b82e0`
- `0x1802157d0`
- `0x18022459c`
- `0x180224608`
- `0x180224748`
- `0x1802248d8`
- `0x180224b3c`
- `0x180224c48`
- `0x180252504`
- `0x180252784`
- `0x18035e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1801b8418`
- `msvcrt!wcscpy_s` at `0x1801b8418`
- `msvcrt!wcsrchr` at `0x1801b83ed`
- `msvcrt!wcsrchr` at `0x1801b83fe`
- `msvcrt!wcsrchr` at `0x1801b83ed`
- `msvcrt!wcsrchr` at `0x1801b83fe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801b8385`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801b8385`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ScriptDebugDocument::Register(ScriptDebugDocument *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  ScriptEngine *v4; // r13
  __int64 *v5; // r12
  bool v6; // zf
  void **ppv; // rsi
  HRESULT LatestPDM; // eax
  __int64 v9; // rcx
  int DebugApplicationCoreNoRef; // ebx
  const unsigned __int16 *v11; // rbx
  wchar_t *v12; // r14
  unsigned __int16 *v13; // r15
  int v14; // r9d
  wchar_t *v15; // rax
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  char v26; // [rsp+40h] [rbp-40h]
  struct IDebugApplicationNode *v27; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  struct IDebugDocumentContext *v29; // [rsp+58h] [rbp-28h] BYREF
  struct IDebugApplicationNode *v30; // [rsp+60h] [rbp-20h] BYREF
  struct IDebugApplication64 *v31; // [rsp+68h] [rbp-18h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h]
  __int64 v33; // [rsp+78h] [rbp-8h]

  v33 = -2;
  v3 = *((_QWORD *)this + 4);
  v4 = *(ScriptEngine **)(v3 + 32);
  v5 = *(__int64 **)(*(_QWORD *)(v3 + 16) + 72LL);
  v32 = *(_QWORD *)(*v5 + 8);
  v6 = (*((_BYTE *)v5 + 36) & 1) == 0;
  v26 = *((_BYTE *)v5 + 36) & 1;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  ppv = (void **)((char *)this + 24);
  if ( !v6 )
  {
    DebugApplicationCoreNoRef = 0;
    v13 = 0;
    v12 = 0;
LABEL_24:
    if ( ScriptDebugDocument::GetDocumentContext(this, *((_DWORD *)v5 + 5), 1u, &v29) >= 0 )
    {
      v31 = 0;
      if ( ((int (__fastcall *)(struct IDebugDocumentContext *, struct IDebugApplication64 **))v29->lpVtbl->GetDocument)(
             v29,
             &v31) >= 0 )
      {
        v28 = 0;
        if ( ((__int64 (__fastcall *)(struct IDebugApplication64 *, GUID *, __int64 *))v31->lpVtbl->QueryInterface)(
               v31,
               &GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a,
               &v28) >= 0 )
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL) + 56LL) = v28;
        ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v28);
      }
      ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v31);
    }
    if ( !v26 )
    {
      DebugApplicationCoreNoRef = ScriptDebugDocument::AddText(this);
      if ( DebugApplicationCoreNoRef >= 0 )
      {
        if ( !(*(unsigned int (__fastcall **)(void *, struct IDebugApplicationNode **))(*(_QWORD *)*ppv + 128LL))(
                *ppv,
                &v27) )
        {
          ScriptDebugDocument::DbgGetRootApplicationNode(this, &v30);
          v28 = 0;
          if ( !(**(unsigned int (__fastcall ***)(void *, GUID *, __int64 *))*ppv)(
                  *ppv,
                  &GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a,
                  &v28) )
          {
            v21 = operator new[]<HeapAllocator>(32, v19, v20, HeapAllocator::NoThrowAlloc);
            if ( v21 )
            {
              v22 = *v5;
              v23 = v28;
              *(_QWORD *)v21 = &ScriptDocumentProviderBridge::`vftable';
              *(_DWORD *)(v21 + 8) = 0;
              *(_QWORD *)(v21 + 16) = v23;
              *(_QWORD *)(v21 + 24) = v22;
              if ( v23 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
              v31 = (struct IDebugApplication64 *)v21;
              _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
            }
            else
            {
              v21 = 0;
              v31 = 0;
            }
            v24 = v21;
            if ( !v21 )
              v24 = v28;
            ((void (__fastcall *)(struct IDebugApplicationNode *, __int64))v27->lpVtbl->SetDocumentProvider)(v27, v24);
            ATL::CComPtr<ScriptDocumentProviderBridge>::~CComPtr<ScriptDocumentProviderBridge>(&v31);
          }
          ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v28);
        }
        DebugApplicationCoreNoRef = ScriptDebugDocument::AttachNode(this, v27, v30);
        if ( DebugApplicationCoreNoRef >= 0 )
          *((_BYTE *)this + 52) = 1;
      }
    }
    goto LABEL_45;
  }
  if ( (unsigned int)ShouldUseLocalPDM() )
    LatestPDM = LoadLatestPDM(&CLSID_CDebugDocumentHelper, &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871, ppv);
  else
    LatestPDM = CoCreateInstance(&CLSID_CDebugDocumentHelper, 0, 1u, &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871, ppv);
  DebugApplicationCoreNoRef = LatestPDM;
  if ( LatestPDM )
    goto LABEL_50;
  v11 = L"script block";
  if ( a2 )
    v11 = a2;
  if ( *(_QWORD *)(*v5 + 8) == -1 )
  {
    v12 = (wchar_t *)v11;
    v13 = (unsigned __int16 *)AllocateArray<HeapAllocator,unsigned short,1>(v9, HeapAllocator::NoThrowAlloc, 255);
    ScriptDebugDocument::GetFormattedTitle(this, v11, v13, v14);
  }
  else
  {
    v13 = (unsigned __int16 *)v11;
    v12 = (wchar_t *)AllocateArray<HeapAllocator,unsigned short,1>(v9, HeapAllocator::NoThrowAlloc, 255);
    v15 = wcsrchr(v11, 0x2Fu);
    if ( v15 || (v15 = wcsrchr(v11, 0x5Cu)) != 0 )
      v11 = v15 + 1;
    wcscpy_s(v12, 0xFFu, v11);
  }
  v31 = 0;
  DebugApplicationCoreNoRef = ScriptEngine::GetDebugApplicationCoreNoRef(v4, &v31);
  if ( DebugApplicationCoreNoRef >= 0 )
  {
    v17 = 1;
    if ( v32 != -1 )
      v17 = 8;
    DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(void *, struct IDebugApplication64 *, wchar_t *, unsigned __int16 *, int))(*(_QWORD *)*ppv + 24LL))(
                                  *ppv,
                                  v31,
                                  v12,
                                  v13,
                                  v17);
    if ( DebugApplicationCoreNoRef >= 0 )
    {
      v18 = v4 ? (__int64)v4 + 48 : 0LL;
      DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64, _DWORD, char *))(*(_QWORD *)*ppv + 80LL))(
                                    *ppv,
                                    0,
                                    *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL) + 24LL),
                                    v18,
                                    0,
                                    (char *)this + 40);
      if ( DebugApplicationCoreNoRef >= 0 )
        goto LABEL_24;
    }
  }
LABEL_45:
  if ( v32 == -1 )
  {
    if ( v13 )
      goto LABEL_49;
  }
  else if ( v12 )
  {
LABEL_49:
    DeleteArray<HeapAllocator,unsigned short const *>(v16, 255);
  }
LABEL_50:
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v29);
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v27);
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v30);
  return (unsigned int)DebugApplicationCoreNoRef;
}

```

## disassembly

```asm
0x1801b82e0  mov     rax, rsp
0x1801b82e3  mov     [rax+10h], rdx
0x1801b82e7  mov     [rax+8], rcx
0x1801b82eb  push    rbp
0x1801b82ec  push    rsi
0x1801b82ed  push    rdi
0x1801b82ee  push    r12
0x1801b82f0  push    r13
0x1801b82f2  push    r14
0x1801b82f4  push    r15
0x1801b82f6  mov     rbp, rsp
0x1801b82f9  sub     rsp, 80h
0x1801b8300  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1801b8308  mov     [rax+18h], rbx
0x1801b830c  mov     rdi, [rbp+arg_0]
0x1801b8310  mov     rax, [rdi+20h]
0x1801b8314  mov     r13, [rax+20h]
0x1801b8318  mov     rax, [rax+10h]
0x1801b831c  mov     r12, [rax+48h]
0x1801b8320  mov     rax, [r12]
0x1801b8324  mov     rax, [rax+8]
0x1801b8328  mov     [rbp+var_10], rax
0x1801b832c  mov     al, [r12+24h]
0x1801b8331  and     al, 1
0x1801b8333  mov     [rbp+var_40], al
0x1801b8336  mov     r14d, 0
0x1801b833c  mov     [rbp+var_20], r14
0x1801b8340  mov     [rbp+var_38], r14
0x1801b8344  mov     [rbp+var_28], r14
0x1801b8348  lea     rsi, [rdi+18h]
0x1801b834c  jnz     loc_1801B84C2
0x1801b8352  call    ?ShouldUseLocalPDM@@YAHXZ; ShouldUseLocalPDM(void)
0x1801b8357  lea     rcx, CLSID_CDebugDocumentHelper; struct _GUID *
0x1801b835e  test    eax, eax
0x1801b8360  jz      short loc_1801B8373
0x1801b8362  mov     r8, rsi; void **
0x1801b8365  lea     rdx, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; struct _GUID *
0x1801b836c  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x1801b8371  jmp     short loc_1801B838B
0x1801b8373  mov     [rsp+80h+ppv], rsi; ppv
0x1801b8378  lea     r9, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; riid
0x1801b837f  xor     edx, edx; pUnkOuter
0x1801b8381  lea     r8d, [rdx+1]; dwClsContext
0x1801b8385  call    cs:__imp_CoCreateInstance
0x1801b838b  mov     ebx, eax
0x1801b838d  test    eax, eax
0x1801b838f  jnz     loc_1801B8684
0x1801b8395  mov     rax, [rbp+Str]
0x1801b8399  lea     rbx, aScriptBlock; "script block"
0x1801b83a0  test    rax, rax
0x1801b83a3  cmovnz  rbx, rax
0x1801b83a7  mov     rax, [r12]
0x1801b83ab  mov     r8d, 0FFh
0x1801b83b1  lea     rdx, ?NoThrowAlloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAlloc(unsigned __int64)
0x1801b83b8  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1801b83bd  jnz     short loc_1801B83DA
0x1801b83bf  mov     r14, rbx
0x1801b83c2  call    ??$AllocateArray@UHeapAllocator@@G$00@@YAPEAGPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,ushort,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1801b83c7  mov     r15, rax
0x1801b83ca  mov     r8, rax; unsigned __int16 *
0x1801b83cd  mov     rdx, rbx; unsigned __int16 *
0x1801b83d0  mov     rcx, rdi; this
0x1801b83d3  call    ?GetFormattedTitle@ScriptDebugDocument@@QEAAXPEBGPEAGH@Z; ScriptDebugDocument::GetFormattedTitle(ushort const *,ushort *,int)
0x1801b83d8  jmp     short loc_1801B841E
0x1801b83da  mov     r15, rbx
0x1801b83dd  call    ??$AllocateArray@UHeapAllocator@@G$00@@YAPEAGPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,ushort,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1801b83e2  mov     r14, rax
0x1801b83e5  mov     edx, 2Fh ; '/'; Ch
0x1801b83ea  mov     rcx, rbx; Str
0x1801b83ed  call    cs:__imp_wcsrchr
0x1801b83f3  test    rax, rax
0x1801b83f6  jnz     short loc_1801B8409
0x1801b83f8  lea     edx, [rax+5Ch]; Ch
0x1801b83fb  mov     rcx, rbx; Str
0x1801b83fe  call    cs:__imp_wcsrchr
0x1801b8404  test    rax, rax
0x1801b8407  jz      short loc_1801B840D
0x1801b8409  lea     rbx, [rax+2]
0x1801b840d  mov     r8, rbx; Source
0x1801b8410  mov     edx, 0FFh; SizeInWords
0x1801b8415  mov     rcx, r14; Destination
0x1801b8418  call    cs:__imp_wcscpy_s
0x1801b841e  mov     [rbp+var_18], 0
0x1801b8426  lea     rdx, [rbp+var_18]; struct IDebugApplication64 **
0x1801b842a  mov     rcx, r13; this
0x1801b842d  call    ?GetDebugApplicationCoreNoRef@ScriptEngine@@QEAAJPEAPEAUIDebugApplication64@@@Z; ScriptEngine::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)
0x1801b8432  mov     ebx, eax
0x1801b8434  test    eax, eax
0x1801b8436  js      loc_1801B8660
0x1801b843c  mov     rcx, [rsi]
0x1801b843f  mov     rax, [rcx]
0x1801b8442  mov     edx, 1
0x1801b8447  lea     r8d, [rdx+7]
0x1801b844b  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1801b8450  cmovnz  edx, r8d
0x1801b8454  mov     dword ptr [rsp+80h+ppv], edx
0x1801b8458  mov     r9, r15
0x1801b845b  mov     r8, r14
0x1801b845e  mov     rdx, [rbp+var_18]
0x1801b8462  mov     rax, [rax+18h]
0x1801b8466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b846b  mov     ebx, eax
0x1801b846d  test    eax, eax
0x1801b846f  js      loc_1801B8660
0x1801b8475  mov     rcx, [rsi]
0x1801b8478  mov     rax, [rcx]
0x1801b847b  mov     r10, [rax+50h]
0x1801b847f  test    r13, r13
0x1801b8482  jz      short loc_1801B848A
0x1801b8484  lea     rax, [r13+30h]
0x1801b8488  jmp     short loc_1801B848C
0x1801b848a  xor     eax, eax
0x1801b848c  lea     r9, [rdi+28h]
0x1801b8490  mov     rdx, [rdi+20h]
0x1801b8494  mov     r8, [rdx+10h]
0x1801b8498  mov     [rsp+80h+var_58], r9
0x1801b849d  mov     dword ptr [rsp+80h+ppv], 0
0x1801b84a5  mov     r9, rax
0x1801b84a8  mov     r8d, [r8+18h]
0x1801b84ac  xor     edx, edx
0x1801b84ae  mov     rax, r10
0x1801b84b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b84b6  mov     ebx, eax
0x1801b84b8  test    eax, eax
0x1801b84ba  js      loc_1801B8660
0x1801b84c0  jmp     short loc_1801B84CA
0x1801b84c2  xor     ebx, ebx
0x1801b84c4  xor     r15d, r15d
0x1801b84c7  xor     r14d, r14d
0x1801b84ca  lea     r9, [rbp+var_28]; struct IDebugDocumentContext **
0x1801b84ce  mov     r8d, 1; unsigned int
0x1801b84d4  mov     edx, [r12+14h]; unsigned int
0x1801b84d9  mov     rcx, rdi; this
0x1801b84dc  call    ?GetDocumentContext@ScriptDebugDocument@@QEAAJKKPEAPEAUIDebugDocumentContext@@@Z; ScriptDebugDocument::GetDocumentContext(ulong,ulong,IDebugDocumentContext * *)
0x1801b84e1  test    eax, eax
0x1801b84e3  js      short loc_1801B854E
0x1801b84e5  mov     [rbp+var_18], 0
0x1801b84ed  mov     rcx, [rbp+var_28]
0x1801b84f1  mov     rax, [rcx]
0x1801b84f4  lea     rdx, [rbp+var_18]
0x1801b84f8  mov     rax, [rax+18h]
0x1801b84fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8501  test    eax, eax
0x1801b8503  js      short loc_1801B8545
0x1801b8505  mov     [rbp+var_30], 0
0x1801b850d  mov     rcx, [rbp+var_18]
0x1801b8511  mov     rax, [rcx]
0x1801b8514  lea     r8, [rbp+var_30]
0x1801b8518  lea     rdx, _GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a
0x1801b851f  mov     rax, [rax]
0x1801b8522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8527  test    eax, eax
0x1801b8529  js      short loc_1801B853B
0x1801b852b  mov     rax, [rdi+20h]
0x1801b852f  mov     rcx, [rax+10h]
0x1801b8533  mov     rax, [rbp+var_30]
0x1801b8537  mov     [rcx+38h], rax
0x1801b853b  lea     rcx, [rbp+var_30]
0x1801b853f  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b8544  nop
0x1801b8545  lea     rcx, [rbp+var_18]
0x1801b8549  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b854e  cmp     [rbp+var_40], 0
0x1801b8552  jnz     loc_1801B8660
0x1801b8558  mov     rcx, rdi; this
0x1801b855b  call    ?AddText@ScriptDebugDocument@@AEAAJXZ; ScriptDebugDocument::AddText(void)
0x1801b8560  mov     ebx, eax
0x1801b8562  test    eax, eax
0x1801b8564  js      loc_1801B8660
0x1801b856a  mov     rcx, [rsi]
0x1801b856d  mov     rax, [rcx]
0x1801b8570  lea     rdx, [rbp+var_38]
0x1801b8574  mov     rax, [rax+80h]
0x1801b857b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8580  test    eax, eax
0x1801b8582  jnz     loc_1801B8646
0x1801b8588  lea     rdx, [rbp+var_20]; struct IDebugApplicationNode **
0x1801b858c  mov     rcx, rdi; this
0x1801b858f  call    ?DbgGetRootApplicationNode@ScriptDebugDocument@@QEAAJPEAPEAUIDebugApplicationNode@@@Z; ScriptDebugDocument::DbgGetRootApplicationNode(IDebugApplicationNode * *)
0x1801b8594  mov     [rbp+var_30], 0
0x1801b859c  mov     rcx, [rsi]
0x1801b859f  mov     rax, [rcx]
0x1801b85a2  lea     r8, [rbp+var_30]
0x1801b85a6  lea     rdx, _GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a
0x1801b85ad  mov     rax, [rax]
0x1801b85b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b85b5  test    eax, eax
0x1801b85b7  jnz     loc_1801B863D
0x1801b85bd  lea     r9, ?NoThrowAlloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAlloc(unsigned __int64)
0x1801b85c4  lea     ecx, [rax+20h]
0x1801b85c7  call    ??$?_UUHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@_NP80@EAAPEAD0@Z@Z; operator new[]<HeapAllocator>(unsigned __int64,HeapAllocator *,bool,char * (HeapAllocator::*)(unsigned __int64))
0x1801b85cc  mov     rbx, rax
0x1801b85cf  test    rax, rax
0x1801b85d2  jz      short loc_1801B8610
0x1801b85d4  mov     rax, [r12]
0x1801b85d8  mov     rcx, [rbp+var_30]
0x1801b85dc  lea     rdx, ??_7ScriptDocumentProviderBridge@@6B@; const ScriptDocumentProviderBridge::`vftable'
0x1801b85e3  mov     [rbx], rdx
0x1801b85e6  mov     dword ptr [rbx+8], 0
0x1801b85ed  mov     [rbx+10h], rcx
0x1801b85f1  mov     [rbx+18h], rax
0x1801b85f5  test    rcx, rcx
0x1801b85f8  jz      short loc_1801B8606
0x1801b85fa  mov     rax, [rcx]
0x1801b85fd  mov     rax, [rax+8]
0x1801b8601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8606  mov     [rbp+var_18], rbx
0x1801b860a  lock inc dword ptr [rbx+8]
0x1801b860e  jmp     short loc_1801B8616
0x1801b8610  xor     ebx, ebx
0x1801b8612  mov     [rbp+var_18], rbx
0x1801b8616  mov     rcx, [rbp+var_38]
0x1801b861a  mov     rax, [rcx]
0x1801b861d  mov     rax, [rax+40h]
0x1801b8621  test    rbx, rbx
0x1801b8624  mov     rdx, rbx
0x1801b8627  jnz     short loc_1801B862D
0x1801b8629  mov     rdx, [rbp+var_30]
0x1801b862d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8632  nop
0x1801b8633  lea     rcx, [rbp+var_18]
0x1801b8637  call    ??1?$CComPtr@VScriptDocumentProviderBridge@@@ATL@@QEAA@XZ; ATL::CComPtr<ScriptDocumentProviderBridge>::~CComPtr<ScriptDocumentProviderBridge>(void)
0x1801b863c  nop
0x1801b863d  lea     rcx, [rbp+var_30]
0x1801b8641  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b8646  mov     r8, [rbp+var_20]; struct IDebugApplicationNode *
0x1801b864a  mov     rdx, [rbp+var_38]; struct IDebugApplicationNode *
0x1801b864e  mov     rcx, rdi; this
0x1801b8651  call    ?AttachNode@ScriptDebugDocument@@AEAAJPEAUIDebugApplicationNode@@0@Z; ScriptDebugDocument::AttachNode(IDebugApplicationNode *,IDebugApplicationNode *)
0x1801b8656  mov     ebx, eax
0x1801b8658  test    eax, eax
0x1801b865a  js      short loc_1801B8660
0x1801b865c  mov     byte ptr [rdi+34h], 1
0x1801b8660  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1801b8665  jnz     short loc_1801B8671
0x1801b8667  test    r15, r15
0x1801b866a  jz      short loc_1801B8684
0x1801b866c  mov     r8, r15
0x1801b866f  jmp     short loc_1801B8679
0x1801b8671  test    r14, r14
0x1801b8674  jz      short loc_1801B8684
0x1801b8676  mov     r8, r14
0x1801b8679  mov     edx, 0FFh
0x1801b867e  call    ??$DeleteArray@UHeapAllocator@@PEBG@@YAXPEAUHeapAllocator@@_KPEAPEBG@Z; DeleteArray<HeapAllocator,ushort const *>(HeapAllocator *,unsigned __int64,ushort const * *)
0x1801b8683  nop
0x1801b8684  lea     rcx, [rbp+var_28]
0x1801b8688  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b868d  nop
0x1801b868e  lea     rcx, [rbp+var_38]
0x1801b8692  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b8697  nop
0x1801b8698  lea     rcx, [rbp+var_20]
0x1801b869c  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801b86a1  mov     eax, ebx
0x1801b86a3  mov     rbx, [rsp+80h+arg_10]
0x1801b86ab  add     rsp, 80h
0x1801b86b2  pop     r15
0x1801b86b4  pop     r14
0x1801b86b6  pop     r13
0x1801b86b8  pop     r12
0x1801b86ba  pop     rdi
0x1801b86bb  pop     rsi
0x1801b86bc  pop     rbp
0x1801b86bd  retn
```
