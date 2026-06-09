# WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(ushort *,bool)

- ea: `0x1800218a8`
- end: `0x180021a82`
- name: `?LoadProfileFromFileOrString@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEAG_N@Z`
- size: `474`
- prototype: `__int64 __fastcall(char ***this, unsigned __int16 *, bool)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x180002f00`
- `0x180018e80`
- `0x180018f80`
- `0x18001a6d0`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x180013c6c`
- `0x18001c798`
- `0x180021810`
- `0x1800218a8`
- `0x180021a88`
- `0x180021b7c`
- `0x1800226d0`
- `0x1800234f0`
- `0x18002d070`
- `0x180035084`
- `0x180039244`
- `0x18004376c`
- `0x180044210`
- `0x18004ed10`
- `0x18005766c`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800218d9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800218d9`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(
        char ***this,
        unsigned __int16 *a2,
        bool a3)
{
  __int64 result; // rax
  WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *v7; // rax
  char *v8; // rax
  char *v9; // rdi
  void *v10; // rax
  int v11; // eax
  char **v12; // rdx
  XmlObjBase *v13; // rbx
  unsigned int v14; // edi
  ATL::CAtlException *v15; // [rsp+28h] [rbp-40h] BYREF
  char v16[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h]
  char v18[16]; // [rsp+40h] [rbp-28h] BYREF
  char *v19; // [rsp+78h] [rbp+10h] BYREF
  XmlObjBase *v20; // [rsp+88h] [rbp+20h]

  if ( !a2 || !SysStringLen(a2) )
    return 3310880513LL;
  result = WindowsPerformanceRecorder::CProfilesCache::ValidateProfileFromFileOrString(
             (WindowsPerformanceRecorder::CProfilesCache *)this,
             a2,
             a3,
             0);
  if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -2147024846 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v7 = (WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *)operator new(0x60u);
      v8 = (char *)WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection::CBaseProfileElementCollection(v7);
      v9 = v8;
      v19 = v8;
      if ( a3 )
      {
        v10 = (void *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        &v19,
                        a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          v16,
          v10);
        v17 = 0;
        v11 = WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime((WindowsPerformanceRecorder::Impl::CFileKey *)v16);
        if ( v11 < 0 )
          ATL::AtlThrowImpl(v11);
        *(_QWORD *)(*(_QWORD *)std::map<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>::_Try_emplace<WindowsPerformanceRecorder::Impl::CFileKey const &,>(
                                 this + 1,
                                 v18,
                                 v16)
                  + 48LL) = v9;
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v16);
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
      }
      else
      {
        v12 = this[4];
        if ( v12 == this[5] )
        {
          std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(
            this + 3,
            v12,
            &v19);
          v9 = v19;
        }
        else
        {
          *v12 = v8;
          ++this[4];
        }
      }
      v19 = (char *)operator new(0x58u);
      v13 = (XmlObjBase *)((_QWORD (__stdcall *)(WindowsPerformanceRecorder::CProfileXmlliteParser *, const unsigned __int16 *))WindowsPerformanceRecorder::CProfileXmlliteParser::CProfileXmlliteParser)(
                            (WindowsPerformanceRecorder::CProfileXmlliteParser *)v19,
                            L"WindowsPerformanceRecorder");
      v20 = v13;
      WindowsPerformanceRecorder::CProfileXmlliteParser::m_pProfilesCache = (struct WindowsPerformanceRecorder::CProfilesCache *)this;
      *((_QWORD *)v13 + 10) = v9;
      if ( a3 )
      {
        v14 = XmlObjBase::ReadFromFile(v13, a2);
      }
      else
      {
        v14 = XmlObjBase::ReadFromString(v13, a2);
        if ( v14 == -1072894461 )
        {
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            &v19,
            a2);
          v14 = XmlObjBase::ReadFromString(v13, v19);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
        }
      }
      (*(void (__fastcall **)(XmlObjBase *, __int64))(*(_QWORD *)v13 + 88LL))(v13, 1);
      result = v14;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        result = 2147942414LL;
        __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_180021A5A);
        return result;
      }
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v15) )
      {
        result = *(unsigned int *)v15;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180021A61);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800218a8  mov     rax, rsp
