# CTravelEntry::_VerifySchemeAndDomainAreSame(IUnknown *,CTravelEntry *,CTravelEntry *,int,int *,IUri * *)

- ea: `0x1810456f0`
- end: `0x181045aa7`
- name: `?_VerifySchemeAndDomainAreSame@CTravelEntry@@IEAAJPEAUIUnknown@@PEAV1@1HPEAHPEAPEAUIUri@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(CTravelEntry *__hidden this, struct IUnknown *, struct CTravelEntry *, struct CTravelEntry *, int, int *, struct IUri **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x181045290`

## callees

- `0x1802e5024`
- `0x1810456f0`
- `0x1810643ac`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1810459d8`
- `KERNEL32!GlobalFree` at `0x1810459d8`
- `iertutil!CreateUri` at `0x181045962`
- `iertutil!CreateUri` at `0x181045962`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1810459c9`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1810459c9`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1810458d7`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1810458d7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18104599f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810459aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810459b4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18104599f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810459aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810459b4`
- `SHELL32!__imp_ILFree` at `0x181045994`
- `SHELL32!__imp_ILFree` at `0x181045994`
- `urlmon!CoInternetCombineUrlEx` at `0x181045781`
- `urlmon!CoInternetCombineUrlEx` at `0x1810457c2`
- `urlmon!CoInternetCombineUrlEx` at `0x181045987`
- `urlmon!CoInternetCombineUrlEx` at `0x181045781`
- `urlmon!CoInternetCombineUrlEx` at `0x1810457c2`
- `urlmon!CoInternetCombineUrlEx` at `0x181045987`

## pseudocode

```c
__int64 __fastcall CTravelEntry::_VerifySchemeAndDomainAreSame(
        CTravelEntry *this,
        struct IUnknown *a2,
        struct CTravelEntry *a3,
        IUri **a4,
        int a5,
        int *a6,
        struct IUri **a7)
{
  IUri *v10; // rcx
  HRESULT v11; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  __int64 v15; // [rsp+38h] [rbp-D0h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-C8h] BYREF
  HGLOBAL phglobal; // [rsp+48h] [rbp-C0h] BYREF
  IUri *ppURI; // [rsp+50h] [rbp-B8h] BYREF
  IUri *v19; // [rsp+58h] [rbp-B0h] BYREF
  IUri *ppCombinedUri; // [rsp+60h] [rbp-A8h] BYREF
  IUri *ppCombinedUri_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 pidl_8; // [rsp+78h] [rbp-90h]
  LPVOID pv; // [rsp+88h] [rbp-80h]
  WCHAR pwzURI[2088]; // [rsp+98h] [rbp-70h] BYREF

