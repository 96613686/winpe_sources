# SetDevnodeProperties(IPropertyStore *,ulong,_DEVPROPERTY * *,ulong *)

- ea: `0x180006524`
- end: `0x180006a8e`
- name: `?SetDevnodeProperties@@YAJPEAUIPropertyStore@@KPEAPEAU_DEVPROPERTY@@PEAK@Z`
- size: `1386`
- prototype: `__int64 __fastcall(struct IPropertyStore *, int, struct _DEVPROPERTY **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b00`

## callees

- `0x180006524`
- `0x180007580`
- `0x180010da8`
- `0x180025464`
- `0x180025ee8`
- `0x180026ff4`
- `0x18003f78c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000658d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000658d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000657c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000657c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800066ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000685f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800068cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800066ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000685f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800068cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000679a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000679a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000696e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000696e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a2c`

## string_xrefs

- `0x1800067bb`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180006990`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x1800069f9`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180006a6a`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SetDevnodeProperties(struct IPropertyStore *a1, int a2, struct _DEVPROPERTY **a3, unsigned int *a4)
{
  unsigned int *v4; // r15
  struct _DEVPROPERTY **v5; // r12
  int v6; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v9; // rbx
  _DWORD *v10; // rdi
  _DWORD *v11; // rax
  __int64 v12; // rbx
  _DWORD *v13; // rdi
  _DWORD *v14; // rax
  __int64 v15; // rbx
  _DWORD *v16; // rdi
  _BYTE *v17; // rax
  __int64 v18; // rbx
  _DWORD *v19; // rdi
  _DWORD *v20; // rax
  unsigned int v21; // ecx
  PROPVARIANT v23; // r14
  __int64 v24; // rax
  unsigned int v25; // r12d
  __int64 v26; // rbx
  _DWORD *v27; // rdi
  void *v28; // rax
  void *v29; // r15
  __int64 v30; // rbx
  _DWORD *v31; // rdi
  _DWORD *v32; // rax
  LPVOID v33; // rbx
  void *v34; // rcx
  unsigned int v35; // edi
  unsigned int i; // edx
  void *v37; // rcx
  unsigned int v38; // edi
  unsigned int j; // edx
  void *v40; // rcx
  __int64 v41; // rdx
  int v42; // [rsp+28h] [rbp-59h]
  unsigned int v43; // [rsp+38h] [rbp-49h] BYREF
  void *v44; // [rsp+40h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v47; // [rsp+60h] [rbp-21h]
  PROPVARIANT v48[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v49; // [rsp+78h] [rbp-9h]
  unsigned int v50[2]; // [rsp+80h] [rbp-1h] BYREF
  _QWORD v51[2]; // [rsp+88h] [rbp+7h] BYREF
  char v52; // [rsp+98h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  *(_OWORD *)pvar = 0;
  v47 = 0;
  v43 = 0;
  *(_QWORD *)v50 = 0;
  ProcessHeap = GetProcessHeap();
  v44 = HeapAlloc(ProcessHeap, 0, 0x150u);
  if ( !v44 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x271,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)0x8007000ELL,
      v42);
    goto LABEL_10;
  }
  v51[0] = &v43;
  v51[1] = &v44;
  v52 = 1;
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         &PKEY_Device_FriendlyName,
         pvar) >= 0
    && LOWORD(pvar[0]) == 31 )
  {
    v23 = pvar[1];
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)pvar[1] + v24) );
    v25 = 2 * v24 + 2;
    v26 = 6LL * v43;
    v27 = v44;
    *(DEVPROPKEY *)((char *)v44 + 8 * v26) = DEVPKEY_Device_FriendlyName;
    v27[2 * v26 + 5] = 0;
    *(_QWORD *)&v27[2 * v26 + 6] = 0;
    v27[2 * v26 + 8] = 18;
    v28 = CoTaskMemAlloc(v25);
    v29 = v28;
    if ( v28 )
    {
      memcpy_0(v28, v23, v25);
      v27[2 * v26 + 9] = v25;
      *(_QWORD *)&v27[2 * v26 + 10] = v29;
      v30 = 6LL * ++v43;
      v31 = v44;
      *(DEVPROPKEY *)((char *)v44 + 8 * v30) = DEVPKEY_Device_FriendlyNameAttributes;
      v31[2 * v30 + 5] = 0;
      *(_QWORD *)&v31[2 * v30 + 6] = 0;
      v31[2 * v30 + 8] = 7;
      v32 = CoTaskMemAlloc(4u);
      v4 = a4;
      v5 = a3;
      if ( v32 )
      {
        *v32 = 2;
        v31[2 * v30 + 9] = 4;
        *(_QWORD *)&v31[2 * v30 + 10] = v32;
        ++v43;
      }
    }
    else
    {
      v4 = a4;
      v5 = a3;
    }
    v6 = a2;
  }
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         &PKEY_DeviceClass_IconPath,
         v48) >= 0
    && LOWORD(v48[0]) == 31 )
  {
    pv = 0;
    if ( (int)StringToStringList((unsigned __int16 *)v48[1], &pv, (unsigned __int64 *)v50) < 0 )
    {
      v34 = pv;
      if ( !pv )
        goto LABEL_4;
      goto LABEL_23;
    }
    v33 = pv;
    if ( InitializeDevProperty((struct _DEVPROPERTY *)v44 + v43, &DEVPKEY_DrvPkg_Icon, 0x2012u, v50[0], pv, 0) >= 0 )
    {
      ++v43;
      goto LABEL_4;
    }
    if ( v33 )
    {
      v34 = v33;
LABEL_23:
      CoTaskMemFree(v34);
    }
  }
LABEL_4:
  v9 = 6LL * v43;
  v10 = v44;
  *(DEVPROPKEY *)((char *)v44 + 8 * v9) = DEVPKEY_DeviceContainer_Category;
  v10[2 * v9 + 5] = 0;
  *(_QWORD *)&v10[2 * v9 + 6] = 0;
  v10[2 * v9 + 8] = 8210;
  v11 = CoTaskMemAlloc(0xEu);
  if ( !v11 )
  {
    v41 = 691;
    goto LABEL_39;
  }
  *(_QWORD *)v11 = 0x69006400750041LL;
  v11[2] = 111;
  *((_WORD *)v11 + 6) = 0;
  v10[2 * v9 + 9] = 14;
  *(_QWORD *)&v10[2 * v9 + 10] = v11;
  v12 = 6LL * ++v43;
  v13 = v44;
  *(DEVPROPKEY *)((char *)v44 + 8 * v12) = DEVPKEY_Device_SessionId;
  v13[2 * v12 + 5] = 0;
  *(_QWORD *)&v13[2 * v12 + 6] = 0;
  v13[2 * v12 + 8] = 7;
  v14 = CoTaskMemAlloc(4u);
  if ( !v14 )
  {
    v41 = 701;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)0x8007000ELL,
      v42);
    v52 = 0;
    lambda_c12a5b54dba3db654ad968b4fdaadd5f_::operator()(v51);
    goto LABEL_10;
  }
  *v14 = v6;
  v13[2 * v12 + 9] = 4;
  *(_QWORD *)&v13[2 * v12 + 10] = v14;
  v15 = 6LL * ++v43;
  v16 = v44;
  *(DEVPROPKEY *)((char *)v44 + 8 * v15) = DEVPKEY_Device_NoConnectSound;
  v16[2 * v15 + 5] = 0;
  *(_QWORD *)&v16[2 * v15 + 6] = 0;
  v16[2 * v15 + 8] = 17;
  v17 = CoTaskMemAlloc(1u);
  if ( v17 )
  {
    *v17 = -1;
    v16[2 * v15 + 9] = 1;
    *(_QWORD *)&v16[2 * v15 + 10] = v17;
    v18 = 6LL * ++v43;
    v19 = v44;
    *(_OWORD *)((char *)v44 + 8 * v18) = DEVPKEY_Device_ProjectionOption;
    v19[2 * v18 + 4] = 2;
    v19[2 * v18 + 5] = 0;
    *(_QWORD *)&v19[2 * v18 + 6] = 0;
    v19[2 * v18 + 8] = 7;
    v20 = CoTaskMemAlloc(4u);
    if ( v20 )
    {
      *v20 = 2;
      v19[2 * v18 + 9] = 4;
      *(_QWORD *)&v19[2 * v18 + 10] = v20;
      v21 = ++v43;
      *v5 = (struct _DEVPROPERTY *)v44;
      *v4 = v21;
      v44 = 0;
      PropVariantClear(pvar);
      PropVariantClear(v48);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)0x8007000ELL,
      v42);
    v35 = 0;
    for ( i = v43; v35 < i; ++v35 )
    {
      v37 = (void *)*((_QWORD *)v44 + 6 * v35 + 5);
      if ( v37 )
      {
        CoTaskMemFree(v37);
        *((_QWORD *)v44 + 6 * v35 + 5) = 0;
        i = v43;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)0x8007000ELL,
      v42);
    v38 = 0;
    for ( j = v43; v38 < j; ++v38 )
    {
      v40 = (void *)*((_QWORD *)v44 + 6 * v38 + 5);
      if ( v40 )
      {
        CoTaskMemFree(v40);
        *((_QWORD *)v44 + 6 * v38 + 5) = 0;
        j = v43;
      }
    }
  }
  operator delete(v44);
  v44 = 0;
LABEL_10:
  PropVariantClear(pvar);
  PropVariantClear(v48);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180006524  mov     rax, rsp
0x180006527  mov     [rax+8], rbx
0x18000652b  mov     [rax+20h], r9
0x18000652f  mov     [rax+18h], r8
0x180006533  mov     [rax+10h], edx
0x180006536  push    rbp
0x180006537  push    rsi
0x180006538  push    rdi
0x180006539  push    r12
0x18000653b  push    r13
0x18000653d  push    r14
0x18000653f  push    r15
0x180006541  lea     rbp, [rax-5Fh]
0x180006545  sub     rsp, 0A0h
0x18000654c  mov     r15, r9
0x18000654f  mov     r12, r8
0x180006552  mov     r14d, edx
0x180006555  mov     rsi, rcx
0x180006558  xor     r13d, r13d
0x18000655b  mov     [rbp+57h+var_98], r13
0x18000655f  xorps   xmm0, xmm0
0x180006562  xor     eax, eax
0x180006564  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180006568  mov     [rbp+57h+var_60], rax
0x18000656c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180006570  mov     [rbp+57h+var_78], rax
0x180006574  mov     [rbp+57h+var_A0], r13d
0x180006578  mov     qword ptr [rbp+57h+var_58], r13
0x18000657c  call    cs:__imp_GetProcessHeap
0x180006582  mov     rcx, rax; hHeap
0x180006585  xor     edx, edx; dwFlags
0x180006587  mov     r8d, 150h; dwBytes
0x18000658d  call    cs:__imp_HeapAlloc
0x180006593  mov     [rbp+57h+var_98], rax
0x180006597  test    rax, rax
0x18000659a  jz      loc_1800067AF
0x1800065a0  lea     rax, [rbp+57h+var_A0]
0x1800065a4  mov     [rbp+57h+var_50], rax
0x1800065a8  lea     rax, [rbp+57h+var_98]
0x1800065ac  mov     [rbp+57h+var_48], rax
0x1800065b0  mov     [rbp+57h+var_40], 1
0x1800065b4  mov     rax, [rsi]
0x1800065b7  lea     r8, [rbp+57h+pvar]
0x1800065bb  lea     rdx, PKEY_Device_FriendlyName
0x1800065c2  mov     rcx, rsi
0x1800065c5  mov     rax, [rax+28h]
0x1800065c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ce  test    eax, eax
0x1800065d0  jns     loc_1800067FF
0x1800065d6  mov     rax, [rsi]
0x1800065d9  lea     r8, [rbp+57h+var_70]
0x1800065dd  lea     rdx, PKEY_DeviceClass_IconPath
0x1800065e4  mov     rcx, rsi
0x1800065e7  mov     rax, [rax+28h]
0x1800065eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f0  mov     esi, 2012h
0x1800065f5  test    eax, eax
0x1800065f7  jns     loc_1800068FC
0x1800065fd  mov     eax, [rbp+57h+var_A0]
0x180006600  lea     rbx, [rax+rax*2]
0x180006604  add     rbx, rbx
0x180006607  mov     rdi, [rbp+57h+var_98]
0x18000660b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Category.fmtid.Data1
0x180006612  movups  xmmword ptr [rdi+rbx*8], xmm0
0x180006616  mov     eax, cs:DEVPKEY_DeviceContainer_Category.pid
0x18000661c  mov     [rdi+rbx*8+10h], eax
0x180006620  mov     [rdi+rbx*8+14h], r13d
0x180006625  mov     [rdi+rbx*8+18h], r13
0x18000662a  mov     [rdi+rbx*8+20h], esi
0x18000662e  mov     esi, 0Eh
0x180006633  mov     ecx, esi; cb
0x180006635  call    cs:__imp_CoTaskMemAlloc
0x18000663b  test    rax, rax
0x18000663e  jz      loc_180006A5D
0x180006644  movsd   xmm0, cs:qword_18006C300
0x18000664c  movsd   qword ptr [rax], xmm0
0x180006650  mov     ecx, cs:dword_18006C308
0x180006656  mov     [rax+8], ecx
0x180006659  movzx   ecx, cs:word_18006C30C
0x180006660  mov     [rax+0Ch], cx
0x180006664  mov     [rdi+rbx*8+24h], esi
0x180006668  mov     [rdi+rbx*8+28h], rax
0x18000666d  mov     eax, [rbp+57h+var_A0]
0x180006670  inc     eax
0x180006672  mov     [rbp+57h+var_A0], eax
0x180006675  lea     rbx, [rax+rax*2]
0x180006679  add     rbx, rbx
0x18000667c  mov     rdi, [rbp+57h+var_98]
0x180006680  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x180006687  movups  xmmword ptr [rdi+rbx*8], xmm0
0x18000668b  mov     eax, cs:DEVPKEY_Device_SessionId.pid
0x180006691  mov     [rdi+rbx*8+10h], eax
0x180006695  mov     [rdi+rbx*8+14h], r13d
0x18000669a  mov     [rdi+rbx*8+18h], r13
0x18000669f  mov     dword ptr [rdi+rbx*8+20h], 7
0x1800066a7  mov     esi, 4
0x1800066ac  mov     ecx, esi; cb
0x1800066ae  call    cs:__imp_CoTaskMemAlloc
0x1800066b4  test    rax, rax
0x1800066b7  jz      loc_180006A56
0x1800066bd  mov     [rax], r14d
0x1800066c0  mov     [rdi+rbx*8+24h], esi
0x1800066c4  mov     [rdi+rbx*8+28h], rax
0x1800066c9  mov     eax, [rbp+57h+var_A0]
0x1800066cc  inc     eax
0x1800066ce  mov     [rbp+57h+var_A0], eax
0x1800066d1  lea     rbx, [rax+rax*2]
0x1800066d5  add     rbx, rbx
0x1800066d8  mov     rdi, [rbp+57h+var_98]
0x1800066dc  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x1800066e3  movups  xmmword ptr [rdi+rbx*8], xmm0
0x1800066e7  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x1800066ed  mov     [rdi+rbx*8+10h], eax
0x1800066f1  mov     [rdi+rbx*8+14h], r13d
0x1800066f6  mov     [rdi+rbx*8+18h], r13
0x1800066fb  mov     dword ptr [rdi+rbx*8+20h], 11h
0x180006703  lea     ecx, [rsi-3]; cb
0x180006706  call    cs:__imp_CoTaskMemAlloc
0x18000670c  test    rax, rax
0x18000670f  jz      loc_1800069ED
0x180006715  mov     byte ptr [rax], 0FFh
0x180006718  mov     dword ptr [rdi+rbx*8+24h], 1
0x180006720  mov     [rdi+rbx*8+28h], rax
0x180006725  mov     eax, [rbp+57h+var_A0]
0x180006728  inc     eax
0x18000672a  mov     [rbp+57h+var_A0], eax
0x18000672d  lea     rbx, [rax+rax*2]
0x180006731  add     rbx, rbx
0x180006734  mov     rdi, [rbp+57h+var_98]
0x180006738  movups  xmm0, cs:DEVPKEY_Device_ProjectionOption
0x18000673f  movups  xmmword ptr [rdi+rbx*8], xmm0
0x180006743  mov     eax, cs:dword_18006C350
0x180006749  mov     [rdi+rbx*8+10h], eax
0x18000674d  mov     [rdi+rbx*8+14h], r13d
0x180006752  mov     [rdi+rbx*8+18h], r13
0x180006757  mov     dword ptr [rdi+rbx*8+20h], 7
0x18000675f  mov     ecx, esi; cb
0x180006761  call    cs:__imp_CoTaskMemAlloc
0x180006767  test    rax, rax
0x18000676a  jz      loc_180006984
0x180006770  mov     dword ptr [rax], 2
0x180006776  mov     [rdi+rbx*8+24h], esi
0x18000677a  mov     [rdi+rbx*8+28h], rax
0x18000677f  mov     ecx, [rbp+57h+var_A0]
0x180006782  inc     ecx
0x180006784  mov     [rbp+57h+var_A0], ecx
0x180006787  mov     rax, [rbp+57h+var_98]
0x18000678b  mov     [r12], rax
0x18000678f  mov     [r15], ecx
0x180006792  mov     [rbp+57h+var_98], r13
0x180006796  lea     rcx, [rbp+57h+pvar]; pvar
0x18000679a  call    cs:__imp_PropVariantClear
0x1800067a0  nop
0x1800067a1  lea     rcx, [rbp+57h+var_70]; pvar
0x1800067a5  call    cs:__imp_PropVariantClear
0x1800067ab  xor     eax, eax
0x1800067ad  jmp     short loc_1800067E4
0x1800067af  mov     rcx, [rbp+5Fh]; this
0x1800067b3  mov     ebx, 8007000Eh
0x1800067b8  mov     r9d, ebx; char *
0x1800067bb  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x1800067c2  mov     edx, 271h; void *
0x1800067c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067cc  nop
0x1800067cd  lea     rcx, [rbp+57h+pvar]; pvar
0x1800067d1  call    cs:__imp_PropVariantClear
0x1800067d7  nop
0x1800067d8  lea     rcx, [rbp+57h+var_70]; pvar
0x1800067dc  call    cs:__imp_PropVariantClear
0x1800067e2  mov     eax, ebx
0x1800067e4  mov     rbx, [rsp+0D0h+arg_0]
0x1800067ec  add     rsp, 0A0h
0x1800067f3  pop     r15
0x1800067f5  pop     r14
0x1800067f7  pop     r13
0x1800067f9  pop     r12
0x1800067fb  pop     rdi
0x1800067fc  pop     rsi
0x1800067fd  pop     rbp
0x1800067fe  retn
0x1800067ff  cmp     word ptr [rbp+57h+pvar], 1Fh
0x180006804  jnz     loc_1800065D6
0x18000680a  mov     r14, [rbp+57h+pvar+8]
0x18000680e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006812  inc     rax
0x180006815  cmp     [r14+rax*2], r13w
0x18000681a  jnz     short loc_180006812
0x18000681c  lea     r12d, ds:2[rax*2]
0x180006824  mov     eax, [rbp+57h+var_A0]
0x180006827  lea     rbx, [rax+rax*2]
0x18000682b  add     rbx, rbx
0x18000682e  mov     rdi, [rbp+57h+var_98]
0x180006832  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x180006839  movups  xmmword ptr [rdi+rbx*8], xmm0
0x18000683d  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x180006843  mov     [rdi+rbx*8+10h], eax
0x180006847  mov     [rdi+rbx*8+14h], r13d
0x18000684c  mov     [rdi+rbx*8+18h], r13
0x180006851  mov     dword ptr [rdi+rbx*8+20h], 12h
0x180006859  mov     r13d, r12d
0x18000685c  mov     ecx, r12d; cb
0x18000685f  call    cs:__imp_CoTaskMemAlloc
0x180006865  mov     r15, rax
0x180006868  test    rax, rax
0x18000686b  jz      loc_180006A46
0x180006871  mov     r8d, r13d; Size
0x180006874  mov     rdx, r14; Src
0x180006877  mov     rcx, rax; void *
0x18000687a  call    memcpy_0
0x18000687f  mov     [rdi+rbx*8+24h], r12d
0x180006884  mov     [rdi+rbx*8+28h], r15
0x180006889  mov     eax, [rbp+57h+var_A0]
0x18000688c  inc     eax
0x18000688e  mov     [rbp+57h+var_A0], eax
0x180006891  lea     rbx, [rax+rax*2]
0x180006895  add     rbx, rbx
0x180006898  mov     rdi, [rbp+57h+var_98]
0x18000689c  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyNameAttributes.fmtid.Data1
0x1800068a3  movups  xmmword ptr [rdi+rbx*8], xmm0
0x1800068a7  mov     eax, cs:DEVPKEY_Device_FriendlyNameAttributes.pid
0x1800068ad  mov     [rdi+rbx*8+10h], eax
0x1800068b1  xor     r13d, r13d
0x1800068b4  mov     [rdi+rbx*8+14h], r13d
0x1800068b9  mov     [rdi+rbx*8+18h], r13
0x1800068be  mov     dword ptr [rdi+rbx*8+20h], 7
0x1800068c6  lea     r14d, [r13+4]
0x1800068ca  mov     ecx, r14d; cb
0x1800068cd  call    cs:__imp_CoTaskMemAlloc
0x1800068d3  mov     r15, [rbp+57h+arg_18]
0x1800068d7  mov     r12, [rbp+57h+arg_10]
0x1800068db  test    rax, rax
0x1800068de  jz      short loc_1800068F3
0x1800068e0  mov     dword ptr [rax], 2
0x1800068e6  mov     [rdi+rbx*8+24h], r14d
0x1800068eb  mov     [rdi+rbx*8+28h], rax
0x1800068f0  inc     [rbp+57h+var_A0]
0x1800068f3  mov     r14d, [rbp+57h+arg_8]
0x1800068f7  jmp     loc_1800065D6
0x1800068fc  cmp     word ptr [rbp+57h+var_70], 1Fh
0x180006901  jnz     loc_1800065FD
0x180006907  mov     [rbp+57h+pv], r13
0x18000690b  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x18000690f  lea     rdx, [rbp+57h+pv]; void **
0x180006913  mov     rcx, [rbp+57h+var_70+8]; Src
0x180006917  call    ?StringToStringList@@YAJPEAGPEAPEAXPEA_K@Z; StringToStringList(ushort *,void * *,unsigned __int64 *)
0x18000691c  test    eax, eax
0x18000691e  js      short loc_18000695C
0x180006920  mov     eax, [rbp+57h+var_A0]
0x180006923  lea     rcx, [rax+rax*2]
0x180006927  shl     rcx, 4
0x18000692b  add     rcx, [rbp+57h+var_98]; struct _DEVPROPERTY *
0x18000692f  mov     [rsp+0D0h+var_B0+8], r13d; int
0x180006934  mov     rbx, [rbp+57h+pv]
0x180006938  mov     qword ptr [rsp+0D0h+var_B0], rbx; void *
0x18000693d  mov     r9d, [rbp+57h+var_58]; unsigned int
0x180006941  mov     r8d, esi; unsigned int
0x180006944  lea     rdx, DEVPKEY_DrvPkg_Icon; struct _DEVPROPKEY *
0x18000694b  call    ?InitializeDevProperty@@YAJPEAU_DEVPROPERTY@@AEBU_DEVPROPKEY@@KKPEAXH@Z; InitializeDevProperty(_DEVPROPERTY *,_DEVPROPKEY const &,ulong,ulong,void *,int)
0x180006950  test    eax, eax
0x180006952  js      short loc_180006979
0x180006954  inc     [rbp+57h+var_A0]
0x180006957  jmp     loc_1800065FD
0x18000695c  mov     rcx, [rbp+57h+pv]
0x180006960  test    rcx, rcx
0x180006963  jz      loc_1800065FD
0x180006969  jmp     short loc_18000696E
0x18000696b  mov     rcx, rbx; pv
0x18000696e  call    cs:__imp_CoTaskMemFree
0x180006974  jmp     loc_1800065FD
0x180006979  test    rbx, rbx
0x18000697c  jz      loc_1800065FD
0x180006982  jmp     short loc_18000696B
0x180006984  mov     rcx, [rbp+5Fh]; this
0x180006988  mov     ebx, 8007000Eh
0x18000698d  mov     r9d, ebx; char *
0x180006990  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180006997  mov     edx, 2D2h; void *
0x18000699c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069a1  nop
0x1800069a2  mov     edi, r13d
0x1800069a5  mov     edx, [rbp+57h+var_A0]
0x1800069a8  test    edx, edx
0x1800069aa  jz      short loc_1800069DB
0x1800069ac  mov     eax, edi
0x1800069ae  lea     rsi, [rax+rax*2]
0x1800069b2  add     rsi, rsi
0x1800069b5  mov     rax, [rbp+57h+var_98]
0x1800069b9  mov     rcx, [rax+rsi*8+28h]; pv
0x1800069be  test    rcx, rcx
0x1800069c1  jz      short loc_1800069D5
0x1800069c3  call    cs:__imp_CoTaskMemFree
0x1800069c9  mov     rax, [rbp+57h+var_98]
0x1800069cd  mov     [rax+rsi*8+28h], r13
0x1800069d2  mov     edx, [rbp+57h+var_A0]
0x1800069d5  inc     edi
0x1800069d7  cmp     edi, edx
0x1800069d9  jb      short loc_1800069AC
0x1800069db  mov     rcx, [rbp+57h+var_98]; void *
0x1800069df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800069e4  mov     [rbp+57h+var_98], r13
  ... truncated ...
```
