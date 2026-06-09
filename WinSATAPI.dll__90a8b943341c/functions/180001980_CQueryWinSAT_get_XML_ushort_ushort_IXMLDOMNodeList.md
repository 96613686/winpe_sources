# CQueryWinSAT::get_XML(ushort *,ushort *,IXMLDOMNodeList * *)

- ea: `0x180001980`
- end: `0x180001eca`
- name: `?get_XML@CQueryWinSAT@@UEAAJPEAG0PEAPEAUIXMLDOMNodeList@@@Z`
- size: `1354`
- prototype: `__int64 __fastcall(CQueryWinSAT *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNodeList **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001640`
- `0x180001980`
- `0x18000206c`
- `0x1800020f4`
- `0x180003300`
- `0x180004020`
- `0x180004048`
- `0x1800043f0`
- `0x180007080`
- `0x180007ea0`
- `0x180008490`
- `0x1800084f0`
- `0x18000e490`
- `0x18001ee64`
- `0x18001f2e4`
- `0x18002df78`
- `0x180033010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001a94`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001b0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001bd6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001c7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001db2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e34`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001a94`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001b0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001bd6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001c7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001db2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e34`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CQueryWinSAT::get_XML(
        CQueryWinSAT *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNodeList **a4)
{
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  int WinSATDataStoreDir; // ebx
  CSupportErrorInfo *v11; // rcx
  __int64 v12; // rcx
  int AllWinSATAssessmentFileNames; // ebx
  mlib *v14; // rcx
  unsigned __int16 v15; // r9
  const unsigned __int16 *v16; // rax
  CSupportErrorInfo *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rbx
  int v20; // edi
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rbx
  mlib *v24; // rcx
  unsigned __int16 v25; // r9
  const unsigned __int16 *v26; // rax
  CSupportErrorInfo *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  const unsigned __int16 *v30; // rdx
  HINSTANCE v31; // [rsp+20h] [rbp-98h]
  HINSTANCE v32; // [rsp+20h] [rbp-98h]
  __int128 v33; // [rsp+30h] [rbp-88h] BYREF
  __int64 v34; // [rsp+40h] [rbp-78h]
  __int64 v35; // [rsp+48h] [rbp-70h] BYREF
  struct HINSTANCE__ v36[2]; // [rsp+50h] [rbp-68h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-60h] BYREF
  _BYTE v38[8]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v39; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v40[8]; // [rsp+70h] [rbp-48h] BYREF
  _QWORD *v41[2]; // [rsp+78h] [rbp-40h] BYREF
  __int64 v42; // [rsp+88h] [rbp-30h] BYREF
  const unsigned __int16 *v43; // [rsp+90h] [rbp-28h]
  __int64 v44; // [rsp+D8h] [rbp+20h] BYREF

  v41[1] = (_QWORD *)-2LL;
  if ( !a4 )
    return 2147500037LL;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v38,
      a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v36,
      v8);
    v37 = 0;
    v35 = 0;
    v9 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v44 = v9;
    if ( v9 )
      v9 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v9,
             260);
    v44 = v9;
    WinSATDataStoreDir = DataStoreReader::GetWinSATDataStoreDir((__int64)&v44);
    if ( WinSATDataStoreDir >= 0 )
    {
      v33 = 0;
      v34 = 0;
      AllWinSATAssessmentFileNames = DataStoreReader::GetAllWinSATAssessmentFileNames((__int64)&v44, &v33);
      if ( AllWinSATAssessmentFileNames >= 0 )
      {
        if ( *((_QWORD *)&v33 + 1) == (_QWORD)v33 )
        {
          if ( (_QWORD)v33 )
          {
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
              v12,
              v33,
              *((_QWORD *)&v33 + 1));
            operator delete((void *)v33);
            v33 = 0;
            v34 = 0;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
          result = 2147745810LL;
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v40,
            v33);
          if ( (int)mlib::XmlDOM::LoadDocumentFromFile(v33, (char *)&v37, (__int64)v40) >= 0 )
          {
            v19 = (__int64)v37;
            v20 = (**v37)(v37, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v35);
            if ( v20 >= 0 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v41,
                a3);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v39,
                a2);
              v22 = mlib::XmlDOM::SelectXml(v35, (__int64)&v39, v41, a4, (__int64)v36);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v41);
              if ( v22 >= 0 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v40);
                if ( (_QWORD)v33 )
                {
                  std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                    v29,
                    v33,
                    *((_QWORD *)&v33 + 1));
                  operator delete((void *)v33);
                  v33 = 0;
                  v34 = 0;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
                if ( v35 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
                result = 0;
              }
              else
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v39,
                  1024);
                v23 = *(_QWORD *)(*(_QWORD *)&v36[0].unused + 24LL);
                v26 = mlib::MUIStr_(v24, (const char *)0x1D7, 110, v25, v32);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
                  &v39,
                  v26,
                  v23);
                CSupportErrorInfo::SetErrorInfo(
                  v27,
                  *(const unsigned __int16 **)(v39 + 24),
                  &IID_IQueryRecentWinSATAssessment);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v40);
                if ( (_QWORD)v33 )
                {
                  std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                    v28,
                    v33,
                    *((_QWORD *)&v33 + 1));
                  operator delete((void *)v33);
                  v33 = 0;
                  v34 = 0;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
                result = 2147500037LL;
              }
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v40);
              if ( (_QWORD)v33 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v21,
                  v33,
                  *((_QWORD *)&v33 + 1));
                operator delete((void *)v33);
                v33 = 0;
                v34 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
              result = (unsigned int)v20;
            }
          }
          else
          {
            v16 = mlib::MUIStr_(v14, (const char *)0x1C5, 109, v15, v31);
            CSupportErrorInfo::SetErrorInfo(v17, v16, &IID_IQueryRecentWinSATAssessment);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v40);
            if ( (_QWORD)v33 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                v18,
                v33,
                *((_QWORD *)&v33 + 1));
              operator delete((void *)v33);
              v33 = 0;
              v34 = 0;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
            result = 2147549183LL;
          }
        }
      }
      else
      {
        if ( (_QWORD)v33 )
        {
          std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
            v12,
            v33,
            *((_QWORD *)&v33 + 1));
          operator delete((void *)v33);
          v33 = 0;
          v34 = 0;
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
        result = (unsigned int)AllWinSATAssessmentFileNames;
      }
    }
    else
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v38);
      result = (unsigned int)WinSATDataStoreDir;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( mlib::MSError v42 )
  {
    v30 = &String2;
    if ( v43 )
      v30 = v43;
    CSupportErrorInfo::SetErrorInfo(v11, v30, &IID_IQueryAllWinSATAssessments);
    mlib::MSError::~MSError((mlib::MSError *)&v42);
    return 2147500037LL;
  }
  catch ( mlib::MUIError )
  {
    CSupportErrorInfo::SetErrorInfo(v11, L"Cannot load string from resouce.", &IID_IQueryAllWinSATAssessments);
    return 2147500037LL;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001980  mov     rax, rsp
0x180001983  push    rdi
0x180001984  push    r14
0x180001986  push    r15
0x180001988  sub     rsp, 0A0h
0x18000198f  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001997  mov     [rax+8], rbx
0x18000199b  mov     [rax+10h], rsi
0x18000199f  mov     rsi, r9
0x1800019a2  mov     r14, r8
0x1800019a5  mov     r15, rdx
0x1800019a8  test    r9, r9
0x1800019ab  jnz     short loc_1800019B7
0x1800019ad  mov     eax, 80004005h
0x1800019b2  jmp     loc_180001EAE
0x1800019b7  lea     rcx, [rsp+0B8h+var_58]
0x1800019bc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1800019c1  nop
0x1800019c2  lea     rcx, [rsp+0B8h+var_68]
0x1800019c7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1800019cc  nop
0x1800019cd  and     [rsp+0B8h+var_60], 0
0x1800019d3  and     [rsp+0B8h+var_70], 0
0x1800019d9  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x1800019de  mov     [rsp+0B8h+arg_18], rax
0x1800019e6  test    rax, rax
0x1800019e9  jz      short loc_1800019F9
0x1800019eb  mov     edx, 104h
0x1800019f0  mov     rcx, rax
0x1800019f3  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x1800019f8  nop
0x1800019f9  mov     [rsp+0B8h+arg_18], rax
0x180001a01  lea     rcx, [rsp+0B8h+arg_18]
0x180001a09  call    ?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180001a0e  mov     ebx, eax
0x180001a10  test    eax, eax
0x180001a12  jns     short loc_180001A54
0x180001a14  lea     rcx, [rsp+0B8h+arg_18]
0x180001a1c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001a21  nop
0x180001a22  lea     rcx, [rsp+0B8h+var_70]
0x180001a27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001a2c  nop
0x180001a2d  lea     rcx, [rsp+0B8h+var_60]
0x180001a32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001a37  nop
0x180001a38  lea     rcx, [rsp+0B8h+var_68]
0x180001a3d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001a42  nop
0x180001a43  lea     rcx, [rsp+0B8h+var_58]
0x180001a48  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001a4d  mov     eax, ebx
0x180001a4f  jmp     loc_180001EAE
0x180001a54  xorps   xmm0, xmm0
0x180001a57  movdqu  [rsp+0B8h+var_88], xmm0
0x180001a5d  and     [rsp+0B8h+var_78], 0
0x180001a63  lea     rdx, [rsp+0B8h+var_88]
0x180001a68  lea     rcx, [rsp+0B8h+arg_18]
0x180001a70  call    ?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z; DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,DataStoreID,AssessmentTimeTaken)
0x180001a75  mov     ebx, eax
0x180001a77  test    eax, eax
0x180001a79  jns     short loc_180001AEF
0x180001a7b  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001a80  test    rdx, rdx
0x180001a83  jz      short loc_180001AAF
0x180001a85  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001a8a  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001a8f  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001a94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001a9b  nop     dword ptr [rax+rax+00h]
0x180001aa0  xorps   xmm0, xmm0
0x180001aa3  movdqu  [rsp+0B8h+var_88], xmm0
0x180001aa9  and     [rsp+0B8h+var_78], 0
0x180001aaf  lea     rcx, [rsp+0B8h+arg_18]
0x180001ab7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001abc  nop
0x180001abd  lea     rcx, [rsp+0B8h+var_70]
0x180001ac2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ac7  nop
0x180001ac8  lea     rcx, [rsp+0B8h+var_60]
0x180001acd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ad2  nop
0x180001ad3  lea     rcx, [rsp+0B8h+var_68]
0x180001ad8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001add  nop
0x180001ade  lea     rcx, [rsp+0B8h+var_58]
0x180001ae3  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ae8  mov     eax, ebx
0x180001aea  jmp     loc_180001EAE
0x180001aef  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001af4  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001af9  cmp     r8, rdx
0x180001afc  jnz     short loc_180001B6B
0x180001afe  test    rdx, rdx
0x180001b01  jz      short loc_180001B28
0x180001b03  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001b08  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001b0d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001b14  nop     dword ptr [rax+rax+00h]
0x180001b19  xorps   xmm0, xmm0
0x180001b1c  movdqu  [rsp+0B8h+var_88], xmm0
0x180001b22  and     [rsp+0B8h+var_78], 0
0x180001b28  lea     rcx, [rsp+0B8h+arg_18]
0x180001b30  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b35  nop
0x180001b36  lea     rcx, [rsp+0B8h+var_70]
0x180001b3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b40  nop
0x180001b41  lea     rcx, [rsp+0B8h+var_60]
0x180001b46  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b4b  nop
0x180001b4c  lea     rcx, [rsp+0B8h+var_68]
0x180001b51  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b56  nop
0x180001b57  lea     rcx, [rsp+0B8h+var_58]
0x180001b5c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b61  mov     eax, 80040012h
0x180001b66  jmp     loc_180001EAE
0x180001b6b  lea     rcx, [rsp+0B8h+var_48]
0x180001b70  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180001b75  nop
0x180001b76  lea     r8, [rsp+0B8h+var_48]
0x180001b7b  lea     rdx, [rsp+0B8h+var_60]
0x180001b80  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001b85  call    ?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z; mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)
0x180001b8a  test    eax, eax
0x180001b8c  jns     loc_180001C34
0x180001b92  mov     edx, 1C5h; char *
0x180001b97  mov     r8d, 6Dh ; 'm'; int
0x180001b9d  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x180001ba2  lea     r8, IID_IQueryRecentWinSATAssessment; struct _GUID *
0x180001ba9  mov     rdx, rax; unsigned __int16 *
0x180001bac  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x180001bb1  nop
0x180001bb2  lea     rcx, [rsp+0B8h+var_48]
0x180001bb7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001bbc  nop
0x180001bbd  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001bc2  test    rdx, rdx
0x180001bc5  jz      short loc_180001BF1
0x180001bc7  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001bcc  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001bd1  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001bd6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001bdd  nop     dword ptr [rax+rax+00h]
0x180001be2  xorps   xmm0, xmm0
0x180001be5  movdqu  [rsp+0B8h+var_88], xmm0
0x180001beb  and     [rsp+0B8h+var_78], 0
0x180001bf1  lea     rcx, [rsp+0B8h+arg_18]
0x180001bf9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001bfe  nop
0x180001bff  lea     rcx, [rsp+0B8h+var_70]
0x180001c04  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001c09  nop
0x180001c0a  lea     rcx, [rsp+0B8h+var_60]
0x180001c0f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001c14  nop
0x180001c15  lea     rcx, [rsp+0B8h+var_68]
0x180001c1a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c1f  nop
0x180001c20  lea     rcx, [rsp+0B8h+var_58]
0x180001c25  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c2a  mov     eax, 8000FFFFh
0x180001c2f  jmp     loc_180001EAE
0x180001c34  mov     rbx, [rsp+0B8h+var_60]
0x180001c39  mov     rax, [rbx]
0x180001c3c  lea     r8, [rsp+0B8h+var_70]
0x180001c41  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180001c48  mov     rcx, rbx
0x180001c4b  mov     rax, [rax]
0x180001c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c53  mov     edi, eax
0x180001c55  test    eax, eax
0x180001c57  jns     short loc_180001CD8
0x180001c59  lea     rcx, [rsp+0B8h+var_48]
0x180001c5e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c63  nop
0x180001c64  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001c69  test    rdx, rdx
0x180001c6c  jz      short loc_180001C98
0x180001c6e  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001c73  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001c78  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001c7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001c84  nop     dword ptr [rax+rax+00h]
0x180001c89  xorps   xmm0, xmm0
0x180001c8c  movdqu  [rsp+0B8h+var_88], xmm0
0x180001c92  and     [rsp+0B8h+var_78], 0
0x180001c98  lea     rcx, [rsp+0B8h+arg_18]
0x180001ca0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ca5  nop
0x180001ca6  lea     rcx, [rsp+0B8h+var_70]
0x180001cab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001cb0  nop
0x180001cb1  lea     rcx, [rsp+0B8h+var_60]
0x180001cb6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001cbb  nop
0x180001cbc  lea     rcx, [rsp+0B8h+var_68]
0x180001cc1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001cc6  nop
0x180001cc7  lea     rcx, [rsp+0B8h+var_58]
0x180001ccc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001cd1  mov     eax, edi
0x180001cd3  jmp     loc_180001EAE
0x180001cd8  mov     rdx, r14
0x180001cdb  lea     rcx, [rsp+0B8h+var_40]
0x180001ce0  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180001ce5  nop
0x180001ce6  mov     rdx, r15
0x180001ce9  lea     rcx, [rsp+0B8h+var_50]
0x180001cee  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180001cf3  nop
0x180001cf4  lea     rax, [rsp+0B8h+var_68]
0x180001cf9  mov     [rsp+0B8h+var_98], rax; HINSTANCE
0x180001cfe  mov     r9, rsi
0x180001d01  lea     r8, [rsp+0B8h+var_40]
0x180001d06  lea     rdx, [rsp+0B8h+var_50]
0x180001d0b  mov     rcx, [rsp+0B8h+var_70]
0x180001d10  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001d15  mov     edi, eax
0x180001d17  lea     rcx, [rsp+0B8h+var_50]
0x180001d1c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d21  nop
0x180001d22  lea     rcx, [rsp+0B8h+var_40]
0x180001d27  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d2c  test    edi, edi
0x180001d2e  jns     loc_180001E10
0x180001d34  mov     edx, 400h
0x180001d39  lea     rcx, [rsp+0B8h+var_50]
0x180001d3e  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180001d43  nop
0x180001d44  mov     rax, qword ptr [rsp+0B8h+var_68.unused]
0x180001d49  mov     rbx, [rax+18h]
0x180001d4d  mov     edx, 1D7h; char *
0x180001d52  mov     r8d, 6Eh ; 'n'; int
0x180001d58  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x180001d5d  mov     r8, rbx
0x180001d60  mov     rdx, rax
0x180001d63  lea     rcx, [rsp+0B8h+var_50]
0x180001d68  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180001d6d  mov     rax, [rsp+0B8h+var_50]
0x180001d72  lea     r8, IID_IQueryRecentWinSATAssessment; struct _GUID *
0x180001d79  mov     rdx, [rax+18h]; unsigned __int16 *
0x180001d7d  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x180001d82  nop
0x180001d83  lea     rcx, [rsp+0B8h+var_50]
0x180001d88  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d8d  nop
0x180001d8e  lea     rcx, [rsp+0B8h+var_48]
0x180001d93  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d98  nop
0x180001d99  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001d9e  test    rdx, rdx
0x180001da1  jz      short loc_180001DCD
0x180001da3  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001da8  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001dad  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001db2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001db9  nop     dword ptr [rax+rax+00h]
0x180001dbe  xorps   xmm0, xmm0
0x180001dc1  movdqu  [rsp+0B8h+var_88], xmm0
0x180001dc7  and     [rsp+0B8h+var_78], 0
0x180001dcd  lea     rcx, [rsp+0B8h+arg_18]
0x180001dd5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001dda  nop
0x180001ddb  lea     rcx, [rsp+0B8h+var_70]
0x180001de0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001de5  nop
0x180001de6  lea     rcx, [rsp+0B8h+var_60]
0x180001deb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001df0  nop
0x180001df1  lea     rcx, [rsp+0B8h+var_68]
0x180001df6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001dfb  nop
0x180001dfc  lea     rcx, [rsp+0B8h+var_58]
0x180001e01  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001e06  mov     eax, 80004005h
0x180001e0b  jmp     loc_180001EAE
0x180001e10  lea     rcx, [rsp+0B8h+var_48]
0x180001e15  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001e1a  nop
0x180001e1b  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001e20  test    rdx, rdx
0x180001e23  jz      short loc_180001E4F
0x180001e25  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001e2a  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001e2f  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001e34  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001e3b  nop     dword ptr [rax+rax+00h]
0x180001e40  xorps   xmm0, xmm0
0x180001e43  movdqu  [rsp+0B8h+var_88], xmm0
0x180001e49  and     [rsp+0B8h+var_78], 0
0x180001e4f  lea     rcx, [rsp+0B8h+arg_18]
0x180001e57  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001e5c  nop
0x180001e5d  mov     rcx, [rsp+0B8h+var_70]
0x180001e62  test    rcx, rcx
0x180001e65  jz      short loc_180001E74
0x180001e67  mov     rax, [rcx]
0x180001e6a  mov     rax, [rax+10h]
  ... truncated ...
```
