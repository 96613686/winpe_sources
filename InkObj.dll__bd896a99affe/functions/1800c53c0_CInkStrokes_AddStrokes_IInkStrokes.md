# CInkStrokes::AddStrokes(IInkStrokes *)

- ea: `0x1800c53c0`
- end: `0x1800c5707`
- name: `?AddStrokes@CInkStrokes@@UEAAJPEAUIInkStrokes@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(CInkStrokes *__hidden this, struct IInkStrokes *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c20`
- `0x180009b64`
- `0x180030950`
- `0x180034e08`
- `0x18007dcf4`
- `0x1800a38dc`
- `0x1800bdbec`
- `0x1800c53c0`
- `0x1800c5a74`
- `0x1800c5f20`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c5581`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c558c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c5581`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c558c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5661`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5661`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c56b3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c56b3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c55d8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c55d8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c5627`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c5627`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c55bb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c55bb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c54ed`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c5534`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c54ed`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c5534`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CInkStrokes::AddStrokes(CInkStrokes *this, struct IInkStrokes *a2)
{
  int Id; // ebx
  __int64 v5; // r8
  const unsigned __int16 *v6; // r9
  __int64 v7; // rdx
  GUID *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // rdi
  __int64 v13; // r14
  int v14; // r15d
  HRESULT v15; // eax
  void (__fastcall ***v16)(_QWORD, VARIANTARG *); // rcx
  unsigned int v18; // [rsp+28h] [rbp-A0h]
  HINSTANCE v19; // [rsp+30h] [rbp-98h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-80h] BYREF
  __int128 v21; // [rsp+60h] [rbp-68h] BYREF
  ULONG cElements; // [rsp+70h] [rbp-58h]
  VARIANTARG v23; // [rsp+80h] [rbp-48h] BYREF
  char *dwindex; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v25; // [rsp+E0h] [rbp+18h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+20h]

  if ( !a2 )
    return 2147500035LL;
  try
  {
    v25 = 0;
    Id = ((__int64 (__fastcall *)(struct IInkStrokes *, __int64 *))a2->lpVtbl->get_Ink)(a2, &v25);
    if ( v25 == ((*((_QWORD *)this + 11) + 8LL) & -(__int64)(*((_QWORD *)this + 11) != 0)) )
    {
      v9 = InkDynamicCast<CInkStrokes *,IInkStrokes *>(a2);
      v10 = v9;
      if ( v9 )
      {
        if ( *((_QWORD *)this + 11) && *(_QWORD *)(v9 + 96) )
        {
          v21 = 0;
          cElements = 0;
          v26 = v9 + 72;
          LODWORD(dwindex) = 0;
          CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v9 + 80), (LPDWORD)&dwindex);
          LODWORD(dwindex) = 0;
          CoWaitForMultipleHandles(
            0,
            0xFFFFFFFF,
            1u,
            (LPHANDLE)((((unsigned __int64)this + 64) & -(__int64)(this != (CInkStrokes *)8)) + 8),
            (LPDWORD)&dwindex);
          dwindex = *(char **)(*((_QWORD *)this + 11) + 112LL);
          InkObj_Lock();
          if ( (unsigned int)CInkBasicQueue<CStrokeWithInk,1,1,1>::CopyAllToUnique(v10 + 104, (char *)this + 96, &v21) != 1 )
            Id = -2147024882;
          CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&dwindex);
          ReleaseMutex(*(HANDLE *)((((unsigned __int64)this + 64) & -(__int64)(this != (CInkStrokes *)8)) + 8));
          ReleaseMutex(*(HANDLE *)(v10 + 80));
          if ( Id >= 0 && cElements )
          {
            dwindex = 0;
            Vector = SafeArrayCreateVector(3u, 0, cElements);
            v12 = Vector;
            if ( Vector )
            {
              Id = SafeArrayAccessData(Vector, (void **)&dwindex);
              if ( Id >= 0 )
              {
                v13 = v21;
                v14 = 0;
                while ( v13 && Id >= 0 )
                {
                  Id = InkStroke_GetId(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 16LL), &dwindex[4 * v14]);
                  if ( Id >= 0 )
                  {
                    v13 = *(_QWORD *)(v13 + 32);
                    ++v14;
                  }
                }
                v15 = SafeArrayUnaccessData(v12);
                if ( Id >= 0 )
                {
                  Id = v15;
                  if ( v15 >= 0 )
                  {
                    CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesAdded((char *)this + 32, v12);
                    if ( *((_QWORD *)this + 17) )
                    {
                      memset(&pvarg, 0, sizeof(pvarg));
                      VariantInit(&pvarg);
                      pvarg.vt = 8195;
                      pvarg.llVal = (LONGLONG)v12;
                      v16 = (void (__fastcall ***)(_QWORD, VARIANTARG *))(*((_QWORD *)this + 17) + 16LL);
                      v23 = pvarg;
                      (**v16)(v16, &v23);
                    }
                  }
                }
              }
              SafeArrayDestroy(v12);
            }
            else
            {
              Id = -2147024882;
            }
          }
          CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(&v21);
        }
        else
        {
          Id = -2147418113;
        }
        goto LABEL_30;
      }
      v19 = hInstance;
      v18 = -2144862204;
      v7 = 1105;
      v8 = &GUID_NULL;
    }
    else
    {
      if ( Id < 0 )
      {
LABEL_30:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v25);
        return (unsigned int)Id;
      }
      v19 = hInstance;
      v18 = -2144862206;
      v7 = 1107;
      v8 = &CLSID_InkStrokes;
    }
    Id = ATL::AtlSetErrorInfo(v8, (WCHAR *)v7, v5, v6, &IID_IInkStrokes, v18, v19);
    goto LABEL_30;
  }
  catch ( ... )
  {
    LODWORD(dwindex) = ReportWispException();
    return (unsigned int)dwindex;
  }
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x1800c53c0  mov     r11, rsp
0x1800c53c3  mov     [r11+8], rbx
0x1800c53c7  push    rsi
0x1800c53c8  push    rdi
0x1800c53c9  push    r12
0x1800c53cb  push    r14
0x1800c53cd  push    r15
0x1800c53cf  sub     rsp, 0A0h
0x1800c53d6  mov     rdi, rdx
0x1800c53d9  mov     rsi, rcx
0x1800c53dc  test    rdx, rdx
0x1800c53df  jz      loc_1800C56EA
0x1800c53e5  mov     qword ptr [r11+18h], 0
0x1800c53ed  mov     rax, [rdx]
0x1800c53f0  lea     rdx, [r11+18h]
0x1800c53f4  mov     rcx, rdi
0x1800c53f7  mov     rax, [rax+48h]
0x1800c53fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5400  mov     ebx, eax
0x1800c5402  mov     rax, [rsi+58h]
0x1800c5406  lea     rcx, [rax+8]
0x1800c540a  neg     rax
0x1800c540d  sbb     rax, rax
0x1800c5410  and     rax, rcx
0x1800c5413  cmp     [rsp+0C8h+arg_10], rax
0x1800c541b  jz      short loc_1800C5447
0x1800c541d  test    ebx, ebx
0x1800c541f  js      loc_1800C56CF
0x1800c5425  mov     rax, cs:hInstance
0x1800c542c  mov     [rsp+0C8h+var_98], rax
0x1800c5431  mov     [rsp+0C8h+var_A0], 80280002h
0x1800c5439  mov     edx, 453h
0x1800c543e  lea     rcx, CLSID_InkStrokes
0x1800c5445  jmp     short loc_1800C5477
0x1800c5447  mov     rcx, rdi
0x1800c544a  call    ??$InkDynamicCast@PEAVCInkStrokes@@PEAUIInkStrokes@@@@YAPEAVCInkStrokes@@PEAUIInkStrokes@@@Z; InkDynamicCast<CInkStrokes *,IInkStrokes *>(IInkStrokes *)
0x1800c544f  mov     rdi, rax
0x1800c5452  test    rax, rax
0x1800c5455  jnz     short loc_1800C548F
0x1800c5457  mov     rax, cs:hInstance
0x1800c545e  mov     [rsp+0C8h+var_98], rax; HINSTANCE
0x1800c5463  mov     [rsp+0C8h+var_A0], 80280004h; int
0x1800c546b  mov     edx, 451h; unsigned __int16 *
0x1800c5470  lea     rcx, GUID_NULL; clsid
0x1800c5477  lea     rax, IID_IInkStrokes
0x1800c547e  mov     [rsp+0C8h+lpdwindex], rax; struct _GUID *
0x1800c5483  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800c5488  mov     ebx, eax
0x1800c548a  jmp     loc_1800C56CF
0x1800c548f  cmp     qword ptr [rsi+58h], 0
0x1800c5494  jz      loc_1800C56CA
0x1800c549a  cmp     qword ptr [rax+60h], 0
0x1800c549f  jz      loc_1800C56CA
0x1800c54a5  xorps   xmm0, xmm0
0x1800c54a8  movdqu  [rsp+0C8h+var_68], xmm0
0x1800c54ae  mov     [rsp+0C8h+cElements], 0
0x1800c54b6  add     rax, 48h ; 'H'
0x1800c54ba  mov     [rsp+0C8h+arg_18], rax
0x1800c54c2  mov     dword ptr [rsp+0C8h+dwindex], 0
0x1800c54cd  lea     rax, [rsp+0C8h+dwindex]
0x1800c54d5  mov     [rsp+0C8h+lpdwindex], rax; lpdwindex
0x1800c54da  lea     r9, [rdi+50h]; pHandles
0x1800c54de  mov     r8d, 1; cHandles
0x1800c54e4  or      r12d, 0FFFFFFFFh
0x1800c54e8  mov     edx, r12d; dwTimeout
0x1800c54eb  xor     ecx, ecx; dwFlags
0x1800c54ed  call    cs:__imp_CoWaitForMultipleHandles
0x1800c54f3  nop
0x1800c54f4  lea     rax, [rsi-8]
0x1800c54f8  lea     rcx, [rsi+40h]
0x1800c54fc  neg     rax
0x1800c54ff  sbb     r8, r8
0x1800c5502  and     r8, rcx
0x1800c5505  mov     [rsp+0C8h+var_88], r8
0x1800c550a  mov     dword ptr [rsp+0C8h+dwindex], 0
0x1800c5515  lea     r15, [r8+8]
0x1800c5519  lea     rax, [rsp+0C8h+dwindex]
0x1800c5521  mov     [rsp+0C8h+lpdwindex], rax; lpdwindex
0x1800c5526  mov     r9, r15; pHandles
0x1800c5529  mov     r8d, 1; cHandles
0x1800c552f  mov     edx, r12d; dwTimeout
0x1800c5532  xor     ecx, ecx; dwFlags
0x1800c5534  call    cs:__imp_CoWaitForMultipleHandles
0x1800c553a  nop
0x1800c553b  mov     rcx, [rsi+58h]
0x1800c553f  mov     rcx, [rcx+70h]
0x1800c5543  mov     [rsp+0C8h+dwindex], rcx
0x1800c554b  call    InkObj_Lock
0x1800c5550  nop
0x1800c5551  lea     rdx, [rsi+60h]
0x1800c5555  lea     rcx, [rdi+68h]
0x1800c5559  lea     r8, [rsp+0C8h+var_68]
0x1800c555e  call    ?CopyAllToUnique@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAHAEAV1@PEAV1@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::CopyAllToUnique(CInkBasicQueue<CStrokeWithInk,1,1,1> &,CInkBasicQueue<CStrokeWithInk,1,1,1> *)
0x1800c5563  mov     r12d, 8007000Eh
0x1800c5569  cmp     eax, 1
0x1800c556c  cmovnz  ebx, r12d
0x1800c5570  lea     rcx, [rsp+0C8h+dwindex]; this
0x1800c5578  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c557d  nop
0x1800c557e  mov     rcx, [r15]; hMutex
0x1800c5581  call    cs:__imp_ReleaseMutex
0x1800c5587  nop
0x1800c5588  mov     rcx, [rdi+50h]; hMutex
0x1800c558c  call    cs:__imp_ReleaseMutex
0x1800c5592  test    ebx, ebx
0x1800c5594  js      loc_1800C56BE
0x1800c559a  mov     r8d, [rsp+0C8h+cElements]; cElements
0x1800c559f  test    r8d, r8d
0x1800c55a2  jz      loc_1800C56BE
0x1800c55a8  mov     [rsp+0C8h+dwindex], 0
0x1800c55b4  mov     ecx, 3; vt
0x1800c55b9  xor     edx, edx; lLbound
0x1800c55bb  call    cs:__imp_SafeArrayCreateVector
0x1800c55c1  mov     rdi, rax
0x1800c55c4  test    rax, rax
0x1800c55c7  jz      loc_1800C56BB
0x1800c55cd  lea     rdx, [rsp+0C8h+dwindex]; ppvData
0x1800c55d5  mov     rcx, rax; psa
0x1800c55d8  call    cs:__imp_SafeArrayAccessData
0x1800c55de  mov     ebx, eax
0x1800c55e0  test    eax, eax
0x1800c55e2  js      loc_1800C56B0
0x1800c55e8  mov     r14, qword ptr [rsp+0C8h+var_68]
0x1800c55ed  xor     r15d, r15d
0x1800c55f0  jmp     short loc_1800C561F
0x1800c55f2  test    ebx, ebx
0x1800c55f4  js      short loc_1800C5624
0x1800c55f6  movsxd  rcx, r15d
0x1800c55f9  mov     rax, [rsp+0C8h+dwindex]
0x1800c5601  lea     rdx, [rax+rcx*4]
0x1800c5605  mov     rcx, [r14+10h]
0x1800c5609  mov     rcx, [rcx+10h]
0x1800c560d  call    InkStroke_GetId
0x1800c5612  mov     ebx, eax
0x1800c5614  test    eax, eax
0x1800c5616  js      short loc_1800C561F
0x1800c5618  mov     r14, [r14+20h]
0x1800c561c  inc     r15d
0x1800c561f  test    r14, r14
0x1800c5622  jnz     short loc_1800C55F2
0x1800c5624  mov     rcx, rdi; psa
0x1800c5627  call    cs:__imp_SafeArrayUnaccessData
0x1800c562d  test    ebx, ebx
0x1800c562f  js      short loc_1800C56B0
0x1800c5631  mov     ebx, eax
0x1800c5633  test    eax, eax
0x1800c5635  js      short loc_1800C56B0
0x1800c5637  lea     rcx, [rsi+20h]
0x1800c563b  mov     rdx, rdi
0x1800c563e  call    ?Fire_StrokesAdded@?$CProxy_IInkStrokesEvents@VCInkStrokes@@@@QEAAJPEAUtagSAFEARRAY@@@Z; CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesAdded(tagSAFEARRAY *)
0x1800c5643  cmp     qword ptr [rsi+88h], 0
0x1800c564b  jz      short loc_1800C56B0
0x1800c564d  xorps   xmm0, xmm0
0x1800c5650  xor     eax, eax
0x1800c5652  movups  xmmword ptr [rsp+0C8h+pvarg], xmm0
0x1800c5657  mov     qword ptr [rsp+0C8h+pvarg+10h], rax
0x1800c565c  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800c5661  call    cs:__imp_VariantInit
0x1800c5667  mov     eax, 2003h
0x1800c566c  mov     word ptr [rsp+0C8h+pvarg], ax
0x1800c5671  mov     qword ptr [rsp+0C8h+pvarg+8], rdi
0x1800c5676  mov     rcx, [rsi+88h]
0x1800c567d  add     rcx, 10h
0x1800c5681  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x1800c5686  movaps  [rsp+0C8h+var_48], xmm0
0x1800c568e  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x1800c5694  movsd   [rsp+0C8h+var_38], xmm1
0x1800c569d  mov     rax, [rcx]
0x1800c56a0  lea     rdx, [rsp+0C8h+var_48]
0x1800c56a8  mov     rax, [rax]
0x1800c56ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c56b0  mov     rcx, rdi; psa
0x1800c56b3  call    cs:__imp_SafeArrayDestroy
0x1800c56b9  jmp     short loc_1800C56BE
0x1800c56bb  mov     ebx, r12d
0x1800c56be  lea     rcx, [rsp+0C8h+var_68]
0x1800c56c3  call    ??1?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAA@XZ; CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(void)
0x1800c56c8  jmp     short loc_1800C56CF
0x1800c56ca  mov     ebx, 8000FFFFh
0x1800c56cf  lea     rcx, [rsp+0C8h+arg_10]; void *
0x1800c56d7  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800c56dc  nop
0x1800c56dd  jmp     short loc_1800C56E6
0x1800c56df  mov     ebx, dword ptr [rsp+0C8h+dwindex]
0x1800c56e6  mov     eax, ebx
0x1800c56e8  jmp     short loc_1800C56EF
0x1800c56ea  mov     eax, 80004003h
0x1800c56ef  mov     rbx, [rsp+0C8h+arg_0]
0x1800c56f7  add     rsp, 0A0h
0x1800c56fe  pop     r15
0x1800c5700  pop     r14
0x1800c5702  pop     r12
0x1800c5704  pop     rdi
0x1800c5705  pop     rsi
0x1800c5706  retn
```
