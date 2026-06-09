# AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)

- ea: `0x18003c4c4`
- end: `0x18003c8c5`
- name: `?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z`
- size: `1025`
- prototype: `unsigned int(unsigned int, void *, unsigned __int64, unsigned int, int, const unsigned __int16 *, struct _CONSENTUI_PARAM_HEADER *, unsigned int, const unsigned __int16 *, unsigned __int64 *, unsigned int, const char *, enum UACPROMPT_POLICY *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ced0`
- `0x18003d3d0`
- `0x18003d590`
- `0x18003da80`

## callees

- `0x18000a230`
- `0x18000f11c`
- `0x180011eb8`
- `0x180012584`
- `0x1800168f0`
- `0x180016c54`
- `0x180019748`
- `0x180019dfc`
- `0x18001a17c`
- `0x18003c4c4`
- `0x180041c24`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003c616`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003c616`
- `ntdll!NtClose` at `0x18003c7d7`
- `ntdll!NtClose` at `0x18003c866`
- `ntdll!NtClose` at `0x18003c87a`
- `ntdll!NtClose` at `0x18003c893`
- `ntdll!NtClose` at `0x18003c7d7`
- `ntdll!NtClose` at `0x18003c866`
- `ntdll!NtClose` at `0x18003c87a`
- `ntdll!NtClose` at `0x18003c893`
- `ntdll!NtDuplicateObject` at `0x18003c83a`
- `ntdll!NtDuplicateObject` at `0x18003c83a`
- `ntdll!NtDuplicateToken` at `0x18003c7af`
- `ntdll!NtDuplicateToken` at `0x18003c7af`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c5fe`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c669`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c7c1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c848`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c5fe`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c669`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c7c1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c848`

## pseudocode

