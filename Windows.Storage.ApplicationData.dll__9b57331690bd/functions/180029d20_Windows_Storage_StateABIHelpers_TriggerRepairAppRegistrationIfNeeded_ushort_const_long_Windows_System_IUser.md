# Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)

- ea: `0x180029d20`
- end: `0x180029dea`
- name: `?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z`
- size: `202`
- prototype: `void __fastcall(const wchar_t *operation, const HRESULT inputHr, Windows::System::IUser *userParam)`
- caller_count: `10`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007f98`
- `0x180012d50`
- `0x1800199f4`
- `0x180021440`
- `0x180035c28`
- `0x180036abc`
- `0x180037c60`
- `0x18003eae0`
- `0x18003ec70`
- `0x18003ee28`

## callees

- `0x1800186bc`
- `0x1800207c0`
- `0x180029ad8`
- `0x180029d20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180029db1`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180029db1`

## string_xrefs

- `0x180029d7c`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x180029dcc`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x180029dc0`: `The calling thread/process token is restricted. Skip auto repair as it may not fix the issue. Failed operation: %ws`
- `0x180029d71`: `RepairAppRegistration %ws 0x%0x`

## pseudocode

```c
void __fastcall Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        const wchar_t *operation,
        HRESULT inputHr,
        Windows::System::IUser *userParam)
{
  HRESULT v6; // eax
  HRESULT v7; // [rsp+30h] [rbp-18h]
  void *retaddr; // [rsp+48h] [rbp+0h]

  if ( inputHr < 0 )
  {
    if ( inputHr != -2147024894 && inputHr != -2147024893 )
    {
      if ( inputHr == -2147024891 )
      {
        if ( IsTokenRestricted((HANDLE)0xFFFFFFFFFFFFFFFALL) )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            0x1D1u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
            -2147024891,
            "The calling thread/process token is restricted. Skip auto repair as it may not fix the issue. Failed operation: %ws",
            operation);
          return;
        }
      }
      else if ( inputHr != -2147009096 )
      {
        return;
      }
    }
    v6 = Windows::Storage::StateABIHelpers::RepairAppRegistration(operation, inputHr, userParam);
    v7 = inputHr;
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      0x1DAu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
      v6,
      "RepairAppRegistration %ws 0x%0x",
      operation,
      v7);
  }
}

```

## disassembly

```asm
0x180029d20  test    inputHr, inputHr
0x180029d22  jns     locret_180029DA9
0x180029d28  mov     [rsp+arg_0], rbx
0x180029d2d  mov     [rsp+arg_8], rsi
0x180029d32  push    rdi
0x180029d33  sub     rsp, 40h
0x180029d37  mov     rsi, userParam
0x180029d3a  mov     ebx, inputHr
0x180029d3c  mov     rdi, operation
0x180029d3f  cmp     inputHr, 80070002h
0x180029d45  jz      short loc_180029D5F
0x180029d47  cmp     inputHr, 80070003h
0x180029d4d  jz      short loc_180029D5F
0x180029d4f  cmp     inputHr, 80070005h
0x180029d55  jz      short loc_180029DAA
0x180029d57  cmp     inputHr, 80073DB8h
0x180029d5d  jnz     short loc_180029D9A
0x180029d5f  mov     userParam, rsi; userParam
0x180029d62  mov     inputHr, ebx; inputHr
0x180029d64  mov     operation, rdi; operation
0x180029d67  call    ?RepairAppRegistration@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::RepairAppRegistration(ushort const *,long,Windows::System::IUser *)
0x180029d6c  mov     operation, [rsp+48h]; callerReturnAddress
0x180029d71  lea     rdx, aRepairappregis; "RepairAppRegistration %ws 0x%0x"
0x180029d78  mov     [rsp+48h+var_18], ebx
0x180029d7c  lea     userParam, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180029d83  mov     [rsp+48h+var_20], rdi
0x180029d88  mov     r9d, eax; hr
0x180029d8b  mov     [rsp+48h+formatString], rdx; formatString
0x180029d90  mov     inputHr, 1DAh; lineNumber
0x180029d95  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180029d9a  mov     rbx, [rsp+48h+arg_0]
0x180029d9f  mov     rsi, [rsp+48h+arg_8]
0x180029da4  add     rsp, 40h
0x180029da8  pop     rdi
0x180029da9  retn
0x180029daa  mov     operation, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180029db1  call    cs:__imp_IsTokenRestricted
0x180029db7  test    eax, eax
0x180029db9  jz      short loc_180029D5F
0x180029dbb  mov     operation, [rsp+48h]; callerReturnAddress
0x180029dc0  lea     rax, aTheCallingThre; "The calling thread/process token is res"...
0x180029dc7  mov     [rsp+48h+var_20], rdi
0x180029dcc  lea     userParam, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180029dd3  mov     r9d, 80070005h; hr
0x180029dd9  mov     [rsp+48h+formatString], rax; formatString
0x180029dde  mov     inputHr, 1D1h; lineNumber
0x180029de3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180029de8  jmp     short loc_180029D9A
```
