# CClassContainer::ChangePackageSourceList(ushort const *,uint,ushort const * *)

- ea: `0x18001f570`
- end: `0x18001f7ed`
- name: `?ChangePackageSourceList@CClassContainer@@UEAAJPEBGIPEAPEBG@Z`
- size: `637`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x18001f570`
- `0x180023448`
- `0x18002350c`
- `0x18002435c`
- `0x180024458`
- `0x180026f3c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f64b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f6a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f64b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f6a2`
- `adsldpc!ADSICloseDSObject` at `0x18001f78d`
- `adsldpc!ADSICloseDSObject` at `0x18001f78d`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f73d`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f73d`

## string_xrefs

- `0x18001f702`: `lastUpdateSequence`
- `0x18001f715`: `msiFileList`

## pseudocode

```c
__int64 __fastcall CClassContainer::ChangePackageSourceList(
        void **this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 **a4)
{
  unsigned int v4; // edi
  __int64 v5; // rsi
  int v8; // ecx
  unsigned int v9; // r13d
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // ebx
  unsigned int v14; // eax
  _QWORD *v15; // r14
  unsigned int v16; // edx
  int v17; // ecx
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  __int64 i; // rbx
  int v21; // [rsp+30h] [rbp-79h] BYREF
  void *v22; // [rsp+38h] [rbp-71h] BYREF
  HLOCAL v23; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-61h] BYREF
  struct _ads_attr_info v25; // [rsp+50h] [rbp-59h] BYREF
  struct _ads_attr_info v26; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 v27[20]; // [rsp+90h] [rbp-19h] BYREF

  v4 = 0;
  v5 = a3;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  if ( !a2 || !a4 )
    return 2147942487LL;
  v8 = 0;
  if ( a3 )
  {
    while ( a4[v8] )
    {
      if ( ++v8 >= a3 )
        goto LABEL_6;
    }
    return 2147942487LL;
  }
LABEL_6:
  v9 = 0;
  v10 = (*((__int64 (__fastcall **)(void **, const unsigned __int16 *, HLOCAL *))*this + 19))(this, a2, &v23);
  v12 = v10;
  if ( v10 >= 0 )
  {
    if ( v10 )
      return 2147746153LL;
    if ( (gCsOptions & 1) != 0 )
      v14 = GetADsOpenObjectFlags() | 0x21;
    else
      v14 = 101;
    v12 = DSServerOpenDSObject((struct CServerContext *)(this + 74), (const unsigned __int16 *)v23, v14, &v22);
    if ( v12 >= 0 )
    {
      v15 = LocalAlloc(0, 8 * v5);
      if ( v15 )
      {
        if ( (_DWORD)v5 )
        {
          while ( 1 )
          {
            v16 = v5;
            v17 = 0;
            do
            {
              ++v17;
              v16 /= 0xAu;
            }
            while ( v16 );
            v18 = -1;
            do
              ++v18;
            while ( a4[v4][v18] );
            v24 = (unsigned __int16 *)(unsigned int)(v17 + 3 + v18);
            v19 = (unsigned __int16 *)LocalAlloc(0, 2LL * (_QWORD)v24);
            v15[v4] = v19;
            if ( !v19 )
              break;
            v12 = StringCchPrintfW(v19, (unsigned __int64)v24, L"%d:%s", v4, a4[v4]);
            if ( v12 < 0 )
              goto LABEL_28;
            if ( ++v4 >= (unsigned int)v5 )
              goto LABEL_23;
          }
          for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
            LocalFree((HLOCAL)v15[i]);
          LocalFree(v15);
          v12 = -2147024882;
LABEL_28:
          v4 = 0;
        }
        else
        {
LABEL_23:
          GetCurrentUsn(v27);
          v24 = v27;
          PackStrArrToAttr(&v25, L"lastUpdateSequence", &v24, 1u);
          PackStrArrToAttr(&v26, L"msiFileList", (unsigned __int16 **)v15, v5);
          v9 = 2;
          v4 = 0;
          v12 = ADSISetObjectAttributes(v22, &v25, 2, &v21);
          if ( v12 >= 0 )
            UpdateStoreUsn(this[69], v27);
        }
      }
      else
      {
        v12 = -2147024882;
      }
    }
  }
  if ( v22 )
    ADSICloseDSObject(v22, v11);
  if ( v9 )
  {
    do
      LocalFree(*((HLOCAL *)&v25.pADsValues + 4 * v4++));
    while ( v4 < v9 );
  }
  if ( v23 )
    LocalFree(v23);
  return RemapErrorCode(v12, v11);
}

