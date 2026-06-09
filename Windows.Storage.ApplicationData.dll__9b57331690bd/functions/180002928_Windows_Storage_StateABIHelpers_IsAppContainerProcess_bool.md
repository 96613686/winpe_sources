# Windows::Storage::StateABIHelpers::IsAppContainerProcess(bool *)

- ea: `0x180002928`
- end: `0x1800029aa`
- name: `?IsAppContainerProcess@StateABIHelpers@Storage@Windows@@YAJPEA_N@Z`
- size: `130`
- prototype: `HRESULT __fastcall(bool *isAppContainerProcess)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000275c`
- `0x18001f238`
- `0x180035f5c`
- `0x180036558`
- `0x180037074`

## callees

- `0x1800022b0`
- `0x180002928`
- `0x180021fc4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002961`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002961`

## string_xrefs

- `0x180002990`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x180002989`: `GetTokenInformation`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::StateABIHelpers::IsAppContainerProcess(bool *isAppContainerProcess)
{
  void *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int dataSize; // [rsp+48h] [rbp+10h] BYREF
  unsigned int data; // [rsp+50h] [rbp+18h] BYREF

  data = 0;
  dataSize = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppContainer, &data, 4u, &dataSize) )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             0x72u,
             "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
             "GetTokenInformation");
  if ( dataSize != 4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *isAppContainerProcess = data != 0;
  return 0;
}

```

## disassembly

```asm
0x180002928  push    rbx
0x18000292a  sub     rsp, 30h
0x18000292e  mov     r9d, 4; TokenInformationLength
0x180002934  mov     [rsp+38h+data], 0
0x18000293c  mov     rbx, isAppContainerProcess
0x18000293f  mov     [rsp+38h+dataSize], 0
0x180002947  lea     rax, [rsp+38h+dataSize]
0x18000294c  mov     isAppContainerProcess, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180002953  lea     r8, [rsp+38h+data]; TokenInformation
0x180002958  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000295d  lea     edx, [r9+19h]; TokenInformationClass
0x180002961  call    cs:__imp_GetTokenInformation
0x180002967  test    eax, eax
0x180002969  jz      short loc_180002984
0x18000296b  cmp     [rsp+38h+dataSize], 4
0x180002970  jnz     short loc_1800029A3
0x180002972  cmp     [rsp+38h+data], 0
0x180002977  setnz   al
0x18000297a  mov     [rbx], al
0x18000297c  xor     eax, eax
0x18000297e  add     rsp, 30h
0x180002982  pop     rbx
0x180002983  retn
0x180002984  mov     isAppContainerProcess, [rsp+38h]; callerReturnAddress
0x180002989  lea     r9, aGettokeninform; "GetTokenInformation"
0x180002990  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180002997  mov     edx, 72h ; 'r'; lineNumber
0x18000299c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800029a1  jmp     short loc_18000297E
0x1800029a3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "sizeof(data) == dataSize")
0x1800029a8  jmp     short loc_180002972
```
