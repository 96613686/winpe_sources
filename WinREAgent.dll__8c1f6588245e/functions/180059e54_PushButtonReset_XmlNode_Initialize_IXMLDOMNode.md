# PushButtonReset::XmlNode::Initialize(IXMLDOMNode *)

- ea: `0x180059e54`
- end: `0x18005a144`
- name: `?Initialize@XmlNode@PushButtonReset@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(PushButtonReset::XmlNode *__hidden this, struct IXMLDOMNode *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058c74`
- `0x180059430`
- `0x180059aa8`
- `0x18005ab64`
- `0x18005aed4`

## callees

- `0x180011ef4`
- `0x180012968`
- `0x180037344`
- `0x180059e54`
- `0x18005a498`
- `0x18006f010`

## string_xrefs

- `0x180059ee2`: `base\reset\util\src\xml.cpp`
- `0x180059f9c`: `base\reset\util\src\xml.cpp`
- `0x18005a042`: `base\reset\util\src\xml.cpp`
- `0x18005a0e0`: `base\reset\util\src\xml.cpp`
- `0x180059f88`: `Failed to get namespace URI`
- `0x180059ee9`: `PushButtonReset::XmlNode::Initialize`
- `0x180059fa3`: `PushButtonReset::XmlNode::Initialize`
- `0x18005a049`: `PushButtonReset::XmlNode::Initialize`
- `0x18005a0e7`: `PushButtonReset::XmlNode::Initialize`
- `0x18005a0cc`: `Failed to cast NODE_ELEMENT IXMLDOMNode to IXMLDOMElement`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PushButtonReset::XmlNode::Initialize(PushButtonReset::XmlNode *this, struct IXMLDOMNode *a2)
{
  char *v3; // rsi
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64); // rbx
  __int64 v6; // rax
  int v7; // ebx
  _QWORD *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  _QWORD *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64); // rbx
  __int64 v20; // rax
  void **v22; // [rsp+30h] [rbp-28h] BYREF
  __int64 v23; // [rsp+38h] [rbp-20h] BYREF
  void **v24; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-10h] BYREF

  v3 = (char *)this + 8;
  (*(void (__fastcall **)(char *, struct IXMLDOMNode *))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, a2);
  v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 24LL))(v3);
  v5 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 328LL);
  v6 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v22);
  v7 = v5(v4, v6);
  if ( v7 >= 0 )
  {
    v8 = (_QWORD *)((__int64 (__fastcall *)(void ***))v22[4])(&v22);
    v9 = ATL::CSimpleStringT<unsigned short,0>::StringLength(*v8);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 40, v10, v9);
    v24 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    v25[0] = 0;
    v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 24LL))(v3);
    v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 312LL);
    v13 = ((__int64 (__fastcall *)(void ***))v24[3])(&v24);
    v7 = v12(v11, v13);
    if ( v7 >= 0 )
    {
      v14 = (_QWORD *)((__int64 (__fastcall *)(void ***))v24[4])(&v24);
      v15 = ATL::CSimpleStringT<unsigned short,0>::StringLength(*v14);
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 48, v16, v15);
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 24LL))(v3);
      v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 80LL))(v17, (char *)this + 56);
      if ( v7 >= 0 )
      {
        if ( *((_DWORD *)this + 14) == 1
          && (v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 24LL))(v3),
              v19 = **v18,
              v20 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 8LL))((char *)this + 24),
              v7 = v19(v18, &IID_IXMLDOMElement, v20),
              v7 < 0) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v7,
            "PushButtonReset::XmlNode::Initialize",
            "base\\reset\\util\\src\\xml.cpp",
            544,
            L"Failed to cast NODE_ELEMENT IXMLDOMNode to IXMLDOMElement");
          v24 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(v25);
          v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v23);
        }
        else
        {
          v24 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(v25);
          v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v23);
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v7,
          "PushButtonReset::XmlNode::Initialize",
          "base\\reset\\util\\src\\xml.cpp",
          539,
          L"Failed to get node type");
        v24 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(v25);
        v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v23);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v7,
        "PushButtonReset::XmlNode::Initialize",
        "base\\reset\\util\\src\\xml.cpp",
        534,
        L"Failed to get namespace URI");
      v24 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(v25);
      v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v23);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "PushButtonReset::XmlNode::Initialize",
      "base\\reset\\util\\src\\xml.cpp",
      528,
      L"Failed to get base name");
    v22 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v23);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180059e54  push    rbp
