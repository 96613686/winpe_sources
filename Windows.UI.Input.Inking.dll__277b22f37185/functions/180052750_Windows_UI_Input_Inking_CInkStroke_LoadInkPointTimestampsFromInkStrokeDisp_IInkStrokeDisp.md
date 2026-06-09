# Windows::UI::Input::Inking::CInkStroke::LoadInkPointTimestampsFromInkStrokeDisp(IInkStrokeDisp *)

- ea: `0x180052750`
- end: `0x1800529f7`
- name: `?LoadInkPointTimestampsFromInkStrokeDisp@CInkStroke@Inking@Input@UI@Windows@@UEAAJPEAUIInkStrokeDisp@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStroke *__hidden this, struct IInkStrokeDisp *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800101bc`
- `0x18001043c`
- `0x180052750`
- `0x180055e24`
- `0x180061790`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800529e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800529e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800527b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005280f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800527b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005280f`
- `OLEAUT32!__imp_SysFreeString` at `0x180052946`
- `OLEAUT32!__imp_SysFreeString` at `0x1800529c1`
- `OLEAUT32!__imp_SysFreeString` at `0x180052946`
- `OLEAUT32!__imp_SysFreeString` at `0x1800529c1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800528e2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800528e2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800528cb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800528cb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005289d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005289d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005293b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005293b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::LoadInkPointTimestampsFromInkStrokeDisp(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2)
{
  struct IInkStrokeDispVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_ExtendedProperties)(IInkStrokeDisp *, IInkExtendedProperties **); // rbx
  HRESULT v6; // edi
  OLECHAR *v7; // r14
  SAFEARRAY *v8; // r15
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, SAFEARRAY **, __int64 *); // rbx
  _QWORD *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // ecx
  unsigned int v15; // r9d
  __int64 v16; // rbx
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  void *ppvData; // [rsp+28h] [rbp-38h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-30h] BYREF
  SAFEARRAY *psa[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h]
  __int16 v23; // [rsp+A0h] [rbp+40h] BYREF
  LONG plLbound; // [rsp+A8h] [rbp+48h] BYREF
  LONG plUbound; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+58h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 280);
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  get_ExtendedProperties = lpVtbl->get_ExtendedProperties;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v6 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))get_ExtendedProperties)(a2, &v26);
  if ( v6 >= 0 )
  {
    v7 = SysAllocString(L"{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}");
    if ( v7 )
    {
      v23 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int16 *))(*(_QWORD *)v26 + 104LL))(v26, v7, &v23);
      if ( v6 < 0 || v23 != -1 )
        goto LABEL_26;
      *(_OWORD *)psa = 0;
      LOWORD(psa[0]) = 8;
      psa[1] = (SAFEARRAY *)SysAllocString(L"{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}");
      v8 = psa[1];
      if ( !psa[1] )
      {
        v6 = -2147024882;
        goto LABEL_26;
      }
      v9 = v26;
      v18 = 0;
      v10 = *(__int64 (__fastcall **)(__int64, SAFEARRAY **, __int64 *))(*(_QWORD *)v26 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      v22 = 0;
      v6 = v10(v9, psa, &v18);
      if ( v6 >= 0 )
      {
        v22 = 0;
        *(_OWORD *)psa = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY **))(*(_QWORD *)v18 + 64LL))(v18, psa);
        if ( v6 >= 0 )
        {
          ppvData = 0;
          v6 = SafeArrayAccessData(psa[1], &ppvData);
          if ( v6 >= 0 )
          {
            plLbound = 0;
            plUbound = 0;
            v6 = -2147418113;
            if ( SafeArrayGetLBound(psa[1], 1u, &plLbound) >= 0
              && SafeArrayGetUBound(psa[1], 1u, &plUbound) >= 0
              && plLbound <= plUbound )
            {
              v11 = ppvData;
              v12 = *(_QWORD *)ppvData;
              if ( *(_QWORD *)ppvData )
              {
                if ( plUbound - plLbound + 1 == v12 + 1 )
                {
                  *((_BYTE *)this + 148) = 1;
                  if ( v12 == 1 )
                  {
                    *((_BYTE *)this + 149) = 1;
                    *((_QWORD *)this + 19) = v11[1];
                    Windows::UI::Input::Inking::CInkStroke::UpdateInkPointTimestampsWithLowerBound(this);
                  }
                  else
                  {
                    v13 = *((_QWORD *)this + 31);
                    plLbound = 0;
                    v6 = (*(__int64 (__fastcall **)(__int64, LONG *))(*(_QWORD *)v13 + 56LL))(v13, &plLbound);
                    if ( v6 < 0 )
                      goto LABEL_17;
                    v14 = plLbound;
                    if ( plLbound != v12 )
                    {
                      v6 = -2147418113;
                      goto LABEL_17;
                    }
                    v15 = 0;
                    while ( v15 < v14 )
                    {
                      v16 = v15 + 1;
                      v6 = InkPointHelper::SetInkPointTimestampAtIndex(
                             v15,
                             *((_QWORD *)this + 31),
                             *((_QWORD *)ppvData + v16));
                      v15 = v16;
                      if ( v6 < 0 )
                        goto LABEL_17;
                      v14 = plLbound;
                    }
                  }
                  v6 = SafeArrayUnaccessData(psa[1]);
                }
              }
            }
          }
        }
      }
