# CDeploymentSessionWrapper::RequestPayloadFiles(IDeploymentDownloadRequest *,IDeploymentSessionHelper *,ushort const *)

- ea: `0x18019e940`
- end: `0x18019f134`
- name: `?RequestPayloadFiles@CDeploymentSessionWrapper@@AEAAJPEAUIDeploymentDownloadRequest@@PEAVIDeploymentSessionHelper@@PEBG@Z`
- size: `2036`
- prototype: `__int64 __fastcall(CDeploymentSessionWrapper *__hidden this, struct IDeploymentDownloadRequest *, struct IDeploymentSessionHelper *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180199068`

## callees

- `0x1800031d0`
- `0x180068c4c`
- `0x18006fab0`
- `0x1801961c4`
- `0x180198e84`
- `0x18019cb24`
- `0x18019e940`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ebe3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ecc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f0af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ebe3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019ecc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f0af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ebce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ecb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f09a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ebce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ecb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ebb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ebb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f0cb`

## pseudocode

```c
__int64 __fastcall CDeploymentSessionWrapper::RequestPayloadFiles(
        CDeploymentSessionWrapper *this,
        struct IDeploymentDownloadRequest *a2,
        struct IDeploymentSessionHelper *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v9; // rsi
  __int64 v10; // rcx
  unsigned int v11; // edi
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r12d
  int v19; // eax
  HANDLE ProcessHeap; // rax
  int v21; // eax
  void *v22; // rbx
  int StringCch; // eax
  int Internal; // eax
  HANDLE v25; // rax
  int v26; // eax
  void *v27; // rbx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  HANDLE v34; // rax
  HANDLE v35; // rax
  int v37; // [rsp+20h] [rbp-69h]
  int v38; // [rsp+28h] [rbp-61h]
  __int64 v39; // [rsp+30h] [rbp-59h] BYREF
  __int64 v40; // [rsp+38h] [rbp-51h]
  __int64 v41; // [rsp+40h] [rbp-49h]
  const unsigned __int16 *v42; // [rsp+48h] [rbp-41h]
  unsigned int v43; // [rsp+50h] [rbp-39h] BYREF
  __int64 v44; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v45; // [rsp+60h] [rbp-29h] BYREF
  __int64 v46; // [rsp+68h] [rbp-21h] BYREF
  LPVOID Src; // [rsp+70h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-11h] BYREF
  __int64 v49; // [rsp+80h] [rbp-9h] BYREF
  __int64 v50; // [rsp+88h] [rbp-1h] BYREF

  v4 = 0;
  v42 = a4;
  v5 = 0;
  v49 = 0;
  v50 = 0;
  v43 = 0;
  v44 = 0;
  pv = 0;
  v40 = 0;
  Src = 0;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  if ( !a2 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024809;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942487LL);
      v38 = -2147024809;
      v37 = 419;
LABEL_4:
      v13 = v9;
      goto LABEL_87;
    }
    goto LABEL_89;
  }
  if ( !a3 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024809;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942487LL);
      v38 = -2147024809;
      v37 = 420;
      goto LABEL_4;
    }
LABEL_89:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
    goto LABEL_90;
  }
  v14 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, &v49);
  v11 = v14;
  if ( v14 < 0 )
  {
    v15 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_89;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v14);
    v38 = v11;
    v37 = 422;
LABEL_86:
    v13 = v15;