0x180059e56  push    rbx
0x180059e57  push    rsi
0x180059e58  push    rdi
0x180059e59  push    r14
0x180059e5b  push    r15
0x180059e5d  mov     rbp, rsp
0x180059e60  sub     rsp, 58h
0x180059e64  mov     r14, rcx
0x180059e67  lea     rsi, [rcx+8]
0x180059e6b  mov     rax, [rsi]
0x180059e6e  mov     rcx, rsi
0x180059e71  mov     rax, [rax+30h]
0x180059e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e7a  lea     r15, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x180059e81  mov     [rbp+var_28], r15
0x180059e85  mov     [rbp+var_20], 0
0x180059e8d  mov     rax, [rsi]
0x180059e90  mov     rcx, rsi
0x180059e93  mov     rax, [rax+18h]
0x180059e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e9c  mov     rdi, rax
0x180059e9f  mov     rcx, [rax]
0x180059ea2  mov     rbx, [rcx+148h]
0x180059ea9  mov     rcx, [rbp+var_28]
0x180059ead  mov     rax, [rcx+18h]
0x180059eb1  lea     rcx, [rbp+var_28]
0x180059eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059eba  mov     rdx, rax
0x180059ebd  mov     rcx, rdi
0x180059ec0  mov     rax, rbx
0x180059ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ec8  mov     ebx, eax
0x180059eca  test    eax, eax
0x180059ecc  jns     short loc_180059F10
0x180059ece  lea     rax, aFailedToGetBas; "Failed to get base name"
0x180059ed5  mov     [rsp+58h+var_30], rax
0x180059eda  mov     [rsp+58h+var_38], 210h
0x180059ee2  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059ee9  lea     r8, aPushbuttonrese_91; "PushButtonReset::XmlNode::Initialize"
0x180059ef0  mov     edx, ebx
0x180059ef2  mov     ecx, 2
0x180059ef7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059efc  nop
0x180059efd  mov     [rbp+var_28], r15
0x180059f01  lea     rcx, [rbp+var_20]
0x180059f05  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059f0a  nop
0x180059f0b  jmp     loc_18005A135
0x180059f10  mov     rax, [rbp+var_28]
0x180059f14  lea     rcx, [rbp+var_28]
0x180059f18  mov     rax, [rax+20h]
0x180059f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f21  mov     r9, [rax]
0x180059f24  mov     rcx, r9
0x180059f27  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180059f2c  mov     r8d, eax
0x180059f2f  lea     rcx, [r14+28h]
0x180059f33  mov     rdx, r9
0x180059f36  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180059f3b  mov     [rbp+var_18], r15
0x180059f3f  mov     [rbp+var_10], 0
0x180059f47  mov     rax, [rsi]
0x180059f4a  mov     rcx, rsi
0x180059f4d  mov     rax, [rax+18h]
0x180059f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f56  mov     rdi, rax
0x180059f59  mov     rcx, [rax]
0x180059f5c  mov     rbx, [rcx+138h]
0x180059f63  mov     rcx, [rbp+var_18]
0x180059f67  mov     rax, [rcx+18h]
0x180059f6b  lea     rcx, [rbp+var_18]
0x180059f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f74  mov     rdx, rax
0x180059f77  mov     rcx, rdi
0x180059f7a  mov     rax, rbx
0x180059f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f82  mov     ebx, eax
0x180059f84  test    eax, eax
0x180059f86  jns     short loc_180059FD8
0x180059f88  lea     rax, aFailedToGetNam; "Failed to get namespace URI"
0x180059f8f  mov     [rsp+58h+var_30], rax
0x180059f94  mov     [rsp+58h+var_38], 216h
0x180059f9c  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059fa3  lea     r8, aPushbuttonrese_91; "PushButtonReset::XmlNode::Initialize"
0x180059faa  mov     edx, ebx
0x180059fac  mov     ecx, 2
0x180059fb1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059fb6  nop
0x180059fb7  mov     [rbp+var_18], r15
0x180059fbb  lea     rcx, [rbp+var_10]
0x180059fbf  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059fc4  nop
0x180059fc5  mov     [rbp+var_28], r15
0x180059fc9  lea     rcx, [rbp+var_20]
0x180059fcd  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059fd2  nop
0x180059fd3  jmp     loc_18005A135
0x180059fd8  mov     rax, [rbp+var_18]
0x180059fdc  lea     rcx, [rbp+var_18]
0x180059fe0  mov     rax, [rax+20h]
0x180059fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fe9  mov     r9, [rax]
0x180059fec  mov     rcx, r9
0x180059fef  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180059ff4  mov     r8d, eax
0x180059ff7  lea     rcx, [r14+30h]
0x180059ffb  mov     rdx, r9
0x180059ffe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18005a003  mov     rax, [rsi]
0x18005a006  mov     rcx, rsi
0x18005a009  mov     rax, [rax+18h]
0x18005a00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a012  mov     r8, rax
0x18005a015  mov     rcx, [rax]
0x18005a018  mov     rax, [rcx+50h]
0x18005a01c  lea     rdx, [r14+38h]
0x18005a020  mov     rcx, r8
0x18005a023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a028  mov     ebx, eax
0x18005a02a  test    eax, eax
0x18005a02c  jns     short loc_18005A07E
0x18005a02e  lea     rax, aFailedToGetNod; "Failed to get node type"
0x18005a035  mov     [rsp+58h+var_30], rax
0x18005a03a  mov     [rsp+58h+var_38], 21Bh
0x18005a042  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a049  lea     r8, aPushbuttonrese_91; "PushButtonReset::XmlNode::Initialize"
0x18005a050  mov     edx, ebx
0x18005a052  mov     ecx, 2
0x18005a057  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a05c  nop
0x18005a05d  mov     [rbp+var_18], r15
0x18005a061  lea     rcx, [rbp+var_10]
0x18005a065  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a06a  nop
0x18005a06b  mov     [rbp+var_28], r15
0x18005a06f  lea     rcx, [rbp+var_20]
0x18005a073  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a078  nop
0x18005a079  jmp     loc_18005A135
0x18005a07e  cmp     dword ptr [r14+38h], 1
0x18005a083  jnz     loc_18005A119
0x18005a089  mov     rax, [rsi]
0x18005a08c  mov     rcx, rsi
0x18005a08f  mov     rax, [rax+18h]
0x18005a093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a098  mov     rdi, rax
0x18005a09b  mov     rcx, [rax]
0x18005a09e  mov     rbx, [rcx]
0x18005a0a1  lea     rcx, [r14+18h]
0x18005a0a5  mov     rdx, [rcx]
0x18005a0a8  mov     rax, [rdx+8]
0x18005a0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0b1  mov     r8, rax
0x18005a0b4  lea     rdx, IID_IXMLDOMElement
0x18005a0bb  mov     rcx, rdi
0x18005a0be  mov     rax, rbx
0x18005a0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0c6  mov     ebx, eax
0x18005a0c8  test    eax, eax
0x18005a0ca  jns     short loc_18005A119
0x18005a0cc  lea     rax, aFailedToCastNo; "Failed to cast NODE_ELEMENT IXMLDOMNode"...
0x18005a0d3  mov     [rsp+58h+var_30], rax
0x18005a0d8  mov     [rsp+58h+var_38], 220h
0x18005a0e0  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a0e7  lea     r8, aPushbuttonrese_91; "PushButtonReset::XmlNode::Initialize"
0x18005a0ee  mov     edx, ebx
0x18005a0f0  mov     ecx, 2
0x18005a0f5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a0fa  nop
0x18005a0fb  mov     [rbp+var_18], r15
0x18005a0ff  lea     rcx, [rbp+var_10]
0x18005a103  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a108  nop
0x18005a109  mov     [rbp+var_28], r15
0x18005a10d  lea     rcx, [rbp+var_20]
0x18005a111  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a116  nop
0x18005a117  jmp     short loc_18005A135
0x18005a119  mov     [rbp+var_18], r15
0x18005a11d  lea     rcx, [rbp+var_10]
0x18005a121  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a126  nop
0x18005a127  mov     [rbp+var_28], r15
0x18005a12b  lea     rcx, [rbp+var_20]
0x18005a12f  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a134  nop
0x18005a135  mov     eax, ebx
0x18005a137  add     rsp, 58h
0x18005a13b  pop     r15
0x18005a13d  pop     r14
0x18005a13f  pop     rdi
0x18005a140  pop     rsi
0x18005a141  pop     rbx
0x18005a142  pop     rbp
0x18005a143  retn
```