```c
__int64 __fastcall AipGetTokenForService(
        unsigned int a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        const unsigned __int16 *a6,
        struct _CONSENTUI_PARAM_HEADER *a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned __int64 *a10,
        unsigned int a11,
        const char *a12,
        enum UACPROMPT_POLICY *a13,
        int *a14)
{
  int *v15; // r12
  enum UACPROMPT_POLICY *v16; // rdx
  unsigned int v17; // ebx
  unsigned int v18; // r13d
  unsigned int v19; // edi
  NTSTATUS v20; // eax
  unsigned int ClientInformation; // eax
  HANDLE v22; // rsi
  NTSTATUS v23; // eax
  unsigned int v24; // r12d
  unsigned int v25; // ebx
  unsigned int v26; // eax
  unsigned __int64 v27; // rdi
  int v28; // eax
  NTSTATUS v29; // eax
  unsigned int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  int v33; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TargetProcessHandle; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v36; // [rsp+7Ch] [rbp-84h]
  unsigned int v37; // [rsp+80h] [rbp-80h]
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-70h] BYREF
  HANDLE SourceHandle; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v41; // [rsp+A0h] [rbp-60h]
  const char *v42; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v44; // [rsp+B8h] [rbp-48h]
  struct _CONSENTUI_PARAM_HEADER *v45; // [rsp+C0h] [rbp-40h]
  PHANDLE TargetHandle; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+100h] [rbp+0h] BYREF
  int v49; // [rsp+108h] [rbp+8h]

  v31 = 0;
  ExistingTokenHandle = 0;
  SourceHandle = 0;
  TargetProcessHandle = 0;
  Handle = 0;
  v32 = 0;
  v15 = a14;
  v37 = a1;
  v43 = a3;
  v45 = a7;
  v41 = a9;
  v42 = a12;
  v16 = a13;
  v36 = a4;
  *a10 = 0;
  v44 = a6;
  TargetHandle = (PHANDLE)a10;
  v33 = 1;
  v48 = 0;
  v49 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a6 || a4 >= 3 )
    return 87;
  if ( !a1 )
  {
    v18 = 4;
    v19 = a11 | 0x4000;
    goto LABEL_10;
  }
  if ( a1 == 1 )
  {
    v18 = 5;
    v19 = a11 | 0x14000;
    goto LABEL_10;
  }
  if ( a1 != 2 )
    return 87;
  v18 = 7;
  v19 = a11 | 0x20000;
LABEL_10:
  a11 = v19;
  if ( v16 )
  {
    v35 = 0;
    v20 = LUAGetUACPromptPolicy(&v35, v16);
    if ( v20 < 0 )
      return RtlNtStatusToDosErrorNoTeb(v20);
  }
  v17 = CheckElevationEnabled(&v33);
  if ( v17 )
    return v17;
  ClientInformation = AiGetClientInformation(a2, &TargetProcessHandle, &Handle, &v31, 0);
  v22 = Handle;
  v17 = ClientInformation;
  if ( ClientInformation )
    goto LABEL_38;
  v23 = AiCheckForElevatedUser(Handle, &v32);
  if ( v23 < 0 || v15 && (v23 = AiCheckForAdminUser(v22, v32, v15), v23 < 0) )
  {
    v17 = RtlNtStatusToDosErrorNoTeb(v23);
  }
  else
  {
    v24 = v31;
    if ( !(unsigned int)AiIsElevationAllowedForSession(v31) )
      goto LABEL_20;
    v25 = v33 != 0 ? v36 : 0;
    if ( v41 )
    {
      v31 = 0;
      if ( !(unsigned int)AiCheckSecureApplicationDirectory(v41, &v31) && (v31 & 0x4000) != 0 )
      {
        v19 |= 0x10000u;
        a11 = v19;
      }
    }
    if ( (v19 & 0x2000000) == 0 || v32 )
    {
      v26 = AiCheckLUA(v25, &a11, v18, v22, v45, v44, v43, v24, a8, v42, &ExistingTokenHandle);
      v27 = (unsigned __int64)ExistingTokenHandle;
      v17 = v26;
      if ( v26 )
      {
LABEL_36:
        if ( v27 )
          NtClose((HANDLE)v27);
        goto LABEL_38;
      }
      if ( ExistingTokenHandle )
      {
        memset(&ObjectAttributes.RootDirectory, 0, 20);
        ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.SecurityQualityOfService = &v48;
        v48 = 0x20000000CLL;
        LOWORD(v49) = 1;
        ObjectAttributes.Length = 48;
        v28 = NtDuplicateToken(ExistingTokenHandle, 0, &ObjectAttributes, 0, TokenImpersonation, &SourceHandle);
        if ( v28 >= 0 )
        {
          NtClose((HANDLE)v27);
          v27 = (unsigned __int64)SourceHandle;
          if ( !a5
            || (v17 = AipAdjustTokenSD(SourceHandle, v37)) == 0 && (v17 = AipAddTokenUserInTokenSD((HANDLE)v27)) == 0 )
          {
            v17 = AiSetMandatoryPolicy((HANDLE)v27);
            if ( !v17 )
            {
              v29 = NtDuplicateObject(
                      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      (HANDLE)v27,
                      TargetProcessHandle,
                      TargetHandle,
                      0,
                      0,
                      3u);
              v17 = RtlNtStatusToDosErrorNoTeb(v29);
              v27 &= -(__int64)(v17 != 0);
            }
          }
        }
        else
        {
          v17 = RtlNtStatusToDosErrorNoTeb(v28);
        }
        goto LABEL_36;
      }
    }
    else
    {
LABEL_20:
      v17 = 50;
    }
  }
LABEL_38:
  if ( v22 )
    NtClose(v22);
  if ( TargetProcessHandle )
    NtClose(TargetProcessHandle);
  return v17;
}

```

## disassembly

