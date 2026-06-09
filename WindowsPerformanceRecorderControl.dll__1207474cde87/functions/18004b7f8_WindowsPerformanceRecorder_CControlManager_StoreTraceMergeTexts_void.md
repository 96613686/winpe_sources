# WindowsPerformanceRecorder::CControlManager::StoreTraceMergeTexts(void)

- ea: `0x18004b7f8`
- end: `0x18004bc9e`
- name: `?StoreTraceMergeTexts@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ`
- size: `1190`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18005b310`

## callees

- `0x18000829c`
- `0x180008330`
- `0x180016480`
- `0x18001c458`
- `0x18001c820`
- `0x18001e6e0`
- `0x180021810`
- `0x180026460`
- `0x180040a04`
- `0x18004b7f8`
- `0x18004bca4`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004b86d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b879`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b949`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b98e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b99a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba00`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba26`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bad3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004baed`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb07`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb13`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb69`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb83`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbce`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbe8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc02`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc54`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b86d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b879`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b949`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b98e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b99a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba00`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ba26`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bad3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004baed`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb07`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb13`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb69`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb83`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbce`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbe8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc02`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc54`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc7a`

## string_xrefs

- `0x18004baa7`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::StoreTraceMergeTexts(
        WindowsPerformanceRecorder::CControlManager *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  int v4; // edi
  int v5; // edi
  unsigned int i; // esi
  __int64 v7; // rcx
  int v8; // edi
  signed int v9; // edi
  unsigned int v10; // ebx
  int v11; // edi
  const char *v12; // [rsp+28h] [rbp-60h]
  __int64 v13; // [rsp+38h] [rbp-50h] BYREF
  BSTR v14; // [rsp+40h] [rbp-48h] BYREF
  BSTR v15; // [rsp+48h] [rbp-40h] BYREF
  BSTR v16[2]; // [rsp+50h] [rbp-38h] BYREF
  ATL::CAtlException *v17; // [rsp+60h] [rbp-28h] BYREF
  const void *v18; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v19; // [rsp+A0h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+20h]

  v16[1] = (BSTR)-2LL;
  if ( !*((_QWORD *)this + 48) )
    return 2147549183LL;
  bstrString = 0;
  v3 = *((_QWORD *)this + 48);
  try
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 88LL))(v3);
    if ( v4 >= 0 )
    {
      *((_BYTE *)this + 448) = 0;
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 456, 0);
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 464, bstrString);
      *((_BYTE *)this + 472) = 0;
      v13 = 0;
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 48))(
             *((_QWORD *)this + 48),
             &GUID_f99dbe52_715f_4410_927c_c58d9eb7a252,
             &v13) >= 0 )
      {
        LOWORD(v18) = 0;
        v16[0] = 0;
        if ( (*(int (__fastcall **)(__int64, const void **, BSTR *))(*(_QWORD *)v13 + 96LL))(v13, &v18, v16) >= 0 )
        {
          *((_BYTE *)this + 472) = (_WORD)v18 == 0xFFFF;
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 480, v16[0]);
        }
        SysFreeString(v16[0]);
      }
      v19 = 0;
      v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 48) + 56LL))(
             *((_QWORD *)this + 48),
             &v19);
      if ( v5 >= 0 )
      {
        v14 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v18);
        for ( i = 0; ; ++i )
        {
          v7 = *((_QWORD *)this + 48);
          if ( i >= v19 )
            break;
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v7 + 64LL))(v7, i, &v14);
          if ( v8 < 0 )
          {
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
            SysFreeString(v14);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            SysFreeString(bstrString);
            SysFreeString(0);
            return (unsigned int)v8;
          }
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, v14);
          if ( *((_QWORD *)this + 63) == *((_QWORD *)this + 64) )
          {
            std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Emplace_reallocate<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &>(
              (char *)this + 496,
              *((_QWORD *)this + 63),
              &v18);
          }
          else
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              *((_QWORD **)this + 63),
              &v18);
            *((_QWORD *)this + 63) += 8LL;
          }
        }
        v15 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 80LL))(v7, &v15);
        if ( v9 >= 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 488, v15);
          if ( *(_DWORD *)(*((_QWORD *)this + 61) - 16LL) )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v16);
            v11 = WindowsPerformanceRecorder::Impl::ConvertToFullPath((__int64)v16, *((const wchar_t **)this + 61));
            if ( v11 >= 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 488, v16);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v16);
              SysFreeString(v15);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
              SysFreeString(v14);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
              SysFreeString(bstrString);
              SysFreeString(0);
              result = 0;
            }
            else
            {
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v16);
              SysFreeString(v15);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
              SysFreeString(v14);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
              SysFreeString(bstrString);
              SysFreeString(0);
              result = (unsigned int)v11;
            }
          }
          else
          {
            v10 = ATL::AtlHresultFromWin32(0x4C7u);
            SysFreeString(v15);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
            SysFreeString(v14);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            SysFreeString(bstrString);
            SysFreeString(0);
            result = v10;
          }
        }
        else
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "StoreTraceMergeTexts",
            (const char *)0x1B48,
            v9,
            "COMGUARD",
            v12);
          SysFreeString(v15);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
          SysFreeString(v14);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
          SysFreeString(bstrString);
          SysFreeString(0);
          result = (unsigned int)v9;
        }
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
        SysFreeString(bstrString);
        SysFreeString(0);
        result = (unsigned int)v5;
      }
    }
    else
    {
      SysFreeString(bstrString);
      SysFreeString(0);
      result = (unsigned int)v4;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v17 )
  {
    return *(unsigned int *)v17;
  }
  return result;
}

