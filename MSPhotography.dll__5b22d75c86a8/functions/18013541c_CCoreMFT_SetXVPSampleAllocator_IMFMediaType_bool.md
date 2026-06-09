# CCoreMFT::SetXVPSampleAllocator(IMFMediaType *,bool)

- ea: `0x18013541c`
- end: `0x1801356da`
- name: `?SetXVPSampleAllocator@CCoreMFT@@AEAAJPEAUIMFMediaType@@_N@Z`
- size: `702`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, struct IMFMediaType *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180132010`

## callees

- `0x18000290c`
- `0x18000c0f8`
- `0x1800280e4`
- `0x18002bb98`
- `0x1801316bc`
- `0x180131748`
- `0x1801350a4`
- `0x18013541c`
- `0x180135fe4`
- `0x180136048`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1801354a7`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1801354a7`

## pseudocode

```c
__int64 __fastcall CCoreMFT::SetXVPSampleAllocator(CCoreMFT *this, struct IMFMediaType *a2, char a3)
{
  unsigned int v3; // ebp
  __int64 v4; // rsi
  _QWORD *v8; // r15
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // edi
  _QWORD *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rsi
  CCoreMFT::XVPSampleAllocator *v16; // rax
  CCoreMFT::XVPSampleAllocator *v17; // rsi
  __int64 v18; // rbp
  __int64 v19; // rbp
  int v21; // [rsp+60h] [rbp+8h] BYREF
  __int64 v22; // [rsp+78h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 64);
  v4 = 0;
  v21 = 0;
  if ( v3 )
  {
    while ( 1 )
    {
      v8 = *(_QWORD **)(*((_QWORD *)this + 31) + 8 * v4);
      v9 = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaType *, __int64, int *))(*(_QWORD *)*v8 + 48LL))(
             *v8,
             a2,
             2,
             &v21);
      v12 = v9;
      if ( v9 < 0 )
        break;
      if ( v21 )
      {
        v15 = v8[1];
        if ( *((_QWORD *)this + 34) != v15 )
        {
          v22 = v8[1];
          Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v22);
          v22 = *((_QWORD *)this + 34);
          *((_QWORD *)this + 34) = v15;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v22);
        }
        goto LABEL_30;
      }
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= v3 )
        goto LABEL_5;
    }
    if ( !g_wppLevels )
      goto LABEL_30;
    v14 = 176;
    goto LABEL_12;
  }
