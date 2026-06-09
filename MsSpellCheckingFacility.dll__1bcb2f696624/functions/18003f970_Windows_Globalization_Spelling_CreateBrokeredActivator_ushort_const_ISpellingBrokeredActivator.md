# Windows::Globalization::Spelling::CreateBrokeredActivator(ushort const *,ISpellingBrokeredActivator * *)

- ea: `0x18003f970`
- end: `0x18003fa4f`
- name: `?CreateBrokeredActivator@Spelling@Globalization@Windows@@YAJPEBGPEAPEAUISpellingBrokeredActivator@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling *__hidden this, const unsigned __int16 *, struct ISpellingBrokeredActivator **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800506c0`

## callees

- `0x18003f970`
- `0x180040cc4`
- `0x180061320`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f9bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f9bd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003f9d9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003f9d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Globalization::Spelling::CreateBrokeredActivator(
        Windows::Globalization::Spelling *this,
        unsigned __int16 *a2,
        struct ISpellingBrokeredActivator **a3)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  *(_QWORD *)a2 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Globalization.Spelling.Internal.Facility", 0x30u, &hstringHeader, &string);
  if ( v4 >= 0 )
  {
    v8 = 0;
    v4 = RoActivateInstance(string, &v8);
    if ( v4 >= 0 )
    {
      v7 = 0;
      v4 = (**v8)(v8, &GUID_838253a5_307d_45b3_bf54_6c83e1b431e2, &v7);
      if ( v4 >= 0 )
      {
        v5 = v7;
        v7 = 0;
        *(_QWORD *)a2 = v5;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f970  mov     [rsp-8+arg_0], rbx
0x18003f975  mov     [rsp-8+arg_10], rdi
0x18003f97a  push    rbp
0x18003f97b  mov     rbp, rsp
0x18003f97e  sub     rsp, 60h
0x18003f982  mov     rax, cs:__security_cookie
0x18003f989  xor     rax, rsp
0x18003f98c  mov     [rbp+var_10], rax
0x18003f990  mov     rdi, rdx
0x18003f993  mov     qword ptr [rdx], 0
0x18003f99a  xorps   xmm0, xmm0
0x18003f99d  xor     eax, eax
0x18003f99f  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18003f9a3  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rax
0x18003f9a7  mov     [rbp+string], rax
0x18003f9ab  lea     r9, [rbp+string]; string
0x18003f9af  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003f9b3  lea     edx, [rax+30h]; length
0x18003f9b6  lea     rcx, sourceString; "Windows.Globalization.Spelling.Internal"...
0x18003f9bd  call    cs:__imp_WindowsCreateStringReference
0x18003f9c3  mov     ebx, eax
0x18003f9c5  test    eax, eax
0x18003f9c7  js      short loc_18003FA2F
0x18003f9c9  mov     [rbp+var_38], 0
0x18003f9d1  lea     rdx, [rbp+var_38]
0x18003f9d5  mov     rcx, [rbp+string]
0x18003f9d9  call    cs:__imp_RoActivateInstance
0x18003f9df  mov     ebx, eax
0x18003f9e1  test    eax, eax
0x18003f9e3  js      short loc_18003FA26
0x18003f9e5  mov     [rbp+var_40], 0
0x18003f9ed  mov     rcx, [rbp+var_38]
0x18003f9f1  mov     rax, [rcx]
0x18003f9f4  lea     r8, [rbp+var_40]
0x18003f9f8  lea     rdx, _GUID_838253a5_307d_45b3_bf54_6c83e1b431e2
0x18003f9ff  mov     rax, [rax]
0x18003fa02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa07  mov     ebx, eax
0x18003fa09  test    eax, eax
0x18003fa0b  js      short loc_18003FA1C
0x18003fa0d  mov     rax, [rbp+var_40]
0x18003fa11  mov     [rbp+var_40], 0
0x18003fa19  mov     [rdi], rax
0x18003fa1c  lea     rcx, [rbp+var_40]
0x18003fa20  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003fa25  nop
0x18003fa26  lea     rcx, [rbp+var_38]
0x18003fa2a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003fa2f  mov     eax, ebx
0x18003fa31  mov     rcx, [rbp+var_10]
0x18003fa35  xor     rcx, rsp; StackCookie
0x18003fa38  call    __security_check_cookie
0x18003fa3d  lea     r11, [rsp+60h+var_s0]
0x18003fa42  mov     rbx, [r11+10h]
0x18003fa46  mov     rdi, [r11+20h]
0x18003fa4a  mov     rsp, r11
0x18003fa4d  pop     rbp
0x18003fa4e  retn
```
