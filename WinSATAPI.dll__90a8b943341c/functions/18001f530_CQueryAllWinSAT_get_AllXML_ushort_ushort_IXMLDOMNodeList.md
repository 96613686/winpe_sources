# CQueryAllWinSAT::get_AllXML(ushort *,ushort *,IXMLDOMNodeList * *)

- ea: `0x18001f530`
- end: `0x18001f954`
- name: `?get_AllXML@CQueryAllWinSAT@@UEAAJPEAG0PEAPEAUIXMLDOMNodeList@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CQueryAllWinSAT *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNodeList **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000206c`
- `0x1800020f4`
- `0x180003300`
- `0x180004048`
- `0x180007080`
- `0x180007ea0`
- `0x180008490`
- `0x1800084f0`
- `0x18000e490`
- `0x18001ee64`
- `0x18001f2e4`
- `0x18001f530`
- `0x18002df78`
- `0x18002ea74`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f61f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f68d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f753`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f875`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f8de`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f61f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f68d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f753`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f875`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f8de`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CQueryAllWinSAT::get_AllXML(
        CQueryAllWinSAT *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNodeList **a4)
{
  __int64 result; // rax
  __int64 v8; // rdx
  int WinSATDataStoreDir; // ebx
  CSupportErrorInfo *v10; // rcx
  __int64 v11; // rcx
  int AllWinSATAssessmentFileNames; // ebx
  char v13; // bl
  mlib *v14; // rcx
  unsigned __int16 v15; // r9
  const unsigned __int16 *v16; // rax
  CSupportErrorInfo *v17; // rcx
  __int64 v18; // rcx
  int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rbx
  mlib *v22; // rcx
  unsigned __int16 v23; // r9
  const unsigned __int16 *v24; // rax
  CSupportErrorInfo *v25; // rcx
  __int64 v26; // rcx
  const unsigned __int16 *v27; // rdx
  HINSTANCE v28; // [rsp+20h] [rbp-78h]
  HINSTANCE v29; // [rsp+20h] [rbp-78h]
  __int64 v30; // [rsp+30h] [rbp-68h] BYREF
  __int128 v31; // [rsp+38h] [rbp-60h] BYREF
  __int64 v32; // [rsp+48h] [rbp-50h]
  __int64 v33; // [rsp+50h] [rbp-48h] BYREF
  struct HINSTANCE__ v34[2]; // [rsp+58h] [rbp-40h] BYREF
  _BYTE v35[8]; // [rsp+60h] [rbp-38h] BYREF
  _QWORD *v36[2]; // [rsp+68h] [rbp-30h] BYREF
  __int64 v37; // [rsp+78h] [rbp-20h] BYREF
  const unsigned __int16 *v38; // [rsp+80h] [rbp-18h]
  char v39; // [rsp+B8h] [rbp+20h] BYREF

  v36[1] = (_QWORD *)-2LL;
  if ( !a4 )
    return 2147500037LL;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v35,
      a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v34,
      v8);
    v33 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v39,
      260);
    WinSATDataStoreDir = DataStoreReader::GetWinSATDataStoreDir((__int64)&v39);
    if ( WinSATDataStoreDir >= 0 )
    {
      v31 = 0;
      v32 = 0;
      AllWinSATAssessmentFileNames = DataStoreReader::GetAllWinSATAssessmentFileNames((__int64)&v39, &v31);
      if ( AllWinSATAssessmentFileNames >= 0 )
      {
        if ( *((_QWORD *)&v31 + 1) == (_QWORD)v31 )
        {
          if ( (_QWORD)v31 )
          {
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
              v11,
              v31,
              *((_QWORD *)&v31 + 1));
            operator delete((void *)v31);
            v31 = 0;
            v32 = 0;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
          result = 2147745810LL;
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v30,
            L"WinsatAssessments");
          v13 = mlib::XmlDOM::LoadManyFilesIntoOneDocument((__int64)&v30, (__int64)&v31, &v33);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v30);
          if ( v13 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v36,
              a3);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v30,
              a2);
            v19 = mlib::XmlDOM::SelectXml(v33, (__int64)&v30, v36, a4, (__int64)v34);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v30);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v36);
            if ( v19 >= 0 )
            {
              if ( (_QWORD)v31 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v20,
                  v31,
                  *((_QWORD *)&v31 + 1));
                operator delete((void *)v31);
                v31 = 0;
                v32 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
              result = 0;
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v30,
                1024);
              v21 = *(_QWORD *)(*(_QWORD *)&v34[0].unused + 24LL);
              v24 = mlib::MUIStr_(v22, (const char *)0x238, 110, v23, v29);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
                &v30,
                v24,
                v21);
              CSupportErrorInfo::SetErrorInfo(
                v25,
                *(const unsigned __int16 **)(v30 + 24),
                &IID_IQueryAllWinSATAssessments);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v30);
              if ( (_QWORD)v31 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v26,
                  v31,
                  *((_QWORD *)&v31 + 1));
                operator delete((void *)v31);
                v31 = 0;
                v32 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
              result = 2147500037LL;
            }
          }
          else
          {
            v16 = mlib::MUIStr_(v14, (const char *)0x22C, 109, v15, v28);
            CSupportErrorInfo::SetErrorInfo(v17, v16, &IID_IQueryAllWinSATAssessments);
            if ( (_QWORD)v31 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                v18,
                v31,
                *((_QWORD *)&v31 + 1));
              operator delete((void *)v31);
              v31 = 0;
              v32 = 0;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
            result = 2147549183LL;
          }
        }
      }
      else
      {
        if ( (_QWORD)v31 )
        {
          std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
            v11,
            v31,
            *((_QWORD *)&v31 + 1));
          operator delete((void *)v31);
          v31 = 0;
          v32 = 0;
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
        result = (unsigned int)AllWinSATAssessmentFileNames;
      }
    }
    else
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v35);
      result = (unsigned int)WinSATDataStoreDir;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( mlib::MSError v37 )
  {
    v27 = &String2;
    if ( v38 )
      v27 = v38;
    CSupportErrorInfo::SetErrorInfo(v10, v27, &IID_IQueryAllWinSATAssessments);
    mlib::MSError::~MSError((mlib::MSError *)&v37);
    return 2147500037LL;
  }
  catch ( mlib::MUIError )
  {
    CSupportErrorInfo::SetErrorInfo(v10, L"Cannot load string from resouce.", &IID_IQueryAllWinSATAssessments);
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
0x18001f530  mov     rax, rsp
0x18001f533  push    r14
0x18001f535  sub     rsp, 90h
0x18001f53c  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001f544  mov     [rax+8], rbx
0x18001f548  mov     [rax+10h], rsi
0x18001f54c  mov     [rax+18h], rdi
0x18001f550  mov     rsi, r9
0x18001f553  mov     rdi, r8
0x18001f556  mov     r14, rdx
0x18001f559  test    r9, r9
0x18001f55c  jnz     short loc_18001F568
0x18001f55e  mov     eax, 80004005h
0x18001f563  jmp     loc_18001F937
0x18001f568  lea     rcx, [rsp+98h+var_38]
0x18001f56d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18001f572  nop
0x18001f573  lea     rcx, [rsp+98h+var_40]
0x18001f578  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18001f57d  nop
0x18001f57e  and     [rsp+98h+var_48], 0
0x18001f584  mov     edx, 104h
0x18001f589  lea     rcx, [rsp+98h+arg_18]
0x18001f591  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001f596  nop
0x18001f597  lea     rcx, [rsp+98h+arg_18]
0x18001f59f  call    ?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18001f5a4  mov     ebx, eax
0x18001f5a6  test    eax, eax
0x18001f5a8  jns     short loc_18001F5DF
0x18001f5aa  lea     rcx, [rsp+98h+arg_18]
0x18001f5b2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f5b7  nop
0x18001f5b8  lea     rcx, [rsp+98h+var_48]
0x18001f5bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f5c2  nop
0x18001f5c3  lea     rcx, [rsp+98h+var_40]
0x18001f5c8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f5cd  nop
0x18001f5ce  lea     rcx, [rsp+98h+var_38]
0x18001f5d3  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f5d8  mov     eax, ebx
0x18001f5da  jmp     loc_18001F937
0x18001f5df  xorps   xmm0, xmm0
0x18001f5e2  movdqu  [rsp+98h+var_60], xmm0
0x18001f5e8  and     [rsp+98h+var_50], 0
0x18001f5ee  lea     rdx, [rsp+98h+var_60]
0x18001f5f3  lea     rcx, [rsp+98h+arg_18]
0x18001f5fb  call    ?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z; DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,DataStoreID,AssessmentTimeTaken)
0x18001f600  mov     ebx, eax
0x18001f602  test    eax, eax
0x18001f604  jns     short loc_18001F66F
0x18001f606  mov     rdx, qword ptr [rsp+98h+var_60]
0x18001f60b  test    rdx, rdx
0x18001f60e  jz      short loc_18001F63A
0x18001f610  mov     r8, qword ptr [rsp+98h+var_60+8]
0x18001f615  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f61a  mov     rcx, qword ptr [rsp+98h+var_60]
0x18001f61f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f626  nop     dword ptr [rax+rax+00h]
0x18001f62b  xorps   xmm0, xmm0
0x18001f62e  movdqu  [rsp+98h+var_60], xmm0
0x18001f634  and     [rsp+98h+var_50], 0
0x18001f63a  lea     rcx, [rsp+98h+arg_18]
0x18001f642  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f647  nop
0x18001f648  lea     rcx, [rsp+98h+var_48]
0x18001f64d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f652  nop
0x18001f653  lea     rcx, [rsp+98h+var_40]
0x18001f658  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f65d  nop
0x18001f65e  lea     rcx, [rsp+98h+var_38]
0x18001f663  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f668  mov     eax, ebx
0x18001f66a  jmp     loc_18001F937
0x18001f66f  mov     r8, qword ptr [rsp+98h+var_60+8]
0x18001f674  mov     rdx, qword ptr [rsp+98h+var_60]
0x18001f679  cmp     r8, rdx
0x18001f67c  jnz     short loc_18001F6E0
0x18001f67e  test    rdx, rdx
0x18001f681  jz      short loc_18001F6A8
0x18001f683  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f688  mov     rcx, qword ptr [rsp+98h+var_60]
0x18001f68d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f694  nop     dword ptr [rax+rax+00h]
0x18001f699  xorps   xmm0, xmm0
0x18001f69c  movdqu  [rsp+98h+var_60], xmm0
0x18001f6a2  and     [rsp+98h+var_50], 0
0x18001f6a8  lea     rcx, [rsp+98h+arg_18]
0x18001f6b0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f6b5  nop
0x18001f6b6  lea     rcx, [rsp+98h+var_48]
0x18001f6bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f6c0  nop
0x18001f6c1  lea     rcx, [rsp+98h+var_40]
0x18001f6c6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f6cb  nop
0x18001f6cc  lea     rcx, [rsp+98h+var_38]
0x18001f6d1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f6d6  mov     eax, 80040012h
0x18001f6db  jmp     loc_18001F937
0x18001f6e0  lea     rdx, aWinsatassessme; "WinsatAssessments"
0x18001f6e7  lea     rcx, [rsp+98h+var_68]
0x18001f6ec  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f6f1  nop
0x18001f6f2  lea     r8, [rsp+98h+var_48]
0x18001f6f7  lea     rdx, [rsp+98h+var_60]
0x18001f6fc  lea     rcx, [rsp+98h+var_68]
0x18001f701  call    ?LoadManyFilesIntoOneDocument@XmlDOM@mlib@@SA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAPEAUIXMLDOMNode@@@Z; mlib::XmlDOM::LoadManyFilesIntoOneDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> const &,IXMLDOMNode * *)
0x18001f706  mov     bl, al
0x18001f708  lea     rcx, [rsp+98h+var_68]
0x18001f70d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f712  test    bl, bl
0x18001f714  jnz     loc_18001F7A6
0x18001f71a  mov     edx, 22Ch; char *
0x18001f71f  mov     r8d, 6Dh ; 'm'; int
0x18001f725  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x18001f72a  lea     r8, IID_IQueryAllWinSATAssessments; struct _GUID *
0x18001f731  mov     rdx, rax; unsigned __int16 *
0x18001f734  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x18001f739  nop
0x18001f73a  mov     rdx, qword ptr [rsp+98h+var_60]
0x18001f73f  test    rdx, rdx
0x18001f742  jz      short loc_18001F76E
0x18001f744  mov     r8, qword ptr [rsp+98h+var_60+8]
0x18001f749  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f74e  mov     rcx, qword ptr [rsp+98h+var_60]
0x18001f753  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f75a  nop     dword ptr [rax+rax+00h]
0x18001f75f  xorps   xmm0, xmm0
0x18001f762  movdqu  [rsp+98h+var_60], xmm0
0x18001f768  and     [rsp+98h+var_50], 0
0x18001f76e  lea     rcx, [rsp+98h+arg_18]
0x18001f776  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f77b  nop
0x18001f77c  lea     rcx, [rsp+98h+var_48]
0x18001f781  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f786  nop
0x18001f787  lea     rcx, [rsp+98h+var_40]
0x18001f78c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f791  nop
0x18001f792  lea     rcx, [rsp+98h+var_38]
0x18001f797  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f79c  mov     eax, 8000FFFFh
0x18001f7a1  jmp     loc_18001F937
0x18001f7a6  mov     rdx, rdi
0x18001f7a9  lea     rcx, [rsp+98h+var_30]
0x18001f7ae  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f7b3  nop
0x18001f7b4  mov     rdx, r14
0x18001f7b7  lea     rcx, [rsp+98h+var_68]
0x18001f7bc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f7c1  nop
0x18001f7c2  lea     rax, [rsp+98h+var_40]
0x18001f7c7  mov     [rsp+98h+var_78], rax; HINSTANCE
0x18001f7cc  mov     r9, rsi
0x18001f7cf  lea     r8, [rsp+98h+var_30]
0x18001f7d4  lea     rdx, [rsp+98h+var_68]
0x18001f7d9  mov     rcx, [rsp+98h+var_48]
0x18001f7de  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f7e3  mov     ebx, eax
0x18001f7e5  lea     rcx, [rsp+98h+var_68]
0x18001f7ea  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f7ef  nop
0x18001f7f0  lea     rcx, [rsp+98h+var_30]
0x18001f7f5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f7fa  test    ebx, ebx
0x18001f7fc  jns     loc_18001F8C5
0x18001f802  mov     edx, 400h
0x18001f807  lea     rcx, [rsp+98h+var_68]
0x18001f80c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001f811  nop
0x18001f812  mov     rax, qword ptr [rsp+98h+var_40.unused]
0x18001f817  mov     rbx, [rax+18h]
0x18001f81b  mov     edx, 238h; char *
0x18001f820  mov     r8d, 6Eh ; 'n'; int
0x18001f826  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x18001f82b  mov     r8, rbx
0x18001f82e  mov     rdx, rax
0x18001f831  lea     rcx, [rsp+98h+var_68]
0x18001f836  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x18001f83b  mov     rax, [rsp+98h+var_68]
0x18001f840  lea     r8, IID_IQueryAllWinSATAssessments; struct _GUID *
0x18001f847  mov     rdx, [rax+18h]; unsigned __int16 *
0x18001f84b  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x18001f850  nop
0x18001f851  lea     rcx, [rsp+98h+var_68]
0x18001f856  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f85b  nop
0x18001f85c  mov     rdx, qword ptr [rsp+98h+var_60]
0x18001f861  test    rdx, rdx
0x18001f864  jz      short loc_18001F890
0x18001f866  mov     r8, qword ptr [rsp+98h+var_60+8]
0x18001f86b  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f870  mov     rcx, qword ptr [rsp+98h+var_60]
0x18001f875  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f87c  nop     dword ptr [rax+rax+00h]
0x18001f881  xorps   xmm0, xmm0
0x18001f884  movdqu  [rsp+98h+var_60], xmm0
0x18001f88a  and     [rsp+98h+var_50], 0
0x18001f890  lea     rcx, [rsp+98h+arg_18]
0x18001f898  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f89d  nop
0x18001f89e  lea     rcx, [rsp+98h+var_48]
0x18001f8a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f8a8  nop
0x18001f8a9  lea     rcx, [rsp+98h+var_40]
0x18001f8ae  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f8b3  nop
0x18001f8b4  lea     rcx, [rsp+98h+var_38]
0x18001f8b9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f8be  mov     eax, 80004005h
0x18001f8c3  jmp     short loc_18001F937
0x18001f8c5  mov     rdx, qword ptr [rsp+98h+var_60]
0x18001f8ca  test    rdx, rdx
0x18001f8cd  jz      short loc_18001F8F9
0x18001f8cf  mov     r8, qword ptr [rsp+98h+var_60+8]
0x18001f8d4  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f8d9  mov     rcx, qword ptr [rsp+98h+var_60]
0x18001f8de  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f8e5  nop     dword ptr [rax+rax+00h]
0x18001f8ea  xorps   xmm0, xmm0
0x18001f8ed  movdqu  [rsp+98h+var_60], xmm0
0x18001f8f3  and     [rsp+98h+var_50], 0
0x18001f8f9  lea     rcx, [rsp+98h+arg_18]
0x18001f901  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f906  nop
0x18001f907  lea     rcx, [rsp+98h+var_48]
0x18001f90c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f911  nop
0x18001f912  lea     rcx, [rsp+98h+var_40]
0x18001f917  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f91c  nop
0x18001f91d  lea     rcx, [rsp+98h+var_38]
0x18001f922  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f927  xor     eax, eax
0x18001f929  jmp     short loc_18001F937
0x18001f92b  mov     eax, 8007000Eh
0x18001f930  jmp     short loc_18001F937
0x18001f932  mov     eax, 80004005h
0x18001f937  lea     r11, [rsp+98h+var_8]
0x18001f93f  mov     rbx, [r11+10h]
0x18001f943  mov     rsi, [r11+18h]
0x18001f947  mov     rdi, [r11+20h]
0x18001f94b  mov     rsp, r11
0x18001f94e  pop     r14
0x18001f950  retn
0x18001f952  jmp     short loc_18001F932
```
