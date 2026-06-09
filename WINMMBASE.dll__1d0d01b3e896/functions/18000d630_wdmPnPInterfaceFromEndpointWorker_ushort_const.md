# wdmPnPInterfaceFromEndpointWorker(ushort const *)

- ea: `0x18000d630`
- end: `0x18000da77`
- name: `?wdmPnPInterfaceFromEndpointWorker@@YAPEBGPEBG@Z`
- size: `1095`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003c80`
- `0x180007dd0`

## callees

- `0x18000d630`
- `0x18000da80`
- `0x18000eb68`
- `0x1800102ac`
- `0x1800106c0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d981`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d981`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d772`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d78d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d882`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d931`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d882`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d931`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000d68b`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000d68b`

## string_xrefs

- `0x18000da0c`: `wdmPnPInterfaceFromEndpointWorker: Failed to open property store for endpoint %ls: %x\n`
- `0x18000da65`: `wdmPnPInterfaceFromEndpointWorker: Failed to get device path for endpoint %ls: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
unsigned __int16 *__fastcall wdmPnPInterfaceFromEndpointWorker(const unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rdi
  int v3; // eax
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  int v8; // eax
  unsigned int i; // ebx
  int v10; // ecx
  void (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  void (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // rax
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // r14
  int v14; // eax
  void (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+20h] [rbp-79h] BYREF
  _DWORD v16[2]; // [rsp+28h] [rbp-71h]
  void (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-69h] BYREF
  __int64 v18; // [rsp+38h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-59h] BYREF
  __int64 v20; // [rsp+48h] [rbp-51h] BYREF
  __int64 v21; // [rsp+50h] [rbp-49h] BYREF
  void (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp-41h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v24; // [rsp+70h] [rbp-29h]
  __int64 v25; // [rsp+78h] [rbp-21h]
  __int64 v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+88h] [rbp-11h]
  _DWORD v28[6]; // [rsp+90h] [rbp-9h] BYREF

  v21 = 0;
  v20 = 0;
  v22 = 0;
  v15 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v2 = 0;
  pv = 0;
  v16[0] = 9568257;
  if ( (int)MMDeviceGetDeviceEnumerator(&v21) >= 0 )
  {
    if ( v20 != v21 )
    {
      v20 = 0;
      if ( v21 )
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
          v21,
          &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0,
          &v20);
    }
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)v21 + 40LL))(v21, a1, &v22) < 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)v20 + 40LL))(
              v20,
              a1,
              &v15);
      if ( v14 < 0 )
      {
        Squirt(
          "wdmPnPInterfaceFromEndpointWorker: Failed to retrieve device or PnP device for endpoint %ls: %x\n",
          a1,
          v14);
        goto LABEL_14;
      }
    }
    else if ( v15 != v22 )
    {
      v15 = 0;
      if ( v22 )
        (**v22)(v22, &GUID_3ade56af_4375_4413_9c91_4c652595ab07, &v15);
    }
    if ( !v15 )
    {
      v18 = 0;
      *(_OWORD *)pvar = 0;
      v24 = 0;
      v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))(*v22)[4])(v22, 0, &v18);
      if ( v8 < 0 )
      {
        Squirt("wdmPnPInterfaceFromEndpointWorker: Failed to open property store for endpoint %ls: %x\n", a1, v8);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        goto LABEL_14;
      }
      for ( i = 0; i < 2; ++i )
      {
        v10 = *((unsigned __int16 *)v16 + (int)i);
        v17 = 0;
        v28[0] = 590439624;
        v28[1] = 1283267372;
        v28[2] = 1907779772;
        v28[3] = 1730509416;
        v28[4] = v10;
        PropVariantClear(pvar);
        if ( (*(unsigned int (__fastcall **)(__int64, _DWORD *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(v18, v28, pvar)
          || LOWORD(pvar[0]) != 31
          || (*(unsigned int (__fastcall **)(__int64, PROPVARIANT, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, pvar[1], &v17) )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        }
        else
        {
          v11 = v17;
          v12 = v15;
          if ( v15 != v17 )
          {
            v13 = v15;
            v12 = 0;
            v15 = 0;
            if ( v17 )
            {
              (**v17)(v17, &GUID_3ade56af_4375_4413_9c91_4c652595ab07, &v15);
              v12 = v15;
              v11 = v17;
            }
            if ( v13 )
            {
              ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
              v12 = v15;
              v11 = v17;
            }
          }
          if ( v12 )
          {
            if ( v11 )
              ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
            break;
          }
          if ( v11 )
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
        }
      }
      PropVariantClear(pvar);
      if ( !v15 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        goto LABEL_14;
      }
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v3 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), LPVOID *))(*v15)[4])(v15, &pv);
    if ( v3 < 0 )
    {
      Squirt("wdmPnPInterfaceFromEndpointWorker: Failed to get device path for endpoint %ls: %x", a1, v3);
    }
    else
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_WORD *)pv + v4) );
      v5 = v4 + 1;
      v6 = (unsigned __int16 *)HeapAlloc(hHeap, 8u, 2 * (v4 + 1));
      v2 = v6;
      if ( v6 && (unsigned int)StringCchCopyW(v6, v5, (const unsigned __int16 *)pv) )
      {
        HeapFree(hHeap, 0, v2);
        v2 = 0;
      }
    }
  }
