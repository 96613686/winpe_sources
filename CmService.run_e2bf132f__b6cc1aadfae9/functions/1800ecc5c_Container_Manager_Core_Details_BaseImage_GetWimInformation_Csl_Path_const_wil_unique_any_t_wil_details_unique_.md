# Container::Manager::Core::Details::BaseImage::GetWimInformation(Csl::Path const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::com_ptr_t<IXmlReader,wil::err_exception_policy> &,wil::com_ptr_t<IStream,wil::err_exception_policy> &)

- ea: `0x1800ecc5c`
- end: `0x1800ecf46`
- name: `?GetWimInformation@BaseImage@Details@Core@Manager@Container@@SAJAEBVPath@Csl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIXmlReader@@Uerr_exception_policy@wil@@@9@AEAV?$com_ptr_t@UIStream@@Uerr_exception_policy@wil@@@9@@Z`
- size: `746`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d1764`
- `0x1800ecf4c`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x1800ecc5c`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ece70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ece70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ece8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ece8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ecd38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ece81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ecf0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ecd38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ece81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ecf0d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800ecd4d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800ecd4d`
- `XmlLite!CreateXmlReader` at `0x1800ecda8`
- `XmlLite!CreateXmlReader` at `0x1800ecda8`
- `WIMGAPI!WIMCreateFile` at `0x1800ecc9d`
- `WIMGAPI!WIMCreateFile` at `0x1800ecc9d`
- `WIMGAPI!WIMCloseHandle` at `0x1800ecf1f`
- `WIMGAPI!WIMCloseHandle` at `0x1800ecf1f`
- `WIMGAPI!WIMGetImageInformation` at `0x1800eccde`
- `WIMGAPI!WIMGetImageInformation` at `0x1800eccde`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::BaseImage::GetWimInformation(
        _QWORD *a1,
        HLOCAL *a2,
        __int64 *a3,
        IStream **a4)
{
  __int64 *v5; // r14
  __int64 v7; // rax
  const char *v8; // r9
  __int64 v9; // rbx
  const char *v11; // r9
  unsigned int v12; // edi
  IStream *v13; // rax
  IStream *v14; // rsi
  HRESULT v15; // eax
  int v16; // eax
  HLOCAL v17; // r12
  HLOCAL v18; // r14
  DWORD LastError; // edi
  void *v20; // rax
  void *v21; // rcx
  __int64 v22; // rdx
  IStream *v23; // rdx
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  UINT cbInit; // [rsp+80h] [rbp+40h] BYREF
  __int64 *v28; // [rsp+90h] [rbp+50h]

  v28 = a3;
  v5 = a3;
  v7 = WIMCreateFile(*a1, 0, 3, 0x20000000);
  v9 = v7;
  if ( !v7 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x48B,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
             v8);
  cbInit = 0;
  hMem = 0;
  if ( (unsigned int)WIMGetImageInformation(v7, &hMem, &cbInit) )
  {
    if ( cbInit )
    {
      v13 = SHCreateMemStream((const BYTE *)hMem, cbInit);
      v14 = v13;
      if ( v13 )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( v14 )
      {
        ppvObject = 0;
        v15 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
        v12 = v15;
        if ( v15 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v14);
          v12 = v16;
          if ( v16 >= 0 )
          {
            if ( a2 != &hMem )
            {
              v17 = hMem;
              v18 = *a2;
              if ( *a2 )
              {
                LastError = GetLastError();
                LocalFree(v18);
                SetLastError(LastError);
              }
              *a2 = v17;
              hMem = 0;
              v5 = v28;
            }
            v20 = ppvObject;
            v21 = 0;
            ppvObject = 0;
            v22 = *v5;
            *v5 = (__int64)v20;
            if ( v22 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              v21 = ppvObject;
            }
            v23 = *a4;
            *a4 = v14;
            if ( v23 )
            {
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v23 + 16LL))(v23);
              v21 = ppvObject;
            }
            if ( v21 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
            if ( hMem )
              LocalFree(hMem);
            v12 = 0;
            goto LABEL_34;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4A1,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
            (const char *)(unsigned int)v16,
            0);
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x49F,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
            (const char *)(unsigned int)v15,
            0);
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        }
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      else
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
          (const char *)0x8007000ELL,
          0);
      }
    }
    else
    {
      v12 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x495,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)0x8007000DLL,
        0);
    }
  }
  else
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x493,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
            v11);
  }
  if ( hMem )
    LocalFree(hMem);
LABEL_34:
  WIMCloseHandle(v9);
  return v12;
}

```

## disassembly

