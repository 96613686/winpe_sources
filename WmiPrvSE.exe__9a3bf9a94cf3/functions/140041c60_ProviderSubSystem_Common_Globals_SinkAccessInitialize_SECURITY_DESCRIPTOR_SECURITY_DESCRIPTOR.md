# ProviderSubSystem_Common_Globals::SinkAccessInitialize(_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR * &)

- ea: `0x140041c60`
- end: `0x140041d6e`
- name: `?SinkAccessInitialize@ProviderSubSystem_Common_Globals@@SAJPEAU_SECURITY_DESCRIPTOR@@AEAPEAU2@@Z`
- size: `270`
- prototype: `static int(struct _SECURITY_DESCRIPTOR *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140006d5c`

## callees

- `0x14000a0f0`
- `0x140040e78`
- `0x1400417cc`
- `0x1400418dc`
- `0x140041c60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140041cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140041cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041c86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041c86`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041c9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041c9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140041ccb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140041ccb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140041c72`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140041c72`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140041ca4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140041ca4`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Common_Globals::SinkAccessInitialize(
        struct _SECURITY_DESCRIPTOR *a1,
        struct _SECURITY_DESCRIPTOR **a2)
{
  HRESULT v3; // eax
  int GroupSid; // ebx
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  bool v7; // zf
  HANDLE CurrentProcess; // rax
  __int64 v9; // r8
  void *lpMem; // [rsp+30h] [rbp-10h] BYREF
  PSID pSid; // [rsp+38h] [rbp-8h] BYREF
  struct _SECURITY_DESCRIPTOR *v13; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  v13 = a1;
  v3 = CoImpersonateClient();
  TokenHandle = 0;
  GroupSid = v3;
  if ( v3 < 0 )
  {
    if ( v3 != -2147417833 )
      return (unsigned int)GroupSid;
    CurrentProcess = GetCurrentProcess();
    v7 = !OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    CoRevertToSelf();
    v7 = !v6;
  }
  if ( v7 )
  {
    return (unsigned int)-2147217405;
  }
  else
  {
    v14 = 0;
    pSid = 0;
    if ( (int)ProviderSubSystem_Common_Globals::GetUserSid(TokenHandle, &v14, &pSid) < 0 )
    {
      GroupSid = -2147217398;
    }
    else
    {
      v14 = 0;
      lpMem = 0;
      GroupSid = ProviderSubSystem_Common_Globals::GetGroupSid(TokenHandle, &v14, &lpMem);
      if ( GroupSid >= 0 )
      {
        GroupSid = ProviderSubSystem_Common_Globals::AdjustSecurityDescriptorWithSid(
                     pSid,
                     lpMem,
                     v9,
                     (PSECURITY_DESCRIPTOR *)&v13,
                     a2);
        operator delete(lpMem);
      }
      operator delete(pSid);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)GroupSid;
}

```

## disassembly

```asm
0x140041c60  mov     [rsp-18h+arg_0], rcx
0x140041c65  push    rbp
0x140041c66  push    rbx
0x140041c67  push    rdi
0x140041c68  mov     rbp, rsp
0x140041c6b  sub     rsp, 40h
0x140041c6f  mov     rdi, rdx
0x140041c72  call    cs:__imp_CoImpersonateClient
0x140041c78  mov     [rbp+TokenHandle], 0
0x140041c80  mov     ebx, eax
0x140041c82  test    eax, eax
0x140041c84  js      short loc_140041CAE
0x140041c86  call    cs:__imp_GetCurrentThread
0x140041c8c  mov     edx, 8; DesiredAccess
0x140041c91  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140041c95  mov     rcx, rax; ThreadHandle
0x140041c98  lea     r8d, [rdx-7]; OpenAsSelf
0x140041c9c  call    cs:__imp_OpenThreadToken
0x140041ca2  mov     ebx, eax
0x140041ca4  call    cs:__imp_CoRevertToSelf
0x140041caa  test    ebx, ebx
0x140041cac  jmp     short loc_140041CD3
0x140041cae  cmp     eax, 80010117h
0x140041cb3  jnz     loc_140041D64
0x140041cb9  call    cs:__imp_GetCurrentProcess
0x140041cbf  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140041cc3  mov     edx, 8; DesiredAccess
0x140041cc8  mov     rcx, rax; ProcessHandle
0x140041ccb  call    cs:__imp_OpenProcessToken
0x140041cd1  test    eax, eax
0x140041cd3  jnz     short loc_140041CDF
0x140041cd5  mov     ebx, 80041003h
0x140041cda  jmp     loc_140041D64
0x140041cdf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140041ce3  lea     r8, [rbp+pSid]; void **
0x140041ce7  lea     rdx, [rbp+arg_10]; unsigned int *
0x140041ceb  mov     [rbp+arg_10], 0
0x140041cf2  mov     [rbp+pSid], 0
0x140041cfa  call    ?GetUserSid@ProviderSubSystem_Common_Globals@@SAJPEAXPEAKAEAPEAX@Z; ProviderSubSystem_Common_Globals::GetUserSid(void *,ulong *,void * &)
0x140041cff  test    eax, eax
0x140041d01  js      short loc_140041D55
0x140041d03  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140041d07  lea     r8, [rbp+lpMem]; void **
0x140041d0b  lea     rdx, [rbp+arg_10]; unsigned int *
0x140041d0f  mov     [rbp+arg_10], 0
0x140041d16  mov     [rbp+lpMem], 0
0x140041d1e  call    ?GetGroupSid@ProviderSubSystem_Common_Globals@@SAJPEAXPEAKAEAPEAX@Z; ProviderSubSystem_Common_Globals::GetGroupSid(void *,ulong *,void * &)
0x140041d23  mov     ebx, eax
0x140041d25  test    eax, eax
0x140041d27  js      short loc_140041D4A
0x140041d29  mov     rdx, [rbp+lpMem]; pGroup
0x140041d2d  lea     r9, [rbp+arg_0]; struct _SECURITY_DESCRIPTOR **
0x140041d31  mov     rcx, [rbp+pSid]; pSid
0x140041d35  mov     [rsp+40h+var_20], rdi; struct _SECURITY_DESCRIPTOR **
0x140041d3a  call    ?AdjustSecurityDescriptorWithSid@ProviderSubSystem_Common_Globals@@SAJPEAU_SID@@0KAEAPEAU_SECURITY_DESCRIPTOR@@1@Z; ProviderSubSystem_Common_Globals::AdjustSecurityDescriptorWithSid(_SID *,_SID *,ulong,_SECURITY_DESCRIPTOR * &,_SECURITY_DESCRIPTOR * &)
0x140041d3f  mov     rcx, [rbp+lpMem]; lpMem
0x140041d43  mov     ebx, eax
0x140041d45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140041d4a  mov     rcx, [rbp+pSid]; lpMem
0x140041d4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140041d53  jmp     short loc_140041D5A
0x140041d55  mov     ebx, 8004100Ah
0x140041d5a  mov     rcx, [rbp+TokenHandle]; hObject
0x140041d5e  call    cs:__imp_CloseHandle
0x140041d64  mov     eax, ebx
0x140041d66  add     rsp, 40h
0x140041d6a  pop     rdi
0x140041d6b  pop     rbx
0x140041d6c  pop     rbp
0x140041d6d  retn
```
