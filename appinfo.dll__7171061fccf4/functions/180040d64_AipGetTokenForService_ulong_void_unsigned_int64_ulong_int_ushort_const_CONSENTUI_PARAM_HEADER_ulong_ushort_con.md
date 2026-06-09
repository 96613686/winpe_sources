# AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)

- ea: `0x180040d64`
- end: `0x180041140`
- name: `?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z`
- size: `988`
- prototype: `__int64 __fastcall(unsigned int, void *, __int64, unsigned int, int, const unsigned __int16 *, struct _CONSENTUI_PARAM_HEADER *, unsigned int, unsigned __int16 *, unsigned __int64 *, unsigned int, const char *, enum UACPROMPT_POLICY *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041700`
- `0x180041c00`
- `0x180041dc0`
- `0x1800422a0`

## callees

- `0x180009d50`
- `0x18000f210`
- `0x180010dd4`
- `0x1800113a4`
- `0x18001b9e4`
- `0x18001c378`
- `0x18001c634`
- `0x18003ef28`
- `0x18003f14c`
- `0x180040d64`
- `0x180045fa4`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x180040ec2`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x180040ec2`
- `ntdll!NtClose` at `0x180041077`
- `ntdll!NtClose` at `0x1800410f4`
- `ntdll!NtClose` at `0x180041102`
- `ntdll!NtClose` at `0x180041115`
- `ntdll!NtClose` at `0x180041077`
- `ntdll!NtClose` at `0x1800410f4`
- `ntdll!NtClose` at `0x180041102`
- `ntdll!NtClose` at `0x180041115`
- `ntdll!NtDuplicateObject` at `0x1800410d4`
- `ntdll!NtDuplicateObject` at `0x1800410d4`
- `ntdll!NtDuplicateToken` at `0x18004105e`
- `ntdll!NtDuplicateToken` at `0x18004105e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040eb0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040f12`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004106a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800410dc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040eb0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040f12`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004106a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800410dc`

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
  int *v14; // r12
  enum UACPROMPT_POLICY *v16; // rdx
  ULONG v17; // ebx
  unsigned int v18; // r13d
  unsigned int v19; // edi
  NTSTATUS v20; // eax
  unsigned int ClientInformation; // eax
  HANDLE v22; // rsi
  NTSTATUS v23; // eax
  unsigned int v24; // r12d
  unsigned int v25; // ebx
  ULONG v26; // eax
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

  v14 = a14;
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
  v31 = 0;
  ExistingTokenHandle = 0;
  SourceHandle = 0;
  TargetProcessHandle = 0;
  Handle = 0;
  v33 = 1;
  v32 = 0;
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
  if ( v23 < 0 || v14 && (v23 = AiCheckForAdminUser(v22, v32, v14), v23 < 0) )
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
      if ( !AiCheckSecureApplicationDirectory(v41, &v31) && (v31 & 0x4000) != 0 )
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
        ObjectAttributes.SecurityQualityOfService = &v48;
        v48 = 0x20000000CLL;
        LOWORD(v49) = 1;
        ObjectAttributes.Length = 48;
        memset(&ObjectAttributes.RootDirectory, 0, 20);
        ObjectAttributes.SecurityDescriptor = 0;
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
0x180040d64  mov     [rsp-8+arg_10], rbx
0x180040d69  push    rbp
0x180040d6a  push    rsi
0x180040d6b  push    rdi
0x180040d6c  push    r12
0x180040d6e  push    r13
0x180040d70  lea     rbp, [rsp-20h]
0x180040d75  sub     rsp, 120h
0x180040d7c  mov     rax, cs:__security_cookie
0x180040d83  xor     rax, rsp
0x180040d86  mov     [rbp+40h+var_30], rax
0x180040d8a  mov     r12, [rbp+40h+arg_68]
0x180040d91  xor     r10d, r10d
0x180040d94  mov     [rbp+40h+var_C0], ecx
0x180040d97  xorps   xmm0, xmm0
0x180040d9a  mov     eax, r9d
0x180040d9d  mov     [rbp+40h+var_90], r8
0x180040da1  mov     r9, [rbp+40h+arg_28]
0x180040da5  mov     r8d, ecx
0x180040da8  mov     rcx, [rbp+40h+arg_30]
0x180040daf  mov     rsi, rdx
0x180040db2  mov     rdx, [rbp+40h+arg_58]
0x180040db9  mov     [rbp+40h+var_80], rcx
0x180040dbd  mov     rcx, [rbp+40h+arg_40]
0x180040dc4  mov     [rbp+40h+var_A0], rcx
0x180040dc8  mov     rcx, [rbp+40h+arg_48]
0x180040dcf  mov     [rbp+40h+var_98], rdx
0x180040dd3  mov     rdx, [rbp+40h+arg_60]
0x180040dda  mov     [rsp+140h+var_C4], eax
0x180040dde  mov     [rcx], r10
0x180040de1  mov     [rbp+40h+var_88], r9
0x180040de5  mov     [rbp+40h+TargetHandle], rcx
0x180040de9  mov     [rsp+140h+var_E0], 0
0x180040df1  mov     [rbp+40h+ExistingTokenHandle], 0
0x180040df9  mov     [rbp+40h+SourceHandle], 0
0x180040e01  mov     [rsp+140h+TargetProcessHandle], 0
0x180040e0a  mov     [rbp+40h+Handle], 0
0x180040e12  mov     [rsp+140h+var_D8], 1
0x180040e1a  mov     [rsp+140h+var_DC], 0
0x180040e22  mov     [rbp+40h+var_40], r10
0x180040e26  mov     [rbp+40h+var_38], r10d
0x180040e2a  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180040e2e  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180040e32  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180040e36  test    r9, r9
0x180040e39  jnz     short loc_180040E45
0x180040e3b  mov     ebx, 57h ; 'W'
0x180040e40  jmp     loc_18004111B
0x180040e45  cmp     eax, 3
0x180040e48  jnb     short loc_180040E3B
0x180040e4a  mov     eax, r8d
0x180040e4d  test    r8d, r8d
0x180040e50  jz      short loc_180040E80
0x180040e52  sub     eax, 1
0x180040e55  jz      short loc_180040E6C
0x180040e57  cmp     eax, 1
0x180040e5a  jnz     short loc_180040E3B
0x180040e5c  mov     edi, [rbp+40h+arg_50]
0x180040e62  lea     r13d, [rax+6]
0x180040e66  bts     edi, 11h
0x180040e6a  jmp     short loc_180040E90
0x180040e6c  mov     edi, [rbp+40h+arg_50]
0x180040e72  mov     r13d, 5
0x180040e78  or      edi, 14000h
0x180040e7e  jmp     short loc_180040E90
0x180040e80  mov     edi, [rbp+40h+arg_50]
0x180040e86  mov     r13d, 4
0x180040e8c  bts     edi, 0Eh
0x180040e90  mov     [rbp+40h+arg_50], edi
0x180040e96  test    rdx, rdx
0x180040e99  jz      short loc_180040EBD
0x180040e9b  lea     rcx, [rsp+140h+var_C8]
0x180040ea0  mov     [rsp+140h+var_C8], r10d
0x180040ea5  call    LUAGetUACPromptPolicy
0x180040eaa  test    eax, eax
0x180040eac  jns     short loc_180040EBD
0x180040eae  mov     ecx, eax; Status
0x180040eb0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040eb6  mov     ebx, eax
0x180040eb8  jmp     loc_18004111B
0x180040ebd  lea     rcx, [rsp+140h+var_D8]
0x180040ec2  call    cs:__imp_CheckElevationEnabled
0x180040ec8  mov     ebx, eax
0x180040eca  test    eax, eax
0x180040ecc  jnz     loc_18004111B
0x180040ed2  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x180040ed7  mov     qword ptr [rsp+140h+TokenType], 0; unsigned int *
0x180040ee0  lea     r8, [rbp+40h+Handle]; void **
0x180040ee4  mov     rcx, rsi; void *
0x180040ee7  lea     rdx, [rsp+140h+TargetProcessHandle]; void **
0x180040eec  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180040ef1  mov     rsi, [rbp+40h+Handle]
0x180040ef5  mov     ebx, eax
0x180040ef7  test    eax, eax
0x180040ef9  jnz     loc_1800410FA
0x180040eff  lea     rdx, [rsp+140h+var_DC]; int *
0x180040f04  mov     rcx, rsi; void *
0x180040f07  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180040f0c  test    eax, eax
0x180040f0e  jns     short loc_180040F1F
0x180040f10  mov     ecx, eax; Status
0x180040f12  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040f18  mov     ebx, eax
0x180040f1a  jmp     loc_1800410FA
0x180040f1f  test    r12, r12
0x180040f22  jz      short loc_180040F37
0x180040f24  mov     edx, [rsp+140h+var_DC]; int
0x180040f28  mov     r8, r12; int *
0x180040f2b  mov     rcx, rsi; Handle
0x180040f2e  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x180040f33  test    eax, eax
0x180040f35  js      short loc_180040F10
0x180040f37  mov     r12d, [rsp+140h+var_E0]
0x180040f3c  mov     ecx, r12d; unsigned int
0x180040f3f  call    ?AiIsElevationAllowedForSession@@YAHK@Z; AiIsElevationAllowedForSession(ulong)
0x180040f44  test    eax, eax
0x180040f46  jnz     short loc_180040F52
0x180040f48  mov     ebx, 32h ; '2'
0x180040f4d  jmp     loc_1800410FA
0x180040f52  mov     eax, [rsp+140h+var_D8]
0x180040f56  neg     eax
0x180040f58  mov     rax, [rbp+40h+var_A0]
0x180040f5c  sbb     ebx, ebx
0x180040f5e  and     ebx, [rsp+140h+var_C4]
0x180040f62  test    rax, rax
0x180040f65  jz      short loc_180040F94
0x180040f67  lea     rdx, [rsp+140h+var_E0]; unsigned int *
0x180040f6c  mov     [rsp+140h+var_E0], 0
0x180040f74  mov     rcx, rax; unsigned __int16 *
0x180040f77  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x180040f7c  test    eax, eax
0x180040f7e  jnz     short loc_180040F94
0x180040f80  test    [rsp+140h+var_E0], 4000h
0x180040f88  jz      short loc_180040F94
0x180040f8a  bts     edi, 10h
0x180040f8e  mov     [rbp+40h+arg_50], edi
0x180040f94  bt      edi, 19h
0x180040f98  jnb     short loc_180040FA1
0x180040f9a  cmp     [rsp+140h+var_DC], 0
0x180040f9f  jz      short loc_180040F48
0x180040fa1  lea     rax, [rbp+40h+ExistingTokenHandle]
0x180040fa5  mov     r9, rsi
0x180040fa8  mov     [rsp+140h+var_F0], rax
0x180040fad  lea     rdx, [rbp+40h+arg_50]
0x180040fb4  mov     rax, [rbp+40h+var_98]
0x180040fb8  mov     r8d, r13d
0x180040fbb  mov     [rsp+140h+var_F8], rax
0x180040fc0  mov     ecx, ebx
0x180040fc2  mov     eax, [rbp+40h+arg_38]
0x180040fc8  mov     [rsp+140h+var_100], eax
0x180040fcc  mov     rax, [rbp+40h+var_90]
0x180040fd0  mov     [rsp+140h+var_108], r12d
0x180040fd5  mov     qword ptr [rsp+140h+Options], rax
0x180040fda  mov     rax, [rbp+40h+var_88]
0x180040fde  mov     [rsp+140h+NewTokenHandle], rax
0x180040fe3  mov     rax, [rbp+40h+var_80]
0x180040fe7  mov     qword ptr [rsp+140h+TokenType], rax
0x180040fec  call    ?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z; AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)
0x180040ff1  mov     rdi, [rbp+40h+ExistingTokenHandle]
0x180040ff5  mov     ebx, eax
0x180040ff7  test    eax, eax
0x180040ff9  jnz     loc_1800410EC
0x180040fff  test    rdi, rdi
0x180041002  jz      loc_1800410FA
0x180041008  lea     ecx, [rax+2]
0x18004100b  mov     [rbp+40h+ObjectAttributes.Attributes], eax
0x18004100e  lea     rax, [rbp+40h+var_40]
0x180041012  mov     dword ptr [rbp+40h+var_40+4], ecx
0x180041015  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x180041019  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18004101d  lea     rax, [rbp+40h+SourceHandle]
0x180041021  mov     dword ptr [rbp+40h+var_40], 0Ch
0x180041028  mov     [rsp+140h+NewTokenHandle], rax; NewTokenHandle
0x18004102d  xor     r9d, r9d; EffectiveOnly
0x180041030  mov     [rsp+140h+TokenType], ecx; TokenType
0x180041034  xor     edx, edx; DesiredAccess
0x180041036  mov     rcx, rdi; ExistingTokenHandle
0x180041039  mov     word ptr [rbp+40h+var_38], 1
0x18004103f  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180041046  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x18004104e  mov     [rbp+40h+ObjectAttributes.ObjectName], 0
0x180041056  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], 0
0x18004105e  call    cs:__imp_NtDuplicateToken
0x180041064  test    eax, eax
0x180041066  jns     short loc_180041074
0x180041068  mov     ecx, eax; Status
0x18004106a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180041070  mov     ebx, eax
0x180041072  jmp     short loc_1800410EC
0x180041074  mov     rcx, rdi; Handle
0x180041077  call    cs:__imp_NtClose
0x18004107d  cmp     [rbp+40h+arg_20], 0
0x180041081  mov     rdi, [rbp+40h+SourceHandle]
0x180041085  jz      short loc_1800410A6
0x180041087  mov     edx, [rbp+40h+var_C0]; unsigned int
0x18004108a  mov     rcx, rdi; Handle
0x18004108d  call    ?AipAdjustTokenSD@@YAKPEAXK@Z; AipAdjustTokenSD(void *,ulong)
0x180041092  mov     ebx, eax
0x180041094  test    eax, eax
0x180041096  jnz     short loc_1800410EC
0x180041098  mov     rcx, rdi; Handle
0x18004109b  call    ?AipAddTokenUserInTokenSD@@YAKPEAX@Z; AipAddTokenUserInTokenSD(void *)
0x1800410a0  mov     ebx, eax
0x1800410a2  test    eax, eax
0x1800410a4  jnz     short loc_1800410EC
0x1800410a6  mov     rcx, rdi; TokenHandle
0x1800410a9  call    ?AiSetMandatoryPolicy@@YAKPEAX@Z; AiSetMandatoryPolicy(void *)
0x1800410ae  mov     ebx, eax
0x1800410b0  test    eax, eax
0x1800410b2  jnz     short loc_1800410EC
0x1800410b4  mov     r9, [rbp+40h+TargetHandle]; TargetHandle
0x1800410b8  mov     rdx, rdi; SourceHandle
0x1800410bb  mov     r8, [rsp+140h+TargetProcessHandle]; TargetProcessHandle
0x1800410c0  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800410c4  mov     [rsp+140h+Options], 3; Options
0x1800410cc  mov     dword ptr [rsp+140h+NewTokenHandle], eax; HandleAttributes
0x1800410d0  mov     [rsp+140h+TokenType], eax; DesiredAccess
0x1800410d4  call    cs:__imp_NtDuplicateObject
0x1800410da  mov     ecx, eax; Status
0x1800410dc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800410e2  mov     ebx, eax
0x1800410e4  neg     eax
0x1800410e6  sbb     rcx, rcx
0x1800410e9  and     rdi, rcx
0x1800410ec  test    rdi, rdi
0x1800410ef  jz      short loc_1800410FA
0x1800410f1  mov     rcx, rdi; Handle
0x1800410f4  call    cs:__imp_NtClose
0x1800410fa  test    rsi, rsi
0x1800410fd  jz      short loc_180041108
0x1800410ff  mov     rcx, rsi; Handle
0x180041102  call    cs:__imp_NtClose
0x180041108  cmp     [rsp+140h+TargetProcessHandle], 0
0x18004110e  jz      short loc_18004111B
0x180041110  mov     rcx, [rsp+140h+TargetProcessHandle]; Handle
0x180041115  call    cs:__imp_NtClose
0x18004111b  mov     eax, ebx
0x18004111d  mov     rcx, [rbp+40h+var_30]
0x180041121  xor     rcx, rsp; StackCookie
0x180041124  call    __security_check_cookie
0x180041129  mov     rbx, [rsp+140h+arg_10]
0x180041131  add     rsp, 120h
0x180041138  pop     r13
0x18004113a  pop     r12
0x18004113c  pop     rdi
0x18004113d  pop     rsi
0x18004113e  pop     rbp
0x18004113f  retn
```