  *a6 = 0;
  v10 = (IUri *)*((_QWORD *)a3 + 7);
  ppCombinedUri = 0;
  v11 = CoInternetCombineUrlEx(v10, L"/", 0, &ppCombinedUri, 0);
  if ( v11 < 0 )
    return (unsigned int)v11;
  ppURI = 0;
  v19 = 0;
  if ( ((a5 + 1) & 0xFFFFFFFD) != 0 )
  {
    v11 = CoInternetCombineUrlEx(a4[7], L"/", 0, &v19, 0);
LABEL_25:
    if ( v11 >= 0 )
    {
      LODWORD(v15) = 0;
      if ( ((int (__fastcall *)(IUri *, IUri *, __int64 *))ppCombinedUri->lpVtbl->IsEqual)(ppCombinedUri, v19, &v15) >= 0 )
      {
        *a6 = v15;
        *a7 = ppURI;
        ppURI = 0;
      }
    }
    goto LABEL_28;
  }
  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
          a2,
          &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
          &v15);
  if ( v11 >= 0 )
  {
    v13 = *((unsigned int *)this + 18);
    if ( (_DWORD)v13 == -1 )
      goto LABEL_11;
    ppstm = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, LPSTREAM *))(*(_QWORD *)v15 + 24LL))(v15, v13, &ppstm);
    if ( v11 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      v11 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, __int64 *))ppstm)(
              ppstm,
              &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
              &v15);
      if ( v11 >= 0 )
      {
        phglobal = 0;
        v11 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, HGLOBAL *))ppstm)(
                ppstm,
                &GUID_cef3b021_5ab5_465e_9d62_0e97a2e30d3b,
                &phglobal);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(HGLOBAL, __int64))(*(_QWORD *)phglobal + 24LL))(phglobal, 0xFFFFFFFFLL);
          (*(void (__fastcall **)(HGLOBAL))(*(_QWORD *)phglobal + 16LL))(phglobal);
        }
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      if ( v11 >= 0 )
      {
LABEL_11:
        ppstm = 0;
        v11 = CreateStreamOnHGlobal(0, 0, &ppstm);
        if ( v11 >= 0 )
        {
          pv = 0;
          *(_OWORD *)ppCombinedUri_8 = 0;
          pidl_8 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, LPSTREAM, IUri **))(*(_QWORD *)v15 + 32LL))(
                  v15,
                  ppstm,
                  ppCombinedUri_8);
          if ( v11 >= 0 )
          {
            pwzURI[0] = 0;
            if ( ppCombinedUri_8[1] )
            {
              IEGetNameAndFlagsEx((struct _ITEMIDLIST_RELATIVE *)ppCombinedUri_8[1]);
            }
            else if ( (_QWORD)pidl_8 )
            {
              StringCchCopyW(pwzURI, 0x824u, (const unsigned __int16 *)pidl_8);
            }
            v11 = CreateUri(pwzURI, 0x3002B84u, 0, &ppURI);
            if ( v11 >= 0 )
              v11 = CoInternetCombineUrlEx(ppURI, L"/", 0, &v19, 0);
            ILFree((LPITEMIDLIST)ppCombinedUri_8[1]);
            CoTaskMemFree((LPVOID)pidl_8);
            CoTaskMemFree(*((LPVOID *)&pidl_8 + 1));
            CoTaskMemFree(pv);
          }
          phglobal = 0;
          if ( GetHGlobalFromStream(ppstm, &phglobal) >= 0 )
            GlobalFree(phglobal);
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        }
      }
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_25;
  }
