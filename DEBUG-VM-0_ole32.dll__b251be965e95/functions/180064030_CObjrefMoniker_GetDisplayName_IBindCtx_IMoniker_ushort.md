# CObjrefMoniker::GetDisplayName(IBindCtx *,IMoniker *,ushort * *)

- ea: `0x180064030`
- end: `0x1800642ed`
- name: `?GetDisplayName@CObjrefMoniker@@UEAAJPEAUIBindCtx@@PEAUIMoniker@@PEAPEAG@Z`
- size: `701`
- prototype: `HRESULT __fastcall(CObjrefMoniker *this, IBindCtx *pbc, IMoniker *pmkToLeft, wchar_t **lplpszDisplayName)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009374`
- `0x18001248c`
- `0x18001b810`
- `0x180058824`
- `0x180064030`
- `0x1800643d0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800640a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006419f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180064295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800640a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006419f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180064295`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180064093`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180064093`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800640e8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800640e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064259`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064259`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642bb`

## pseudocode

```c
__int64 __fastcall CObjrefMoniker::GetDisplayName(
        CObjrefMoniker *this,
        IBindCtx *pbc,
        IMoniker *pmkToLeft,
        LPVOID *lplpszDisplayName)
{
  HRESULT v7; // ebx
  wchar_t *v8; // rax
  int v9; // eax
  struct IMonikerVtbl *lpVtbl; // rcx
  int v11; // r15d
  DWORD v12; // r14d
  unsigned __int64 v13; // r14
  wchar_t *v14; // rax
  wchar_t *m_lpszDisplayName; // rcx
  int v16; // eax
  unsigned __int64 v17; // r14
  wchar_t *v18; // rax
  unsigned int v19; // [rsp+28h] [rbp-38h]
  unsigned int v20; // [rsp+28h] [rbp-38h]
  wchar_t *pszPrefix; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 cch; // [rsp+38h] [rbp-28h] BYREF
  wchar_t *pszTemp; // [rsp+40h] [rbp-20h] BYREF
  _ULARGE_INTEGER uli; // [rsp+48h] [rbp-18h] BYREF
  _ULARGE_INTEGER uliNewPos; // [rsp+50h] [rbp-10h] BYREF
  IStream *pIStream; // [rsp+A8h] [rbp+48h] BYREF

  if ( !lplpszDisplayName )
    return 2147942487LL;
  *lplpszDisplayName = 0;
  if ( !this->m_pUnk || pmkToLeft )
    return 2147549183LL;
  v7 = 0;
  pszPrefix = 0;
  if ( !this->m_lpszDisplayName )
  {
    v7 = ProgIDFromCLSID(&CLSID_ObjrefMoniker, &pszPrefix);
    if ( v7 < 0 )
    {
      v8 = (wchar_t *)CoTaskMemAlloc(0xEu);
      pszPrefix = v8;
      if ( !v8 )
      {
        v7 = -2147024882;
        pIStream = 0;
LABEL_23:
        if ( v8 )
          CoTaskMemFree(v8);
        goto LABEL_25;
      }
      v7 = StringCchCopyW(v8, 7u, L"objref");
    }
    pIStream = 0;
    if ( v7 >= 0 )
    {
      v7 = CreateStreamOnHGlobal(0, 1, &pIStream);
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(CObjrefMoniker *, IStream *, __int64))this->CPointerMoniker::CBaseMoniker::IMoniker::lpVtbl->Save)(
               this,
               pIStream,
               1);
        if ( v7 >= 0 )
        {
          v9 = safe_lstrlenW(pszPrefix);
          lpVtbl = this->CPointerMoniker::CBaseMoniker::IMoniker::lpVtbl;
          v11 = v9;
          uli.QuadPart = 0;
          v7 = ((__int64 (__fastcall *)(CObjrefMoniker *, _ULARGE_INTEGER *))lpVtbl->GetSizeMax)(this, &uli);
          if ( v7 >= 0 )
          {
            uliNewPos.QuadPart = 0;
            v12 = uli.LowPart + 2;
            pszTemp = 0;
            v7 = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _ULARGE_INTEGER *))pIStream->lpVtbl->Seek)(
                   pIStream,
                   0,
                   0,
                   &uliNewPos);
            if ( v7 >= 0 )
            {
              v13 = 4 * (v12 / 3) + 1 + 1LL + v11 + 1;
              cch = v13;
              v14 = (wchar_t *)CoTaskMemAlloc(2 * v13);
              this->m_lpszDisplayName = v14;
              if ( v14 )
              {
                pszTemp = v14;
                v7 = StringCchCopyExW(v14, v13, pszPrefix, &pszTemp, &cch, v19);
                if ( v7 >= 0 )
                {
                  v7 = StringCchCopyExW(pszTemp, cch, L":", &pszTemp, &cch, v20);
                  if ( v7 >= 0 )
                  {
                    v7 = IStreamToBase64(pIStream, pszTemp, cch);
                    if ( v7 >= 0 )
                      v7 = StringCchCatW(this->m_lpszDisplayName, v13, L":");
                  }
                }
              }
              else
              {
                v7 = -2147024882;
              }
            }
          }
        }
        ((void (__fastcall *)(IStream *))pIStream->lpVtbl->Release)(pIStream);
      }
    }
    v8 = pszPrefix;
    goto LABEL_23;
  }
