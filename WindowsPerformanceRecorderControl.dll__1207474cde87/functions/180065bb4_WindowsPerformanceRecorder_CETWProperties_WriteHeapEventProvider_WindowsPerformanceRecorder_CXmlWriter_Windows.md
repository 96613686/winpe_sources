# WindowsPerformanceRecorder::CETWProperties::WriteHeapEventProvider(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CETWProperties::CEventSession const *)

- ea: `0x180065bb4`
- end: `0x180065d1f`
- name: `?WriteHeapEventProvider@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBUCEventSession@12@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct WindowsPerformanceRecorder::CXmlWriter *this, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003e33c`

## callees

- `0x180008330`
- `0x1800102d8`
- `0x180013038`
- `0x180013094`
- `0x18001e6b8`
- `0x1800234f0`
- `0x180025580`
- `0x180035250`
- `0x180043204`
- `0x180065bb4`

## string_xrefs

- `0x180065c7c`: `HeapProcessIds`
- `0x180065cc9`: `HeapProcessIds`
- `0x180065c9a`: `HeapProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::WriteHeapEventProvider(
        struct WindowsPerformanceRecorder::CXmlWriter *this,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  __int64 v3; // rsi
  unsigned __int64 v4; // r14
  __int64 v5; // r13
  char *SessionName; // rax
  unsigned __int64 v7; // r12
  unsigned __int16 *v8; // rdi
  int i; // r15d
  ATL::CAtlException *v11; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp+10h] BYREF

  v3 = *((_QWORD *)a2 + 1);
  v4 = 0;
  if ( *(_DWORD *)(v3 + 72) )
  {
    v5 = *(unsigned __int16 *)(v3 + 72);
    if ( *(_WORD *)(v3 + v5 + 2) )
    {
      SessionName = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
      try
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64 *)&v12,
          SessionName);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v12, L"_Provider");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          &v12,
          58);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          &v12,
          32);
        WindowsPerformanceRecorder::CXmlWriter::Start(this, L"HeapEventProvider");
        WindowsPerformanceRecorder::CXmlWriter::Attr(this, L"Id", v12);
        v8 = (unsigned __int16 *)(v5 + v3 + 4);
        for ( i = 0; i < *(unsigned __int16 *)(v3 + v5 + 2); ++i )
        {
          if ( v8[1] == 2 )
          {
            WindowsPerformanceRecorder::CXmlWriter::Start(this, L"HeapProcessIds");
            v7 = *v8 - 1LL;
            while ( v4 < v7 )
            {
              WindowsPerformanceRecorder::CXmlWriter::Start(this, L"HeapProcessId");
              WindowsPerformanceRecorder::CXmlWriter::Attr(this, L"Value", *(_DWORD *)&v8[2 * v4 + 2]);
              WindowsPerformanceRecorder::CXmlWriter::End(this, 0);
              ++v4;
            }
            WindowsPerformanceRecorder::CXmlWriter::End(this, L"HeapProcessIds");
            v4 = 0;
          }
          v8 += 2 * *v8;
        }
        WindowsPerformanceRecorder::CXmlWriter::End(this, L"HeapEventProvider");
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v12);
      }
      catch ( ATL::CAtlException *v11 )
      {
        LODWORD(v12) = *(_DWORD *)v11;
        return (unsigned int)v12;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180065bb4  push    rdi
0x180065bb6  push    r12
0x180065bb8  push    r13
0x180065bba  push    r14
0x180065bbc  push    r15
0x180065bbe  sub     rsp, 30h
0x180065bc2  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180065bcb  mov     [rsp+58h+arg_0], rbx
0x180065bd0  mov     [rsp+58h+arg_10], rsi
0x180065bd5  mov     rbx, rcx
0x180065bd8  mov     rsi, [rdx+8]
0x180065bdc  xor     r14d, r14d
0x180065bdf  cmp     [rsi+48h], r14d
0x180065be3  jz      loc_180065CFF
0x180065be9  movzx   r13d, word ptr [rsi+48h]
0x180065bee  cmp     [rsi+r13+2], r14w
0x180065bf4  jz      loc_180065CFF
0x180065bfa  mov     rcx, rdx; this
0x180065bfd  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180065c02  mov     rdx, rax
0x180065c05  lea     rcx, [rsp+58h+arg_8]
0x180065c0a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180065c0f  nop
0x180065c10  lea     rdx, aProvider; "_Provider"
0x180065c17  lea     rcx, [rsp+58h+arg_8]
0x180065c1c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180065c21  lea     edx, [r14+3Ah]
0x180065c25  lea     rcx, [rsp+58h+arg_8]
0x180065c2a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180065c2f  lea     edx, [r14+20h]
0x180065c33  lea     rcx, [rsp+58h+arg_8]
0x180065c38  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180065c3d  lea     rdx, aHeapeventprovi_0; "HeapEventProvider"
0x180065c44  mov     rcx, rbx; this
0x180065c47  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180065c4c  mov     r8, [rsp+58h+arg_8]; unsigned __int16 *
0x180065c51  lea     rdx, aId; "Id"
0x180065c58  mov     rcx, rbx; this
0x180065c5b  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180065c60  lea     rdi, [rsi+4]
0x180065c64  add     rdi, r13
0x180065c67  mov     r15d, r14d
0x180065c6a  movzx   eax, word ptr [rsi+r13+2]
0x180065c70  cmp     r15d, eax
0x180065c73  jge     short loc_180065CE4
0x180065c75  cmp     word ptr [rdi+2], 2
0x180065c7a  jnz     short loc_180065CD8
0x180065c7c  lea     rdx, aHeapprocessids; "HeapProcessIds"
0x180065c83  mov     rcx, rbx; this
0x180065c86  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180065c8b  movzx   r12d, word ptr [rdi]
0x180065c8f  dec     r12
0x180065c92  mov     rcx, rbx; this
0x180065c95  cmp     r14, r12
0x180065c98  jnb     short loc_180065CC9
0x180065c9a  lea     rdx, aHeapprocessid; "HeapProcessId"
0x180065ca1  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180065ca6  mov     r8d, [rdi+r14*4+4]; unsigned int
0x180065cab  lea     rdx, aValue; "Value"
0x180065cb2  mov     rcx, rbx; this
0x180065cb5  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBGK@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ulong)
0x180065cba  xor     edx, edx; unsigned __int16 *
0x180065cbc  mov     rcx, rbx; this
0x180065cbf  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180065cc4  inc     r14
0x180065cc7  jmp     short loc_180065C92
0x180065cc9  lea     rdx, aHeapprocessids; "HeapProcessIds"
0x180065cd0  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180065cd5  xor     r14d, r14d
0x180065cd8  movzx   eax, word ptr [rdi]
0x180065cdb  lea     rdi, [rdi+rax*4]
0x180065cdf  inc     r15d
0x180065ce2  jmp     short loc_180065C6A
0x180065ce4  lea     rdx, aHeapeventprovi_0; "HeapEventProvider"
0x180065ceb  mov     rcx, rbx; this
0x180065cee  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180065cf3  nop
0x180065cf4  lea     rcx, [rsp+58h+arg_8]; this
0x180065cf9  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180065cfe  nop
0x180065cff  xor     eax, eax
0x180065d01  mov     rbx, [rsp+58h+arg_0]
0x180065d06  mov     rsi, [rsp+58h+arg_10]
0x180065d0b  add     rsp, 30h
0x180065d0f  pop     r15
0x180065d11  pop     r14
0x180065d13  pop     r13
0x180065d15  pop     r12
0x180065d17  pop     rdi
0x180065d18  retn
0x180065d19  mov     eax, dword ptr [rsp+58h+arg_8]
0x180065d1d  jmp     short loc_180065D01
```