LABEL_28:
  ((void (__fastcall *)(IUri *))ppCombinedUri->lpVtbl->Release)(ppCombinedUri);
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  if ( v19 )
    ((void (__fastcall *)(IUri *))v19->lpVtbl->Release)(v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1810456f0  mov     rax, rsp
0x1810456f3  mov     [rax+20h], r9
0x1810456f7  mov     [rax+18h], r8
0x1810456fb  mov     [rax+10h], rdx
0x1810456ff  mov     [rax+8], rcx
0x181045703  push    rbp
0x181045704  push    rbx
0x181045705  push    rsi
0x181045706  push    rdi
0x181045707  push    r12
0x181045709  push    r13
0x18104570b  push    r14
0x18104570d  push    r15
0x18104570f  lea     rbp, [rax-1038h]
0x181045716  mov     eax, 10F8h
0x18104571b  call    _alloca_probe
0x181045720  sub     rsp, rax
0x181045723  mov     rax, cs:__security_cookie
0x18104572a  xor     rax, rsp
0x18104572d  mov     [rbp+1030h+var_50], rax
0x181045734  mov     r15, [rbp+1030h+arg_28]
0x18104573b  lea     r9, [rsp+1130h+ppCombinedUri]; ppCombinedUri
0x181045740  mov     rcx, [rbp+1030h+arg_10]
0x181045747  lea     rdx, asc_181447E48; "/"
0x18104574e  mov     rsi, [rbp+1030h+arg_0]
0x181045755  xor     r13d, r13d
0x181045758  mov     rdi, [rbp+1030h+arg_8]
0x18104575f  xor     r8d, r8d; dwCombineFlags
0x181045762  mov     r14, [rbp+1030h+arg_18]
0x181045769  mov     r12, [rbp+1030h+arg_30]
0x181045770  mov     [r15], r13d
0x181045773  mov     rcx, [rcx+38h]; pBaseUri
0x181045777  mov     [rsp+1130h+ppCombinedUri], r13
0x18104577c  mov     [rsp+20h], r13; dwReserved
0x181045781  call    cs:__imp_CoInternetCombineUrlEx
0x181045787  mov     ebx, eax
0x181045789  test    eax, eax
0x18104578b  js      loc_181045A82
0x181045791  mov     eax, [rbp+1030h+arg_20]
0x181045797  inc     eax
0x181045799  mov     [rsp+1130h+ppURI], r13
0x18104579e  mov     [rsp+1130h+var_10E0], r13
0x1810457a3  test    eax, 0FFFFFFFDh
0x1810457a8  jz      short loc_1810457CF
0x1810457aa  mov     rcx, [r14+38h]; pBaseUri
0x1810457ae  lea     r9, [rsp+1130h+var_10E0]; ppCombinedUri
0x1810457b3  xor     r8d, r8d; dwCombineFlags
0x1810457b6  mov     [rsp+20h], r13; dwReserved
0x1810457bb  lea     rdx, asc_181447E48; "/"
0x1810457c2  call    cs:__imp_CoInternetCombineUrlEx
0x1810457c8  mov     ebx, eax
0x1810457ca  jmp     loc_181045A05
0x1810457cf  mov     rax, [rdi]
0x1810457d2  lea     r8, [rsp+1130h+var_1100]
0x1810457d7  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x1810457de  mov     [rsp+1130h+var_1100], r13
0x1810457e3  mov     rcx, rdi
0x1810457e6  mov     rax, [rax]
0x1810457e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810457ee  mov     ebx, eax
0x1810457f0  test    eax, eax
0x1810457f2  js      loc_181045A45
0x1810457f8  mov     edx, [rsi+48h]
0x1810457fb  or      edi, 0FFFFFFFFh
0x1810457fe  cmp     edx, edi
0x181045800  jz      loc_1810458C9
0x181045806  mov     rcx, [rsp+1130h+var_1100]
0x18104580b  lea     r8, [rsp+1130h+ppstm]
0x181045810  mov     [rsp+1130h+ppstm], r13
0x181045815  mov     rax, [rcx]
0x181045818  mov     rax, [rax+18h]
0x18104581c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045821  mov     ebx, eax
0x181045823  test    eax, eax
0x181045825  js      loc_1810459EF
0x18104582b  mov     rcx, [rsp+1130h+var_1100]
0x181045830  mov     rax, [rcx]
0x181045833  mov     rax, [rax+10h]
0x181045837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104583c  mov     rcx, [rsp+1130h+ppstm]
0x181045841  lea     r8, [rsp+1130h+var_1100]
0x181045846  mov     [rsp+1130h+var_1100], r13
0x18104584b  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x181045852  mov     rax, [rcx]
0x181045855  mov     rax, [rax]
0x181045858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104585d  mov     ebx, eax
0x18104585f  test    eax, eax
0x181045861  js      short loc_1810458B0
0x181045863  mov     rcx, [rsp+1130h+ppstm]
0x181045868  lea     r8, [rsp+1130h+phglobal]
0x18104586d  mov     [rsp+1130h+phglobal], r13
0x181045872  lea     rdx, _GUID_cef3b021_5ab5_465e_9d62_0e97a2e30d3b
0x181045879  mov     rax, [rcx]
0x18104587c  mov     rax, [rax]
0x18104587f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045884  mov     ebx, eax
0x181045886  test    eax, eax
0x181045888  js      short loc_1810458B0
0x18104588a  mov     rcx, [rsp+1130h+phglobal]
0x18104588f  mov     edx, edi
0x181045891  mov     rax, [rcx]
0x181045894  mov     rax, [rax+18h]
0x181045898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104589d  mov     rcx, [rsp+1130h+phglobal]
0x1810458a2  mov     ebx, eax
0x1810458a4  mov     rax, [rcx]
0x1810458a7  mov     rax, [rax+10h]
0x1810458ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810458b0  mov     rcx, [rsp+1130h+ppstm]
0x1810458b5  mov     rax, [rcx]
0x1810458b8  mov     rax, [rax+10h]
0x1810458bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810458c1  test    ebx, ebx
0x1810458c3  js      loc_1810459EF
0x1810458c9  lea     r8, [rsp+1130h+ppstm]; ppstm
0x1810458ce  mov     [rsp+1130h+ppstm], r13
0x1810458d3  xor     edx, edx; fDeleteOnRelease
0x1810458d5  xor     ecx, ecx; hGlobal
0x1810458d7  call    cs:__imp_CreateStreamOnHGlobal
0x1810458dd  mov     ebx, eax
0x1810458df  test    eax, eax
0x1810458e1  js      loc_1810459EF
0x1810458e7  mov     rcx, [rsp+1130h+var_1100]
0x1810458ec  lea     r8, [rsp+1130h+ppCombinedUri+8]
0x1810458f1  mov     rdx, [rsp+1130h+ppstm]
0x1810458f6  xor     eax, eax
0x1810458f8  xorps   xmm0, xmm0
0x1810458fb  mov     [rbp+1030h+pv], rax
0x1810458ff  movups  xmmword ptr [rsp+1130h+ppCombinedUri+8], xmm0
0x181045904  movups  xmmword ptr [rsp+1130h+pidl+8], xmm0
0x181045909  mov     rax, [rcx]
0x18104590c  mov     rax, [rax+20h]
0x181045910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045915  mov     ebx, eax
0x181045917  test    eax, eax
0x181045919  js      loc_1810459BA
0x18104591f  mov     rcx, qword ptr [rsp+1130h+pidl]; struct _ITEMIDLIST_RELATIVE *
0x181045924  mov     [rbp+1030h+pwzURI], r13w
0x181045929  test    rcx, rcx
0x18104592c  jz      short loc_181045939
0x18104592e  lea     r9, [rbp+1030h+pwzURI]
0x181045932  call    IEGetNameAndFlagsEx
0x181045937  jmp     short loc_181045951
0x181045939  mov     r8, qword ptr [rsp+1130h+pidl+8]; unsigned __int16 *
0x18104593e  test    r8, r8
0x181045941  jz      short loc_181045951
0x181045943  mov     edx, 824h; unsigned __int64
0x181045948  lea     rcx, [rbp+1030h+pwzURI]; unsigned __int16 *
0x18104594c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x181045951  lea     r9, [rsp+1130h+ppURI]; ppURI
0x181045956  xor     r8d, r8d; dwReserved
0x181045959  mov     edx, 3002B84h; dwFlags
0x18104595e  lea     rcx, [rbp+1030h+pwzURI]; pwzURI
0x181045962  call    cs:__imp_CreateUri
0x181045968  mov     ebx, eax
0x18104596a  test    eax, eax
0x18104596c  js      short loc_18104598F
0x18104596e  mov     rcx, [rsp+1130h+ppURI]; pBaseUri
0x181045973  lea     r9, [rsp+1130h+var_10E0]; ppCombinedUri
0x181045978  xor     r8d, r8d; dwCombineFlags
0x18104597b  mov     [rsp+20h], r13; dwReserved
0x181045980  lea     rdx, asc_181447E48; "/"
0x181045987  call    cs:__imp_CoInternetCombineUrlEx
0x18104598d  mov     ebx, eax
0x18104598f  mov     rcx, qword ptr [rsp+1130h+pidl]; pidl
0x181045994  call    cs:__imp_ILFree
0x18104599a  mov     rcx, qword ptr [rsp+1130h+pidl+8]; pv
0x18104599f  call    cs:__imp_CoTaskMemFree
0x1810459a5  mov     rcx, qword ptr [rsp+1130h+pidl+10h]; pv
0x1810459aa  call    cs:__imp_CoTaskMemFree
0x1810459b0  mov     rcx, [rbp+1030h+pv]; pv
0x1810459b4  call    cs:__imp_CoTaskMemFree
0x1810459ba  mov     rcx, [rsp+1130h+ppstm]; pstm
0x1810459bf  lea     rdx, [rsp+1130h+phglobal]; phglobal
0x1810459c4  mov     [rsp+1130h+phglobal], r13
0x1810459c9  call    cs:__imp_GetHGlobalFromStream
0x1810459cf  test    eax, eax
0x1810459d1  js      short loc_1810459DE
0x1810459d3  mov     rcx, [rsp+1130h+phglobal]; hMem
0x1810459d8  call    cs:__imp_GlobalFree
0x1810459de  mov     rcx, [rsp+1130h+ppstm]
0x1810459e3  mov     rax, [rcx]
0x1810459e6  mov     rax, [rax+10h]
0x1810459ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810459ef  mov     rcx, [rsp+1130h+var_1100]
0x1810459f4  test    rcx, rcx
0x1810459f7  jz      short loc_181045A05
0x1810459f9  mov     rax, [rcx]
0x1810459fc  mov     rax, [rax+10h]
0x181045a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045a05  test    ebx, ebx
0x181045a07  js      short loc_181045A45
0x181045a09  mov     rcx, [rsp+1130h+ppCombinedUri]
0x181045a0e  lea     r8, [rsp+1130h+var_1100]
0x181045a13  mov     rdx, [rsp+1130h+var_10E0]
0x181045a18  mov     dword ptr [rsp+1130h+var_1100], r13d
0x181045a1d  mov     rax, [rcx]
0x181045a20  mov     rax, [rax+0D8h]
0x181045a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045a2c  test    eax, eax
0x181045a2e  js      short loc_181045A45
0x181045a30  mov     eax, dword ptr [rsp+1130h+var_1100]
0x181045a34  mov     [r15], eax
0x181045a37  mov     rax, [rsp+1130h+ppURI]
0x181045a3c  mov     [r12], rax
0x181045a40  mov     [rsp+1130h+ppURI], r13
0x181045a45  mov     rcx, [rsp+1130h+ppCombinedUri]
0x181045a4a  mov     rax, [rcx]
0x181045a4d  mov     rax, [rax+10h]
0x181045a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045a56  mov     rcx, [rsp+1130h+ppURI]
0x181045a5b  test    rcx, rcx
0x181045a5e  jz      short loc_181045A6C
0x181045a60  mov     rax, [rcx]
0x181045a63  mov     rax, [rax+10h]
0x181045a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045a6c  mov     rcx, [rsp+1130h+var_10E0]
0x181045a71  test    rcx, rcx
0x181045a74  jz      short loc_181045A82
0x181045a76  mov     rax, [rcx]
0x181045a79  mov     rax, [rax+10h]
0x181045a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181045a82  mov     eax, ebx
0x181045a84  mov     rcx, [rbp+1030h+var_50]
0x181045a8b  xor     rcx, rsp; StackCookie
0x181045a8e  call    __security_check_cookie
0x181045a93  add     rsp, 10F8h
0x181045a9a  pop     r15
0x181045a9c  pop     r14
0x181045a9e  pop     r13
0x181045aa0  pop     r12
0x181045aa2  pop     rdi
0x181045aa3  pop     rsi
0x181045aa4  pop     rbx
0x181045aa5  pop     rbp
0x181045aa6  retn
```
