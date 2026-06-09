# WindowsPerformanceRecorder::CInstanceNameScopedData::CInstanceNameScopedData(ushort const *)

- ea: `0x180043f10`
- end: `0x180044088`
- name: `??0CInstanceNameScopedData@WindowsPerformanceRecorder@@QEAA@PEBG@Z`
- size: `376`
- prototype: `WindowsPerformanceRecorder::CInstanceNameScopedData *__fastcall(WindowsPerformanceRecorder::CInstanceNameScopedData *this, const char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800509a0`

## callees

- `0x180008330`
- `0x18000c514`
- `0x1800102d8`
- `0x18001c458`
- `0x18001c820`
- `0x18001e6e0`
- `0x180035760`
- `0x180043f10`
- `0x180044090`
- `0x180044210`
- `0x180046b74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043fb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044009`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f7a`

## string_xrefs

- `0x18004401b`: `Failed to Create SingletonEvent`
- `0x180044046`: `InstanceNameScopedData created`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
WindowsPerformanceRecorder::CInstanceNameScopedData *__fastcall WindowsPerformanceRecorder::CInstanceNameScopedData::CInstanceNameScopedData(
        WindowsPerformanceRecorder::CInstanceNameScopedData *this,
        const char *a2)
{
  DWORD LastError; // eax
  signed int v5; // eax
  char *v7; // [rsp+28h] [rbp-20h]
  LPCWSTR lpName; // [rsp+60h] [rbp+18h] BYREF

  ATL::CComAutoCriticalSection::CComAutoCriticalSection(this);
  *((_QWORD *)this + 5) = &WindowsPerformanceRecorder::CProfilesCache::`vftable';
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy();
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>((_QWORD *)this + 8);
  *((_QWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 0;
  *((_QWORD *)this + 13) = 0;
  SetLastError(0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpName);
  ATL::CSimpleStringT<unsigned short,0>::SetString(
    &lpName,
    L"MicrosoftWindowsPerformanceRecorderControlSingletonEvent_");
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpName, a2);
  *((_QWORD *)this + 13) = CreateEventW(0, 1, 0, lpName);
  LastError = GetLastError();
  if ( LastError )
  {
    if ( LastError == 183 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)1,
        (unsigned __int8)"CInstanceNameScopedData",
        (const char *)0x34,
        0xC5580601,
        "Instancename (%ws)",
        a2,
        -2);
      ATL::AtlThrowImpl(-984087039);
    }
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)1,
      (unsigned __int8)"CInstanceNameScopedData",
      (const char *)0x39,
      v5,
      "Failed to Create SingletonEvent",
      v7);
    ATL::AtlThrowLastWin32();
  }
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)4,
    (unsigned __int8)"CInstanceNameScopedData",
    (const char *)0x3F,
    0,
    "InstanceNameScopedData created",
    v7);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpName);
  return this;
}

```

## disassembly

```asm
0x180043f10  mov     rax, rsp
0x180043f13  mov     [rax+8], rcx
0x180043f17  push    rdi
0x180043f18  sub     rsp, 40h
0x180043f1c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180043f24  mov     [rax+10h], rbx
0x180043f28  mov     [rax+20h], rsi
0x180043f2c  mov     rsi, rdx
0x180043f2f  mov     rdi, rcx
0x180043f32  call    ??0CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)
0x180043f37  nop
0x180043f38  lea     rax, ??_7CProfilesCache@WindowsPerformanceRecorder@@6B@; const WindowsPerformanceRecorder::CProfilesCache::`vftable'
0x180043f3f  mov     [rdi+28h], rax
0x180043f43  lea     rcx, [rdi+30h]
0x180043f47  mov     qword ptr [rcx], 0
0x180043f4e  mov     qword ptr [rcx+8], 0
0x180043f56  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@UCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@U?$less@UCFileKey@Impl@WindowsPerformanceRecorder@@@std@@V?$allocator@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@7@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180043f5b  lea     rcx, [rdi+40h]
0x180043f5f  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x180043f64  mov     qword ptr [rdi+58h], 0
0x180043f6c  mov     byte ptr [rdi+60h], 0
0x180043f70  mov     qword ptr [rdi+68h], 0
0x180043f78  xor     ecx, ecx; dwErrCode
0x180043f7a  call    cs:__imp_SetLastError
0x180043f80  lea     rcx, [rsp+48h+lpName]; void *
0x180043f85  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043f8a  nop
0x180043f8b  lea     rdx, aMicrosoftwindo; "MicrosoftWindowsPerformanceRecorderCont"...
0x180043f92  lea     rcx, [rsp+48h+lpName]
0x180043f97  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180043f9c  mov     rdx, rsi
0x180043f9f  lea     rcx, [rsp+48h+lpName]
0x180043fa4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180043fa9  mov     r9, [rsp+48h+lpName]; lpName
0x180043fae  xor     r8d, r8d; bInitialState
0x180043fb1  lea     edx, [r8+1]; bManualReset
0x180043fb5  xor     ecx, ecx; lpEventAttributes
0x180043fb7  call    cs:__imp_CreateEventW
0x180043fbd  mov     [rdi+68h], rax
0x180043fc1  call    cs:__imp_GetLastError
0x180043fc7  test    eax, eax
0x180043fc9  jz      short loc_180044046
0x180043fcb  cmp     eax, 0B7h
0x180043fd0  jnz     short loc_180044009
0x180043fd2  mov     [rsp+48h+var_20], rsi; char *
0x180043fd7  lea     rax, aInstancenameWs_0; "Instancename (%ws)"
0x180043fde  mov     [rsp+48h+Format], rax; Format
0x180043fe3  mov     ebx, 0C5580601h
0x180043fe8  mov     r9d, ebx; unsigned int
0x180043feb  mov     r8d, 34h ; '4'; char *
0x180043ff1  lea     rdx, aCinstancenames_0; "CInstanceNameScopedData"
0x180043ff8  lea     ecx, [r8-33h]; this
0x180043ffc  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180044001  mov     ecx, ebx; int
0x180044003  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180044009  call    cs:__imp_GetLastError
0x18004400f  test    eax, eax
0x180044011  jle     short loc_18004401B
0x180044013  movzx   eax, ax
0x180044016  or      eax, 80070000h
0x18004401b  lea     rcx, aFailedToCreate; "Failed to Create SingletonEvent"
0x180044022  mov     [rsp+48h+Format], rcx; Format
0x180044027  mov     r9d, eax; unsigned int
0x18004402a  mov     r8d, 39h ; '9'; char *
0x180044030  lea     rdx, aCinstancenames_0; "CInstanceNameScopedData"
0x180044037  lea     ecx, [r8-38h]; this
0x18004403b  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180044040  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180044046  lea     rax, aInstancenamesc_0; "InstanceNameScopedData created"
0x18004404d  mov     [rsp+48h+Format], rax; Format
0x180044052  xor     r9d, r9d; unsigned int
0x180044055  lea     r8d, [r9+3Fh]; char *
0x180044059  lea     rdx, aCinstancenames_0; "CInstanceNameScopedData"
0x180044060  lea     ecx, [r9+4]; this
0x180044064  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180044069  nop
0x18004406a  lea     rcx, [rsp+48h+lpName]; this
0x18004406f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180044074  nop
0x180044075  mov     rax, rdi
0x180044078  mov     rbx, [rsp+48h+arg_8]
0x18004407d  mov     rsi, [rsp+48h+arg_18]
0x180044082  add     rsp, 40h
0x180044086  pop     rdi
0x180044087  retn
```
