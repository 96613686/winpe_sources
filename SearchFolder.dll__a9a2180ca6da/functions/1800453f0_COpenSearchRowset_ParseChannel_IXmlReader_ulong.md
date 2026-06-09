# COpenSearchRowset::_ParseChannel(IXmlReader *,ulong)

- ea: `0x1800453f0`
- end: `0x180045697`
- name: `?_ParseChannel@COpenSearchRowset@@AEAAJPEAUIXmlReader@@K@Z`
- size: `679`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IXmlReader *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046a08`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000ebd0`
- `0x1800120a4`
- `0x1800453f0`
- `0x1800456a0`
- `0x180047b74`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800454b7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800454b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004564e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004564e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045657`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseChannel(COpenSearchRowset *this, struct IXmlReader *a2, unsigned int a3)
{
  __int64 v3; // r12
  int v6; // ebx
  int v7; // esi
  struct IXmlReaderVtbl *v8; // rax
  COpenSearchRowset *v9; // rcx
  struct IXmlReaderVtbl *lpVtbl; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct IXmlReaderVtbl *v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  WCHAR *psz1; // r15
  COpenSearchRowset *v18; // rcx
  COpenSearchRowset *v19; // rcx
  _DWORD *v20; // rdx
  int v21; // r8d
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v25; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v28[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = a3;
  v23 = 0;
  v6 = 0;
  memset_0(v28, 0, 0x208u);
  v7 = 0;
  do
  {
    if ( v7 )
      break;
    v6 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->Read)(a2, &v23);
    if ( v6 >= 0 )
    {
      if ( v23 == 1 )
      {
        lpVtbl = a2->lpVtbl;
        v27 = 0;
        v6 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))lpVtbl->GetNamespaceUri)(a2, &v27, 0);
        if ( v6 >= 0 )
        {
          pv = 0;
          v6 = _AllocString<CTCoAllocPolicy>(v12, v11, v27);
          if ( v6 >= 0 )
          {
            v13 = a2->lpVtbl;
            v25 = 0;
            v14 = ((__int64 (__fastcall *)(struct IXmlReader *, unsigned __int16 **, _QWORD))v13->GetLocalName)(
                    a2,
                    &v25,
                    0);
            psz1 = (WCHAR *)pv;
            v6 = v14;
            if ( v14 >= 0 )
            {
              pv = 0;
              v6 = _AllocString<CTCoAllocPolicy>(v16, v15, (__int64)v25);
              if ( v6 >= 0 )
              {
                if ( !v28[0] || (v6 = StringCchCatW(v28, 0x104u, L"/"), v6 >= 0) )
                {
                  v6 = StringCchCatW(v28, 0x104u, v25);
                  if ( v6 >= 0 )
                  {
                    if ( ((unsigned int (__fastcall *)(struct IXmlReader *))a2->lpVtbl->IsEmptyElement)(a2) )
                    {
                      COpenSearchRowset::_XmlPathRemoveElement(v18, v28);
                    }
                    else
                    {
                      v6 = COpenSearchRowset::_ParseChannelElement(this, a2, v3, v28, psz1);
                      if ( v6 >= 0 )
                      {
                        v6 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->GetNodeType)(a2, &v23);
                        if ( v6 >= 0 && v23 == 15 )
                          COpenSearchRowset::_XmlPathRemoveElement(v19, v28);
                        if ( *((_DWORD *)this + 21) )
                        {
                          v20 = (_DWORD *)*((_QWORD *)this + 3 * v3 + 81);
                          v21 = v20 ? *v20 : 0;
                          if ( *((_DWORD *)this + 6 * v3 + 160) == v21 )
                            v7 = 1;
                        }
                      }
                    }
                  }
                }
                CoTaskMemFree(pv);
              }
            }
            CoTaskMemFree(psz1);
          }
        }
      }
      else if ( v23 == 15 )
      {
        v8 = a2->lpVtbl;
        pszStr1 = 0;
        v6 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v8->GetLocalName)(a2, &pszStr1, 0);
        if ( v6 >= 0 )
        {
          if ( StrCmpICW(pszStr1, L"channel") )
            COpenSearchRowset::_XmlPathRemoveElement(v9, v28);
          else
            v7 = 1;
        }
      }
    }
  }
  while ( !v6 );
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800453f0  mov     [rsp-8+arg_18], rbx
0x1800453f5  push    rbp
0x1800453f6  push    rsi
0x1800453f7  push    rdi
0x1800453f8  push    r12
0x1800453fa  push    r13
0x1800453fc  push    r14
0x1800453fe  push    r15
0x180045400  lea     rbp, [rsp-180h]
0x180045408  sub     rsp, 280h
0x18004540f  mov     rax, cs:__security_cookie
0x180045416  xor     rax, rsp
0x180045419  mov     [rbp+1B0h+var_40], rax
0x180045420  xor     r13d, r13d
0x180045423  mov     r12d, r8d
0x180045426  mov     rdi, rdx
0x180045429  mov     [rsp+2B0h+var_280], r13d
0x18004542e  mov     r14, rcx
0x180045431  xor     edx, edx; Val
0x180045433  mov     r8d, 208h; Size
0x180045439  lea     rcx, [rsp+2B0h+var_250]; void *
0x18004543e  mov     ebx, r13d
0x180045441  call    memset_0
0x180045446  mov     esi, r13d
0x180045449  lea     r15d, [r13+1]
0x18004544d  test    esi, esi
0x18004544f  jnz     loc_18004566B
0x180045455  mov     rax, [rdi]
0x180045458  lea     rdx, [rsp+2B0h+var_280]
0x18004545d  mov     rcx, rdi
0x180045460  mov     rax, [rax+30h]
0x180045464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045469  mov     ebx, eax
0x18004546b  test    eax, eax
0x18004546d  js      loc_180045663
0x180045473  mov     eax, [rsp+2B0h+var_280]
0x180045477  sub     eax, 1
0x18004547a  jz      short loc_1800454D8
0x18004547c  cmp     eax, 0Eh
0x18004547f  jnz     loc_180045663
0x180045485  mov     rax, [rdi]
0x180045488  lea     rdx, [rsp+2B0h+pszStr1]
0x18004548d  xor     r8d, r8d
0x180045490  mov     [rsp+2B0h+pszStr1], r13
0x180045495  mov     rcx, rdi
0x180045498  mov     rax, [rax+70h]
0x18004549c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454a1  mov     ebx, eax
0x1800454a3  test    eax, eax
0x1800454a5  js      loc_180045663
0x1800454ab  mov     rcx, [rsp+2B0h+pszStr1]; pszStr1
0x1800454b0  lea     rdx, aChannel; "channel"
0x1800454b7  call    cs:__imp_StrCmpICW
0x1800454bd  test    eax, eax
0x1800454bf  jnz     short loc_1800454C9
0x1800454c1  mov     esi, r15d
0x1800454c4  jmp     loc_180045663
0x1800454c9  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800454ce  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x1800454d3  jmp     loc_180045663
0x1800454d8  mov     rax, [rdi]
0x1800454db  lea     rdx, [rsp+2B0h+var_260]
0x1800454e0  xor     r8d, r8d
0x1800454e3  mov     [rsp+2B0h+var_260], r13
0x1800454e8  mov     rcx, rdi
0x1800454eb  mov     rax, [rax+68h]
0x1800454ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454f4  mov     ebx, eax
0x1800454f6  test    eax, eax
0x1800454f8  js      loc_180045663
0x1800454fe  mov     r8, [rsp+2B0h+var_260]
0x180045503  lea     r9, [rsp+2B0h+pv]
0x180045508  mov     [rsp+2B0h+pv], r13
0x18004550d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180045512  mov     ebx, eax
0x180045514  test    eax, eax
0x180045516  js      loc_180045663
0x18004551c  mov     rax, [rdi]
0x18004551f  lea     rdx, [rsp+2B0h+var_270]
0x180045524  xor     r8d, r8d
0x180045527  mov     [rsp+2B0h+var_270], r13
0x18004552c  mov     rcx, rdi
0x18004552f  mov     rax, [rax+70h]
0x180045533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045538  mov     r15, [rsp+2B0h+pv]
0x18004553d  mov     ebx, eax
0x18004553f  test    eax, eax
0x180045541  js      loc_180045654
0x180045547  mov     r8, [rsp+2B0h+var_270]
0x18004554c  lea     r9, [rsp+2B0h+pv]
0x180045551  mov     [rsp+2B0h+pv], r13
0x180045556  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004555b  mov     ebx, eax
0x18004555d  test    eax, eax
0x18004555f  js      loc_180045654
0x180045565  cmp     [rsp+2B0h+var_250], r13w
0x18004556b  jz      short loc_18004558D
0x18004556d  lea     r8, asc_180058A0C; "/"
0x180045574  mov     edx, 104h; unsigned __int64
0x180045579  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18004557e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180045583  mov     ebx, eax
0x180045585  test    eax, eax
0x180045587  js      loc_180045649
0x18004558d  mov     r8, [rsp+2B0h+var_270]; unsigned __int16 *
0x180045592  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180045597  mov     edx, 104h; unsigned __int64
0x18004559c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800455a1  mov     ebx, eax
0x1800455a3  test    eax, eax
0x1800455a5  js      loc_180045649
0x1800455ab  mov     rax, [rdi]
0x1800455ae  mov     rcx, rdi
0x1800455b1  mov     rax, [rax+0A0h]
0x1800455b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455bd  test    eax, eax
0x1800455bf  jz      short loc_1800455CD
0x1800455c1  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800455c6  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x1800455cb  jmp     short loc_180045649
0x1800455cd  lea     r9, [rsp+2B0h+var_250]; pszStr1
0x1800455d2  mov     [rsp+2B0h+psz1], r15; psz1
0x1800455d7  mov     r8d, r12d; unsigned int
0x1800455da  mov     rdx, rdi; struct IXmlReader *
0x1800455dd  mov     rcx, r14; this
0x1800455e0  call    ?_ParseChannelElement@COpenSearchRowset@@AEAAJPEAUIXmlReader@@KPEBG1@Z; COpenSearchRowset::_ParseChannelElement(IXmlReader *,ulong,ushort const *,ushort const *)
0x1800455e5  mov     ebx, eax
0x1800455e7  test    eax, eax
0x1800455e9  js      short loc_180045649
0x1800455eb  mov     rax, [rdi]
0x1800455ee  lea     rdx, [rsp+2B0h+var_280]
0x1800455f3  mov     rcx, rdi
0x1800455f6  mov     rax, [rax+38h]
0x1800455fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455ff  mov     ebx, eax
0x180045601  test    eax, eax
0x180045603  js      short loc_180045616
0x180045605  cmp     [rsp+2B0h+var_280], 0Fh
0x18004560a  jnz     short loc_180045616
0x18004560c  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180045611  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x180045616  cmp     [r14+54h], r13d
0x18004561a  jbe     short loc_180045649
0x18004561c  lea     rax, [r12+r12*2]
0x180045620  mov     rdx, [r14+rax*8+288h]
0x180045628  test    rdx, rdx
0x18004562b  jz      short loc_180045632
0x18004562d  mov     r8d, [rdx]
0x180045630  jmp     short loc_180045635
0x180045632  mov     r8d, r13d
0x180045635  lea     rax, [r12+r12*2]
0x180045639  cmp     [r14+rax*8+280h], r8d
0x180045641  mov     eax, 1
0x180045646  cmovz   esi, eax
0x180045649  mov     rcx, [rsp+2B0h+pv]; pv
0x18004564e  call    cs:__imp_CoTaskMemFree
0x180045654  mov     rcx, r15; pv
0x180045657  call    cs:__imp_CoTaskMemFree
0x18004565d  mov     r15d, 1
0x180045663  test    ebx, ebx
0x180045665  jz      loc_18004544D
0x18004566b  mov     eax, ebx
0x18004566d  mov     rcx, [rbp+1B0h+var_40]
0x180045674  xor     rcx, rsp; StackCookie
0x180045677  call    __security_check_cookie
0x18004567c  mov     rbx, [rsp+2B0h+arg_18]
0x180045684  add     rsp, 280h
0x18004568b  pop     r15
0x18004568d  pop     r14
0x18004568f  pop     r13
0x180045691  pop     r12
0x180045693  pop     rdi
0x180045694  pop     rsi
0x180045695  pop     rbp
0x180045696  retn
```
