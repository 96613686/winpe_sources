# Utils::GetSemStoreKey(void)

- ea: `0x18003cccc`
- end: `0x18003cf05`
- name: `?GetSemStoreKey@Utils@@YA?AV?$vector@EU?$secure_allocator@E@wil@@@std@@XZ`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b7b0`

## callees

- `0x180008f84`
- `0x180009cf0`
- `0x180018778`
- `0x18001899c`
- `0x18002b520`
- `0x18002b8fc`
- `0x180032164`
- `0x18003cccc`
- `0x18004ba10`
- `0x18004d138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce5c`
- `CRYPT32!CryptUnprotectData` at `0x18003ce21`
- `CRYPT32!CryptUnprotectData` at `0x18003ce21`

## string_xrefs

- `0x18003ce87`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18003ce9d`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18003ceb2`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18003cec4`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18003cef3`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Utils::GetSemStoreKey(_QWORD *a1)
{
  const char *v2; // r9
  unsigned int ValueW; // eax
  unsigned int v4; // eax
  const char *v5; // r9
  unsigned int v7; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-19h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-19h]
  const char *pvData; // [rsp+28h] [rbp-11h]
  DATA_BLOB pDataOut; // [rsp+40h] [rbp+7h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp+17h] BYREF
  DATA_BLOB *p_pDataOut; // [rsp+60h] [rbp+27h]
  char v14; // [rsp+68h] [rbp+2Fh]
  PVOID v15[2]; // [rsp+70h] [rbp+37h] BYREF
  __int64 v16; // [rsp+80h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  DWORD pcbData; // [rsp+A8h] [rbp+6Fh] BYREF
  int v19; // [rsp+B0h] [rbp+77h]

  v19 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
      v2);
  pcbData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer\\Store",
             L"Key",
             8u,
             0,
             0,
             &pcbData);
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
      (const char *)ValueW,
      pdwType);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v19 = 1;
  if ( pcbData )
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(v15);
  v4 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer\\Store",
         L"Key",
         8u,
         0,
         v15[0],
         &pcbData);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
      (const char *)v4,
      pdwTypea);
  pDataIn.cbData = LODWORD(v15[1]) - LODWORD(v15[0]);
  *(&pDataIn.cbData + 1) = 0;
  pDataIn.pbData = (BYTE *)v15[0];
  pDataOut = 0;
  p_pDataOut = &pDataOut;
  v14 = 1;
  if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
      v5);
  if ( pDataOut.cbData != 32 )
  {
    v7 = wil::verify_hresult(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
      (const char *)v7,
      (int)"Key corrupted",
      pvData);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Insert_counted_range<unsigned char *>(
    a1,
    a1[1],
    pDataOut.pbData,
    32);
  LocalFree(pDataOut.pbData);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(v15);
  return a1;
}

```

## disassembly

