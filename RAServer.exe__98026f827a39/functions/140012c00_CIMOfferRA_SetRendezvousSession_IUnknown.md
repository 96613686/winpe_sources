# CIMOfferRA::SetRendezvousSession(IUnknown *)

- ea: `0x140012c00`
- end: `0x140012e60`
- name: `?SetRendezvousSession@CIMOfferRA@@UEAAJPEAUIUnknown@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(CIMOfferRA *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001f58`
- `0x1400035c8`
- `0x140012c00`
- `0x140012f10`
- `0x140015240`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140012e22`
- `OLEAUT32!__imp_SysFreeString` at `0x140012e2a`
- `OLEAUT32!__imp_SysFreeString` at `0x140012e32`
- `OLEAUT32!__imp_SysFreeString` at `0x140012e22`
- `OLEAUT32!__imp_SysFreeString` at `0x140012e2a`
- `OLEAUT32!__imp_SysFreeString` at `0x140012e32`

## string_xrefs

- `0x140012e0f`: `base\diagnosis\ra\dcom\src\raimoffer.cpp`

## pseudocode

```c
__int64 __fastcall CIMOfferRA::SetRendezvousSession(CIMOfferRA *this, struct IUnknown *a2)
{
  char *v4; // rax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  char *v7; // rbx
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // ebx
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  signed int v15; // eax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  _QWORD *v18; // r14
  signed int v19; // eax
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  __int64 v22; // rcx
  signed int v23; // eax
  const struct _EVENT_DESCRIPTOR *v24; // rdx
  CEventLogger *v25; // rcx
  signed int v26; // eax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  __int64 v30; // [rsp+30h] [rbp-10h] BYREF
  int v31; // [rsp+70h] [rbp+30h] BYREF
  struct IConnectionPoint *v32; // [rsp+80h] [rbp+40h] BYREF
  __int64 v33; // [rsp+88h] [rbp+48h] BYREF

  v33 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 8) = 0;
    *(_QWORD *)v4 = &CIMOfferRAEvent::`vftable';
    *(GUID *)(v4 + 36) = GUID_3fa19cf8_64c4_4f53_ae60_635b3806eca6;
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 1) = this;
    (*(void (__fastcall **)(CIMOfferRA *))(*(_QWORD *)this + 8LL))(this);
    *((_DWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 3) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 2) = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    if ( a2 )
    {
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
             &v33);
      v11 = v8;
      if ( v8 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IConnectionPoint **))(*(_QWORD *)v33 + 32LL))(
                v33,
                &DIID_DRendezvousSessionEvents,
                &v32);
        v11 = v12;
        if ( v12 >= 0 )
        {
          v15 = CIMOfferRAEvent::Advise(*((CIMOfferRAEvent **)this + 2), v32);
          v11 = v15;
          if ( v15 >= 0 )
          {
            v18 = (_QWORD *)((char *)this + 24);
            v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
                    a2,
                    &GUID_9ba4b1dd_8b0c_48b7_9e7c_2f25857c8df5,
                    (char *)this + 24);
            v11 = v19;
            if ( v19 >= 0 )
            {
              v22 = *v18;
              if ( *v18 )
              {
                v31 = 0;
                v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 40LL))(v22, &v31);
                v11 = v23;
                if ( v23 >= 0 )
                {
                  if ( (v31 & 1) != 0 )
                    *((_DWORD *)this + 10) = 1;
                  if ( (v31 & 2) != 0 )
                    *((_DWORD *)this + 11) = 1;
                  v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v18 + 32LL))(*v18, (char *)this + 48);
                  v11 = v26;
                  if ( v26 < 0 )
                    CEventLogger::LogError(
                      v28,
                      v27,
                      L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
                      0x142u,
                      L"CIMOfferRA::SetRendezvousSession",
                      v26);
                }
                else
                {
                  CEventLogger::LogError(
                    v25,
                    v24,
                    L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
                    0x11Du,
                    L"CIMOfferRA::SetRendezvousSession",
                    v23);
                }
              }
              else
              {
                v11 = -2147467259;
                CEventLogger::LogError(
                  0,
                  v20,
                  L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
                  0x110u,
                  L"CIMOfferRA::SetRendezvousSession",
                  0x80004005);
              }
            }
            else
            {
              CEventLogger::LogError(
                v21,
                v20,
                L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
                0x108u,
                L"CIMOfferRA::SetRendezvousSession",
                v19);
            }
          }
          else
          {
            CEventLogger::LogError(
              v17,
              v16,
              L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
              0xF3u,
              L"CIMOfferRA::SetRendezvousSession",
              v15);
          }
        }
        else
        {
          CEventLogger::LogError(
            v14,
            v13,
            L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
            0xEBu,
            L"CIMOfferRA::SetRendezvousSession",
            v12);
        }
      }
      else
      {
        CEventLogger::LogError(
          v10,
          v9,
          L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
          0xE4u,
          L"CIMOfferRA::SetRendezvousSession",
          v8);
      }
    }
    else
    {
      v11 = -2147467261;
    }
  }
  else
  {
    v11 = -2147024882;
    CEventLogger::LogError(
      v6,
      v5,
      L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
      0xD4u,
      L"CIMOfferRA::SetRendezvousSession",
      0x8007000E);
  }
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  return v11;
}

```

