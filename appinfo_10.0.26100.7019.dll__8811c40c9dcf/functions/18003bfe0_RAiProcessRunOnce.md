# RAiProcessRunOnce

- ea: `0x18003bfe0`
- end: `0x18003c2b6`
- name: `RAiProcessRunOnce`
- size: `726`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18000a230`
- `0x180011eb8`
- `0x180014d40`
- `0x1800168f0`
- `0x18001e424`
- `0x18002444c`
- `0x18003b5cc`
- `0x18003bfe0`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003c0b3`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003c0b3`
- `ntdll!NtClose` at `0x18003c102`
- `ntdll!NtClose` at `0x18003c11a`
- `ntdll!NtClose` at `0x18003c12f`
- `ntdll!NtClose` at `0x18003c102`
- `ntdll!NtClose` at `0x18003c11a`
- `ntdll!NtClose` at `0x18003c12f`
- `ntdll!NtQueryInformationToken` at `0x18003c1ef`
- `ntdll!NtQueryInformationToken` at `0x18003c1ef`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c177`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c177`

## pseudocode

```c
__int64 __fastcall RAiProcessRunOnce(void *a1, unsigned __int16 *a2, struct _PROCESS_INFORMATION *a3)
{
  DWORD v6; // r14d
  HANDLE v7; // rdi
  const unsigned __int16 *v8; // r9
  unsigned int ElevationToken; // ebx
  unsigned int ClientInformation; // eax
  unsigned int v11; // esi
  int v13; // eax
  unsigned int v14; // eax
  HANDLE v15; // rax
  void *v16; // rcx
  HANDLE v17; // rdx
  int v18; // [rsp+90h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-41h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp-39h] BYREF
  int v21; // [rsp+A4h] [rbp-35h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp-31h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp-29h] BYREF
  HANDLE v24; // [rsp+B8h] [rbp-21h] BYREF
  void *TokenInformation; // [rsp+C0h] [rbp-19h] BYREF
  unsigned __int16 v26[8]; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v27; // [rsp+D8h] [rbp-1h]
  __int64 v28; // [rsp+E8h] [rbp+Fh]
  int v29; // [rsp+F0h] [rbp+17h]
  __int16 v30; // [rsp+F4h] [rbp+1Bh]

  v29 = *(_DWORD *)L"r";
  *(_OWORD *)v26 = *(_OWORD *)L"runonce.exe /Explorer";
  v28 = *(_QWORD *)L"lorer";
  v6 = 0;
  v20 = 0;
  v7 = 0;
  v21 = 1;
  v18 = 0;
  Handle = 0;
  v24 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v27 = *(_OWORD *)L"exe /Explorer";
  v30 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = a2;
    if ( !a2 )
      v8 = L"NULL";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_61489c9bcb6c3e35b38483acb7c78608_Traceguids, v8);
  }
  ElevationToken = CheckElevationEnabled(&v21);
  if ( !ElevationToken )
  {
    ClientInformation = AiGetClientInformation(a1, &v24, &TokenHandle, &v20, 0);
    v7 = TokenHandle;
    ElevationToken = ClientInformation;
    if ( !ClientInformation )
    {
      v11 = v20;
      if ( !v20 )
      {
        ElevationToken = 1459;
        goto LABEL_10;
      }
      v13 = AiCheckForElevatedUser(TokenHandle, &v18);
      if ( v13 < 0 )
        goto LABEL_19;
      if ( v18 )
      {
        v15 = Handle;
      }
      else
      {
        if ( !v21 )
          goto LABEL_23;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          ElevationToken = AiGetElevationToken(0, v7, &Handle, 0);
          if ( ElevationToken )
            goto LABEL_10;
          v15 = Handle;
        }
        else
        {
          v13 = NtQueryInformationToken(v7, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
          if ( v13 < 0 )
          {
            if ( v13 == -1073741729 )
              goto LABEL_23;
            goto LABEL_19;
          }
          v15 = TokenInformation;
          Handle = TokenInformation;
        }
        v6 = 1;
      }
      v16 = v7;
      if ( v15 )
        v16 = v15;
      v13 = AiCheckForAdminUser(v16, 1, &v18);
      if ( v13 >= 0 )
      {
        if ( v18 )
        {
          v17 = v7;
          if ( Handle )
            v17 = Handle;
          v14 = AiLaunchProcess(v24, v17, 0, v6, 0, v26, 0x400u, 0, a2, 0, v11, 0, 0, 0, 0, 0, a3);
          goto LABEL_20;
        }
LABEL_23:
        ElevationToken = 740;
        goto LABEL_10;
      }
LABEL_19:
      v14 = RtlNtStatusToDosErrorNoTeb(v13);
LABEL_20:
      ElevationToken = v14;
    }
  }
LABEL_10:
  if ( Handle && Handle != v7 )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v7 )
    NtClose(v7);
  if ( v24 )
    NtClose(v24);
  return ElevationToken;
}

