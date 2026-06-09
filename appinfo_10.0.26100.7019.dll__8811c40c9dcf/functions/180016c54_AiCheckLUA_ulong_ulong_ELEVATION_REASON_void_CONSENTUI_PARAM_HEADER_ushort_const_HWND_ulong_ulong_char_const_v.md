# AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)

- ea: `0x180016c54`
- end: `0x180016e48`
- name: `?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z`
- size: `500`
- prototype: `unsigned int __high(unsigned int, unsigned int *, enum ELEVATION_REASON, void *, struct _CONSENTUI_PARAM_HEADER *, const unsigned __int16 *, HWND, unsigned int, unsigned int, const char *, void **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b828`
- `0x180039cb0`
- `0x18003c4c4`

## callees

- `0x180011eb8`
- `0x18001362c`
- `0x180013740`
- `0x180013824`
- `0x1800168f0`
- `0x180016c54`
- `0x1800263a8`
- `0x180041e64`

## import_xrefs

- `ntdll!NtClose` at `0x180016e1f`
- `ntdll!NtClose` at `0x180016e1f`
- `ntdll!RtlNtStatusToDosError` at `0x180016e02`
- `ntdll!RtlNtStatusToDosError` at `0x180016e02`
- `ntdll!NtSetInformationToken` at `0x180016df0`
- `ntdll!NtSetInformationToken` at `0x180016df0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016c96`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016d9a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016c96`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016d9a`

## pseudocode

```c
__int64 __fastcall AiCheckLUA(
        unsigned int a1,
        unsigned int *a2,
        unsigned int a3,
        void *a4,
        int *a5,
        unsigned __int16 *a6,
        __int64 a7,
        unsigned int TokenInformation,
        DWORD a9,
        unsigned __int16 *a10,
        _QWORD *a11)
{
  _QWORD *v11; // r14
  unsigned int v12; // ebx
  NTSTATUS v16; // eax
  unsigned int v17; // ecx
  DWORD v18; // eax
  HANDLE v19; // rdi
  unsigned int v20; // eax
  NTSTATUS v21; // eax
  ULONG v22; // eax
  int v23; // eax
  int v25; // [rsp+50h] [rbp-10h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-8h] BYREF

  v11 = a11;
  v12 = 0;
  v25 = 0;
  TokenHandle = 0;
  *a11 = 0;
  v16 = AipRequireElevationPrompt(a1, a2, a4);
  if ( v16 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v16);
  v17 = *a2;
  if ( (*a2 & 0x18) == 0x10 )
    return v12;
  if ( (v17 & 8) == 0 || (v17 & 0x80008) == 0x80008 )
  {
    v12 = AipCheckSignatureRequiredPolicy(&v25);
    if ( v12 )
      return v12;
    if ( v25 )
      *a2 = *a2 & 0xFFF7FFF7 | 8;
  }
  v12 = AipCheckAutomaticAdminPolicy(&v25);
  if ( v12 )
    return v12;
  if ( v25 )
    *a2 |= 0x4000000u;
  if ( (unsigned int)LUAIsShadowAdminEnabled() )
    *a2 |= 0x8000000u;
  v18 = AiLaunchConsentUI(a4, a5, a6, a7, TokenInformation, *a2, a3, a9, a10, &TokenHandle);
  v19 = TokenHandle;
  v12 = v18;
  if ( v18 )
    goto LABEL_31;
  v20 = *a2;
  if ( !TokenHandle )
  {
    if ( (v20 & 0x10) == 0 )
      return 1223;
    return v12;
  }
  if ( (v20 & 0x2000000) != 0 )
  {
    *v11 = 0;
    goto LABEL_31;
  }
  v21 = AiCheckForElevatedUser(TokenHandle, &v25);
  if ( v21 < 0 )
    goto LABEL_21;
  if ( !v25 )
    goto LABEL_24;
  if ( (*a2 & 0x240) == 0x240 )
    goto LABEL_28;
  v21 = AiCheckForAdminUser(v19, 1, &v25);
  if ( v21 < 0 )
  {
LABEL_21:
    v22 = RtlNtStatusToDosErrorNoTeb(v21);
LABEL_22:
    v12 = v22;
    goto LABEL_31;
  }
  if ( v25 )
  {
LABEL_28:
    v23 = NtSetInformationToken(v19, TokenSessionId, &TokenInformation, 4u);
    if ( v23 < 0 )
    {
      v22 = RtlNtStatusToDosError(v23);
      goto LABEL_22;
    }
    *v11 = v19;
    v19 = 0;
    v12 = 0;
  }
  else
  {
LABEL_24:
    v12 = 740;
  }
LABEL_31:
  if ( v19 )
    NtClose(v19);
  return v12;
}

```

