# StructuredQuery1::QueryParser::WritePropertyTextAndAfter(wchar_t const *,IRichChunk *,RESTATEMENT_OPTIONS,bool *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x18002e688`
- end: `0x18002e9e6`
- name: `?WritePropertyTextAndAfter@QueryParser@StructuredQuery1@@AEAAJPEB_WPEAUIRichChunk@@W4RESTATEMENT_OPTIONS@@PEA_NPEA_W_KPEAPEA_WPEA_K@Z`
- size: `862`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ce3c`
- `0x18002d5f4`

## callees

- `0x180010700`
- `0x18002e5c0`
- `0x18002e688`
- `0x18002f5a8`
- `0x180059be8`
- `0x18007a9bc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e7b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e7b7`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::WritePropertyTextAndAfter(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        char a4,
        char *a5,
        wchar_t *a6,
        wchar_t *a7,
        wchar_t **a8,
        unsigned __int64 *a9)
{
  unsigned __int64 v9; // rbx
  wchar_t *v11; // r14
  __int64 v12; // r13
  char v13; // si
  signed int v14; // edi
  void *v15; // r9
  __int64 v16; // r10
  const wchar_t *v17; // r11
  bool v18; // r15
  __int64 (__fastcall *v19)(__int64, _QWORD, _QWORD, LPVOID *, PROPVARIANT *); // rax
  void *v20; // rdx
  unsigned __int64 v21; // rcx
  signed int v22; // eax
  unsigned __int64 v23; // rax
  const struct SemanticsUM::Relationship *RelationByName; // rax
  bool v25; // zf
  __int64 v26; // r8
  LPVOID v27; // r13
  __int64 v28; // rax
  signed int v29; // eax
  __int64 v30; // rdx
  wchar_t **v31; // r9
  __int64 v32; // r8
  wchar_t *v33; // rcx
  unsigned __int64 v34; // rdx
  signed int v35; // eax
  unsigned __int64 v36; // rax
  const wchar_t *v37; // rcx
  unsigned __int64 v38; // rdx
  signed int v39; // eax
  unsigned __int64 v40; // rax
  unsigned int v42; // [rsp+28h] [rbp-38h]
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v44; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v46; // [rsp+50h] [rbp-10h]

  v9 = (unsigned __int64)a7;
  v11 = a6;
  v12 = a1;
  v13 = 0;
  v14 = StructuredQuery1::NullTerminateOutputBuffer((StructuredQuery1 *)a6, a7, a3);
  if ( v14 >= 0 )
  {
    v18 = *(_DWORD *)(v12 + 80) != 2;
    if ( v16 )
    {
      pv = v15;
      v46 = 0;
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *, PROPVARIANT *))(*(_QWORD *)v16 + 24LL);
      *(_OWORD *)pvar = 0;
      v14 = v19(v16, 0, 0, &pv, pvar);
      if ( v14 < 0 )
        goto LABEL_51;
      if ( LOWORD(pvar[0]) == 3 )
        v18 = ((__int64)pvar[1] & 0x20) != 0;
      v20 = pv;
      v21 = v9;
      if ( v11 )
      {
        v22 = StringCchCopyExW(v11, v9, (const wchar_t *)pv, &a6, (unsigned __int64 *)&a7, v42);
        v20 = pv;
        v14 = v22;
        v9 = (unsigned __int64)a7;
        v11 = a6;
      }
      else
      {
        v11 = 0;
        a6 = 0;
        v23 = -1;
        do
          ++v23;
        while ( *((_WORD *)pv + v23) );
        if ( v9 < v23 )
          v9 = -1;
        else
          v9 -= v23;
        a7 = (wchar_t *)v9;
        v14 = v21 < v23 ? 0x80070216 : 0;
      }
      v13 = 1;
      CoTaskMemFree(v20);
      PropVariantClear(pvar);
    }
    else
    {
      if ( !v17 )
        goto LABEL_51;
      RelationByName = SemanticsUM::Entity::FindRelationByName(
                         *(SemanticsUM::Entity **)(*(_QWORD *)(*(_QWORD *)(v12 + 104) + 8LL) + 200LL),
                         v17);
      if ( !RelationByName )
        goto LABEL_51;
      v25 = *(_DWORD *)(v12 + 80) == 2;
      v44 = 0;
      v14 = StructuredQuery1::Relationship::CreateInstance(
              RelationByName,
              v25,
              &GUID_2769280b_5108_498c_9c7f_a51239b63147,
              &v44);
      if ( v14 < 0 )
        goto LABEL_51;
      v27 = v44;
      pv = 0;
      v28 = *(_QWORD *)v44;
      if ( (a4 & 1) != 0 )
        v29 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, __int64, _QWORD))(v28 + 24))(v44, &pv, v26, 0);
      else
        v29 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, __int64, _QWORD))(v28 + 56))(v44, &pv, v26, 0);
      v32 = 0;
      v14 = v29;
      if ( !v29 )
      {
        v33 = (wchar_t *)pv;
        if ( (a4 & 2) == 0
          || (v44 = 0,
              v14 = StructuredQuery1::CoAllocStringLowercased((LPCWSTR)pv, 0x400u, (LPWSTR *)&v44, v31),
              CoTaskMemFree(pv),
              v33 = (wchar_t *)v44,
              pv = v44,
              v14 >= 0) )
        {
          v34 = v9;
          if ( v11 )
          {
            v35 = StringCchCopyExW(v11, v9, v33, &a6, (unsigned __int64 *)&a7, v42);
            v33 = (wchar_t *)pv;
            v14 = v35;
            v9 = (unsigned __int64)a7;
            v11 = a6;
          }
          else
          {
            v11 = 0;
            a6 = 0;
            v36 = -1;
            do
              ++v36;
            while ( v33[v36] );
            if ( v9 < v36 )
              v9 = -1;
            else
              v9 -= v36;
            a7 = (wchar_t *)v9;
            v14 = v34 < v36 ? 0x80070216 : 0;
          }
          v13 = 1;
        }
        CoTaskMemFree(v33);
      }
      (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v27 + 16LL))(v27, v30, v32);
      v12 = a1;
    }
    if ( v14 >= 0 && v13 )
    {
      if ( v18 )
      {
        if ( *(_WORD *)(v12 + 56) == 1041 || *(_WORD *)(v12 + 56) == 2052 )
          v37 = (const wchar_t *)&dword_1800A079C;
        else
          v37 = L":";
      }
      else
      {
        v37 = L" ";
      }
      v38 = v9;
      if ( v11 )
      {
        v39 = StringCchCopyExW(v11, v9, v37, &a6, (unsigned __int64 *)&a7, v42);
        v9 = (unsigned __int64)a7;
        v14 = v39;
        v11 = a6;
      }
      else
      {
        v11 = 0;
        v40 = -1;
        do
          ++v40;
        while ( v37[v40] );
        if ( v9 < v40 )
          v9 = -1;
        else
          v9 -= v40;
        v14 = v38 < v40 ? 0x80070216 : 0;
      }
    }
  }
LABEL_51:
  if ( a5 )
    *a5 = v13;
  if ( a8 )
    *a8 = v11;
  if ( a9 )
    *a9 = v9;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002e688  mov     [rsp-38h+arg_8], rbx
0x18002e68d  mov     [rsp-38h+arg_18], r9d
0x18002e692  mov     [rsp-38h+arg_0], rcx
0x18002e697  push    rbp
0x18002e698  push    rsi
0x18002e699  push    rdi
0x18002e69a  push    r12
0x18002e69c  push    r13
0x18002e69e  push    r14
0x18002e6a0  push    r15
0x18002e6a2  mov     rbp, rsp
0x18002e6a5  sub     rsp, 60h
0x18002e6a9  mov     rbx, [rbp+arg_30]
0x18002e6ad  mov     r12d, r9d
0x18002e6b0  mov     r14, [rbp+arg_28]
0x18002e6b4  xor     r9d, r9d
0x18002e6b7  mov     r11, rdx
0x18002e6ba  mov     r13, rcx
0x18002e6bd  mov     rdx, rbx; wchar_t *
0x18002e6c0  mov     rcx, r14; this
0x18002e6c3  mov     sil, r9b
0x18002e6c6  mov     r10, r8
0x18002e6c9  call    ?NullTerminateOutputBuffer@StructuredQuery1@@YAJPEA_W_K@Z; StructuredQuery1::NullTerminateOutputBuffer(wchar_t *,unsigned __int64)
0x18002e6ce  mov     edi, eax
0x18002e6d0  test    eax, eax
0x18002e6d2  js      loc_18002E9A5
0x18002e6d8  cmp     dword ptr [r13+50h], 2
0x18002e6dd  setnz   r15b
0x18002e6e1  test    r10, r10
0x18002e6e4  jz      loc_18002E7C2
0x18002e6ea  xor     eax, eax
0x18002e6ec  mov     [rbp+pv], r9
0x18002e6f0  mov     [rbp+var_10], rax
0x18002e6f4  lea     rcx, [rbp+pvar]
0x18002e6f8  mov     rax, [r10]
0x18002e6fb  lea     r9, [rbp+pv]
0x18002e6ff  xorps   xmm0, xmm0
0x18002e702  mov     [rsp+60h+var_40], rcx
0x18002e707  xor     r8d, r8d
0x18002e70a  xor     edx, edx
0x18002e70c  mov     rcx, r10
0x18002e70f  mov     rax, [rax+18h]
0x18002e713  movups  xmmword ptr [rbp+pvar], xmm0
0x18002e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e71c  xor     r9d, r9d
0x18002e71f  mov     edi, eax
0x18002e721  test    eax, eax
0x18002e723  js      loc_18002E9A5
0x18002e729  cmp     word ptr [rbp+pvar], 3
0x18002e72e  jnz     short loc_18002E73C
0x18002e730  mov     r15b, byte ptr [rbp+pvar+8]
0x18002e734  shr     r15b, 5
0x18002e738  and     r15b, 1
0x18002e73c  mov     rdx, [rbp+pv]
0x18002e740  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002e744  mov     rcx, rbx
0x18002e747  test    r14, r14
0x18002e74a  jz      short loc_18002E777
0x18002e74c  lea     rax, [rbp+arg_30]
0x18002e750  mov     r8, rdx; wchar_t *
0x18002e753  mov     rdx, rbx; unsigned __int64
0x18002e756  mov     [rsp+60h+var_40], rax; unsigned __int64 *
0x18002e75b  lea     r9, [rbp+arg_28]; wchar_t **
0x18002e75f  mov     rcx, r14; wchar_t *
0x18002e762  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18002e767  mov     rdx, [rbp+pv]
0x18002e76b  mov     edi, eax
0x18002e76d  mov     rbx, [rbp+arg_30]
0x18002e771  mov     r14, [rbp+arg_28]
0x18002e775  jmp     short loc_18002E7A7
0x18002e777  mov     r14, r9
0x18002e77a  mov     [rbp+arg_28], r9
0x18002e77e  mov     rax, r12
0x18002e781  inc     rax
0x18002e784  cmp     [rdx+rax*2], r9w
0x18002e789  jnz     short loc_18002E781
0x18002e78b  cmp     rcx, rax
0x18002e78e  jb      short loc_18002E795
0x18002e790  sub     rbx, rax
0x18002e793  jmp     short loc_18002E798
0x18002e795  mov     rbx, r12
0x18002e798  cmp     rcx, rax
0x18002e79b  mov     [rbp+arg_30], rbx
0x18002e79f  sbb     edi, edi
0x18002e7a1  and     edi, 80070216h
0x18002e7a7  mov     rcx, rdx; pv
0x18002e7aa  mov     sil, 1
0x18002e7ad  call    cs:__imp_CoTaskMemFree
0x18002e7b3  lea     rcx, [rbp+pvar]; pvar
0x18002e7b7  call    cs:__imp_PropVariantClear
0x18002e7bd  jmp     loc_18002E907
0x18002e7c2  test    r11, r11
0x18002e7c5  jz      loc_18002E9A5
0x18002e7cb  mov     rax, [r13+68h]
0x18002e7cf  mov     rdx, r11; wchar_t *
0x18002e7d2  mov     rcx, [rax+8]
0x18002e7d6  mov     rcx, [rcx+0C8h]; this
0x18002e7dd  call    ?FindRelationByName@Entity@SemanticsUM@@QEBAPEBVRelationship@2@PEB_W@Z; SemanticsUM::Entity::FindRelationByName(wchar_t const *)
0x18002e7e2  xor     r9d, r9d
0x18002e7e5  test    rax, rax
0x18002e7e8  jz      loc_18002E9A5
0x18002e7ee  cmp     dword ptr [r13+50h], 2
0x18002e7f3  lea     r8, _GUID_2769280b_5108_498c_9c7f_a51239b63147; struct _GUID *
0x18002e7fa  mov     [rbp+var_28], r9
0x18002e7fe  mov     rcx, rax; struct SemanticsUM::Relationship *
0x18002e801  setz    dl; bool
0x18002e804  lea     r9, [rbp+var_28]; void **
0x18002e808  call    ?CreateInstance@Relationship@StructuredQuery1@@SAJPEBV1SemanticsUM@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Relationship::CreateInstance(SemanticsUM::Relationship const *,bool,_GUID const &,void * *)
0x18002e80d  xor     r9d, r9d
0x18002e810  mov     edi, eax
0x18002e812  test    eax, eax
0x18002e814  js      loc_18002E9A5
0x18002e81a  mov     r13, [rbp+var_28]
0x18002e81e  lea     rdx, [rbp+pv]
0x18002e822  mov     [rbp+pv], r9
0x18002e826  mov     rcx, r13
0x18002e829  mov     rax, [r13+0]
0x18002e82d  test    r12b, 1
0x18002e831  jz      short loc_18002E839
0x18002e833  mov     rax, [rax+18h]
0x18002e837  jmp     short loc_18002E83D
0x18002e839  mov     rax, [rax+38h]
0x18002e83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e842  xor     r8d, r8d
0x18002e845  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002e849  mov     edi, eax
0x18002e84b  test    eax, eax
0x18002e84d  jnz     loc_18002E8F3
0x18002e853  test    byte ptr [rbp+arg_18], 2
0x18002e857  mov     rcx, [rbp+pv]; lpSrcStr
0x18002e85b  jz      short loc_18002E88A
0x18002e85d  mov     [rbp+var_28], r8
0x18002e861  mov     edx, 400h; Locale
0x18002e866  lea     r8, [rbp+var_28]; unsigned int
0x18002e86a  call    ?CoAllocStringLowercased@StructuredQuery1@@YAJPEB_WKPEAPEA_W@Z; StructuredQuery1::CoAllocStringLowercased(wchar_t const *,ulong,wchar_t * *)
0x18002e86f  mov     rcx, [rbp+pv]; pv
0x18002e873  mov     edi, eax
0x18002e875  call    cs:__imp_CoTaskMemFree
0x18002e87b  mov     rcx, [rbp+var_28]; pv
0x18002e87f  xor     r8d, r8d
0x18002e882  mov     [rbp+pv], rcx
0x18002e886  test    edi, edi
0x18002e888  js      short loc_18002E8ED
0x18002e88a  mov     rdx, rbx; unsigned __int64
0x18002e88d  test    r14, r14
0x18002e890  jz      short loc_18002E8BA
0x18002e892  lea     rax, [rbp+arg_30]
0x18002e896  mov     r8, rcx; wchar_t *
0x18002e899  mov     rcx, r14; wchar_t *
0x18002e89c  mov     [rsp+60h+var_40], rax; unsigned __int64 *
0x18002e8a1  lea     r9, [rbp+arg_28]; wchar_t **
0x18002e8a5  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18002e8aa  mov     rcx, [rbp+pv]
0x18002e8ae  mov     edi, eax
0x18002e8b0  mov     rbx, [rbp+arg_30]
0x18002e8b4  mov     r14, [rbp+arg_28]
0x18002e8b8  jmp     short loc_18002E8EA
0x18002e8ba  mov     r14, r8
0x18002e8bd  mov     [rbp+arg_28], r8
0x18002e8c1  mov     rax, r12
0x18002e8c4  inc     rax
0x18002e8c7  cmp     [rcx+rax*2], r8w
0x18002e8cc  jnz     short loc_18002E8C4
0x18002e8ce  cmp     rdx, rax
0x18002e8d1  jb      short loc_18002E8D8
0x18002e8d3  sub     rbx, rax
0x18002e8d6  jmp     short loc_18002E8DB
0x18002e8d8  mov     rbx, r12
0x18002e8db  cmp     rdx, rax
0x18002e8de  mov     [rbp+arg_30], rbx
0x18002e8e2  sbb     edi, edi
0x18002e8e4  and     edi, 80070216h
0x18002e8ea  mov     sil, 1
0x18002e8ed  call    cs:__imp_CoTaskMemFree
0x18002e8f3  mov     rax, [r13+0]
0x18002e8f7  mov     rcx, r13
0x18002e8fa  mov     rax, [rax+10h]
0x18002e8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e903  mov     r13, [rbp+arg_0]
0x18002e907  xor     r9d, r9d
0x18002e90a  test    edi, edi
0x18002e90c  js      loc_18002E9A5
0x18002e912  test    sil, sil
0x18002e915  jz      loc_18002E9A5
0x18002e91b  test    r15b, r15b
0x18002e91e  jz      short loc_18002E94A
0x18002e920  mov     eax, 411h
0x18002e925  cmp     [r13+38h], ax
0x18002e92a  jz      short loc_18002E941
0x18002e92c  mov     eax, 804h
0x18002e931  cmp     [r13+38h], ax
0x18002e936  jz      short loc_18002E941
0x18002e938  lea     rcx, asc_18009A9AC; ":"
0x18002e93f  jmp     short loc_18002E951
0x18002e941  lea     rcx, dword_1800A079C
0x18002e948  jmp     short loc_18002E951
0x18002e94a  lea     rcx, pszTrimChars; " "
0x18002e951  mov     rdx, rbx; unsigned __int64
0x18002e954  test    r14, r14
0x18002e957  jz      short loc_18002E97D
0x18002e959  lea     rax, [rbp+arg_30]
0x18002e95d  mov     r8, rcx; wchar_t *
0x18002e960  mov     rcx, r14; wchar_t *
0x18002e963  mov     [rsp+60h+var_40], rax; unsigned __int64 *
0x18002e968  lea     r9, [rbp+arg_28]; wchar_t **
0x18002e96c  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18002e971  mov     rbx, [rbp+arg_30]
0x18002e975  mov     edi, eax
0x18002e977  mov     r14, [rbp+arg_28]
0x18002e97b  jmp     short loc_18002E9A5
0x18002e97d  mov     r14, r9
0x18002e980  mov     rax, r12
0x18002e983  inc     rax
0x18002e986  cmp     [rcx+rax*2], r9w
0x18002e98b  jnz     short loc_18002E983
0x18002e98d  cmp     rdx, rax
0x18002e990  jb      short loc_18002E997
0x18002e992  sub     rbx, rax
0x18002e995  jmp     short loc_18002E99A
0x18002e997  mov     rbx, r12
0x18002e99a  cmp     rdx, rax
0x18002e99d  sbb     edi, edi
0x18002e99f  and     edi, 80070216h
0x18002e9a5  mov     rax, [rbp+arg_20]
0x18002e9a9  test    rax, rax
0x18002e9ac  jz      short loc_18002E9B1
0x18002e9ae  mov     [rax], sil
0x18002e9b1  mov     rax, [rbp+arg_38]
0x18002e9b5  test    rax, rax
0x18002e9b8  jz      short loc_18002E9BD
0x18002e9ba  mov     [rax], r14
0x18002e9bd  mov     rax, [rbp+arg_40]
0x18002e9c4  test    rax, rax
0x18002e9c7  jz      short loc_18002E9CC
0x18002e9c9  mov     [rax], rbx
0x18002e9cc  mov     rbx, [rsp+60h+arg_8]
0x18002e9d4  mov     eax, edi
0x18002e9d6  add     rsp, 60h
0x18002e9da  pop     r15
0x18002e9dc  pop     r14
0x18002e9de  pop     r13
0x18002e9e0  pop     r12
0x18002e9e2  pop     rdi
0x18002e9e3  pop     rsi
0x18002e9e4  pop     rbp
0x18002e9e5  retn
```
