# CIMRequestRA::SetRendezvousSession(IUnknown *)

- ea: `0x140011530`
- end: `0x140011762`
- name: `?SetRendezvousSession@CIMRequestRA@@UEAAJPEAUIUnknown@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CIMRequestRAEvent **this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001f58`
- `0x1400035c8`
- `0x140011530`
- `0x140011864`
- `0x140011ab0`
- `0x140015240`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011724`
- `OLEAUT32!__imp_SysFreeString` at `0x14001172c`
- `OLEAUT32!__imp_SysFreeString` at `0x140011734`
- `OLEAUT32!__imp_SysFreeString` at `0x140011724`
- `OLEAUT32!__imp_SysFreeString` at `0x14001172c`
- `OLEAUT32!__imp_SysFreeString` at `0x140011734`

## string_xrefs

- `0x140011711`: `base\diagnosis\ra\dcom\src\raimrequest.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRA::SetRendezvousSession(CIMRequestRAEvent **this, struct IUnknown *a2)
{
  CIMRequestRAEvent *v4; // rax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CIMRequestRAEvent *v6; // rcx
  signed int v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // ebx
  signed int v11; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  signed int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  _QWORD *v17; // r14
  signed int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  __int64 v21; // rcx
  signed int v22; // eax
  const struct _EVENT_DESCRIPTOR *v23; // rdx
  CEventLogger *v24; // rcx
  char v25; // al
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
  v4 = (CIMRequestRAEvent *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v6 = CIMRequestRAEvent::CIMRequestRAEvent(v4, (struct CIMRequestRA *)this);
  else
    v6 = 0;
  this[2] = v6;
  if ( v6 )
  {
    (*(void (__fastcall **)(CIMRequestRAEvent *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( a2 )
    {
      v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
             &v33);
      v10 = v7;
      if ( v7 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IConnectionPoint **))(*(_QWORD *)v33 + 32LL))(
                v33,
                &DIID_DRendezvousSessionEvents,
                &v32);
        v10 = v11;
        if ( v11 >= 0 )
        {
          v14 = CIMRequestRAEvent::Advise(this[2], v32);
          v10 = v14;
          if ( v14 >= 0 )
          {
            v17 = this + 3;
            v18 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, CIMRequestRAEvent **))a2->lpVtbl->QueryInterface)(
                    a2,
                    &GUID_9ba4b1dd_8b0c_48b7_9e7c_2f25857c8df5,
                    this + 3);
            v10 = v18;
            if ( v18 >= 0 )
            {
              v21 = *v17;
              if ( *v17 )
              {
                v31 = 0;
                v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 40LL))(v21, &v31);
                v10 = v22;
                if ( v22 >= 0 )
                {
                  v25 = v31;
                  if ( (v31 & 1) != 0 )
                  {
                    *((_DWORD *)this + 10) = 1;
                    if ( (v25 & 8) != 0 )
                      *((_DWORD *)this + 13) = 1;
                  }
                  if ( (v25 & 2) != 0 )
                  {
                    *((_DWORD *)this + 11) = 1;
                    if ( (v25 & 8) != 0 )
                      *((_DWORD *)this + 12) = 1;
                  }
                  v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v17 + 32LL))(*v17, (char *)this + 56);
                  v10 = v26;
                  if ( v26 < 0 )
                    CEventLogger::LogError(
                      v28,
                      v27,
                      L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
                      0x163u,
                      L"CIMRequestRA::SetRendezvousSession",
                      v26);
                }
                else
                {
                  CEventLogger::LogError(
                    v24,
                    v23,
                    L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
                    0x139u,
                    L"CIMRequestRA::SetRendezvousSession",
                    v22);
                }
              }
              else
              {
                v10 = -2147467259;
                CEventLogger::LogError(
                  0,
                  v19,
                  L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
                  0x12Du,
                  L"CIMRequestRA::SetRendezvousSession",
                  0x80004005);
              }
            }
            else
            {
              CEventLogger::LogError(
                v20,
                v19,
                L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
                0x127u,
                L"CIMRequestRA::SetRendezvousSession",
                v18);
            }
          }
          else
          {
            CEventLogger::LogError(
              v16,
              v15,
              L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
              0x11Cu,
              L"CIMRequestRA::SetRendezvousSession",
              v14);
          }
        }
        else
        {
          CEventLogger::LogError(
            v13,
            v12,
            L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
            0x116u,
            L"CIMRequestRA::SetRendezvousSession",
            v11);
        }
      }
      else
      {
        CEventLogger::LogError(
          v9,
          v8,
          L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
          0x110u,
          L"CIMRequestRA::SetRendezvousSession",
          v7);
      }
    }
    else
    {
      v10 = -2147467261;
    }
  }
  else
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      0,
      v5,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
      0x101u,
      L"CIMRequestRA::SetRendezvousSession",
      0x8007000E);
  }
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  return v10;
}

