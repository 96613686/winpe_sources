# WindowsPerformanceRecorder::CControlManager::QueryXML(ushort * *,short)

- ea: `0x1800326e0`
- end: `0x1800328a1`
- name: `?QueryXML@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAPEAGF@Z`
- size: `449`
- prototype: `int(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int16 **, __int16)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x18000eeb0`
- `0x18001c458`
- `0x18001c8bc`
- `0x18001e6e0`
- `0x18001ea58`
- `0x1800326e0`
- `0x1800328a8`
- `0x1800328f8`
- `0x180048c30`
- `0x180049044`
- `0x18004b128`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003288d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003288d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327ea`

## string_xrefs

- `0x18003285c`: `QueryXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::QueryXML(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 **a2,
        __int16 a3)
{
  unsigned __int16 **v4; // rdi
  BSTR *v6; // r14
  int v7; // ebx
  unsigned int v9; // esi
  __int64 v10; // rax
  const char *v11; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-58h] BYREF
  BSTR *v13; // [rsp+38h] [rbp-50h]
  _BYTE v14[8]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+48h] [rbp-40h]
  ATL::CAtlException *v16; // [rsp+50h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int16 **v18; // [rsp+98h] [rbp+10h]
  const char *v19; // [rsp+A8h] [rbp+20h] BYREF

  v18 = a2;
  v15 = -2;
  v4 = a2;
  lpCriticalSection = 0;
  v6 = (BSTR *)((char *)this - 184);
  v13 = (BSTR *)((char *)this - 184);
  v7 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(
         &lpCriticalSection,
         (char *)this - 184);
  if ( v7 >= 0 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this - 22) + 24LL))((char *)this - 176);
    WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo((char *)this - 80);
    WindowsPerformanceRecorder::CControlManager::QueryXML_::_2_::CPerfEventMacro::CPerfEventMacro(v14);
    v9 = v4 == 0 ? 0x80004003 : 0;
    v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    try
    {
      v11 = (const char *)(v10 + 24);
      v19 = (const char *)(v10 + 24);
      if ( v4 )
      {
        bstrString = 0;
        v9 = WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(v6, a3 == -1, &bstrString, v4, 0);
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, bstrString);
        SysFreeString(bstrString);
        v11 = v19;
      }
    }
    catch ( ATL::CAtlException *v16 )
    {
      LODWORD(bstrString) = *(_DWORD *)v16;
      v4 = v18;
      v9 = (unsigned int)bstrString;
      v11 = v19;
      v6 = v13;
    }
    if ( (v9 & 0x80000000) != 0 )
    {
      if ( v4 )
        *v4 = 0;
      WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(v6, v9, 1, &IID_IControlManager, v11);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "QueryXML",
        (const char *)0x905,
        v9,
        "%ws",
        v11);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
    WindowsPerformanceRecorder::CControlManager::QueryXML_::_2_::CPerfEventMacro::_CPerfEventMacro(v14);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return v9;
  }
  else
  {
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&lpCriticalSection);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1800326e0  mov     rax, rsp
0x1800326e3  mov     [rax+10h], rdx
0x1800326e7  push    rbx
0x1800326e8  push    rsi
0x1800326e9  push    rdi
0x1800326ea  push    r14
0x1800326ec  push    r15
0x1800326ee  sub     rsp, 60h
0x1800326f2  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x1800326fa  movzx   r15d, r8w
0x1800326fe  mov     rdi, rdx
0x180032701  mov     rsi, rcx
0x180032704  mov     qword ptr [rax-58h], 0
0x18003270c  lea     r14, [rcx-0B8h]
0x180032713  mov     [rsp+88h+var_50], r14
0x180032718  mov     rdx, r14
0x18003271b  lea     rcx, [rax-58h]
0x18003271f  call    ??$Acquire@VCControlManager@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCControlManager@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(WindowsPerformanceRecorder::CControlManager *)
0x180032724  mov     ebx, eax
0x180032726  test    eax, eax
0x180032728  jns     short loc_18003273B
0x18003272a  lea     rcx, [rsp+88h+lpCriticalSection]; this
0x18003272f  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x180032734  mov     eax, ebx
0x180032736  jmp     loc_180032895
0x18003273b  lea     rcx, [rsi-0B0h]
0x180032742  mov     rax, [rcx]
0x180032745  mov     rax, [rax+18h]
0x180032749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003274e  lea     rcx, [rsi-50h]
0x180032752  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x180032757  lea     rcx, [rsp+88h+var_48]
0x18003275c  call    _WindowsPerformanceRecorder__CControlManager__QueryXML____2___CPerfEventMacro__CPerfEventMacro
0x180032761  nop
0x180032762  mov     rax, rdi
0x180032765  neg     rax
0x180032768  sbb     esi, esi
0x18003276a  not     esi
0x18003276c  and     esi, 80004003h
0x180032772  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180032779  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180032780  mov     rax, [rax+18h]
0x180032784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032789  lea     rbx, [rax+18h]
0x18003278d  mov     [rsp+88h+arg_18], rbx
0x180032795  test    rdi, rdi
0x180032798  jz      short loc_1800327F8
0x18003279a  mov     [rsp+88h+bstrString], 0
0x1800327a6  cmp     r15w, 0FFFFh
0x1800327ab  setz    dl; bool
0x1800327ae  mov     [rsp+88h+Format], 0; struct IProfileCollection **
0x1800327b7  mov     r9, rdi; unsigned __int16 **
0x1800327ba  lea     r8, [rsp+88h+bstrString]; unsigned __int16 **
0x1800327c2  mov     rcx, r14; this
0x1800327c5  call    ?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z; WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)
0x1800327ca  mov     esi, eax
0x1800327cc  mov     rdx, [rsp+88h+bstrString]
0x1800327d4  lea     rcx, [rsp+88h+arg_18]
0x1800327dc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800327e1  nop
0x1800327e2  mov     rcx, [rsp+88h+bstrString]; bstrString
0x1800327ea  call    cs:__imp_SysFreeString
0x1800327f0  mov     rbx, [rsp+88h+arg_18]
0x1800327f8  jmp     short loc_180032816
0x1800327fa  mov     rdi, [rsp+88h+arg_8]
0x180032802  mov     esi, dword ptr [rsp+88h+bstrString]
0x180032809  mov     rbx, [rsp+88h+arg_18]
0x180032811  mov     r14, [rsp+88h+var_50]
0x180032816  test    esi, esi
0x180032818  jns     short loc_18003286E
0x18003281a  test    rdi, rdi
0x18003281d  jz      short loc_180032826
0x18003281f  mov     qword ptr [rdi], 0
0x180032826  mov     [rsp+88h+Format], rbx
0x18003282b  lea     r9, IID_IControlManager
0x180032832  mov     r8d, 1
0x180032838  mov     edx, esi
0x18003283a  mov     rcx, r14
0x18003283d  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x180032842  mov     [rsp+88h+var_60], rbx; char *
0x180032847  lea     rax, aWs_0; "%ws"
0x18003284e  mov     [rsp+88h+Format], rax; Format
0x180032853  mov     r9d, esi; unsigned int
0x180032856  mov     r8d, 905h; char *
0x18003285c  lea     rdx, aQueryxml; "QueryXML"
0x180032863  mov     ecx, 2; this
0x180032868  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003286d  nop
0x18003286e  lea     rcx, [rbx-18h]; this
0x180032872  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032877  nop
0x180032878  lea     rcx, [rsp+88h+var_48]
0x18003287d  call    _WindowsPerformanceRecorder__CControlManager__QueryXML____2___CPerfEventMacro___CPerfEventMacro
0x180032882  nop
0x180032883  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180032888  test    rcx, rcx
0x18003288b  jz      short loc_180032893
0x18003288d  call    cs:__imp_LeaveCriticalSection
0x180032893  mov     eax, esi
0x180032895  add     rsp, 60h
0x180032899  pop     r15
0x18003289b  pop     r14
0x18003289d  pop     rdi
0x18003289e  pop     rsi
0x18003289f  pop     rbx
0x1800328a0  retn
```
