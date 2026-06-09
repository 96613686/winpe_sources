# s_CreateChildShape

- ea: `0x180038bc0`
- end: `0x180038ea4`
- name: `s_CreateChildShape`
- size: `740`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032a8c`
- `0x1800335dc`
- `0x180033838`
- `0x180033cfc`
- `0x180038848`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x180038bc0`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180038dcb`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180038dcb`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180038caa`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180038caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall s_CreateChildShape(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // ebx
  unsigned int v5; // edi
  int v7; // [rsp+40h] [rbp-29h] BYREF
  __int64 v8; // [rsp+48h] [rbp-21h] BYREF
  __int64 v9; // [rsp+50h] [rbp-19h] BYREF
  void *ppv; // [rsp+58h] [rbp-11h] BYREF
  __int64 v11; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+68h] [rbp-1h] BYREF
  __int64 v13; // [rsp+70h] [rbp+7h] BYREF
  __int128 v14; // [rsp+78h] [rbp+Fh] BYREF
  int v15; // [rsp+88h] [rbp+1Fh]
  __int128 v16; // [rsp+90h] [rbp+27h] BYREF
  int v17; // [rsp+A0h] [rbp+37h]

  *a2 = 0;
  v16 = 0;
  v17 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v8);
  if ( (*(int (__fastcall **)(__int64, __int128 *, GUID *, __int64 *))(*(_QWORD *)a1 + 56LL))(
         a1,
         &v16,
         &GUID_6bc63938_8254_4965_9680_565933185060,
         &v8) < 0 )
  {
    v4 = 0;
    *a2 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  else
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v9);
    v4 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v8 + 24LL))(
           v8,
           &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
           &v9);
    if ( v4 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, const PROPERTYKEY *))(*(_QWORD *)v9 + 56LL))(v9, &PKEY_ParsingPath) )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v11);
        v4 = PSCreatePropertyKeyStore(&PKEY_ParsingPath, 1, &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b, &v11);
        if ( v4 >= 0 )
        {
          v7 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v7);
          v5 = 0;
          if ( v7 <= 0 )
          {
LABEL_11:
            if ( v4 >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
              v4 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v8 + 32LL))(
                     v8,
                     &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                     &v13);
              if ( v4 >= 0 )
              {
                ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v12);
                if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8)
                  || (v4 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v8 + 80LL))(
                             v8,
                             &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
                             &v12),
                      v4 >= 0) )
                {
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
                  v4 = SHCoCreateInstance(0, &CLSID_ResultShape, 0, &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94, &ppv);
                  if ( v4 >= 0 )
                  {
                    v4 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, const PROPERTYKEY *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                           ppv,
                           v11,
                           v13,
                           v12,
                           &PKEY_Null,
                           0,
                           0);
                    if ( v4 >= 0 )
                      v4 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(
                             ppv,
                             &GUID_6bc63938_8254_4965_9680_565933185060,
                             a2);
                  }
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
                }
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v12);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
            }
          }
          else
          {
            while ( v4 >= 0 )
            {
              v14 = 0;
              v15 = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v9 + 32LL))(v9, v5, &v14);
              if ( v4 >= 0 )
                v4 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 40LL))(v11, &v14);
              if ( (int)++v5 >= v7 )
                goto LABEL_11;
            }
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v11);
      }
      else
      {
        *a2 = ATL::CComPtrBase<IScope>::Detach(&v8);
      }
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v9);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038bc0  mov     [rsp-8+arg_10], rbx
0x180038bc5  push    rbp
0x180038bc6  push    rsi
0x180038bc7  push    rdi
0x180038bc8  lea     rbp, [rsp-47h]
0x180038bcd  sub     rsp, 0B0h
0x180038bd4  mov     rax, cs:__security_cookie
0x180038bdb  xor     rax, rsp
0x180038bde  mov     [rbp+57h+var_18], rax
0x180038be2  mov     rsi, rdx
0x180038be5  mov     rdi, rcx
0x180038be8  mov     qword ptr [rdx], 0
0x180038bef  xorps   xmm0, xmm0
0x180038bf2  xor     eax, eax
0x180038bf4  movups  [rbp+57h+var_30], xmm0
0x180038bf8  mov     [rbp+57h+var_20], eax
0x180038bfb  lea     rcx, [rbp+57h+var_78]; void *
0x180038bff  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038c04  nop
0x180038c05  mov     rax, [rdi]
0x180038c08  lea     r9, [rbp+57h+var_78]
0x180038c0c  lea     r8, _GUID_6bc63938_8254_4965_9680_565933185060
0x180038c13  lea     rdx, [rbp+57h+var_30]
0x180038c17  mov     rcx, rdi
0x180038c1a  mov     rax, [rax+38h]
0x180038c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c23  test    eax, eax
0x180038c25  js      loc_180038E65
0x180038c2b  lea     rcx, [rbp+57h+var_70]; void *
0x180038c2f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038c34  nop
0x180038c35  mov     rcx, [rbp+57h+var_78]
0x180038c39  mov     rax, [rcx]
0x180038c3c  lea     r8, [rbp+57h+var_70]
0x180038c40  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180038c47  mov     rax, [rax+18h]
0x180038c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c50  mov     ebx, eax
0x180038c52  test    eax, eax
0x180038c54  js      loc_180038E5A
0x180038c5a  mov     r8, [rbp+57h+var_70]
0x180038c5e  mov     rcx, [r8]
0x180038c61  mov     rax, [rcx+38h]
0x180038c65  lea     rdx, PKEY_ParsingPath
0x180038c6c  mov     rcx, r8
0x180038c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c74  test    eax, eax
0x180038c76  jnz     short loc_180038C89
0x180038c78  lea     rcx, [rbp+57h+var_78]
0x180038c7c  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x180038c81  mov     [rsi], rax
0x180038c84  jmp     loc_180038E5A
0x180038c89  lea     rcx, [rbp+57h+var_60]; void *
0x180038c8d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038c92  nop
0x180038c93  lea     r9, [rbp+57h+var_60]
0x180038c97  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180038c9e  mov     edx, 1
0x180038ca3  lea     rcx, PKEY_ParsingPath
0x180038caa  call    cs:__imp_PSCreatePropertyKeyStore
0x180038cb0  mov     ebx, eax
0x180038cb2  test    eax, eax
0x180038cb4  js      loc_180038E50
0x180038cba  mov     [rbp+57h+var_80], 0
0x180038cc1  mov     rcx, [rbp+57h+var_70]
0x180038cc5  mov     rax, [rcx]
0x180038cc8  lea     rdx, [rbp+57h+var_80]
0x180038ccc  mov     rax, [rax+18h]
0x180038cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cd5  mov     ebx, eax
0x180038cd7  xor     edi, edi
0x180038cd9  cmp     [rbp+57h+var_80], edi
0x180038cdc  jle     short loc_180038D2B
0x180038cde  test    ebx, ebx
0x180038ce0  js      loc_180038E50
0x180038ce6  xorps   xmm0, xmm0
0x180038ce9  xor     eax, eax
0x180038ceb  movups  [rbp+57h+var_48], xmm0
0x180038cef  mov     [rbp+57h+var_38], eax
0x180038cf2  mov     rcx, [rbp+57h+var_70]
0x180038cf6  mov     rax, [rcx]
0x180038cf9  lea     r8, [rbp+57h+var_48]
0x180038cfd  mov     edx, edi
0x180038cff  mov     rax, [rax+20h]
0x180038d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d08  mov     ebx, eax
0x180038d0a  test    eax, eax
0x180038d0c  js      short loc_180038D24
0x180038d0e  mov     rcx, [rbp+57h+var_60]
0x180038d12  mov     rax, [rcx]
0x180038d15  lea     rdx, [rbp+57h+var_48]
0x180038d19  mov     rax, [rax+28h]
0x180038d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d22  mov     ebx, eax
0x180038d24  inc     edi
0x180038d26  cmp     edi, [rbp+57h+var_80]
0x180038d29  jl      short loc_180038CDE
0x180038d2b  test    ebx, ebx
0x180038d2d  js      loc_180038E50
0x180038d33  lea     rcx, [rbp+57h+var_50]; void *
0x180038d37  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038d3c  nop
0x180038d3d  mov     rcx, [rbp+57h+var_78]
0x180038d41  mov     rax, [rcx]
0x180038d44  lea     r8, [rbp+57h+var_50]
0x180038d48  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180038d4f  mov     rax, [rax+20h]
0x180038d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d58  mov     ebx, eax
0x180038d5a  test    eax, eax
0x180038d5c  js      loc_180038E46
0x180038d62  lea     rcx, [rbp+57h+var_58]; void *
0x180038d66  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038d6b  nop
0x180038d6c  mov     rcx, [rbp+57h+var_78]
0x180038d70  mov     rax, [rcx]
0x180038d73  mov     rax, [rax+48h]
0x180038d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d7c  test    eax, eax
0x180038d7e  jnz     short loc_180038DA5
0x180038d80  mov     rcx, [rbp+57h+var_78]
0x180038d84  mov     rax, [rcx]
0x180038d87  lea     r8, [rbp+57h+var_58]
0x180038d8b  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x180038d92  mov     rax, [rax+50h]
0x180038d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d9b  mov     ebx, eax
0x180038d9d  test    eax, eax
0x180038d9f  js      loc_180038E3C
0x180038da5  lea     rcx, [rbp+57h+var_68]; void *
0x180038da9  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038dae  nop
0x180038daf  lea     rax, [rbp+57h+var_68]
0x180038db3  mov     [rsp+0C0h+ppv], rax; ppv
0x180038db8  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180038dbf  xor     r8d, r8d; pUnkOuter
0x180038dc2  lea     rdx, CLSID_ResultShape; pclsid
0x180038dc9  xor     ecx, ecx; pszCLSID
0x180038dcb  call    cs:__imp_SHCoCreateInstance
0x180038dd1  mov     ebx, eax
0x180038dd3  test    eax, eax
0x180038dd5  js      short loc_180038E32
0x180038dd7  mov     rcx, [rbp+57h+var_68]
0x180038ddb  mov     rax, [rcx]
0x180038dde  mov     [rsp+0C0h+var_90], 0
0x180038de7  mov     [rsp+0C0h+var_98], 0
0x180038df0  lea     rdx, PKEY_Null
0x180038df7  mov     [rsp+0C0h+ppv], rdx
0x180038dfc  mov     r9, [rbp+57h+var_58]
0x180038e00  mov     r8, [rbp+57h+var_50]
0x180038e04  mov     rdx, [rbp+57h+var_60]
0x180038e08  mov     rax, [rax+18h]
0x180038e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e11  mov     ebx, eax
0x180038e13  test    eax, eax
0x180038e15  js      short loc_180038E32
0x180038e17  mov     rcx, [rbp+57h+var_68]
0x180038e1b  mov     rax, [rcx]
0x180038e1e  mov     r8, rsi
0x180038e21  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180038e28  mov     rax, [rax]
0x180038e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e30  mov     ebx, eax
0x180038e32  lea     rcx, [rbp+57h+var_68]
0x180038e36  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e3b  nop
0x180038e3c  lea     rcx, [rbp+57h+var_58]
0x180038e40  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e45  nop
0x180038e46  lea     rcx, [rbp+57h+var_50]
0x180038e4a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e4f  nop
0x180038e50  lea     rcx, [rbp+57h+var_60]
0x180038e54  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e59  nop
0x180038e5a  lea     rcx, [rbp+57h+var_70]
0x180038e5e  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e63  jmp     short loc_180038E7A
0x180038e65  xor     ebx, ebx
0x180038e67  mov     [rsi], rdi
0x180038e6a  mov     rax, [rdi]
0x180038e6d  mov     rcx, rdi
0x180038e70  mov     rax, [rax+8]
0x180038e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e79  nop
0x180038e7a  lea     rcx, [rbp+57h+var_78]
0x180038e7e  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038e83  mov     eax, ebx
0x180038e85  mov     rcx, [rbp+57h+var_18]
0x180038e89  xor     rcx, rsp; StackCookie
0x180038e8c  call    __security_check_cookie
0x180038e91  mov     rbx, [rsp+0C0h+arg_10]
0x180038e99  add     rsp, 0B0h
0x180038ea0  pop     rdi
0x180038ea1  pop     rsi
0x180038ea2  pop     rbp
0x180038ea3  retn
```
