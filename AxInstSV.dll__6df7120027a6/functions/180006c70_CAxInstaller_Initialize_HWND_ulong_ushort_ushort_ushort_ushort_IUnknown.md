# CAxInstaller::Initialize(HWND__ *,ulong,ushort *,ushort *,ushort *,ushort * *,IUnknown * *)

- ea: `0x180006c70`
- end: `0x180006dbb`
- name: `?Initialize@CAxInstaller@@UEAAJPEAUHWND__@@KPEAG11PEAPEAGPEAPEAUIUnknown@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CAxInstaller *this, HWND, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002c00`
- `0x180005cc0`
- `0x180005de0`
- `0x180006aec`
- `0x180006c70`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d9e`

## pseudocode

```c
__int64 __fastcall CAxInstaller::Initialize(
        CAxInstaller *this,
        HWND a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7,
        struct IUnknown **a8)
{
  int v9; // r14d
  HWND v10; // r15
  CAxInstaller *v11; // rdi
  _DWORD *v12; // rbx
  int v13; // ebx
  unsigned __int16 *v14; // rsi
  BSTR bstrString; // [rsp+28h] [rbp-50h] BYREF
  _DWORD *v17; // [rsp+30h] [rbp-48h]
  ATL::CAtlException *v18; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v19[56]; // [rsp+40h] [rbp-38h] BYREF

  v9 = a3;
  v10 = a2;
  v11 = this;
  bstrString = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v19,
    (char *)this + 592);
  v12 = (_DWORD *)((char *)v11 + 672);
  v17 = (_DWORD *)((char *)v11 + 672);
  if ( *((_DWORD *)v11 + 168) )
  {
    v13 = -2147024891;
LABEL_3:
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v19);
    goto LABEL_10;
  }
  v14 = a6;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CComBSTR::operator=((char *)v11 + 632, a6);
    ATL::CComBSTR::operator=((char *)v11 + 656, a4);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v18) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180006D02);
      v13 = *(_DWORD *)v18;
      if ( *(int *)v18 < 0 )
        goto LABEL_3;
      v11 = this;
      v14 = a6;
      v9 = a3;
      v10 = a2;
      v12 = v17;
    }
  }
  *((_QWORD *)v11 + 86) = v10;
  *((_DWORD *)v11 + 166) = v9;
  *v12 = 1;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v19);
  v13 = CAxInstaller::Initialize(v11);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(CAxInstaller *, unsigned __int16 *, BSTR *))(*(_QWORD *)v11 + 64LL))(
            v11,
            v14,
            &bstrString);
    if ( v13 >= 0 )
      v13 = (*(__int64 (__fastcall **)(CAxInstaller *, unsigned __int16 **, struct IUnknown **))(*(_QWORD *)v11 + 56LL))(
              v11,
              a7,
              a8);
  }
LABEL_10:
  SysFreeString(bstrString);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006c70  mov     rax, rsp
0x180006c73  mov     [rax+20h], rbx
0x180006c77  mov     [rax+18h], r8d
0x180006c7b  mov     [rax+10h], rdx
0x180006c7f  mov     [rax+8], rcx
0x180006c83  push    rsi
0x180006c84  push    rdi
0x180006c85  push    r12
0x180006c87  push    r14
0x180006c89  push    r15
0x180006c8b  sub     rsp, 50h
0x180006c8f  mov     r12, r9
0x180006c92  mov     r14d, r8d
0x180006c95  mov     r15, rdx
0x180006c98  mov     rdi, rcx
0x180006c9b  mov     qword ptr [rax-50h], 0
0x180006ca3  lea     rdx, [rcx+250h]
0x180006caa  lea     rcx, [rax-38h]
0x180006cae  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180006cb3  nop
0x180006cb4  lea     rbx, [rdi+2A0h]
0x180006cbb  mov     [rsp+78h+var_48], rbx
0x180006cc0  cmp     dword ptr [rbx], 0
0x180006cc3  jz      short loc_180006CD9
0x180006cc5  mov     ebx, 80070005h
0x180006cca  lea     rcx, [rsp+78h+var_38]
0x180006ccf  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180006cd4  jmp     loc_180006D99
0x180006cd9  lea     rcx, [rdi+278h]
0x180006ce0  mov     rsi, [rsp+78h+arg_28]
0x180006ce8  mov     rdx, rsi
0x180006ceb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006cf0  lea     rcx, [rdi+290h]
0x180006cf7  mov     rdx, r12
0x180006cfa  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006cff  nop
0x180006d00  jmp     short loc_180006D2F
0x180006d02  mov     ebx, [rsp+78h+var_58]
0x180006d06  test    ebx, ebx
0x180006d08  js      short loc_180006CCA
0x180006d0a  mov     rdi, [rsp+78h+arg_0]
0x180006d12  mov     rsi, [rsp+78h+arg_28]
0x180006d1a  mov     r14d, [rsp+78h+arg_10]
0x180006d22  mov     r15, [rsp+78h+arg_8]
0x180006d2a  mov     rbx, [rsp+78h+var_48]
0x180006d2f  mov     [rdi+2B0h], r15
0x180006d36  mov     [rdi+298h], r14d
0x180006d3d  mov     dword ptr [rbx], 1
0x180006d43  lea     rcx, [rsp+78h+var_38]
0x180006d48  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180006d4d  mov     rcx, rdi; this
0x180006d50  call    ?Initialize@CAxInstaller@@QEAAJXZ; CAxInstaller::Initialize(void)
0x180006d55  mov     ebx, eax
0x180006d57  test    eax, eax
0x180006d59  js      short loc_180006D99
0x180006d5b  mov     rax, [rdi]
0x180006d5e  lea     r8, [rsp+78h+bstrString]
0x180006d63  mov     rdx, rsi
0x180006d66  mov     rcx, rdi
0x180006d69  mov     rax, [rax+40h]
0x180006d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d72  mov     ebx, eax
0x180006d74  test    eax, eax
0x180006d76  js      short loc_180006D99
0x180006d78  mov     rax, [rdi]
0x180006d7b  mov     r8, [rsp+78h+arg_38]
0x180006d83  mov     rdx, [rsp+78h+arg_30]
0x180006d8b  mov     rcx, rdi
0x180006d8e  mov     rax, [rax+38h]
0x180006d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d97  mov     ebx, eax
0x180006d99  mov     rcx, [rsp+78h+bstrString]; bstrString
0x180006d9e  call    cs:__imp_SysFreeString
0x180006da4  mov     eax, ebx
0x180006da6  mov     rbx, [rsp+78h+arg_18]
0x180006dae  add     rsp, 50h
0x180006db2  pop     r15
0x180006db4  pop     r14
0x180006db6  pop     r12
0x180006db8  pop     rdi
0x180006db9  pop     rsi
0x180006dba  retn
```
