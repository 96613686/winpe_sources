# s_DeviceCredentialRpcGetDeviceInfo

- ea: `0x18009f360`
- end: `0x18009f694`
- name: `s_DeviceCredentialRpcGetDeviceInfo`
- size: `820`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x180029940`
- `0x180081438`
- `0x18009b8b0`
- `0x18009b928`
- `0x18009f360`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f544`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f553`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f553`

## string_xrefs

- `0x18009f393`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f3f7`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f458`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f4b4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f51c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f565`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`

## pseudocode

```c
__int64 __fastcall s_DeviceCredentialRpcGetDeviceInfo(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  void *v9; // rcx
  int v10; // edi
  void *v11; // rdx
  wil::details *v12; // rcx
  void *v13; // rcx
  wil::details *v14; // rcx
  void *v15; // rcx
  wil::details *v16; // rcx
  void *v17; // rcx
  unsigned int v18; // r15d
  wil::details *v19; // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v21; // rax
  void *v22; // rdx
  _DWORD *v23; // rcx
  void *v24; // rdx
  wil::details *v25; // rcx
  wil::details *v26; // rcx
  wil::details *v27; // rcx
  wil::details *v28; // rcx
  wil::details *v29; // rax
  wil::details *v30; // rax
  wil::details *v31; // rax
  int v32; // eax
  wil::details *v33; // rax
  wil::details *v34; // rcx
  wil::details *v35; // rcx
  wil::details *v36; // rcx
  wil::details *v37; // rcx
  wil::details *v38; // [rsp+20h] [rbp-30h] BYREF
  wil::details *v39; // [rsp+28h] [rbp-28h] BYREF
  wil::details **v40; // [rsp+30h] [rbp-20h] BYREF
  __int64 v41; // [rsp+38h] [rbp-18h]
  char v42; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  wil::details *v44; // [rsp+88h] [rbp+38h] BYREF
  wil::details *v45; // [rsp+98h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v6 = 424;
LABEL_3:
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)0x80004003LL,
      (int)v38);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 425;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 2;
  v9 = *(void **)a1;
  v44 = 0;
  v40 = &v44;
  v41 = 0;
  v42 = 1;
  v10 = CopyToHeapString(v9);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v40);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)(unsigned int)v10,
      (int)v38);
LABEL_9:
    v12 = v44;
    v44 = 0;
    if ( v12 )
      wil::details::FreeProcessHeap(v12, v11);
    return (unsigned int)v10;
  }
  v13 = *(void **)(a1 + 8);
  v40 = &v45;
  v45 = 0;
  v41 = 0;
  v42 = 1;
  v10 = CopyToHeapString(v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v40);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)(unsigned int)v10,
      (int)v38);
LABEL_14:
    v14 = v45;
    v45 = 0;
    if ( v14 )
      wil::details::FreeProcessHeap(v14, v11);
    goto LABEL_9;
  }
  v15 = *(void **)(a1 + 16);
  v40 = &v38;
  v38 = 0;
  v41 = 0;
  v42 = 1;
  v10 = CopyToHeapString(v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v40);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)(unsigned int)v10,
      (int)v38);
LABEL_18:
    v16 = v38;
    v38 = 0;
    if ( v16 )
      wil::details::FreeProcessHeap(v16, v11);
    goto LABEL_14;
  }
  v17 = *(void **)(a1 + 40);
  v18 = *(_DWORD *)(a1 + 48);
  v39 = 0;
  if ( v17 )
  {
    v41 = 0;
    v40 = &v39;
    v42 = 1;
    v10 = CopyToHeapMemory(v17, v18);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v40);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
        (const char *)(unsigned int)v10,
        (int)v38);
      v19 = v39;
      v39 = 0;
      if ( v19 )
        wil::details::FreeProcessHeap(v19, v11);
      goto LABEL_18;
    }
  }
  ProcessHeap = GetProcessHeap();
  v21 = HeapAlloc(ProcessHeap, 0, 0x38u);
  v23 = v21;
  if ( !v21 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)0x8007000ELL,
      (int)v38);
    v25 = v39;
    v39 = 0;
    if ( v25 )
      wil::details::FreeProcessHeap(v25, v24);
    v26 = v38;
    v38 = 0;
    if ( v26 )
      wil::details::FreeProcessHeap(v26, v24);
    v27 = v45;
    v45 = 0;
    if ( v27 )
      wil::details::FreeProcessHeap(v27, v24);
    v28 = v44;
    v44 = 0;
    if ( v28 )
      wil::details::FreeProcessHeap(v28, v24);
    return v7;
  }
  *v21 = *(_DWORD *)(a1 + 32);
  v29 = v44;
  v44 = 0;
  *((_QWORD *)v23 + 1) = v29;
  v30 = v45;
  v45 = 0;
  *((_QWORD *)v23 + 2) = v30;
  v31 = v38;
  v38 = 0;
  *((_QWORD *)v23 + 3) = v31;
  v32 = 0;
  if ( *(_QWORD *)a1 )
    v32 = *(_DWORD *)(a1 + 28);
  v23[11] = v32;
  v33 = v39;
  v39 = 0;
  *((_QWORD *)v23 + 4) = v33;
  v23[10] = v18;
  v23[12] = *(_DWORD *)(a1 + 52);
  v23[13] = *(_BYTE *)(a1 + 56) != 0;
  *a2 = v23;
  v34 = v39;
  *a3 = *(_DWORD *)(a1 + 24);
  v39 = 0;
  if ( v34 )
    wil::details::FreeProcessHeap(v34, v22);
  v35 = v38;
  v38 = 0;
  if ( v35 )
    wil::details::FreeProcessHeap(v35, v22);
  v36 = v45;
  v45 = 0;
  if ( v36 )
    wil::details::FreeProcessHeap(v36, v22);
  v37 = v44;
  v44 = 0;
  if ( v37 )
    wil::details::FreeProcessHeap(v37, v22);
  return 0;
}

```