```

## disassembly

```asm
0x18001f570  push    rbp
0x18001f572  push    rbx
0x18001f573  push    rsi
0x18001f574  push    rdi
0x18001f575  push    r12
0x18001f577  push    r13
0x18001f579  push    r14
0x18001f57b  push    r15
0x18001f57d  lea     rbp, [rsp-1Fh]
0x18001f582  sub     rsp, 0C8h
0x18001f589  mov     rax, cs:__security_cookie
0x18001f590  xor     rax, rsp
0x18001f593  mov     [rbp+57h+var_48], rax
0x18001f597  xor     edi, edi
0x18001f599  mov     esi, r8d
0x18001f59c  mov     [rbp+57h+var_C8], rdi
0x18001f5a0  mov     r15, r9
0x18001f5a3  mov     [rbp+57h+var_C0], rdi
0x18001f5a7  mov     r12, rcx
0x18001f5aa  mov     [rbp+57h+var_D0], edi
0x18001f5ad  test    rdx, rdx
0x18001f5b0  jz      loc_18001F7C8
0x18001f5b6  test    r9, r9
0x18001f5b9  jz      loc_18001F7C8
0x18001f5bf  mov     ecx, edi
0x18001f5c1  test    r8d, r8d
0x18001f5c4  jz      short loc_18001F5D8
0x18001f5c6  mov     eax, ecx
0x18001f5c8  cmp     [r9+rax*8], rdi
0x18001f5cc  jz      loc_18001F7C8
0x18001f5d2  inc     ecx
0x18001f5d4  cmp     ecx, esi
0x18001f5d6  jb      short loc_18001F5C6
0x18001f5d8  mov     rax, [r12]
0x18001f5dc  lea     r8, [rbp+57h+var_C0]
0x18001f5e0  mov     rcx, r12
0x18001f5e3  mov     r13d, edi
0x18001f5e6  mov     rax, [rax+98h]
0x18001f5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5f2  mov     ebx, eax
0x18001f5f4  test    eax, eax
0x18001f5f6  js      loc_18001F784
0x18001f5fc  jz      short loc_18001F608
0x18001f5fe  mov     eax, 80040169h
0x18001f603  jmp     loc_18001F7CD
0x18001f608  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001f60f  jz      short loc_18001F61B
0x18001f611  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001f616  or      eax, 21h
0x18001f619  jmp     short loc_18001F620
0x18001f61b  mov     eax, 65h ; 'e'
0x18001f620  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x18001f624  lea     rcx, [r12+250h]; struct CServerContext *
0x18001f62c  lea     r9, [rbp+57h+var_C8]; void **
0x18001f630  mov     r8d, eax; int
0x18001f633  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001f638  mov     ebx, eax
0x18001f63a  test    eax, eax
0x18001f63c  js      loc_18001F784
0x18001f642  mov     rdx, rsi
0x18001f645  xor     ecx, ecx; uFlags
0x18001f647  shl     rdx, 3; uBytes
0x18001f64b  call    cs:__imp_LocalAlloc
0x18001f651  mov     r14, rax
0x18001f654  test    rax, rax
0x18001f657  jnz     short loc_18001F663
0x18001f659  mov     ebx, 8007000Eh
0x18001f65e  jmp     loc_18001F784
0x18001f663  xor     r8d, r8d
0x18001f666  test    esi, esi
0x18001f668  jz      short loc_18001F6E7
0x18001f66a  mov     edx, esi
0x18001f66c  mov     ecx, r8d
0x18001f66f  mov     eax, 0CCCCCCCDh
0x18001f674  inc     ecx
0x18001f676  mul     edx
0x18001f678  shr     edx, 3
0x18001f67b  test    edx, edx
0x18001f67d  jnz     short loc_18001F66F
0x18001f67f  mov     ebx, edi
0x18001f681  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f685  mov     rdx, [r15+rbx*8]
0x18001f689  inc     rax
0x18001f68c  cmp     [rdx+rax*2], r8w
0x18001f691  jnz     short loc_18001F689
0x18001f693  add     ecx, 3
0x18001f696  add     eax, ecx
0x18001f698  xor     ecx, ecx; uFlags
0x18001f69a  mov     [rbp+57h+var_B8], rax
0x18001f69e  lea     rdx, [rax+rax]; uBytes
0x18001f6a2  call    cs:__imp_LocalAlloc
0x18001f6a8  mov     [r14+rbx*8], rax
0x18001f6ac  test    rax, rax
0x18001f6af  jz      loc_18001F75E
0x18001f6b5  mov     rcx, [r15+rbx*8]
0x18001f6b9  lea     r8, aDS; "%d:%s"
0x18001f6c0  mov     rdx, [rbp+57h+var_B8]; unsigned __int64
0x18001f6c4  mov     r9d, edi
0x18001f6c7  mov     [rsp+100h+var_E0], rcx
0x18001f6cc  mov     rcx, rax; unsigned __int16 *
0x18001f6cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f6d4  xor     r8d, r8d
0x18001f6d7  mov     ebx, eax
0x18001f6d9  test    eax, eax
0x18001f6db  js      loc_18001F782
0x18001f6e1  inc     edi
0x18001f6e3  cmp     edi, esi
0x18001f6e5  jb      short loc_18001F66A
0x18001f6e7  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18001f6eb  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x18001f6f0  lea     rax, [rbp+57h+var_70]
0x18001f6f4  mov     r9d, 1; unsigned int
0x18001f6fa  lea     r8, [rbp+57h+var_B8]; unsigned __int16 **
0x18001f6fe  mov     [rbp+57h+var_B8], rax
0x18001f702  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x18001f709  lea     rcx, [rbp+57h+var_B0]; struct _ads_attr_info *
0x18001f70d  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f712  mov     r9d, esi; unsigned int
0x18001f715  lea     rdx, aMsifilelist; "msiFileList"
0x18001f71c  mov     r8, r14; unsigned __int16 **
0x18001f71f  lea     rcx, [rbp+57h+var_90]; struct _ads_attr_info *
0x18001f723  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f728  mov     rcx, [rbp+57h+var_C8]
0x18001f72c  lea     r9, [rbp+57h+var_D0]
0x18001f730  mov     r13d, 2
0x18001f736  lea     rdx, [rbp+57h+var_B0]
0x18001f73a  mov     r8d, r13d
0x18001f73d  call    cs:__imp_ADSISetObjectAttributes
0x18001f743  xor     edi, edi
0x18001f745  mov     ebx, eax
0x18001f747  test    eax, eax
0x18001f749  js      short loc_18001F784
0x18001f74b  mov     rcx, [r12+228h]; void *
0x18001f753  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18001f757  call    ?UpdateStoreUsn@@YAJPEAXPEBG@Z; UpdateStoreUsn(void *,ushort const *)
0x18001f75c  jmp     short loc_18001F784
0x18001f75e  xor     ebx, ebx
0x18001f760  test    edi, edi
0x18001f762  jz      short loc_18001F774
0x18001f764  mov     rcx, [r14+rbx*8]; hMem
0x18001f768  call    cs:__imp_LocalFree
0x18001f76e  inc     ebx
0x18001f770  cmp     ebx, edi
0x18001f772  jb      short loc_18001F764
0x18001f774  mov     rcx, r14; hMem
0x18001f777  call    cs:__imp_LocalFree
0x18001f77d  mov     ebx, 8007000Eh
0x18001f782  xor     edi, edi
0x18001f784  mov     rcx, [rbp+57h+var_C8]
0x18001f788  test    rcx, rcx
0x18001f78b  jz      short loc_18001F793
0x18001f78d  call    cs:__imp_ADSICloseDSObject
0x18001f793  test    r13d, r13d
0x18001f796  jz      short loc_18001F7B0
0x18001f798  mov     ecx, edi
0x18001f79a  shl     rcx, 5
0x18001f79e  mov     rcx, [rbp+rcx+57h+var_B0.pADsValues]; hMem
0x18001f7a3  call    cs:__imp_LocalFree
0x18001f7a9  inc     edi
0x18001f7ab  cmp     edi, r13d
0x18001f7ae  jb      short loc_18001F798
0x18001f7b0  mov     rcx, [rbp+57h+var_C0]; hMem
0x18001f7b4  test    rcx, rcx
0x18001f7b7  jz      short loc_18001F7BF
0x18001f7b9  call    cs:__imp_LocalFree
0x18001f7bf  mov     ecx, ebx; int
0x18001f7c1  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001f7c6  jmp     short loc_18001F7CD
0x18001f7c8  mov     eax, 80070057h
0x18001f7cd  mov     rcx, [rbp+57h+var_48]
0x18001f7d1  xor     rcx, rsp; StackCookie
0x18001f7d4  call    __security_check_cookie
0x18001f7d9  add     rsp, 0C8h
0x18001f7e0  pop     r15
0x18001f7e2  pop     r14
0x18001f7e4  pop     r13
0x18001f7e6  pop     r12
0x18001f7e8  pop     rdi
0x18001f7e9  pop     rsi
0x18001f7ea  pop     rbx
0x18001f7eb  pop     rbp
0x18001f7ec  retn
```
