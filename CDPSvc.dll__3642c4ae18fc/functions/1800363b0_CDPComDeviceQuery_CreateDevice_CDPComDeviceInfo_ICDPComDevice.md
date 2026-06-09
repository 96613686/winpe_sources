# CDPComDeviceQuery::CreateDevice(CDPComDeviceInfo *,ICDPComDevice * *)

- ea: `0x1800363b0`
- end: `0x180036682`
- name: `?CreateDevice@CDPComDeviceQuery@@UEAAJPEAUCDPComDeviceInfo@@PEAPEAUICDPComDevice@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *this, struct CDPComDeviceInfo *, struct ICDPComDevice **)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003d64`
- `0x180003de4`
- `0x180003e60`
- `0x180018970`
- `0x18001ddf8`
- `0x1800225d0`
- `0x18002b8a8`
- `0x180030b70`
- `0x180034c60`
- `0x180034d50`
- `0x180035294`
- `0x180035670`
- `0x1800363b0`
- `0x1800429e0`
- `0x18006a010`

## string_xrefs

- `0x1800363e7`: `.\cdpcomdevicequery.cpp`
- `0x18003642b`: `.\cdpcomdevicequery.cpp`
- `0x180036487`: `.\cdpcomdevicequery.cpp`
- `0x1800364d0`: `.\cdpcomdevicequery.cpp`
- `0x180036574`: `.\cdpcomdevicequery.cpp`
- `0x1800365d6`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDPComDeviceQuery::CreateDevice(
        CDPComDeviceQuery *this,
        struct CDPComDeviceInfo *a2,
        struct ICDPComDevice **a3)
{
  __int64 result; // rax
  int v6; // ebx
  unsigned __int64 *v7; // rdx
  __int64 v8; // rdx
  int CallerUserContextToken; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rdx
  struct ICDPComDevice *v15; // rax
  unsigned __int64 v16; // rax
  int v17; // r8d
  struct ICDPDeviceQuery *v18; // [rsp+30h] [rbp-A8h] BYREF
  std::_Ref_count_base **v19; // [rsp+38h] [rbp-A0h]
  unsigned __int64 v20; // [rsp+40h] [rbp-98h] BYREF
  struct ICDPComDevice *v21; // [rsp+48h] [rbp-90h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+50h] [rbp-88h] BYREF
  std::_Ref_count_base *v23[2]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v24; // [rsp+70h] [rbp-68h] BYREF
  std::_Ref_count_base *v25; // [rsp+78h] [rbp-60h]
  _QWORD v26[3]; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v27[56]; // [rsp+98h] [rbp-40h] BYREF
  CDPComDeviceQuery::CDPDeviceInfo *v28; // [rsp+E8h] [rbp+10h] BYREF
  int v29; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    if ( a2 )
    {
      if ( a3 )
      {
        *(_OWORD *)v23 = 0;
        *(_OWORD *)v22 = 0;
        v18 = 0;
        v19 = v22;
        v6 = CDPComDeviceQuery::CreateDeviceQueryInternalSafe(this, &v18);
        cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(&v18);
        if ( v6 < 0 )
        {
          v18 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v19) = 178;
          v8 = cdp::MakeException<cdp::hresult_exception>(v27, &v18, (unsigned int)v6);
          cdp::CdpThrow<cdp::hresult_exception>(&v18, v8);
        }
        CallerUserContextToken = cdp::GetCallerUserContextToken((cdp *)&v20, v7);
        if ( CallerUserContextToken < 0 )
        {
          v18 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v19) = 181;
          v10 = cdp::MakeException<cdp::hresult_exception>(v27, &v18, (unsigned int)CallerUserContextToken);
          cdp::CdpThrow<cdp::hresult_exception>(&v18, v10);
        }
        v28 = (CDPComDeviceQuery::CDPDeviceInfo *)operator new(0x1B8u);
        v11 = CDPComDeviceQuery::CDPDeviceInfo::CDPDeviceInfo(v28, a2, v20);
        cdp::detail::wrap_unknown<CDPComDeviceQuery::CDPDeviceInfo>(&v24, v11);
        v12 = *(_QWORD *)v22[0];
        v18 = 0;
        v19 = v23;
        v13 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64, struct ICDPDeviceQuery **))(v12 + 104))(
                v22[0],
                v24,
                &v18);
        cdp::detail::address_of<ICDPDevice>::~address_of<ICDPDevice>(&v18);
        if ( v13 < 0 )
        {
          v18 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v19) = 185;
          v14 = cdp::MakeException<cdp::hresult_exception>(v27, &v18, (unsigned int)v13);
          cdp::CdpThrow<cdp::hresult_exception>(&v18, v14);
        }
        v28 = v23[0];
        Microsoft::WRL::Details::Make<CDPComDevice,ICDPDevice * &>(&v21, &v28);
        v15 = v21;
        if ( !v21 )
        {
          v18 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v19) = 188;
          v26[2] = 0;
          v26[1] = "bad allocation";
          v26[0] = &std::bad_alloc::`vftable';
          cdp::CdpThrow<std::bad_alloc>(&v18, v26);
        }
        v21 = 0;
        *a3 = v15;
        if ( v25 )
          std::_Ref_count_base::_Decref(v25);
        if ( v22[1] )
          std::_Ref_count_base::_Decref(v22[1]);
        if ( v23[1] )
          std::_Ref_count_base::_Decref(v23[1]);
        result = 0;
      }
      else
      {
        LODWORD(v28) = -2147467261;
        v29 = 173;
        Log<long &,char const (&)[28],int>(
          (_DWORD)this,
          (_DWORD)a2,
          (unsigned int)&v28,
          (unsigned int)".\\cdpcomdevicequery.cpp",
          (__int64)&v29);
        result = (unsigned int)v28;
      }
    }
    else
    {
      LODWORD(v28) = -2147024809;
      v29 = 172;
      Log<long &,char const (&)[28],int>(
        (_DWORD)this,
        0,
        (unsigned int)&v28,
        (unsigned int)".\\cdpcomdevicequery.cpp",
        (__int64)&v29);
      result = (unsigned int)v28;
    }
  }
  catch ( ... )
  {
    LODWORD(v28) = -2147418113;
    LODWORD(v16) = GetCurrentThreadId();
    v20 = v16;
    v29 = 192;
    cdp::CatchAllToHR<char const (&)[24],int,unsigned __int64>(
      (unsigned int)&v28,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      v17,
      (unsigned int)&v29,
      (__int64)&v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800363b0  mov     r11, rsp
0x1800363b3  mov     [r11+8], rbx
0x1800363b7  mov     [r11+18h], rsi
0x1800363bb  push    rdi
0x1800363bc  sub     rsp, 0D0h
0x1800363c3  mov     rsi, r8
0x1800363c6  mov     rdi, rdx
0x1800363c9  test    rdx, rdx
0x1800363cc  jnz     short loc_180036403
0x1800363ce  mov     dword ptr [r11+10h], 80070057h
0x1800363d6  mov     dword ptr [r11+20h], 0ACh
0x1800363de  lea     rax, [r11+20h]
0x1800363e2  mov     [rsp+0D8h+var_B8], rax
0x1800363e7  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x1800363ee  lea     r8, [r11+10h]
0x1800363f2  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x1800363f7  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x1800363fe  jmp     loc_18003666C
0x180036403  test    rsi, rsi
0x180036406  jnz     short loc_18003644B
0x180036408  mov     dword ptr [rsp+0D8h+arg_8], 80004003h
0x180036413  mov     [rsp+0D8h+arg_18], 0ADh
0x18003641e  lea     rax, [rsp+0D8h+arg_18]
0x180036426  mov     [rsp+0D8h+var_B8], rax
0x18003642b  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180036432  lea     r8, [rsp+0D8h+arg_8]
0x18003643a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003643f  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x180036446  jmp     loc_18003666C
0x18003644b  xorps   xmm0, xmm0
0x18003644e  movdqu  xmmword ptr [rsp+0D8h+var_78], xmm0
0x180036454  movdqu  xmmword ptr [rsp+0D8h+var_88], xmm0
0x18003645a  mov     [rsp+0D8h+var_A8], 0
0x180036463  lea     rax, [rsp+0D8h+var_88]
0x180036468  mov     [rsp+0D8h+var_A0], rax
0x18003646d  lea     rdx, [rsp+0D8h+var_A8]; struct ICDPDeviceQuery **
0x180036472  call    ?CreateDeviceQueryInternalSafe@CDPComDeviceQuery@@AEAAJPEAPEAVICDPDeviceQuery@@@Z; CDPComDeviceQuery::CreateDeviceQueryInternalSafe(ICDPDeviceQuery * *)
0x180036477  mov     ebx, eax
0x180036479  lea     rcx, [rsp+0D8h+var_A8]
0x18003647e  call    ??1?$address_of@VICDPDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(void)
0x180036483  test    ebx, ebx
0x180036485  jns     short loc_1800364BF
0x180036487  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18003648e  mov     [rsp+0D8h+var_A8], rax
0x180036493  mov     dword ptr [rsp+0D8h+var_A0], 0B2h
0x18003649b  mov     r8d, ebx
0x18003649e  lea     rdx, [rsp+0D8h+var_A8]
0x1800364a3  lea     rcx, [rsp+0D8h+var_40]
0x1800364ab  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800364b0  nop
0x1800364b1  mov     rdx, rax
0x1800364b4  lea     rcx, [rsp+0D8h+var_A8]
0x1800364b9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800364bf  lea     rcx, [rsp+0D8h+var_98]; this
0x1800364c4  call    ?GetCallerUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCallerUserContextToken(unsigned __int64 &)
0x1800364c9  mov     r8d, eax
0x1800364cc  test    eax, eax
0x1800364ce  jns     short loc_180036505
0x1800364d0  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x1800364d7  mov     [rsp+0D8h+var_A8], rax
0x1800364dc  mov     dword ptr [rsp+0D8h+var_A0], 0B5h
0x1800364e4  lea     rdx, [rsp+0D8h+var_A8]
0x1800364e9  lea     rcx, [rsp+0D8h+var_40]
0x1800364f1  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800364f6  nop
0x1800364f7  mov     rdx, rax
0x1800364fa  lea     rcx, [rsp+0D8h+var_A8]
0x1800364ff  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180036505  mov     ecx, 1B8h; Size
0x18003650a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003650f  mov     [rsp+0D8h+arg_8], rax
0x180036517  mov     r8, [rsp+0D8h+var_98]; unsigned __int64
0x18003651c  mov     rdx, rdi; struct CDPComDeviceInfo *
0x18003651f  mov     rcx, rax; this
0x180036522  call    ??0CDPDeviceInfo@CDPComDeviceQuery@@QEAA@PEAUCDPComDeviceInfo@@_K@Z; CDPComDeviceQuery::CDPDeviceInfo::CDPDeviceInfo(CDPComDeviceInfo *,unsigned __int64)
0x180036527  nop
0x180036528  mov     rdx, rax
0x18003652b  lea     rcx, [rsp+0D8h+var_68]
0x180036530  call    ??$wrap_unknown@VCDPDeviceInfo@CDPComDeviceQuery@@@detail@cdp@@YA?AV?$shared_ptr@VCDPDeviceInfo@CDPComDeviceQuery@@@std@@PEAVCDPDeviceInfo@CDPComDeviceQuery@@_N@Z; cdp::detail::wrap_unknown<CDPComDeviceQuery::CDPDeviceInfo>(CDPComDeviceQuery::CDPDeviceInfo *,bool)
0x180036535  nop
0x180036536  mov     rcx, [rsp+0D8h+var_88]
0x18003653b  mov     rax, [rcx]
0x18003653e  mov     [rsp+0D8h+var_A8], 0
0x180036547  lea     rdx, [rsp+0D8h+var_78]
0x18003654c  mov     [rsp+0D8h+var_A0], rdx
0x180036551  lea     r8, [rsp+0D8h+var_A8]
0x180036556  mov     rdx, [rsp+0D8h+var_68]
0x18003655b  mov     rax, [rax+68h]
0x18003655f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036564  mov     ebx, eax
0x180036566  lea     rcx, [rsp+0D8h+var_A8]
0x18003656b  call    ??1?$address_of@VICDPDevice@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDevice>::~address_of<ICDPDevice>(void)
0x180036570  test    ebx, ebx
0x180036572  jns     short loc_1800365AC
0x180036574  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18003657b  mov     [rsp+0D8h+var_A8], rax
0x180036580  mov     dword ptr [rsp+0D8h+var_A0], 0B9h
0x180036588  mov     r8d, ebx
0x18003658b  lea     rdx, [rsp+0D8h+var_A8]
0x180036590  lea     rcx, [rsp+0D8h+var_40]
0x180036598  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18003659d  nop
0x18003659e  mov     rdx, rax
0x1800365a1  lea     rcx, [rsp+0D8h+var_A8]
0x1800365a6  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800365ac  mov     rax, [rsp+0D8h+var_78]
0x1800365b1  mov     [rsp+0D8h+arg_8], rax
0x1800365b9  lea     rdx, [rsp+0D8h+arg_8]
0x1800365c1  lea     rcx, [rsp+0D8h+var_90]
0x1800365c6  call    ??$Make@VCDPComDevice@@AEAPEAVICDPDevice@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDPComDevice@@@12@AEAPEAVICDPDevice@@@Z; Microsoft::WRL::Details::Make<CDPComDevice,ICDPDevice * &>(ICDPDevice * &)
0x1800365cb  nop
0x1800365cc  mov     rax, [rsp+0D8h+var_90]
0x1800365d1  test    rax, rax
0x1800365d4  jnz     short loc_180036626
0x1800365d6  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x1800365dd  mov     [rsp+0D8h+var_A8], rax
0x1800365e2  mov     dword ptr [rsp+0D8h+var_A0], 0BCh
0x1800365ea  xorps   xmm0, xmm0
0x1800365ed  movups  [rsp+0D8h+var_50], xmm0
0x1800365f5  lea     rax, aBadAllocation; "bad allocation"
0x1800365fc  mov     qword ptr [rsp+0D8h+var_50], rax
0x180036604  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18003660b  mov     [rsp+0D8h+var_58], rax
0x180036613  lea     rdx, [rsp+0D8h+var_58]
0x18003661b  lea     rcx, [rsp+0D8h+var_A8]
0x180036620  call    ??$CdpThrow@Vbad_alloc@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVbad_alloc@std@@@Z; cdp::CdpThrow<std::bad_alloc>(cdp::CDPSourceLocationInfo const &,std::bad_alloc &&)
0x180036626  mov     [rsp+0D8h+var_90], 0
0x18003662f  mov     [rsi], rax
0x180036632  mov     rcx, [rsp+0D8h+var_60]; this
0x180036637  test    rcx, rcx
0x18003663a  jz      short loc_180036642
0x18003663c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036641  nop
0x180036642  mov     rcx, [rsp+0D8h+var_88+8]; this
0x180036647  test    rcx, rcx
0x18003664a  jz      short loc_180036652
0x18003664c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036651  nop
0x180036652  mov     rcx, [rsp+0D8h+var_78+8]; this
0x180036657  test    rcx, rcx
0x18003665a  jz      short loc_180036661
0x18003665c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036661  xor     eax, eax
0x180036663  jmp     short loc_18003666C
0x180036665  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x18003666c  lea     r11, [rsp+0D8h+var_8]
0x180036674  mov     rbx, [r11+10h]
0x180036678  mov     rsi, [r11+20h]
0x18003667c  mov     rsp, r11
0x18003667f  pop     rdi
0x180036680  retn
```
