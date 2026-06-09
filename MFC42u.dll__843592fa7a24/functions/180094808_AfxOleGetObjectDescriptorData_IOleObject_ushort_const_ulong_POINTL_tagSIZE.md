# _AfxOleGetObjectDescriptorData(IOleObject *,ushort const *,ulong,_POINTL,tagSIZE *)

- ea: `0x180094808`
- end: `0x180094ace`
- name: `?_AfxOleGetObjectDescriptorData@@YAPEAXPEAUIOleObject@@PEBGKU_POINTL@@PEAUtagSIZE@@@Z`
- size: `710`
- prototype: `void *__usercall@<rax>(struct IOleObject *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct _POINTL@<r9>, struct tagSIZE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180082130`
- `0x18009b060`

## callees

- `0x18000a150`
- `0x180014420`
- `0x180094808`
- `0x180094ad4`
- `0x180094c50`
- `0x18009cf3c`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180094936`
- `msvcrt!swprintf_s` at `0x180094936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180094919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180094919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094a87`
- `OLE32!CreateBindCtx` at `0x180094996`
- `OLE32!CreateBindCtx` at `0x180094996`

## pseudocode

```c
void *__fastcall _AfxOleGetObjectDescriptorData(
        struct IUnknown *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _POINTL a4,
        struct tagSIZE *a5)
{
  int v5; // edi
  unsigned int v7; // r12d
  struct IUnknown *v9; // r14
  struct IUnknown *v10; // rax
  struct IOleObjectVtbl *lpVtbl; // rcx
  struct IUnknown *v12; // r15
  int v13; // edi
  size_t v14; // r12
  wchar_t *v15; // rax
  wchar_t *v16; // rdi
  unsigned int v17; // ecx
  void *ObjectDescriptorData; // rbx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+4Ch] [rbp-B4h]
  struct tagSIZE v23; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v24; // [rsp+58h] [rbp-A8h] BYREF
  LPBC ppbc; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v26; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *Interface; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v28; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v29; // [rsp+80h] [rbp-80h] BYREF
  GUID v30; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Format[80]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = 0;
  v24 = a2;
  pv = 0;
  v30 = 0;
  v26 = 0;
  ppbc = 0;
  v7 = a3;
  v23 = 0;
  v21 = 0;
  v22 = a3;
  Interface = _AfxQueryInterface(a1, &IID_IOleLink);
  v9 = Interface;
  v10 = _AfxQueryInterface(a1, &IID_IViewObject2);
  lpVtbl = (struct IOleObjectVtbl *)a1->lpVtbl;
  v12 = v10;
  v28 = v10;
  if ( ((unsigned int (__fastcall *)(struct IUnknown *, GUID *))lpVtbl->GetUserClassID)(a1, &v30) )
    v30 = GUID_NULL;
  ((void (__fastcall *)(struct IUnknown *, __int64, LPVOID *))a1->lpVtbl[5].AddRef)(a1, 1, &pv);
  if ( v9 )
  {
    if ( pv )
    {
      AfxLoadString(0xF094u, Format, 0x50u);
      v13 = ocslen((const unsigned __int16 *)pv);
      v14 = (int)(v13 + ocslen(Format) + 1);
      v15 = (wchar_t *)CoTaskMemAlloc(2 * v14);
      v16 = v15;
      if ( v15 )
      {
        swprintf_s(v15, v14, Format, pv);
        CoTaskMemFree(pv);
        pv = v16;
      }
      v7 = v22;
    }
    ((void (__fastcall *)(struct IUnknown *, LPCWSTR *))v9->lpVtbl[2].Release)(v9, &v24);
    goto LABEL_12;
  }
  if ( !v24
    && !((unsigned int (__fastcall *)(struct IUnknown *, __int64, __int64, struct IUnknown **))a1->lpVtbl[2].Release)(
          a1,
          4,
          3,
          &v26) )
  {
    CreateBindCtx(0, &ppbc);
    ((void (__fastcall *)(struct IUnknown *, LPBC, _QWORD, LPCWSTR *))v26->lpVtbl[6].Release)(v26, ppbc, 0, &v24);
    _AfxRelease((struct IUnknown **)&ppbc);
LABEL_12:
    v5 = 1;
  }
  if ( a5 )
  {
    v23 = *a5;
  }
  else if ( !v12
         || ((unsigned int (__fastcall *)(struct IUnknown *, _QWORD, __int64, _QWORD, struct tagSIZE *))v12->lpVtbl[3].QueryInterface)(
              v12,
              v7,
              0xFFFFFFFFLL,
              0,
              &v23) )
  {
    v23 = 0;
  }
  if ( ((unsigned int (__fastcall *)(struct IUnknown *, _QWORD, unsigned int *))a1->lpVtbl[7].AddRef)(a1, v7, &v21) )
  {
    v17 = 0;
    v21 = 0;
  }
  else
  {
    v17 = v21;
  }
  v29 = v30;
  ObjectDescriptorData = _AfxOleGetObjectDescriptorData(&v29, v7, v23, a4, v17, (LPCWSTR)pv, v24);
  CoTaskMemFree(pv);
  if ( v5 )
    CoTaskMemFree((LPVOID)v24);
  _AfxRelease(&v26);
  _AfxRelease(&Interface);
  _AfxRelease(&v28);
  return ObjectDescriptorData;
}