LABEL_5:
  v13 = (_QWORD *)((char *)this + 272);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease((char *)this + 272);
  v9 = MFCreateVideoSampleAllocatorEx(&IID_IMFVideoSampleAllocatorEx, (void **)this + 34);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v14 = 177;
    goto LABEL_12;
  }
  if ( a3
    && (v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v13 + 24LL))(*v13, *((_QWORD *)this + 20)),
        v12 = v9,
        v9 < 0) )
  {
    if ( g_wppLevels )
    {
      v14 = 178;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v9);
    }
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IMFMediaType *))(*(_QWORD *)*v13 + 56LL))(
           *v13,
           1,
           *((unsigned int *)this + 27),
           *((_QWORD *)this + 35),
           a2);
    v12 = v9;
    if ( v9 >= 0 )
    {
      if ( g_wppLevels >= 0x20u )
        WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, v11, this, *((_QWORD *)this + 20), *v13);
      v16 = (CCoreMFT::XVPSampleAllocator *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v17 = v16;
      if ( v16 )
      {
        *(_QWORD *)v16 = 0;
        *((_QWORD *)v16 + 1) = 0;
        Microsoft::WRL::ComPtr<IMFMediaType>::operator=(v16, a2);
        v18 = *((_QWORD *)this + 34);
        if ( *((_QWORD *)v17 + 1) != v18 )
        {
          v22 = *((_QWORD *)this + 34);
          Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v22);
          v22 = *((_QWORD *)v17 + 1);
          *((_QWORD *)v17 + 1) = v18;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v22);
        }
        v19 = *((unsigned int *)this + 64);
        if ( (unsigned int)CTEntryArray<CCoreMFT::XVPSampleAllocator *>::SetSize(
                             (char *)this + 248,
                             (unsigned int)(v19 + 1)) )
        {
          *(_QWORD *)(*((_QWORD *)this + 31) + 8 * v19) = v17;
        }
        else
        {
          CCoreMFT::XVPSampleAllocator::`scalar deleting destructor'(v17, v10);
          v12 = -2147024882;
        }
      }
      else
      {
        v12 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            181,
            &WPP_55bf114490c93d008a53f926557b4d05_Traceguids,
            this,
            -2147024882);
      }
    }
    else if ( g_wppLevels )
    {
      v14 = 179;
      goto LABEL_12;
    }
  }
LABEL_30:
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, this, *((_QWORD *)this + 34), v12);
  return v12;
}

```

## disassembly

```asm
0x18013541c  mov     [rsp+arg_8], rbx
0x180135421  mov     [rsp+arg_10], rbp
0x180135426  push    rsi
0x180135427  push    rdi
0x180135428  push    r12
0x18013542a  push    r14
0x18013542c  push    r15
0x18013542e  sub     rsp, 30h
0x180135432  mov     ebp, [rcx+100h]
0x180135438  xor     esi, esi
0x18013543a  mov     [rsp+58h+arg_0], 0
0x180135442  mov     r12b, r8b
0x180135445  mov     r14, rdx
0x180135448  mov     rbx, rcx
0x18013544b  test    ebp, ebp
0x18013544d  jz      short loc_18013548E
0x18013544f  mov     rax, [rbx+0F8h]
0x180135456  lea     r9, [rsp+58h+arg_0]
0x18013545b  mov     r8d, 2
0x180135461  mov     rdx, r14
0x180135464  mov     r15, [rax+rsi*8]
0x180135468  mov     rcx, [r15]
0x18013546b  mov     rax, [rcx]
0x18013546e  mov     rax, [rax+30h]
0x180135472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135477  mov     edi, eax
0x180135479  test    eax, eax
0x18013547b  js      loc_180135509
0x180135481  cmp     [rsp+58h+arg_0], 0
0x180135486  jnz     short loc_1801354C7
0x180135488  inc     esi
0x18013548a  cmp     esi, ebp
0x18013548c  jb      short loc_18013544F
0x18013548e  lea     rsi, [rbx+110h]
0x180135495  mov     rcx, rsi
0x180135498  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18013549d  mov     rdx, rsi; ppSampleAllocator
0x1801354a0  lea     rcx, IID_IMFVideoSampleAllocatorEx; riid
0x1801354a7  call    cs:__imp_MFCreateVideoSampleAllocatorEx
0x1801354ad  mov     edi, eax
0x1801354af  test    eax, eax
0x1801354b1  jns     short loc_180135524
0x1801354b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801354ba  jb      loc_180135695
0x1801354c0  mov     edx, 0B1h
0x1801354c5  jmp     short loc_18013551B
0x1801354c7  mov     rsi, [r15+8]
0x1801354cb  cmp     [rbx+110h], rsi
0x1801354d2  jz      loc_180135695
0x1801354d8  lea     rcx, [rsp+58h+arg_18]
0x1801354dd  mov     [rsp+58h+arg_18], rsi
0x1801354e2  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x1801354e7  mov     rax, [rbx+110h]
0x1801354ee  lea     rcx, [rsp+58h+arg_18]
0x1801354f3  mov     [rsp+58h+arg_18], rax
0x1801354f8  mov     [rbx+110h], rsi
0x1801354ff  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180135504  jmp     loc_180135695
0x180135509  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180135510  jb      loc_180135695
0x180135516  mov     edx, 0B0h
0x18013551b  mov     dword ptr [rsp+58h+var_38], eax
0x18013551f  jmp     loc_18013567B
0x180135524  test    r12b, r12b
0x180135527  jz      short loc_180135559
0x180135529  mov     rcx, [rsi]
0x18013552c  mov     rdx, [rbx+0A0h]
0x180135533  mov     rax, [rcx]
0x180135536  mov     rax, [rax+18h]
0x18013553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013553f  mov     edi, eax
0x180135541  test    eax, eax
0x180135543  jns     short loc_180135559
0x180135545  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013554c  jb      loc_180135695
0x180135552  mov     edx, 0B2h
0x180135557  jmp     short loc_18013551B
0x180135559  mov     rcx, [rsi]
0x18013555c  mov     edx, 1
0x180135561  mov     r9, [rbx+118h]
0x180135568  mov     r8d, [rbx+6Ch]
0x18013556c  mov     [rsp+58h+var_38], r14
0x180135571  mov     rax, [rcx]
0x180135574  mov     rax, [rax+38h]
0x180135578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013557d  mov     edi, eax
0x18013557f  test    eax, eax
0x180135581  jns     short loc_180135597
0x180135583  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013558a  jb      loc_180135695
0x180135590  mov     edx, 0B3h
0x180135595  jmp     short loc_18013551B
0x180135597  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18013559e  jb      short loc_1801355CC
0x1801355a0  mov     rax, [rsi]
0x1801355a3  mov     edx, 0B4h
0x1801355a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801355af  mov     r9, rbx
0x1801355b2  mov     [rsp+58h+var_30], rax
0x1801355b7  mov     rax, [rbx+0A0h]
0x1801355be  mov     [rsp+58h+var_38], rax
0x1801355c3  mov     rcx, [rcx+10h]
0x1801355c7  call    WPP_SF_qqq
0x1801355cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801355d3  mov     ecx, 10h; unsigned __int64
0x1801355d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801355dd  mov     rsi, rax
0x1801355e0  test    rax, rax
0x1801355e3  jz      short loc_180135664
0x1801355e5  mov     rdx, r14
0x1801355e8  mov     qword ptr [rax], 0
0x1801355ef  mov     rcx, rax
0x1801355f2  mov     qword ptr [rax+8], 0
0x1801355fa  call    ??4?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFMediaType@@@Z; Microsoft::WRL::ComPtr<IMFMediaType>::operator=(IMFMediaType *)
0x1801355ff  mov     rbp, [rbx+110h]
0x180135606  cmp     [rsi+8], rbp
0x18013560a  jz      short loc_180135632
0x18013560c  lea     rcx, [rsp+58h+arg_18]
0x180135611  mov     [rsp+58h+arg_18], rbp
0x180135616  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x18013561b  mov     rax, [rsi+8]
0x18013561f  lea     rcx, [rsp+58h+arg_18]
0x180135624  mov     [rsp+58h+arg_18], rax
0x180135629  mov     [rsi+8], rbp
0x18013562d  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180135632  lea     r14, [rbx+0F8h]
0x180135639  mov     ebp, [r14+8]
0x18013563d  mov     rcx, r14
0x180135640  lea     edx, [rbp+1]
0x180135643  call    ?SetSize@?$CTEntryArray@PEAUXVPSampleAllocator@CCoreMFT@@@@QEAAHKK@Z; CTEntryArray<CCoreMFT::XVPSampleAllocator *>::SetSize(ulong,ulong)
0x180135648  test    eax, eax
0x18013564a  jnz     short loc_18013565B
0x18013564c  mov     rcx, rsi; this
0x18013564f  call    ??_GXVPSampleAllocator@CCoreMFT@@QEAAPEAXI@Z; CCoreMFT::XVPSampleAllocator::`scalar deleting destructor'(uint)
0x180135654  mov     edi, 8007000Eh
0x180135659  jmp     short loc_180135695
0x18013565b  mov     rax, [r14]
0x18013565e  mov     [rax+rbp*8], rsi
0x180135662  jmp     short loc_180135695
0x180135664  mov     edi, 8007000Eh
0x180135669  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180135670  jb      short loc_180135695
0x180135672  mov     edx, 0B5h
0x180135677  mov     dword ptr [rsp+58h+var_38], edi
0x18013567b  mov     rcx, cs:WPP_GLOBAL_Control
0x180135682  lea     r8, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x180135689  mov     r9, rbx
0x18013568c  mov     rcx, [rcx+10h]
0x180135690  call    WPP_SF_qD
0x180135695  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18013569c  jb      short loc_1801356C1
0x18013569e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801356a5  mov     r9, rbx
0x1801356a8  mov     rax, [rbx+110h]
0x1801356af  mov     dword ptr [rsp+58h+var_30], edi
0x1801356b3  mov     [rsp+58h+var_38], rax
0x1801356b8  mov     rcx, [rcx+10h]
0x1801356bc  call    WPP_SF_qqD
0x1801356c1  mov     rbx, [rsp+58h+arg_8]
0x1801356c6  mov     eax, edi
0x1801356c8  mov     rbp, [rsp+58h+arg_10]
0x1801356cd  add     rsp, 30h
0x1801356d1  pop     r15
0x1801356d3  pop     r14
0x1801356d5  pop     r12
0x1801356d7  pop     rdi
0x1801356d8  pop     rsi
0x1801356d9  retn
```
