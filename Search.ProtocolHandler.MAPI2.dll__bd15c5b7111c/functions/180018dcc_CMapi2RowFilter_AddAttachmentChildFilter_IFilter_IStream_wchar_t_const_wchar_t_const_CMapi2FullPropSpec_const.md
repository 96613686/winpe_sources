# CMapi2RowFilter::AddAttachmentChildFilter(IFilter *,IStream *,wchar_t const *,wchar_t const *,CMapi2FullPropSpec const *)

- ea: `0x180018dcc`
- end: `0x180018eca`
- name: `?AddAttachmentChildFilter@CMapi2RowFilter@@AEAAXPEAUIFilter@@PEAUIStream@@PEB_W2PEBVCMapi2FullPropSpec@@@Z`
- size: `254`
- prototype: `void __fastcall(CMapi2RowFilter *this, struct IFilter *, struct IStream *, const wchar_t *, const wchar_t *, const struct CMapi2FullPropSpec *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001afa8`

## callees

- `0x18000ea18`
- `0x18000fd58`
- `0x1800113ec`
- `0x18001356c`
- `0x180018dcc`
- `0x18001a660`
- `0x1800204dc`
- `0x180020508`
- `0x18002b0c0`
- `0x18002b784`

## string_xrefs

- `0x180018eb3`: `Failed to create or initialize child filter attachment: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMapi2RowFilter::AddAttachmentChildFilter(
        CMapi2RowFilter *this,
        struct IFilter *a2,
        struct IStream *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const struct CMapi2FullPropSpec *a6)
{
  int Instance; // eax
  CFilterMapiFps *v11; // rbx
  CUnkSList *v12; // rcx
  struct IFilter *v13; // rdx
  struct CSingleLink *Link; // rax
  CFilterMapiFps *v15[7]; // [rsp+30h] [rbp-38h] BYREF

  v15[0] = 0;
  Instance = ATL::CComObject<CFilterMapiFps>::CreateInstance(v15);
  if ( Instance < 0 )
  {
    CLogger::Error(Instance, L"Failed to create or initialize child filter attachment: %s", a5);
  }
  else
  {
    TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(v15, v15[0]);
    if ( a2 )
    {
      v13 = a2;
      v11 = v15[0];
      CFilterMapiFps::Initialize(v15[0], v13, a6);
    }
    else
    {
      v11 = v15[0];
      CFilterMapiFps::Initialize(
        v15[0],
        *(struct IProtocolHandlerSite **)(*(_QWORD *)(*((_QWORD *)this + 2645) + 64LL) + 200LL),
        a3,
        a4,
        0,
        a6);
    }
    Link = CUnkSList::CreateLink(v12, (struct IUnknown *)(((unsigned __int64)v11 + 8) & -(__int64)(v11 != 0)));
    CLnkList::InsertAfter((CMapi2RowFilter *)((char *)this + 23976), *((struct CSingleLink **)this + 2999), Link);
    CLogger::Info(L"Indexing attachment: %s", a5);
    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(v15);
  }
}

```

## disassembly

```asm
0x180018dcc  push    rbx
0x180018dce  push    rbp
0x180018dcf  push    rsi
0x180018dd0  push    rdi
0x180018dd1  sub     rsp, 48h
0x180018dd5  mov     rsi, r9
0x180018dd8  mov     rbp, r8
0x180018ddb  mov     rbx, rdx
0x180018dde  mov     rdi, rcx
0x180018de1  mov     [rsp+68h+var_38], 0
0x180018dea  lea     rcx, [rsp+68h+var_38]
0x180018def  call    ?CreateInstance@?$CComObject@VCFilterMapiFps@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterMapiFps>::CreateInstance(ATL::CComObject<CFilterMapiFps> * *)
0x180018df4  test    eax, eax
0x180018df6  js      loc_180018EAB
0x180018dfc  mov     rdx, [rsp+68h+var_38]
0x180018e01  lea     rcx, [rsp+68h+var_38]
0x180018e06  call    ??0?$TComNoUnkPointer@VCMapi2RowFilter@@@@QEAA@PEAVCMapi2RowFilter@@@Z; TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(CMapi2RowFilter *)
0x180018e0b  nop
0x180018e0c  test    rbx, rbx
0x180018e0f  jnz     short loc_180018E4A
0x180018e11  mov     rax, [rdi+52A8h]
0x180018e18  mov     rdx, [rax+40h]
0x180018e1c  mov     rax, [rsp+68h+arg_28]
0x180018e24  mov     [rsp+68h+var_40], rax; struct CMapi2FullPropSpec *
0x180018e29  mov     [rsp+68h+var_48], rbx; struct _GUID *
0x180018e2e  mov     r9, rsi; wchar_t *
0x180018e31  mov     r8, rbp; struct IStream *
0x180018e34  mov     rdx, [rdx+0C8h]; struct IProtocolHandlerSite *
0x180018e3b  mov     rbx, [rsp+68h+var_38]
0x180018e40  mov     rcx, rbx; this
0x180018e43  call    ?Initialize@CFilterMapiFps@@QEAAXPEAUIProtocolHandlerSite@@PEAUIStream@@PEB_WPEBU_GUID@@PEBVCMapi2FullPropSpec@@@Z; CFilterMapiFps::Initialize(IProtocolHandlerSite *,IStream *,wchar_t const *,_GUID const *,CMapi2FullPropSpec const *)
0x180018e48  jmp     short loc_180018E62
0x180018e4a  mov     r8, [rsp+68h+arg_28]; struct CMapi2FullPropSpec *
0x180018e52  mov     rdx, rbx; struct IFilter *
0x180018e55  mov     rbx, [rsp+68h+var_38]
0x180018e5a  mov     rcx, rbx; this
0x180018e5d  call    ?Initialize@CFilterMapiFps@@QEAAXPEAUIFilter@@PEBVCMapi2FullPropSpec@@@Z; CFilterMapiFps::Initialize(IFilter *,CMapi2FullPropSpec const *)
0x180018e62  lea     rax, [rbx+8]
0x180018e66  neg     rbx
0x180018e69  sbb     rdx, rdx
0x180018e6c  and     rdx, rax; struct IUnknown *
0x180018e6f  call    ?CreateLink@CUnkSList@@IEAAPEAVCUnkSingleLink@@PEAUIUnknown@@@Z; CUnkSList::CreateLink(IUnknown *)
0x180018e74  mov     r8, rax; struct CSingleLink *
0x180018e77  mov     rdx, [rdi+5DB8h]; struct CSingleLink *
0x180018e7e  lea     rcx, [rdi+5DA8h]; this
0x180018e85  call    ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x180018e8a  mov     rdx, [rsp+68h+arg_20]
0x180018e92  lea     rcx, aIndexingAttach; "Indexing attachment: %s"
0x180018e99  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180018e9e  nop
0x180018e9f  lea     rcx, [rsp+68h+var_38]
0x180018ea4  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180018ea9  jmp     short loc_180018EC1
0x180018eab  mov     r8, [rsp+68h+arg_20]
0x180018eb3  lea     rdx, aFailedToCreate; "Failed to create or initialize child fi"...
0x180018eba  mov     ecx, eax; int
0x180018ebc  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180018ec1  add     rsp, 48h
0x180018ec5  pop     rdi
0x180018ec6  pop     rsi
0x180018ec7  pop     rbp
0x180018ec8  pop     rbx
0x180018ec9  retn
```