```

## disassembly

```asm
0x180094808  push    rbp
0x18009480a  push    rbx
0x18009480b  push    rsi
0x18009480c  push    rdi
0x18009480d  push    r12
0x18009480f  push    r13
0x180094811  push    r14
0x180094813  push    r15
0x180094815  lea     rbp, [rsp-58h]
0x18009481a  sub     rsp, 158h
0x180094821  mov     rax, cs:__security_cookie
0x180094828  xor     rax, rsp
0x18009482b  mov     [rbp+90h+var_50], rax
0x18009482f  mov     r13, [rbp+90h+arg_20]
0x180094836  xor     edi, edi
0x180094838  mov     [rsp+190h+var_138], rdx
0x18009483d  xorps   xmm0, xmm0
0x180094840  lea     rdx, IID_IOleLink; struct _GUID *
0x180094847  mov     [rsp+190h+pv], rdi
0x18009484c  movups  [rbp+90h+var_100], xmm0
0x180094850  mov     [rsp+190h+var_128], rdi
0x180094855  mov     rbx, r9
0x180094858  mov     [rsp+190h+ppbc], rdi
0x18009485d  mov     r12d, r8d
0x180094860  mov     qword ptr [rsp+190h+var_140.cx], rdi
0x180094865  mov     rsi, rcx
0x180094868  mov     [rsp+190h+var_148], edi
0x18009486c  mov     [rsp+190h+var_144], r8d
0x180094871  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180094876  lea     rdx, IID_IViewObject2; struct _GUID *
0x18009487d  mov     [rsp+190h+var_120], rax
0x180094882  mov     rcx, rsi; struct IUnknown *
0x180094885  mov     r14, rax
0x180094888  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x18009488d  mov     rcx, [rsi]
0x180094890  lea     rdx, [rbp+90h+var_100]
0x180094894  mov     r15, rax
0x180094897  mov     [rsp+190h+var_118], rax
0x18009489c  mov     rax, [rcx+78h]
0x1800948a0  mov     rcx, rsi
0x1800948a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948a8  test    eax, eax
0x1800948aa  jz      short loc_1800948B8
0x1800948ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800948b3  movdqu  [rbp+90h+var_100], xmm0
0x1800948b8  mov     rax, [rsi]
0x1800948bb  lea     r8, [rsp+190h+pv]
0x1800948c0  mov     edx, 1
0x1800948c5  mov     rcx, rsi
0x1800948c8  mov     rax, [rax+80h]
0x1800948cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948d4  test    r14, r14
0x1800948d7  jz      loc_180094967
0x1800948dd  cmp     [rsp+190h+pv], rdi
0x1800948e2  jz      short loc_180094951
0x1800948e4  mov     r8d, 50h ; 'P'; cchBufferMax
0x1800948ea  lea     rdx, [rbp+90h+Format]; lpBuffer
0x1800948ee  mov     ecx, 0F094h; uID
0x1800948f3  call    ?AfxLoadString@@YAHIPEAGI@Z; AfxLoadString(uint,ushort *,uint)
0x1800948f8  mov     rcx, [rsp+190h+pv]; unsigned __int16 *
0x1800948fd  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180094902  lea     rcx, [rbp+90h+Format]; unsigned __int16 *
0x180094906  mov     edi, eax
0x180094908  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18009490d  lea     ecx, [rax+1]
0x180094910  add     ecx, edi
0x180094912  movsxd  r12, ecx
0x180094915  lea     rcx, [r12+r12]; cb
0x180094919  call    cs:__imp_CoTaskMemAlloc
0x18009491f  mov     rdi, rax
0x180094922  test    rax, rax
0x180094925  jz      short loc_18009494C
0x180094927  mov     r9, [rsp+190h+pv]
0x18009492c  lea     r8, [rbp+90h+Format]; Format
0x180094930  mov     rdx, r12; BufferCount
0x180094933  mov     rcx, rax; Buffer
0x180094936  call    cs:__imp_swprintf_s
0x18009493c  mov     rcx, [rsp+190h+pv]; pv
0x180094941  call    cs:__imp_CoTaskMemFree
0x180094947  mov     [rsp+190h+pv], rdi
0x18009494c  mov     r12d, [rsp+190h+var_144]
0x180094951  mov     rax, [r14]
0x180094954  lea     rdx, [rsp+190h+var_138]
0x180094959  mov     rcx, r14
0x18009495c  mov     rax, [rax+40h]
0x180094960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094965  jmp     short loc_1800949C7
0x180094967  cmp     [rsp+190h+var_138], rdi
0x18009496c  jnz     short loc_1800949CC
0x18009496e  mov     rax, [rsi]
0x180094971  lea     r9, [rsp+190h+var_128]
0x180094976  mov     edx, 4
0x18009497b  mov     rcx, rsi
0x18009497e  mov     rax, [rax+40h]
0x180094982  lea     r8d, [rdx-1]
0x180094986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009498b  test    eax, eax
0x18009498d  jnz     short loc_1800949CC
0x18009498f  lea     rdx, [rsp+190h+ppbc]; ppbc
0x180094994  xor     ecx, ecx; reserved
0x180094996  call    cs:__imp_CreateBindCtx
0x18009499c  mov     rcx, [rsp+190h+var_128]
0x1800949a1  lea     r9, [rsp+190h+var_138]
0x1800949a6  mov     rdx, [rsp+190h+ppbc]
0x1800949ab  xor     r8d, r8d
0x1800949ae  mov     rax, [rcx]
0x1800949b1  mov     rax, [rax+0A0h]
0x1800949b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800949bd  lea     rcx, [rsp+190h+ppbc]; struct IUnknown **
0x1800949c2  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x1800949c7  mov     edi, 1
0x1800949cc  test    r13, r13
0x1800949cf  jz      short loc_1800949DC
0x1800949d1  mov     rax, [r13+0]
0x1800949d5  mov     qword ptr [rsp+190h+var_140.cx], rax
0x1800949da  jmp     short loc_180094A11
0x1800949dc  test    r15, r15
0x1800949df  jz      short loc_180094A08
0x1800949e1  mov     rax, [r15]
0x1800949e4  lea     rcx, [rsp+190h+var_140]
0x1800949e9  mov     qword ptr [rsp+190h+var_170], rcx
0x1800949ee  xor     r9d, r9d
0x1800949f1  or      r8d, 0FFFFFFFFh
0x1800949f5  mov     edx, r12d
0x1800949f8  mov     rcx, r15
0x1800949fb  mov     rax, [rax+48h]
0x1800949ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a04  test    eax, eax
0x180094a06  jz      short loc_180094A11
0x180094a08  mov     qword ptr [rsp+190h+var_140.cx], 0
0x180094a11  mov     rax, [rsi]
0x180094a14  lea     r8, [rsp+190h+var_148]
0x180094a19  mov     edx, r12d
0x180094a1c  mov     rcx, rsi
0x180094a1f  mov     rax, [rax+0B0h]
0x180094a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a2b  test    eax, eax
0x180094a2d  jz      short loc_180094A37
0x180094a2f  xor     ecx, ecx
0x180094a31  mov     [rsp+190h+var_148], ecx
0x180094a35  jmp     short loc_180094A3B
0x180094a37  mov     ecx, [rsp+190h+var_148]
0x180094a3b  mov     rax, [rsp+190h+var_138]
0x180094a40  mov     r9, rbx; struct _POINTL
0x180094a43  movaps  xmm0, [rbp+90h+var_100]
0x180094a47  mov     edx, r12d; unsigned int
0x180094a4a  mov     r8, qword ptr [rsp+190h+var_140.cx]; struct tagSIZE
0x180094a4f  mov     [rsp+190h+var_160], rax; LPCWSTR
0x180094a54  mov     rax, [rsp+190h+pv]
0x180094a59  mov     [rsp+190h+lpString2], rax; lpString2
0x180094a5e  mov     [rsp+190h+var_170], ecx; unsigned int
0x180094a62  lea     rcx, [rbp+90h+var_110]; struct _GUID *
0x180094a66  movdqa  xmmword ptr [rbp+90h+var_110.Data1], xmm0
0x180094a6b  call    ?_AfxOleGetObjectDescriptorData@@YAPEAXU_GUID@@KUtagSIZE@@U_POINTL@@KPEBG3@Z; _AfxOleGetObjectDescriptorData(_GUID,ulong,tagSIZE,_POINTL,ulong,ushort const *,ushort const *)
0x180094a70  mov     rcx, [rsp+190h+pv]; pv
0x180094a75  mov     rbx, rax
0x180094a78  call    cs:__imp_CoTaskMemFree
0x180094a7e  test    edi, edi
0x180094a80  jz      short loc_180094A8D
0x180094a82  mov     rcx, [rsp+190h+var_138]; pv
0x180094a87  call    cs:__imp_CoTaskMemFree
0x180094a8d  lea     rcx, [rsp+190h+var_128]; struct IUnknown **
0x180094a92  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180094a97  lea     rcx, [rsp+190h+var_120]; struct IUnknown **
0x180094a9c  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180094aa1  lea     rcx, [rsp+190h+var_118]; struct IUnknown **
0x180094aa6  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180094aab  mov     rax, rbx
0x180094aae  mov     rcx, [rbp+90h+var_50]
0x180094ab2  xor     rcx, rsp; StackCookie
0x180094ab5  call    __security_check_cookie
0x180094aba  add     rsp, 158h
0x180094ac1  pop     r15
0x180094ac3  pop     r14
0x180094ac5  pop     r13
0x180094ac7  pop     r12
0x180094ac9  pop     rdi
0x180094aca  pop     rsi
0x180094acb  pop     rbx
0x180094acc  pop     rbp
0x180094acd  retn
```
