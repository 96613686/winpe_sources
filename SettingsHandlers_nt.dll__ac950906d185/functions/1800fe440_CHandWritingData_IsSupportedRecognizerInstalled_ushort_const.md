# CHandWritingData::_IsSupportedRecognizerInstalled(ushort const *)

- ea: `0x1800fe440`
- end: `0x1800fe663`
- name: `?_IsSupportedRecognizerInstalled@CHandWritingData@@AEAAJPEBG@Z`
- size: `547`
- prototype: `__int64 __fastcall(CHandWritingData *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800fe2b4`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x18001d624`
- `0x1800fe440`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fe4da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fe4da`
- `OLEAUT32!__imp_VariantInit` at `0x1800fe559`
- `OLEAUT32!__imp_VariantInit` at `0x1800fe559`
- `OLEAUT32!__imp_VariantClear` at `0x1800fe60a`
- `OLEAUT32!__imp_VariantClear` at `0x1800fe60a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fe5ae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fe5ae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fe5f9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fe5f9`
- `Bcp47Langs!LcidFromBcp47` at `0x1800fe489`
- `Bcp47Langs!LcidFromBcp47` at `0x1800fe489`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHandWritingData::_IsSupportedRecognizerInstalled(CHandWritingData *this, unsigned __int16 *a2)
{
  __int64 v3; // rax
  HRESULT v4; // ebx
  unsigned int i; // esi
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD, __int64 *); // rbx
  SAFEARRAY *parray; // rcx
  __int64 v9; // r8
  __int16 *v10; // r9
  int v12; // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  void *ppvData; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF

  ppvData = a2;
  v13 = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&pvarg, &ppvData);
  if ( (int)LcidFromBcp47(*(_QWORD *)(v3 + 24), &v13) < 0 )
  {
    return 0;
  }
  else
  {
    ppv = 0;
    v14 = 0;
    v12 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    if ( CoCreateInstance(&CLSID_InkRecognizers, 0, 0x17u, &GUID_9ccc4f12_b0b7_4a8b_bf58_4aeca4e8cefd, &ppv) < 0 )
    {
      v4 = 0;
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v12);
      for ( i = 0; (int)i < v12; ++i )
      {
        if ( v4 < 0 || *((_BYTE *)this + 2048) )
          break;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        v6 = ppv;
        v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 80LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        v4 = v7(v6, i, &v14);
        VariantInit(&pvarg);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 80LL))(v14, &pvarg);
          if ( v4 >= 0 && (pvarg.vt & 0x2000) != 0 && pvarg.llVal && *(_DWORD *)(pvarg.llVal + 24) )
          {
            ppvData = 0;
            v4 = SafeArrayAccessData(pvarg.parray, &ppvData);
            parray = pvarg.parray;
            if ( v4 >= 0 )
            {
              v9 = 0;
              if ( *(_DWORD *)(pvarg.llVal + 24) )
              {
                v10 = (__int16 *)ppvData;
                do
                {
                  if ( *((_BYTE *)this + 2048) )
                    break;
                  *((_BYTE *)this + 2048) = v10[v9] == (unsigned __int16)v13;
                  v9 = (unsigned int)(v9 + 1);
                }
                while ( (unsigned int)v9 < parray->rgsabound[0].cElements );
              }
            }
            SafeArrayUnaccessData(parray);
          }
        }
        VariantClear(&pvarg);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800fe440  mov     [rsp-18h+arg_10], rbx
