# WindowsPerformanceRecorder::CWPRControl::CWPRControl(void)

- ea: `0x1800368dc`
- end: `0x1800369fd`
- name: `??0CWPRControl@WindowsPerformanceRecorder@@QEAA@XZ`
- size: `289`
- prototype: `WindowsPerformanceRecorder::CWPRControl *__fastcall(WindowsPerformanceRecorder::CWPRControl *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009a84`

## callees

- `0x180009b40`
- `0x18000c514`
- `0x18001d8fc`
- `0x18001e6e0`
- `0x180020b08`
- `0x180035760`
- `0x1800368dc`
- `0x180044210`
- `0x180046b74`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003698c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003698c`

## string_xrefs

- `0x1800368fe`: `api-ms-win-eventing-controller-l1-1-0.dll`

## pseudocode

```c
WindowsPerformanceRecorder::CWPRControl *__fastcall WindowsPerformanceRecorder::CWPRControl::CWPRControl(
        WindowsPerformanceRecorder::CWPRControl *this)
{
  char *v2; // rdi
  BSTR v3; // rax
  int v4; // edi
  const char *v6; // [rsp+28h] [rbp-30h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = L"api-ms-win-eventing-controller-l1-1-0.dll";
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 5) = "EnableTraceEx2";
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  v2 = (char *)this + 80;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 15) = 0;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>((_QWORD *)this + 10);
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *,std::less<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,std::allocator<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,0>>::_Alloc_sentinel_and_proxy();
  v2[40] = 0;
  ATL::CComAutoCriticalSection::CComAutoCriticalSection((WindowsPerformanceRecorder::CWPRControl *)((char *)this + 128));
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy();
  v3 = SysAllocString(L"WPR_DEFAULT");
  *((_QWORD *)this + 23) = v3;
  if ( !v3 )
    ATL::AtlThrowImpl(-2147024882);
  Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 32);
  v4 = WindowsPerformanceRecorder::CEventProvidersCollection::Initialize((WindowsPerformanceRecorder::CEventProvidersCollection *)v2);
  if ( v4 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"CWPRControl",
      (const char *)0x7A,
      v4,
      "CEventProvidersCollection Initialization error",
      v6);
    ATL::AtlThrowImpl(v4);
  }
  return this;
}

```

## disassembly

```asm
0x1800368dc  mov     r11, rsp
0x1800368df  mov     [r11+8], rcx
0x1800368e3  push    rbp
0x1800368e4  push    rsi
0x1800368e5  push    rdi
0x1800368e6  sub     rsp, 40h
0x1800368ea  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x1800368f2  mov     [r11+20h], rbx
0x1800368f6  mov     rbx, rcx
0x1800368f9  xor     ebp, ebp
0x1800368fb  mov     [rcx], rbp
0x1800368fe  lea     rax, aApiMsWinEventi_4; "api-ms-win-eventing-controller-l1-1-0.d"...
0x180036905  mov     [rcx+8], rax
0x180036909  mov     [rcx+10h], rbp
0x18003690d  mov     [rcx+18h], bpl
0x180036911  mov     [rcx+20h], rcx
0x180036915  lea     rax, aEnabletraceex2; "EnableTraceEx2"
0x18003691c  mov     [rcx+28h], rax
0x180036920  mov     [rcx+30h], rbp
0x180036924  mov     [rcx+38h], bpl
0x180036928  mov     [rcx+40h], rbp
0x18003692c  mov     [rcx+48h], rbp
0x180036930  lea     rdi, [rcx+50h]
0x180036934  mov     [rdi], rbp
0x180036937  mov     [rdi+8], rbp
0x18003693b  mov     [rdi+10h], rbp
0x18003693f  mov     [rdi+28h], rbp
0x180036943  mov     [r11+10h], rdi
0x180036947  mov     rcx, rdi
0x18003694a  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x18003694f  nop
0x180036950  lea     rcx, [rdi+18h]
0x180036954  mov     [rcx], rbp
0x180036957  mov     [rcx+8], rbp
0x18003695b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@U?$less@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *,std::less<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,std::allocator<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,0>>::_Alloc_sentinel_and_proxy(void)
0x180036960  mov     [rdi+28h], bpl
0x180036964  lea     rcx, [rbx+80h]; this
0x18003696b  call    ??0CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)
0x180036970  nop
0x180036971  lea     rcx, [rbx+0A8h]
0x180036978  mov     [rcx], rbp
0x18003697b  mov     [rcx+8], rbp
0x18003697f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@UCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@U?$less@UCFileKey@Impl@WindowsPerformanceRecorder@@@std@@V?$allocator@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@7@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180036984  nop
0x180036985  lea     rcx, psz; "WPR_DEFAULT"
0x18003698c  call    cs:__imp_SysAllocString
0x180036992  mov     [rbx+0B8h], rax
0x180036999  test    rax, rax
0x18003699c  jnz     short loc_1800369A9
0x18003699e  mov     ecx, 8007000Eh; int
0x1800369a3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800369a9  lea     rcx, [rbx+20h]
0x1800369ad  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800369b2  mov     rcx, rdi; this
0x1800369b5  call    ?Initialize@CEventProvidersCollection@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CEventProvidersCollection::Initialize(void)
0x1800369ba  mov     edi, eax
0x1800369bc  test    eax, eax
0x1800369be  jns     short loc_1800369ED
0x1800369c0  lea     rax, aCeventprovider; "CEventProvidersCollection Initializatio"...
0x1800369c7  mov     [rsp+58h+Format], rax; Format
0x1800369cc  mov     r9d, edi; unsigned int
0x1800369cf  mov     r8d, 7Ah ; 'z'; char *
0x1800369d5  lea     rdx, aCwprcontrol; "CWPRControl"
0x1800369dc  lea     ecx, [r8-78h]; this
0x1800369e0  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800369e5  mov     ecx, edi; int
0x1800369e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800369ed  mov     rax, rbx
0x1800369f0  mov     rbx, [rsp+58h+arg_18]
0x1800369f5  add     rsp, 40h
0x1800369f9  pop     rdi
0x1800369fa  pop     rsi
0x1800369fb  pop     rbp
0x1800369fc  retn
```
