# AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)

- ea: `0x18003e5d4`
- end: `0x18003e9d5`
- name: `?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z`
- size: `1025`
- prototype: `unsigned int(unsigned int, void *, unsigned __int64, unsigned int, int, const unsigned __int16 *, struct _CONSENTUI_PARAM_HEADER *, unsigned int, const unsigned __int16 *, unsigned __int64 *, unsigned int, const char *, enum UACPROMPT_POLICY *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003efe0`
- `0x18003f4e0`
- `0x18003f6a0`
- `0x18003fb90`

## callees

- `0x18000a230`
- `0x18000f24c`
- `0x180011ff8`
- `0x1800126c4`
- `0x180016a40`
- `0x180016da4`
- `0x180019b18`
- `0x18001a1cc`
- `0x18001a54c`
- `0x18003e5d4`
- `0x180043d2c`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e726`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e726`
- `ntdll!NtClose` at `0x18003e8e7`
- `ntdll!NtClose` at `0x18003e976`
- `ntdll!NtClose` at `0x18003e98a`
- `ntdll!NtClose` at `0x18003e9a3`
- `ntdll!NtClose` at `0x18003e8e7`
- `ntdll!NtClose` at `0x18003e976`
- `ntdll!NtClose` at `0x18003e98a`
- `ntdll!NtClose` at `0x18003e9a3`
- `ntdll!NtDuplicateObject` at `0x18003e94a`
- `ntdll!NtDuplicateObject` at `0x18003e94a`
- `ntdll!NtDuplicateToken` at `0x18003e8bf`
- `ntdll!NtDuplicateToken` at `0x18003e8bf`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e70e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e779`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e8d1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e958`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e70e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e779`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e8d1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e958`

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
    if ( !AiIsElevationAllowedForSession(v31) )
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
0x18003e5d4  mov     [rsp-8+arg_10], rbx
0x18003e5d9  push    rbp
0x18003e5da  push    rsi
0x18003e5db  push    rdi
0x18003e5dc  push    r12
0x18003e5de  push    r13
0x18003e5e0  lea     rbp, [rsp-20h]
0x18003e5e5  sub     rsp, 120h
0x18003e5ec  mov     rax, cs:__security_cookie
0x18003e5f3  xor     rax, rsp
0x18003e5f6  mov     [rbp+40h+var_30], rax
0x18003e5fa  and     [rsp+140h+var_E0], 0
0x18003e5ff  xor     r10d, r10d
0x18003e602  and     [rbp+40h+ExistingTokenHandle], 0
0x18003e607  xorps   xmm0, xmm0
0x18003e60a  and     [rbp+40h+SourceHandle], 0
0x18003e60f  mov     eax, r9d
0x18003e612  mov     r9, [rbp+40h+arg_28]
0x18003e616  mov     rsi, rdx
0x18003e619  mov     rdx, [rbp+40h+arg_58]
0x18003e620  and     [rsp+140h+TargetProcessHandle], 0
0x18003e626  and     [rbp+40h+Handle], 0
0x18003e62b  and     [rsp+140h+var_DC], 0
0x18003e630  mov     r12, [rbp+40h+arg_68]
0x18003e637  mov     [rbp+40h+var_C0], ecx
0x18003e63a  mov     [rbp+40h+var_90], r8
0x18003e63e  mov     r8d, ecx
0x18003e641  mov     rcx, [rbp+40h+arg_30]
0x18003e648  mov     [rbp+40h+var_80], rcx
0x18003e64c  mov     rcx, [rbp+40h+arg_40]
0x18003e653  mov     [rbp+40h+var_A0], rcx
0x18003e657  mov     rcx, [rbp+40h+arg_48]
0x18003e65e  mov     [rbp+40h+var_98], rdx
0x18003e662  mov     rdx, [rbp+40h+arg_60]
0x18003e669  mov     [rsp+140h+var_C4], eax
0x18003e66d  and     [rcx], r10
0x18003e670  mov     [rbp+40h+var_88], r9
0x18003e674  mov     [rbp+40h+TargetHandle], rcx
0x18003e678  mov     [rsp+140h+var_D8], 1
0x18003e680  mov     [rbp+40h+var_40], r10
0x18003e684  mov     [rbp+40h+var_38], r10d
0x18003e688  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18003e68c  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18003e690  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003e694  test    r9, r9
0x18003e697  jnz     short loc_18003E6A3
0x18003e699  mov     ebx, 57h ; 'W'
0x18003e69e  jmp     loc_18003E9AF
0x18003e6a3  cmp     eax, 3
0x18003e6a6  jnb     short loc_18003E699
0x18003e6a8  mov     eax, r8d
0x18003e6ab  test    r8d, r8d
0x18003e6ae  jz      short loc_18003E6DE
0x18003e6b0  sub     eax, 1
0x18003e6b3  jz      short loc_18003E6CA
0x18003e6b5  cmp     eax, 1
0x18003e6b8  jnz     short loc_18003E699
0x18003e6ba  mov     edi, [rbp+40h+arg_50]
0x18003e6c0  lea     r13d, [rax+6]
0x18003e6c4  bts     edi, 11h
0x18003e6c8  jmp     short loc_18003E6EE
0x18003e6ca  mov     edi, [rbp+40h+arg_50]
0x18003e6d0  mov     r13d, 5
0x18003e6d6  or      edi, 14000h
0x18003e6dc  jmp     short loc_18003E6EE
0x18003e6de  mov     edi, [rbp+40h+arg_50]
0x18003e6e4  mov     r13d, 4
0x18003e6ea  bts     edi, 0Eh
0x18003e6ee  mov     [rbp+40h+arg_50], edi
0x18003e6f4  test    rdx, rdx
0x18003e6f7  jz      short loc_18003E721
0x18003e6f9  and     [rsp+140h+var_C8], r10d
0x18003e6fe  lea     rcx, [rsp+140h+var_C8]
0x18003e703  call    LUAGetUACPromptPolicy
0x18003e708  test    eax, eax
0x18003e70a  jns     short loc_18003E721
0x18003e70c  mov     ecx, eax; Status
0x18003e70e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e715  nop     dword ptr [rax+rax+00h]
0x18003e71a  mov     ebx, eax
0x18003e71c  jmp     loc_18003E9AF
0x18003e721  lea     rcx, [rsp+140h+var_D8]
0x18003e726  call    cs:__imp_CheckElevationEnabled
0x18003e72d  nop     dword ptr [rax+rax+00h]
0x18003e732  mov     ebx, eax
0x18003e734  test    eax, eax
0x18003e736  jnz     loc_18003E9AF
0x18003e73c  and     qword ptr [rsp+140h+TokenType], 0
0x18003e742  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x18003e747  lea     r8, [rbp+40h+Handle]; void **
0x18003e74b  mov     rcx, rsi; void *
0x18003e74e  lea     rdx, [rsp+140h+TargetProcessHandle]; void **
0x18003e753  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003e758  mov     rsi, [rbp+40h+Handle]
0x18003e75c  mov     ebx, eax
0x18003e75e  test    eax, eax
0x18003e760  jnz     loc_18003E982
0x18003e766  lea     rdx, [rsp+140h+var_DC]; int *
0x18003e76b  mov     rcx, rsi; void *
0x18003e76e  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003e773  test    eax, eax
0x18003e775  jns     short loc_18003E78C
0x18003e777  mov     ecx, eax; Status
0x18003e779  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e780  nop     dword ptr [rax+rax+00h]
0x18003e785  mov     ebx, eax
0x18003e787  jmp     loc_18003E982
0x18003e78c  test    r12, r12
0x18003e78f  jz      short loc_18003E7A4
0x18003e791  mov     edx, [rsp+140h+var_DC]; int
0x18003e795  mov     r8, r12; int *
0x18003e798  mov     rcx, rsi; Handle
0x18003e79b  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003e7a0  test    eax, eax
0x18003e7a2  js      short loc_18003E777
0x18003e7a4  mov     r12d, [rsp+140h+var_E0]
0x18003e7a9  mov     ecx, r12d; unsigned int
0x18003e7ac  call    ?AiIsElevationAllowedForSession@@YAHK@Z; AiIsElevationAllowedForSession(ulong)
0x18003e7b1  test    eax, eax
0x18003e7b3  jnz     short loc_18003E7BF
0x18003e7b5  mov     ebx, 32h ; '2'
0x18003e7ba  jmp     loc_18003E982
0x18003e7bf  mov     eax, [rsp+140h+var_D8]
0x18003e7c3  neg     eax
0x18003e7c5  mov     rax, [rbp+40h+var_A0]
0x18003e7c9  sbb     ebx, ebx
0x18003e7cb  and     ebx, [rsp+140h+var_C4]
0x18003e7cf  test    rax, rax
0x18003e7d2  jz      short loc_18003E7FE
0x18003e7d4  and     [rsp+140h+var_E0], 0
0x18003e7d9  lea     rdx, [rsp+140h+var_E0]; unsigned int *
0x18003e7de  mov     rcx, rax; unsigned __int16 *
0x18003e7e1  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18003e7e6  test    eax, eax
0x18003e7e8  jnz     short loc_18003E7FE
0x18003e7ea  test    [rsp+140h+var_E0], 4000h
0x18003e7f2  jz      short loc_18003E7FE
0x18003e7f4  bts     edi, 10h
0x18003e7f8  mov     [rbp+40h+arg_50], edi
0x18003e7fe  bt      edi, 19h
0x18003e802  jnb     short loc_18003E80B
0x18003e804  cmp     [rsp+140h+var_DC], 0
0x18003e809  jz      short loc_18003E7B5
0x18003e80b  lea     rax, [rbp+40h+ExistingTokenHandle]
0x18003e80f  mov     r9, rsi
0x18003e812  mov     [rsp+140h+var_F0], rax
0x18003e817  lea     rdx, [rbp+40h+arg_50]
0x18003e81e  mov     rax, [rbp+40h+var_98]
0x18003e822  mov     r8d, r13d
0x18003e825  mov     [rsp+140h+var_F8], rax
0x18003e82a  mov     ecx, ebx
0x18003e82c  mov     eax, [rbp+40h+arg_38]
0x18003e832  mov     [rsp+140h+var_100], eax
0x18003e836  mov     rax, [rbp+40h+var_90]
0x18003e83a  mov     [rsp+140h+var_108], r12d
0x18003e83f  mov     qword ptr [rsp+140h+Options], rax
0x18003e844  mov     rax, [rbp+40h+var_88]
0x18003e848  mov     [rsp+140h+NewTokenHandle], rax
0x18003e84d  mov     rax, [rbp+40h+var_80]
0x18003e851  mov     qword ptr [rsp+140h+TokenType], rax
0x18003e856  call    ?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z; AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)
0x18003e85b  mov     rdi, [rbp+40h+ExistingTokenHandle]
0x18003e85f  mov     ebx, eax
0x18003e861  test    eax, eax
0x18003e863  jnz     loc_18003E96E
0x18003e869  test    rdi, rdi
0x18003e86c  jz      loc_18003E982
0x18003e872  and     [rbp+40h+ObjectAttributes.Attributes], eax
0x18003e875  lea     ecx, [rax+2]
0x18003e878  and     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x18003e87d  lea     rax, [rbp+40h+var_40]
0x18003e881  and     [rbp+40h+ObjectAttributes.ObjectName], 0
0x18003e886  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18003e88a  and     [rbp+40h+ObjectAttributes.SecurityDescriptor], 0
0x18003e88f  xor     r9d, r9d; EffectiveOnly
0x18003e892  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x18003e896  xor     edx, edx; DesiredAccess
0x18003e898  lea     rax, [rbp+40h+SourceHandle]
0x18003e89c  mov     dword ptr [rbp+40h+var_40+4], ecx
0x18003e89f  mov     [rsp+140h+NewTokenHandle], rax; HandleAttributes
0x18003e8a4  mov     [rsp+140h+TokenType], ecx; DesiredAccess
0x18003e8a8  mov     rcx, rdi; ExistingTokenHandle
0x18003e8ab  mov     dword ptr [rbp+40h+var_40], 0Ch
0x18003e8b2  mov     word ptr [rbp+40h+var_38], 1
0x18003e8b8  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18003e8bf  call    cs:__imp_NtDuplicateToken
0x18003e8c6  nop     dword ptr [rax+rax+00h]
0x18003e8cb  test    eax, eax
0x18003e8cd  jns     short loc_18003E8E4
0x18003e8cf  mov     ecx, eax; Status
0x18003e8d1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e8d8  nop     dword ptr [rax+rax+00h]
0x18003e8dd  mov     ebx, eax
0x18003e8df  jmp     loc_18003E96E
0x18003e8e4  mov     rcx, rdi; Handle
0x18003e8e7  call    cs:__imp_NtClose
0x18003e8ee  nop     dword ptr [rax+rax+00h]
0x18003e8f3  cmp     [rbp+40h+arg_20], 0
0x18003e8f7  mov     rdi, [rbp+40h+SourceHandle]
0x18003e8fb  jz      short loc_18003E91C
0x18003e8fd  mov     edx, [rbp+40h+var_C0]; unsigned int
0x18003e900  mov     rcx, rdi; Handle
0x18003e903  call    ?AipAdjustTokenSD@@YAKPEAXK@Z; AipAdjustTokenSD(void *,ulong)
0x18003e908  mov     ebx, eax
0x18003e90a  test    eax, eax
0x18003e90c  jnz     short loc_18003E96E
0x18003e90e  mov     rcx, rdi; Handle
0x18003e911  call    ?AipAddTokenUserInTokenSD@@YAKPEAX@Z; AipAddTokenUserInTokenSD(void *)
0x18003e916  mov     ebx, eax
0x18003e918  test    eax, eax
0x18003e91a  jnz     short loc_18003E96E
0x18003e91c  mov     rcx, rdi; TokenHandle
0x18003e91f  call    ?AiSetMandatoryPolicy@@YAKPEAX@Z; AiSetMandatoryPolicy(void *)
0x18003e924  mov     ebx, eax
0x18003e926  test    eax, eax
0x18003e928  jnz     short loc_18003E96E
0x18003e92a  mov     r9, [rbp+40h+TargetHandle]; TargetHandle
0x18003e92e  mov     rdx, rdi; SourceHandle
0x18003e931  mov     r8, [rsp+140h+TargetProcessHandle]; TargetProcessHandle
0x18003e936  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18003e93a  mov     [rsp+140h+Options], 3; Options
0x18003e942  and     dword ptr [rsp+140h+NewTokenHandle], eax
0x18003e946  and     [rsp+140h+TokenType], eax
0x18003e94a  call    cs:__imp_NtDuplicateObject
0x18003e951  nop     dword ptr [rax+rax+00h]
0x18003e956  mov     ecx, eax; Status
0x18003e958  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e95f  nop     dword ptr [rax+rax+00h]
0x18003e964  mov     ebx, eax
0x18003e966  neg     eax
0x18003e968  sbb     rcx, rcx
0x18003e96b  and     rdi, rcx
0x18003e96e  test    rdi, rdi
0x18003e971  jz      short loc_18003E982
0x18003e973  mov     rcx, rdi; Handle
0x18003e976  call    cs:__imp_NtClose
0x18003e97d  nop     dword ptr [rax+rax+00h]
0x18003e982  test    rsi, rsi
0x18003e985  jz      short loc_18003E996
0x18003e987  mov     rcx, rsi; Handle
0x18003e98a  call    cs:__imp_NtClose
0x18003e991  nop     dword ptr [rax+rax+00h]
0x18003e996  cmp     [rsp+140h+TargetProcessHandle], 0
0x18003e99c  jz      short loc_18003E9AF
0x18003e99e  mov     rcx, [rsp+140h+TargetProcessHandle]; Handle
0x18003e9a3  call    cs:__imp_NtClose
0x18003e9aa  nop     dword ptr [rax+rax+00h]
0x18003e9af  mov     eax, ebx
0x18003e9b1  mov     rcx, [rbp+40h+var_30]
0x18003e9b5  xor     rcx, rsp; StackCookie
0x18003e9b8  call    __security_check_cookie
0x18003e9bd  mov     rbx, [rsp+140h+arg_10]
0x18003e9c5  add     rsp, 120h
0x18003e9cc  pop     r13
0x18003e9ce  pop     r12
0x18003e9d0  pop     rdi
0x18003e9d1  pop     rsi
0x18003e9d2  pop     rbp
0x18003e9d3  retn
```
