# CStMuxPinMgr::UpdateMediaTypes(void)

- ea: `0x1800cbc54`
- end: `0x1800cbfb3`
- name: `?UpdateMediaTypes@CStMuxPinMgr@@IEAAJXZ`
- size: `863`
- prototype: `__int64 __fastcall(CStMuxPinMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cac94`

## callees

- `0x180009608`
- `0x180018e9c`
- `0x1800cbc54`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbf81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbf81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbc8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbc8b`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800cbe06`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800cbe06`
- `MFPlat!MFCreateCollection` at `0x1800cbc9e`
- `MFPlat!MFCreateCollection` at `0x1800cbc9e`

## pseudocode

```c
__int64 __fastcall CStMuxPinMgr::UpdateMediaTypes(CStMuxPinMgr *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // edi
  __int64 v11; // rdx
  unsigned int v12; // r13d
  __int64 i; // r12
  __int64 v14; // rsi
  int (__fastcall *v15)(__int64, _QWORD, __int64 *); // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, _QWORD, __int64 *); // rdi
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, void *, GUID *, __int64 *); // rdi
  unsigned int v33; // r13d
  __int64 j; // r12
  __int64 v35; // rsi
  __int64 v36; // rcx
  __int64 (__fastcall *v37)(__int64, __int64); // rdi
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v49; // [rsp+70h] [rbp+40h] BYREF
  __int64 v50; // [rsp+78h] [rbp+48h] BYREF
  __int64 v51; // [rsp+80h] [rbp+50h] BYREF
  __int64 v52; // [rsp+88h] [rbp+58h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  v51 = 0;
  v50 = 0;
  v52 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, v3, v4, v5);
  v6 = MFCreateCollection(&v51);
  v10 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 34;
LABEL_38:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v6);
    goto LABEL_39;
  }
  v12 = *((_DWORD *)this + 4);
  for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
  {
    v14 = *((_QWORD *)this + 11);
    v49 = 0;
    v15 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v7, v8, v9);
    if ( v15(v14, (unsigned int)i, &v49) < 0 )
    {
      v19 = *((_QWORD *)this + 11);
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v19 + 112LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v16, v17, v18);
      v21 = v20(v19, (unsigned int)i, 0, &v49);
      v10 = v21;
      if ( v21 < 0 )
      {
        if ( g_wppLevels )
        {
          v27 = 35;
          goto LABEL_14;
        }
LABEL_15:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v22, v23, v24);
        goto LABEL_39;
      }
    }
    v25 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * i);
    v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, v49);
    v10 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v27 = 36;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v21);
      goto LABEL_15;
    }
    v26 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * i);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26) != -1 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 40LL))(v51, v49);
      v10 = v21;
      if ( v21 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_15;
        v27 = 37;
        goto LABEL_14;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v22, v23, v24);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v7, v8, v9);
  v6 = MFCreateMuxStreamMediaType(v51, &v50);
  v10 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 38;
    goto LABEL_38;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const GUID *, void *))(*(_QWORD *)v50 + 192LL))(
         v50,
         &MF_MT_SUBTYPE,
         &MFMultiplexFormat_TimeCorrelation);
  v10 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 39;
    goto LABEL_38;
  }
  v31 = v50;
  v32 = *(__int64 (__fastcall **)(__int64, void *, GUID *, __int64 *))(*(_QWORD *)v50 + 136LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52, v28, v29, v30);
  v6 = v32(v31, &MF_MEDIATYPE_MULTIPLEXED_MANAGER, &GUID_505a2c72_42f7_4690_aeab_8f513d0ffdb8, &v52);
  v10 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 40;
    goto LABEL_38;
  }
  v33 = *((_DWORD *)this + 10);
  for ( j = 0; (unsigned int)j < v33; j = (unsigned int)(j + 1) )
  {
    v35 = v52;
    v36 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * j);
    v37 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 48LL);
    v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
    v6 = v37(v35, v38);
    v10 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v11 = 41;
      goto LABEL_38;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 10) + 40LL))(*((_QWORD *)this + 10), v50);
  v10 = v6;
  if ( v6 < 0 && g_wppLevels )
  {
    v11 = 42;
    goto LABEL_38;
  }
LABEL_39:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 43, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v10);
  LeaveCriticalSection(v1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52, v39, v40, v41);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v42, v43, v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, v45, v46, v47);
  return v10;
}