LABEL_17:
      SysFreeString(&v8->cDims);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
LABEL_26:
      SysFreeString(v7);
      goto LABEL_28;
    }
    v6 = -2147024882;
  }
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180052750  push    rbp
0x180052752  push    rbx
0x180052753  push    rsi
0x180052754  push    rdi
0x180052755  push    r13
0x180052757  push    r14
0x180052759  push    r15
0x18005275b  mov     rbp, rsp
0x18005275e  sub     rsp, 60h
0x180052762  mov     rdi, rdx
0x180052765  mov     rsi, rcx
0x180052768  lea     rdx, [rcx+118h]
0x18005276f  lea     rcx, [rbp+SRWLock]
0x180052773  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180052778  mov     rax, [rdi]
0x18005277b  lea     rcx, [rbp+arg_18]
0x18005277f  mov     [rbp+arg_18], 0
0x180052787  mov     rbx, [rax+60h]
0x18005278b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052790  lea     rdx, [rbp+arg_18]
0x180052794  mov     rcx, rdi
0x180052797  mov     rax, rbx
0x18005279a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005279f  mov     edi, eax
0x1800527a1  test    eax, eax
0x1800527a3  js      loc_1800529CE
0x1800527a9  lea     rcx, a65d6c92fE2f04d; "{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}"
0x1800527b0  call    cs:__imp_SysAllocString
0x1800527b6  mov     r14, rax
0x1800527b9  test    rax, rax
0x1800527bc  jz      loc_1800529C9
0x1800527c2  xor     ecx, ecx
0x1800527c4  lea     r8, [rbp+arg_0]
0x1800527c8  mov     [rbp+arg_0], cx
0x1800527cc  mov     rcx, [rbp+arg_18]
0x1800527d0  mov     rdx, [rcx]
0x1800527d3  mov     rax, [rdx+68h]
0x1800527d7  mov     rdx, r14
0x1800527da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527df  mov     edi, eax
0x1800527e1  test    eax, eax
0x1800527e3  js      loc_1800529BE
0x1800527e9  or      eax, 0FFFFFFFFh
0x1800527ec  cmp     ax, [rbp+arg_0]
0x1800527f0  jnz     loc_1800529BE
0x1800527f6  xorps   xmm0, xmm0
0x1800527f9  lea     rcx, a65d6c92fE2f04d; "{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}"
0x180052800  movups  xmmword ptr [rbp+psa], xmm0
0x180052804  xor     r13d, r13d
0x180052807  lea     eax, [r13+8]
0x18005280b  mov     word ptr [rbp+psa], ax
0x18005280f  call    cs:__imp_SysAllocString
0x180052815  mov     [rbp+psa+8], rax
0x180052819  mov     r15, rax
0x18005281c  test    rax, rax
0x18005281f  jz      loc_1800529B9
0x180052825  mov     rdi, [rbp+arg_18]
0x180052829  lea     rcx, [rbp+var_40]
0x18005282d  mov     [rbp+var_40], r13
0x180052831  mov     rax, [rdi]
0x180052834  mov     rbx, [rax+48h]
0x180052838  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005283d  movups  xmm0, xmmword ptr [rbp+psa]
0x180052841  lea     r8, [rbp+var_40]
0x180052845  mov     [rbp+var_10], r13
0x180052849  lea     rdx, [rbp+psa]
0x18005284d  mov     rcx, rdi
0x180052850  mov     rax, rbx
0x180052853  movaps  xmmword ptr [rbp+psa], xmm0
0x180052857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005285c  mov     edi, eax
0x18005285e  test    eax, eax
0x180052860  js      loc_180052943
0x180052866  mov     rcx, [rbp+var_40]
0x18005286a  lea     rdx, [rbp+psa]
0x18005286e  xor     eax, eax
0x180052870  xorps   xmm0, xmm0
0x180052873  mov     [rbp+var_10], rax
0x180052877  movups  xmmword ptr [rbp+psa], xmm0
0x18005287b  mov     rax, [rcx]
0x18005287e  mov     rax, [rax+40h]
0x180052882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052887  mov     edi, eax
0x180052889  test    eax, eax
0x18005288b  js      loc_180052943
0x180052891  mov     rcx, [rbp+psa+8]; psa
0x180052895  lea     rdx, [rbp+ppvData]; ppvData
0x180052899  mov     [rbp+ppvData], r13
0x18005289d  call    cs:__imp_SafeArrayAccessData
0x1800528a3  mov     edi, eax
0x1800528a5  test    eax, eax
0x1800528a7  js      loc_180052943
0x1800528ad  mov     rcx, [rbp+psa+8]; psa
0x1800528b1  lea     r8, [rbp+plLbound]; plLbound
0x1800528b5  mov     [rbp+plLbound], r13d
0x1800528b9  mov     edx, 1; nDim
0x1800528be  mov     [rbp+plUbound], r13d
0x1800528c2  mov     r13d, 8000FFFFh
0x1800528c8  mov     edi, r13d
0x1800528cb  call    cs:__imp_SafeArrayGetLBound
0x1800528d1  test    eax, eax
0x1800528d3  js      short loc_180052943
0x1800528d5  mov     rcx, [rbp+psa+8]; psa
0x1800528d9  lea     r8, [rbp+plUbound]; plUbound
0x1800528dd  mov     edx, 1; nDim
0x1800528e2  call    cs:__imp_SafeArrayGetUBound
0x1800528e8  test    eax, eax
0x1800528ea  js      short loc_180052943
0x1800528ec  mov     eax, [rbp+plUbound]
0x1800528ef  cmp     [rbp+plLbound], eax
0x1800528f2  jg      short loc_180052943
0x1800528f4  mov     rdx, [rbp+ppvData]
0x1800528f8  mov     rbx, [rdx]
0x1800528fb  test    rbx, rbx
0x1800528fe  jz      short loc_180052943
0x180052900  sub     eax, [rbp+plLbound]
0x180052903  inc     eax
0x180052905  movsxd  rcx, eax
0x180052908  lea     rax, [rbx+1]
0x18005290c  cmp     rcx, rax
0x18005290f  jnz     short loc_180052943
0x180052911  mov     byte ptr [rsi+94h], 1
0x180052918  cmp     rbx, 1
0x18005291c  jnz     short loc_180052957
0x18005291e  mov     [rsi+95h], bl
0x180052924  mov     rcx, rsi; this
0x180052927  mov     rax, [rdx+8]
0x18005292b  mov     [rsi+98h], rax
0x180052932  call    ?UpdateInkPointTimestampsWithLowerBound@CInkStroke@Inking@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Inking::CInkStroke::UpdateInkPointTimestampsWithLowerBound(void)
0x180052937  mov     rcx, [rbp+psa+8]; psa
0x18005293b  call    cs:__imp_SafeArrayUnaccessData
0x180052941  mov     edi, eax
0x180052943  mov     rcx, r15; bstrString
0x180052946  call    cs:__imp_SysFreeString
0x18005294c  lea     rcx, [rbp+var_40]
0x180052950  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052955  jmp     short loc_1800529BE
0x180052957  mov     rcx, [rsi+0F8h]
0x18005295e  lea     rdx, [rbp+plLbound]
0x180052962  mov     [rbp+plLbound], 0
0x180052969  mov     rax, [rcx]
0x18005296c  mov     rax, [rax+38h]
0x180052970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052975  mov     edi, eax
0x180052977  test    eax, eax
0x180052979  js      short loc_180052943
0x18005297b  mov     ecx, [rbp+plLbound]
0x18005297e  cmp     rcx, rbx
0x180052981  jz      short loc_180052988
0x180052983  mov     edi, r13d
0x180052986  jmp     short loc_180052943
0x180052988  xor     r9d, r9d
0x18005298b  cmp     r9d, ecx
0x18005298e  jnb     short loc_180052937
0x180052990  mov     r8, [rbp+ppvData]
0x180052994  lea     ebx, [r9+1]
0x180052998  mov     rdx, [rsi+0F8h]
0x18005299f  mov     ecx, r9d
0x1800529a2  mov     r8, [r8+rbx*8]
0x1800529a6  call    ?SetInkPointTimestampAtIndex@InkPointHelper@@SAJIPEAU?$IVector@PEAVInkPoint@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@_K@Z; InkPointHelper::SetInkPointTimestampAtIndex(uint,Windows::Foundation::Collections::IVector<Windows::UI::Input::Inking::InkPoint *> *,unsigned __int64)
0x1800529ab  mov     edi, eax
0x1800529ad  mov     r9d, ebx
0x1800529b0  test    eax, eax
0x1800529b2  js      short loc_180052943
0x1800529b4  mov     ecx, [rbp+plLbound]
0x1800529b7  jmp     short loc_18005298B
0x1800529b9  mov     edi, 8007000Eh
0x1800529be  mov     rcx, r14; bstrString
0x1800529c1  call    cs:__imp_SysFreeString
0x1800529c7  jmp     short loc_1800529CE
0x1800529c9  mov     edi, 8007000Eh
0x1800529ce  lea     rcx, [rbp+arg_18]
0x1800529d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800529d7  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800529db  test    rcx, rcx
0x1800529de  jz      short loc_1800529E6
0x1800529e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800529e6  mov     eax, edi
0x1800529e8  add     rsp, 60h
0x1800529ec  pop     r15
0x1800529ee  pop     r14
0x1800529f0  pop     r13
0x1800529f2  pop     rdi
0x1800529f3  pop     rsi
0x1800529f4  pop     rbx
0x1800529f5  pop     rbp
0x1800529f6  retn
```