## disassembly

```asm
0x140012c00  push    rbp
0x140012c02  push    rbx
0x140012c03  push    rsi
0x140012c04  push    rdi
0x140012c05  push    r14
0x140012c07  mov     rbp, rsp
0x140012c0a  sub     rsp, 40h
0x140012c0e  mov     rsi, rdx
0x140012c11  mov     [rbp+arg_18], 0
0x140012c19  mov     rdi, rcx
0x140012c1c  mov     [rbp+arg_10], 0
0x140012c24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012c2b  mov     [rbp+var_10], 0
0x140012c33  mov     ecx, 40h ; '@'; unsigned __int64
0x140012c38  mov     [rbp+arg_0], 0
0x140012c3f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140012c44  mov     rbx, rax
0x140012c47  test    rax, rax
0x140012c4a  jz      short loc_140012C95
0x140012c4c  movups  xmm0, xmmword ptr cs:_GUID_3fa19cf8_64c4_4f53_ae60_635b3806eca6.Data1
0x140012c53  mov     dword ptr [rbx+20h], 0
0x140012c5a  lea     rax, ??_7CIMOfferRAEvent@@6B@; const CIMOfferRAEvent::`vftable'
0x140012c61  mov     [rbx], rax
0x140012c64  mov     rcx, rdi
0x140012c67  movdqu  xmmword ptr [rbx+24h], xmm0
0x140012c6c  mov     qword ptr [rbx+38h], 0
0x140012c74  mov     [rbx+8], rdi
0x140012c78  mov     rax, [rdi]
0x140012c7b  mov     rax, [rax+8]
0x140012c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c84  mov     dword ptr [rbx+10h], 0
0x140012c8b  mov     qword ptr [rbx+18h], 0
0x140012c93  jmp     short loc_140012C97
0x140012c95  xor     ebx, ebx
0x140012c97  mov     [rdi+10h], rbx
0x140012c9b  test    rbx, rbx
0x140012c9e  jz      loc_140012DF5
0x140012ca4  mov     rax, [rbx]
0x140012ca7  mov     rcx, rbx
0x140012caa  mov     rax, [rax+8]
0x140012cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cb3  test    rsi, rsi
0x140012cb6  jz      loc_140012DEE
0x140012cbc  mov     rax, [rsi]
0x140012cbf  lea     r8, [rbp+arg_18]
0x140012cc3  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x140012cca  mov     rcx, rsi
0x140012ccd  mov     rax, [rax]
0x140012cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cd5  mov     ebx, eax
0x140012cd7  test    eax, eax
0x140012cd9  jns     short loc_140012CEA
0x140012cdb  mov     [rsp+40h+var_18], eax
0x140012cdf  mov     r9d, 0E4h
0x140012ce5  jmp     loc_140012E08
0x140012cea  mov     rcx, [rbp+arg_18]
0x140012cee  lea     r8, [rbp+arg_10]
0x140012cf2  lea     rdx, DIID_DRendezvousSessionEvents
0x140012cf9  mov     rax, [rcx]
0x140012cfc  mov     rax, [rax+20h]
0x140012d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d05  mov     ebx, eax
0x140012d07  test    eax, eax
0x140012d09  jns     short loc_140012D1A
0x140012d0b  mov     [rsp+40h+var_18], eax
0x140012d0f  mov     r9d, 0EBh
0x140012d15  jmp     loc_140012E08
0x140012d1a  mov     rdx, [rbp+arg_10]; struct IConnectionPoint *
0x140012d1e  mov     rcx, [rdi+10h]; this
0x140012d22  call    ?Advise@CIMOfferRAEvent@@QEAAJPEAUIConnectionPoint@@@Z; CIMOfferRAEvent::Advise(IConnectionPoint *)
0x140012d27  mov     ebx, eax
0x140012d29  test    eax, eax
0x140012d2b  jns     short loc_140012D3C
0x140012d2d  mov     [rsp+40h+var_18], eax
0x140012d31  mov     r9d, 0F3h
0x140012d37  jmp     loc_140012E08
0x140012d3c  mov     rax, [rsi]
0x140012d3f  lea     r14, [rdi+18h]
0x140012d43  mov     r8, r14
0x140012d46  lea     rdx, _GUID_9ba4b1dd_8b0c_48b7_9e7c_2f25857c8df5
0x140012d4d  mov     rcx, rsi
0x140012d50  mov     rax, [rax]
0x140012d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d58  mov     ebx, eax
0x140012d5a  test    eax, eax
0x140012d5c  jns     short loc_140012D6D
0x140012d5e  mov     [rsp+40h+var_18], eax
0x140012d62  mov     r9d, 108h
0x140012d68  jmp     loc_140012E08
0x140012d6d  mov     rcx, [r14]
0x140012d70  test    rcx, rcx
0x140012d73  jnz     short loc_140012D8A
0x140012d75  mov     ebx, 80004005h
0x140012d7a  mov     [rsp+40h+var_18], 80004005h
0x140012d82  mov     r9d, 110h
0x140012d88  jmp     short loc_140012E08
0x140012d8a  mov     [rbp+arg_0], 0
0x140012d91  lea     rdx, [rbp+arg_0]
0x140012d95  mov     rax, [rcx]
0x140012d98  mov     rax, [rax+28h]
0x140012d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012da1  mov     ebx, eax
0x140012da3  test    eax, eax
0x140012da5  jns     short loc_140012DB3
0x140012da7  mov     [rsp+40h+var_18], eax
0x140012dab  mov     r9d, 11Dh
0x140012db1  jmp     short loc_140012E08
0x140012db3  mov     eax, 1
0x140012db8  test    byte ptr [rbp+arg_0], al
0x140012dbb  jz      short loc_140012DC0
0x140012dbd  mov     [rdi+28h], eax
0x140012dc0  test    byte ptr [rbp+arg_0], 2
0x140012dc4  jz      short loc_140012DC9
0x140012dc6  mov     [rdi+2Ch], eax
0x140012dc9  mov     rcx, [r14]
0x140012dcc  lea     rdx, [rdi+30h]
0x140012dd0  mov     rax, [rcx]
0x140012dd3  mov     rax, [rax+20h]
0x140012dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ddc  mov     ebx, eax
0x140012dde  test    eax, eax
0x140012de0  jns     short loc_140012E20
0x140012de2  mov     [rsp+40h+var_18], eax
0x140012de6  mov     r9d, 142h
0x140012dec  jmp     short loc_140012E08
0x140012dee  mov     ebx, 80004003h
0x140012df3  jmp     short loc_140012E20
0x140012df5  mov     ebx, 8007000Eh
0x140012dfa  mov     [rsp+40h+var_18], 8007000Eh; unsigned int
0x140012e02  mov     r9d, 0D4h; unsigned int
0x140012e08  lea     rax, aCimofferraSetr; "CIMOfferRA::SetRendezvousSession"
0x140012e0f  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x140012e16  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x140012e1b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140012e20  xor     ecx, ecx; bstrString
0x140012e22  call    cs:__imp_SysFreeString
0x140012e28  xor     ecx, ecx; bstrString
0x140012e2a  call    cs:__imp_SysFreeString
0x140012e30  xor     ecx, ecx; bstrString
0x140012e32  call    cs:__imp_SysFreeString
0x140012e38  lea     rcx, [rbp+var_10]
0x140012e3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e41  lea     rcx, [rbp+arg_10]
0x140012e45  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e4a  lea     rcx, [rbp+arg_18]
0x140012e4e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e53  mov     eax, ebx
0x140012e55  add     rsp, 40h
0x140012e59  pop     r14
0x140012e5b  pop     rdi
0x140012e5c  pop     rsi
0x140012e5d  pop     rbx
0x140012e5e  pop     rbp
0x140012e5f  retn
```