## disassembly

```asm
0x180016c54  mov     [rsp-18h+arg_0], rbx
0x180016c59  mov     [rsp-18h+arg_8], rsi
0x180016c5e  mov     [rsp-18h+arg_10], rdi
0x180016c63  push    rbp
0x180016c64  push    r14
0x180016c66  push    r15
0x180016c68  mov     rbp, rsp
0x180016c6b  sub     rsp, 60h
0x180016c6f  mov     r14, [rbp+arg_50]
0x180016c73  xor     ebx, ebx
0x180016c75  and     [rbp+var_10], ebx
0x180016c78  mov     r15d, r8d
0x180016c7b  and     [rbp+TokenHandle], rbx
0x180016c7f  mov     r8, r9; void *
0x180016c82  mov     rdi, r9
0x180016c85  mov     rsi, rdx
0x180016c88  and     [r14], rbx
0x180016c8b  call    ?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z; AipRequireElevationPrompt(ulong,ulong *,void *)
0x180016c90  test    eax, eax
0x180016c92  jns     short loc_180016CA9
0x180016c94  mov     ecx, eax; Status
0x180016c96  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180016c9d  nop     dword ptr [rax+rax+00h]
0x180016ca2  mov     ebx, eax
0x180016ca4  jmp     loc_180016E2B
0x180016ca9  mov     ecx, [rsi]
0x180016cab  mov     eax, ecx
0x180016cad  and     al, 18h
0x180016caf  cmp     al, 10h
0x180016cb1  jz      loc_180016E2B
0x180016cb7  test    cl, 8
0x180016cba  jz      short loc_180016CC7
0x180016cbc  mov     eax, 80008h
0x180016cc1  and     ecx, eax
0x180016cc3  cmp     ecx, eax
0x180016cc5  jnz     short loc_180016CEA
0x180016cc7  lea     rcx, [rbp+var_10]; int *
0x180016ccb  call    ?AipCheckSignatureRequiredPolicy@@YAKPEAH@Z; AipCheckSignatureRequiredPolicy(int *)
0x180016cd0  mov     ebx, eax
0x180016cd2  test    eax, eax
0x180016cd4  jnz     loc_180016E2B
0x180016cda  cmp     [rbp+var_10], eax
0x180016cdd  jz      short loc_180016CEA
0x180016cdf  mov     eax, [rsi]
0x180016ce1  btr     eax, 13h
0x180016ce5  or      eax, 8
0x180016ce8  mov     [rsi], eax
0x180016cea  lea     rcx, [rbp+var_10]; int *
0x180016cee  call    ?AipCheckAutomaticAdminPolicy@@YAKPEAH@Z; AipCheckAutomaticAdminPolicy(int *)
0x180016cf3  mov     ebx, eax
0x180016cf5  test    eax, eax
0x180016cf7  jnz     loc_180016E2B
0x180016cfd  cmp     [rbp+var_10], eax
0x180016d00  jz      short loc_180016D06
0x180016d02  bts     dword ptr [rsi], 1Ah
0x180016d06  call    LUAIsShadowAdminEnabled
0x180016d0b  test    eax, eax
0x180016d0d  jz      short loc_180016D13
0x180016d0f  bts     dword ptr [rsi], 1Bh
0x180016d13  mov     r9, [rbp+arg_30]
0x180016d17  lea     rax, [rbp+TokenHandle]
0x180016d1b  mov     r8, [rbp+arg_28]
0x180016d1f  mov     rcx, rdi
0x180016d22  mov     rdx, [rbp+arg_20]
0x180016d26  mov     [rsp+60h+var_18], rax
0x180016d2b  mov     rax, [rbp+arg_48]
0x180016d2f  mov     [rsp+60h+var_20], rax
0x180016d34  mov     eax, [rbp+arg_40]
0x180016d37  mov     [rsp+60h+var_28], eax
0x180016d3b  mov     eax, [rsi]
0x180016d3d  mov     [rsp+60h+var_30], r15d
0x180016d42  mov     [rsp+60h+var_38], eax
0x180016d46  mov     eax, [rbp+TokenInformation]
0x180016d49  mov     [rsp+60h+var_40], eax
0x180016d4d  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180016d52  mov     rdi, [rbp+TokenHandle]
0x180016d56  mov     ebx, eax
0x180016d58  test    eax, eax
0x180016d5a  jnz     loc_180016E17
0x180016d60  mov     eax, [rsi]
0x180016d62  test    rdi, rdi
0x180016d65  jnz     short loc_180016D79
0x180016d67  test    al, 10h
0x180016d69  jnz     loc_180016E2B
0x180016d6f  mov     ebx, 4C7h
0x180016d74  jmp     loc_180016E2B
0x180016d79  bt      eax, 19h
0x180016d7d  jnb     short loc_180016D88
0x180016d7f  and     qword ptr [r14], 0
0x180016d83  jmp     loc_180016E17
0x180016d88  lea     rdx, [rbp+var_10]; int *
0x180016d8c  mov     rcx, rdi; void *
0x180016d8f  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180016d94  test    eax, eax
0x180016d96  jns     short loc_180016DAA
0x180016d98  mov     ecx, eax; Status
0x180016d9a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180016da1  nop     dword ptr [rax+rax+00h]
0x180016da6  mov     ebx, eax
0x180016da8  jmp     short loc_180016E17
0x180016daa  cmp     [rbp+var_10], 0
0x180016dae  jnz     short loc_180016DB7
0x180016db0  mov     ebx, 2E4h
0x180016db5  jmp     short loc_180016E17
0x180016db7  mov     eax, [rsi]
0x180016db9  mov     ecx, 240h
0x180016dbe  and     eax, ecx
0x180016dc0  cmp     eax, ecx
0x180016dc2  jz      short loc_180016DDF
0x180016dc4  lea     r8, [rbp+var_10]; int *
0x180016dc8  mov     edx, 1; int
0x180016dcd  mov     rcx, rdi; Handle
0x180016dd0  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x180016dd5  test    eax, eax
0x180016dd7  js      short loc_180016D98
0x180016dd9  cmp     [rbp+var_10], 0
0x180016ddd  jz      short loc_180016DB0
0x180016ddf  mov     r9d, 4; TokenInformationLength
0x180016de5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180016de9  mov     rcx, rdi; TokenHandle
0x180016dec  lea     edx, [r9+8]; TokenInformationClass
0x180016df0  call    cs:__imp_NtSetInformationToken
0x180016df7  nop     dword ptr [rax+rax+00h]
0x180016dfc  test    eax, eax
0x180016dfe  jns     short loc_180016E10
0x180016e00  mov     ecx, eax; Status
0x180016e02  call    cs:__imp_RtlNtStatusToDosError
0x180016e09  nop     dword ptr [rax+rax+00h]
0x180016e0e  jmp     short loc_180016DA6
0x180016e10  mov     [r14], rdi
0x180016e13  xor     edi, edi
0x180016e15  xor     ebx, ebx
0x180016e17  test    rdi, rdi
0x180016e1a  jz      short loc_180016E2B
0x180016e1c  mov     rcx, rdi; Handle
0x180016e1f  call    cs:__imp_NtClose
0x180016e26  nop     dword ptr [rax+rax+00h]
0x180016e2b  lea     r11, [rsp+60h+var_s0]
0x180016e30  mov     eax, ebx
0x180016e32  mov     rbx, [r11+20h]
0x180016e36  mov     rsi, [r11+28h]
0x180016e3a  mov     rdi, [r11+30h]
0x180016e3e  mov     rsp, r11
0x180016e41  pop     r15
0x180016e43  pop     r14
0x180016e45  pop     rbp
0x180016e46  retn
```