## disassembly

```asm
0x18009f360  mov     [rsp-28h+arg_0], rbx
0x18009f365  mov     [rsp-28h+arg_10], rsi
0x18009f36a  push    rbp
0x18009f36b  push    rdi
0x18009f36c  push    r12
0x18009f36e  push    r14
0x18009f370  push    r15
0x18009f372  mov     rbp, rsp
0x18009f375  sub     rsp, 50h
0x18009f379  xor     r12d, r12d
0x18009f37c  mov     rsi, r8
0x18009f37f  mov     r14, rdx
0x18009f382  mov     rbx, rcx
0x18009f385  test    rdx, rdx
0x18009f388  jnz     short loc_18009F3AE
0x18009f38a  mov     edx, 1A8h; void *
0x18009f38f  mov     rcx, [rbp+28h]; this
0x18009f393  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f39a  mov     ebx, 80004003h
0x18009f39f  mov     r9d, ebx; char *
0x18009f3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f3a7  mov     eax, ebx
0x18009f3a9  jmp     loc_18009F67B
0x18009f3ae  test    rsi, rsi
0x18009f3b1  jnz     short loc_18009F3BA
0x18009f3b3  mov     edx, 1A9h
0x18009f3b8  jmp     short loc_18009F38F
0x18009f3ba  mov     [rdx], r12
0x18009f3bd  lea     rax, [rbp+arg_8]
0x18009f3c1  mov     dword ptr [r8], 2
0x18009f3c8  lea     rdx, [rbp+var_18]
0x18009f3cc  mov     rcx, [rcx]; Source
0x18009f3cf  mov     [rbp+arg_8], r12
0x18009f3d3  mov     [rbp+var_20], rax
0x18009f3d7  mov     [rbp+var_18], r12
0x18009f3db  mov     [rbp+var_10], 1
0x18009f3df  call    CopyToHeapString
0x18009f3e4  lea     rcx, [rbp+var_20]
0x18009f3e8  mov     edi, eax
0x18009f3ea  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f3ef  test    edi, edi
0x18009f3f1  jns     short loc_18009F424
0x18009f3f3  mov     rcx, [rbp+28h]; this
0x18009f3f7  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f3fe  mov     r9d, edi; char *
0x18009f401  mov     edx, 1B2h; void *
0x18009f406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f40b  mov     rcx, [rbp+arg_8]; this
0x18009f40f  mov     [rbp+arg_8], r12
0x18009f413  test    rcx, rcx
0x18009f416  jz      short loc_18009F41D
0x18009f418  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f41d  mov     eax, edi
0x18009f41f  jmp     loc_18009F67B
0x18009f424  mov     rcx, [rbx+8]; Source
0x18009f428  lea     rax, [rbp+arg_18]
0x18009f42c  lea     rdx, [rbp+var_18]
0x18009f430  mov     [rbp+var_20], rax
0x18009f434  mov     [rbp+arg_18], r12
0x18009f438  mov     [rbp+var_18], r12
0x18009f43c  mov     [rbp+var_10], 1
0x18009f440  call    CopyToHeapString
0x18009f445  lea     rcx, [rbp+var_20]
0x18009f449  mov     edi, eax
0x18009f44b  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f450  test    edi, edi
0x18009f452  jns     short loc_18009F480
0x18009f454  mov     rcx, [rbp+28h]; this
0x18009f458  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f45f  mov     r9d, edi; char *
0x18009f462  mov     edx, 1B7h; void *
0x18009f467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f46c  mov     rcx, [rbp+arg_18]; this
0x18009f470  mov     [rbp+arg_18], r12
0x18009f474  test    rcx, rcx
0x18009f477  jz      short loc_18009F40B
0x18009f479  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f47e  jmp     short loc_18009F40B
0x18009f480  mov     rcx, [rbx+10h]; Source
0x18009f484  lea     rax, [rbp+var_30]
0x18009f488  lea     rdx, [rbp+var_18]
0x18009f48c  mov     [rbp+var_20], rax
0x18009f490  mov     [rbp+var_30], r12
0x18009f494  mov     [rbp+var_18], r12
0x18009f498  mov     [rbp+var_10], 1
0x18009f49c  call    CopyToHeapString
0x18009f4a1  lea     rcx, [rbp+var_20]
0x18009f4a5  mov     edi, eax
0x18009f4a7  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f4ac  test    edi, edi
0x18009f4ae  jns     short loc_18009F4DC
0x18009f4b0  mov     rcx, [rbp+28h]; this
0x18009f4b4  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f4bb  mov     r9d, edi; char *
0x18009f4be  mov     edx, 1BCh; void *
0x18009f4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f4c8  mov     rcx, [rbp+var_30]; this
0x18009f4cc  mov     [rbp+var_30], r12
0x18009f4d0  test    rcx, rcx
0x18009f4d3  jz      short loc_18009F46C
0x18009f4d5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f4da  jmp     short loc_18009F46C
0x18009f4dc  mov     rcx, [rbx+28h]; Source
0x18009f4e0  mov     r15d, [rbx+30h]
0x18009f4e4  mov     [rbp+var_28], r12
0x18009f4e8  test    rcx, rcx
0x18009f4eb  jz      short loc_18009F544
0x18009f4ed  lea     rax, [rbp+var_28]
0x18009f4f1  mov     [rbp+var_18], r12
0x18009f4f5  mov     edx, r15d; SourceSize
0x18009f4f8  mov     [rbp+var_20], rax
0x18009f4fc  lea     r8, [rbp+var_18]
0x18009f500  mov     [rbp+var_10], 1
0x18009f504  call    CopyToHeapMemory
0x18009f509  lea     rcx, [rbp+var_20]
0x18009f50d  mov     edi, eax
0x18009f50f  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f514  test    edi, edi
0x18009f516  jns     short loc_18009F544
0x18009f518  mov     rcx, [rbp+28h]; this
0x18009f51c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f523  mov     r9d, edi; char *
0x18009f526  mov     edx, 1C6h; void *
0x18009f52b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f530  mov     rcx, [rbp+var_28]; this
0x18009f534  mov     [rbp+var_28], r12
0x18009f538  test    rcx, rcx
0x18009f53b  jz      short loc_18009F4C8
0x18009f53d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f542  jmp     short loc_18009F4C8
0x18009f544  call    cs:__imp_GetProcessHeap
0x18009f54a  xor     edx, edx; dwFlags
0x18009f54c  mov     rcx, rax; hHeap
0x18009f54f  lea     r8d, [rdx+38h]; dwBytes
0x18009f553  call    cs:__imp_HeapAlloc
0x18009f559  mov     rcx, rax
0x18009f55c  test    rax, rax
0x18009f55f  jnz     short loc_18009F5CF
0x18009f561  mov     rcx, [rbp+28h]; this
0x18009f565  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f56c  mov     ebx, 8007000Eh
0x18009f571  mov     edx, 1CBh; void *
0x18009f576  mov     r9d, ebx; char *
0x18009f579  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f57e  mov     rcx, [rbp+var_28]; this
0x18009f582  mov     [rbp+var_28], r12
0x18009f586  test    rcx, rcx
0x18009f589  jz      short loc_18009F590
0x18009f58b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f590  mov     rcx, [rbp+var_30]; this
0x18009f594  mov     [rbp+var_30], r12
0x18009f598  test    rcx, rcx
0x18009f59b  jz      short loc_18009F5A2
0x18009f59d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f5a2  mov     rcx, [rbp+arg_18]; this
0x18009f5a6  mov     [rbp+arg_18], r12
0x18009f5aa  test    rcx, rcx
0x18009f5ad  jz      short loc_18009F5B4
0x18009f5af  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f5b4  mov     rcx, [rbp+arg_8]; this
0x18009f5b8  mov     [rbp+arg_8], r12
0x18009f5bc  test    rcx, rcx
0x18009f5bf  jz      loc_18009F3A7
0x18009f5c5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f5ca  jmp     loc_18009F3A7
0x18009f5cf  mov     eax, [rbx+20h]
0x18009f5d2  mov     [rcx], eax
0x18009f5d4  mov     rax, [rbp+arg_8]
0x18009f5d8  mov     [rbp+arg_8], r12
0x18009f5dc  mov     [rcx+8], rax
0x18009f5e0  mov     rax, [rbp+arg_18]
0x18009f5e4  mov     [rbp+arg_18], r12
0x18009f5e8  mov     [rcx+10h], rax
0x18009f5ec  mov     rax, [rbp+var_30]
0x18009f5f0  mov     [rbp+var_30], r12
0x18009f5f4  mov     [rcx+18h], rax
0x18009f5f8  mov     eax, r12d
0x18009f5fb  cmp     [rbx], r12
0x18009f5fe  jz      short loc_18009F603
0x18009f600  mov     eax, [rbx+1Ch]
0x18009f603  mov     [rcx+2Ch], eax
0x18009f606  mov     rax, [rbp+var_28]
0x18009f60a  mov     [rbp+var_28], r12
0x18009f60e  mov     [rcx+20h], rax
0x18009f612  mov     [rcx+28h], r15d
0x18009f616  mov     eax, [rbx+34h]
0x18009f619  mov     [rcx+30h], eax
0x18009f61c  mov     eax, r12d
0x18009f61f  cmp     [rbx+38h], r12b
0x18009f623  setnz   al
0x18009f626  mov     [rcx+34h], eax
0x18009f629  mov     [r14], rcx
0x18009f62c  mov     rcx, [rbp+var_28]; this
0x18009f630  mov     eax, [rbx+18h]
0x18009f633  mov     [rsi], eax
0x18009f635  mov     [rbp+var_28], r12
0x18009f639  test    rcx, rcx
0x18009f63c  jz      short loc_18009F643
0x18009f63e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f643  mov     rcx, [rbp+var_30]; this
0x18009f647  mov     [rbp+var_30], r12
0x18009f64b  test    rcx, rcx
0x18009f64e  jz      short loc_18009F655
0x18009f650  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f655  mov     rcx, [rbp+arg_18]; this
0x18009f659  mov     [rbp+arg_18], r12
0x18009f65d  test    rcx, rcx
0x18009f660  jz      short loc_18009F667
0x18009f662  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f667  mov     rcx, [rbp+arg_8]; this
0x18009f66b  mov     [rbp+arg_8], r12
0x18009f66f  test    rcx, rcx
0x18009f672  jz      short loc_18009F679
0x18009f674  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f679  xor     eax, eax
0x18009f67b  lea     r11, [rsp+50h+var_s0]
0x18009f680  mov     rbx, [r11+30h]
0x18009f684  mov     rsi, [r11+40h]
0x18009f688  mov     rsp, r11
0x18009f68b  pop     r15
0x18009f68d  pop     r14
0x18009f68f  pop     r12
0x18009f691  pop     rdi
0x18009f692  pop     rbp
0x18009f693  retn
```