LABEL_25:
  m_lpszDisplayName = this->m_lpszDisplayName;
  if ( m_lpszDisplayName && v7 >= 0 )
  {
    v16 = safe_lstrlenW(m_lpszDisplayName);
    if ( (unsigned __int64)v16 < 0x800 )
    {
      if ( v16 )
      {
        v17 = v16 + 1LL;
        v7 = -2147024882;
        v18 = (wchar_t *)CoTaskMemAlloc(2 * v17);
        *lplpszDisplayName = v18;
        if ( v18 )
        {
          v7 = StringCchCopyW(v18, v17, this->m_lpszDisplayName);
          if ( v7 < 0 )
          {
            CoTaskMemFree(*lplpszDisplayName);
            *lplpszDisplayName = 0;
          }
        }
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064030  mov     [rsp-28h+arg_0], rbx
0x180064035  mov     [rsp-28h+arg_8], rsi
0x18006403a  push    rbp
0x18006403b  push    rdi
0x18006403c  push    r12
0x18006403e  push    r14
0x180064040  push    r15
0x180064042  mov     rbp, rsp
0x180064045  sub     rsp, 60h
0x180064049  xor     r12d, r12d
0x18006404c  mov     rsi, lplpszDisplayName
0x18006404f  mov     rdi, this
0x180064052  test    lplpszDisplayName, lplpszDisplayName
0x180064055  jnz     short loc_180064061
0x180064057  mov     eax, 80070057h
0x18006405c  jmp     loc_1800642D4
0x180064061  mov     [lplpszDisplayName], r12
0x180064064  cmp     [this+30h], r12
0x180064068  jz      loc_1800642CF
0x18006406e  test    pmkToLeft, pmkToLeft
0x180064071  jnz     loc_1800642CF
0x180064077  mov     ebx, r12d
0x18006407a  mov     [rbp+pszPrefix], r12
0x18006407e  cmp     [this+38h], r12
0x180064082  jnz     loc_18006425F
0x180064088  lea     pbc, [rbp+pszPrefix]; lplpszProgID
0x18006408c  lea     this, CLSID_ObjrefMoniker; clsid
0x180064093  call    cs:__imp_ProgIDFromCLSID
0x180064099  mov     ebx, eax
0x18006409b  test    eax, eax
0x18006409d  jns     short loc_1800640CD
0x18006409f  mov     ecx, 0Eh; cb
0x1800640a4  call    cs:__imp_CoTaskMemAlloc
0x1800640aa  mov     [rbp+pszPrefix], rax
0x1800640ae  test    rax, rax
0x1800640b1  jz      loc_18006422D
0x1800640b7  lea     pmkToLeft, aObjref; "objref"
0x1800640be  mov     edx, 7; cchDest
0x1800640c3  mov     this, rax; pszDest
0x1800640c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800640cb  mov     ebx, eax
0x1800640cd  mov     [rbp+pIStream], r12
0x1800640d1  test    ebx, ebx
0x1800640d3  js      loc_18006424D
0x1800640d9  mov     r14d, 1
0x1800640df  lea     pmkToLeft, [rbp+pIStream]; ppstm
0x1800640e3  mov     edx, r14d; fDeleteOnRelease
0x1800640e6  xor     ecx, ecx; hGlobal
0x1800640e8  call    cs:__imp_CreateStreamOnHGlobal
0x1800640ee  mov     ebx, eax
0x1800640f0  test    eax, eax
0x1800640f2  js      loc_18006424D
0x1800640f8  mov     rax, [rdi]
0x1800640fb  mov     r8d, r14d
0x1800640fe  mov     pbc, [rbp+pIStream]
0x180064102  mov     this, rdi
0x180064105  mov     rax, [rax+30h]
0x180064109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006410e  mov     ebx, eax
0x180064110  test    eax, eax
0x180064112  js      loc_18006423D
0x180064118  mov     this, [rbp+pszPrefix]; string
0x18006411c  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180064121  mov     this, [rdi]
0x180064124  lea     pbc, [rbp+uli]
0x180064128  mov     r15d, eax
0x18006412b  mov     qword ptr [rbp+uli], r12
0x18006412f  mov     rax, [this+38h]
0x180064133  mov     this, rdi
0x180064136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006413b  mov     ebx, eax
0x18006413d  test    eax, eax
0x18006413f  js      loc_18006423D
0x180064145  mov     this, [rbp+pIStream]
0x180064149  lea     lplpszDisplayName, [rbp+uliNewPos]
0x18006414d  mov     r14d, dword ptr [rbp+uli]
0x180064151  xor     r8d, r8d
0x180064154  mov     qword ptr [rbp+uliNewPos], r12
0x180064158  mov     pbc, r12
0x18006415b  add     r14d, 2
0x18006415f  mov     [rbp+pszTemp], r12
0x180064163  mov     rax, [this]
0x180064166  mov     rax, [rax+28h]
0x18006416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006416f  mov     ebx, eax
0x180064171  test    eax, eax
0x180064173  js      loc_18006423D
0x180064179  mov     eax, 0AAAAAAABh
0x18006417e  mul     r14d
0x180064181  lea     eax, [r15+1]
0x180064185  shr     edx, 1
0x180064187  movsxd  r14, eax
0x18006418a  lea     edx, ds:1[pbc*4]
0x180064191  inc     pbc
0x180064194  add     r14, pbc
0x180064197  mov     [rbp+cch], r14
0x18006419b  lea     this, [r14+r14]; cb
0x18006419f  call    cs:__imp_CoTaskMemAlloc
0x1800641a5  mov     [rdi+38h], rax
0x1800641a9  test    rax, rax
0x1800641ac  jz      loc_180064238
0x1800641b2  mov     pmkToLeft, [rbp+pszPrefix]; pszSrc
0x1800641b6  lea     this, [rbp+cch]
0x1800641ba  mov     [rsp+60h+pcchRemaining], this; pcchRemaining
0x1800641bf  lea     lplpszDisplayName, [rbp+pszTemp]; ppszDestEnd
0x1800641c3  mov     this, rax; pszDest
0x1800641c6  mov     [rbp+pszTemp], rax
0x1800641ca  mov     pbc, r14; cchDest
0x1800641cd  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800641d2  mov     ebx, eax
0x1800641d4  test    eax, eax
0x1800641d6  js      short loc_18006423D
0x1800641d8  mov     pbc, [rbp+cch]; cchDest
0x1800641dc  lea     rax, [rbp+cch]
0x1800641e0  mov     this, [rbp+pszTemp]; pszDest
0x1800641e4  lea     lplpszDisplayName, [rbp+pszTemp]; ppszDestEnd
0x1800641e8  lea     pmkToLeft, asc_1800E0994; ":"
0x1800641ef  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x1800641f4  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800641f9  mov     ebx, eax
0x1800641fb  test    eax, eax
0x1800641fd  js      short loc_18006423D
0x1800641ff  mov     pmkToLeft, [rbp+cch]; cchEncoded
0x180064203  mov     pbc, [rbp+pszTemp]; pszEncoded
0x180064207  mov     this, [rbp+pIStream]; pStream
0x18006420b  call    ?IStreamToBase64@@YAJPEAUIStream@@PEAG_K@Z; IStreamToBase64(IStream *,ushort *,unsigned __int64)
0x180064210  mov     ebx, eax
0x180064212  test    eax, eax
0x180064214  js      short loc_18006423D
0x180064216  mov     this, [rdi+38h]; pszDest
0x18006421a  lea     pmkToLeft, asc_1800E0994; ":"
0x180064221  mov     pbc, r14; cchDest
0x180064224  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180064229  mov     ebx, eax
0x18006422b  jmp     short loc_18006423D
0x18006422d  mov     ebx, 8007000Eh
0x180064232  mov     [rbp+pIStream], r12
0x180064236  jmp     short loc_180064251
0x180064238  mov     ebx, 8007000Eh
0x18006423d  mov     this, [rbp+pIStream]
0x180064241  mov     rax, [this]
0x180064244  mov     rax, [rax+10h]
0x180064248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006424d  mov     rax, [rbp+pszPrefix]
0x180064251  test    rax, rax
0x180064254  jz      short loc_18006425F
0x180064256  mov     this, rax; pv
0x180064259  call    cs:__imp_CoTaskMemFree
0x18006425f  mov     this, [rdi+38h]; string
0x180064263  test    this, this
0x180064266  jz      short loc_1800642CB
0x180064268  test    ebx, ebx
0x18006426a  js      short loc_1800642CB
0x18006426c  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180064271  movsxd  this, eax
0x180064274  cmp     this, 800h
0x18006427b  jb      short loc_180064284
0x18006427d  mov     ebx, 80070057h
0x180064282  jmp     short loc_1800642CB
0x180064284  test    eax, eax
0x180064286  jz      short loc_1800642C6
0x180064288  lea     r14, [this+1]
0x18006428c  mov     ebx, 8007000Eh
0x180064291  lea     this, [r14+r14]; cb
0x180064295  call    cs:__imp_CoTaskMemAlloc
0x18006429b  mov     [rsi], rax
0x18006429e  test    rax, rax
0x1800642a1  jz      short loc_1800642CB
0x1800642a3  mov     pmkToLeft, [rdi+38h]; pszSrc
0x1800642a7  mov     pbc, r14; cchDest
0x1800642aa  mov     this, rax; pszDest
0x1800642ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800642b2  mov     ebx, eax
0x1800642b4  test    eax, eax
0x1800642b6  jns     short loc_1800642CB
0x1800642b8  mov     this, [rsi]; pv
0x1800642bb  call    cs:__imp_CoTaskMemFree
0x1800642c1  mov     [rsi], r12
0x1800642c4  jmp     short loc_1800642CB
0x1800642c6  mov     ebx, 80004005h
0x1800642cb  mov     eax, ebx
0x1800642cd  jmp     short loc_1800642D4
0x1800642cf  mov     eax, 8000FFFFh
0x1800642d4  lea     r11, [rsp+60h+var_s0]
0x1800642d9  mov     rbx, [r11+30h]
0x1800642dd  mov     rsi, [r11+38h]
0x1800642e1  mov     rsp, r11
0x1800642e4  pop     r15
0x1800642e6  pop     r14
0x1800642e8  pop     r12
0x1800642ea  pop     rdi
0x1800642eb  pop     rbp
0x1800642ec  retn
```
