# PushButtonReset::XmlDocument::Create(PushButtonReset::XmlDocument * *)

- ea: `0x180059054`
- end: `0x180059427`
- name: `?Create@XmlDocument@PushButtonReset@@SAJPEAPEAV12@@Z`
- size: `979`
- prototype: `__int64 __fastcall(struct PushButtonReset::XmlDocument **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180050fe8`
- `0x18005a14c`

## callees

- `0x180005c00`
- `0x180005cc0`
- `0x180023620`
- `0x180037344`
- `0x1800527c0`
- `0x180058858`
- `0x180059054`
- `0x18005a498`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800591ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800591ff`
- `ole32!CoCreateInstance` at `0x1800590ca`
- `ole32!CoCreateInstance` at `0x1800590ca`

## string_xrefs

- `0x1800590ea`: `base\reset\util\src\xml.cpp`
- `0x18005915a`: `base\reset\util\src\xml.cpp`
- `0x1800591ca`: `base\reset\util\src\xml.cpp`
- `0x180059237`: `base\reset\util\src\xml.cpp`
- `0x1800592fb`: `base\reset\util\src\xml.cpp`
- `0x18005936f`: `base\reset\util\src\xml.cpp`
- `0x1800590d6`: `Failed to create IXMLDOMDocument3 instance`
- `0x180059146`: `Failed to set IXMLDOMDocument3::async`
- `0x1800590f1`: `PushButtonReset::XmlDocument::Create`
- `0x180059161`: `PushButtonReset::XmlDocument::Create`
- `0x1800591d1`: `PushButtonReset::XmlDocument::Create`
- `0x18005923e`: `PushButtonReset::XmlDocument::Create`
- `0x180059302`: `PushButtonReset::XmlDocument::Create`
- `0x180059376`: `PushButtonReset::XmlDocument::Create`
- `0x1800591b6`: `Failed to set IXMLDOMDocument3::validateOnParse`
- `0x1800592e7`: `Failed to set IXMLDOMDocument3 MultipleErrorMessages`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PushButtonReset::XmlDocument::Create(struct PushButtonReset::XmlDocument **a1)
{
  LPVOID *ppv; // rax
  HRESULT v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  BSTR v6; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int128 *); // rbx
  _QWORD *v10; // rax
  struct PushButtonReset::XmlDocument *v11; // rax
  void **v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h]
  void **v14; // [rsp+40h] [rbp-39h] BYREF
  BSTR v15; // [rsp+48h] [rbp-31h] BYREF
  void **v16; // [rsp+50h] [rbp-29h] BYREF
  struct PushButtonReset::XmlDocument *v17; // [rsp+58h] [rbp-21h]
  __int128 v18; // [rsp+60h] [rbp-19h] BYREF
  __int64 v19; // [rsp+70h] [rbp-9h]
  IID riid; // [rsp+80h] [rbp+7h] BYREF
  IID rclsid; // [rsp+90h] [rbp+17h] BYREF

  rclsid = CLSID_DOMDocument60;
  riid = IID_IXMLDOMDocument3;
  v13 = 0;
  v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
  ppv = (LPVOID *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v12);
  v3 = CoCreateInstance(&rclsid, 0, 1u, &riid, ppv);
  if ( v3 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(void ***))v12[3])(&v12);
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 504LL))(v4, 0);
    if ( v3 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(void ***))v12[3])(&v12);
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 544LL))(v5, 0);
      if ( v3 >= 0 )
      {
        v6 = SysAllocString(L"MultipleErrorMessages");
        v14 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        v15 = v6;
        if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v14) )
        {
          v18 = 0;
          LOWORD(v18) = 11;
          WORD4(v18) = -1;
          v8 = ((__int64 (__fastcall *)(void ***))v12[3])(&v12);
          v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v8 + 640LL);
          v10 = (_QWORD *)((__int64 (__fastcall *)(void ***))v14[4])(&v14);
          v19 = 0;
          v3 = v9(v8, *v10, &v18);
          if ( v3 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v3,
              "PushButtonReset::XmlDocument::Create",
              "base\\reset\\util\\src\\xml.cpp",
              56,
              L"Failed to set IXMLDOMDocument3 MultipleErrorMessages");
            v14 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
            RAII::CleanupInfo<unsigned short *>::Release(&v15);
            v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
            return (unsigned int)v3;
          }
          v17 = (struct PushButtonReset::XmlDocument *)PbrNew<PushButtonReset::XmlDocument,RAII::CAutoRelease<IXMLDOMDocument3 *> &>((__int64)&v12);
          v16 = &RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable';
          if ( !(unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v16) )
          {
            v13 = 0;
            v11 = v17;
            v17 = 0;
            *a1 = v11;
            v16 = &RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(&v16);
            v14 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
            RAII::CleanupInfo<unsigned short *>::Release(&v15);
            v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
            return (unsigned int)v3;
          }
          PushButtonReset::Logging::TraceErr(
            2,
            2147942414LL,
            "PushButtonReset::XmlDocument::Create",
            "base\\reset\\util\\src\\xml.cpp",
            59,
            L"Failed to allocate xdoc");
          v16 = &RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(&v16);
          v14 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v15);
          v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147942414LL,
            "PushButtonReset::XmlDocument::Create",
            "base\\reset\\util\\src\\xml.cpp",
            49,
            L"Failed to allocate multipleErrorMessages");
          v14 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v15);
          v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
        }
        return 2147942414LL;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v3,
        "PushButtonReset::XmlDocument::Create",
        "base\\reset\\util\\src\\xml.cpp",
        46,
        L"Failed to set IXMLDOMDocument3::validateOnParse");
      v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v3,
        "PushButtonReset::XmlDocument::Create",
        "base\\reset\\util\\src\\xml.cpp",
        43,
        L"Failed to set IXMLDOMDocument3::async");
      v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v3,
      "PushButtonReset::XmlDocument::Create",
      "base\\reset\\util\\src\\xml.cpp",
      40,
      L"Failed to create IXMLDOMDocument3 instance");
    v12 = &RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v12);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180059054  mov     [rsp-8+arg_8], rbx
0x180059059  mov     [rsp-8+arg_10], rsi
0x18005905e  push    rbp
0x18005905f  push    rdi
0x180059060  push    r12
0x180059062  push    r13
0x180059064  push    r14
0x180059066  lea     rbp, [rsp-37h]
0x18005906b  sub     rsp, 0B0h
0x180059072  mov     rax, cs:__security_cookie
0x180059079  xor     rax, rsp
0x18005907c  mov     [rbp+57h+var_30], rax
0x180059080  mov     rsi, rcx
0x180059083  movups  xmm0, xmmword ptr cs:CLSID_DOMDocument60.Data1
0x18005908a  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x18005908f  movups  xmm1, xmmword ptr cs:IID_IXMLDOMDocument3.Data1
0x180059096  movdqu  xmmword ptr [rbp+57h+riid.Data1], xmm1
0x18005909b  mov     [rbp+57h+var_98], 0
0x1800590a3  lea     r12, ??_7?$CAutoRelease@PEAUIXMLDOMDocument3@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMDocument3 *>::`vftable'
0x1800590aa  mov     [rbp+57h+var_A0], r12
0x1800590ae  lea     rcx, [rbp+57h+var_A0]
0x1800590b2  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800590b7  mov     [rsp+0D0h+ppv], rax; ppv
0x1800590bc  lea     r9, [rbp+57h+riid]; riid
0x1800590c0  xor     edx, edx; pUnkOuter
0x1800590c2  lea     r8d, [rdx+1]; dwClsContext
0x1800590c6  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800590ca  call    cs:__imp_CoCreateInstance
0x1800590d0  mov     ebx, eax
0x1800590d2  test    eax, eax
0x1800590d4  jns     short loc_180059118
0x1800590d6  lea     rax, aFailedToCreate_27; "Failed to create IXMLDOMDocument3 insta"...
0x1800590dd  mov     [rsp+0D0h+var_A8], rax
0x1800590e2  mov     dword ptr [rsp+0D0h+ppv], 28h ; '('
0x1800590ea  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x1800590f1  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x1800590f8  mov     edx, ebx
0x1800590fa  mov     ecx, 2
0x1800590ff  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059104  nop
0x180059105  mov     [rbp+57h+var_A0], r12
0x180059109  lea     rcx, [rbp+57h+var_A0]
0x18005910d  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059112  nop
0x180059113  jmp     loc_1800593FD
0x180059118  mov     rax, [rbp+57h+var_A0]
0x18005911c  lea     rcx, [rbp+57h+var_A0]
0x180059120  mov     rax, [rax+18h]
0x180059124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059129  mov     r8, rax
0x18005912c  mov     rcx, [rax]
0x18005912f  xor     edx, edx
0x180059131  mov     rax, [rcx+1F8h]
0x180059138  mov     rcx, r8
0x18005913b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059140  mov     ebx, eax
0x180059142  test    eax, eax
0x180059144  jns     short loc_180059188
0x180059146  lea     rax, aFailedToSetIxm_0; "Failed to set IXMLDOMDocument3::async"
0x18005914d  mov     [rsp+0D0h+var_A8], rax
0x180059152  mov     dword ptr [rsp+0D0h+ppv], 2Bh ; '+'
0x18005915a  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059161  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x180059168  mov     edx, ebx
0x18005916a  mov     ecx, 2
0x18005916f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059174  nop
0x180059175  mov     [rbp+57h+var_A0], r12
0x180059179  lea     rcx, [rbp+57h+var_A0]
0x18005917d  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059182  nop
0x180059183  jmp     loc_1800593FD
0x180059188  mov     rax, [rbp+57h+var_A0]
0x18005918c  lea     rcx, [rbp+57h+var_A0]
0x180059190  mov     rax, [rax+18h]
0x180059194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059199  mov     r8, rax
0x18005919c  mov     rcx, [rax]
0x18005919f  xor     edx, edx
0x1800591a1  mov     rax, [rcx+220h]
0x1800591a8  mov     rcx, r8
0x1800591ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591b0  mov     ebx, eax
0x1800591b2  test    eax, eax
0x1800591b4  jns     short loc_1800591F8
0x1800591b6  lea     rax, aFailedToSetIxm; "Failed to set IXMLDOMDocument3::validat"...
0x1800591bd  mov     [rsp+0D0h+var_A8], rax
0x1800591c2  mov     dword ptr [rsp+0D0h+ppv], 2Eh ; '.'
0x1800591ca  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x1800591d1  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x1800591d8  mov     edx, ebx
0x1800591da  mov     ecx, 2
0x1800591df  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800591e4  nop
0x1800591e5  mov     [rbp+57h+var_A0], r12
0x1800591e9  lea     rcx, [rbp+57h+var_A0]
0x1800591ed  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800591f2  nop
0x1800591f3  jmp     loc_1800593FD
0x1800591f8  lea     rcx, psz; "MultipleErrorMessages"
0x1800591ff  call    cs:__imp_SysAllocString
0x180059205  lea     r13, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005920c  mov     [rbp+57h+var_90], r13
0x180059210  mov     [rbp+57h+var_88], rax
0x180059214  lea     rcx, [rbp+57h+var_90]
0x180059218  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005921d  cmp     qword ptr [rax], 0
0x180059221  jnz     short loc_18005927B
0x180059223  lea     rax, aFailedToAlloca_36; "Failed to allocate multipleErrorMessage"...
0x18005922a  mov     [rsp+0D0h+var_A8], rax
0x18005922f  mov     dword ptr [rsp+0D0h+ppv], 31h ; '1'
0x180059237  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005923e  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x180059245  mov     edx, 8007000Eh
0x18005924a  mov     ecx, 2
0x18005924f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059254  nop
0x180059255  mov     [rbp+57h+var_90], r13
0x180059259  lea     rcx, [rbp+57h+var_88]
0x18005925d  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059262  nop
0x180059263  mov     [rbp+57h+var_A0], r12
0x180059267  lea     rcx, [rbp+57h+var_A0]
0x18005926b  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059270  nop
0x180059271  mov     eax, 8007000Eh
0x180059276  jmp     loc_1800593FF
0x18005927b  xorps   xmm0, xmm0
0x18005927e  xor     r14d, r14d
0x180059281  movups  [rbp+57h+var_70], xmm0
0x180059285  lea     eax, [r14+0Bh]
0x180059289  mov     word ptr [rbp+57h+var_70], ax
0x18005928d  or      eax, 0FFFFFFFFh
0x180059290  mov     word ptr [rbp+57h+var_70+8], ax
0x180059294  mov     rax, [rbp+57h+var_A0]
0x180059298  lea     rcx, [rbp+57h+var_A0]
0x18005929c  mov     rax, [rax+18h]
0x1800592a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592a5  mov     rdi, rax
0x1800592a8  mov     rcx, [rax]
0x1800592ab  mov     rbx, [rcx+280h]
0x1800592b2  mov     rcx, [rbp+57h+var_90]
0x1800592b6  mov     rax, [rcx+20h]
0x1800592ba  lea     rcx, [rbp+57h+var_90]
0x1800592be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592c3  movups  xmm0, [rbp+57h+var_70]
0x1800592c7  movaps  [rbp+57h+var_70], xmm0
0x1800592cb  mov     [rbp+57h+var_60], r14
0x1800592cf  lea     r8, [rbp+57h+var_70]
0x1800592d3  mov     rdx, [rax]
0x1800592d6  mov     rcx, rdi
0x1800592d9  mov     rax, rbx
0x1800592dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592e1  mov     ebx, eax
0x1800592e3  test    eax, eax
0x1800592e5  jns     short loc_180059336
0x1800592e7  lea     rax, aFailedToSetIxm_1; "Failed to set IXMLDOMDocument3 Multiple"...
0x1800592ee  mov     [rsp+0D0h+var_A8], rax
0x1800592f3  mov     dword ptr [rsp+0D0h+ppv], 38h ; '8'
0x1800592fb  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059302  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x180059309  mov     edx, ebx
0x18005930b  lea     ecx, [r14+2]
0x18005930f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059314  nop
0x180059315  mov     [rbp+57h+var_90], r13
0x180059319  lea     rcx, [rbp+57h+var_88]
0x18005931d  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059322  nop
0x180059323  mov     [rbp+57h+var_A0], r12
0x180059327  lea     rcx, [rbp+57h+var_A0]
0x18005932b  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059330  nop
0x180059331  jmp     loc_1800593FD
0x180059336  lea     rcx, [rbp+57h+var_A0]
0x18005933a  call    ??$PbrNew@VXmlDocument@PushButtonReset@@AEAV?$CAutoRelease@PEAUIXMLDOMDocument3@@@RAII@@@@YAPEAVXmlDocument@PushButtonReset@@AEAV?$CAutoRelease@PEAUIXMLDOMDocument3@@@RAII@@@Z; PbrNew<PushButtonReset::XmlDocument,RAII::CAutoRelease<IXMLDOMDocument3 *> &>(RAII::CAutoRelease<IXMLDOMDocument3 *> &)
0x18005933f  mov     [rbp+57h+var_78], rax
0x180059343  lea     rdi, ??_7?$CAutoPbrDelete@PEAVXmlDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable'
0x18005934a  mov     [rbp+57h+var_80], rdi
0x18005934e  lea     rcx, [rbp+57h+var_80]
0x180059352  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180059357  test    al, al
0x180059359  jz      short loc_1800593BC
0x18005935b  lea     rax, aFailedToAlloca_8; "Failed to allocate xdoc"
0x180059362  mov     [rsp+0D0h+var_A8], rax
0x180059367  mov     dword ptr [rsp+0D0h+ppv], 3Bh ; ';'
0x18005936f  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059376  lea     r8, aPushbuttonrese_69; "PushButtonReset::XmlDocument::Create"
0x18005937d  mov     edx, 8007000Eh
0x180059382  mov     ecx, 2
0x180059387  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005938c  nop
0x18005938d  mov     [rbp+57h+var_80], rdi
0x180059391  lea     rcx, [rbp+57h+var_80]
0x180059395  call    ?Release@?$CAutoPbrDelete@PEAVXmlDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(void)
0x18005939a  nop
0x18005939b  mov     [rbp+57h+var_90], r13
0x18005939f  lea     rcx, [rbp+57h+var_88]
0x1800593a3  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800593a8  nop
0x1800593a9  mov     [rbp+57h+var_A0], r12
0x1800593ad  lea     rcx, [rbp+57h+var_A0]
0x1800593b1  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800593b6  nop
0x1800593b7  jmp     loc_180059271
0x1800593bc  mov     [rbp+57h+var_98], 0
0x1800593c4  mov     rax, [rbp+57h+var_78]
0x1800593c8  mov     [rbp+57h+var_78], 0
0x1800593d0  mov     [rsi], rax
0x1800593d3  mov     [rbp+57h+var_80], rdi
0x1800593d7  lea     rcx, [rbp+57h+var_80]
0x1800593db  call    ?Release@?$CAutoPbrDelete@PEAVXmlDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(void)
0x1800593e0  nop
0x1800593e1  mov     [rbp+57h+var_90], r13
0x1800593e5  lea     rcx, [rbp+57h+var_88]
0x1800593e9  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800593ee  nop
0x1800593ef  mov     [rbp+57h+var_A0], r12
0x1800593f3  lea     rcx, [rbp+57h+var_A0]
0x1800593f7  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800593fc  nop
0x1800593fd  mov     eax, ebx
0x1800593ff  mov     rcx, [rbp+57h+var_30]
0x180059403  xor     rcx, rsp; StackCookie
0x180059406  call    __security_check_cookie
0x18005940b  lea     r11, [rsp+0D0h+var_20]
0x180059413  mov     rbx, [r11+38h]
0x180059417  mov     rsi, [r11+40h]
0x18005941b  mov     rsp, r11
0x18005941e  pop     r14
0x180059420  pop     r13
0x180059422  pop     r12
0x180059424  pop     rdi
0x180059425  pop     rbp
0x180059426  retn
```
