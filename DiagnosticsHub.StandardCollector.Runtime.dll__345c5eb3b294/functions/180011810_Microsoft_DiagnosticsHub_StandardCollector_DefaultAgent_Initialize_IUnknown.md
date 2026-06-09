# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::Initialize(IUnknown *)

- ea: `0x180011810`
- end: `0x180011b56`
- name: `?Initialize@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUIUnknown@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, struct IUnknown *)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016580`
- `0x1800165b0`
- `0x1800165d0`
- `0x180016600`

## callees

- `0x180002604`
- `0x1800086a4`
- `0x180011264`
- `0x180011320`
- `0x180011810`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800119fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800119fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180011a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ad4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ad4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011a72`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011ac9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011a72`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011ac9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180011a65`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180011abc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180011a65`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180011abc`

## string_xrefs

- `0x1800119b4`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\DefaultAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::Initialize(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        struct IUnknown *a2)
{
  __int64 result; // rax
  _QWORD *v4; // rsi
  HRESULT v5; // edi
  bool v6; // al
  SAFEARRAY *v7; // rbx
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-48h] BYREF
  __int128 v10; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+50h] [rbp-30h] BYREF
  __int64 v12; // [rsp+58h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp-20h] BYREF
  int v14; // [rsp+68h] [rbp-18h] BYREF
  int v15; // [rsp+6Ch] [rbp-14h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (_QWORD *)((char *)this + 88);
  result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_a67a826d_c6b3_4d47_b752_032b89624429,
             (char *)this + 88);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v13 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 88LL))(*v4, &v13);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v13)(
             v13,
             &GUID_25a84e24_f810_44ce_a896_aaf9f1f477ec,
             (char *)this + 96);
      if ( v5 >= 0 )
      {
        _mm_lfence();
        v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 96LL))(*v4, &v14);
        if ( v5 >= 0 )
        {
          *((_BYTE *)this + 280) = (v14 & 2) != 0;
          v6 = (unsigned __int8)anonymous_namespace_::IsDebugOverheadHandlingEnabled() && *((_BYTE *)this + 280);
          *((_BYTE *)this + 281) = v6;
          if ( !*((_BYTE *)this + 282) )
          {
LABEL_38:
            v5 = 0;
            goto LABEL_39;
          }
          _mm_lfence();
          v5 = anonymous_namespace_::DoMarkProvider(*((_QWORD *)this + 12), 0);
          if ( v5 >= 0 )
          {
            _mm_lfence();
            v12 = 0;
            v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 72LL))(*v4, &v12);
            if ( v5 < 0 )
            {
LABEL_27:
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              goto LABEL_39;
            }
            v11 = 0;
            v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
                   v12,
                   &GUID_03779dc9_70da_4063_808f_43ee228b18c4,
                   &v11);
            if ( v5 < 0
              || (v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, qword_180056590),
                  v5 < 0)
              || (_mm_lfence(),
                  DiagHubCommon::LogStream::Write(
                    _logger,
                    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\DefaultAgent.cpp",
                    L"User Marks Tool added to package."),
                  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 56LL))(*v4, &v15),
                  v5 < 0) )
            {
LABEL_25:
              if ( v11 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
              goto LABEL_27;
            }
            if ( v15 == 2 )
            {
              v10 = 0;
              bstrString = SysAllocString(L"DiagnosticsHub.Counters.UserMarks");
              if ( !bstrString )
                ATL::AtlThrowImpl(-2147024882);
              psa = 0;
              v5 = ATL::CComSafeArray<unsigned short *,8>::Add(&psa, (const OLECHAR **)&bstrString, 1);
              v7 = psa;
              if ( v5 < 0
                || (*((_QWORD *)&v10 + 1) = psa,
                    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v13 + 24LL))(
                           v13,
                           4,
                           16,
                           &v10),
                    v5 < 0) )
              {
                if ( v7 && SafeArrayUnlock(v7) >= 0 )
                  SafeArrayDestroy(v7);
                SysFreeString(bstrString);
                goto LABEL_25;
              }
              if ( v7 && SafeArrayUnlock(v7) >= 0 )
                SafeArrayDestroy(v7);
              SysFreeString(bstrString);
            }
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            goto LABEL_38;
          }
        }
      }
    }
LABEL_39:
    _mm_lfence();
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x180011810  mov     [rsp-18h+arg_10], rbx
0x180011815  mov     [rsp-18h+arg_18], rsi
0x18001181a  push    rbp
0x18001181b  push    rdi
0x18001181c  push    r14
0x18001181e  mov     rbp, rsp
0x180011821  sub     rsp, 80h
0x180011828  mov     rax, cs:__security_cookie
0x18001182f  xor     rax, rsp
0x180011832  mov     [rbp+var_10], rax
0x180011836  mov     r9, rdx
0x180011839  mov     rbx, rcx
0x18001183c  test    rdx, rdx
0x18001183f  jnz     short loc_18001184B
0x180011841  mov     eax, 80004003h
0x180011846  jmp     loc_180011B27
0x18001184b  lea     rsi, [rcx+58h]
0x18001184f  mov     rax, [rdx]
0x180011852  mov     r8, rsi
0x180011855  lea     rdx, _GUID_a67a826d_c6b3_4d47_b752_032b89624429
0x18001185c  mov     rcx, r9
0x18001185f  mov     rax, [rax]
0x180011862  call    cs:__guard_dispatch_icall_fptr
0x180011868  lfence
0x18001186b  test    eax, eax
0x18001186d  js      loc_180011B27
0x180011873  mov     [rbp+var_20], 0
0x18001187b  mov     rcx, [rsi]
0x18001187e  mov     rax, [rcx]
0x180011881  lea     rdx, [rbp+var_20]
0x180011885  mov     rax, [rax+58h]
0x180011889  call    cs:__guard_dispatch_icall_fptr
0x18001188f  mov     edi, eax
0x180011891  test    eax, eax
0x180011893  js      loc_180011B0B
0x180011899  lfence
0x18001189c  mov     rcx, [rbp+var_20]
0x1800118a0  mov     rax, [rcx]
0x1800118a3  lea     r8, [rbx+60h]
0x1800118a7  lea     rdx, _GUID_25a84e24_f810_44ce_a896_aaf9f1f477ec
0x1800118ae  mov     rax, [rax]
0x1800118b1  call    cs:__guard_dispatch_icall_fptr
0x1800118b7  mov     edi, eax
0x1800118b9  test    eax, eax
0x1800118bb  js      loc_180011B0B
0x1800118c1  lfence
0x1800118c4  mov     rcx, [rsi]
0x1800118c7  mov     rax, [rcx]
0x1800118ca  lea     rdx, [rbp+var_18]
0x1800118ce  mov     rax, [rax+60h]
0x1800118d2  call    cs:__guard_dispatch_icall_fptr
0x1800118d8  mov     edi, eax
0x1800118da  test    eax, eax
0x1800118dc  js      loc_180011B0B
0x1800118e2  mov     eax, [rbp+var_18]
0x1800118e5  shr     eax, 1
0x1800118e7  and     al, 1
0x1800118e9  mov     [rbx+118h], al
0x1800118ef  call    _anonymous_namespace___IsDebugOverheadHandlingEnabled
0x1800118f4  test    al, al
0x1800118f6  jz      short loc_180011905
0x1800118f8  cmp     byte ptr [rbx+118h], 0
0x1800118ff  jz      short loc_180011905
0x180011901  mov     al, 1
0x180011903  jmp     short loc_180011907
0x180011905  xor     al, al
0x180011907  mov     [rbx+119h], al
0x18001190d  cmp     byte ptr [rbx+11Ah], 0
0x180011914  jz      loc_180011B09
0x18001191a  lfence
0x18001191d  xor     edx, edx
0x18001191f  mov     rcx, [rbx+60h]
0x180011923  call    _anonymous_namespace___DoMarkProvider
0x180011928  mov     edi, eax
0x18001192a  test    eax, eax
0x18001192c  js      loc_180011B0B
0x180011932  lfence
0x180011935  mov     [rbp+var_28], 0
0x18001193d  mov     rcx, [rsi]
0x180011940  mov     rax, [rcx]
0x180011943  lea     rdx, [rbp+var_28]
0x180011947  mov     rax, [rax+48h]
0x18001194b  call    cs:__guard_dispatch_icall_fptr
0x180011951  mov     edi, eax
0x180011953  test    eax, eax
0x180011955  js      loc_180011A9B
0x18001195b  mov     [rbp+var_30], 0
0x180011963  mov     rcx, [rbp+var_28]
0x180011967  mov     rax, [rcx]
0x18001196a  lea     r8, [rbp+var_30]
0x18001196e  lea     rdx, _GUID_03779dc9_70da_4063_808f_43ee228b18c4
0x180011975  mov     rax, [rax]
0x180011978  call    cs:__guard_dispatch_icall_fptr
0x18001197e  mov     edi, eax
0x180011980  test    eax, eax
0x180011982  js      loc_180011A84
0x180011988  mov     rcx, [rbp+var_30]
0x18001198c  mov     rax, [rcx]
0x18001198f  lea     rdx, qword_180056590
0x180011996  mov     rax, [rax+18h]
0x18001199a  call    cs:__guard_dispatch_icall_fptr
0x1800119a0  mov     edi, eax
0x1800119a2  test    eax, eax
0x1800119a4  js      loc_180011A84
0x1800119aa  lfence
0x1800119ad  lea     r8, aUserMarksToolA; "User Marks Tool added to package."
0x1800119b4  lea     rdx, aDAWork1SSource_12; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800119bb  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x1800119c2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800119c7  mov     rcx, [rsi]
0x1800119ca  mov     rax, [rcx]
0x1800119cd  lea     rdx, [rbp+var_14]
0x1800119d1  mov     rax, [rax+38h]
0x1800119d5  call    cs:__guard_dispatch_icall_fptr
0x1800119db  mov     edi, eax
0x1800119dd  test    eax, eax
0x1800119df  js      loc_180011A84
0x1800119e5  cmp     [rbp+var_14], 2
0x1800119e9  jnz     loc_180011ADB
0x1800119ef  xorps   xmm0, xmm0
0x1800119f2  movups  [rbp+var_40], xmm0
0x1800119f6  lea     rcx, aDiagnosticshub_8; "DiagnosticsHub.Counters.UserMarks"
0x1800119fd  call    cs:__imp_SysAllocString
0x180011a03  mov     [rbp+bstrString], rax
0x180011a07  test    rax, rax
0x180011a0a  jz      loc_180011B4B
0x180011a10  mov     [rbp+psa], 0
0x180011a18  mov     r8d, 1
0x180011a1e  lea     rdx, [rbp+bstrString]
0x180011a22  lea     rcx, [rbp+psa]
0x180011a26  call    ?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)
0x180011a2b  mov     edi, eax
0x180011a2d  mov     rbx, [rbp+psa]
0x180011a31  test    eax, eax
0x180011a33  js      short loc_180011A5D
0x180011a35  mov     qword ptr [rbp+var_40+8], rbx
0x180011a39  mov     rcx, [rbp+var_20]
0x180011a3d  mov     rax, [rcx]
0x180011a40  lea     r9, [rbp+var_40]
0x180011a44  mov     edx, 4
0x180011a49  lea     r8d, [rdx+0Ch]
0x180011a4d  mov     rax, [rax+18h]
0x180011a51  call    cs:__guard_dispatch_icall_fptr
0x180011a57  mov     edi, eax
0x180011a59  test    eax, eax
0x180011a5b  jns     short loc_180011AB4
0x180011a5d  test    rbx, rbx
0x180011a60  jz      short loc_180011A79
0x180011a62  mov     rcx, rbx; psa
0x180011a65  call    cs:__imp_SafeArrayUnlock
0x180011a6b  test    eax, eax
0x180011a6d  js      short loc_180011A79
0x180011a6f  mov     rcx, rbx; psa
0x180011a72  call    cs:__imp_SafeArrayDestroy
0x180011a78  nop
0x180011a79  mov     rcx, [rbp+bstrString]; bstrString
0x180011a7d  call    cs:__imp_SysFreeString
0x180011a83  nop
0x180011a84  mov     rcx, [rbp+var_30]
0x180011a88  test    rcx, rcx
0x180011a8b  jz      short loc_180011A9B
0x180011a8d  mov     rax, [rcx]
0x180011a90  mov     rax, [rax+10h]
0x180011a94  call    cs:__guard_dispatch_icall_fptr
0x180011a9a  nop
0x180011a9b  mov     rcx, [rbp+var_28]
0x180011a9f  test    rcx, rcx
0x180011aa2  jz      short loc_180011AB2
0x180011aa4  mov     rax, [rcx]
0x180011aa7  mov     rax, [rax+10h]
0x180011aab  call    cs:__guard_dispatch_icall_fptr
0x180011ab1  nop
0x180011ab2  jmp     short loc_180011B0B
0x180011ab4  test    rbx, rbx
0x180011ab7  jz      short loc_180011AD0
0x180011ab9  mov     rcx, rbx; psa
0x180011abc  call    cs:__imp_SafeArrayUnlock
0x180011ac2  test    eax, eax
0x180011ac4  js      short loc_180011AD0
0x180011ac6  mov     rcx, rbx; psa
0x180011ac9  call    cs:__imp_SafeArrayDestroy
0x180011acf  nop
0x180011ad0  mov     rcx, [rbp+bstrString]; bstrString
0x180011ad4  call    cs:__imp_SysFreeString
0x180011ada  nop
0x180011adb  mov     rcx, [rbp+var_30]
0x180011adf  test    rcx, rcx
0x180011ae2  jz      short loc_180011AF2
0x180011ae4  mov     rax, [rcx]
0x180011ae7  mov     rax, [rax+10h]
0x180011aeb  call    cs:__guard_dispatch_icall_fptr
0x180011af1  nop
0x180011af2  mov     rcx, [rbp+var_28]
0x180011af6  test    rcx, rcx
0x180011af9  jz      short loc_180011B09
0x180011afb  mov     rax, [rcx]
0x180011afe  mov     rax, [rax+10h]
0x180011b02  call    cs:__guard_dispatch_icall_fptr
0x180011b08  nop
0x180011b09  xor     edi, edi
0x180011b0b  lfence
0x180011b0e  mov     rcx, [rbp+var_20]
0x180011b12  test    rcx, rcx
0x180011b15  jz      short loc_180011B25
0x180011b17  mov     rdx, [rcx]
0x180011b1a  mov     rax, [rdx+10h]
0x180011b1e  call    cs:__guard_dispatch_icall_fptr
0x180011b24  nop
0x180011b25  mov     eax, edi
0x180011b27  mov     rcx, [rbp+var_10]
0x180011b2b  xor     rcx, rsp; StackCookie
0x180011b2e  call    __security_check_cookie
0x180011b33  lea     r11, [rsp+80h+var_s0]
0x180011b3b  mov     rbx, [r11+30h]
0x180011b3f  mov     rsi, [r11+38h]
0x180011b43  mov     rsp, r11
0x180011b46  pop     r14
0x180011b48  pop     rdi
0x180011b49  pop     rbp
0x180011b4a  retn
0x180011b4b  mov     ecx, 8007000Eh; int
0x180011b50  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
