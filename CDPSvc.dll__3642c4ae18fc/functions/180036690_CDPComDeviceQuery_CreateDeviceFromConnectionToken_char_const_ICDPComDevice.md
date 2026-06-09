# CDPComDeviceQuery::CreateDeviceFromConnectionToken(char const *,ICDPComDevice * *)

- ea: `0x180036690`
- end: `0x180036919`
- name: `?CreateDeviceFromConnectionToken@CDPComDeviceQuery@@UEAAJPEBDPEAPEAUICDPComDevice@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *__hidden this, const char *, struct ICDPComDevice **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003d64`
- `0x180003de4`
- `0x180003e60`
- `0x180018970`
- `0x18001ddf8`
- `0x18002b8a8`
- `0x180030b70`
- `0x180034c60`
- `0x180034d50`
- `0x180036690`
- `0x1800429e0`
- `0x18006a010`

## string_xrefs

- `0x1800366c7`: `.\cdpcomdevicequery.cpp`
- `0x18003670b`: `.\cdpcomdevicequery.cpp`
- `0x180036761`: `.\cdpcomdevicequery.cpp`
- `0x1800367ad`: `.\cdpcomdevicequery.cpp`
- `0x180036827`: `.\cdpcomdevicequery.cpp`
- `0x180036889`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDPComDeviceQuery::CreateDeviceFromConnectionToken(
        CDPComDeviceQuery *this,
        const char *a2,
        struct ICDPComDevice **a3)
{
  __int64 result; // rax
  int v6; // edi
  unsigned __int64 *v7; // rdx
  __int64 v8; // rdx
  int CallerUserContextToken; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // edi
  __int64 v13; // rdx
  struct ICDPComDevice *v14; // rax
  struct ICDPComDevice *v15; // rax
  int v16; // r8d
  struct ICDPDeviceQuery *v17; // [rsp+30h] [rbp-98h] BYREF
  std::_Ref_count_base **v18; // [rsp+38h] [rbp-90h]
  struct ICDPComDevice *v19; // [rsp+40h] [rbp-88h] BYREF
  std::_Ref_count_base *v20[2]; // [rsp+48h] [rbp-80h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v22[3]; // [rsp+68h] [rbp-60h] BYREF
  char v23[8]; // [rsp+80h] [rbp-48h] BYREF
  _BYTE v24[56]; // [rsp+88h] [rbp-40h] BYREF
  std::_Ref_count_base *v25; // [rsp+D8h] [rbp+10h] BYREF
  int v26; // [rsp+E8h] [rbp+20h] BYREF

