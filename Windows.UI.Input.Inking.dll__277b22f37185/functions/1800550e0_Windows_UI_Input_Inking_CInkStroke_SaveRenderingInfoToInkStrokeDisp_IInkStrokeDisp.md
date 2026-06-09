# Windows::UI::Input::Inking::CInkStroke::SaveRenderingInfoToInkStrokeDisp(IInkStrokeDisp *)

- ea: `0x1800550e0`
- end: `0x1800554e0`
- name: `?SaveRenderingInfoToInkStrokeDisp@CInkStroke@Inking@Input@UI@Windows@@UEAAJPEAUIInkStrokeDisp@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStroke *__hidden this, struct IInkStrokeDisp *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001043c`
- `0x1800550e0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800554b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800554b4`
- `OLEAUT32!__imp_SysAllocString` at `0x180055176`
- `OLEAUT32!__imp_SysAllocString` at `0x180055176`
- `OLEAUT32!__imp_SysFreeString` at `0x180055495`
- `OLEAUT32!__imp_SysFreeString` at `0x180055495`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180055485`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180055485`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005525f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005525f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180055418`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180055418`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005523e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005523e`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::SaveRenderingInfoToInkStrokeDisp(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2)
{
  struct IInkStrokeDispVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_ExtendedProperties)(IInkStrokeDisp *, IInkExtendedProperties **); // rbx
  HRESULT v7; // ebx
  OLECHAR *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // r10
  __int64 v15; // r9
  int v16; // r11d
  __int64 v17; // r11
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, OLECHAR *, _QWORD *, __int64 *); // rbx
  void *ppvData; // [rsp+30h] [rbp-49h] BYREF
  int v21; // [rsp+38h] [rbp-41h] BYREF
  __int64 v22; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+48h] [rbp-31h] BYREF
  __int64 v24; // [rsp+50h] [rbp-29h] BYREF
  int v25; // [rsp+58h] [rbp-21h] BYREF
  __int64 v26; // [rsp+60h] [rbp-19h] BYREF
  __int64 v27; // [rsp+68h] [rbp-11h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v29[4]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v30; // [rsp+A0h] [rbp+27h] BYREF
  int v31; // [rsp+A8h] [rbp+2Fh]

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 280);
  if ( *((_QWORD *)this + 25) )
  {
    lpVtbl = a2->lpVtbl;
    v24 = 0;
    get_ExtendedProperties = lpVtbl->get_ExtendedProperties;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    v7 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))get_ExtendedProperties)(a2, &v24);
    if ( v7 >= 0 )
    {
      v8 = SysAllocString(L"{29079F6D-5576-4612-8B05-C526280D067B}");
      if ( v8 )
      {
        v9 = *((_QWORD *)this + 25);
        v30 = 0;
        v31 = 0;
        v22 = 0;
        v21 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 88LL))(v9, &v30);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64 *))(**((_QWORD **)this + 25) + 96LL))(
                 *((_QWORD *)this + 25),
                 &v21,
                 &v22);
          if ( v7 >= 0 )
          {
            if ( v22 )
            {
              v10 = *((_QWORD *)this + 25);
              v26 = 0;
              v25 = 0;
              v23 = 0;
              v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *, __int64 *))(*(_QWORD *)v10 + 104LL))(
                     v10,
                     &v26,
                     &v25,
                     &v23);
              if ( v7 >= 0 )
              {
                if ( v23 )
                {
                  Vector = SafeArrayCreateVector(4u, 0, 15 * v21 + 6);
                  v12 = Vector;
                  if ( Vector )
                  {
                    ppvData = 0;
                    v7 = SafeArrayAccessData(Vector, &ppvData);
                    if ( v7 < 0 )
                    {
                      SafeArrayDestroy(v12);
                    }
                    else
                    {
                      v13 = 0;
                      *(float *)ppvData = (float)v21;
                      *(_QWORD *)((char *)ppvData + 4) = v30;
                      *((_DWORD *)ppvData + 3) = v31;
                      for ( *((_QWORD *)ppvData + 2) = v26;
                            (unsigned int)v13 < v21;
                            *((_DWORD *)ppvData + (unsigned int)(v17 + 14)) = *(_DWORD *)(v23 + 8 * v15 + 20) )
                      {
                        v14 = 9 * v13;
                        v15 = 3 * v13;
                        v16 = 15 * v13;
                        v13 = (unsigned int)(v13 + 1);
                        v17 = (unsigned int)(v16 + 6);
                        *((_DWORD *)ppvData + v17) = *(_DWORD *)(v22 + 4 * v14);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 1)) = *(_DWORD *)(v22 + 4 * v14 + 4);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 2)) = *(_DWORD *)(v22 + 4 * v14 + 8);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 3)) = *(_DWORD *)(v23 + 8 * v15);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 4)) = *(_DWORD *)(v23 + 8 * v15 + 4);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 5)) = *(_DWORD *)(v22 + 4 * v14 + 12);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 6)) = *(_DWORD *)(v22 + 4 * v14 + 16);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 7)) = *(_DWORD *)(v22 + 4 * v14 + 20);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 8)) = *(_DWORD *)(v23 + 8 * v15 + 8);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 9)) = *(_DWORD *)(v23 + 8 * v15 + 12);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 10)) = *(_DWORD *)(v22 + 4 * v14 + 24);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 11)) = *(_DWORD *)(v22 + 4 * v14 + 28);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 12)) = *(_DWORD *)(v22 + 4 * v14 + 32);
                        *((_DWORD *)ppvData + (unsigned int)(v17 + 13)) = *(_DWORD *)(v23 + 8 * v15 + 16);
                      }
                      v7 = SafeArrayUnaccessData(v12);
                      if ( v7 >= 0 )
                      {
                        v29[0] = 8196;
                        v29[1] = v12;
                        v18 = v24;
                        v27 = 0;
                        v19 = *(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *, __int64 *))(*(_QWORD *)v24 + 80LL);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
                        v29[2] = 0;
                        v7 = v19(v18, v8, v29, &v27);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
                      }
                    }
                  }
                  else
                  {
                    v7 = -2147024882;
                  }
                }
              }
            }
          }
        }
        SysFreeString(v8);
      }
      else
      {
        v7 = -2147024882;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    return (unsigned int)v7;
  }
  else
  {
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x1800550e0  mov     [rsp-8+arg_10], rbx
0x1800550e5  mov     [rsp-8+arg_18], rsi
0x1800550ea  push    rbp
0x1800550eb  push    rdi
0x1800550ec  push    r14
0x1800550ee  lea     rbp, [rsp-47h]
0x1800550f3  sub     rsp, 0C0h
0x1800550fa  mov     rax, cs:__security_cookie
0x180055101  xor     rax, rsp
0x180055104  mov     [rbp+57h+var_20], rax
0x180055108  mov     rsi, rdx
0x18005510b  mov     rdi, rcx
0x18005510e  lea     rdx, [rcx+118h]
0x180055115  lea     rcx, [rbp+57h+SRWLock]
0x180055119  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005511e  cmp     qword ptr [rdi+0C8h], 0
0x180055126  jnz     short loc_18005513E
0x180055128  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005512c  test    rcx, rcx
0x18005512f  jz      short loc_180055137
0x180055131  call    cs:__imp_ReleaseSRWLockExclusive
0x180055137  xor     eax, eax
0x180055139  jmp     loc_1800554BC
0x18005513e  mov     rax, [rsi]
0x180055141  lea     rcx, [rbp+57h+var_80]
0x180055145  mov     [rbp+57h+var_80], 0
0x18005514d  mov     rbx, [rax+60h]
0x180055151  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055156  lea     rdx, [rbp+57h+var_80]
0x18005515a  mov     rcx, rsi
0x18005515d  mov     rax, rbx
0x180055160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055165  mov     ebx, eax
0x180055167  test    eax, eax
0x180055169  js      loc_1800554A2
0x18005516f  lea     rcx, a29079f6d557646; "{29079F6D-5576-4612-8B05-C526280D067B}"
0x180055176  call    cs:__imp_SysAllocString
0x18005517c  mov     rsi, rax
0x18005517f  test    rax, rax
0x180055182  jz      loc_18005549D
0x180055188  mov     rcx, [rdi+0C8h]
0x18005518f  xor     eax, eax
0x180055191  mov     [rbp+57h+var_30], rax
0x180055195  mov     [rbp+57h+var_28], eax
0x180055198  mov     [rbp+57h+var_90], rax
0x18005519c  mov     [rbp+57h+var_98], 0
0x1800551a3  mov     rdx, [rcx]
0x1800551a6  mov     rax, [rdx+58h]
0x1800551aa  lea     rdx, [rbp+57h+var_30]
0x1800551ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551b3  mov     ebx, eax
0x1800551b5  test    eax, eax
0x1800551b7  js      loc_180055492
0x1800551bd  mov     rcx, [rdi+0C8h]
0x1800551c4  lea     r8, [rbp+57h+var_90]
0x1800551c8  lea     rdx, [rbp+57h+var_98]
0x1800551cc  mov     rax, [rcx]
0x1800551cf  mov     rax, [rax+60h]
0x1800551d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551d8  mov     ebx, eax
0x1800551da  test    eax, eax
0x1800551dc  js      loc_180055492
0x1800551e2  cmp     [rbp+57h+var_90], 0
0x1800551e7  jz      loc_180055492
0x1800551ed  mov     rcx, [rdi+0C8h]
0x1800551f4  lea     r9, [rbp+57h+var_88]
0x1800551f8  xor     eax, eax
0x1800551fa  lea     r8, [rbp+57h+var_78]
0x1800551fe  mov     [rbp+57h+var_70], rax
0x180055202  lea     rdx, [rbp+57h+var_70]
0x180055206  mov     [rbp+57h+var_78], eax
0x180055209  mov     [rbp+57h+var_88], rax
0x18005520d  mov     rax, [rcx]
0x180055210  mov     rax, [rax+68h]
0x180055214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055219  mov     ebx, eax
0x18005521b  test    eax, eax
0x18005521d  js      loc_180055492
0x180055223  cmp     [rbp+57h+var_88], 0
0x180055228  jz      loc_180055492
0x18005522e  imul    r8d, [rbp+57h+var_98], 0Fh
0x180055233  mov     ecx, 4; vt
0x180055238  xor     edx, edx; lLbound
0x18005523a  add     r8d, 6; cElements
0x18005523e  call    cs:__imp_SafeArrayCreateVector
0x180055244  mov     rdi, rax
0x180055247  test    rax, rax
0x18005524a  jz      loc_18005548D
0x180055250  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180055254  mov     [rbp+57h+ppvData], 0
0x18005525c  mov     rcx, rax; psa
0x18005525f  call    cs:__imp_SafeArrayAccessData
0x180055265  mov     ebx, eax
0x180055267  test    eax, eax
0x180055269  js      loc_180055482
0x18005526f  mov     ecx, [rbp+57h+var_98]
0x180055272  xorps   xmm0, xmm0
0x180055275  xor     ebx, ebx
0x180055277  cvtsi2ss xmm0, rcx
0x18005527c  mov     rcx, [rbp+57h+ppvData]
0x180055280  movss   dword ptr [rcx], xmm0
0x180055284  mov     rax, [rbp+57h+ppvData]
0x180055288  movss   xmm0, dword ptr [rbp+57h+var_30]
0x18005528d  movss   dword ptr [rax+4], xmm0
0x180055292  mov     rax, [rbp+57h+ppvData]
0x180055296  movss   xmm1, dword ptr [rbp+57h+var_30+4]
0x18005529b  movss   dword ptr [rax+8], xmm1
0x1800552a0  mov     rax, [rbp+57h+ppvData]
0x1800552a4  movss   xmm0, [rbp+57h+var_28]
0x1800552a9  movss   dword ptr [rax+0Ch], xmm0
0x1800552ae  mov     rax, [rbp+57h+ppvData]
0x1800552b2  movss   xmm1, dword ptr [rbp+57h+var_70]
0x1800552b7  movss   dword ptr [rax+10h], xmm1
0x1800552bc  mov     rax, [rbp+57h+ppvData]
0x1800552c0  movss   xmm0, dword ptr [rbp+57h+var_70+4]
0x1800552c5  movss   dword ptr [rax+14h], xmm0
0x1800552ca  cmp     [rbp+57h+var_98], ebx
0x1800552cd  jbe     loc_180055415
0x1800552d3  mov     rax, [rbp+57h+var_90]
0x1800552d7  lea     r10, [rbx+rbx*8]
0x1800552db  lea     r9, [rbx+rbx*2]
0x1800552df  imul    r11d, ebx, 0Fh
0x1800552e3  inc     ebx
0x1800552e5  mov     ecx, [rax+r10*4]
0x1800552e9  mov     rax, [rbp+57h+ppvData]
0x1800552ed  add     r11d, 6
0x1800552f1  mov     [rax+r11*4], ecx
0x1800552f5  lea     edx, [r11+1]
0x1800552f9  mov     rax, [rbp+57h+var_90]
0x1800552fd  mov     ecx, [rax+r10*4+4]
0x180055302  mov     rax, [rbp+57h+ppvData]
0x180055306  mov     [rax+rdx*4], ecx
0x180055309  lea     edx, [r11+2]
0x18005530d  mov     rax, [rbp+57h+var_90]
0x180055311  mov     ecx, [rax+r10*4+8]
0x180055316  mov     rax, [rbp+57h+ppvData]
0x18005531a  mov     [rax+rdx*4], ecx
0x18005531d  lea     edx, [r11+3]
0x180055321  mov     rax, [rbp+57h+var_88]
0x180055325  mov     ecx, [rax+r9*8]
0x180055329  mov     rax, [rbp+57h+ppvData]
0x18005532d  mov     [rax+rdx*4], ecx
0x180055330  lea     edx, [r11+4]
0x180055334  mov     rax, [rbp+57h+var_88]
0x180055338  mov     ecx, [rax+r9*8+4]
0x18005533d  mov     rax, [rbp+57h+ppvData]
0x180055341  mov     [rax+rdx*4], ecx
0x180055344  lea     edx, [r11+5]
0x180055348  mov     rax, [rbp+57h+var_90]
0x18005534c  mov     ecx, [rax+r10*4+0Ch]
0x180055351  mov     rax, [rbp+57h+ppvData]
0x180055355  mov     [rax+rdx*4], ecx
0x180055358  lea     edx, [r11+6]
0x18005535c  mov     rax, [rbp+57h+var_90]
0x180055360  mov     ecx, [rax+r10*4+10h]
0x180055365  mov     rax, [rbp+57h+ppvData]
0x180055369  mov     [rax+rdx*4], ecx
0x18005536c  lea     edx, [r11+7]
0x180055370  mov     rax, [rbp+57h+var_90]
0x180055374  mov     ecx, [rax+r10*4+14h]
0x180055379  mov     rax, [rbp+57h+ppvData]
0x18005537d  mov     [rax+rdx*4], ecx
0x180055380  lea     edx, [r11+8]
0x180055384  mov     rax, [rbp+57h+var_88]
0x180055388  mov     ecx, [rax+r9*8+8]
0x18005538d  mov     rax, [rbp+57h+ppvData]
0x180055391  mov     [rax+rdx*4], ecx
0x180055394  lea     edx, [r11+9]
0x180055398  mov     rax, [rbp+57h+var_88]
0x18005539c  mov     ecx, [rax+r9*8+0Ch]
0x1800553a1  mov     rax, [rbp+57h+ppvData]
0x1800553a5  mov     [rax+rdx*4], ecx
0x1800553a8  lea     edx, [r11+0Ah]
0x1800553ac  mov     rax, [rbp+57h+var_90]
0x1800553b0  mov     ecx, [rax+r10*4+18h]
0x1800553b5  mov     rax, [rbp+57h+ppvData]
0x1800553b9  mov     [rax+rdx*4], ecx
0x1800553bc  lea     edx, [r11+0Bh]
0x1800553c0  mov     rax, [rbp+57h+var_90]
0x1800553c4  mov     ecx, [rax+r10*4+1Ch]
0x1800553c9  mov     rax, [rbp+57h+ppvData]
0x1800553cd  mov     [rax+rdx*4], ecx
0x1800553d0  lea     edx, [r11+0Ch]
0x1800553d4  mov     rax, [rbp+57h+var_90]
0x1800553d8  mov     ecx, [rax+r10*4+20h]
0x1800553dd  mov     rax, [rbp+57h+ppvData]
0x1800553e1  mov     [rax+rdx*4], ecx
0x1800553e4  lea     edx, [r11+0Dh]
0x1800553e8  mov     rax, [rbp+57h+var_88]
0x1800553ec  mov     ecx, [rax+r9*8+10h]
0x1800553f1  mov     rax, [rbp+57h+ppvData]
0x1800553f5  mov     [rax+rdx*4], ecx
0x1800553f8  lea     edx, [r11+0Eh]
0x1800553fc  mov     rax, [rbp+57h+var_88]
0x180055400  mov     ecx, [rax+r9*8+14h]
0x180055405  mov     rax, [rbp+57h+ppvData]
0x180055409  mov     [rax+rdx*4], ecx
0x18005540c  cmp     ebx, [rbp+57h+var_98]
0x18005540f  jb      loc_1800552D3
0x180055415  mov     rcx, rdi; psa
0x180055418  call    cs:__imp_SafeArrayUnaccessData
0x18005541e  mov     ebx, eax
0x180055420  test    eax, eax
0x180055422  js      short loc_180055492
0x180055424  xorps   xmm0, xmm0
0x180055427  lea     rcx, [rbp+57h+var_68]
0x18005542b  movups  [rbp+57h+var_50], xmm0
0x18005542f  mov     eax, 2004h
0x180055434  mov     qword ptr [rbp+57h+var_50+8], rdi
0x180055438  mov     rdi, [rbp+57h+var_80]
0x18005543c  xor     r14d, r14d
0x18005543f  mov     word ptr [rbp+57h+var_50], ax
0x180055443  mov     [rbp+57h+var_68], r14
0x180055447  mov     rax, [rdi]
0x18005544a  mov     rbx, [rax+50h]
0x18005544e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055453  movups  xmm0, [rbp+57h+var_50]
0x180055457  lea     r9, [rbp+57h+var_68]
0x18005545b  mov     [rbp+57h+var_40], r14
0x18005545f  lea     r8, [rbp+57h+var_50]
0x180055463  mov     rdx, rsi
0x180055466  mov     rcx, rdi
0x180055469  movaps  [rbp+57h+var_50], xmm0
0x18005546d  mov     rax, rbx
0x180055470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055475  lea     rcx, [rbp+57h+var_68]
0x180055479  mov     ebx, eax
0x18005547b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055480  jmp     short loc_180055492
0x180055482  mov     rcx, rdi; psa
0x180055485  call    cs:__imp_SafeArrayDestroy
0x18005548b  jmp     short loc_180055492
0x18005548d  mov     ebx, 8007000Eh
0x180055492  mov     rcx, rsi; bstrString
0x180055495  call    cs:__imp_SysFreeString
0x18005549b  jmp     short loc_1800554A2
0x18005549d  mov     ebx, 8007000Eh
0x1800554a2  lea     rcx, [rbp+57h+var_80]
0x1800554a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800554ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800554af  test    rcx, rcx
0x1800554b2  jz      short loc_1800554BA
0x1800554b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800554ba  mov     eax, ebx
0x1800554bc  mov     rcx, [rbp+57h+var_20]
0x1800554c0  xor     rcx, rsp; StackCookie
0x1800554c3  call    __security_check_cookie
0x1800554c8  lea     r11, [rsp+0D0h+var_10]
0x1800554d0  mov     rbx, [r11+30h]
0x1800554d4  mov     rsi, [r11+38h]
0x1800554d8  mov     rsp, r11
0x1800554db  pop     r14
0x1800554dd  pop     rdi
0x1800554de  pop     rbp
0x1800554df  retn
```
