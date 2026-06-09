# InitializeAEBSvc(void *)

- ea: `0x18005c44c`
- end: `0x18005c54c`
- name: `?InitializeAEBSvc@@YAJPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003984c`

## callees

- `0x180010da8`
- `0x180033444`
- `0x18005c42c`
- `0x18005c44c`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x18005c51b`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005c51b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005c4af`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005c4af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005c472`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005c472`

## string_xrefs

- `0x18005c481`: `avcore\audiocore\server\audioendpointbuilder\dll\aebsvc.cpp`
- `0x18005c4d2`: `avcore\audiocore\server\audioendpointbuilder\dll\aebsvc.cpp`

## pseudocode

```c
__int64 __fastcall InitializeAEBSvc(void *a1)
{
  const char *v1; // r9
  unsigned int LastError; // ebx
  RPC_STATUS v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;; GRGWGX;;; S-1-5-80-2676549577-1911656217-2625096541-4178041876-1366760775)(A;;GA;;;BA)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v3 = RpcServerUseProtseqEpW(
           (RPC_WSTR)L"ncalrpc",
           0xAu,
           (RPC_WSTR)L"AudioEndpointBuilderClientRpc",
           SecurityDescriptor);
    if ( !v3 || v3 == 1740 )
    {
      v7 = 1234;
      v5 = RpcServerRegisterIf3(qword_18006AF40, 0, 0, 33);
      LastError = v5 != 0 ? v5 | 0x80010000 : 0;
      if ( (LastError & 0x80000000) == 0 )
      {
        LastError = 0;
        goto LABEL_10;
      }
      v4 = 61;
    }
    else
    {
      LastError = v3 | 0x80010000;
      v4 = 51;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\aebsvc.cpp",
      (const char *)LastError,
      v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x28,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\aebsvc.cpp",
                  v1);
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18005c44c  mov     [rsp+SecurityDescriptor], rcx
0x18005c451  push    rbx
0x18005c452  sub     rsp, 40h
0x18005c456  xor     r9d, r9d; SecurityDescriptorSize
0x18005c459  mov     [rsp+48h+SecurityDescriptor], 0
0x18005c462  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18005c467  lea     rcx, StringSecurityDescriptor; "D:(A;; GRGWGX;;; S-1-5-80-2676549577-19"...
0x18005c46e  lea     edx, [r9+1]; StringSDRevision
0x18005c472  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005c478  test    eax, eax
0x18005c47a  jnz     short loc_18005C497
0x18005c47c  mov     rcx, [rsp+48h]; this
0x18005c481  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\audioendpoin"...
0x18005c488  lea     edx, [rax+28h]; void *
0x18005c48b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c490  mov     ebx, eax
0x18005c492  jmp     loc_18005C53A
0x18005c497  mov     r9, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18005c49c  lea     r8, Endpoint; "AudioEndpointBuilderClientRpc"
0x18005c4a3  mov     edx, 0Ah; MaxCalls
0x18005c4a8  lea     rcx, Protseq; "ncalrpc"
0x18005c4af  call    cs:__imp_RpcServerUseProtseqEpW
0x18005c4b5  mov     ebx, eax
0x18005c4b7  test    eax, eax
0x18005c4b9  jz      short loc_18005C4E3
0x18005c4bb  cmp     eax, 6CCh
0x18005c4c0  jz      short loc_18005C4E3
0x18005c4c2  or      ebx, 80010000h
0x18005c4c8  mov     edx, 33h ; '3'; void *
0x18005c4cd  mov     rcx, [rsp+48h]; this
0x18005c4d2  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\audioendpoin"...
0x18005c4d9  mov     r9d, ebx; char *
0x18005c4dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c4e1  jmp     short loc_18005C53A
0x18005c4e3  mov     rax, [rsp+48h+SecurityDescriptor]
0x18005c4e8  lea     rcx, qword_18006AF40
0x18005c4ef  mov     [rsp+48h+var_10], rax
0x18005c4f4  mov     r9d, 21h ; '!'
0x18005c4fa  lea     rax, ?LKDIfCallback@@YAJPEAX0@Z; LKDIfCallback(void *,void *)
0x18005c501  xor     r8d, r8d
0x18005c504  mov     [rsp+48h+var_18], rax
0x18005c509  xor     edx, edx
0x18005c50b  mov     [rsp+48h+var_20], 0
0x18005c513  mov     [rsp+48h+var_28], 4D2h
0x18005c51b  call    cs:__imp_RpcServerRegisterIf3
0x18005c521  mov     ecx, eax
0x18005c523  or      ecx, 80010000h
0x18005c529  neg     eax
0x18005c52b  sbb     ebx, ebx
0x18005c52d  and     ebx, ecx
0x18005c52f  jge     short loc_18005C538
0x18005c531  mov     edx, 3Dh ; '='
0x18005c536  jmp     short loc_18005C4CD
0x18005c538  xor     ebx, ebx
0x18005c53a  lea     rcx, [rsp+48h+SecurityDescriptor]
0x18005c53f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005c544  mov     eax, ebx
0x18005c546  add     rsp, 40h
0x18005c54a  pop     rbx
0x18005c54b  retn
```