```asm
0x18003cccc  mov     [rsp-8+arg_18], rbx
0x18003ccd1  mov     [rsp-8+arg_0], rcx
0x18003ccd6  push    rbp
0x18003ccd7  lea     rbp, [rsp-57h]
0x18003ccdc  sub     rsp, 90h
0x18003cce3  mov     rbx, rcx
0x18003cce6  mov     [rbp+57h+arg_10], 1
0x18003cced  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54620742@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742> `wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl(void)'::`2'::impl
0x18003ccf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(void)
0x18003ccf9  test    al, al
0x18003ccfb  jz      loc_18003CE99
0x18003cd01  mov     [rbp+57h+arg_8], 0
0x18003cd08  lea     rax, [rbp+57h+arg_8]
0x18003cd0c  mov     [rsp+90h+pcbData], rax; pcbData
0x18003cd11  mov     [rsp+90h+pvData], 0; pvData
0x18003cd1a  mov     [rsp+90h+pdwType], 0; unsigned int
0x18003cd23  mov     r9d, 8; dwFlags
0x18003cd29  lea     r8, aKey; "Key"
0x18003cd30  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x18003cd37  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003cd3e  call    cs:__imp_RegGetValueW
0x18003cd44  test    eax, eax
0x18003cd46  jnz     loc_18003CE80
0x18003cd4c  xorps   xmm0, xmm0
0x18003cd4f  movdqu  xmmword ptr [rbp+57h+var_20], xmm0
0x18003cd54  mov     [rbp+57h+var_10], 0
0x18003cd5c  mov     qword ptr [rbx], 0
0x18003cd63  mov     qword ptr [rbx+8], 0
0x18003cd6b  mov     qword ptr [rbx+10h], 0
0x18003cd73  mov     [rbp+57h+arg_10], 1
0x18003cd7a  mov     edx, [rbp+57h+arg_8]
0x18003cd7d  test    rdx, rdx
0x18003cd80  jz      short loc_18003CD8B
0x18003cd82  lea     rcx, [rbp+57h+var_20]
0x18003cd86  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003cd8b  lea     rax, [rbp+57h+arg_8]
0x18003cd8f  mov     [rsp+90h+pcbData], rax; pcbData
0x18003cd94  mov     rax, [rbp+57h+var_20]
0x18003cd98  mov     [rsp+90h+pvData], rax; pvData
0x18003cd9d  mov     [rsp+90h+pdwType], 0; unsigned int
0x18003cda6  mov     r9d, 8; dwFlags
0x18003cdac  lea     r8, aKey; "Key"
0x18003cdb3  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x18003cdba  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003cdc1  call    cs:__imp_RegGetValueW
0x18003cdc7  mov     rcx, [rbp+5Fh]; this
0x18003cdcb  test    eax, eax
0x18003cdcd  jnz     loc_18003CEAF
0x18003cdd3  mov     eax, dword ptr [rbp+57h+var_20+8]
0x18003cdd6  mov     rcx, [rbp+57h+var_20]
0x18003cdda  sub     eax, ecx
0x18003cddc  mov     [rbp+57h+pDataIn.cbData], eax
0x18003cddf  xor     eax, eax
0x18003cde1  mov     dword ptr [rbp+57h+pDataIn+4], eax
0x18003cde4  mov     [rbp+57h+pDataIn.pbData], rcx
0x18003cde8  xorps   xmm0, xmm0
0x18003cdeb  movups  xmmword ptr [rbp+57h+pDataOut.cbData], xmm0
0x18003cdef  lea     rax, [rbp+57h+pDataOut]
0x18003cdf3  mov     [rbp+57h+var_30], rax
0x18003cdf7  mov     [rbp+57h+var_28], 1
0x18003cdfb  lea     rax, [rbp+57h+pDataOut]
0x18003cdff  mov     [rsp+90h+pcbData], rax; pDataOut
0x18003ce04  mov     dword ptr [rsp+90h+pvData], 0; char *
0x18003ce0c  mov     [rsp+90h+pdwType], 0; pPromptStruct
0x18003ce15  xor     r9d, r9d; pvReserved
0x18003ce18  xor     r8d, r8d; pOptionalEntropy
0x18003ce1b  xor     edx, edx; ppszDataDescr
0x18003ce1d  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18003ce21  call    cs:__imp_CryptUnprotectData
0x18003ce27  mov     rcx, [rbp+5Fh]; this
0x18003ce2b  test    eax, eax
0x18003ce2d  jz      loc_18003CEC4
0x18003ce33  cmp     [rbp+57h+pDataOut.cbData], 20h ; ' '
0x18003ce37  jnz     loc_18003CED6
0x18003ce3d  mov     r8, [rbp+57h+pDataOut.pbData]
0x18003ce41  mov     r9, r8
0x18003ce44  sub     r9, r8
0x18003ce47  add     r9, 20h ; ' '
0x18003ce4b  mov     rdx, [rbx+8]
0x18003ce4f  mov     rcx, rbx
0x18003ce52  call    ??$_Insert_counted_range@PEAE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18003ce57  nop
0x18003ce58  mov     rcx, [rbp+57h+pDataOut.pbData]; hMem
0x18003ce5c  call    cs:__imp_LocalFree
0x18003ce62  nop
0x18003ce63  lea     rcx, [rbp+57h+var_20]
0x18003ce67  call    ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
0x18003ce6c  mov     rax, rbx
0x18003ce6f  mov     rbx, [rsp+90h+arg_18]
0x18003ce77  add     rsp, 90h
0x18003ce7e  pop     rbp
0x18003ce7f  retn
0x18003ce80  mov     rcx, [rbp+5Fh]; this
0x18003ce84  mov     r9d, eax; char *
0x18003ce87  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003ce8e  mov     edx, 8Bh; void *
0x18003ce93  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003ce99  mov     rcx, [rbp+5Fh]; this
0x18003ce9d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003cea4  mov     edx, 91h; void *
0x18003cea9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18003ceaf  mov     r9d, eax; char *
0x18003ceb2  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003ceb9  mov     edx, 76h ; 'v'; void *
0x18003cebe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003cec4  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003cecb  mov     edx, 7Dh ; '}'; void *
0x18003ced0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ced6  mov     ecx, 8000FFFFh
0x18003cedb  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18003cee0  mov     r9d, eax; char *
0x18003cee3  mov     rcx, [rbp+5Fh]; this
0x18003cee7  lea     rax, aKeyCorrupted; "Key corrupted"
0x18003ceee  mov     [rsp+90h+pdwType], rax; int
0x18003cef3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003cefa  mov     edx, 82h; void *
0x18003ceff  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