LABEL_87:
    v33 = CFCLogLiteT<CEmptyType>::LogFormat(
            v13,
            4 - (unsigned int)(v12 != 0),
            L"%s(%d): Result = 0x%X",
            L"CDeploymentSessionWrapper::RequestPayloadFiles",
            v37,
            v38,
            v39);
    v10 = (unsigned int)v33;
    if ( v33 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v33);
    goto LABEL_89;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 24LL))(v49, &v43);
  v11 = v16;
  if ( v16 < 0 )
  {
    v15 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_89;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v16);
    v38 = v11;
    v37 = 423;
    goto LABEL_86;
  }
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(
      *(_QWORD *)this,
      2,
      L"DeploymentSessionWrapper: Download Request File Count = [%ld]",
      v43);
  v17 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, &v50);
  v11 = v17;
  if ( v17 < 0 )
  {
    v15 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_89;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v17);
    v38 = v11;
    v37 = 426;
    goto LABEL_86;
  }
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(
      *(_QWORD *)this,
      2,
      L"DeploymentSessionWrapper: Download Request Size = [%lld]",
      v50);
  v18 = 0;
  if ( v43 )
  {
    while ( 1 )
    {
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper: Download Request File Index = [%ld]",
          v18);
      if ( v44 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        v44 = 0;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 32LL))(v49, v18, &v44);
      v11 = v19;
      if ( v19 < 0 )
        break;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v5 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v5 = 0;
        v40 = 0;
      }
      v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v44 + 24LL))(v44, &pv);
      v11 = v21;
      if ( v21 < 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v21);
        v38 = v11;
        v37 = 438;
        goto LABEL_86;
      }
      v22 = pv;
      if ( pv )
      {
        LODWORD(v39) = 0;
        StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(pv, &v39);
        v11 = StringCch;
        if ( StringCch >= 0 )
        {
          Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v22);
          v11 = Internal;
          if ( Internal < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
          v5 = v40;
        }
        else
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
        if ( (v11 & 0x80000000) != 0 )
        {
          v15 = *(_QWORD *)this;
          v10 = 0;
          if ( !*(_QWORD *)this )
            goto LABEL_89;
          v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, v11);
          v38 = v11;
          v37 = 442;
          goto LABEL_86;
        }
        if ( *(_QWORD *)this )
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            2,
            L"DeploymentSessionWrapper:         File Identifier = [%s]",
            v5);
      }
      if ( Src )
      {
        CoTaskMemFree(Src);
        Src = 0;
      }
      if ( v4 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, (LPVOID)(v4 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v4 = 0;
        v41 = 0;
      }
      v26 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v44 + 40LL))(v44, &Src);
      v11 = v26;
      if ( v26 < 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v26);
        v38 = v11;
        v37 = 448;
        goto LABEL_86;
      }
      v27 = Src;
      if ( Src
        && (LODWORD(v39) = 0,
            v32 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v39),
            v11 = v32,
            v32 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
      }
      else
      {
        v28 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v27);
        v11 = v28;
        if ( v28 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v28);
        v4 = v41;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      if ( (v11 & 0x80000000) != 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, v11);
        v38 = v11;
        v37 = 449;
        goto LABEL_86;
      }
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper:         File Name = [%s]",
          v4);
      if ( v46 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        v46 = 0;
      }
      v29 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL))(v44, &v46);
      v11 = v29;
      if ( v29 < 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v29);
        v38 = v11;
        v37 = 453;
        goto LABEL_86;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 24LL))(v46, &v45);
      v11 = v30;
      if ( v30 < 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v30);
        v38 = v11;
        v37 = 454;
        goto LABEL_86;
      }
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper:         File Range Count = [%lu]",
          v45);
      if ( v45 )
      {
        v15 = *(_QWORD *)this;
        if ( *(_QWORD *)this )
        {
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            4,
            L"DeploymentSessionWrapper: File Range Request is not supported");
          v15 = *(_QWORD *)this;
        }
        v10 = 0;
        v11 = -2147024846;
        if ( v15 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, 2147942450LL);
          v38 = -2147024846;
          v37 = 459;
          goto LABEL_86;
        }
        goto LABEL_89;
      }
      v31 = (*(__int64 (__fastcall **)(struct IDeploymentSessionHelper *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a3 + 16LL))(
              a3,
              v5,
              v4,
              v42);
      v11 = v31;
      if ( v31 < 0 )
      {
        v15 = *(_QWORD *)this;
        v10 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_89;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v31);
        v38 = v11;
        v37 = 462;
        goto LABEL_86;
      }
      if ( ++v18 >= v43 )
        goto LABEL_90;
    }
    v15 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_89;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(*(_QWORD *)this, (unsigned int)v19);
    v38 = v11;
    v37 = 434;
    goto LABEL_86;
  }
