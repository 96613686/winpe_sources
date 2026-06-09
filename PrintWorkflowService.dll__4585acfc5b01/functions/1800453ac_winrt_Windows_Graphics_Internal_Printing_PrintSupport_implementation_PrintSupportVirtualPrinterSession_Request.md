# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::RequestPreferredPdlHandleForRead(winrt::Windows::Graphics::Internal::Printing::PrintSupport::AppSessionType const &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)

- ea: `0x1800453ac`
- end: `0x1800455c0`
- name: `?RequestPreferredPdlHandleForRead@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAAXAEBW4AppSessionType@345678@AEA_K11@Z`
- size: `532`
- prototype: `void(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *__hidden this, const enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::AppSessionType *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b920`

## callees

- `0x1800014e8`
- `0x180001614`
- `0x180003ca0`
- `0x1800127a4`
- `0x180021570`
- `0x1800441c4`
- `0x1800453ac`

## string_xrefs

- `0x180045544`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x18004555d`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180045576`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180045592`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x1800455ab`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::RequestPreferredPdlHandleForRead(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *this,
        const enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::AppSessionType *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-71h]
  int v14; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-59h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int64 v17; // [rsp+48h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int64 *v19; // [rsp+70h] [rbp-21h]
  __int64 v20; // [rsp+78h] [rbp-19h]
  unsigned __int64 *v21; // [rsp+80h] [rbp-11h]
  __int64 v22; // [rsp+88h] [rbp-9h]
  unsigned __int64 *v23; // [rsp+90h] [rbp-1h]
  __int64 v24; // [rsp+98h] [rbp+7h]
  int *v25; // [rsp+A0h] [rbp+Fh]
  __int64 v26; // [rsp+A8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  if ( (unsigned int)dword_180083000 > 5 )
  {
    v14 = *((_DWORD *)this + 54);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180083000,
      (__int64)byte_180074C9D,
      (__int64)a3,
      (__int64)a4,
      (__int64)&v14);
  }
  if ( !winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::IsSessionActive(*((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler **)this + 40)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)0x8000000ELL,
      v13);
  if ( *(_DWORD *)a2 == 1 )
  {
    v9 = DuplicateHandleToClient(*((HANDLE *)this + 56), a3);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
        (const char *)(unsigned int)v9,
        v13);
  }
  else
  {
    v10 = DuplicateHandleToClient(*((HANDLE *)this + 57), a3);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
        (const char *)(unsigned int)v10,
        v13);
  }
  v11 = DuplicateHandleToClient(*((HANDLE *)this + 52), a4);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)v11,
      v13);
  v12 = DuplicateHandleToClient(*((HANDLE *)this + 53), a5);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)v12,
      v13);
  if ( (unsigned int)dword_180083000 > 5 )
  {
    v14 = *((_DWORD *)this + 54);
    v15 = *a5;
    v16 = *a4;
    v17 = *a3;
    v25 = &v14;
    v23 = &v15;
    v21 = &v16;
    v19 = &v17;
    v26 = 4;
    v24 = 8;
    v22 = 8;
    v20 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180083000, (unsigned __int8 *)byte_180074CFB, 0, 0, 6u, &v18);
  }
}

