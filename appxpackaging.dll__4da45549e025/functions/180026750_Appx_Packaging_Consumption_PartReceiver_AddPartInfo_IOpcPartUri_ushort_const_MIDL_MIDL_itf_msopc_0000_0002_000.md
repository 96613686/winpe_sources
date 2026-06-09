# Appx::Packaging::Consumption::PartReceiver::AddPartInfo(IOpcPartUri *,ushort const *,__MIDL___MIDL_itf_msopc_0000_0002_0002,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *,IByteSender *)

- ea: `0x180026750`
- end: `0x1800269c9`
- name: `?AddPartInfo@PartReceiver@Consumption@Packaging@Appx@@UEAAJPEAUIOpcPartUri@@PEBGW4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@PEAUIByteSender@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(Appx::Packaging::Consumption::PartReceiver *__hidden this, struct IOpcPartUri *, const unsigned __int16 *, enum __MIDL___MIDL_itf_msopc_0000_0002_0002, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *, struct IByteSender *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800133fc`
- `0x180026750`
- `0x1800269d0`
- `0x180026a0c`
- `0x180026a60`
- `0x180071f50`
- `0x1800992d0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800268cc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800268cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800267a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800267a7`
- `OLEAUT32!__imp_SysFreeString` at `0x180026904`
- `OLEAUT32!__imp_SysFreeString` at `0x18002695e`
- `OLEAUT32!__imp_SysFreeString` at `0x180026904`
- `OLEAUT32!__imp_SysFreeString` at `0x18002695e`

## string_xrefs

- `0x1800268ec`: `onecore\printscan\appxpackaging\consumption\src\readerpushinterfaces.cpp`
- `0x180026946`: `onecore\printscan\appxpackaging\consumption\src\readerpushinterfaces.cpp`
- `0x180026982`: `onecore\printscan\appxpackaging\consumption\src\readerpushinterfaces.cpp`
- `0x1800269ab`: `onecore\printscan\appxpackaging\consumption\src\readerpushinterfaces.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::PartReceiver::AddPartInfo(
        PRTL_AVL_TABLE *this,
        struct IOpcPartUri *a2,
        OLECHAR *a3,
        enum __MIDL___MIDL_itf_msopc_0000_0002_0002 a4,
        const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *a5,
        struct IByteSender *a6)
{
  OLECHAR *v9; // rbx
  unsigned int v10; // esi
  OLECHAR *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // edi
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  __int128 v16; // xmm1
  __int64 v17; // rcx
  struct IOpcPartUriVtbl *lpVtbl; // rax
  int v19; // eax
  OLECHAR *v20; // rcx
  unsigned int v21; // edx
  unsigned int v23; // edx
  int NewElement; // [rsp+20h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-20h] BYREF
  _QWORD Buffer[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v9 = (OLECHAR *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\readerpushinterfaces.cpp",
      (const char *)0x8007000ELL,
      NewElement);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(0);
    return v10;
  }
  *(_OWORD *)v9 = 0;
  *((_OWORD *)v9 + 1) = 0;
  *((_OWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 6) = 0;
  CoTaskMemFree(*(LPVOID *)v9);
  *(_QWORD *)v9 = 0;
  v10 = -2147024882;
  if ( !a3 )
    goto LABEL_10;
  v11 = a3;
  v12 = 0x7FFFFFFF;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = v12 == 0 ? 0x80070057 : 0;
  v14 = (const unsigned __int16 *)((0x7FFFFFFF - v12) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64));
  if ( !v12
    || ((unsigned int)v14 > 0x3FFFFFFF
      ? (v13 = -2147024809)
      : (v15 = Common::AutoCoTaskMemStringAllocateAndCopy((Common *)a3, v14, 0x7FFFFFFF - (int)v12),
         *(_QWORD *)v9 = v15,
         v13 = v15 == 0 ? 0x8007000E : 0),
        a3 = 0,
        (v13 & 0x80000000) != 0) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\readerpushinterfaces.cpp",
      (const char *)v13,
      NewElement);
    Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(
      (Appx::Packaging::Consumption::AppxFileInfo *)v9,
      v23);
  }
  else
  {
LABEL_10:
    *((_DWORD *)v9 + 2) = a4;
    v16 = *((_OWORD *)a5 + 1);
    *((_OWORD *)v9 + 1) = *(_OWORD *)a5;
    *((_OWORD *)v9 + 2) = v16;
    if ( *((struct IByteSender **)v9 + 6) != a6 )
    {
      if ( a6 )
        (*(void (__fastcall **)(struct IByteSender *))(*(_QWORD *)a6 + 8LL))(a6);
      v17 = *((_QWORD *)v9 + 6);
      *((_QWORD *)v9 + 6) = a6;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    lpVtbl = a2->lpVtbl;
    bstrString = a3;
    v19 = ((__int64 (__fastcall *)(struct IOpcPartUri *, BSTR *))lpVtbl->GetAbsoluteUri)(a2, &bstrString);
    v13 = v19;
    if ( v19 >= 0 )
    {
      Buffer[0] = bstrString;
      Buffer[1] = v9;
      LOBYTE(NewElement) = (_BYTE)a3;
      if ( RtlInsertElementGenericTableAvl(this[4], Buffer, 0x10u, (PBOOLEAN)&NewElement) )
      {
        if ( (_BYTE)NewElement != (_BYTE)a3 )
        {
          v20 = a3;
          v10 = (unsigned int)a3;
          bstrString = a3;
          v9 = a3;
LABEL_20:
          SysFreeString(v20);
          if ( v9 )
            Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(
              (Appx::Packaging::Consumption::AppxFileInfo *)v9,
              v21);
          return v10;
        }
        v10 = -2147024198;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\readerpushinterfaces.cpp",
        (const char *)v10,
        NewElement);
      v20 = bstrString;
      goto LABEL_20;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\readerpushinterfaces.cpp",
      (const char *)(unsigned int)v19,
      NewElement);
    SysFreeString(bstrString);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(v9);
  }
  return v13;
}

```