```

## disassembly

```asm
0x18004b7f8  push    rbx
0x18004b7fa  push    rsi
0x18004b7fb  push    rdi
0x18004b7fc  sub     rsp, 70h
0x18004b800  mov     [rsp+88h+var_30], 0FFFFFFFFFFFFFFFEh
0x18004b809  mov     rbx, rcx
0x18004b80c  cmp     qword ptr [rcx+180h], 0
0x18004b814  jnz     short loc_18004B820
0x18004b816  mov     eax, 8000FFFFh
0x18004b81b  jmp     loc_18004BC95
0x18004b820  xor     eax, eax
0x18004b822  mov     word ptr [rsp+88h+arg_0], ax
0x18004b82a  mov     [rsp+88h+var_58], rax
0x18004b82f  mov     [rsp+88h+bstrString], rax
0x18004b837  mov     rcx, [rcx+180h]
0x18004b83e  mov     rax, [rcx]
0x18004b841  lea     r9, [rsp+88h+bstrString]
0x18004b849  lea     r8, [rsp+88h+var_58]
0x18004b84e  lea     rdx, [rsp+88h+arg_0]
0x18004b856  mov     rax, [rax+58h]
0x18004b85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b85f  mov     edi, eax
0x18004b861  test    eax, eax
0x18004b863  jns     short loc_18004B886
0x18004b865  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004b86d  call    cs:__imp_SysFreeString
0x18004b873  nop
0x18004b874  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004b879  call    cs:__imp_SysFreeString
0x18004b87f  mov     eax, edi
0x18004b881  jmp     loc_18004BC95
0x18004b886  cmp     word ptr [rsp+88h+arg_0], 0FFFFh
0x18004b88f  setz    al
0x18004b892  mov     [rbx+1C0h], al
0x18004b898  lea     rcx, [rbx+1C8h]
0x18004b89f  mov     rdx, [rsp+88h+var_58]
0x18004b8a4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004b8a9  lea     rcx, [rbx+1D0h]
0x18004b8b0  mov     rdx, [rsp+88h+bstrString]
0x18004b8b8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004b8bd  mov     byte ptr [rbx+1D8h], 0
0x18004b8c4  mov     [rsp+88h+var_50], 0
0x18004b8cd  mov     rcx, [rbx+180h]
0x18004b8d4  mov     rax, [rcx]
0x18004b8d7  lea     r8, [rsp+88h+var_50]
0x18004b8dc  lea     rdx, _GUID_f99dbe52_715f_4410_927c_c58d9eb7a252
0x18004b8e3  mov     rax, [rax]
0x18004b8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8eb  test    eax, eax
0x18004b8ed  js      short loc_18004B94F
0x18004b8ef  xor     eax, eax
0x18004b8f1  mov     word ptr [rsp+88h+arg_8], ax
0x18004b8f9  mov     [rsp+88h+var_38], rax
0x18004b8fe  mov     rcx, [rsp+88h+var_50]
0x18004b903  mov     rax, [rcx]
0x18004b906  lea     r8, [rsp+88h+var_38]
0x18004b90b  lea     rdx, [rsp+88h+arg_8]
0x18004b913  mov     rax, [rax+60h]
0x18004b917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b91c  test    eax, eax
0x18004b91e  js      short loc_18004B944
0x18004b920  cmp     word ptr [rsp+88h+arg_8], 0FFFFh
0x18004b929  setz    al
0x18004b92c  mov     [rbx+1D8h], al
0x18004b932  lea     rcx, [rbx+1E0h]
0x18004b939  mov     rdx, [rsp+88h+var_38]
0x18004b93e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004b943  nop
0x18004b944  mov     rcx, [rsp+88h+var_38]; bstrString
0x18004b949  call    cs:__imp_SysFreeString
0x18004b94f  mov     [rsp+88h+arg_10], 0
0x18004b95a  mov     rcx, [rbx+180h]
0x18004b961  mov     rax, [rcx]
0x18004b964  lea     rdx, [rsp+88h+arg_10]
0x18004b96c  mov     rax, [rax+38h]
0x18004b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b975  mov     edi, eax
0x18004b977  test    eax, eax
0x18004b979  jns     short loc_18004B9A7
0x18004b97b  lea     rcx, [rsp+88h+var_50]
0x18004b980  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b985  nop
0x18004b986  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004b98e  call    cs:__imp_SysFreeString
0x18004b994  nop
0x18004b995  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004b99a  call    cs:__imp_SysFreeString
0x18004b9a0  mov     eax, edi
0x18004b9a2  jmp     loc_18004BC95
0x18004b9a7  mov     [rsp+88h+var_48], 0
0x18004b9b0  lea     rcx, [rsp+88h+arg_8]; void *
0x18004b9b8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004b9bd  nop
0x18004b9be  xor     esi, esi
0x18004b9c0  mov     rcx, [rbx+180h]
0x18004b9c7  cmp     esi, [rsp+88h+arg_10]
0x18004b9ce  jnb     loc_18004BA87
0x18004b9d4  mov     rax, [rcx]
0x18004b9d7  lea     r8, [rsp+88h+var_48]
0x18004b9dc  mov     edx, esi
0x18004b9de  mov     rax, [rax+40h]
0x18004b9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9e7  mov     edi, eax
0x18004b9e9  test    eax, eax
0x18004b9eb  jns     short loc_18004BA33
0x18004b9ed  lea     rcx, [rsp+88h+arg_8]; this
0x18004b9f5  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004b9fa  nop
0x18004b9fb  mov     rcx, [rsp+88h+var_48]; bstrString
0x18004ba00  call    cs:__imp_SysFreeString
0x18004ba06  nop
0x18004ba07  lea     rcx, [rsp+88h+var_50]
0x18004ba0c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ba11  nop
0x18004ba12  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004ba1a  call    cs:__imp_SysFreeString
0x18004ba20  nop
0x18004ba21  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004ba26  call    cs:__imp_SysFreeString
0x18004ba2c  mov     eax, edi
0x18004ba2e  jmp     loc_18004BC95
0x18004ba33  mov     rdx, [rsp+88h+var_48]
0x18004ba38  lea     rcx, [rsp+88h+arg_8]
0x18004ba40  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004ba45  lea     rdi, [rbx+1F0h]
0x18004ba4c  mov     rax, [rdi+8]
0x18004ba50  cmp     rax, [rdi+10h]
0x18004ba54  jz      short loc_18004BA6D
0x18004ba56  lea     rdx, [rsp+88h+arg_8]; void *
0x18004ba5e  mov     rcx, rax; void *
0x18004ba61  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004ba66  add     qword ptr [rdi+8], 8
0x18004ba6b  jmp     short loc_18004BA80
0x18004ba6d  lea     r8, [rsp+88h+arg_8]
0x18004ba75  mov     rdx, rax
0x18004ba78  mov     rcx, rdi
0x18004ba7b  call    ??$_Emplace_reallocate@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@AEAAPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Emplace_reallocate<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004ba80  inc     esi
0x18004ba82  jmp     loc_18004B9C0
0x18004ba87  mov     [rsp+88h+var_40], 0
0x18004ba90  mov     rax, [rcx]
0x18004ba93  lea     rdx, [rsp+88h+var_40]
0x18004ba98  mov     rax, [rax+50h]
0x18004ba9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004baa1  mov     edi, eax
0x18004baa3  test    eax, eax
0x18004baa5  jns     short loc_18004BB20
0x18004baa7  lea     rax, aComguard; "COMGUARD"
0x18004baae  mov     [rsp+88h+Format], rax; Format
0x18004bab3  mov     r9d, edi; unsigned int
0x18004bab6  mov     r8d, 1B48h; char *
0x18004babc  lea     rdx, aStoretracemerg; "StoreTraceMergeTexts"
0x18004bac3  mov     ecx, 2; this
0x18004bac8  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18004bacd  nop
0x18004bace  mov     rcx, [rsp+88h+var_40]; bstrString
0x18004bad3  call    cs:__imp_SysFreeString
0x18004bad9  nop
0x18004bada  lea     rcx, [rsp+88h+arg_8]; this
0x18004bae2  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bae7  nop
0x18004bae8  mov     rcx, [rsp+88h+var_48]; bstrString
0x18004baed  call    cs:__imp_SysFreeString
0x18004baf3  nop
0x18004baf4  lea     rcx, [rsp+88h+var_50]
0x18004baf9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004bafe  nop
0x18004baff  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004bb07  call    cs:__imp_SysFreeString
0x18004bb0d  nop
0x18004bb0e  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004bb13  call    cs:__imp_SysFreeString
0x18004bb19  mov     eax, edi
0x18004bb1b  jmp     loc_18004BC95
0x18004bb20  mov     rdx, [rsp+88h+var_40]
0x18004bb25  lea     rcx, [rbx+1E8h]
0x18004bb2c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004bb31  mov     rax, [rbx+1E8h]
0x18004bb38  cmp     dword ptr [rax-10h], 0
0x18004bb3c  jnz     short loc_18004BB9C
0x18004bb3e  mov     ecx, 4C7h; unsigned int
0x18004bb43  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004bb48  mov     ebx, eax
0x18004bb4a  mov     rcx, [rsp+88h+var_40]; bstrString
0x18004bb4f  call    cs:__imp_SysFreeString
0x18004bb55  nop
0x18004bb56  lea     rcx, [rsp+88h+arg_8]; this
0x18004bb5e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bb63  nop
0x18004bb64  mov     rcx, [rsp+88h+var_48]; bstrString
0x18004bb69  call    cs:__imp_SysFreeString
0x18004bb6f  nop
0x18004bb70  lea     rcx, [rsp+88h+var_50]
0x18004bb75  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004bb7a  nop
0x18004bb7b  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004bb83  call    cs:__imp_SysFreeString
0x18004bb89  nop
0x18004bb8a  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004bb8f  call    cs:__imp_SysFreeString
0x18004bb95  mov     eax, ebx
0x18004bb97  jmp     loc_18004BC95
0x18004bb9c  lea     rcx, [rsp+88h+var_38]; void *
0x18004bba1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004bba6  nop
0x18004bba7  mov     rdx, [rbx+1E8h]
0x18004bbae  lea     rcx, [rsp+88h+var_38]
0x18004bbb3  call    ?ConvertToFullPath@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::Impl::ConvertToFullPath(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,ushort const *)
0x18004bbb8  mov     edi, eax
0x18004bbba  test    eax, eax
0x18004bbbc  jns     short loc_18004BC18
0x18004bbbe  lea     rcx, [rsp+88h+var_38]; this
0x18004bbc3  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bbc8  nop
0x18004bbc9  mov     rcx, [rsp+88h+var_40]; bstrString
0x18004bbce  call    cs:__imp_SysFreeString
0x18004bbd4  nop
0x18004bbd5  lea     rcx, [rsp+88h+arg_8]; this
0x18004bbdd  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bbe2  nop
0x18004bbe3  mov     rcx, [rsp+88h+var_48]; bstrString
0x18004bbe8  call    cs:__imp_SysFreeString
0x18004bbee  nop
0x18004bbef  lea     rcx, [rsp+88h+var_50]
0x18004bbf4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004bbf9  nop
0x18004bbfa  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004bc02  call    cs:__imp_SysFreeString
0x18004bc08  nop
0x18004bc09  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004bc0e  call    cs:__imp_SysFreeString
0x18004bc14  mov     eax, edi
0x18004bc16  jmp     short loc_18004BC95
0x18004bc18  lea     rdx, [rsp+88h+var_38]
0x18004bc1d  lea     rcx, [rbx+1E8h]
0x18004bc24  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18004bc29  nop
0x18004bc2a  lea     rcx, [rsp+88h+var_38]; this
0x18004bc2f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bc34  nop
0x18004bc35  mov     rcx, [rsp+88h+var_40]; bstrString
0x18004bc3a  call    cs:__imp_SysFreeString
0x18004bc40  nop
0x18004bc41  lea     rcx, [rsp+88h+arg_8]; this
0x18004bc49  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004bc4e  nop
0x18004bc4f  mov     rcx, [rsp+88h+var_48]; bstrString
0x18004bc54  call    cs:__imp_SysFreeString
0x18004bc5a  nop
0x18004bc5b  lea     rcx, [rsp+88h+var_50]
0x18004bc60  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004bc65  nop
0x18004bc66  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004bc6e  call    cs:__imp_SysFreeString
0x18004bc74  nop
0x18004bc75  mov     rcx, [rsp+88h+var_58]; bstrString
0x18004bc7a  call    cs:__imp_SysFreeString
0x18004bc80  nop
0x18004bc81  xor     eax, eax
0x18004bc83  jmp     short loc_18004BC95
0x18004bc85  mov     eax, 8007000Eh
0x18004bc8a  jmp     short loc_18004BC95
0x18004bc8c  jmp     short loc_18004BC85
0x18004bc8e  mov     eax, [rsp+88h+arg_0]
0x18004bc95  add     rsp, 70h
0x18004bc99  pop     rdi
0x18004bc9a  pop     rsi
0x18004bc9b  pop     rbx
0x18004bc9c  retn
```
