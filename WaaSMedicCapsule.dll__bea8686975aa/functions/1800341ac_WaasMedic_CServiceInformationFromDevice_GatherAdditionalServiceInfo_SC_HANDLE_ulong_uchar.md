# WaasMedic::CServiceInformationFromDevice::GatherAdditionalServiceInfo(SC_HANDLE__ * &,ulong,uchar * *)

- ea: `0x1800341ac`
- end: `0x18003428a`
- name: `?GatherAdditionalServiceInfo@CServiceInformationFromDevice@WaasMedic@@AEAAJAEAPEAUSC_HANDLE__@@KPEAPEAE@Z`
- size: `222`
- prototype: `int(WaasMedic::CServiceInformationFromDevice *__hidden this, struct SC_HANDLE__ **, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18003460c`

## callees

- `0x180009a54`
- `0x180024fc4`
- `0x1800341ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003426a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003426a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180034218`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180034260`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180034218`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180034260`

## pseudocode

```c
__int64 __fastcall WaasMedic::CServiceInformationFromDevice::GatherAdditionalServiceInfo(
        WaasMedic::CServiceInformationFromDevice *this,
        struct SC_HANDLE__ **a2,
        DWORD a3,
        unsigned __int8 **a4)
{
  SC_HANDLE v4; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  signed int LastError; // eax
  unsigned __int64 v11; // rdx
  bool v12; // r8
  unsigned __int8 *v13; // rax
  int pcbBytesNeeded; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  WaasMedic::CServiceInformationFromDevice *cbBufSize; // [rsp+60h] [rbp+8h] BYREF

  cbBufSize = this;
  v4 = *a2;
  LODWORD(cbBufSize) = 0;
  if ( !v4 )
  {
    v8 = -2147024890;
    v9 = 745;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)v8,
      pcbBytesNeeded);
    return v8;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v9 = 746;
    goto LABEL_3;
  }
  if ( QueryServiceConfig2W(v4, a3, 0, 0, (LPDWORD)&cbBufSize) )
    goto LABEL_10;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError == 122 )
  {
    v13 = (unsigned __int8 *)WaasMedic::SafeAlloc((WaasMedic *)(unsigned int)cbBufSize, v11, v12);
    *a4 = v13;
    if ( !v13 )
      return (unsigned int)-2147024882;
LABEL_10:
    v8 = 0;
    if ( QueryServiceConfig2W(*a2, a3, *a4, (DWORD)cbBufSize, (LPDWORD)&cbBufSize) )
      return v8;
    LastError = GetLastError();
    v8 = LastError;
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v8;
}

```

## disassembly

```asm
0x1800341ac  mov     [rsp+cbBufSize], rcx
0x1800341b1  push    rbx
0x1800341b2  push    rbp
0x1800341b3  push    rsi
0x1800341b4  push    rdi
0x1800341b5  sub     rsp, 38h
0x1800341b9  mov     rcx, [rdx]; hService
0x1800341bc  mov     rdi, r9
0x1800341bf  mov     dword ptr [rsp+58h+cbBufSize], 0
0x1800341c7  mov     ebp, r8d
0x1800341ca  mov     rsi, rdx
0x1800341cd  test    rcx, rcx
0x1800341d0  jnz     short loc_1800341F5
0x1800341d2  mov     ebx, 80070006h
0x1800341d7  mov     edx, 2E9h; void *
0x1800341dc  mov     rcx, [rsp+58h]; this
0x1800341e1  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800341e8  mov     r9d, ebx; char *
0x1800341eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341f0  jmp     loc_18003427F
0x1800341f5  test    rdi, rdi
0x1800341f8  jnz     short loc_180034206
0x1800341fa  mov     ebx, 80004003h
0x1800341ff  mov     edx, 2EAh
0x180034204  jmp     short loc_1800341DC
0x180034206  lea     rax, [rsp+58h+cbBufSize]
0x18003420b  xor     r9d, r9d; cbBufSize
0x18003420e  xor     r8d, r8d; lpBuffer
0x180034211  mov     qword ptr [rsp+58h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180034216  mov     edx, ebp; dwInfoLevel
0x180034218  call    cs:__imp_QueryServiceConfig2W
0x18003421e  test    eax, eax
0x180034220  jnz     short loc_180034247
0x180034222  call    cs:__imp_GetLastError
0x180034228  mov     ebx, eax
0x18003422a  cmp     eax, 7Ah ; 'z'
0x18003422d  jnz     short loc_180034272
0x18003422f  mov     ecx, dword ptr [rsp+58h+cbBufSize]; this
0x180034233  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180034238  mov     [rdi], rax
0x18003423b  test    rax, rax
0x18003423e  jnz     short loc_180034247
0x180034240  mov     ebx, 8007000Eh
0x180034245  jmp     short loc_18003427F
0x180034247  mov     r9d, dword ptr [rsp+58h+cbBufSize]; cbBufSize
0x18003424c  lea     rax, [rsp+58h+cbBufSize]
0x180034251  mov     r8, [rdi]; lpBuffer
0x180034254  mov     edx, ebp; dwInfoLevel
0x180034256  mov     rcx, [rsi]; hService
0x180034259  xor     ebx, ebx
0x18003425b  mov     qword ptr [rsp+58h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180034260  call    cs:__imp_QueryServiceConfig2W
0x180034266  test    eax, eax
0x180034268  jnz     short loc_18003427F
0x18003426a  call    cs:__imp_GetLastError
0x180034270  mov     ebx, eax
0x180034272  test    eax, eax
0x180034274  jle     short loc_18003427F
0x180034276  movzx   ebx, ax
0x180034279  or      ebx, 80070000h
0x18003427f  mov     eax, ebx
0x180034281  add     rsp, 38h
0x180034285  pop     rdi
0x180034286  pop     rsi
0x180034287  pop     rbp
0x180034288  pop     rbx
0x180034289  retn
```