## disassembly

```asm
0x180026750  mov     [rsp-40h+arg_0], rcx
0x180026755  push    rbp
0x180026756  push    rbx
0x180026757  push    rsi
0x180026758  push    rdi
0x180026759  push    r12
0x18002675b  push    r13
0x18002675d  push    r14
0x18002675f  push    r15
0x180026761  mov     rbp, rsp
0x180026764  sub     rsp, 48h
0x180026768  mov     r12, rdx
0x18002676b  mov     ecx, 38h ; '8'; unsigned __int64
0x180026770  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026777  mov     r13d, r9d
0x18002677a  mov     r15, r8
0x18002677d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026782  xor     edi, edi
0x180026784  mov     rbx, rax
0x180026787  test    rax, rax
0x18002678a  jz      loc_18002697E
0x180026790  xorps   xmm0, xmm0
0x180026793  xor     eax, eax
0x180026795  movups  xmmword ptr [rbx], xmm0
0x180026798  movups  xmmword ptr [rbx+10h], xmm0
0x18002679c  movups  xmmword ptr [rbx+20h], xmm0
0x1800267a0  mov     [rbx+30h], rax
0x1800267a4  mov     rcx, [rbx]; pv
0x1800267a7  call    cs:__imp_CoTaskMemFree
0x1800267ae  nop     dword ptr [rax+rax+00h]
0x1800267b3  mov     [rbx], rdi
0x1800267b6  mov     esi, 8007000Eh
0x1800267bb  mov     r14, rbx
0x1800267be  test    r15, r15
0x1800267c1  jz      short loc_180026834
0x1800267c3  mov     r8d, 7FFFFFFFh
0x1800267c9  mov     rax, r15
0x1800267cc  mov     ecx, r8d
0x1800267cf  cmp     [rax], di
0x1800267d2  jz      short loc_1800267DE
0x1800267d4  add     rax, 2
0x1800267d8  sub     rcx, 1
0x1800267dc  jnz     short loc_1800267CF
0x1800267de  mov     rax, rcx
0x1800267e1  mov     r9d, 80070057h
0x1800267e7  neg     rax
0x1800267ea  mov     rax, rcx
0x1800267ed  sbb     edi, edi
0x1800267ef  sub     r8, rcx; unsigned int
0x1800267f2  not     edi
0x1800267f4  and     edi, r9d
0x1800267f7  neg     rax
0x1800267fa  sbb     rdx, rdx
0x1800267fd  and     rdx, r8; unsigned __int16 *
0x180026800  test    rcx, rcx
0x180026803  jz      loc_1800269A7
0x180026809  cmp     edx, 3FFFFFFFh
0x18002680f  ja      loc_180026976
0x180026815  mov     rcx, r15; this
0x180026818  call    ?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z; Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint)
0x18002681d  mov     [rbx], rax
0x180026820  neg     rax
0x180026823  sbb     edi, edi
0x180026825  not     edi
0x180026827  and     edi, esi
0x180026829  xor     r15d, r15d
0x18002682c  test    edi, edi
0x18002682e  js      loc_1800269A7
0x180026834  mov     rax, [rbp+arg_20]
0x180026838  mov     rdi, [rbp+arg_28]
0x18002683c  mov     [r14+8], r13d
0x180026840  movups  xmm0, xmmword ptr [rax]
0x180026843  movups  xmm1, xmmword ptr [rax+10h]
0x180026847  movups  xmmword ptr [r14+10h], xmm0
0x18002684c  movups  xmmword ptr [r14+20h], xmm1
0x180026851  cmp     [r14+30h], rdi
0x180026855  jz      short loc_180026884
0x180026857  test    rdi, rdi
0x18002685a  jz      short loc_18002686B
0x18002685c  mov     rax, [rdi]
0x18002685f  mov     rcx, rdi
0x180026862  mov     rax, [rax+8]
0x180026866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002686b  mov     rcx, [r14+30h]
0x18002686f  mov     [r14+30h], rdi
0x180026873  test    rcx, rcx
0x180026876  jz      short loc_180026884
0x180026878  mov     rax, [rcx]
0x18002687b  mov     rax, [rax+10h]
0x18002687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026884  mov     rax, [r12]
0x180026888  lea     rdx, [rbp+bstrString]
0x18002688c  mov     rcx, r12
0x18002688f  mov     [rbp+bstrString], r15
0x180026893  mov     rax, [rax+38h]
0x180026897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002689c  mov     edi, eax
0x18002689e  test    eax, eax
0x1800268a0  js      loc_180026942
0x1800268a6  mov     rax, [rbp+bstrString]
0x1800268aa  lea     r9, [rbp+NewElement]; NewElement
0x1800268ae  mov     rcx, [rbp+arg_0]
0x1800268b2  lea     rdx, [rbp+Buffer]; Buffer
0x1800268b6  mov     r8d, 10h; BufferSize
0x1800268bc  mov     [rbp+Buffer], rax
0x1800268c0  mov     [rbp+var_10], r14
0x1800268c4  mov     byte ptr [rbp+NewElement], r15b
0x1800268c8  mov     rcx, [rcx+20h]; Table
0x1800268cc  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800268d3  nop     dword ptr [rax+rax+00h]
0x1800268d8  test    rax, rax
0x1800268db  jz      short loc_1800268E8
0x1800268dd  cmp     byte ptr [rbp+NewElement], r15b
0x1800268e1  jnz     short loc_180026929
0x1800268e3  mov     esi, 800702BAh
0x1800268e8  mov     rcx, [rbp+40h]; this
0x1800268ec  lea     r8, aOnecorePrintsc_129; "onecore\\printscan\\appxpackaging\\cons"...
0x1800268f3  mov     r9d, esi; char *
0x1800268f6  mov     edx, 39h ; '9'; void *
0x1800268fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026900  mov     rcx, [rbp+bstrString]; bstrString
0x180026904  call    cs:__imp_SysFreeString
0x18002690b  nop     dword ptr [rax+rax+00h]
0x180026910  test    rbx, rbx
0x180026913  jnz     short loc_180026938
0x180026915  mov     eax, esi
0x180026917  add     rsp, 48h
0x18002691b  pop     r15
0x18002691d  pop     r14
0x18002691f  pop     r13
0x180026921  pop     r12
0x180026923  pop     rdi
0x180026924  pop     rsi
0x180026925  pop     rbx
0x180026926  pop     rbp
0x180026927  retn
0x180026929  mov     rcx, r15
0x18002692c  mov     esi, r15d
0x18002692f  mov     [rbp+bstrString], rcx
0x180026933  mov     rbx, r15
0x180026936  jmp     short loc_180026904
0x180026938  mov     rcx, rbx; this
0x18002693b  call    ??_GAppxFileInfo@Consumption@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(uint)
0x180026940  jmp     short loc_180026915
0x180026942  mov     rcx, [rbp+40h]; this
0x180026946  lea     r8, aOnecorePrintsc_129; "onecore\\printscan\\appxpackaging\\cons"...
0x18002694d  mov     r9d, edi; char *
0x180026950  mov     edx, 2Fh ; '/'; void *
0x180026955  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002695a  mov     rcx, [rbp+bstrString]; bstrString
0x18002695e  call    cs:__imp_SysFreeString
0x180026965  nop     dword ptr [rax+rax+00h]
0x18002696a  mov     rcx, r14
0x18002696d  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x180026972  mov     eax, edi
0x180026974  jmp     short loc_180026917
0x180026976  mov     edi, r9d
0x180026979  jmp     loc_180026829
0x18002697e  mov     rcx, [rbp+40h]; this
0x180026982  lea     r8, aOnecorePrintsc_129; "onecore\\printscan\\appxpackaging\\cons"...
0x180026989  mov     esi, 8007000Eh
0x18002698e  mov     edx, 22h ; '"'; void *
0x180026993  mov     r9d, esi; char *
0x180026996  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002699b  xor     ecx, ecx
0x18002699d  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x1800269a2  jmp     loc_180026915
0x1800269a7  mov     rcx, [rbp+40h]; this
0x1800269ab  lea     r8, aOnecorePrintsc_129; "onecore\\printscan\\appxpackaging\\cons"...
0x1800269b2  mov     r9d, edi; char *
0x1800269b5  mov     edx, 26h ; '&'; void *
0x1800269ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800269bf  mov     rcx, rbx; this
0x1800269c2  call    ??_GAppxFileInfo@Consumption@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(uint)
0x1800269c7  jmp     short loc_180026972
```
