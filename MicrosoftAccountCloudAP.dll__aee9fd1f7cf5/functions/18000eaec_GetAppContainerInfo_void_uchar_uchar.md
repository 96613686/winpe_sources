# GetAppContainerInfo(void *,uchar *,uchar *)

- ea: `0x18000eaec`
- end: `0x18000ebfe`
- name: `?GetAppContainerInfo@@YAJPEAXPEAE1@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, bool *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013478`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000eaec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000eba6`
- `ntdll!RtlInitUnicodeString` at `0x18000eba6`
- `ntdll!NtQueryInformationToken` at `0x18000eb8c`
- `ntdll!NtQueryInformationToken` at `0x18000eb8c`
- `ntdll!RtlCapabilityCheck` at `0x18000ebb7`
- `ntdll!RtlCapabilityCheck` at `0x18000ebb7`

## string_xrefs

- `0x18000eb52`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000eb9b`: `liveIdService`

## pseudocode

```c
__int64 __fastcall GetAppContainerInfo(HANDLE TokenHandle, bool *a2, unsigned __int8 *a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-50h]
  int TokenInformation; // [rsp+30h] [rbp-40h] BYREF
  ULONG v10; // [rsp+34h] [rbp-3Ch] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v12[5]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int8 v13; // [rsp+98h] [rbp+28h] BYREF
  NTSTATUS v14; // [rsp+A8h] [rbp+38h] BYREF

  v14 = 0;
  TokenInformation = 0;
  v12[0] = "GetAppContainerInfo";
  v10 = 0;
  v13 = 0;
  v12[2] = 0;
  v12[1] = &v14;
  v12[3] = 0;
  DestinationString = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "GetAppContainerInfo",
    (const char *)0x73F,
    0,
    ReturnLength);
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v14 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v10);
    v6 = v14;
    if ( v14 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"liveIdService");
      v14 = RtlCapabilityCheck(TokenHandle, &DestinationString, &v13);
      v6 = v14;
      if ( v14 >= 0 )
      {
        *a2 = TokenInformation != 0;
        *a3 = v13;
      }
    }
  }
  else
  {
    v6 = -1073741811;
    v14 = -1073741811;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v12);
  return v6;
}

```

## disassembly

```asm
0x18000eaec  mov     [rsp-18h+arg_0], rbx
0x18000eaf1  mov     [rsp-18h+arg_10], rsi
0x18000eaf6  push    rbp
0x18000eaf7  push    rdi
0x18000eaf8  push    r14
0x18000eafa  mov     rbp, rsp
0x18000eafd  sub     rsp, 70h
0x18000eb01  mov     rsi, rdx
0x18000eb04  mov     [rbp+arg_18], 0
0x18000eb0b  lea     rdx, aGetappcontaine; "GetAppContainerInfo"
0x18000eb12  mov     [rbp+TokenInformation], 0
0x18000eb19  mov     rdi, r8
0x18000eb1c  mov     [rbp+var_28], rdx
0x18000eb20  mov     r14, rcx
0x18000eb23  mov     [rbp+var_3C], 0
0x18000eb2a  xorps   xmm0, xmm0
0x18000eb2d  mov     [rbp+arg_8], 0
0x18000eb31  lea     rax, [rbp+arg_18]
0x18000eb35  mov     [rbp+var_18], 0
0x18000eb3d  xor     r9d, r9d; unsigned int
0x18000eb40  mov     [rbp+var_20], rax
0x18000eb44  mov     r8d, 73Fh; char *
0x18000eb4a  mov     [rbp+var_10], 0
0x18000eb52  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000eb59  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000eb5d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000eb62  test    rsi, rsi
0x18000eb65  jz      short loc_18000EBD6
0x18000eb67  test    rdi, rdi
0x18000eb6a  jz      short loc_18000EBD6
0x18000eb6c  mov     r9d, 4; TokenInformationLength
0x18000eb72  mov     byte ptr [rsi], 0
0x18000eb75  lea     rax, [rbp+var_3C]
0x18000eb79  mov     byte ptr [rdi], 0
0x18000eb7c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000eb80  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000eb85  mov     rcx, r14; TokenHandle
0x18000eb88  lea     edx, [r9+19h]; TokenInformationClass
0x18000eb8c  call    cs:__imp_NtQueryInformationToken
0x18000eb92  mov     [rbp+arg_18], eax
0x18000eb95  mov     ebx, eax
0x18000eb97  test    eax, eax
0x18000eb99  js      short loc_18000EBDE
0x18000eb9b  lea     rdx, SourceString; "liveIdService"
0x18000eba2  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000eba6  call    cs:__imp_RtlInitUnicodeString
0x18000ebac  lea     r8, [rbp+arg_8]
0x18000ebb0  mov     rcx, r14
0x18000ebb3  lea     rdx, [rbp+DestinationString]
0x18000ebb7  call    cs:__imp_RtlCapabilityCheck
0x18000ebbd  mov     [rbp+arg_18], eax
0x18000ebc0  mov     ebx, eax
0x18000ebc2  test    eax, eax
0x18000ebc4  js      short loc_18000EBDE
0x18000ebc6  cmp     [rbp+TokenInformation], 0
0x18000ebca  setnz   al
0x18000ebcd  mov     [rsi], al
0x18000ebcf  mov     al, [rbp+arg_8]
0x18000ebd2  mov     [rdi], al
0x18000ebd4  jmp     short loc_18000EBDE
0x18000ebd6  mov     ebx, 0C000000Dh
0x18000ebdb  mov     [rbp+arg_18], ebx
0x18000ebde  lea     rcx, [rbp+var_28]
0x18000ebe2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000ebe7  lea     r11, [rsp+70h+var_s0]
0x18000ebec  mov     eax, ebx
0x18000ebee  mov     rbx, [r11+20h]
0x18000ebf2  mov     rsi, [r11+30h]
0x18000ebf6  mov     rsp, r11
0x18000ebf9  pop     r14
0x18000ebfb  pop     rdi
0x18000ebfc  pop     rbp
0x18000ebfd  retn
```