LABEL_14:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v15 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
  if ( v22 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v22)[2])(v22);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return v2;
}

```

## disassembly

```asm
0x18000d630  push    rbp
0x18000d632  push    rbx
0x18000d633  push    rsi
0x18000d634  push    rdi
0x18000d635  push    r12
0x18000d637  push    r13
0x18000d639  push    r14
0x18000d63b  push    r15
0x18000d63d  lea     rbp, [rsp-1Fh]
0x18000d642  sub     rsp, 0B8h
0x18000d649  mov     rax, cs:__security_cookie
0x18000d650  xor     rax, rsp
0x18000d653  mov     [rbp+57h+var_48], rax
0x18000d657  mov     rsi, rcx
0x18000d65a  xor     r15d, r15d
0x18000d65d  mov     [rbp+57h+var_A0], r15
0x18000d661  mov     [rbp+57h+var_A8], r15
0x18000d665  mov     [rbp+57h+var_98], r15
0x18000d669  mov     [rbp+57h+var_D0], r15
0x18000d66d  mov     [rbp+57h+var_78], r15
0x18000d671  mov     [rbp+57h+var_70], r15
0x18000d675  mov     [rbp+57h+var_68], r15
0x18000d679  mov     edi, r15d
0x18000d67c  mov     [rbp+57h+pv], r15
0x18000d680  mov     [rbp+57h+var_C8], 920001h
0x18000d687  lea     rcx, [rbp+57h+var_A0]
0x18000d68b  call    cs:__imp_MMDeviceGetDeviceEnumerator
0x18000d691  test    eax, eax
0x18000d693  js      loc_18000D784
0x18000d699  mov     rcx, [rbp+57h+var_A0]
0x18000d69d  mov     rbx, [rbp+57h+var_A8]
0x18000d6a1  cmp     rbx, rcx
0x18000d6a4  jz      short loc_18000D6CE
0x18000d6a6  mov     [rbp+57h+var_A8], r15
0x18000d6aa  test    rcx, rcx
0x18000d6ad  jz      short loc_18000D6C5
0x18000d6af  mov     rax, [rcx]
0x18000d6b2  lea     r8, [rbp+57h+var_A8]
0x18000d6b6  lea     rdx, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0
0x18000d6bd  mov     rax, [rax]
0x18000d6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c5  test    rbx, rbx
0x18000d6c8  jnz     loc_18000D9A8
0x18000d6ce  mov     rcx, [rbp+57h+var_A0]
0x18000d6d2  mov     rax, [rcx]
0x18000d6d5  lea     r8, [rbp+57h+var_98]
0x18000d6d9  mov     rdx, rsi
0x18000d6dc  mov     rax, [rax+28h]
0x18000d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6e5  test    eax, eax
0x18000d6e7  js      loc_18000D9BC
0x18000d6ed  mov     rcx, [rbp+57h+var_98]
0x18000d6f1  mov     rbx, [rbp+57h+var_D0]
0x18000d6f5  cmp     rbx, rcx
0x18000d6f8  jz      short loc_18000D722
0x18000d6fa  mov     [rbp+57h+var_D0], r15
0x18000d6fe  test    rcx, rcx
0x18000d701  jz      short loc_18000D719
0x18000d703  mov     rax, [rcx]
0x18000d706  lea     r8, [rbp+57h+var_D0]
0x18000d70a  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x18000d711  mov     rax, [rax]
0x18000d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d719  test    rbx, rbx
0x18000d71c  jnz     loc_18000D9F2
0x18000d722  cmp     [rbp+57h+var_D0], r15
0x18000d726  jz      loc_18000D812
0x18000d72c  mov     rcx, [rbp+57h+var_D0]
0x18000d730  mov     rax, [rcx]
0x18000d733  lea     rdx, [rbp+57h+pv]
0x18000d737  mov     rax, [rax+20h]
0x18000d73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d740  test    eax, eax
0x18000d742  js      loc_18000DA5F
0x18000d748  mov     rcx, [rbp+57h+pv]
0x18000d74c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d753  lea     rax, [rax+1]
0x18000d757  cmp     word ptr [rcx+rax*2], 0
0x18000d75c  jnz     short loc_18000D753
0x18000d75e  lea     rbx, [rax+1]
0x18000d762  lea     r8, [rbx+rbx]; dwBytes
0x18000d766  mov     edx, 8; dwFlags
0x18000d76b  mov     rcx, cs:hHeap; hHeap
0x18000d772  call    cs:__imp_HeapAlloc
0x18000d778  mov     rdi, rax
0x18000d77b  test    rax, rax
0x18000d77e  jnz     loc_18000D95E
0x18000d784  mov     rcx, [rbp+57h+pv]; pv
0x18000d788  test    rcx, rcx
0x18000d78b  jz      short loc_18000D797
0x18000d78d  call    cs:__imp_CoTaskMemFree
0x18000d793  mov     [rbp+57h+pv], r15
0x18000d797  mov     rcx, [rbp+57h+var_D0]
0x18000d79b  test    rcx, rcx
0x18000d79e  jz      short loc_18000D7AD
0x18000d7a0  mov     rax, [rcx]
0x18000d7a3  mov     rax, [rax+10h]
0x18000d7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ac  nop
0x18000d7ad  mov     rcx, [rbp+57h+var_98]
0x18000d7b1  test    rcx, rcx
0x18000d7b4  jz      short loc_18000D7C3
0x18000d7b6  mov     rax, [rcx]
0x18000d7b9  mov     rax, [rax+10h]
0x18000d7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c2  nop
0x18000d7c3  mov     rcx, [rbp+57h+var_A8]
0x18000d7c7  test    rcx, rcx
0x18000d7ca  jz      short loc_18000D7D9
0x18000d7cc  mov     rax, [rcx]
0x18000d7cf  mov     rax, [rax+10h]
0x18000d7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d8  nop
0x18000d7d9  mov     rcx, [rbp+57h+var_A0]
0x18000d7dd  test    rcx, rcx
0x18000d7e0  jz      short loc_18000D7EF
0x18000d7e2  mov     rax, [rcx]
0x18000d7e5  mov     rax, [rax+10h]
0x18000d7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ee  nop
0x18000d7ef  mov     rax, rdi
0x18000d7f2  mov     rcx, [rbp+57h+var_48]
0x18000d7f6  xor     rcx, rsp; StackCookie
0x18000d7f9  call    __security_check_cookie
0x18000d7fe  add     rsp, 0B8h
0x18000d805  pop     r15
0x18000d807  pop     r14
0x18000d809  pop     r13
0x18000d80b  pop     r12
0x18000d80d  pop     rdi
0x18000d80e  pop     rsi
0x18000d80f  pop     rbx
0x18000d810  pop     rbp
0x18000d811  retn
0x18000d812  mov     [rbp+57h+var_B8], r15
0x18000d816  xorps   xmm0, xmm0
0x18000d819  xor     eax, eax
0x18000d81b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000d81f  mov     [rbp+57h+var_80], rax
0x18000d823  mov     rcx, [rbp+57h+var_98]
0x18000d827  mov     rax, [rcx]
0x18000d82a  lea     r8, [rbp+57h+var_B8]
0x18000d82e  xor     edx, edx
0x18000d830  mov     rax, [rax+20h]
0x18000d834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d839  test    eax, eax
0x18000d83b  js      loc_18000DA06
0x18000d841  mov     ebx, r15d
0x18000d844  mov     r12d, 1Fh
0x18000d84a  cmp     ebx, 2
0x18000d84d  jnb     loc_18000D92D
0x18000d853  movsxd  rax, ebx
0x18000d856  movzx   ecx, word ptr [rbp+rax*2+57h+var_C8]
0x18000d85b  mov     [rbp+57h+var_C0], r15
0x18000d85f  mov     [rbp+57h+var_60], 233164C8h
0x18000d866  mov     [rbp+57h+var_5C], 4C7D1B2Ch
0x18000d86d  mov     [rbp+57h+var_58], 71B668BCh
0x18000d874  mov     [rbp+57h+var_54], 67257A68h
0x18000d87b  mov     [rbp+57h+var_50], ecx
0x18000d87e  lea     rcx, [rbp+57h+pvar]; pvar
0x18000d882  call    cs:__imp_PropVariantClear
0x18000d888  mov     rcx, [rbp+57h+var_B8]
0x18000d88c  mov     rax, [rcx]
0x18000d88f  lea     r8, [rbp+57h+pvar]
0x18000d893  lea     rdx, [rbp+57h+var_60]
0x18000d897  mov     rax, [rax+28h]
0x18000d89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a0  test    eax, eax
0x18000d8a2  jnz     loc_18000DA43
0x18000d8a8  cmp     r12w, word ptr [rbp+57h+pvar]
0x18000d8ad  jnz     loc_18000DA43
0x18000d8b3  mov     rcx, [rbp+57h+var_A0]
0x18000d8b7  mov     rax, [rcx]
0x18000d8ba  lea     r8, [rbp+57h+var_C0]
0x18000d8be  mov     rdx, [rbp+57h+pvar+8]
0x18000d8c2  mov     rax, [rax+28h]
0x18000d8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cb  test    eax, eax
0x18000d8cd  jnz     loc_18000DA43
0x18000d8d3  mov     rcx, [rbp+57h+var_C0]
0x18000d8d7  mov     rax, [rbp+57h+var_D0]
0x18000d8db  cmp     rax, rcx
0x18000d8de  jz      short loc_18000D916
0x18000d8e0  mov     r14, rax
0x18000d8e3  mov     rax, r15
0x18000d8e6  mov     [rbp+57h+var_D0], rax
0x18000d8ea  test    rcx, rcx
0x18000d8ed  jz      short loc_18000D90D
0x18000d8ef  mov     rax, [rcx]
0x18000d8f2  lea     r8, [rbp+57h+var_D0]
0x18000d8f6  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x18000d8fd  mov     rax, [rax]
0x18000d900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d905  mov     rax, [rbp+57h+var_D0]
0x18000d909  mov     rcx, [rbp+57h+var_C0]
0x18000d90d  test    r14, r14
0x18000d910  jnz     loc_18000DA27
0x18000d916  test    rax, rax
0x18000d919  jz      short loc_18000D98F
0x18000d91b  test    rcx, rcx
0x18000d91e  jz      short loc_18000D92D
0x18000d920  mov     rax, [rcx]
0x18000d923  mov     rax, [rax+10h]
0x18000d927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92c  nop
0x18000d92d  lea     rcx, [rbp+57h+pvar]; pvar
0x18000d931  call    cs:__imp_PropVariantClear
0x18000d937  nop
0x18000d938  cmp     [rbp+57h+var_D0], 0
0x18000d93d  jz      loc_18000DA51
0x18000d943  mov     rcx, [rbp+57h+var_B8]
0x18000d947  test    rcx, rcx
0x18000d94a  jz      short loc_18000D959
0x18000d94c  mov     rax, [rcx]
0x18000d94f  mov     rax, [rax+10h]
0x18000d953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d958  nop
0x18000d959  jmp     loc_18000D72C
0x18000d95e  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x18000d962  mov     rdx, rbx; unsigned __int64
0x18000d965  mov     rcx, rdi; unsigned __int16 *
0x18000d968  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d96d  test    eax, eax
0x18000d96f  jz      loc_18000D784
0x18000d975  mov     r8, rdi; lpMem
0x18000d978  xor     edx, edx; dwFlags
0x18000d97a  mov     rcx, cs:hHeap; hHeap
0x18000d981  call    cs:__imp_HeapFree
0x18000d987  mov     rdi, r15
0x18000d98a  jmp     loc_18000D784
0x18000d98f  test    rcx, rcx
0x18000d992  jz      short loc_18000D9A1
0x18000d994  mov     rax, [rcx]
0x18000d997  mov     rax, [rax+10h]
0x18000d99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9a0  nop
0x18000d9a1  inc     ebx
0x18000d9a3  jmp     loc_18000D84A
0x18000d9a8  mov     rax, [rbx]
0x18000d9ab  mov     rcx, rbx
0x18000d9ae  mov     rax, [rax+10h]
0x18000d9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b7  jmp     loc_18000D6CE
0x18000d9bc  mov     rcx, [rbp+57h+var_A8]
0x18000d9c0  mov     rax, [rcx]
0x18000d9c3  lea     r8, [rbp+57h+var_D0]
0x18000d9c7  mov     rdx, rsi
0x18000d9ca  mov     rax, [rax+28h]
0x18000d9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d3  test    eax, eax
0x18000d9d5  jns     loc_18000D722
0x18000d9db  mov     r8d, eax
0x18000d9de  mov     rdx, rsi
0x18000d9e1  lea     rcx, aWdmpnpinterfac; "wdmPnPInterfaceFromEndpointWorker: Fail"...
0x18000d9e8  call    Squirt
0x18000d9ed  jmp     loc_18000D784
0x18000d9f2  mov     rax, [rbx]
0x18000d9f5  mov     rcx, rbx
0x18000d9f8  mov     rax, [rax+10h]
0x18000d9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da01  jmp     loc_18000D722
0x18000da06  mov     r8d, eax
0x18000da09  mov     rdx, rsi
0x18000da0c  lea     rcx, aWdmpnpinterfac_1; "wdmPnPInterfaceFromEndpointWorker: Fail"...
0x18000da13  call    Squirt
0x18000da18  nop
0x18000da19  lea     rcx, [rbp+57h+var_B8]
0x18000da1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000da22  jmp     loc_18000D784
0x18000da27  mov     rax, [r14]
0x18000da2a  mov     rcx, r14
0x18000da2d  mov     rax, [rax+10h]
0x18000da31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da36  mov     rax, [rbp+57h+var_D0]
0x18000da3a  mov     rcx, [rbp+57h+var_C0]
0x18000da3e  jmp     loc_18000D916
0x18000da43  lea     rcx, [rbp+57h+var_C0]
0x18000da47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000da4c  jmp     loc_18000D9A1
0x18000da51  lea     rcx, [rbp+57h+var_B8]
0x18000da55  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000da5a  jmp     loc_18000D784
0x18000da5f  mov     r8d, eax
0x18000da62  mov     rdx, rsi
0x18000da65  lea     rcx, aWdmpnpinterfac_0; "wdmPnPInterfaceFromEndpointWorker: Fail"...
0x18000da6c  call    Squirt
0x18000da71  jmp     loc_18000D784
```
