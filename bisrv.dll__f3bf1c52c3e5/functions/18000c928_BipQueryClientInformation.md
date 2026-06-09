# BipQueryClientInformation

- ea: `0x18000c928`
- end: `0x18000cbef`
- name: `BipQueryClientInformation`
- size: `711`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, void *@<rdx>, void *@<r8>, int, PVOID, __int64, char)`
- caller_count: `20`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008f40`
- `0x180009ba0`
- `0x18000a1c0`
- `0x18000aa10`
- `0x18000ab10`
- `0x18000af90`
- `0x18000b510`
- `0x18000c730`
- `0x18000c7c0`
- `0x180030c60`
- `0x180031150`
- `0x180031300`
- `0x1800315b0`
- `0x18003a2b0`
- `0x180043740`
- `0x1800480b0`
- `0x18004a960`
- `0x18004da00`
- `0x18004ef80`
- `0x18007a320`

## callees

- `0x18000c928`
- `0x180044260`
- `0x18004de88`
- `0x180053100`
- `0x18006d364`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlQueryPackageIdentityEx` at `0x18000cad9`
- `ntdll!RtlQueryPackageIdentityEx` at `0x18000cad9`
- `ntdll!NtOpenThreadToken` at `0x18000c9be`
- `ntdll!NtOpenThreadToken` at `0x18000c9be`
- `ntdll!NtOpenProcessToken` at `0x18000c9d9`
- `ntdll!NtOpenProcessToken` at `0x18000c9d9`
- `ntdll!RtlValidSid` at `0x18000ca4b`
- `ntdll!RtlValidSid` at `0x18000ca4b`
- `ntdll!RtlCopySid` at `0x18000ca32`
- `ntdll!RtlCopySid` at `0x18000ca32`
- `ntdll!NtClose` at `0x18000cb6f`
- `ntdll!NtClose` at `0x18000cb6f`
- `ntdll!NtQueryInformationToken` at `0x18000ca0d`
- `ntdll!NtQueryInformationToken` at `0x18000cb0d`
- `ntdll!NtQueryInformationToken` at `0x18000ca0d`
- `ntdll!NtQueryInformationToken` at `0x18000cb0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c9c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c9c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c9aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c9aa`

## pseudocode

```c
__int64 __fastcall BipQueryClientInformation(
        PSID Sid,
        void *a2,
        void *a3,
        _OWORD *a4,
        int a5,
        PVOID a6,
        int *a7,
        char a8)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  HANDLE CurrentProcess; // rax
  NTSTATUS v17; // ebx
  int v18; // edi
  int Policy; // eax
  unsigned int v20; // eax
  int v21; // ebx
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // [rsp+40h] [rbp-A1h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-99h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-91h] BYREF
  NTSTATUS v28; // [rsp+54h] [rbp-8Dh] BYREF
  __int64 v29; // [rsp+58h] [rbp-89h] BYREF
  __int64 v30; // [rsp+60h] [rbp-81h] BYREF
  PSID TokenInformation[12]; // [rsp+70h] [rbp-71h] BYREF

  ReturnLength = 0;
  v30 = 0;
  v29 = 0;
  TokenHandle = 0;
  v25 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  if ( a8 )
  {
    CurrentThread = GetCurrentThread();
    v13 = NtOpenThreadToken(CurrentThread, 8u, 1u, &TokenHandle);
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v13 = NtOpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v13 < 0 )
    return 3221225473LL;
  if ( Sid )
  {
    if ( NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) < 0 )
    {
      v17 = -1073741823;
      v18 = 10;
      goto LABEL_35;
    }
    v17 = RtlCopySid(0x44u, Sid, TokenInformation[0]);
    if ( v17 < 0 )
    {
      v18 = 20;
      goto LABEL_35;
    }
    RtlValidSid(Sid);
  }
  v29 = 0;
  v30 = 0;
  if ( a2 )
  {
    v30 = 256;
    memset_0(a2, 0, 0x100u);
  }
  if ( a3 )
  {
    v29 = 130;
    memset_0(a3, 0, 0x82u);
  }
  if ( a4 )
    *a4 = 0;
  if ( (a2 || a3 || a4) && (v17 = RtlQueryPackageIdentityEx(TokenHandle, a2, &v30, a3, &v29, a4, 0), v17 < 0) )
  {
    v18 = 30;
  }
  else if ( a6 && (v17 = NtQueryInformationToken(TokenHandle, TokenSessionId, a6, 4u, &ReturnLength), v17 < 0) )
  {
    v18 = 40;
  }
  else
  {
    if ( a7 )
    {
      Policy = AppModelPolicy_GetPolicy(TokenHandle, v14, &v25);
      if ( Policy < 0 )
      {
        v17 = (unsigned __int16)Policy;
        v18 = 50;
        v20 = (unsigned __int16)Policy | 0xC0070000;
        if ( v17 )
          v17 = v20;
        goto LABEL_35;
      }
      v21 = v25;
      if ( (unsigned int)(v25 - 0x10000) > 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *a7 = v21;
    }
    v17 = 0;
    v18 = 0;
  }
LABEL_35:
  NtClose(TokenHandle);
  if ( v17 < 0 && (unsigned int)dword_1800C3098 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x200000000000LL, v22) )
    {
      v25 = v18;
      v28 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800C3098,
        (unsigned __int8 *)byte_1800B3C5D,
        v23,
        v24,
        (__int64)&v28,
        (__int64)&v25);
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000c928  push    rbp
0x18000c92a  push    rbx
0x18000c92b  push    rsi
0x18000c92c  push    rdi
0x18000c92d  push    r12
0x18000c92f  push    r13
0x18000c931  push    r14
0x18000c933  push    r15
0x18000c935  lea     rbp, [rsp-7]
0x18000c93a  sub     rsp, 0E8h
0x18000c941  mov     rax, cs:__security_cookie
0x18000c948  xor     rax, rsp
0x18000c94b  mov     [rbp+3Fh+var_50], rax
0x18000c94f  mov     r13, [rbp+3Fh+arg_28]
0x18000c953  mov     r14, r8
0x18000c956  mov     r12, [rbp+3Fh+arg_30]
0x18000c95a  mov     rsi, rdx
0x18000c95d  mov     r15, rcx
0x18000c960  mov     [rsp+120h+var_D0], 0
0x18000c968  mov     ebx, 58h ; 'X'
0x18000c96d  mov     [rsp+120h+var_C0], 0
0x18000c976  mov     r8d, ebx; Size
0x18000c979  mov     [rsp+120h+var_C8], 0
0x18000c982  xor     edx, edx; Val
0x18000c984  mov     [rsp+120h+TokenHandle], 0
0x18000c98d  lea     rcx, [rbp+3Fh+TokenInformation]; void *
0x18000c991  mov     [rsp+120h+var_E0], 0
0x18000c999  mov     rdi, r9
0x18000c99c  call    memset_0
0x18000c9a1  cmp     [rbp+3Fh+arg_38], 0
0x18000c9a8  jz      short loc_18000C9C6
0x18000c9aa  call    cs:__imp_GetCurrentThread
0x18000c9b0  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x18000c9b5  mov     r8b, 1; OpenAsSelf
0x18000c9b8  mov     rcx, rax; ThreadHandle
0x18000c9bb  lea     edx, [rbx-50h]; DesiredAccess
0x18000c9be  call    cs:__imp_NtOpenThreadToken
0x18000c9c4  jmp     short loc_18000C9DF
0x18000c9c6  call    cs:__imp_GetCurrentProcess
0x18000c9cc  lea     r8, [rsp+120h+TokenHandle]; TokenHandle
0x18000c9d1  mov     edx, 8; DesiredAccess
0x18000c9d6  mov     rcx, rax; ProcessHandle
0x18000c9d9  call    cs:__imp_NtOpenProcessToken
0x18000c9df  test    eax, eax
0x18000c9e1  jns     short loc_18000C9ED
0x18000c9e3  mov     eax, 0C0000001h
0x18000c9e8  jmp     loc_18000CBCF
0x18000c9ed  test    r15, r15
0x18000c9f0  jz      short loc_18000CA51
0x18000c9f2  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000c9f7  lea     rax, [rsp+120h+var_D0]
0x18000c9fc  mov     r9d, ebx; TokenInformationLength
0x18000c9ff  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000ca04  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x18000ca08  mov     edx, 1; TokenInformationClass
0x18000ca0d  call    cs:__imp_NtQueryInformationToken
0x18000ca13  test    eax, eax
0x18000ca15  jns     short loc_18000CA26
0x18000ca17  mov     ebx, 0C0000001h
0x18000ca1c  mov     edi, 0Ah
0x18000ca21  jmp     loc_18000CB6A
0x18000ca26  mov     r8, [rbp+3Fh+TokenInformation]; SourceSid
0x18000ca2a  mov     rdx, r15; DestinationSid
0x18000ca2d  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000ca32  call    cs:__imp_RtlCopySid
0x18000ca38  mov     ebx, eax
0x18000ca3a  test    eax, eax
0x18000ca3c  jns     short loc_18000CA48
0x18000ca3e  mov     edi, 14h
0x18000ca43  jmp     loc_18000CB6A
0x18000ca48  mov     rcx, r15; Sid
0x18000ca4b  call    cs:__imp_RtlValidSid
0x18000ca51  mov     [rsp+120h+var_C8], 0
0x18000ca5a  mov     [rsp+120h+var_C0], 0
0x18000ca63  test    rsi, rsi
0x18000ca66  jz      short loc_18000CA7D
0x18000ca68  mov     r8d, 100h; Size
0x18000ca6e  xor     edx, edx; Val
0x18000ca70  mov     rcx, rsi; void *
0x18000ca73  mov     [rsp+120h+var_C0], r8
0x18000ca78  call    memset_0
0x18000ca7d  test    r14, r14
0x18000ca80  jz      short loc_18000CA97
0x18000ca82  mov     r8d, 82h; Size
0x18000ca88  xor     edx, edx; Val
0x18000ca8a  mov     rcx, r14; void *
0x18000ca8d  mov     [rsp+120h+var_C8], r8
0x18000ca92  call    memset_0
0x18000ca97  test    rdi, rdi
0x18000ca9a  jz      short loc_18000CAA2
0x18000ca9c  xorps   xmm0, xmm0
0x18000ca9f  movups  xmmword ptr [rdi], xmm0
0x18000caa2  test    rsi, rsi
0x18000caa5  jnz     short loc_18000CAB1
0x18000caa7  test    r14, r14
0x18000caaa  jnz     short loc_18000CAB1
0x18000caac  test    rdi, rdi
0x18000caaf  jz      short loc_18000CAEC
0x18000cab1  mov     rcx, [rsp+120h+TokenHandle]
0x18000cab6  lea     rax, [rsp+120h+var_C8]
0x18000cabb  mov     [rsp+120h+var_F0], 0
0x18000cac4  lea     r8, [rsp+120h+var_C0]
0x18000cac9  mov     [rsp+120h+var_F8], rdi
0x18000cace  mov     r9, r14
0x18000cad1  mov     rdx, rsi
0x18000cad4  mov     [rsp+120h+ReturnLength], rax
0x18000cad9  call    cs:__imp_RtlQueryPackageIdentityEx
0x18000cadf  mov     ebx, eax
0x18000cae1  test    eax, eax
0x18000cae3  jns     short loc_18000CAEC
0x18000cae5  mov     edi, 1Eh
0x18000caea  jmp     short loc_18000CB6A
0x18000caec  test    r13, r13
0x18000caef  jz      short loc_18000CB20
0x18000caf1  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000caf6  lea     rax, [rsp+120h+var_D0]
0x18000cafb  mov     r9d, 4; TokenInformationLength
0x18000cb01  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000cb06  mov     r8, r13; TokenInformation
0x18000cb09  lea     edx, [r9+8]; TokenInformationClass
0x18000cb0d  call    cs:__imp_NtQueryInformationToken
0x18000cb13  mov     ebx, eax
0x18000cb15  test    eax, eax
0x18000cb17  jns     short loc_18000CB20
0x18000cb19  mov     edi, 28h ; '('
0x18000cb1e  jmp     short loc_18000CB6A
0x18000cb20  test    r12, r12
0x18000cb23  jz      short loc_18000CB66
0x18000cb25  mov     rcx, [rsp+120h+TokenHandle]
0x18000cb2a  lea     r8, [rsp+120h+var_E0]
0x18000cb2f  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18000cb34  test    eax, eax
0x18000cb36  jns     short loc_18000CB4E
0x18000cb38  movzx   ebx, ax
0x18000cb3b  mov     edi, 32h ; '2'
0x18000cb40  mov     eax, ebx
0x18000cb42  or      eax, 0C0070000h
0x18000cb47  test    ebx, ebx
0x18000cb49  cmovnz  ebx, eax
0x18000cb4c  jmp     short loc_18000CB6A
0x18000cb4e  mov     ebx, [rsp+120h+var_E0]
0x18000cb52  lea     eax, [rbx-10000h]
0x18000cb58  cmp     eax, 1
0x18000cb5b  jbe     short loc_18000CB62
0x18000cb5d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cb62  mov     [r12], ebx
0x18000cb66  xor     ebx, ebx
0x18000cb68  xor     edi, edi
0x18000cb6a  mov     rcx, [rsp+120h+TokenHandle]; Handle
0x18000cb6f  call    cs:__imp_NtClose
0x18000cb75  test    ebx, ebx
0x18000cb77  jns     short loc_18000CBCD
0x18000cb79  mov     eax, cs:dword_1800C3098
0x18000cb7f  cmp     eax, 2
0x18000cb82  jbe     short loc_18000CBCD
0x18000cb84  mov     rdx, 200000000000h
0x18000cb8e  lea     rcx, dword_1800C3098
0x18000cb95  call    _tlgKeywordOn
0x18000cb9a  test    al, al
0x18000cb9c  jz      short loc_18000CBCD
0x18000cb9e  lea     rax, [rsp+120h+var_E0]
0x18000cba3  mov     [rsp+120h+var_E0], edi
0x18000cba7  mov     [rsp+120h+var_F8], rax
0x18000cbac  lea     rdx, byte_1800B3C5D
0x18000cbb3  lea     rax, [rsp+120h+var_CC]
0x18000cbb8  mov     [rsp+120h+var_CC], ebx
0x18000cbbc  lea     rcx, dword_1800C3098
0x18000cbc3  mov     [rsp+120h+ReturnLength], rax
0x18000cbc8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cbcd  mov     eax, ebx
0x18000cbcf  mov     rcx, [rbp+3Fh+var_50]
0x18000cbd3  xor     rcx, rsp; StackCookie
0x18000cbd6  call    __security_check_cookie
0x18000cbdb  add     rsp, 0E8h
0x18000cbe2  pop     r15
0x18000cbe4  pop     r14
0x18000cbe6  pop     r13
0x18000cbe8  pop     r12
0x18000cbea  pop     rdi
0x18000cbeb  pop     rsi
0x18000cbec  pop     rbx
0x18000cbed  pop     rbp
0x18000cbee  retn
```