```

## disassembly

```asm
0x18003bfe0  mov     [rsp-8+arg_18], rbx
0x18003bfe5  push    rbp
0x18003bfe6  push    rsi
0x18003bfe7  push    rdi
0x18003bfe8  push    r12
0x18003bfea  push    r13
0x18003bfec  push    r14
0x18003bfee  push    r15
0x18003bff0  lea     rbp, [rsp-27h]
0x18003bff5  sub     rsp, 100h
0x18003bffc  mov     rax, cs:__security_cookie
0x18003c003  xor     rax, rsp
0x18003c006  mov     [rbp+57h+var_38], rax
0x18003c00a  movups  xmm0, xmmword ptr cs:aRunonceExeExpl; "runonce.exe /Explorer"
0x18003c011  mov     eax, dword ptr cs:aRunonceExeExpl+28h; "r"
0x18003c017  xor     r13d, r13d
0x18003c01a  movups  xmm1, xmmword ptr cs:aRunonceExeExpl+10h; "exe /Explorer"
0x18003c021  mov     [rbp+57h+var_40], eax
0x18003c024  xor     eax, eax
0x18003c026  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18003c02a  mov     r12, r8
0x18003c02d  mov     r15, rdx
0x18003c030  movsd   xmm0, qword ptr cs:aRunonceExeExpl+20h; "lorer"
0x18003c038  mov     rsi, rcx
0x18003c03b  movsd   [rbp+57h+var_48], xmm0
0x18003c040  mov     r14d, r13d
0x18003c043  mov     [rbp+57h+var_90], r13d
0x18003c047  mov     edi, r13d
0x18003c04a  mov     [rbp+57h+var_8C], 1
0x18003c051  mov     [rbp+57h+var_A0], r13d
0x18003c055  mov     [rbp+57h+Handle], r13
0x18003c059  mov     [rbp+57h+var_78], r13
0x18003c05d  mov     [rbp+57h+TokenHandle], r13
0x18003c061  mov     [rbp+57h+TokenInformation], r13
0x18003c065  mov     [rbp+57h+var_80], r13d
0x18003c069  movups  [rbp+57h+var_58], xmm1
0x18003c06d  mov     [rbp+57h+var_3C], ax
0x18003c071  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c078  lea     rax, WPP_GLOBAL_Control
0x18003c07f  cmp     rcx, rax
0x18003c082  jz      short loc_18003C0AF
0x18003c084  test    byte ptr [rcx+1Ch], 1
0x18003c088  jz      short loc_18003C0AF
0x18003c08a  mov     rcx, [rcx+10h]
0x18003c08e  lea     rax, aNull_0; "NULL"
0x18003c095  test    rdx, rdx
0x18003c098  lea     r8, WPP_61489c9bcb6c3e35b38483acb7c78608_Traceguids
0x18003c09f  mov     r9, rdx
0x18003c0a2  lea     edx, [r13+0Ah]
0x18003c0a6  cmovz   r9, rax
0x18003c0aa  call    WPP_SF_S
0x18003c0af  lea     rcx, [rbp+57h+var_8C]
0x18003c0b3  call    cs:__imp_CheckElevationEnabled
0x18003c0ba  nop     dword ptr [rax+rax+00h]
0x18003c0bf  mov     ebx, eax
0x18003c0c1  test    eax, eax
0x18003c0c3  jnz     short loc_18003C0F4
0x18003c0c5  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18003c0c9  mov     [rsp+130h+ReturnLength], r13; unsigned int *
0x18003c0ce  lea     r8, [rbp+57h+TokenHandle]; void **
0x18003c0d2  mov     rcx, rsi; void *
0x18003c0d5  lea     rdx, [rbp+57h+var_78]; void **
0x18003c0d9  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003c0de  mov     rdi, [rbp+57h+TokenHandle]
0x18003c0e2  mov     ebx, eax
0x18003c0e4  test    eax, eax
0x18003c0e6  jnz     short loc_18003C0F4
0x18003c0e8  mov     esi, [rbp+57h+var_90]
0x18003c0eb  test    esi, esi
0x18003c0ed  jnz     short loc_18003C165
0x18003c0ef  mov     ebx, 5B3h
0x18003c0f4  mov     rcx, [rbp+57h+Handle]; Handle
0x18003c0f8  test    rcx, rcx
0x18003c0fb  jz      short loc_18003C112
0x18003c0fd  cmp     rcx, rdi
0x18003c100  jz      short loc_18003C112
0x18003c102  call    cs:__imp_NtClose
0x18003c109  nop     dword ptr [rax+rax+00h]
0x18003c10e  mov     [rbp+57h+Handle], r13
0x18003c112  test    rdi, rdi
0x18003c115  jz      short loc_18003C126
0x18003c117  mov     rcx, rdi; Handle
0x18003c11a  call    cs:__imp_NtClose
0x18003c121  nop     dword ptr [rax+rax+00h]
0x18003c126  mov     rcx, [rbp+57h+var_78]; Handle
0x18003c12a  test    rcx, rcx
0x18003c12d  jz      short loc_18003C13B
0x18003c12f  call    cs:__imp_NtClose
0x18003c136  nop     dword ptr [rax+rax+00h]
0x18003c13b  mov     eax, ebx
0x18003c13d  mov     rcx, [rbp+57h+var_38]
0x18003c141  xor     rcx, rsp; StackCookie
0x18003c144  call    __security_check_cookie
0x18003c149  mov     rbx, [rsp+130h+arg_18]
0x18003c151  add     rsp, 100h
0x18003c158  pop     r15
0x18003c15a  pop     r14
0x18003c15c  pop     r13
0x18003c15e  pop     r12
0x18003c160  pop     rdi
0x18003c161  pop     rsi
0x18003c162  pop     rbp
0x18003c163  retn
0x18003c165  lea     rdx, [rbp+57h+var_A0]; int *
0x18003c169  mov     rcx, rdi; void *
0x18003c16c  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003c171  test    eax, eax
0x18003c173  jns     short loc_18003C18A
0x18003c175  mov     ecx, eax; Status
0x18003c177  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c17e  nop     dword ptr [rax+rax+00h]
0x18003c183  mov     ebx, eax
0x18003c185  jmp     loc_18003C0F4
0x18003c18a  cmp     [rbp+57h+var_A0], r13d
0x18003c18e  jnz     loc_18003C21C
0x18003c194  cmp     [rbp+57h+var_8C], r13d
0x18003c198  jnz     short loc_18003C1A4
0x18003c19a  mov     ebx, 2E4h
0x18003c19f  jmp     loc_18003C0F4
0x18003c1a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003c1ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003c1b0  test    al, al
0x18003c1b2  jz      short loc_18003C1D5
0x18003c1b4  xor     r9d, r9d; int *
0x18003c1b7  lea     r8, [rbp+57h+Handle]; DuplicateTokenHandle
0x18003c1bb  mov     rdx, rdi; HANDLE
0x18003c1be  xor     ecx, ecx; TokenHandle
0x18003c1c0  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x18003c1c5  mov     ebx, eax
0x18003c1c7  test    eax, eax
0x18003c1c9  jnz     loc_18003C0F4
0x18003c1cf  mov     rax, [rbp+57h+Handle]
0x18003c1d3  jmp     short loc_18003C214
0x18003c1d5  mov     r9d, 8; TokenInformationLength
0x18003c1db  lea     rax, [rbp+57h+var_80]
0x18003c1df  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003c1e3  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18003c1e8  mov     rcx, rdi; TokenHandle
0x18003c1eb  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003c1ef  call    cs:__imp_NtQueryInformationToken
0x18003c1f6  nop     dword ptr [rax+rax+00h]
0x18003c1fb  test    eax, eax
0x18003c1fd  jns     short loc_18003C20C
0x18003c1ff  cmp     eax, 0C000005Fh
0x18003c204  jnz     loc_18003C175
0x18003c20a  jmp     short loc_18003C19A
0x18003c20c  mov     rax, [rbp+57h+TokenInformation]
0x18003c210  mov     [rbp+57h+Handle], rax
0x18003c214  mov     r14d, 1
0x18003c21a  jmp     short loc_18003C220
0x18003c21c  mov     rax, [rbp+57h+Handle]
0x18003c220  test    rax, rax
0x18003c223  lea     r8, [rbp+57h+var_A0]; int *
0x18003c227  mov     rcx, rdi
0x18003c22a  mov     edx, 1; int
0x18003c22f  cmovnz  rcx, rax; Handle
0x18003c233  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003c238  test    eax, eax
0x18003c23a  js      loc_18003C175
0x18003c240  cmp     [rbp+57h+var_A0], r13d
0x18003c244  jz      loc_18003C19A
0x18003c24a  mov     rax, [rbp+57h+Handle]
0x18003c24e  mov     rdx, rdi
0x18003c251  mov     rcx, [rbp+57h+var_78]; void *
0x18003c255  test    rax, rax
0x18003c258  mov     [rsp+130h+var_B0], r12; struct _PROCESS_INFORMATION *
0x18003c260  mov     r9d, r14d; unsigned int
0x18003c263  mov     [rsp+130h+Src], r13; Src
0x18003c268  cmovnz  rdx, rax; void *
0x18003c26c  mov     [rsp+130h+var_C0], r13; unsigned __int64
0x18003c271  lea     rax, [rbp+57h+var_68]
0x18003c275  mov     [rsp+130h+var_C8], r13; void *
0x18003c27a  xor     r8d, r8d; void *
0x18003c27d  mov     [rsp+130h+var_D0], r13d; unsigned int
0x18003c282  mov     [rsp+130h+lpValue], r13; lpValue
0x18003c287  mov     [rsp+130h+var_E0], esi; unsigned int
0x18003c28b  mov     [rsp+130h+var_E8], r13; struct _APPINFO_STARTUPINFO *
0x18003c290  mov     [rsp+130h+var_F0], r15; unsigned __int16 *
0x18003c295  mov     [rsp+130h+var_F8], r13; unsigned __int16 *
0x18003c29a  mov     [rsp+130h+var_100], 400h; unsigned int
0x18003c2a2  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18003c2a7  mov     [rsp+130h+ReturnLength], r13; unsigned __int16 *
0x18003c2ac  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)
0x18003c2b1  jmp     loc_18003C183
```