0x1800218ab  push    rdi
0x1800218ac  push    r14
0x1800218ae  push    r15
0x1800218b0  sub     rsp, 50h
0x1800218b4  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800218bc  mov     [rax+8], rbx
0x1800218c0  mov     [rax+18h], rsi
0x1800218c4  mov     r15b, r8b
0x1800218c7  mov     rsi, rdx
0x1800218ca  mov     r14, rcx
0x1800218cd  test    rdx, rdx
0x1800218d0  jz      loc_180021A67
0x1800218d6  mov     rcx, rdx; pbstr
0x1800218d9  call    cs:__imp_SysStringLen
0x1800218df  test    eax, eax
0x1800218e1  jz      loc_180021A67
0x1800218e7  xor     r9d, r9d; bool
0x1800218ea  mov     r8b, r15b; bool
0x1800218ed  mov     rdx, rsi; psz
0x1800218f0  mov     rcx, r14; this
0x1800218f3  call    ?ValidateProfileFromFileOrString@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEAG_N1@Z; WindowsPerformanceRecorder::CProfilesCache::ValidateProfileFromFileOrString(ushort *,bool,bool)
0x1800218f8  mov     edx, 80000000h
0x1800218fd  lea     ecx, [rax+rdx]
0x180021900  test    edx, ecx
0x180021902  jnz     short loc_18002190F
0x180021904  cmp     eax, 80070032h
0x180021909  jnz     loc_180021A6C
0x18002190f  mov     ecx, 60h ; '`'; Size
0x180021914  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021919  mov     rcx, rax; this
0x18002191c  call    ??0CBaseProfileElementCollection@CBaseProfileElement@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection::CBaseProfileElementCollection(void)
0x180021921  mov     rdi, rax
0x180021924  mov     [rsp+68h+arg_8], rax
0x180021929  test    r15b, r15b
0x18002192c  jz      short loc_18002199C
0x18002192e  mov     rdx, rsi
0x180021931  lea     rcx, [rsp+68h+arg_8]
0x180021936  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002193b  nop
0x18002193c  mov     rdx, rax; void *
0x18002193f  lea     rcx, [rsp+68h+var_38]; void *
0x180021944  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180021949  nop
0x18002194a  xor     eax, eax
0x18002194c  mov     [rsp+68h+var_30], rax
0x180021951  lea     rcx, [rsp+68h+var_38]; this
0x180021956  call    ?SetFileTime@CFileKey@Impl@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime(void)
0x18002195b  test    eax, eax
0x18002195d  jns     short loc_180021967
0x18002195f  mov     ecx, eax; int
0x180021961  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180021967  lea     rcx, [r14+8]
0x18002196b  lea     r8, [rsp+68h+var_38]
0x180021970  lea     rdx, [rsp+68h+var_28]
0x180021975  call    ??$_Try_emplace@AEBUCFileKey@Impl@WindowsPerformanceRecorder@@$$V@?$map@UCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@U?$less@UCFileKey@Impl@WindowsPerformanceRecorder@@@std@@V?$allocator@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@7@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@PEAX@std@@_N@1@AEBUCFileKey@Impl@WindowsPerformanceRecorder@@@Z; std::map<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>::_Try_emplace<WindowsPerformanceRecorder::Impl::CFileKey const &,>(WindowsPerformanceRecorder::Impl::CFileKey const &)
0x18002197a  mov     rax, [rax]
0x18002197d  mov     [rax+30h], rdi
0x180021981  lea     rcx, [rsp+68h+var_38]; this
0x180021986  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18002198b  nop
0x18002198c  mov     rcx, [rsp+68h+arg_8]
0x180021991  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021995  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002199a  jmp     short loc_1800219C3
0x18002199c  lea     rcx, [r14+18h]
0x1800219a0  mov     rdx, [rcx+8]
0x1800219a4  cmp     rdx, [rcx+10h]
0x1800219a8  jz      short loc_1800219B4
0x1800219aa  mov     [rdx], rdi
0x1800219ad  add     qword ptr [rcx+8], 8
0x1800219b2  jmp     short loc_1800219C3
0x1800219b4  lea     r8, [rsp+68h+arg_8]
0x1800219b9  call    ??$_Emplace_reallocate@AEBQEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@?$vector@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAPEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAPEAU234@AEBQEAU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(WindowsPerformanceRecorder::CETWProperties::CEventSession * * const,WindowsPerformanceRecorder::CETWProperties::CEventSession * const &)
0x1800219be  mov     rdi, [rsp+68h+arg_8]
0x1800219c3  mov     ecx, 58h ; 'X'; Size
0x1800219c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800219cd  mov     [rsp+68h+arg_8], rax
0x1800219d2  lea     rdx, aWindowsperform_2; "WindowsPerformanceRecorder"
0x1800219d9  mov     rcx, rax; this
0x1800219dc  call    ??0CProfileXmlliteParser@WindowsPerformanceRecorder@@QEAA@PEBG@Z; WindowsPerformanceRecorder::CProfileXmlliteParser::CProfileXmlliteParser(ushort const *)
0x1800219e1  mov     rbx, rax
0x1800219e4  mov     [rsp+68h+arg_18], rax
0x1800219ec  mov     cs:?m_pProfilesCache@CProfileXmlliteParser@WindowsPerformanceRecorder@@0PEAVCProfilesCache@2@EA, r14; WindowsPerformanceRecorder::CProfilesCache * WindowsPerformanceRecorder::CProfileXmlliteParser::m_pProfilesCache
0x1800219f3  mov     [rax+50h], rdi
0x1800219f7  mov     rdx, rsi; unsigned __int16 *
0x1800219fa  mov     rcx, rax; this
0x1800219fd  test    r15b, r15b
0x180021a00  jz      short loc_180021A0B
0x180021a02  call    ?ReadFromFile@XmlObjBase@@QEAAJPEBG@Z; XmlObjBase::ReadFromFile(ushort const *)
0x180021a07  mov     edi, eax
0x180021a09  jmp     short loc_180021A41
0x180021a0b  call    ?ReadFromString@XmlObjBase@@QEAAJPEBG@Z; XmlObjBase::ReadFromString(ushort const *)
0x180021a10  mov     edi, eax
0x180021a12  cmp     eax, 0C00CEE03h
0x180021a17  jnz     short loc_180021A41
0x180021a19  mov     rdx, rsi
0x180021a1c  lea     rcx, [rsp+68h+arg_8]
0x180021a21  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x180021a26  nop
0x180021a27  mov     rdx, [rsp+68h+arg_8]; char *
0x180021a2c  mov     rcx, rbx; this
0x180021a2f  call    ?ReadFromString@XmlObjBase@@QEAAJPEBD@Z; XmlObjBase::ReadFromString(char const *)
0x180021a34  mov     edi, eax
0x180021a36  lea     rcx, [rsp+68h+arg_8]; this
0x180021a3b  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180021a40  nop
0x180021a41  mov     rcx, [rbx]
0x180021a44  mov     rax, [rcx+58h]
0x180021a48  mov     edx, 1
0x180021a4d  mov     rcx, rbx
0x180021a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a55  nop
0x180021a56  mov     eax, edi
0x180021a58  jmp     short loc_180021A6C
0x180021a5a  mov     eax, 8007000Eh
0x180021a5f  jmp     short loc_180021A65
0x180021a61  mov     eax, dword ptr [rsp+68h+arg_8]
0x180021a65  jmp     short loc_180021A6C
0x180021a67  mov     eax, 0C5580701h
0x180021a6c  lea     r11, [rsp+68h+var_18]
0x180021a71  mov     rbx, [r11+20h]
0x180021a75  mov     rsi, [r11+30h]
0x180021a79  mov     rsp, r11
0x180021a7c  pop     r15
0x180021a7e  pop     r14
0x180021a80  pop     rdi
0x180021a81  retn
```