```

## disassembly

```asm
0x1800453ac  mov     [rsp-8+arg_8], rbx
0x1800453b1  push    rbp
0x1800453b2  push    rsi
0x1800453b3  push    rdi
0x1800453b4  push    r14
0x1800453b6  push    r15
0x1800453b8  lea     rbp, [rsp-2Fh]
0x1800453bd  sub     rsp, 0C0h
0x1800453c4  mov     rax, cs:__security_cookie
0x1800453cb  xor     rax, rsp
0x1800453ce  mov     [rbp+4Fh+var_30], rax
0x1800453d2  mov     eax, cs:dword_180083000
0x1800453d8  mov     r14, r9
0x1800453db  mov     r15, [rbp+4Fh+arg_20]
0x1800453df  mov     rdi, r8
0x1800453e2  mov     rsi, rdx
0x1800453e5  mov     rbx, rcx
0x1800453e8  cmp     eax, 5
0x1800453eb  jbe     short loc_180045412
0x1800453ed  mov     eax, [rcx+0D8h]
0x1800453f3  lea     rdx, byte_180074C9D
0x1800453fa  mov     [rbp+4Fh+var_B0], eax
0x1800453fd  lea     rcx, dword_180083000
0x180045404  lea     rax, [rbp+4Fh+var_B0]
0x180045408  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18004540d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180045412  mov     rcx, [rbx+140h]; this
0x180045419  call    ?IsSessionActive@VirtualPrinterSessionStateHandler@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::IsSessionActive(void)
0x18004541e  test    al, al
0x180045420  jz      loc_180045572
0x180045426  cmp     dword ptr [rsi], 1
0x180045429  mov     rdx, rdi; unsigned __int64 *
0x18004542c  jnz     short loc_180045444
0x18004542e  mov     rcx, [rbx+1C0h]; hSourceHandle
0x180045435  call    ?DuplicateHandleToClient@@YAJPEAXPEA_K@Z; DuplicateHandleToClient(void *,unsigned __int64 *)
0x18004543a  test    eax, eax
0x18004543c  js      loc_180045559
0x180045442  jmp     short loc_180045458
0x180045444  mov     rcx, [rbx+1C8h]; hSourceHandle
0x18004544b  call    ?DuplicateHandleToClient@@YAJPEAXPEA_K@Z; DuplicateHandleToClient(void *,unsigned __int64 *)
0x180045450  test    eax, eax
0x180045452  js      loc_18004558E
0x180045458  mov     rcx, [rbx+1A0h]; hSourceHandle
0x18004545f  mov     rdx, r14; unsigned __int64 *
0x180045462  call    ?DuplicateHandleToClient@@YAJPEAXPEA_K@Z; DuplicateHandleToClient(void *,unsigned __int64 *)
0x180045467  test    eax, eax
0x180045469  js      loc_1800455A7
0x18004546f  mov     rcx, [rbx+1A8h]; hSourceHandle
0x180045476  mov     rdx, r15; unsigned __int64 *
0x180045479  call    ?DuplicateHandleToClient@@YAJPEAXPEA_K@Z; DuplicateHandleToClient(void *,unsigned __int64 *)
0x18004547e  test    eax, eax
0x180045480  js      loc_180045540
0x180045486  mov     eax, cs:dword_180083000
0x18004548c  cmp     eax, 5
0x18004548f  jbe     loc_18004551D
0x180045495  mov     eax, [rbx+0D8h]
0x18004549b  lea     rdx, byte_180074CFB
0x1800454a2  mov     [rbp+4Fh+var_B0], eax
0x1800454a5  lea     rcx, dword_180083000
0x1800454ac  mov     rax, [r15]
0x1800454af  xor     r9d, r9d
0x1800454b2  mov     [rbp+4Fh+var_A8], rax
0x1800454b6  xor     r8d, r8d
0x1800454b9  mov     rax, [r14]
0x1800454bc  mov     [rbp+4Fh+var_A0], rax
0x1800454c0  mov     rax, [rdi]
0x1800454c3  mov     [rbp+4Fh+var_98], rax
0x1800454c7  lea     rax, [rbp+4Fh+var_B0]
0x1800454cb  mov     [rbp+4Fh+var_40], rax
0x1800454cf  lea     rax, [rbp+4Fh+var_A8]
0x1800454d3  mov     [rbp+4Fh+var_50], rax
0x1800454d7  lea     rax, [rbp+4Fh+var_A0]
0x1800454db  mov     [rbp+4Fh+var_60], rax
0x1800454df  lea     rax, [rbp+4Fh+var_98]
0x1800454e3  mov     [rbp+4Fh+var_70], rax
0x1800454e7  lea     rax, [rbp+4Fh+var_90]
0x1800454eb  mov     [rsp+0E0h+var_B8], rax
0x1800454f0  mov     [rsp+0E0h+var_C0], 6
0x1800454f8  mov     [rbp+4Fh+var_38], 4
0x180045500  mov     [rbp+4Fh+var_48], 8
0x180045508  mov     [rbp+4Fh+var_58], 8
0x180045510  mov     [rbp+4Fh+var_68], 8
0x180045518  call    _tlgWriteTransfer_EventWriteTransfer
0x18004551d  mov     rcx, [rbp+4Fh+var_30]
0x180045521  xor     rcx, rsp; StackCookie
0x180045524  call    __security_check_cookie
0x180045529  mov     rbx, [rsp+0E0h+arg_8]
0x180045531  add     rsp, 0C0h
0x180045538  pop     r15
0x18004553a  pop     r14
0x18004553c  pop     rdi
0x18004553d  pop     rsi
0x18004553e  pop     rbp
0x18004553f  retn
0x180045540  mov     rcx, [rbp+57h]; this
0x180045544  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x18004554b  mov     r9d, eax; char *
0x18004554e  mov     edx, 1D1h; void *
0x180045553  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045559  mov     rcx, [rbp+57h]; this
0x18004555d  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180045564  mov     r9d, eax; char *
0x180045567  mov     edx, 1C9h; void *
0x18004556c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045572  mov     rcx, [rbp+57h]; this
0x180045576  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x18004557d  mov     r9d, 8000000Eh; char *
0x180045583  mov     edx, 1C5h; void *
0x180045588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004558e  mov     rcx, [rbp+57h]; this
0x180045592  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180045599  mov     r9d, eax; char *
0x18004559c  mov     edx, 1CDh; void *
0x1800455a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800455a7  mov     rcx, [rbp+57h]; this
0x1800455ab  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x1800455b2  mov     r9d, eax; char *
0x1800455b5  mov     edx, 1D0h; void *
0x1800455ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
