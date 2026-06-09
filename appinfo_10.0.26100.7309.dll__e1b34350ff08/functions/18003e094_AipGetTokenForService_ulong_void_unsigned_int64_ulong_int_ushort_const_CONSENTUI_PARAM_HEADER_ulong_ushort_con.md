# AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)

- ea: `0x18003e094`
- end: `0x18003e495`
- name: `?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z`
- size: `1025`
- prototype: `unsigned int(unsigned int, void *, unsigned __int64, unsigned int, int, const unsigned __int16 *, struct _CONSENTUI_PARAM_HEADER *, unsigned int, const unsigned __int16 *, unsigned __int64 *, unsigned int, const char *, enum UACPROMPT_POLICY *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003eaa0`
- `0x18003efa0`
- `0x18003f160`
- `0x18003f650`

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
- `0x18003e094`
- `0x1800437ec`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e1e6`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e1e6`
- `ntdll!NtClose` at `0x18003e3a7`
- `ntdll!NtClose` at `0x18003e436`
- `ntdll!NtClose` at `0x18003e44a`
- `ntdll!NtClose` at `0x18003e463`
- `ntdll!NtClose` at `0x18003e3a7`
- `ntdll!NtClose` at `0x18003e436`
- `ntdll!NtClose` at `0x18003e44a`
- `ntdll!NtClose` at `0x18003e463`
- `ntdll!NtDuplicateObject` at `0x18003e40a`
- `ntdll!NtDuplicateObject` at `0x18003e40a`
- `ntdll!NtDuplicateToken` at `0x18003e37f`
- `ntdll!NtDuplicateToken` at `0x18003e37f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e1ce`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e239`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e391`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e418`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e1ce`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e239`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e391`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e418`

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
0x18003e094  mov     [rsp-8+arg_10], rbx
0x18003e099  push    rbp
0x18003e09a  push    rsi
0x18003e09b  push    rdi
0x18003e09c  push    r12
0x18003e09e  push    r13
0x18003e0a0  lea     rbp, [rsp-20h]
0x18003e0a5  sub     rsp, 120h
0x18003e0ac  mov     rax, cs:__security_cookie
0x18003e0b3  xor     rax, rsp
0x18003e0b6  mov     [rbp+40h+var_30], rax
0x18003e0ba  and     [rsp+140h+var_E0], 0
0x18003e0bf  xor     r10d, r10d
0x18003e0c2  and     [rbp+40h+ExistingTokenHandle], 0
0x18003e0c7  xorps   xmm0, xmm0
0x18003e0ca  and     [rbp+40h+SourceHandle], 0
0x18003e0cf  mov     eax, r9d
0x18003e0d2  mov     r9, [rbp+40h+arg_28]
0x18003e0d6  mov     rsi, rdx
0x18003e0d9  mov     rdx, [rbp+40h+arg_58]
0x18003e0e0  and     [rsp+140h+TargetProcessHandle], 0
0x18003e0e6  and     [rbp+40h+Handle], 0
0x18003e0eb  and     [rsp+140h+var_DC], 0
0x18003e0f0  mov     r12, [rbp+40h+arg_68]
0x18003e0f7  mov     [rbp+40h+var_C0], ecx
0x18003e0fa  mov     [rbp+40h+var_90], r8
0x18003e0fe  mov     r8d, ecx
0x18003e101  mov     rcx, [rbp+40h+arg_30]
0x18003e108  mov     [rbp+40h+var_80], rcx
0x18003e10c  mov     rcx, [rbp+40h+arg_40]
0x18003e113  mov     [rbp+40h+var_A0], rcx
0x18003e117  mov     rcx, [rbp+40h+arg_48]
0x18003e11e  mov     [rbp+40h+var_98], rdx
0x18003e122  mov     rdx, [rbp+40h+arg_60]
0x18003e129  mov     [rsp+140h+var_C4], eax
0x18003e12d  and     [rcx], r10
0x18003e130  mov     [rbp+40h+var_88], r9
0x18003e134  mov     [rbp+40h+TargetHandle], rcx
0x18003e138  mov     [rsp+140h+var_D8], 1
0x18003e140  mov     [rbp+40h+var_40], r10
0x18003e144  mov     [rbp+40h+var_38], r10d
0x18003e148  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18003e14c  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18003e150  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003e154  test    r9, r9
0x18003e157  jnz     short loc_18003E163
0x18003e159  mov     ebx, 57h ; 'W'
0x18003e15e  jmp     loc_18003E46F
0x18003e163  cmp     eax, 3
0x18003e166  jnb     short loc_18003E159
0x18003e168  mov     eax, r8d
0x18003e16b  test    r8d, r8d
0x18003e16e  jz      short loc_18003E19E
0x18003e170  sub     eax, 1
0x18003e173  jz      short loc_18003E18A
0x18003e175  cmp     eax, 1
0x18003e178  jnz     short loc_18003E159
0x18003e17a  mov     edi, [rbp+40h+arg_50]
0x18003e180  lea     r13d, [rax+6]
0x18003e184  bts     edi, 11h
0x18003e188  jmp     short loc_18003E1AE
0x18003e18a  mov     edi, [rbp+40h+arg_50]
0x18003e190  mov     r13d, 5
0x18003e196  or      edi, 14000h
0x18003e19c  jmp     short loc_18003E1AE
0x18003e19e  mov     edi, [rbp+40h+arg_50]
0x18003e1a4  mov     r13d, 4
0x18003e1aa  bts     edi, 0Eh
0x18003e1ae  mov     [rbp+40h+arg_50], edi
0x18003e1b4  test    rdx, rdx
0x18003e1b7  jz      short loc_18003E1E1
0x18003e1b9  and     [rsp+140h+var_C8], r10d
0x18003e1be  lea     rcx, [rsp+140h+var_C8]
0x18003e1c3  call    LUAGetUACPromptPolicy
0x18003e1c8  test    eax, eax
0x18003e1ca  jns     short loc_18003E1E1
0x18003e1cc  mov     ecx, eax; Status
0x18003e1ce  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e1d5  nop     dword ptr [rax+rax+00h]
0x18003e1da  mov     ebx, eax
0x18003e1dc  jmp     loc_18003E46F
0x18003e1e1  lea     rcx, [rsp+140h+var_D8]
0x18003e1e6  call    cs:__imp_CheckElevationEnabled
0x18003e1ed  nop     dword ptr [rax+rax+00h]
0x18003e1f2  mov     ebx, eax
0x18003e1f4  test    eax, eax
0x18003e1f6  jnz     loc_18003E46F
0x18003e1fc  and     qword ptr [rsp+140h+TokenType], 0
0x18003e202  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x18003e207  lea     r8, [rbp+40h+Handle]; void **
0x18003e20b  mov     rcx, rsi; void *
0x18003e20e  lea     rdx, [rsp+140h+TargetProcessHandle]; void **
0x18003e213  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003e218  mov     rsi, [rbp+40h+Handle]
0x18003e21c  mov     ebx, eax
0x18003e21e  test    eax, eax
0x18003e220  jnz     loc_18003E442
0x18003e226  lea     rdx, [rsp+140h+var_DC]; int *
0x18003e22b  mov     rcx, rsi; void *
0x18003e22e  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003e233  test    eax, eax
0x18003e235  jns     short loc_18003E24C
0x18003e237  mov     ecx, eax; Status
0x18003e239  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e240  nop     dword ptr [rax+rax+00h]
0x18003e245  mov     ebx, eax
0x18003e247  jmp     loc_18003E442
0x18003e24c  test    r12, r12
0x18003e24f  jz      short loc_18003E264
0x18003e251  mov     edx, [rsp+140h+var_DC]; int
0x18003e255  mov     r8, r12; int *
0x18003e258  mov     rcx, rsi; Handle
0x18003e25b  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003e260  test    eax, eax
0x18003e262  js      short loc_18003E237
0x18003e264  mov     r12d, [rsp+140h+var_E0]
0x18003e269  mov     ecx, r12d; unsigned int
0x18003e26c  call    ?AiIsElevationAllowedForSession@@YAHK@Z; AiIsElevationAllowedForSession(ulong)
0x18003e271  test    eax, eax
0x18003e273  jnz     short loc_18003E27F
0x18003e275  mov     ebx, 32h ; '2'
0x18003e27a  jmp     loc_18003E442
0x18003e27f  mov     eax, [rsp+140h+var_D8]
0x18003e283  neg     eax
0x18003e285  mov     rax, [rbp+40h+var_A0]
0x18003e289  sbb     ebx, ebx
0x18003e28b  and     ebx, [rsp+140h+var_C4]
0x18003e28f  test    rax, rax
0x18003e292  jz      short loc_18003E2BE
0x18003e294  and     [rsp+140h+var_E0], 0
0x18003e299  lea     rdx, [rsp+140h+var_E0]; unsigned int *
0x18003e29e  mov     rcx, rax; unsigned __int16 *
0x18003e2a1  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18003e2a6  test    eax, eax
0x18003e2a8  jnz     short loc_18003E2BE
0x18003e2aa  test    [rsp+140h+var_E0], 4000h
0x18003e2b2  jz      short loc_18003E2BE
0x18003e2b4  bts     edi, 10h
0x18003e2b8  mov     [rbp+40h+arg_50], edi
0x18003e2be  bt      edi, 19h
0x18003e2c2  jnb     short loc_18003E2CB
0x18003e2c4  cmp     [rsp+140h+var_DC], 0
0x18003e2c9  jz      short loc_18003E275
0x18003e2cb  lea     rax, [rbp+40h+ExistingTokenHandle]
0x18003e2cf  mov     r9, rsi
0x18003e2d2  mov     [rsp+140h+var_F0], rax
0x18003e2d7  lea     rdx, [rbp+40h+arg_50]
0x18003e2de  mov     rax, [rbp+40h+var_98]
0x18003e2e2  mov     r8d, r13d
0x18003e2e5  mov     [rsp+140h+var_F8], rax
0x18003e2ea  mov     ecx, ebx
0x18003e2ec  mov     eax, [rbp+40h+arg_38]
0x18003e2f2  mov     [rsp+140h+var_100], eax
0x18003e2f6  mov     rax, [rbp+40h+var_90]
0x18003e2fa  mov     [rsp+140h+var_108], r12d
0x18003e2ff  mov     qword ptr [rsp+140h+Options], rax
0x18003e304  mov     rax, [rbp+40h+var_88]
0x18003e308  mov     [rsp+140h+NewTokenHandle], rax
0x18003e30d  mov     rax, [rbp+40h+var_80]
0x18003e311  mov     qword ptr [rsp+140h+TokenType], rax
0x18003e316  call    ?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z; AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)
0x18003e31b  mov     rdi, [rbp+40h+ExistingTokenHandle]
0x18003e31f  mov     ebx, eax
0x18003e321  test    eax, eax
0x18003e323  jnz     loc_18003E42E
0x18003e329  test    rdi, rdi
0x18003e32c  jz      loc_18003E442
0x18003e332  and     [rbp+40h+ObjectAttributes.Attributes], eax
0x18003e335  lea     ecx, [rax+2]
0x18003e338  and     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x18003e33d  lea     rax, [rbp+40h+var_40]
0x18003e341  and     [rbp+40h+ObjectAttributes.ObjectName], 0
0x18003e346  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18003e34a  and     [rbp+40h+ObjectAttributes.SecurityDescriptor], 0
0x18003e34f  xor     r9d, r9d; EffectiveOnly
0x18003e352  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x18003e356  xor     edx, edx; DesiredAccess
0x18003e358  lea     rax, [rbp+40h+SourceHandle]
0x18003e35c  mov     dword ptr [rbp+40h+var_40+4], ecx
0x18003e35f  mov     [rsp+140h+NewTokenHandle], rax; HandleAttributes
0x18003e364  mov     [rsp+140h+TokenType], ecx; DesiredAccess
0x18003e368  mov     rcx, rdi; ExistingTokenHandle
0x18003e36b  mov     dword ptr [rbp+40h+var_40], 0Ch
0x18003e372  mov     word ptr [rbp+40h+var_38], 1
0x18003e378  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18003e37f  call    cs:__imp_NtDuplicateToken
0x18003e386  nop     dword ptr [rax+rax+00h]
0x18003e38b  test    eax, eax
0x18003e38d  jns     short loc_18003E3A4
0x18003e38f  mov     ecx, eax; Status
0x18003e391  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e398  nop     dword ptr [rax+rax+00h]
0x18003e39d  mov     ebx, eax
0x18003e39f  jmp     loc_18003E42E
0x18003e3a4  mov     rcx, rdi; Handle
0x18003e3a7  call    cs:__imp_NtClose
0x18003e3ae  nop     dword ptr [rax+rax+00h]
0x18003e3b3  cmp     [rbp+40h+arg_20], 0
0x18003e3b7  mov     rdi, [rbp+40h+SourceHandle]
0x18003e3bb  jz      short loc_18003E3DC
0x18003e3bd  mov     edx, [rbp+40h+var_C0]; unsigned int
0x18003e3c0  mov     rcx, rdi; Handle
0x18003e3c3  call    ?AipAdjustTokenSD@@YAKPEAXK@Z; AipAdjustTokenSD(void *,ulong)
0x18003e3c8  mov     ebx, eax
0x18003e3ca  test    eax, eax
0x18003e3cc  jnz     short loc_18003E42E
0x18003e3ce  mov     rcx, rdi; Handle
0x18003e3d1  call    ?AipAddTokenUserInTokenSD@@YAKPEAX@Z; AipAddTokenUserInTokenSD(void *)
0x18003e3d6  mov     ebx, eax
0x18003e3d8  test    eax, eax
0x18003e3da  jnz     short loc_18003E42E
0x18003e3dc  mov     rcx, rdi; TokenHandle
0x18003e3df  call    ?AiSetMandatoryPolicy@@YAKPEAX@Z; AiSetMandatoryPolicy(void *)
0x18003e3e4  mov     ebx, eax
0x18003e3e6  test    eax, eax
0x18003e3e8  jnz     short loc_18003E42E
0x18003e3ea  mov     r9, [rbp+40h+TargetHandle]; TargetHandle
0x18003e3ee  mov     rdx, rdi; SourceHandle
0x18003e3f1  mov     r8, [rsp+140h+TargetProcessHandle]; TargetProcessHandle
0x18003e3f6  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18003e3fa  mov     [rsp+140h+Options], 3; Options
0x18003e402  and     dword ptr [rsp+140h+NewTokenHandle], eax
0x18003e406  and     [rsp+140h+TokenType], eax
0x18003e40a  call    cs:__imp_NtDuplicateObject
0x18003e411  nop     dword ptr [rax+rax+00h]
0x18003e416  mov     ecx, eax; Status
0x18003e418  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e41f  nop     dword ptr [rax+rax+00h]
0x18003e424  mov     ebx, eax
0x18003e426  neg     eax
0x18003e428  sbb     rcx, rcx
0x18003e42b  and     rdi, rcx
0x18003e42e  test    rdi, rdi
0x18003e431  jz      short loc_18003E442
0x18003e433  mov     rcx, rdi; Handle
0x18003e436  call    cs:__imp_NtClose
0x18003e43d  nop     dword ptr [rax+rax+00h]
0x18003e442  test    rsi, rsi
0x18003e445  jz      short loc_18003E456
0x18003e447  mov     rcx, rsi; Handle
0x18003e44a  call    cs:__imp_NtClose
0x18003e451  nop     dword ptr [rax+rax+00h]
0x18003e456  cmp     [rsp+140h+TargetProcessHandle], 0
0x18003e45c  jz      short loc_18003E46F
0x18003e45e  mov     rcx, [rsp+140h+TargetProcessHandle]; Handle
0x18003e463  call    cs:__imp_NtClose
0x18003e46a  nop     dword ptr [rax+rax+00h]
0x18003e46f  mov     eax, ebx
0x18003e471  mov     rcx, [rbp+40h+var_30]
0x18003e475  xor     rcx, rsp; StackCookie
0x18003e478  call    __security_check_cookie
0x18003e47d  mov     rbx, [rsp+140h+arg_10]
0x18003e485  add     rsp, 120h
0x18003e48c  pop     r13
0x18003e48e  pop     r12
0x18003e490  pop     rdi
0x18003e491  pop     rsi
0x18003e492  pop     rbp
0x18003e493  retn
```
