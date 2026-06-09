# CDPComBeaconControl::EnsureBeaconControl(void)

- ea: `0x18002be1c`
- end: `0x18002becc`
- name: `?EnsureBeaconControl@CDPComBeaconControl@@AEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(CDPComBeaconControl *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002bfb0`
- `0x18002c010`

## callees

- `0x18000cb8c`
- `0x180017e74`
- `0x18002b8a8`
- `0x18002b9c8`
- `0x18002be1c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002beaf`
- `msvcp_win!_Mtx_unlock` at `0x18002beaf`
- `cdp!CDPCreateBeaconControlInternal` at `0x18002be5a`
- `cdp!CDPCreateBeaconControlInternal` at `0x18002be5a`

## string_xrefs

- `0x18002be70`: `.\cdpcombeaconcontrol.cpp`
- `0x18002be84`: `Could not create beacon control (internal) through the ABI.`

## pseudocode

```c
__int64 __fastcall CDPComBeaconControl::EnsureBeaconControl(CDPComBeaconControl *this)
{
  struct _Mtx_internal_imp_t *v2; // rdi
  _QWORD *v3; // rsi
  int v4; // esi
  __int64 v5; // rdx
  _BYTE v7[48]; // [rsp+0h] [rbp-98h] BYREF
  const char *v8; // [rsp+30h] [rbp-68h] BYREF
  _QWORD *v9; // [rsp+38h] [rbp-60h]
  _BYTE v10[88]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+B0h] [rbp+18h] BYREF

  try
  {
    v2 = (CDPComBeaconControl *)((char *)this + 24);
    std::_Mutex_base::lock((CDPComBeaconControl *)((char *)this + 24));
    v3 = (_QWORD *)((char *)this + 104);
    if ( !*v3 )
    {
      v8 = 0;
      v9 = v3;
      v4 = CDPCreateBeaconControlInternal(&v8);
      cdp::detail::address_of<ICDPBeaconControl>::~address_of<ICDPBeaconControl>(&v8);
      if ( v4 < 0 )
      {
        v8 = ".\\cdpcombeaconcontrol.cpp";
        LODWORD(v9) = 48;
        v5 = cdp::MakeException<cdp::hresult_exception,>(
               v10,
               &v8,
               (unsigned int)v4,
               "Could not create beacon control (internal) through the ABI.");
        cdp::CdpThrow<cdp::hresult_exception>(&v8, v5);
      }
    }
    _Mtx_unlock(v2);
  }
  catch ( ... )
  {
    GetCurrentThreadId();
    cdp::CatchAllToHR<char const (&)[26],int,unsigned __int64>(
      (unsigned int)v7 + 160,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failure creating beacon control.\"}",
      (unsigned int)".\\cdpcombeaconcontrol.cpp",
      (unsigned int)v7 + 168,
      (__int64)&v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18002be1c  mov     rax, rsp
0x18002be1f  push    rbx
0x18002be20  push    rsi
0x18002be21  push    rdi
0x18002be22  sub     rsp, 80h
0x18002be29  mov     rsi, rcx
0x18002be2c  xor     ebx, ebx
0x18002be2e  mov     [rax+8], ebx
0x18002be31  lea     rdi, [rcx+18h]
0x18002be35  mov     [rax+10h], rdi
0x18002be39  mov     rcx, rdi; this
0x18002be3c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002be41  nop
0x18002be42  add     rsi, 68h ; 'h'
0x18002be46  cmp     [rsi], rbx
0x18002be49  jnz     short loc_18002BEAC
0x18002be4b  mov     [rsp+98h+var_68], rbx
0x18002be50  mov     [rsp+98h+var_60], rsi
0x18002be55  lea     rcx, [rsp+98h+var_68]
0x18002be5a  call    cs:__imp_CDPCreateBeaconControlInternal
0x18002be60  mov     esi, eax
0x18002be62  lea     rcx, [rsp+98h+var_68]
0x18002be67  call    ??1?$address_of@VICDPBeaconControl@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPBeaconControl>::~address_of<ICDPBeaconControl>(void)
0x18002be6c  test    esi, esi
0x18002be6e  jns     short loc_18002BEAC
0x18002be70  lea     rax, aCdpcombeaconco; ".\\cdpcombeaconcontrol.cpp"
0x18002be77  mov     [rsp+98h+var_68], rax
0x18002be7c  mov     dword ptr [rsp+98h+var_60], 30h ; '0'
0x18002be84  lea     r9, aCouldNotCreate; "Could not create beacon control (intern"...
0x18002be8b  mov     r8d, esi
0x18002be8e  lea     rdx, [rsp+98h+var_68]
0x18002be93  lea     rcx, [rsp+98h+var_58]
0x18002be98  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18002be9d  nop
0x18002be9e  mov     rdx, rax
0x18002bea1  lea     rcx, [rsp+98h+var_68]
0x18002bea6  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18002beac  mov     rcx, rdi; _Mtx_t
0x18002beaf  call    cs:__imp__Mtx_unlock
0x18002beb5  nop
0x18002beb6  jmp     short loc_18002BEBF
0x18002beb8  mov     ebx, [rsp+98h+arg_0]
0x18002bebf  mov     eax, ebx
0x18002bec1  add     rsp, 80h
0x18002bec8  pop     rdi
0x18002bec9  pop     rsi
0x18002beca  pop     rbx
0x18002becb  retn
```
