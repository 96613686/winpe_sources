# Windows::UI::Input::Inking::CInkStroke::LoadRenderingInfoFromInkStrokeDisp(IInkStrokeDisp *,float)

- ea: `0x180052a00`
- end: `0x180052ca1`
- name: `?LoadRenderingInfoFromInkStrokeDisp@CInkStroke@Inking@Input@UI@Windows@@AEAAJPEAUIInkStrokeDisp@@M@Z`
- size: `673`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStroke *__hidden this, struct IInkStrokeDisp *, float)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180051aa0`

## callees

- `0x1800101bc`
- `0x18004a558`
- `0x180052a00`
- `0x180054bc0`
- `0x180055bc4`
- `0x18005db80`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180052a62`
- `OLEAUT32!__imp_SysAllocString` at `0x180052abf`
- `OLEAUT32!__imp_SysAllocString` at `0x180052a62`
- `OLEAUT32!__imp_SysAllocString` at `0x180052abf`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c68`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180052b8d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180052b8d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180052b75`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180052b75`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180052b4d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180052b4d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052c33`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052c33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::LoadRenderingInfoFromInkStrokeDisp(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2,
        float a3)
{
  HRESULT (__stdcall *get_ExtendedProperties)(IInkStrokeDisp *, IInkExtendedProperties **); // rbx
  HRESULT v6; // ebx
  OLECHAR *v7; // r14
  SAFEARRAY *v8; // r15
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, SAFEARRAY **, __int64 *); // rbx
  unsigned int v11; // esi
  struct Windows::UI::Input::Inking::IInkStrokeRenderingInfo *v12; // rdi
  HRESULT v13; // eax
  LONG plUbound; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  void *ppvData; // [rsp+48h] [rbp-38h] BYREF
  SAFEARRAY *psa[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h]
  __int16 v21; // [rsp+B8h] [rbp+38h] BYREF
  Windows::UI::Input::Inking::InkStrokeRenderingInfo *plLbound; // [rsp+C8h] [rbp+48h] BYREF

  v16 = 0;
  get_ExtendedProperties = a2->lpVtbl->get_ExtendedProperties;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v6 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))get_ExtendedProperties)(a2, &v16);
  if ( v6 >= 0 )
  {
    v7 = SysAllocString(L"{29079F6D-5576-4612-8B05-C526280D067B}");
    if ( v7 )
    {
      v21 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int16 *))(*(_QWORD *)v16 + 104LL))(v16, v7, &v21);
      if ( v6 >= 0 && v21 == -1 )
      {
        *(_OWORD *)psa = 0;
        LOWORD(psa[0]) = 8;
        v8 = (SAFEARRAY *)SysAllocString(L"{29079F6D-5576-4612-8B05-C526280D067B}");
        psa[1] = v8;
        if ( v8 )
        {
          v17 = 0;
          v9 = v16;
          v10 = *(__int64 (__fastcall **)(__int64, SAFEARRAY **, __int64 *))(*(_QWORD *)v16 + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          v20 = 0;
          v6 = v10(v9, psa, &v17);
          if ( v6 >= 0 )
          {
            *(_OWORD *)psa = 0;
            v20 = 0;
            v6 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY **))(*(_QWORD *)v17 + 64LL))(v17, psa);
            if ( v6 >= 0 )
            {
              ppvData = 0;
              v6 = SafeArrayAccessData(psa[1], &ppvData);
              if ( v6 >= 0 )
              {
                LODWORD(plLbound) = 0;
                plUbound = 0;
                v6 = -2147418113;
                if ( SafeArrayGetLBound(psa[1], 1u, (LONG *)&plLbound) >= 0
                  && SafeArrayGetUBound(psa[1], 1u, &plUbound) >= 0
                  && (int)plLbound <= plUbound )
                {
                  v11 = (int)*(float *)ppvData;
                  if ( v11 )
                  {
                    if ( plUbound - (_DWORD)plLbound == 15 * v11 + 5 )
                    {
                      Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::InkStrokeRenderingInfo,>(&plLbound);
                      v12 = plLbound;
                      if ( plLbound )
                      {
                        v6 = Windows::UI::Input::Inking::InkStrokeRenderingInfo::InitializeFromISF(
                               plLbound,
                               v11,
                               (const float *)ppvData + 1,
                               a3 * 0.125,
                               a3 * 0.875,
                               (Windows::UI::Input::Inking::CInkStroke *)((char *)this + 208));
                        if ( v6 >= 0 )
                          v6 = Windows::UI::Input::Inking::CInkStroke::SetRenderingInfoPrivate(this, v12);
                      }
                      else
                      {
                        v6 = -2147024882;
                      }
                      v13 = SafeArrayUnaccessData(psa[1]);
                      if ( v6 >= 0 )
                        v6 = v13;
                      if ( v12 )
                        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::Inking::IInkStrokeRenderingInfo>::Release(v12);
                    }
                  }
                }
              }
            }
          }
          SysFreeString(&v8->cDims);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        }
        else
        {
          v6 = -2147024882;
        }
      }
      SysFreeString(v7);
    }
    else
    {
      v6 = -2147024882;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180052a00  mov     [rsp-28h+arg_0], rbx
0x180052a05  mov     [rsp-28h+arg_10], rsi
0x180052a0a  push    rbp
0x180052a0b  push    rdi
0x180052a0c  push    r13
0x180052a0e  push    r14
0x180052a10  push    r15
0x180052a12  mov     rbp, rsp
0x180052a15  sub     rsp, 80h
0x180052a1c  movaps  [rsp+80h+var_10], xmm6
0x180052a21  movaps  xmm6, xmm2
0x180052a24  mov     rdi, rdx
0x180052a27  mov     r13, rcx
0x180052a2a  mov     [rbp+var_48], 0
0x180052a32  mov     rax, [rdx]
0x180052a35  mov     rbx, [rax+60h]
0x180052a39  lea     rcx, [rbp+var_48]
0x180052a3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052a42  lea     rdx, [rbp+var_48]
0x180052a46  mov     rcx, rdi
0x180052a49  mov     rax, rbx
0x180052a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a51  mov     ebx, eax
0x180052a53  test    eax, eax
0x180052a55  js      loc_180052C75
0x180052a5b  lea     rcx, a29079f6d557646; "{29079F6D-5576-4612-8B05-C526280D067B}"
0x180052a62  call    cs:__imp_SysAllocString
0x180052a68  mov     r14, rax
0x180052a6b  test    rax, rax
0x180052a6e  jz      loc_180052C70
0x180052a74  xor     ecx, ecx
0x180052a76  mov     [rbp+arg_8], cx
0x180052a7a  mov     rcx, [rbp+var_48]
0x180052a7e  mov     rdx, [rcx]
0x180052a81  mov     rax, [rdx+68h]
0x180052a85  lea     r8, [rbp+arg_8]
0x180052a89  mov     rdx, r14
0x180052a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a91  mov     ebx, eax
0x180052a93  test    eax, eax
0x180052a95  js      loc_180052C65
0x180052a9b  or      eax, 0FFFFFFFFh
0x180052a9e  cmp     ax, [rbp+arg_8]
0x180052aa2  jnz     loc_180052C65
0x180052aa8  xorps   xmm0, xmm0
0x180052aab  xor     esi, esi
0x180052aad  movups  xmmword ptr [rbp+psa], xmm0
0x180052ab1  lea     eax, [rsi+8]
0x180052ab4  mov     word ptr [rbp+psa], ax
0x180052ab8  lea     rcx, a29079f6d557646; "{29079F6D-5576-4612-8B05-C526280D067B}"
0x180052abf  call    cs:__imp_SysAllocString
0x180052ac5  mov     r15, rax
0x180052ac8  mov     [rbp+psa+8], rax
0x180052acc  test    rax, rax
0x180052acf  jz      loc_180052C60
0x180052ad5  mov     [rbp+var_40], rsi
0x180052ad9  mov     rdi, [rbp+var_48]
0x180052add  mov     rax, [rdi]
0x180052ae0  mov     rbx, [rax+48h]
0x180052ae4  lea     rcx, [rbp+var_40]
0x180052ae8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052aed  movups  xmm0, xmmword ptr [rbp+psa]
0x180052af1  movaps  xmmword ptr [rbp+psa], xmm0
0x180052af5  mov     [rbp+var_20], rsi
0x180052af9  lea     r8, [rbp+var_40]
0x180052afd  lea     rdx, [rbp+psa]
0x180052b01  mov     rcx, rdi
0x180052b04  mov     rax, rbx
0x180052b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b0c  mov     ebx, eax
0x180052b0e  test    eax, eax
0x180052b10  js      loc_180052C4B
0x180052b16  xorps   xmm0, xmm0
0x180052b19  xor     eax, eax
0x180052b1b  movups  xmmword ptr [rbp+psa], xmm0
0x180052b1f  mov     [rbp+var_20], rax
0x180052b23  mov     rcx, [rbp+var_40]
0x180052b27  mov     rax, [rcx]
0x180052b2a  lea     rdx, [rbp+psa]
0x180052b2e  mov     rax, [rax+40h]
0x180052b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b37  mov     ebx, eax
0x180052b39  test    eax, eax
0x180052b3b  js      loc_180052C4B
0x180052b41  mov     [rbp+ppvData], rsi
0x180052b45  lea     rdx, [rbp+ppvData]; ppvData
0x180052b49  mov     rcx, [rbp+psa+8]; psa
0x180052b4d  call    cs:__imp_SafeArrayAccessData
0x180052b53  mov     ebx, eax
0x180052b55  test    eax, eax
0x180052b57  js      loc_180052C4B
0x180052b5d  mov     dword ptr [rbp+plLbound], esi
0x180052b60  mov     [rbp+plUbound], esi
0x180052b63  mov     ebx, 8000FFFFh
0x180052b68  lea     r8, [rbp+plLbound]; plLbound
0x180052b6c  lea     edi, [rsi+1]
0x180052b6f  mov     edx, edi; nDim
0x180052b71  mov     rcx, [rbp+psa+8]; psa
0x180052b75  call    cs:__imp_SafeArrayGetLBound
0x180052b7b  test    eax, eax
0x180052b7d  js      loc_180052C4B
0x180052b83  lea     r8, [rbp+plUbound]; plUbound
0x180052b87  mov     edx, edi; nDim
0x180052b89  mov     rcx, [rbp+psa+8]; psa
0x180052b8d  call    cs:__imp_SafeArrayGetUBound
0x180052b93  test    eax, eax
0x180052b95  js      loc_180052C4B
0x180052b9b  mov     ecx, [rbp+plUbound]
0x180052b9e  cmp     dword ptr [rbp+plLbound], ecx
0x180052ba1  jg      loc_180052C4B
0x180052ba7  mov     rax, [rbp+ppvData]
0x180052bab  cvttss2si rsi, dword ptr [rax]
0x180052bb0  test    esi, esi
0x180052bb2  jz      loc_180052C4B
0x180052bb8  imul    eax, esi, 0Fh
0x180052bbb  add     eax, 5
0x180052bbe  sub     ecx, dword ptr [rbp+plLbound]
0x180052bc1  cmp     ecx, eax
0x180052bc3  jnz     loc_180052C4B
0x180052bc9  lea     rcx, [rbp+plLbound]
0x180052bcd  call    ??$Make@VInkStrokeRenderingInfo@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VInkStrokeRenderingInfo@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::InkStrokeRenderingInfo,>(void)
0x180052bd2  mov     rdi, [rbp+plLbound]
0x180052bd6  test    rdi, rdi
0x180052bd9  jz      short loc_180052C2A
0x180052bdb  lea     rax, [r13+0D0h]
0x180052be2  movaps  xmm0, xmm6
0x180052be5  mulss   xmm0, cs:__real@3f600000
0x180052bed  mulss   xmm6, cs:__real@3e000000
0x180052bf5  mov     r8, [rbp+ppvData]
0x180052bf9  add     r8, 4; float *
0x180052bfd  mov     [rsp+80h+var_58], rax; struct Windows::Foundation::Numerics::Matrix3x2 *
0x180052c02  movss   [rsp+80h+var_60], xmm0; float
0x180052c08  movaps  xmm3, xmm6; float
0x180052c0b  mov     edx, esi; unsigned int
0x180052c0d  mov     rcx, rdi; this
0x180052c10  call    ?InitializeFromISF@InkStrokeRenderingInfo@Inking@Input@UI@Windows@@UEAAJIPEBMMMAEBUMatrix3x2@Numerics@Foundation@5@@Z; Windows::UI::Input::Inking::InkStrokeRenderingInfo::InitializeFromISF(uint,float const *,float,float,Windows::Foundation::Numerics::Matrix3x2 const &)
0x180052c15  mov     ebx, eax
0x180052c17  test    eax, eax
0x180052c19  js      short loc_180052C2F
0x180052c1b  mov     rdx, rdi; struct Windows::UI::Input::Inking::IInkStrokeRenderingInfo *
0x180052c1e  mov     rcx, r13; this
0x180052c21  call    ?SetRenderingInfoPrivate@CInkStroke@Inking@Input@UI@Windows@@AEAAJPEAUIInkStrokeRenderingInfo@2345@@Z; Windows::UI::Input::Inking::CInkStroke::SetRenderingInfoPrivate(Windows::UI::Input::Inking::IInkStrokeRenderingInfo *)
0x180052c26  mov     ebx, eax
0x180052c28  jmp     short loc_180052C2F
0x180052c2a  mov     ebx, 8007000Eh
0x180052c2f  mov     rcx, [rbp+psa+8]; psa
0x180052c33  call    cs:__imp_SafeArrayUnaccessData
0x180052c39  test    ebx, ebx
0x180052c3b  cmovns  ebx, eax
0x180052c3e  test    rdi, rdi
0x180052c41  jz      short loc_180052C4B
0x180052c43  mov     rcx, rdi
0x180052c46  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInkStrokeRenderingInfo@Inking@Input@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::Inking::IInkStrokeRenderingInfo>::Release(void)
0x180052c4b  mov     rcx, r15; bstrString
0x180052c4e  call    cs:__imp_SysFreeString
0x180052c54  nop
0x180052c55  lea     rcx, [rbp+var_40]
0x180052c59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052c5e  jmp     short loc_180052C65
0x180052c60  mov     ebx, 8007000Eh
0x180052c65  mov     rcx, r14; bstrString
0x180052c68  call    cs:__imp_SysFreeString
0x180052c6e  jmp     short loc_180052C75
0x180052c70  mov     ebx, 8007000Eh
0x180052c75  lea     rcx, [rbp+var_48]
0x180052c79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052c7e  mov     eax, ebx
0x180052c80  lea     r11, [rsp+80h+var_s0]
0x180052c88  mov     rbx, [r11+30h]
0x180052c8c  mov     rsi, [r11+40h]
0x180052c90  movaps  xmm6, [rsp+80h+var_10]
0x180052c95  mov     rsp, r11
0x180052c98  pop     r15
0x180052c9a  pop     r14
0x180052c9c  pop     r13
0x180052c9e  pop     rdi
0x180052c9f  pop     rbp
0x180052ca0  retn
```
