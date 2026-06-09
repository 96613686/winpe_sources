# WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)

- ea: `0x1800329bc`
- end: `0x180032ad3`
- name: `?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180032620`
- `0x18003a1f0`
- `0x18004ac00`
- `0x180058800`
- `0x180059060`
- `0x18005deb0`
- `0x18005ec50`
- `0x180060940`
- `0x180061780`
- `0x180061f90`
- `0x180062090`
- `0x18006b7d0`

## callees

- `0x18001e6e0`
- `0x1800329bc`
- `0x180040a04`
- `0x18004aa78`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180032aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ab3`
- `OLEAUT32!__imp_SysFreeString` at `0x180032abd`
- `OLEAUT32!__imp_SysFreeString` at `0x180032aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ab3`
- `OLEAUT32!__imp_SysFreeString` at `0x180032abd`

## string_xrefs

- `0x180032a3a`: `COMGUARD`
- `0x180032a4f`: `IsOtherObjectInstanceNameCompatible`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
        __int64 a1,
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  signed int v4; // ebx
  const char *v5; // [rsp+28h] [rbp-20h]
  BSTR bstrString; // [rsp+58h] [rbp+10h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  bstrString = 0;
  v7 = 0;
  (**a2)(a2, &GUID_00383df6_90fc_49c0_b65e_0b585bdfddda, &v7);
  if ( !v7 )
  {
    v4 = -2147418113;
LABEL_11:
    SysFreeString(bstrString);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 40LL))(v7, &bstrString);
  if ( v4 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "IsOtherObjectInstanceNameCompatible",
      (const char *)0xA0,
      v4,
      "COMGUARD",
      v5);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
    goto LABEL_11;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  if ( *(_QWORD *)(a1 + 8) && bstrString )
  {
    if ( (unsigned __int8)ATL::CComBSTR::operator!=(a1 + 8, &bstrString) )
    {
      v4 = -984087013;
      goto LABEL_11;
    }
    SysFreeString(bstrString);
    return 0;
  }
  else
  {
    SysFreeString(bstrString);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800329bc  push    rdi
0x1800329be  sub     rsp, 40h
0x1800329c2  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800329cb  mov     [rsp+48h+arg_0], rbx
0x1800329d0  mov     r9, rdx
0x1800329d3  mov     rdi, rcx
0x1800329d6  test    rdx, rdx
0x1800329d9  jnz     short loc_1800329E5
0x1800329db  mov     eax, 80004003h
0x1800329e0  jmp     loc_180032AC8
0x1800329e5  mov     [rsp+48h+bstrString], 0
0x1800329ee  mov     [rsp+48h+arg_10], 0
0x1800329f7  mov     rax, [rdx]
0x1800329fa  lea     r8, [rsp+48h+arg_10]
0x1800329ff  lea     rdx, _GUID_00383df6_90fc_49c0_b65e_0b585bdfddda
0x180032a06  mov     rcx, r9
0x180032a09  mov     rax, [rax]
0x180032a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a11  nop
0x180032a12  mov     rcx, [rsp+48h+arg_10]
0x180032a17  test    rcx, rcx
0x180032a1a  jnz     short loc_180032A23
0x180032a1c  mov     ebx, 8000FFFFh
0x180032a21  jmp     short loc_180032A9F
0x180032a23  mov     rax, [rcx]
0x180032a26  lea     rdx, [rsp+48h+bstrString]
0x180032a2b  mov     rax, [rax+28h]
0x180032a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a34  mov     ebx, eax
0x180032a36  test    eax, eax
0x180032a38  jns     short loc_180032A6D
0x180032a3a  lea     rax, aComguard; "COMGUARD"
0x180032a41  mov     [rsp+48h+Format], rax; Format
0x180032a46  mov     r9d, ebx; unsigned int
0x180032a49  mov     r8d, 0A0h; char *
0x180032a4f  lea     rdx, aIsotherobjecti; "IsOtherObjectInstanceNameCompatible"
0x180032a56  mov     ecx, 2; this
0x180032a5b  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180032a60  nop
0x180032a61  lea     rcx, [rsp+48h+arg_10]
0x180032a66  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032a6b  jmp     short loc_180032A9F
0x180032a6d  lea     rcx, [rsp+48h+arg_10]
0x180032a72  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032a77  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180032a7c  cmp     qword ptr [rdi+8], 0
0x180032a81  jz      short loc_180032ABD
0x180032a83  test    rcx, rcx
0x180032a86  jz      short loc_180032ABD
0x180032a88  lea     rdx, [rsp+48h+bstrString]
0x180032a8d  lea     rcx, [rdi+8]
0x180032a91  call    ??9CComBSTR@ATL@@QEBA_NAEBV01@@Z; ATL::CComBSTR::operator!=(ATL::CComBSTR const &)
0x180032a96  test    al, al
0x180032a98  jz      short loc_180032AAE
0x180032a9a  mov     ebx, 0C558061Bh
0x180032a9f  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180032aa4  call    cs:__imp_SysFreeString
0x180032aaa  mov     eax, ebx
0x180032aac  jmp     short loc_180032AC8
0x180032aae  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180032ab3  call    cs:__imp_SysFreeString
0x180032ab9  xor     eax, eax
0x180032abb  jmp     short loc_180032AC8
0x180032abd  call    cs:__imp_SysFreeString
0x180032ac3  mov     eax, 8000FFFFh
0x180032ac8  mov     rbx, [rsp+48h+arg_0]
0x180032acd  add     rsp, 40h
0x180032ad1  pop     rdi
0x180032ad2  retn
```