```asm
0x1800ecc5c  mov     rax, rsp
0x1800ecc5f  mov     [rax+10h], rbx
0x1800ecc63  mov     [rax+18h], r8
0x1800ecc67  push    rbp
0x1800ecc68  push    rsi
0x1800ecc69  push    rdi
0x1800ecc6a  push    r12
0x1800ecc6c  push    r13
0x1800ecc6e  push    r14
0x1800ecc70  push    r15
0x1800ecc72  mov     rbp, rsp
0x1800ecc75  sub     rsp, 40h
0x1800ecc79  mov     r13, r9
0x1800ecc7c  mov     r14, r8
0x1800ecc7f  mov     r15, rdx
0x1800ecc82  xor     r12d, r12d
0x1800ecc85  mov     [rax-50h], r12
0x1800ecc89  mov     [rax-58h], r12d
0x1800ecc8d  xor     edx, edx
0x1800ecc8f  mov     r9d, 20000000h
0x1800ecc95  lea     r8d, [r12+3]
0x1800ecc9a  mov     rcx, [rcx]
0x1800ecc9d  call    cs:__imp_WIMCreateFile
0x1800ecca4  nop     dword ptr [rax+rax+00h]
0x1800ecca9  mov     rbx, rax
0x1800eccac  test    rax, rax
0x1800eccaf  jnz     short loc_1800ECCCB
0x1800eccb1  mov     rcx, [rbp+38h]; this
0x1800eccb5  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800eccbc  mov     edx, 48Bh; void *
0x1800eccc1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800eccc6  jmp     loc_1800ECF2D
0x1800ecccb  mov     [rbp+cbInit], r12d
0x1800ecccf  mov     [rbp+hMem], r12
0x1800eccd3  lea     r8, [rbp+cbInit]
0x1800eccd7  lea     rdx, [rbp+hMem]
0x1800eccdb  mov     rcx, rbx
0x1800eccde  call    cs:__imp_WIMGetImageInformation
0x1800ecce5  nop     dword ptr [rax+rax+00h]
0x1800eccea  test    eax, eax
0x1800eccec  jnz     short loc_1800ECD07
0x1800eccee  mov     rcx, [rbp+38h]; this
0x1800eccf2  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800eccf9  mov     edx, 493h; void *
0x1800eccfe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ecd03  mov     edi, eax
0x1800ecd05  jmp     short loc_1800ECD2B
0x1800ecd07  mov     edx, [rbp+cbInit]; cbInit
0x1800ecd0a  test    edx, edx
0x1800ecd0c  jnz     short loc_1800ECD49
0x1800ecd0e  mov     rcx, [rbp+38h]; this
0x1800ecd12  mov     edi, 8007000Dh
0x1800ecd17  mov     r9d, edi; char *
0x1800ecd1a  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ecd21  mov     edx, 495h; void *
0x1800ecd26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ecd2b  mov     rcx, [rbp+hMem]; hMem
0x1800ecd2f  test    rcx, rcx
0x1800ecd32  jz      loc_1800ECF1C
0x1800ecd38  call    cs:__imp_LocalFree
0x1800ecd3f  nop     dword ptr [rax+rax+00h]
0x1800ecd44  jmp     loc_1800ECF1C
0x1800ecd49  mov     rcx, [rbp+hMem]; pInit
0x1800ecd4d  call    cs:__imp_SHCreateMemStream
0x1800ecd54  nop     dword ptr [rax+rax+00h]
0x1800ecd59  mov     rsi, rax
0x1800ecd5c  test    rax, rax
0x1800ecd5f  jz      short loc_1800ECD71
0x1800ecd61  mov     rcx, [rax]
0x1800ecd64  mov     rax, [rcx+8]
0x1800ecd68  mov     rcx, rsi
0x1800ecd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecd70  nop
0x1800ecd71  test    rsi, rsi
0x1800ecd74  jnz     short loc_1800ECD96
0x1800ecd76  mov     rcx, [rbp+38h]; this
0x1800ecd7a  mov     edi, 8007000Eh
0x1800ecd7f  mov     r9d, edi; char *
0x1800ecd82  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ecd89  mov     edx, 49Bh; void *
0x1800ecd8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ecd93  nop
0x1800ecd94  jmp     short loc_1800ECD2B
0x1800ecd96  mov     [rbp+ppvObject], r12
0x1800ecd9a  xor     r8d, r8d; pMalloc
0x1800ecd9d  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800ecda1  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800ecda8  call    cs:__imp_CreateXmlReader
0x1800ecdaf  nop     dword ptr [rax+rax+00h]
0x1800ecdb4  mov     edi, eax
0x1800ecdb6  test    eax, eax
0x1800ecdb8  jns     short loc_1800ECDFE
0x1800ecdba  mov     rcx, [rbp+38h]; this
0x1800ecdbe  mov     r9d, eax; char *
0x1800ecdc1  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ecdc8  mov     edx, 49Fh; void *
0x1800ecdcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ecdd2  nop
0x1800ecdd3  mov     rcx, [rbp+ppvObject]
0x1800ecdd7  test    rcx, rcx
0x1800ecdda  jz      short loc_1800ECDE9
0x1800ecddc  mov     rax, [rcx]
0x1800ecddf  mov     rax, [rax+10h]
0x1800ecde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecde8  nop
0x1800ecde9  mov     rax, [rsi]
0x1800ecdec  mov     rcx, rsi
0x1800ecdef  mov     rax, [rax+10h]
0x1800ecdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecdf8  nop
0x1800ecdf9  jmp     loc_1800ECD2B
0x1800ecdfe  mov     rcx, [rbp+ppvObject]
0x1800ece02  mov     rax, [rcx]
0x1800ece05  mov     rdx, rsi
0x1800ece08  mov     rax, [rax+18h]
0x1800ece0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ece11  mov     edi, eax
0x1800ece13  test    eax, eax
0x1800ece15  jns     short loc_1800ECE5B
0x1800ece17  mov     rcx, [rbp+38h]; this
0x1800ece1b  mov     r9d, eax; char *
0x1800ece1e  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ece25  mov     edx, 4A1h; void *
0x1800ece2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ece2f  nop
0x1800ece30  mov     rcx, [rbp+ppvObject]
0x1800ece34  test    rcx, rcx
0x1800ece37  jz      short loc_1800ECE46
0x1800ece39  mov     rax, [rcx]
0x1800ece3c  mov     rax, [rax+10h]
0x1800ece40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ece45  nop
0x1800ece46  mov     rax, [rsi]
0x1800ece49  mov     rcx, rsi
0x1800ece4c  mov     rax, [rax+10h]
0x1800ece50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ece55  nop
0x1800ece56  jmp     loc_1800ECD2B
0x1800ece5b  lea     rax, [rbp+hMem]
0x1800ece5f  cmp     r15, rax
0x1800ece62  jz      short loc_1800ECEA9
0x1800ece64  mov     r12, [rbp+hMem]
0x1800ece68  mov     r14, [r15]
0x1800ece6b  test    r14, r14
0x1800ece6e  jz      short loc_1800ECE9B
0x1800ece70  call    cs:__imp_GetLastError
0x1800ece77  nop     dword ptr [rax+rax+00h]
0x1800ece7c  mov     edi, eax
0x1800ece7e  mov     rcx, r14; hMem
0x1800ece81  call    cs:__imp_LocalFree
0x1800ece88  nop     dword ptr [rax+rax+00h]
0x1800ece8d  mov     ecx, edi; dwErrCode
0x1800ece8f  call    cs:__imp_SetLastError
0x1800ece96  nop     dword ptr [rax+rax+00h]
0x1800ece9b  mov     [r15], r12
0x1800ece9e  xor     r12d, r12d
0x1800ecea1  mov     [rbp+hMem], r12
0x1800ecea5  mov     r14, [rbp+arg_10]
0x1800ecea9  mov     rax, [rbp+ppvObject]
0x1800ecead  mov     rcx, r12
0x1800eceb0  mov     [rbp+ppvObject], rcx
0x1800eceb4  mov     rdx, [r14]
0x1800eceb7  mov     [r14], rax
0x1800eceba  test    rdx, rdx
0x1800ecebd  jz      short loc_1800ECED2
0x1800ecebf  mov     rax, [rdx]
0x1800ecec2  mov     rcx, rdx
0x1800ecec5  mov     rax, [rax+10h]
0x1800ecec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecece  mov     rcx, [rbp+ppvObject]
0x1800eced2  mov     rdx, [r13+0]
0x1800eced6  mov     [r13+0], rsi
0x1800eceda  test    rdx, rdx
0x1800ecedd  jz      short loc_1800ECEF2
0x1800ecedf  mov     rax, [rdx]
0x1800ecee2  mov     rcx, rdx
0x1800ecee5  mov     rax, [rax+10h]
0x1800ecee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eceee  mov     rcx, [rbp+ppvObject]
0x1800ecef2  test    rcx, rcx
0x1800ecef5  jz      short loc_1800ECF04
0x1800ecef7  mov     rax, [rcx]
0x1800ecefa  mov     rax, [rax+10h]
0x1800ecefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf03  nop
0x1800ecf04  mov     rcx, [rbp+hMem]; hMem
0x1800ecf08  test    rcx, rcx
0x1800ecf0b  jz      short loc_1800ECF19
0x1800ecf0d  call    cs:__imp_LocalFree
0x1800ecf14  nop     dword ptr [rax+rax+00h]
0x1800ecf19  mov     edi, r12d
0x1800ecf1c  mov     rcx, rbx
0x1800ecf1f  call    cs:__imp_WIMCloseHandle
0x1800ecf26  nop     dword ptr [rax+rax+00h]
0x1800ecf2b  mov     eax, edi
0x1800ecf2d  mov     rbx, [rsp+40h+arg_8]
0x1800ecf35  add     rsp, 40h
0x1800ecf39  pop     r15
0x1800ecf3b  pop     r14
0x1800ecf3d  pop     r13
0x1800ecf3f  pop     r12
0x1800ecf41  pop     rdi
0x1800ecf42  pop     rsi
0x1800ecf43  pop     rbp
0x1800ecf44  retn
```