```

## disassembly

```asm
0x1800cbc54  push    rbp
0x1800cbc56  push    rbx
0x1800cbc57  push    rsi
0x1800cbc58  push    rdi
0x1800cbc59  push    r12
0x1800cbc5b  push    r13
0x1800cbc5d  push    r14
0x1800cbc5f  mov     rbp, rsp
0x1800cbc62  sub     rsp, 30h
0x1800cbc66  lea     rbx, [rcx+80h]
0x1800cbc6d  mov     [rbp+arg_10], 0
0x1800cbc75  mov     r14, rcx
0x1800cbc78  mov     [rbp+arg_8], 0
0x1800cbc80  mov     rcx, rbx; lpCriticalSection
0x1800cbc83  mov     [rbp+arg_18], 0
0x1800cbc8b  call    cs:__imp_EnterCriticalSection
0x1800cbc91  lea     rcx, [rbp+arg_10]
0x1800cbc95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbc9a  lea     rcx, [rbp+arg_10]
0x1800cbc9e  call    cs:__imp_MFCreateCollection
0x1800cbca4  mov     edi, eax
0x1800cbca6  test    eax, eax
0x1800cbca8  jns     short loc_1800CBCC1
0x1800cbcaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbcb1  jb      loc_1800CBF4F
0x1800cbcb7  mov     edx, 22h ; '"'
0x1800cbcbc  jmp     loc_1800CBF31
0x1800cbcc1  mov     r13d, [r14+10h]
0x1800cbcc5  xor     r12d, r12d
0x1800cbcc8  cmp     r12d, r13d
0x1800cbccb  jnb     loc_1800CBDF5
0x1800cbcd1  mov     rsi, [r14+58h]
0x1800cbcd5  lea     rcx, [rbp+arg_0]
0x1800cbcd9  mov     [rbp+arg_0], 0
0x1800cbce1  mov     rax, [rsi]
0x1800cbce4  mov     rdi, [rax+90h]
0x1800cbceb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbcf0  lea     r8, [rbp+arg_0]
0x1800cbcf4  mov     edx, r12d
0x1800cbcf7  mov     rcx, rsi
0x1800cbcfa  mov     rax, rdi
0x1800cbcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd02  test    eax, eax
0x1800cbd04  jns     short loc_1800CBD35
0x1800cbd06  mov     rsi, [r14+58h]
0x1800cbd0a  lea     rcx, [rbp+arg_0]
0x1800cbd0e  mov     rax, [rsi]
0x1800cbd11  mov     rdi, [rax+70h]
0x1800cbd15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbd1a  lea     r9, [rbp+arg_0]
0x1800cbd1e  xor     r8d, r8d
0x1800cbd21  mov     edx, r12d
0x1800cbd24  mov     rcx, rsi
0x1800cbd27  mov     rax, rdi
0x1800cbd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd2f  mov     edi, eax
0x1800cbd31  test    eax, eax
0x1800cbd33  js      short loc_1800CBD9B
0x1800cbd35  mov     rax, [r14+8]
0x1800cbd39  mov     rdx, [rbp+arg_0]
0x1800cbd3d  mov     rcx, [rax+r12*8]
0x1800cbd41  mov     rax, [rcx]
0x1800cbd44  mov     rax, [rax+28h]
0x1800cbd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd4d  mov     edi, eax
0x1800cbd4f  test    eax, eax
0x1800cbd51  js      loc_1800CBDE5
0x1800cbd57  mov     rax, [r14+8]
0x1800cbd5b  mov     rcx, [rax+r12*8]
0x1800cbd5f  mov     rax, [rcx]
0x1800cbd62  mov     rax, [rax+50h]
0x1800cbd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd6b  cmp     eax, 0FFFFFFFFh
0x1800cbd6e  jz      short loc_1800CBD8A
0x1800cbd70  mov     rcx, [rbp+arg_10]
0x1800cbd74  mov     rdx, [rbp+arg_0]
0x1800cbd78  mov     rax, [rcx]
0x1800cbd7b  mov     rax, [rax+28h]
0x1800cbd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd84  mov     edi, eax
0x1800cbd86  test    eax, eax
0x1800cbd88  js      short loc_1800CBDD5
0x1800cbd8a  lea     rcx, [rbp+arg_0]
0x1800cbd8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbd93  inc     r12d
0x1800cbd96  jmp     loc_1800CBCC8
0x1800cbd9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbda2  jb      short loc_1800CBDC7
0x1800cbda4  mov     edx, 23h ; '#'
0x1800cbda9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbdb0  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cbdb7  mov     r9, r14
0x1800cbdba  mov     [rsp+30h+var_10], eax
0x1800cbdbe  mov     rcx, [rcx+10h]
0x1800cbdc2  call    WPP_SF_qD
0x1800cbdc7  lea     rcx, [rbp+arg_0]
0x1800cbdcb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbdd0  jmp     loc_1800CBF4F
0x1800cbdd5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbddc  jb      short loc_1800CBDC7
0x1800cbdde  mov     edx, 25h ; '%'
0x1800cbde3  jmp     short loc_1800CBDA9
0x1800cbde5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbdec  jb      short loc_1800CBDC7
0x1800cbdee  mov     edx, 24h ; '$'
0x1800cbdf3  jmp     short loc_1800CBDA9
0x1800cbdf5  lea     rcx, [rbp+arg_8]
0x1800cbdf9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbdfe  mov     rcx, [rbp+arg_10]
0x1800cbe02  lea     rdx, [rbp+arg_8]
0x1800cbe06  call    cs:__imp_MFCreateMuxStreamMediaType
0x1800cbe0c  mov     edi, eax
0x1800cbe0e  test    eax, eax
0x1800cbe10  jns     short loc_1800CBE29
0x1800cbe12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbe19  jb      loc_1800CBF4F
0x1800cbe1f  mov     edx, 26h ; '&'
0x1800cbe24  jmp     loc_1800CBF31
0x1800cbe29  mov     rcx, [rbp+arg_8]
0x1800cbe2d  lea     r8, MFMultiplexFormat_TimeCorrelation
0x1800cbe34  lea     rdx, MF_MT_SUBTYPE
0x1800cbe3b  mov     rax, [rcx]
0x1800cbe3e  mov     rax, [rax+0C0h]
0x1800cbe45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe4a  mov     edi, eax
0x1800cbe4c  test    eax, eax
0x1800cbe4e  jns     short loc_1800CBE67
0x1800cbe50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbe57  jb      loc_1800CBF4F
0x1800cbe5d  mov     edx, 27h ; '''
0x1800cbe62  jmp     loc_1800CBF31
0x1800cbe67  mov     rsi, [rbp+arg_8]
0x1800cbe6b  lea     rcx, [rbp+arg_18]
0x1800cbe6f  mov     rax, [rsi]
0x1800cbe72  mov     rdi, [rax+88h]
0x1800cbe79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbe7e  lea     r9, [rbp+arg_18]
0x1800cbe82  mov     rcx, rsi
0x1800cbe85  lea     r8, _GUID_505a2c72_42f7_4690_aeab_8f513d0ffdb8
0x1800cbe8c  mov     rax, rdi
0x1800cbe8f  lea     rdx, MF_MEDIATYPE_MULTIPLEXED_MANAGER
0x1800cbe96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe9b  mov     edi, eax
0x1800cbe9d  test    eax, eax
0x1800cbe9f  jns     short loc_1800CBEB5
0x1800cbea1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbea8  jb      loc_1800CBF4F
0x1800cbeae  mov     edx, 28h ; '('
0x1800cbeb3  jmp     short loc_1800CBF31
0x1800cbeb5  mov     r13d, [r14+28h]
0x1800cbeb9  xor     r12d, r12d
0x1800cbebc  cmp     r12d, r13d
0x1800cbebf  jnb     short loc_1800CBF09
0x1800cbec1  mov     rdx, [r14+20h]
0x1800cbec5  mov     rsi, [rbp+arg_18]
0x1800cbec9  mov     rcx, [rdx+r12*8]
0x1800cbecd  mov     rax, [rsi]
0x1800cbed0  mov     rdx, [rcx]
0x1800cbed3  mov     rdi, [rax+30h]
0x1800cbed7  mov     rax, [rdx+20h]
0x1800cbedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbee0  mov     rdx, rax
0x1800cbee3  mov     rcx, rsi
0x1800cbee6  mov     rax, rdi
0x1800cbee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbeee  mov     edi, eax
0x1800cbef0  test    eax, eax
0x1800cbef2  js      short loc_1800CBEF9
0x1800cbef4  inc     r12d
0x1800cbef7  jmp     short loc_1800CBEBC
0x1800cbef9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbf00  jb      short loc_1800CBF4F
0x1800cbf02  mov     edx, 29h ; ')'
0x1800cbf07  jmp     short loc_1800CBF31
0x1800cbf09  mov     rcx, [r14+50h]
0x1800cbf0d  mov     rdx, [rbp+arg_8]
0x1800cbf11  mov     rax, [rcx]
0x1800cbf14  mov     rax, [rax+28h]
0x1800cbf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf1d  mov     edi, eax
0x1800cbf1f  test    eax, eax
0x1800cbf21  jns     short loc_1800CBF4F
0x1800cbf23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbf2a  jb      short loc_1800CBF4F
0x1800cbf2c  mov     edx, 2Ah ; '*'
0x1800cbf31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbf38  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cbf3f  mov     r9, r14
0x1800cbf42  mov     [rsp+30h+var_10], eax
0x1800cbf46  mov     rcx, [rcx+10h]
0x1800cbf4a  call    WPP_SF_qD
0x1800cbf4f  cmp     cs:byte_18010EC4D, 8
0x1800cbf56  jb      short loc_1800CBF7E
0x1800cbf58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbf5f  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cbf66  mov     edx, 2Bh ; '+'
0x1800cbf6b  mov     [rsp+30h+var_10], edi
0x1800cbf6f  mov     r9, r14
0x1800cbf72  mov     rcx, [rcx+0D8h]
0x1800cbf79  call    WPP_SF_qD
0x1800cbf7e  mov     rcx, rbx; lpCriticalSection
0x1800cbf81  call    cs:__imp_LeaveCriticalSection
0x1800cbf87  lea     rcx, [rbp+arg_18]
0x1800cbf8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbf90  lea     rcx, [rbp+arg_8]
0x1800cbf94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbf99  lea     rcx, [rbp+arg_10]
0x1800cbf9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cbfa2  mov     eax, edi
0x1800cbfa4  add     rsp, 30h
0x1800cbfa8  pop     r14
0x1800cbfaa  pop     r13
0x1800cbfac  pop     r12
0x1800cbfae  pop     rdi
0x1800cbfaf  pop     rsi
0x1800cbfb0  pop     rbx
0x1800cbfb1  pop     rbp
0x1800cbfb2  retn
```
