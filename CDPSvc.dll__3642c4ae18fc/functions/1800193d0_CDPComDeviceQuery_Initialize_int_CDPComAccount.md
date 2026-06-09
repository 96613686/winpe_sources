# CDPComDeviceQuery::Initialize(int,CDPComAccount *)

- ea: `0x1800193d0`
- end: `0x18001950e`
- name: `?Initialize@CDPComDeviceQuery@@UEAAJHPEAUCDPComAccount@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *this, unsigned __int64 *, struct CDPComAccount *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003e60`
- `0x18000aaf0`
- `0x18000cb8c`
- `0x180018264`
- `0x1800193d0`
- `0x18002b8a8`
- `0x180034d50`
- `0x1800429e0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800194cc`
- `msvcp_win!_Mtx_unlock` at `0x1800194cc`
- `cdp!CDPCreateAccountInternalForUser` at `0x180019466`
- `cdp!CDPCreateAccountInternalForUser` at `0x180019466`

## string_xrefs

- `0x180019401`: `.\cdpcomdevicequery.cpp`
- `0x18001947c`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDeviceQuery::Initialize(
        CDPComDeviceQuery *this,
        unsigned __int64 *a2,
        struct CDPComAccount *a3)
{
  int v4; // esi
  int CallerUserContextToken; // eax
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rdx
  __int64 result; // rax
  const char *v11; // rax
  int v12; // r8d
  _BYTE v13[48]; // [rsp+0h] [rbp-98h] BYREF
  const char *v14; // [rsp+30h] [rbp-68h] BYREF
  std::_Ref_count_base **v15; // [rsp+38h] [rbp-60h]
  std::_Ref_count_base *v16[2]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v17[64]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+18h] BYREF
  int v19; // [rsp+B8h] [rbp+20h]

  try
  {
    v4 = (int)a2;
    if ( a3 )
    {
      CallerUserContextToken = cdp::GetCallerUserContextToken((cdp *)&v18, a2);
      if ( CallerUserContextToken < 0 )
      {
        v14 = ".\\cdpcomdevicequery.cpp";
        LODWORD(v15) = 288;
        v7 = cdp::MakeException<cdp::hresult_exception>(v17, &v14, (unsigned int)CallerUserContextToken);
        cdp::CdpThrow<cdp::hresult_exception>(&v14, v7);
      }
      *(_OWORD *)v16 = 0;
      v14 = 0;
      v15 = v16;
      v8 = CDPCreateAccountInternalForUser(*(_QWORD *)a3, *((unsigned __int16 *)a3 + 4), v18, &v14);
      cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(&v14);
      if ( v8 < 0 )
      {
        v14 = ".\\cdpcomdevicequery.cpp";
        LODWORD(v15) = 291;
        v9 = cdp::MakeException<cdp::hresult_exception>(v17, &v14, (unsigned int)v8);
        cdp::CdpThrow<cdp::hresult_exception>(&v14, v9);
      }
      std::_Mutex_base::lock((CDPComDeviceQuery *)((char *)this + 24));
      std::shared_ptr<CDPComAppControlClient::LaunchCallback>::operator=((char *)this + 120, v16);
      _Mtx_unlock((CDPComDeviceQuery *)((char *)this + 24));
      if ( v16[1] )
        std::_Ref_count_base::_Decref(v16[1]);
    }
    *((_BYTE *)this + 160) = v4 != 0;
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v18) = -2147418113;
    LODWORD(v11) = GetCurrentThreadId();
    v14 = v11;
    v19 = 301;
    cdp::CatchAllToHR<char const (&)[24],int,unsigned __int64>(
      (unsigned int)v13 + 176,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      v12,
      (unsigned int)v13 + 184,
      (__int64)&v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800193d0  mov     rax, rsp
0x1800193d3  mov     [rax+8], rbx
0x1800193d7  mov     [rax+10h], rsi
0x1800193db  push    rdi
0x1800193dc  sub     rsp, 90h
0x1800193e3  mov     rdi, r8
0x1800193e6  mov     esi, edx
0x1800193e8  mov     rbx, rcx
0x1800193eb  test    r8, r8
0x1800193ee  jz      loc_1800194E2
0x1800193f4  lea     rcx, [rax+18h]; this
0x1800193f8  call    ?GetCallerUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCallerUserContextToken(unsigned __int64 &)
0x1800193fd  test    eax, eax
0x1800193ff  jns     short loc_180019436
0x180019401  lea     rcx, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180019408  mov     [rsp+98h+var_68], rcx
0x18001940d  mov     dword ptr [rsp+98h+var_60], 120h
0x180019415  mov     r8d, eax
0x180019418  lea     rdx, [rsp+98h+var_68]
0x18001941d  lea     rcx, [rsp+98h+var_48]
0x180019422  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180019427  nop
0x180019428  mov     rdx, rax
0x18001942b  lea     rcx, [rsp+98h+var_68]
0x180019430  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180019436  xorps   xmm0, xmm0
0x180019439  movdqu  xmmword ptr [rsp+98h+var_58], xmm0
0x18001943f  mov     [rsp+98h+var_68], 0
0x180019448  lea     rax, [rsp+98h+var_58]
0x18001944d  mov     [rsp+98h+var_60], rax
0x180019452  lea     r9, [rsp+98h+var_68]
0x180019457  mov     r8, [rsp+98h+arg_10]
0x18001945f  movzx   edx, word ptr [rdi+8]
0x180019463  mov     rcx, [rdi]
0x180019466  call    cs:__imp_CDPCreateAccountInternalForUser
0x18001946c  mov     edi, eax
0x18001946e  lea     rcx, [rsp+98h+var_68]
0x180019473  call    ??1?$address_of@VICDPAccount@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(void)
0x180019478  test    edi, edi
0x18001947a  jns     short loc_1800194B1
0x18001947c  lea     rcx, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180019483  mov     [rsp+98h+var_68], rcx
0x180019488  mov     dword ptr [rsp+98h+var_60], 123h
0x180019490  mov     r8d, edi
0x180019493  lea     rdx, [rsp+98h+var_68]
0x180019498  lea     rcx, [rsp+98h+var_48]
0x18001949d  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800194a2  nop
0x1800194a3  mov     rdx, rax
0x1800194a6  lea     rcx, [rsp+98h+var_68]
0x1800194ab  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800194b1  lea     rcx, [rbx+18h]; this
0x1800194b5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800194ba  lea     rcx, [rbx+78h]
0x1800194be  lea     rdx, [rsp+98h+var_58]
0x1800194c3  call    ??4?$shared_ptr@VLaunchCallback@CDPComAppControlClient@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CDPComAppControlClient::LaunchCallback>::operator=(std::shared_ptr<CDPComAppControlClient::LaunchCallback> const &)
0x1800194c8  lea     rcx, [rbx+18h]; _Mtx_t
0x1800194cc  call    cs:__imp__Mtx_unlock
0x1800194d2  nop
0x1800194d3  mov     rcx, [rsp+98h+var_58+8]; this
0x1800194d8  test    rcx, rcx
0x1800194db  jz      short loc_1800194E2
0x1800194dd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800194e2  test    esi, esi
0x1800194e4  setnz   al
0x1800194e7  mov     [rbx+0A0h], al
0x1800194ed  xor     eax, eax
0x1800194ef  jmp     short loc_1800194F8
0x1800194f1  mov     eax, dword ptr [rsp+98h+arg_10]
0x1800194f8  lea     r11, [rsp+98h+var_8]
0x180019500  mov     rbx, [r11+10h]
0x180019504  mov     rsi, [r11+18h]
0x180019508  mov     rsp, r11
0x18001950b  pop     rdi
0x18001950c  retn
```
