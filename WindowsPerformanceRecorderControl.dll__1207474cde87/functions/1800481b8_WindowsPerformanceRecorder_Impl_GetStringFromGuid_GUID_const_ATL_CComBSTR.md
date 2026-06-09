# WindowsPerformanceRecorder::Impl::GetStringFromGuid(_GUID const &,ATL::CComBSTR &)

- ea: `0x1800481b8`
- end: `0x180048268`
- name: `?GetStringFromGuid@Impl@WindowsPerformanceRecorder@@YAJAEBU_GUID@@AEAVCComBSTR@ATL@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::Impl *__hidden this, const struct _GUID *, struct ATL::CComBSTR *)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001ea58`
- `0x180045d98`
- `0x18006bbc0`
- `0x18006f3cc`
- `0x180070b3c`
- `0x180070d88`
- `0x180071858`

## callees

- `0x180008330`
- `0x1800234f0`
- `0x18002c950`
- `0x1800481b8`
- `0x18004a5c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800481e6`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800481e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004824d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004824d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::Impl::GetStringFromGuid(
        WindowsPerformanceRecorder::Impl *this,
        const struct _GUID *a2,
        struct ATL::CComBSTR *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  ATL::CAtlException *v7; // [rsp+28h] [rbp-10h] BYREF
  WindowsPerformanceRecorder::Impl *v8; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  v8 = this;
  pv = 0;
  v4 = StringFromIID(&LIBID_WindowsPerformanceRecorderControlLibrary, (LPOLESTR *)&pv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    try
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&v8,
        (char *)pv);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(&v8, 123);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(&v8, 125);
      ATL::CComBSTR::operator=(a2, v8);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v8);
      CoTaskMemFree(pv);
      result = 0;
    }
    catch ( ATL::CAtlException *v7 )
    {
      return *(unsigned int *)v7;
    }
  }
  else
  {
    CoTaskMemFree(pv);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800481b8  mov     rax, rsp
0x1800481bb  mov     [rax+8], rcx
0x1800481bf  push    rdi
0x1800481c0  sub     rsp, 30h
0x1800481c4  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800481cc  mov     [rax+10h], rbx
0x1800481d0  mov     rdi, rdx
0x1800481d3  mov     qword ptr [rax+18h], 0
0x1800481db  lea     rdx, [rax+18h]; lplpsz
0x1800481df  lea     rcx, LIBID_WindowsPerformanceRecorderControlLibrary; rclsid
0x1800481e6  call    cs:__imp_StringFromIID
0x1800481ec  mov     ebx, eax
0x1800481ee  test    eax, eax
0x1800481f0  jns     short loc_180048201
0x1800481f2  mov     rcx, [rsp+38h+pv]; pv
0x1800481f7  call    cs:__imp_CoTaskMemFree
0x1800481fd  mov     eax, ebx
0x1800481ff  jmp     short loc_18004825C
0x180048201  mov     rdx, [rsp+38h+pv]
0x180048206  lea     rcx, [rsp+38h+arg_0]
0x18004820b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180048210  nop
0x180048211  mov     edx, 7Bh ; '{'
0x180048216  lea     rcx, [rsp+38h+arg_0]
0x18004821b  call    ?Remove@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Remove(ushort)
0x180048220  mov     edx, 7Dh ; '}'
0x180048225  lea     rcx, [rsp+38h+arg_0]
0x18004822a  call    ?Remove@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Remove(ushort)
0x18004822f  mov     rdx, [rsp+38h+arg_0]
0x180048234  mov     rcx, rdi
0x180048237  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004823c  nop
0x18004823d  lea     rcx, [rsp+38h+arg_0]; this
0x180048242  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180048247  nop
0x180048248  mov     rcx, [rsp+38h+pv]; pv
0x18004824d  call    cs:__imp_CoTaskMemFree
0x180048253  nop
0x180048254  xor     eax, eax
0x180048256  jmp     short loc_18004825C
0x180048258  mov     eax, dword ptr [rsp+38h+arg_0]
0x18004825c  mov     rbx, [rsp+38h+arg_8]
0x180048261  add     rsp, 30h
0x180048265  pop     rdi
0x180048266  retn
```