0x1800fe445  mov     [rsp-18h+arg_18], rsi
0x1800fe44a  push    rbp
0x1800fe44b  push    rdi
0x1800fe44c  push    r14
0x1800fe44e  mov     rbp, rsp
0x1800fe451  sub     rsp, 80h
0x1800fe458  mov     rax, cs:__security_cookie
0x1800fe45f  xor     rax, rsp
0x1800fe462  mov     [rbp+var_10], rax
0x1800fe466  mov     r14, rcx
0x1800fe469  mov     [rbp+ppvData], rdx
0x1800fe46d  mov     [rbp+var_4C], 0
0x1800fe474  lea     rdx, [rbp+ppvData]
0x1800fe478  lea     rcx, [rbp+pvarg]
0x1800fe47c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800fe481  lea     rdx, [rbp+var_4C]
0x1800fe485  mov     rcx, [rax+18h]
0x1800fe489  call    cs:__imp_LcidFromBcp47
0x1800fe490  nop     dword ptr [rax+rax+00h]
0x1800fe495  test    eax, eax
0x1800fe497  js      loc_1800FE63A
0x1800fe49d  mov     [rbp+var_40], 0
0x1800fe4a5  mov     [rbp+var_48], 0
0x1800fe4ad  mov     [rbp+var_50], 0
0x1800fe4b4  lea     rcx, [rbp+var_40]
0x1800fe4b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe4bd  lea     rax, [rbp+var_40]
0x1800fe4c1  mov     [rsp+80h+ppv], rax; ppv
0x1800fe4c6  lea     r9, _GUID_9ccc4f12_b0b7_4a8b_bf58_4aeca4e8cefd; riid
0x1800fe4cd  xor     edx, edx; pUnkOuter
0x1800fe4cf  lea     r8d, [rdx+17h]; dwClsContext
0x1800fe4d3  lea     rcx, CLSID_InkRecognizers; rclsid
0x1800fe4da  call    cs:__imp_CoCreateInstance
0x1800fe4e1  nop     dword ptr [rax+rax+00h]
0x1800fe4e6  test    eax, eax
0x1800fe4e8  js      loc_1800FE623
0x1800fe4ee  mov     rcx, [rbp+var_40]
0x1800fe4f2  mov     rax, [rcx]
0x1800fe4f5  lea     rdx, [rbp+var_50]
0x1800fe4f9  mov     rax, [rax+38h]
0x1800fe4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe502  mov     ebx, eax
0x1800fe504  xor     esi, esi
0x1800fe506  cmp     [rbp+var_50], esi
0x1800fe509  jle     loc_1800FE625
0x1800fe50f  test    ebx, ebx
0x1800fe511  js      loc_1800FE625
0x1800fe517  cmp     byte ptr [r14+800h], 0
0x1800fe51f  jnz     loc_1800FE625
0x1800fe525  lea     rcx, [rbp+var_48]
0x1800fe529  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe52e  mov     rdi, [rbp+var_40]
0x1800fe532  mov     rax, [rdi]
0x1800fe535  mov     rbx, [rax+50h]
0x1800fe539  lea     rcx, [rbp+var_48]
0x1800fe53d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe542  lea     r8, [rbp+var_48]
0x1800fe546  mov     edx, esi
0x1800fe548  mov     rcx, rdi
0x1800fe54b  mov     rax, rbx
0x1800fe54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe553  mov     ebx, eax
0x1800fe555  lea     rcx, [rbp+pvarg]; pvarg
0x1800fe559  call    cs:__imp_VariantInit
0x1800fe560  nop     dword ptr [rax+rax+00h]
0x1800fe565  nop
0x1800fe566  test    ebx, ebx
0x1800fe568  js      loc_1800FE606
0x1800fe56e  mov     rcx, [rbp+var_48]
0x1800fe572  mov     rax, [rcx]
0x1800fe575  lea     rdx, [rbp+pvarg]
0x1800fe579  mov     rax, [rax+50h]
0x1800fe57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe582  mov     ebx, eax
0x1800fe584  test    eax, eax
0x1800fe586  js      short loc_1800FE606
0x1800fe588  mov     eax, 2000h
0x1800fe58d  test    word ptr [rbp+pvarg], ax
0x1800fe591  jz      short loc_1800FE606
0x1800fe593  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800fe597  test    rcx, rcx
0x1800fe59a  jz      short loc_1800FE606
0x1800fe59c  cmp     dword ptr [rcx+18h], 0
0x1800fe5a0  jbe     short loc_1800FE606
0x1800fe5a2  mov     [rbp+ppvData], 0
0x1800fe5aa  lea     rdx, [rbp+ppvData]; ppvData
0x1800fe5ae  call    cs:__imp_SafeArrayAccessData
0x1800fe5b5  nop     dword ptr [rax+rax+00h]
0x1800fe5ba  mov     ebx, eax
0x1800fe5bc  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800fe5c0  test    eax, eax
0x1800fe5c2  js      short loc_1800FE5F9
0x1800fe5c4  xor     r8d, r8d
0x1800fe5c7  cmp     [rcx+18h], r8d
0x1800fe5cb  jbe     short loc_1800FE5F9
0x1800fe5cd  mov     r9, [rbp+ppvData]
0x1800fe5d1  cmp     byte ptr [r14+800h], 0
0x1800fe5d9  jnz     short loc_1800FE5F9
0x1800fe5db  movsx   edx, word ptr [r9+r8*2]
0x1800fe5e0  movzx   eax, word ptr [rbp+var_4C]
0x1800fe5e4  cmp     edx, eax
0x1800fe5e6  setz    al
0x1800fe5e9  mov     [r14+800h], al
0x1800fe5f0  inc     r8d
0x1800fe5f3  cmp     r8d, [rcx+18h]
0x1800fe5f7  jb      short loc_1800FE5D1
0x1800fe5f9  call    cs:__imp_SafeArrayUnaccessData
0x1800fe600  nop     dword ptr [rax+rax+00h]
0x1800fe605  nop
0x1800fe606  lea     rcx, [rbp+pvarg]; pvarg
0x1800fe60a  call    cs:__imp_VariantClear
0x1800fe611  nop     dword ptr [rax+rax+00h]
0x1800fe616  inc     esi
0x1800fe618  cmp     esi, [rbp+var_50]
0x1800fe61b  jl      loc_1800FE50F
0x1800fe621  jmp     short loc_1800FE625
0x1800fe623  xor     ebx, ebx
0x1800fe625  lea     rcx, [rbp+var_48]
0x1800fe629  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe62e  nop
0x1800fe62f  lea     rcx, [rbp+var_40]
0x1800fe633  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fe638  jmp     short loc_1800FE63C
0x1800fe63a  xor     ebx, ebx
0x1800fe63c  mov     eax, ebx
0x1800fe63e  mov     rcx, [rbp+var_10]
0x1800fe642  xor     rcx, rsp; StackCookie
0x1800fe645  call    __security_check_cookie
0x1800fe64a  lea     r11, [rsp+80h+var_s0]
0x1800fe652  mov     rbx, [r11+30h]
0x1800fe656  mov     rsi, [r11+38h]
0x1800fe65a  mov     rsp, r11
0x1800fe65d  pop     r14
0x1800fe65f  pop     rdi
0x1800fe660  pop     rbp
0x1800fe661  retn
```
