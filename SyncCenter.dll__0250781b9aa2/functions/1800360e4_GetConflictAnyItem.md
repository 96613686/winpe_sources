# _GetConflictAnyItem

- ea: `0x1800360e4`
- end: `0x180036253`
- name: `_GetConflictAnyItem`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800367cc`
- `0x1800369b0`

## callees

- `0x1800133b0`
- `0x1800134dc`
- `0x1800360e4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003620e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003620e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036229`

## pseudocode

```c
__int64 __fastcall GetConflictAnyItem(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  int v5; // ebx
  unsigned int i; // edi
  int v7; // eax
  LPVOID v8; // rcx
  void *v9; // rbx
  void *v10; // rsi
  void *v11; // r14
  void *v12; // r15
  int v13; // eax
  void *v14; // r15
  void *v15; // rsi
  void *v16; // r14
  void *v17; // rdi
  LPVOID pv[2]; // [rsp+20h] [rbp-30h] BYREF
  LPVOID v20[2]; // [rsp+30h] [rbp-20h]
  LPVOID v21[2]; // [rsp+40h] [rbp-10h]
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  v22 = a2;
  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v22);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL))(v4, &v22);
  if ( v5 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      *(_OWORD *)pv = 0;
      *(_OWORD *)v20 = 0;
      *(_OWORD *)v21 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v22 + 32LL))(v22, i, pv);
      v8 = pv[0];
      v5 = v7;
      if ( v7 < 0 )
        break;
      if ( LODWORD(v21[1]) != 2 )
      {
        v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))pv[0])(
                pv[0],
                &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                a3);
        v8 = pv[0];
        v5 = v13;
        break;
      }
      v9 = pv[1];
      v10 = v20[0];
      v11 = v20[1];
      v12 = v21[0];
      *(_OWORD *)pv = 0;
      *(_OWORD *)v20 = 0;
      *(_OWORD *)v21 = 0;
      if ( v8 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      CoTaskMemFree(v9);
      CoTaskMemFree(v10);
      CoTaskMemFree(v11);
      CoTaskMemFree(v12);
    }
    v14 = v21[0];
    v15 = v20[0];
    v16 = v20[1];
    v17 = pv[1];
    *(_OWORD *)v21 = 0;
    *(_OWORD *)v20 = 0;
    *(_OWORD *)pv = 0;
    if ( v8 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    CoTaskMemFree(v17);
    CoTaskMemFree(v15);
    CoTaskMemFree(v16);
    CoTaskMemFree(v14);
  }
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800360e4  mov     [rsp-28h+arg_0], rbx
0x1800360e9  mov     [rsp-28h+arg_10], rsi
0x1800360ee  mov     [rsp-28h+arg_8], rdx
0x1800360f3  push    rbp
0x1800360f4  push    rdi
0x1800360f5  push    r12
0x1800360f7  push    r14
0x1800360f9  push    r15
0x1800360fb  mov     rbp, rsp
0x1800360fe  sub     rsp, 50h
0x180036102  mov     r9, rcx
0x180036105  mov     r12, r8
0x180036108  lea     rcx, [rbp+arg_8]; void *
0x18003610c  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180036111  mov     rdx, [r9]
0x180036114  mov     rcx, r9
0x180036117  mov     rax, [rdx+28h]
0x18003611b  lea     rdx, [rbp+arg_8]
0x18003611f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036124  mov     ebx, eax
0x180036126  test    eax, eax
0x180036128  js      loc_18003622F
0x18003612e  xor     edi, edi
0x180036130  mov     rcx, [rbp+arg_8]
0x180036134  lea     r8, [rbp+pv]
0x180036138  xorps   xmm0, xmm0
0x18003613b  mov     edx, edi
0x18003613d  movups  xmmword ptr [rbp+pv], xmm0
0x180036141  movups  xmmword ptr [rbp+var_20], xmm0
0x180036145  movups  xmmword ptr [rbp+var_10], xmm0
0x180036149  mov     rax, [rcx]
0x18003614c  mov     rax, [rax+20h]
0x180036150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036155  mov     rcx, [rbp+pv]
0x180036159  mov     ebx, eax
0x18003615b  test    eax, eax
0x18003615d  js      short loc_1800361DB
0x18003615f  cmp     dword ptr [rbp+var_10+8], 2
0x180036163  jnz     short loc_1800361C0
0x180036165  mov     rbx, [rbp+pv+8]
0x180036169  xorps   xmm0, xmm0
0x18003616c  mov     rsi, [rbp+var_20]
0x180036170  mov     r14, [rbp+var_20+8]
0x180036174  mov     r15, [rbp+var_10]
0x180036178  movups  xmmword ptr [rbp+pv], xmm0
0x18003617c  movups  xmmword ptr [rbp+var_20], xmm0
0x180036180  movups  xmmword ptr [rbp+var_10], xmm0
0x180036184  test    rcx, rcx
0x180036187  jz      short loc_180036195
0x180036189  mov     rax, [rcx]
0x18003618c  mov     rax, [rax+10h]
0x180036190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036195  mov     rcx, rbx; pv
0x180036198  call    cs:__imp_CoTaskMemFree
0x18003619e  mov     rcx, rsi; pv
0x1800361a1  call    cs:__imp_CoTaskMemFree
0x1800361a7  mov     rcx, r14; pv
0x1800361aa  call    cs:__imp_CoTaskMemFree
0x1800361b0  mov     rcx, r15; pv
0x1800361b3  call    cs:__imp_CoTaskMemFree
0x1800361b9  inc     edi
0x1800361bb  jmp     loc_180036130
0x1800361c0  mov     rax, [rcx]
0x1800361c3  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800361ca  mov     r8, r12
0x1800361cd  mov     rax, [rax]
0x1800361d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361d5  mov     rcx, [rbp+pv]
0x1800361d9  mov     ebx, eax
0x1800361db  mov     r15, [rbp+var_10]
0x1800361df  xorps   xmm0, xmm0
0x1800361e2  mov     rsi, [rbp+var_20]
0x1800361e6  mov     r14, [rbp+var_20+8]
0x1800361ea  mov     rdi, [rbp+pv+8]
0x1800361ee  movups  xmmword ptr [rbp+var_10], xmm0
0x1800361f2  movups  xmmword ptr [rbp+var_20], xmm0
0x1800361f6  movups  xmmword ptr [rbp+pv], xmm0
0x1800361fa  test    rcx, rcx
0x1800361fd  jz      short loc_18003620B
0x1800361ff  mov     rax, [rcx]
0x180036202  mov     rax, [rax+10h]
0x180036206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003620b  mov     rcx, rdi; pv
0x18003620e  call    cs:__imp_CoTaskMemFree
0x180036214  mov     rcx, rsi; pv
0x180036217  call    cs:__imp_CoTaskMemFree
0x18003621d  mov     rcx, r14; pv
0x180036220  call    cs:__imp_CoTaskMemFree
0x180036226  mov     rcx, r15; pv
0x180036229  call    cs:__imp_CoTaskMemFree
0x18003622f  lea     rcx, [rbp+arg_8]
0x180036233  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180036238  lea     r11, [rsp+50h+var_s0]
0x18003623d  mov     eax, ebx
0x18003623f  mov     rbx, [r11+30h]
0x180036243  mov     rsi, [r11+40h]
0x180036247  mov     rsp, r11
0x18003624a  pop     r15
0x18003624c  pop     r14
0x18003624e  pop     r12
0x180036250  pop     rdi
0x180036251  pop     rbp
0x180036252  retn
```