  try
  {
    if ( a2 )
    {
      if ( a3 )
      {
        *(_OWORD *)v21 = 0;
        v17 = 0;
        v18 = v21;
        v6 = CDPComDeviceQuery::CreateDeviceQueryInternalSafe(this, &v17);
        cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(&v17);
        if ( v6 < 0 )
        {
          v17 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v18) = 203;
          v8 = cdp::MakeException<cdp::hresult_exception>(v24, &v17, (unsigned int)v6);
          cdp::CdpThrow<cdp::hresult_exception>(&v17, v8);
        }
        CallerUserContextToken = cdp::GetCallerUserContextToken((cdp *)v23, v7);
        if ( CallerUserContextToken < 0 )
        {
          v17 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v18) = 206;
          v10 = cdp::MakeException<cdp::hresult_exception>(v24, &v17, (unsigned int)CallerUserContextToken);
          cdp::CdpThrow<cdp::hresult_exception>(&v17, v10);
        }
        *(_OWORD *)v20 = 0;
        v11 = *(_QWORD *)v21[0];
        v17 = 0;
        v18 = v20;
        v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, const char *, struct ICDPDeviceQuery **))(v11 + 112))(
                v21[0],
                a2,
                &v17);
        cdp::detail::address_of<ICDPDevice>::~address_of<ICDPDevice>(&v17);
        if ( v12 < 0 )
        {
          v17 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v18) = 209;
          v13 = cdp::MakeException<cdp::hresult_exception>(v24, &v17, (unsigned int)v12);
          cdp::CdpThrow<cdp::hresult_exception>(&v17, v13);
        }
        v25 = v20[0];
        Microsoft::WRL::Details::Make<CDPComDevice,ICDPDevice * &>(&v19, &v25);
        v14 = v19;
        if ( !v19 )
        {
          v17 = (struct ICDPDeviceQuery *)".\\cdpcomdevicequery.cpp";
          LODWORD(v18) = 212;
          v22[2] = 0;
          v22[1] = "bad allocation";
          v22[0] = &std::bad_alloc::`vftable';
          cdp::CdpThrow<std::bad_alloc>(&v17, v22);
        }
        v19 = 0;
        *a3 = v14;
        if ( v20[1] )
          std::_Ref_count_base::_Decref(v20[1]);
        if ( v21[1] )
          std::_Ref_count_base::_Decref(v21[1]);
        result = 0;
      }
      else
      {
        LODWORD(v25) = -2147467261;
        v26 = 200;
        Log<long &,char const (&)[28],int>(
          (_DWORD)this,
          (_DWORD)a2,
          (unsigned int)&v25,
          (unsigned int)".\\cdpcomdevicequery.cpp",
          (__int64)&v26);
        result = (unsigned int)v25;
      }
    }
    else
    {
      LODWORD(v25) = -2147024809;
      v26 = 199;
      Log<long &,char const (&)[28],int>(
        (_DWORD)this,
        0,
        (unsigned int)&v25,
        (unsigned int)".\\cdpcomdevicequery.cpp",
        (__int64)&v26);
      result = (unsigned int)v25;
    }
  }
  catch ( ... )
  {
    LODWORD(v25) = -2147418113;
    LODWORD(v15) = GetCurrentThreadId();
    v19 = v15;
    v26 = 216;
    cdp::CatchAllToHR<char const (&)[24],int,unsigned __int64>(
      (unsigned int)&v25,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      v16,
      (unsigned int)&v26,
      (__int64)&v19);
  }
  return result;
}

```

## disassembly

```asm
0x180036690  mov     r11, rsp
0x180036693  mov     [r11+8], rbx
0x180036697  mov     [r11+18h], rsi
0x18003669b  push    rdi
0x18003669c  sub     rsp, 0C0h
0x1800366a3  mov     rbx, r8
0x1800366a6  mov     rsi, rdx
0x1800366a9  test    rdx, rdx
0x1800366ac  jnz     short loc_1800366E3
0x1800366ae  mov     dword ptr [r11+10h], 80070057h
0x1800366b6  mov     dword ptr [r11+20h], 0C7h
0x1800366be  lea     rax, [r11+20h]
0x1800366c2  mov     [rsp+0C8h+var_A8], rax
0x1800366c7  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x1800366ce  lea     r8, [r11+10h]
0x1800366d2  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x1800366d7  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x1800366de  jmp     loc_180036903
0x1800366e3  test    rbx, rbx
0x1800366e6  jnz     short loc_18003672B
0x1800366e8  mov     dword ptr [rsp+0C8h+arg_8], 80004003h
0x1800366f3  mov     [rsp+0C8h+arg_18], 0C8h
0x1800366fe  lea     rax, [rsp+0C8h+arg_18]
0x180036706  mov     [rsp+0C8h+var_A8], rax
0x18003670b  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180036712  lea     r8, [rsp+0C8h+arg_8]
0x18003671a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003671f  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180036726  jmp     loc_180036903
0x18003672b  xorps   xmm0, xmm0
0x18003672e  movdqu  xmmword ptr [rsp+0C8h+var_70], xmm0
0x180036734  mov     [rsp+0C8h+var_98], 0
0x18003673d  lea     rax, [rsp+0C8h+var_70]
0x180036742  mov     [rsp+0C8h+var_90], rax
0x180036747  lea     rdx, [rsp+0C8h+var_98]; struct ICDPDeviceQuery **
0x18003674c  call    ?CreateDeviceQueryInternalSafe@CDPComDeviceQuery@@AEAAJPEAPEAVICDPDeviceQuery@@@Z; CDPComDeviceQuery::CreateDeviceQueryInternalSafe(ICDPDeviceQuery * *)
0x180036751  mov     edi, eax
0x180036753  lea     rcx, [rsp+0C8h+var_98]
0x180036758  call    ??1?$address_of@VICDPDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(void)
0x18003675d  test    edi, edi
0x18003675f  jns     short loc_180036799
0x180036761  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180036768  mov     [rsp+0C8h+var_98], rax
0x18003676d  mov     dword ptr [rsp+0C8h+var_90], 0CBh
0x180036775  mov     r8d, edi
0x180036778  lea     rdx, [rsp+0C8h+var_98]
0x18003677d  lea     rcx, [rsp+0C8h+var_40]
0x180036785  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18003678a  nop
0x18003678b  mov     rdx, rax
0x18003678e  lea     rcx, [rsp+0C8h+var_98]
0x180036793  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180036799  lea     rcx, [rsp+0C8h+var_48]; this
0x1800367a1  call    ?GetCallerUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCallerUserContextToken(unsigned __int64 &)
0x1800367a6  mov     r8d, eax
0x1800367a9  test    eax, eax
0x1800367ab  jns     short loc_1800367E2
0x1800367ad  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x1800367b4  mov     [rsp+0C8h+var_98], rax
0x1800367b9  mov     dword ptr [rsp+0C8h+var_90], 0CEh
0x1800367c1  lea     rdx, [rsp+0C8h+var_98]
0x1800367c6  lea     rcx, [rsp+0C8h+var_40]
0x1800367ce  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800367d3  nop
0x1800367d4  mov     rdx, rax
0x1800367d7  lea     rcx, [rsp+0C8h+var_98]
0x1800367dc  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800367e2  xorps   xmm0, xmm0
0x1800367e5  movdqu  xmmword ptr [rsp+0C8h+var_80], xmm0
0x1800367eb  mov     rcx, [rsp+0C8h+var_70]
0x1800367f0  mov     rax, [rcx]
0x1800367f3  mov     [rsp+0C8h+var_98], 0
0x1800367fc  lea     rdx, [rsp+0C8h+var_80]
0x180036801  mov     [rsp+0C8h+var_90], rdx
0x180036806  lea     r8, [rsp+0C8h+var_98]
0x18003680b  mov     rdx, rsi
0x18003680e  mov     rax, [rax+70h]
0x180036812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036817  mov     edi, eax
0x180036819  lea     rcx, [rsp+0C8h+var_98]
0x18003681e  call    ??1?$address_of@VICDPDevice@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDevice>::~address_of<ICDPDevice>(void)
0x180036823  test    edi, edi
0x180036825  jns     short loc_18003685F
0x180036827  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18003682e  mov     [rsp+0C8h+var_98], rax
0x180036833  mov     dword ptr [rsp+0C8h+var_90], 0D1h
0x18003683b  mov     r8d, edi
0x18003683e  lea     rdx, [rsp+0C8h+var_98]
0x180036843  lea     rcx, [rsp+0C8h+var_40]
0x18003684b  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180036850  nop
0x180036851  mov     rdx, rax
0x180036854  lea     rcx, [rsp+0C8h+var_98]
0x180036859  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18003685f  mov     rax, [rsp+0C8h+var_80]
0x180036864  mov     [rsp+0C8h+arg_8], rax
0x18003686c  lea     rdx, [rsp+0C8h+arg_8]
0x180036874  lea     rcx, [rsp+0C8h+var_88]
0x180036879  call    ??$Make@VCDPComDevice@@AEAPEAVICDPDevice@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDPComDevice@@@12@AEAPEAVICDPDevice@@@Z; Microsoft::WRL::Details::Make<CDPComDevice,ICDPDevice * &>(ICDPDevice * &)
0x18003687e  nop
0x18003687f  mov     rax, [rsp+0C8h+var_88]
0x180036884  test    rax, rax
0x180036887  jnz     short loc_1800368CD
0x180036889  lea     rax, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180036890  mov     [rsp+0C8h+var_98], rax
0x180036895  mov     dword ptr [rsp+0C8h+var_90], 0D4h
0x18003689d  xorps   xmm0, xmm0
0x1800368a0  movups  [rsp+0C8h+var_58], xmm0
0x1800368a5  lea     rax, aBadAllocation; "bad allocation"
0x1800368ac  mov     qword ptr [rsp+0C8h+var_58], rax
0x1800368b1  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800368b8  mov     [rsp+0C8h+var_60], rax
0x1800368bd  lea     rdx, [rsp+0C8h+var_60]
0x1800368c2  lea     rcx, [rsp+0C8h+var_98]
0x1800368c7  call    ??$CdpThrow@Vbad_alloc@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVbad_alloc@std@@@Z; cdp::CdpThrow<std::bad_alloc>(cdp::CDPSourceLocationInfo const &,std::bad_alloc &&)
0x1800368cd  mov     [rsp+0C8h+var_88], 0
0x1800368d6  mov     [rbx], rax
0x1800368d9  mov     rcx, [rsp+0C8h+var_80+8]; this
0x1800368de  test    rcx, rcx
0x1800368e1  jz      short loc_1800368E9
0x1800368e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800368e8  nop
0x1800368e9  mov     rcx, [rsp+0C8h+var_70+8]; this
0x1800368ee  test    rcx, rcx
0x1800368f1  jz      short loc_1800368F8
0x1800368f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800368f8  xor     eax, eax
0x1800368fa  jmp     short loc_180036903
0x1800368fc  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180036903  lea     r11, [rsp+0C8h+var_8]
0x18003690b  mov     rbx, [r11+10h]
0x18003690f  mov     rsi, [r11+20h]
0x180036913  mov     rsp, r11
0x180036916  pop     rdi
0x180036917  retn
```
