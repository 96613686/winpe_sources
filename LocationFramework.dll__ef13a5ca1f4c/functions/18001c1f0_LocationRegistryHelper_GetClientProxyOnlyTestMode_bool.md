# LocationRegistryHelper::GetClientProxyOnlyTestMode(bool *)

- ea: `0x18001c1f0`
- end: `0x18001c3e2`
- name: `?GetClientProxyOnlyTestMode@LocationRegistryHelper@@SAJPEA_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001c0ac`
- `0x18003d8d4`
- `0x18003de4c`
- `0x18005591c`
- `0x1800a2918`
- `0x1800a3944`

## callees

- `0x18001c1f0`
- `0x18008fa98`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001c2bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001c381`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001c2bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001c381`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18001c308`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18001c308`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001c258`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001c258`

## string_xrefs

- `0x18001c24a`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x18001c2ad`: `TestConfig\`
- `0x18001c2d4`: `SYSTEM\CurrentControlSet\Services\lfsvc\Migrated\`
- `0x18001c3b0`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x18001c394`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x18001c3a4`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`

## pseudocode

```c
__int64 __fastcall LocationRegistryHelper::GetClientProxyOnlyTestMode(bool *a1)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v5; // r8d
  __int64 result; // rax
  wil::details *v7; // [rsp+28h] [rbp-250h]
  _DWORD v8[4]; // [rsp+50h] [rbp-228h] BYREF
  _WORD v9[256]; // [rsp+60h] [rbp-218h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+0h]

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v8[0] = 0;
  memset_0(v9, 0, 0x1FEu);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"LfSvc",
                                 L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                 v9,
                                 510,
                                 0);
  v3 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      goto LABEL_11;
    return v3;
  }
  v4 = -1;
  do
    ++v4;
  while ( v9[v4] );
  if ( (unsigned __int64)(v4 + 12) >= 0xFF )
  {
    v3 = -2147418113;
    LODWORD(v7) = -2147418113;
    wil::details::in1diag5::Return_HrMsg(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
      "CLocationPersistedRegPathHelper::GetPersistedRegPath",
      "E_UNEXPECTED",
      v7,
      (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
      (const char *)v4,
      11);
    return v3;
  }
  v5 = *((unsigned __int16 *)&v8[3] + v4 + 1) - 92;
  if ( *((_WORD *)&v8[3] + v4 + 1) == 92 )
    v5 = (unsigned __int16)v9[v4];
  if ( v5 )
    _o_wcscat_s(v9, 255, L"\\");
  _o_wcscat_s(v9, 255, L"TestConfig\\");
LABEL_11:
  result = GetRegistryValueWithFallbackW(
             -2147483646,
             v9,
             -2147483646,
             L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Migrated\\",
             L"USE_CLIENT_PROXY_INFERENCE_ONLY",
             16,
             0,
             v8,
             4,
             0);
  if ( (result & 0xFFFFFFFD) != 0 )
  {
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *a1 = v8[0] == 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c1f0  mov     [rsp+arg_8], rbx
0x18001c1f5  mov     [rsp+arg_10], rsi
0x18001c1fa  push    rdi
0x18001c1fb  sub     rsp, 270h
0x18001c202  mov     rax, cs:__security_cookie
0x18001c209  xor     rax, rsp
0x18001c20c  mov     [rsp+278h+var_18], rax
0x18001c214  xor     esi, esi
0x18001c216  mov     rdi, rcx
0x18001c219  test    rcx, rcx
0x18001c21c  jz      loc_18001C354
0x18001c222  mov     [rcx], sil
0x18001c225  mov     ebx, 1FEh
0x18001c22a  mov     r8d, ebx; Size
0x18001c22d  mov     [rsp+278h+var_228], esi
0x18001c231  xor     edx, edx; Val
0x18001c233  lea     rcx, [rsp+278h+var_218]; void *
0x18001c238  call    memset_0
0x18001c23d  mov     r9d, ebx
0x18001c240  mov     [rsp+278h+var_258], rsi
0x18001c245  lea     r8, [rsp+278h+var_218]
0x18001c24a  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18001c251  lea     rcx, aLfsvc_1; "LfSvc"
0x18001c258  call    cs:__imp_GetPersistedRegistryLocationW
0x18001c25e  mov     ebx, eax
0x18001c260  test    eax, eax
0x18001c262  jnz     loc_18001C365
0x18001c268  lea     rax, [rsp+278h+var_218]
0x18001c26d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c271  inc     rdx
0x18001c274  cmp     [rax+rdx*2], si
0x18001c278  jnz     short loc_18001C271
0x18001c27a  lea     rax, [rdx+0Ch]
0x18001c27e  mov     ebx, 0FFh
0x18001c283  cmp     rax, rbx
0x18001c286  jnb     loc_18001C38C
0x18001c28c  movzx   r8d, [rsp+rdx*2+278h+var_21A]
0x18001c292  sub     r8d, 5Ch ; '\'
0x18001c296  jnz     short loc_18001C2A4
0x18001c298  movzx   r8d, [rsp+rdx*2+278h+var_218]
0x18001c29e  movzx   ecx, si
0x18001c2a1  sub     r8d, ecx
0x18001c2a4  test    r8d, r8d
0x18001c2a7  jnz     loc_18001C372
0x18001c2ad  lea     r8, aTestconfig; "TestConfig\\"
0x18001c2b4  mov     rdx, rbx
0x18001c2b7  lea     rcx, [rsp+278h+var_218]
0x18001c2bc  call    cs:__imp__o_wcscat_s
0x18001c2c2  mov     [rsp+278h+var_230], rsi
0x18001c2c7  lea     rax, [rsp+278h+var_228]
0x18001c2cc  mov     dword ptr [rsp+278h+var_238], 4
0x18001c2d4  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18001c2db  mov     [rsp+278h+var_240], rax
0x18001c2e0  lea     rdx, [rsp+278h+var_218]
0x18001c2e5  mov     rcx, 0FFFFFFFF80000002h
0x18001c2ec  mov     [rsp+278h+var_248], rsi
0x18001c2f1  lea     rax, aUseClientProxy; "USE_CLIENT_PROXY_INFERENCE_ONLY"
0x18001c2f8  mov     dword ptr [rsp+278h+var_250], 10h
0x18001c300  mov     r8, rcx
0x18001c303  mov     [rsp+278h+var_258], rax
0x18001c308  call    cs:__imp_GetRegistryValueWithFallbackW
0x18001c30e  test    eax, 0FFFFFFFDh
0x18001c313  jz      short loc_18001C346
0x18001c315  test    eax, eax
0x18001c317  jle     short loc_18001C321
0x18001c319  movzx   eax, ax
0x18001c31c  or      eax, 80070000h
0x18001c321  mov     rcx, [rsp+278h+var_18]
0x18001c329  xor     rcx, rsp; StackCookie
0x18001c32c  call    __security_check_cookie
0x18001c331  lea     r11, [rsp+278h+var_8]
0x18001c339  mov     rbx, [r11+18h]
0x18001c33d  mov     rsi, [r11+20h]
0x18001c341  mov     rsp, r11
0x18001c344  pop     rdi
0x18001c345  retn
0x18001c346  cmp     [rsp+278h+var_228], 1
0x18001c34b  setz    al
0x18001c34e  mov     [rdi], al
0x18001c350  xor     eax, eax
0x18001c352  jmp     short loc_18001C321
0x18001c354  mov     eax, 80004003h
0x18001c359  jmp     short loc_18001C321
0x18001c35b  test    ebx, ebx
0x18001c35d  jns     loc_18001C2C2
0x18001c363  jmp     short loc_18001C3DB
0x18001c365  jle     short loc_18001C35B
0x18001c367  movzx   ebx, ax
0x18001c36a  or      ebx, 80070000h
0x18001c370  jmp     short loc_18001C35B
0x18001c372  lea     r8, asc_18016EDDC; "\\"
0x18001c379  mov     rdx, rbx
0x18001c37c  lea     rcx, [rsp+278h+var_218]
0x18001c381  call    cs:__imp__o_wcscat_s
0x18001c387  jmp     loc_18001C2AD
0x18001c38c  mov     rcx, [rsp+278h]; this
0x18001c394  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x18001c39b  mov     [rsp+278h+var_238], 0Bh
0x18001c3a4  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x18001c3ab  mov     [rsp+278h+var_240], rdx; char *
0x18001c3b0  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18001c3b7  mov     [rsp+278h+var_248], rax; __int64
0x18001c3bc  mov     ebx, 8000FFFFh
0x18001c3c1  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18001c3c8  mov     dword ptr [rsp+278h+var_250], ebx; wil::details *
0x18001c3cc  mov     edx, 35h ; '5'; void *
0x18001c3d1  mov     [rsp+278h+var_258], rax; char *
0x18001c3d6  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18001c3db  mov     eax, ebx
0x18001c3dd  jmp     loc_18001C321
```
