# AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)

- ea: `0x180016da4`
- end: `0x180016f98`
- name: `?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a2a8`
- `0x18003ac30`
- `0x18003e5d4`

## callees

- `0x180011ff8`
- `0x180013798`
- `0x18001387c`
- `0x180016a40`
- `0x180016da4`
- `0x180016fa0`
- `0x180024a98`
- `0x180043f6c`

## import_xrefs

- `ntdll!NtClose` at `0x180016f6f`
- `ntdll!NtClose` at `0x180016f6f`
- `ntdll!RtlNtStatusToDosError` at `0x180016f52`
- `ntdll!RtlNtStatusToDosError` at `0x180016f52`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016de6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016eea`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016de6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016eea`
- `ntdll!NtSetInformationToken` at `0x180016f40`
- `ntdll!NtSetInformationToken` at `0x180016f40`

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
0x180016da4  mov     [rsp-18h+arg_0], rbx
0x180016da9  mov     [rsp-18h+arg_8], rsi
0x180016dae  mov     [rsp-18h+arg_10], rdi
0x180016db3  push    rbp
0x180016db4  push    r14
0x180016db6  push    r15
0x180016db8  mov     rbp, rsp
0x180016dbb  sub     rsp, 60h
0x180016dbf  mov     r14, [rbp+arg_50]
0x180016dc3  xor     ebx, ebx
0x180016dc5  and     [rbp+var_10], ebx
0x180016dc8  mov     r15d, r8d
0x180016dcb  and     [rbp+TokenHandle], rbx
0x180016dcf  mov     r8, r9; void *
0x180016dd2  mov     rdi, r9
0x180016dd5  mov     rsi, rdx
0x180016dd8  and     [r14], rbx
0x180016ddb  call    ?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z; AipRequireElevationPrompt(ulong,ulong *,void *)
0x180016de0  test    eax, eax
0x180016de2  jns     short loc_180016DF9
0x180016de4  mov     ecx, eax; Status
0x180016de6  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180016ded  nop     dword ptr [rax+rax+00h]
0x180016df2  mov     ebx, eax
0x180016df4  jmp     loc_180016F7B
0x180016df9  mov     ecx, [rsi]
0x180016dfb  mov     eax, ecx
0x180016dfd  and     al, 18h
0x180016dff  cmp     al, 10h
0x180016e01  jz      loc_180016F7B
0x180016e07  test    cl, 8
0x180016e0a  jz      short loc_180016E17
0x180016e0c  mov     eax, 80008h
0x180016e11  and     ecx, eax
0x180016e13  cmp     ecx, eax
0x180016e15  jnz     short loc_180016E3A
0x180016e17  lea     rcx, [rbp+var_10]; int *
0x180016e1b  call    ?AipCheckSignatureRequiredPolicy@@YAKPEAH@Z; AipCheckSignatureRequiredPolicy(int *)
0x180016e20  mov     ebx, eax
0x180016e22  test    eax, eax
0x180016e24  jnz     loc_180016F7B
0x180016e2a  cmp     [rbp+var_10], eax
0x180016e2d  jz      short loc_180016E3A
0x180016e2f  mov     eax, [rsi]
0x180016e31  btr     eax, 13h
0x180016e35  or      eax, 8
0x180016e38  mov     [rsi], eax
0x180016e3a  lea     rcx, [rbp+var_10]; int *
0x180016e3e  call    ?AipCheckAutomaticAdminPolicy@@YAKPEAH@Z; AipCheckAutomaticAdminPolicy(int *)
0x180016e43  mov     ebx, eax
0x180016e45  test    eax, eax
0x180016e47  jnz     loc_180016F7B
0x180016e4d  cmp     [rbp+var_10], eax
0x180016e50  jz      short loc_180016E56
0x180016e52  bts     dword ptr [rsi], 1Ah
0x180016e56  call    LUAIsShadowAdminEnabled
0x180016e5b  test    eax, eax
0x180016e5d  jz      short loc_180016E63
0x180016e5f  bts     dword ptr [rsi], 1Bh
0x180016e63  mov     r9, [rbp+arg_30]
0x180016e67  lea     rax, [rbp+TokenHandle]
0x180016e6b  mov     r8, [rbp+arg_28]
0x180016e6f  mov     rcx, rdi
0x180016e72  mov     rdx, [rbp+arg_20]
0x180016e76  mov     [rsp+60h+var_18], rax
0x180016e7b  mov     rax, [rbp+arg_48]
0x180016e7f  mov     [rsp+60h+var_20], rax
0x180016e84  mov     eax, [rbp+arg_40]
0x180016e87  mov     [rsp+60h+var_28], eax
0x180016e8b  mov     eax, [rsi]
0x180016e8d  mov     [rsp+60h+var_30], r15d
0x180016e92  mov     [rsp+60h+var_38], eax
0x180016e96  mov     eax, [rbp+TokenInformation]
0x180016e99  mov     [rsp+60h+var_40], eax
0x180016e9d  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180016ea2  mov     rdi, [rbp+TokenHandle]
0x180016ea6  mov     ebx, eax
0x180016ea8  test    eax, eax
0x180016eaa  jnz     loc_180016F67
0x180016eb0  mov     eax, [rsi]
0x180016eb2  test    rdi, rdi
0x180016eb5  jnz     short loc_180016EC9
0x180016eb7  test    al, 10h
0x180016eb9  jnz     loc_180016F7B
0x180016ebf  mov     ebx, 4C7h
0x180016ec4  jmp     loc_180016F7B
0x180016ec9  bt      eax, 19h
0x180016ecd  jnb     short loc_180016ED8
0x180016ecf  and     qword ptr [r14], 0
0x180016ed3  jmp     loc_180016F67
0x180016ed8  lea     rdx, [rbp+var_10]; int *
0x180016edc  mov     rcx, rdi; void *
0x180016edf  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180016ee4  test    eax, eax
0x180016ee6  jns     short loc_180016EFA
0x180016ee8  mov     ecx, eax; Status
0x180016eea  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180016ef1  nop     dword ptr [rax+rax+00h]
0x180016ef6  mov     ebx, eax
0x180016ef8  jmp     short loc_180016F67
0x180016efa  cmp     [rbp+var_10], 0
0x180016efe  jnz     short loc_180016F07
0x180016f00  mov     ebx, 2E4h
0x180016f05  jmp     short loc_180016F67
0x180016f07  mov     eax, [rsi]
0x180016f09  mov     ecx, 240h
0x180016f0e  and     eax, ecx
0x180016f10  cmp     eax, ecx
0x180016f12  jz      short loc_180016F2F
0x180016f14  lea     r8, [rbp+var_10]; int *
0x180016f18  mov     edx, 1; int
0x180016f1d  mov     rcx, rdi; Handle
0x180016f20  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x180016f25  test    eax, eax
0x180016f27  js      short loc_180016EE8
0x180016f29  cmp     [rbp+var_10], 0
0x180016f2d  jz      short loc_180016F00
0x180016f2f  mov     r9d, 4; TokenInformationLength
0x180016f35  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180016f39  mov     rcx, rdi; TokenHandle
0x180016f3c  lea     edx, [r9+8]; TokenInformationClass
0x180016f40  call    cs:__imp_NtSetInformationToken
0x180016f47  nop     dword ptr [rax+rax+00h]
0x180016f4c  test    eax, eax
0x180016f4e  jns     short loc_180016F60
0x180016f50  mov     ecx, eax; Status
0x180016f52  call    cs:__imp_RtlNtStatusToDosError
0x180016f59  nop     dword ptr [rax+rax+00h]
0x180016f5e  jmp     short loc_180016EF6
0x180016f60  mov     [r14], rdi
0x180016f63  xor     edi, edi
0x180016f65  xor     ebx, ebx
0x180016f67  test    rdi, rdi
0x180016f6a  jz      short loc_180016F7B
0x180016f6c  mov     rcx, rdi; Handle
0x180016f6f  call    cs:__imp_NtClose
0x180016f76  nop     dword ptr [rax+rax+00h]
0x180016f7b  lea     r11, [rsp+60h+var_s0]
0x180016f80  mov     eax, ebx
0x180016f82  mov     rbx, [r11+20h]
0x180016f86  mov     rsi, [r11+28h]
0x180016f8a  mov     rdi, [r11+30h]
0x180016f8e  mov     rsp, r11
0x180016f91  pop     r15
0x180016f93  pop     r14
0x180016f95  pop     rbp
0x180016f96  retn
```