```asm
0x18003c4c4  mov     [rsp-8+arg_10], rbx
0x18003c4c9  push    rbp
0x18003c4ca  push    rsi
0x18003c4cb  push    rdi
0x18003c4cc  push    r12
0x18003c4ce  push    r13
0x18003c4d0  lea     rbp, [rsp-20h]
0x18003c4d5  sub     rsp, 120h
0x18003c4dc  mov     rax, cs:__security_cookie
0x18003c4e3  xor     rax, rsp
0x18003c4e6  mov     [rbp+40h+var_30], rax
0x18003c4ea  and     [rsp+140h+var_E0], 0
0x18003c4ef  xor     r10d, r10d
0x18003c4f2  and     [rbp+40h+ExistingTokenHandle], 0
0x18003c4f7  xorps   xmm0, xmm0
0x18003c4fa  and     [rbp+40h+SourceHandle], 0
0x18003c4ff  mov     eax, r9d
0x18003c502  mov     r9, [rbp+40h+arg_28]
0x18003c506  mov     rsi, rdx
0x18003c509  mov     rdx, [rbp+40h+arg_58]
0x18003c510  and     [rsp+140h+TargetProcessHandle], 0
0x18003c516  and     [rbp+40h+Handle], 0
0x18003c51b  and     [rsp+140h+var_DC], 0
0x18003c520  mov     r12, [rbp+40h+arg_68]
0x18003c527  mov     [rbp+40h+var_C0], ecx
0x18003c52a  mov     [rbp+40h+var_90], r8
0x18003c52e  mov     r8d, ecx
0x18003c531  mov     rcx, [rbp+40h+arg_30]
0x18003c538  mov     [rbp+40h+var_80], rcx
0x18003c53c  mov     rcx, [rbp+40h+arg_40]
0x18003c543  mov     [rbp+40h+var_A0], rcx
0x18003c547  mov     rcx, [rbp+40h+arg_48]
0x18003c54e  mov     [rbp+40h+var_98], rdx
0x18003c552  mov     rdx, [rbp+40h+arg_60]
0x18003c559  mov     [rsp+140h+var_C4], eax
0x18003c55d  and     [rcx], r10
0x18003c560  mov     [rbp+40h+var_88], r9
0x18003c564  mov     [rbp+40h+TargetHandle], rcx
0x18003c568  mov     [rsp+140h+var_D8], 1
0x18003c570  mov     [rbp+40h+var_40], r10
0x18003c574  mov     [rbp+40h+var_38], r10d
0x18003c578  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18003c57c  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18003c580  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c584  test    r9, r9
0x18003c587  jnz     short loc_18003C593
0x18003c589  mov     ebx, 57h ; 'W'
0x18003c58e  jmp     loc_18003C89F
0x18003c593  cmp     eax, 3
0x18003c596  jnb     short loc_18003C589
0x18003c598  mov     eax, r8d
0x18003c59b  test    r8d, r8d
0x18003c59e  jz      short loc_18003C5CE
0x18003c5a0  sub     eax, 1
0x18003c5a3  jz      short loc_18003C5BA
0x18003c5a5  cmp     eax, 1
0x18003c5a8  jnz     short loc_18003C589
0x18003c5aa  mov     edi, [rbp+40h+arg_50]
0x18003c5b0  lea     r13d, [rax+6]
0x18003c5b4  bts     edi, 11h
0x18003c5b8  jmp     short loc_18003C5DE
0x18003c5ba  mov     edi, [rbp+40h+arg_50]
0x18003c5c0  mov     r13d, 5
0x18003c5c6  or      edi, 14000h
0x18003c5cc  jmp     short loc_18003C5DE
0x18003c5ce  mov     edi, [rbp+40h+arg_50]
0x18003c5d4  mov     r13d, 4
0x18003c5da  bts     edi, 0Eh
0x18003c5de  mov     [rbp+40h+arg_50], edi
0x18003c5e4  test    rdx, rdx
0x18003c5e7  jz      short loc_18003C611
0x18003c5e9  and     [rsp+140h+var_C8], r10d
0x18003c5ee  lea     rcx, [rsp+140h+var_C8]
0x18003c5f3  call    LUAGetUACPromptPolicy
0x18003c5f8  test    eax, eax
0x18003c5fa  jns     short loc_18003C611
0x18003c5fc  mov     ecx, eax; Status
0x18003c5fe  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c605  nop     dword ptr [rax+rax+00h]
0x18003c60a  mov     ebx, eax
0x18003c60c  jmp     loc_18003C89F
0x18003c611  lea     rcx, [rsp+140h+var_D8]
0x18003c616  call    cs:__imp_CheckElevationEnabled
0x18003c61d  nop     dword ptr [rax+rax+00h]
0x18003c622  mov     ebx, eax
0x18003c624  test    eax, eax
0x18003c626  jnz     loc_18003C89F
0x18003c62c  and     qword ptr [rsp+140h+TokenType], 0
0x18003c632  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x18003c637  lea     r8, [rbp+40h+Handle]; void **
0x18003c63b  mov     rcx, rsi; void *
0x18003c63e  lea     rdx, [rsp+140h+TargetProcessHandle]; void **
0x18003c643  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003c648  mov     rsi, [rbp+40h+Handle]
0x18003c64c  mov     ebx, eax
0x18003c64e  test    eax, eax
0x18003c650  jnz     loc_18003C872
0x18003c656  lea     rdx, [rsp+140h+var_DC]; int *
0x18003c65b  mov     rcx, rsi; void *
0x18003c65e  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003c663  test    eax, eax
0x18003c665  jns     short loc_18003C67C
0x18003c667  mov     ecx, eax; Status
0x18003c669  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c670  nop     dword ptr [rax+rax+00h]
0x18003c675  mov     ebx, eax
0x18003c677  jmp     loc_18003C872
0x18003c67c  test    r12, r12
0x18003c67f  jz      short loc_18003C694
0x18003c681  mov     edx, [rsp+140h+var_DC]; int
0x18003c685  mov     r8, r12; int *
0x18003c688  mov     rcx, rsi; Handle
0x18003c68b  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003c690  test    eax, eax
0x18003c692  js      short loc_18003C667
0x18003c694  mov     r12d, [rsp+140h+var_E0]
0x18003c699  mov     ecx, r12d; unsigned int
0x18003c69c  call    ?AiIsElevationAllowedForSession@@YAHK@Z; AiIsElevationAllowedForSession(ulong)
0x18003c6a1  test    eax, eax
0x18003c6a3  jnz     short loc_18003C6AF
0x18003c6a5  mov     ebx, 32h ; '2'
0x18003c6aa  jmp     loc_18003C872
0x18003c6af  mov     eax, [rsp+140h+var_D8]
0x18003c6b3  neg     eax
0x18003c6b5  mov     rax, [rbp+40h+var_A0]
0x18003c6b9  sbb     ebx, ebx
0x18003c6bb  and     ebx, [rsp+140h+var_C4]
0x18003c6bf  test    rax, rax
0x18003c6c2  jz      short loc_18003C6EE
0x18003c6c4  and     [rsp+140h+var_E0], 0
0x18003c6c9  lea     rdx, [rsp+140h+var_E0]; unsigned int *
0x18003c6ce  mov     rcx, rax; unsigned __int16 *
0x18003c6d1  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18003c6d6  test    eax, eax
0x18003c6d8  jnz     short loc_18003C6EE
0x18003c6da  test    [rsp+140h+var_E0], 4000h
0x18003c6e2  jz      short loc_18003C6EE
0x18003c6e4  bts     edi, 10h
0x18003c6e8  mov     [rbp+40h+arg_50], edi
0x18003c6ee  bt      edi, 19h
0x18003c6f2  jnb     short loc_18003C6FB
0x18003c6f4  cmp     [rsp+140h+var_DC], 0
0x18003c6f9  jz      short loc_18003C6A5
0x18003c6fb  lea     rax, [rbp+40h+ExistingTokenHandle]
0x18003c6ff  mov     r9, rsi
0x18003c702  mov     [rsp+140h+var_F0], rax
0x18003c707  lea     rdx, [rbp+40h+arg_50]
0x18003c70e  mov     rax, [rbp+40h+var_98]
0x18003c712  mov     r8d, r13d
0x18003c715  mov     [rsp+140h+var_F8], rax
0x18003c71a  mov     ecx, ebx
0x18003c71c  mov     eax, [rbp+40h+arg_38]
0x18003c722  mov     [rsp+140h+var_100], eax
0x18003c726  mov     rax, [rbp+40h+var_90]
0x18003c72a  mov     [rsp+140h+var_108], r12d
0x18003c72f  mov     qword ptr [rsp+140h+Options], rax
0x18003c734  mov     rax, [rbp+40h+var_88]
0x18003c738  mov     [rsp+140h+NewTokenHandle], rax
0x18003c73d  mov     rax, [rbp+40h+var_80]
0x18003c741  mov     qword ptr [rsp+140h+TokenType], rax
0x18003c746  call    ?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z; AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)
0x18003c74b  mov     rdi, [rbp+40h+ExistingTokenHandle]
0x18003c74f  mov     ebx, eax
0x18003c751  test    eax, eax
0x18003c753  jnz     loc_18003C85E
0x18003c759  test    rdi, rdi
0x18003c75c  jz      loc_18003C872
0x18003c762  and     [rbp+40h+ObjectAttributes.Attributes], eax
0x18003c765  lea     ecx, [rax+2]
0x18003c768  and     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x18003c76d  lea     rax, [rbp+40h+var_40]
0x18003c771  and     [rbp+40h+ObjectAttributes.ObjectName], 0
0x18003c776  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18003c77a  and     [rbp+40h+ObjectAttributes.SecurityDescriptor], 0
0x18003c77f  xor     r9d, r9d; EffectiveOnly
0x18003c782  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x18003c786  xor     edx, edx; DesiredAccess
0x18003c788  lea     rax, [rbp+40h+SourceHandle]
0x18003c78c  mov     dword ptr [rbp+40h+var_40+4], ecx
0x18003c78f  mov     [rsp+140h+NewTokenHandle], rax; HandleAttributes
0x18003c794  mov     [rsp+140h+TokenType], ecx; DesiredAccess
0x18003c798  mov     rcx, rdi; ExistingTokenHandle
0x18003c79b  mov     dword ptr [rbp+40h+var_40], 0Ch
0x18003c7a2  mov     word ptr [rbp+40h+var_38], 1
0x18003c7a8  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18003c7af  call    cs:__imp_NtDuplicateToken
0x18003c7b6  nop     dword ptr [rax+rax+00h]
0x18003c7bb  test    eax, eax
0x18003c7bd  jns     short loc_18003C7D4
0x18003c7bf  mov     ecx, eax; Status
0x18003c7c1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c7c8  nop     dword ptr [rax+rax+00h]
0x18003c7cd  mov     ebx, eax
0x18003c7cf  jmp     loc_18003C85E
0x18003c7d4  mov     rcx, rdi; Handle
0x18003c7d7  call    cs:__imp_NtClose
0x18003c7de  nop     dword ptr [rax+rax+00h]
0x18003c7e3  cmp     [rbp+40h+arg_20], 0
0x18003c7e7  mov     rdi, [rbp+40h+SourceHandle]
0x18003c7eb  jz      short loc_18003C80C
0x18003c7ed  mov     edx, [rbp+40h+var_C0]; unsigned int
0x18003c7f0  mov     rcx, rdi; Handle
0x18003c7f3  call    ?AipAdjustTokenSD@@YAKPEAXK@Z; AipAdjustTokenSD(void *,ulong)
0x18003c7f8  mov     ebx, eax
0x18003c7fa  test    eax, eax
0x18003c7fc  jnz     short loc_18003C85E
0x18003c7fe  mov     rcx, rdi; Handle
0x18003c801  call    ?AipAddTokenUserInTokenSD@@YAKPEAX@Z; AipAddTokenUserInTokenSD(void *)
0x18003c806  mov     ebx, eax
0x18003c808  test    eax, eax
0x18003c80a  jnz     short loc_18003C85E
0x18003c80c  mov     rcx, rdi; TokenHandle
0x18003c80f  call    ?AiSetMandatoryPolicy@@YAKPEAX@Z; AiSetMandatoryPolicy(void *)
0x18003c814  mov     ebx, eax
0x18003c816  test    eax, eax
0x18003c818  jnz     short loc_18003C85E
0x18003c81a  mov     r9, [rbp+40h+TargetHandle]; TargetHandle
0x18003c81e  mov     rdx, rdi; SourceHandle
0x18003c821  mov     r8, [rsp+140h+TargetProcessHandle]; TargetProcessHandle
0x18003c826  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18003c82a  mov     [rsp+140h+Options], 3; Options
0x18003c832  and     dword ptr [rsp+140h+NewTokenHandle], eax
0x18003c836  and     [rsp+140h+TokenType], eax
0x18003c83a  call    cs:__imp_NtDuplicateObject
0x18003c841  nop     dword ptr [rax+rax+00h]
0x18003c846  mov     ecx, eax; Status
0x18003c848  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c84f  nop     dword ptr [rax+rax+00h]
0x18003c854  mov     ebx, eax
0x18003c856  neg     eax
0x18003c858  sbb     rcx, rcx
0x18003c85b  and     rdi, rcx
0x18003c85e  test    rdi, rdi
0x18003c861  jz      short loc_18003C872
0x18003c863  mov     rcx, rdi; Handle
0x18003c866  call    cs:__imp_NtClose
0x18003c86d  nop     dword ptr [rax+rax+00h]
0x18003c872  test    rsi, rsi
0x18003c875  jz      short loc_18003C886
0x18003c877  mov     rcx, rsi; Handle
0x18003c87a  call    cs:__imp_NtClose
0x18003c881  nop     dword ptr [rax+rax+00h]
0x18003c886  cmp     [rsp+140h+TargetProcessHandle], 0
0x18003c88c  jz      short loc_18003C89F
0x18003c88e  mov     rcx, [rsp+140h+TargetProcessHandle]; Handle
0x18003c893  call    cs:__imp_NtClose
0x18003c89a  nop     dword ptr [rax+rax+00h]
0x18003c89f  mov     eax, ebx
0x18003c8a1  mov     rcx, [rbp+40h+var_30]
0x18003c8a5  xor     rcx, rsp; StackCookie
0x18003c8a8  call    __security_check_cookie
0x18003c8ad  mov     rbx, [rsp+140h+arg_10]
0x18003c8b5  add     rsp, 120h
0x18003c8bc  pop     r13
0x18003c8be  pop     r12
0x18003c8c0  pop     rdi
0x18003c8c1  pop     rsi
0x18003c8c2  pop     rbp
0x18003c8c3  retn
```