```

## disassembly

```asm
0x140011530  push    rbp
0x140011532  push    rbx
0x140011533  push    rsi
0x140011534  push    rdi
0x140011535  push    r14
0x140011537  mov     rbp, rsp
0x14001153a  sub     rsp, 40h
0x14001153e  mov     rsi, rdx
0x140011541  mov     [rbp+arg_18], 0
0x140011549  mov     rdi, rcx
0x14001154c  mov     [rbp+arg_10], 0
0x140011554  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001155b  mov     [rbp+var_10], 0
0x140011563  mov     ecx, 0D0h; unsigned __int64
0x140011568  mov     [rbp+arg_0], 0
0x14001156f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011574  test    rax, rax
0x140011577  jz      short loc_140011589
0x140011579  mov     rdx, rdi; struct CIMRequestRA *
0x14001157c  mov     rcx, rax; this
0x14001157f  call    ??0CIMRequestRAEvent@@QEAA@PEAVCIMRequestRA@@@Z; CIMRequestRAEvent::CIMRequestRAEvent(CIMRequestRA *)
0x140011584  mov     rcx, rax
0x140011587  jmp     short loc_14001158B
0x140011589  xor     ecx, ecx; this
0x14001158b  mov     [rdi+10h], rcx
0x14001158f  test    rcx, rcx
0x140011592  jz      loc_1400116F7
0x140011598  mov     rax, [rcx]
0x14001159b  mov     rax, [rax+8]
0x14001159f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115a4  test    rsi, rsi
0x1400115a7  jz      loc_1400116F0
0x1400115ad  mov     rax, [rsi]
0x1400115b0  lea     r8, [rbp+arg_18]
0x1400115b4  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x1400115bb  mov     rcx, rsi
0x1400115be  mov     rax, [rax]
0x1400115c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115c6  mov     ebx, eax
0x1400115c8  test    eax, eax
0x1400115ca  jns     short loc_1400115DB
0x1400115cc  mov     [rsp+40h+var_18], eax
0x1400115d0  mov     r9d, 110h
0x1400115d6  jmp     loc_14001170A
0x1400115db  mov     rcx, [rbp+arg_18]
0x1400115df  lea     r8, [rbp+arg_10]
0x1400115e3  lea     rdx, DIID_DRendezvousSessionEvents
0x1400115ea  mov     rax, [rcx]
0x1400115ed  mov     rax, [rax+20h]
0x1400115f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115f6  mov     ebx, eax
0x1400115f8  test    eax, eax
0x1400115fa  jns     short loc_14001160B
0x1400115fc  mov     [rsp+40h+var_18], eax
0x140011600  mov     r9d, 116h
0x140011606  jmp     loc_14001170A
0x14001160b  mov     rdx, [rbp+arg_10]; struct IConnectionPoint *
0x14001160f  mov     rcx, [rdi+10h]; this
0x140011613  call    ?Advise@CIMRequestRAEvent@@QEAAJPEAUIConnectionPoint@@@Z; CIMRequestRAEvent::Advise(IConnectionPoint *)
0x140011618  mov     ebx, eax
0x14001161a  test    eax, eax
0x14001161c  jns     short loc_14001162D
0x14001161e  mov     [rsp+40h+var_18], eax
0x140011622  mov     r9d, 11Ch
0x140011628  jmp     loc_14001170A
0x14001162d  mov     rax, [rsi]
0x140011630  lea     r14, [rdi+18h]
0x140011634  mov     r8, r14
0x140011637  lea     rdx, _GUID_9ba4b1dd_8b0c_48b7_9e7c_2f25857c8df5
0x14001163e  mov     rcx, rsi
0x140011641  mov     rax, [rax]
0x140011644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011649  mov     ebx, eax
0x14001164b  test    eax, eax
0x14001164d  jns     short loc_14001165E
0x14001164f  mov     [rsp+40h+var_18], eax
0x140011653  mov     r9d, 127h
0x140011659  jmp     loc_14001170A
0x14001165e  mov     rcx, [r14]
0x140011661  test    rcx, rcx
0x140011664  jnz     short loc_14001167E
0x140011666  mov     ebx, 80004005h
0x14001166b  mov     [rsp+40h+var_18], 80004005h
0x140011673  mov     r9d, 12Dh
0x140011679  jmp     loc_14001170A
0x14001167e  mov     [rbp+arg_0], 0
0x140011685  lea     rdx, [rbp+arg_0]
0x140011689  mov     rax, [rcx]
0x14001168c  mov     rax, [rax+28h]
0x140011690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011695  mov     ebx, eax
0x140011697  test    eax, eax
0x140011699  jns     short loc_1400116A7
0x14001169b  mov     [rsp+40h+var_18], eax
0x14001169f  mov     r9d, 139h
0x1400116a5  jmp     short loc_14001170A
0x1400116a7  mov     eax, [rbp+arg_0]
0x1400116aa  mov     ecx, 1
0x1400116af  test    cl, al
0x1400116b1  jz      short loc_1400116BD
0x1400116b3  mov     [rdi+28h], ecx
0x1400116b6  test    al, 8
0x1400116b8  jz      short loc_1400116BD
0x1400116ba  mov     [rdi+34h], ecx
0x1400116bd  test    al, 2
0x1400116bf  jz      short loc_1400116CB
0x1400116c1  mov     [rdi+2Ch], ecx
0x1400116c4  test    al, 8
0x1400116c6  jz      short loc_1400116CB
0x1400116c8  mov     [rdi+30h], ecx
0x1400116cb  mov     rcx, [r14]
0x1400116ce  lea     rdx, [rdi+38h]
0x1400116d2  mov     rax, [rcx]
0x1400116d5  mov     rax, [rax+20h]
0x1400116d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116de  mov     ebx, eax
0x1400116e0  test    eax, eax
0x1400116e2  jns     short loc_140011722
0x1400116e4  mov     [rsp+40h+var_18], eax
0x1400116e8  mov     r9d, 163h
0x1400116ee  jmp     short loc_14001170A
0x1400116f0  mov     ebx, 80004003h
0x1400116f5  jmp     short loc_140011722
0x1400116f7  mov     ebx, 8007000Eh
0x1400116fc  mov     [rsp+40h+var_18], 8007000Eh; unsigned int
0x140011704  mov     r9d, 101h; unsigned int
0x14001170a  lea     rax, aCimrequestraSe; "CIMRequestRA::SetRendezvousSession"
0x140011711  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011718  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x14001171d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011722  xor     ecx, ecx; bstrString
0x140011724  call    cs:__imp_SysFreeString
0x14001172a  xor     ecx, ecx; bstrString
0x14001172c  call    cs:__imp_SysFreeString
0x140011732  xor     ecx, ecx; bstrString
0x140011734  call    cs:__imp_SysFreeString
0x14001173a  lea     rcx, [rbp+var_10]
0x14001173e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140011743  lea     rcx, [rbp+arg_10]
0x140011747  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001174c  lea     rcx, [rbp+arg_18]
0x140011750  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140011755  mov     eax, ebx
0x140011757  add     rsp, 40h
0x14001175b  pop     r14
0x14001175d  pop     rdi
0x14001175e  pop     rsi
0x14001175f  pop     rbx
0x140011760  pop     rbp
0x140011761  retn
```