LABEL_90:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v4 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, (LPVOID)(v4 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( Src )
  {
    CoTaskMemFree(Src);
    Src = 0;
  }
  if ( v5 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return v11;
}

```

## disassembly

```asm
0x18019e940  push    rbp
0x18019e942  push    rbx
0x18019e943  push    rsi
0x18019e944  push    rdi
0x18019e945  push    r12
0x18019e947  push    r13
0x18019e949  push    r14
0x18019e94b  push    r15
0x18019e94d  lea     rbp, [rsp-1Fh]
0x18019e952  sub     rsp, 0A8h
0x18019e959  mov     rax, cs:__security_cookie
0x18019e960  xor     rax, rsp
0x18019e963  mov     [rbp+57h+var_50], rax
0x18019e967  xor     r14d, r14d
0x18019e96a  mov     [rbp+57h+var_98], r9
0x18019e96e  xor     r15d, r15d
0x18019e971  mov     [rbp+57h+var_60], 0
0x18019e979  mov     [rbp+57h+var_58], 0
0x18019e981  mov     r13, r8
0x18019e984  mov     [rbp+57h+var_90], 0
0x18019e98b  mov     rbx, rdx
0x18019e98e  mov     [rbp+57h+var_88], 0
0x18019e996  mov     rsi, rcx
0x18019e999  mov     [rbp+57h+pv], 0
0x18019e9a1  mov     [rbp+57h+var_A8], r15
0x18019e9a5  mov     [rbp+57h+Src], r15
0x18019e9a9  mov     [rbp+57h+var_A0], r14
0x18019e9ad  mov     [rbp+57h+var_78], r14
0x18019e9b1  mov     [rbp+57h+var_80], r14d
0x18019e9b5  test    rdx, rdx
0x18019e9b8  jnz     short loc_18019E9F4
0x18019e9ba  mov     rsi, [rsi]
0x18019e9bd  xor     ecx, ecx
0x18019e9bf  mov     ebx, 80070057h
0x18019e9c4  mov     edi, ebx
0x18019e9c6  test    rsi, rsi
0x18019e9c9  jz      loc_18019F022
0x18019e9cf  mov     rax, [rsi]
0x18019e9d2  mov     edx, ebx
0x18019e9d4  mov     rcx, rsi
0x18019e9d7  mov     rax, [rax+20h]
0x18019e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e9e0  mov     [rsp+0E0h+var_B8], ebx
0x18019e9e4  mov     [rsp+0E0h+var_C0], 1A3h
0x18019e9ec  mov     rcx, rsi
0x18019e9ef  jmp     loc_18019EFFD
0x18019e9f4  test    r13, r13
0x18019e9f7  jnz     short loc_18019EA2D
0x18019e9f9  mov     rsi, [rsi]
0x18019e9fc  xor     ecx, ecx
0x18019e9fe  mov     ebx, 80070057h
0x18019ea03  mov     edi, ebx
0x18019ea05  test    rsi, rsi
0x18019ea08  jz      loc_18019F022
0x18019ea0e  mov     rax, [rsi]
0x18019ea11  mov     edx, ebx
0x18019ea13  mov     rcx, rsi
0x18019ea16  mov     rax, [rax+20h]
0x18019ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea1f  mov     [rsp+0E0h+var_B8], ebx
0x18019ea23  mov     [rsp+0E0h+var_C0], 1A4h
0x18019ea2b  jmp     short loc_18019E9EC
0x18019ea2d  mov     rax, [rdx]
0x18019ea30  mov     rcx, rbx
0x18019ea33  lea     rdx, [rbp+57h+var_60]
0x18019ea37  mov     rax, [rax+28h]
0x18019ea3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea40  mov     edi, eax
0x18019ea42  test    eax, eax
0x18019ea44  jns     short loc_18019EA76
0x18019ea46  mov     rbx, [rsi]
0x18019ea49  xor     ecx, ecx
0x18019ea4b  test    rbx, rbx
0x18019ea4e  jz      loc_18019F022
0x18019ea54  mov     rcx, [rbx]
0x18019ea57  mov     edx, edi
0x18019ea59  mov     rax, [rcx+20h]
0x18019ea5d  mov     rcx, rbx
0x18019ea60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea65  mov     [rsp+0E0h+var_B8], edi
0x18019ea69  mov     [rsp+0E0h+var_C0], 1A6h
0x18019ea71  jmp     loc_18019EFFA
0x18019ea76  mov     rcx, [rbp+57h+var_60]
0x18019ea7a  lea     rdx, [rbp+57h+var_90]
0x18019ea7e  mov     rax, [rcx]
0x18019ea81  mov     rax, [rax+18h]
0x18019ea85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea8a  mov     edi, eax
0x18019ea8c  test    eax, eax
0x18019ea8e  jns     short loc_18019EAC0
0x18019ea90  mov     rbx, [rsi]
0x18019ea93  xor     ecx, ecx
0x18019ea95  test    rbx, rbx
0x18019ea98  jz      loc_18019F022
0x18019ea9e  mov     rax, [rbx]
0x18019eaa1  mov     edx, edi
0x18019eaa3  mov     rcx, rbx
0x18019eaa6  mov     rax, [rax+20h]
0x18019eaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eaaf  mov     [rsp+0E0h+var_B8], edi
0x18019eab3  mov     [rsp+0E0h+var_C0], 1A7h
0x18019eabb  jmp     loc_18019EFFA
0x18019eac0  mov     rcx, [rsi]
0x18019eac3  mov     r12d, 2
0x18019eac9  test    rcx, rcx
0x18019eacc  jz      short loc_18019EAE1
0x18019eace  mov     r9d, [rbp+57h+var_90]
0x18019ead2  lea     r8, aDeploymentsess_1; "DeploymentSessionWrapper: Download Requ"...
0x18019ead9  mov     edx, r12d
0x18019eadc  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019eae1  mov     rax, [rbx]
0x18019eae4  lea     rdx, [rbp+57h+var_58]
0x18019eae8  mov     rcx, rbx
0x18019eaeb  mov     rax, [rax+38h]
0x18019eaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eaf4  mov     edi, eax
0x18019eaf6  test    eax, eax
0x18019eaf8  jns     short loc_18019EB2A
0x18019eafa  mov     rbx, [rsi]
0x18019eafd  xor     ecx, ecx
0x18019eaff  test    rbx, rbx
0x18019eb02  jz      loc_18019F022
0x18019eb08  mov     rax, [rbx]
0x18019eb0b  mov     edx, edi
0x18019eb0d  mov     rcx, rbx
0x18019eb10  mov     rax, [rax+20h]
0x18019eb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb19  mov     [rsp+0E0h+var_B8], edi
0x18019eb1d  mov     [rsp+0E0h+var_C0], 1AAh
0x18019eb25  jmp     loc_18019EFFA
0x18019eb2a  mov     rcx, [rsi]
0x18019eb2d  test    rcx, rcx
0x18019eb30  jz      short loc_18019EB45
0x18019eb32  mov     r9, [rbp+57h+var_58]
0x18019eb36  lea     r8, aDeploymentsess_9; "DeploymentSessionWrapper: Download Requ"...
0x18019eb3d  mov     edx, r12d
0x18019eb40  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019eb45  xor     r12d, r12d
0x18019eb48  cmp     [rbp+57h+var_90], r12d
0x18019eb4c  jbe     loc_18019F027
0x18019eb52  mov     rcx, [rsi]
0x18019eb55  test    rcx, rcx
0x18019eb58  jz      short loc_18019EB6E
0x18019eb5a  mov     r9d, r12d
0x18019eb5d  lea     r8, aDeploymentsess_3; "DeploymentSessionWrapper: Download Requ"...
0x18019eb64  mov     edx, 2
0x18019eb69  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019eb6e  mov     rcx, [rbp+57h+var_88]
0x18019eb72  test    rcx, rcx
0x18019eb75  jz      short loc_18019EB8B
0x18019eb77  mov     rax, [rcx]
0x18019eb7a  mov     rax, [rax+10h]
0x18019eb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb83  mov     [rbp+57h+var_88], 0
0x18019eb8b  mov     rcx, [rbp+57h+var_60]
0x18019eb8f  lea     r8, [rbp+57h+var_88]
0x18019eb93  mov     edx, r12d
0x18019eb96  mov     rax, [rcx]
0x18019eb99  mov     rax, [rax+20h]
0x18019eb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eba2  mov     edi, eax
0x18019eba4  test    eax, eax
0x18019eba6  js      loc_18019EFD3
0x18019ebac  mov     rcx, [rbp+57h+pv]; pv
0x18019ebb0  test    rcx, rcx
0x18019ebb3  jz      short loc_18019EBC9
0x18019ebb5  call    cs:__imp_CoTaskMemFree
0x18019ebbc  nop     dword ptr [rax+rax+00h]
0x18019ebc1  mov     [rbp+57h+pv], 0
0x18019ebc9  test    r15, r15
0x18019ebcc  jz      short loc_18019EBFD
0x18019ebce  call    cs:__imp_GetProcessHeap
0x18019ebd5  nop     dword ptr [rax+rax+00h]
0x18019ebda  lea     r8, [r15-4]; lpMem
0x18019ebde  xor     edx, edx; dwFlags
0x18019ebe0  mov     rcx, rax; hHeap
0x18019ebe3  call    cs:__imp_HeapFree
0x18019ebea  nop     dword ptr [rax+rax+00h]
0x18019ebef  xor     ecx, ecx
0x18019ebf1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019ebf6  xor     r15d, r15d
0x18019ebf9  mov     [rbp+57h+var_A8], r15
0x18019ebfd  mov     rcx, [rbp+57h+var_88]
0x18019ec01  lea     rdx, [rbp+57h+pv]
0x18019ec05  mov     rax, [rcx]
0x18019ec08  mov     rax, [rax+18h]
0x18019ec0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ec11  mov     edi, eax
0x18019ec13  test    eax, eax
0x18019ec15  js      loc_18019EFAA
0x18019ec1b  mov     rbx, [rbp+57h+pv]
0x18019ec1f  test    rbx, rbx
0x18019ec22  jz      short loc_18019EC91
0x18019ec24  lea     rdx, [rbp+57h+var_B0]
0x18019ec28  mov     dword ptr [rbp+57h+var_B0], 0
0x18019ec2f  mov     rcx, rbx
0x18019ec32  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18019ec37  mov     edi, eax
0x18019ec39  test    eax, eax
0x18019ec3b  jns     short loc_18019EC46
0x18019ec3d  mov     ecx, eax
0x18019ec3f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019ec44  jmp     short loc_18019EC66
0x18019ec46  mov     edx, dword ptr [rbp+57h+var_B0]
0x18019ec49  lea     r8, [rbp+57h+var_A8]
0x18019ec4d  mov     rcx, rbx; Src
0x18019ec50  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18019ec55  mov     edi, eax
0x18019ec57  test    eax, eax
0x18019ec59  jns     short loc_18019EC62
0x18019ec5b  mov     ecx, eax
0x18019ec5d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019ec62  mov     r15, [rbp+57h+var_A8]
0x18019ec66  mov     ecx, edi
0x18019ec68  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019ec6d  test    edi, edi
0x18019ec6f  js      loc_18019EE3F
0x18019ec75  mov     rcx, [rsi]
0x18019ec78  test    rcx, rcx
0x18019ec7b  jz      short loc_18019EC91
0x18019ec7d  mov     r9, r15
0x18019ec80  lea     r8, aDeploymentsess_0; "DeploymentSessionWrapper:         File "...
0x18019ec87  mov     edx, 2
0x18019ec8c  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019ec91  mov     rcx, [rbp+57h+Src]; pv
0x18019ec95  test    rcx, rcx
0x18019ec98  jz      short loc_18019ECAE
0x18019ec9a  call    cs:__imp_CoTaskMemFree
0x18019eca1  nop     dword ptr [rax+rax+00h]
0x18019eca6  mov     [rbp+57h+Src], 0
0x18019ecae  test    r14, r14
0x18019ecb1  jz      short loc_18019ECE2
0x18019ecb3  call    cs:__imp_GetProcessHeap
0x18019ecba  nop     dword ptr [rax+rax+00h]
0x18019ecbf  lea     r8, [r14-4]; lpMem
0x18019ecc3  xor     edx, edx; dwFlags
0x18019ecc5  mov     rcx, rax; hHeap
0x18019ecc8  call    cs:__imp_HeapFree
0x18019eccf  nop     dword ptr [rax+rax+00h]
0x18019ecd4  xor     ecx, ecx
0x18019ecd6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019ecdb  xor     r14d, r14d
0x18019ecde  mov     [rbp+57h+var_A0], r14
0x18019ece2  mov     rcx, [rbp+57h+var_88]
0x18019ece6  lea     rdx, [rbp+57h+Src]
0x18019ecea  mov     rax, [rcx]
0x18019eced  mov     rax, [rax+28h]
0x18019ecf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ecf6  mov     edi, eax
0x18019ecf8  test    eax, eax
0x18019ecfa  js      loc_18019EF7D
0x18019ed00  mov     rbx, [rbp+57h+Src]
0x18019ed04  test    rbx, rbx
0x18019ed07  jnz     loc_18019EE09
0x18019ed0d  xor     edx, edx
0x18019ed0f  lea     r8, [rbp+57h+var_A0]
0x18019ed13  mov     rcx, rbx; Src
0x18019ed16  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18019ed1b  mov     edi, eax
0x18019ed1d  test    eax, eax
0x18019ed1f  jns     short loc_18019ED28
0x18019ed21  mov     ecx, eax
0x18019ed23  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019ed28  mov     r14, [rbp+57h+var_A0]
0x18019ed2c  mov     ecx, edi
0x18019ed2e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019ed33  test    edi, edi
0x18019ed35  js      loc_18019EF50
0x18019ed3b  mov     rcx, [rsi]
0x18019ed3e  test    rcx, rcx
0x18019ed41  jz      short loc_18019ED57
0x18019ed43  mov     r9, r14
0x18019ed46  lea     r8, aDeploymentsess_4; "DeploymentSessionWrapper:         File "...
0x18019ed4d  mov     edx, 2
0x18019ed52  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019ed57  mov     rcx, [rbp+57h+var_78]
0x18019ed5b  test    rcx, rcx
0x18019ed5e  jz      short loc_18019ED74
0x18019ed60  mov     rax, [rcx]
0x18019ed63  mov     rax, [rax+10h]
0x18019ed67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ed6c  mov     [rbp+57h+var_78], 0
0x18019ed74  mov     rcx, [rbp+57h+var_88]
0x18019ed78  lea     rdx, [rbp+57h+var_78]
0x18019ed7c  mov     rax, [rcx]
0x18019ed7f  mov     rax, [rax+30h]
0x18019ed83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ed88  mov     edi, eax
0x18019ed8a  test    eax, eax
0x18019ed8c  js      loc_18019EF20
0x18019ed92  mov     rcx, [rbp+57h+var_78]
0x18019ed96  lea     rdx, [rbp+57h+var_80]
0x18019ed9a  mov     rax, [rcx]
0x18019ed9d  mov     rax, [rax+18h]
0x18019eda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eda6  mov     edi, eax
0x18019eda8  test    eax, eax
0x18019edaa  js      loc_18019EEF0
0x18019edb0  mov     rcx, [rsi]
0x18019edb3  test    rcx, rcx
  ... truncated ...
```
