# LocationRegistryHelper::GetDefaultLocationCurrentToastCount(ulong,ulong *)

- ea: `0x180060750`
- end: `0x18006091d`
- name: `?GetDefaultLocationCurrentToastCount@LocationRegistryHelper@@SAJKPEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800cd050`

## callees

- `0x180060750`
- `0x18008fa98`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180060828`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006083d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180060828`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006083d`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x180060884`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x180060884`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800607b7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800607b7`

## string_xrefs

- `0x1800607a9`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x180060857`: `SYSTEM\CurrentControlSet\Services\lfsvc\Migrated\`
- `0x1800608cb`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x1800608af`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x1800608bf`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`

## pseudocode

```c
__int64 __fastcall LocationRegistryHelper::GetDefaultLocationCurrentToastCount(__int64 a1, unsigned int *a2)
{
  unsigned int v3; // ebx
  int PersistedRegistryLocationW; // eax
  __int64 v5; // rdx
  int v6; // r8d
  int RegistryValueWithFallbackW; // eax
  wil::details *v9; // [rsp+28h] [rbp-240h]
  _WORD v11[256]; // [rsp+50h] [rbp-218h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(v11, 0, 0x1FEu);
  if ( !a2 )
    return (unsigned int)-2147467261;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"LfSvc",
                                 L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                 v11,
                                 510,
                                 0);
  v3 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v5 = -1;
    do
      ++v5;
    while ( v11[v5] );
    if ( (unsigned __int64)(v5 + 10) >= 0xFF )
    {
      v3 = -2147418113;
      LODWORD(v9) = -2147418113;
      wil::details::in1diag5::Return_HrMsg(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
        "CLocationPersistedRegPathHelper::GetPersistedRegPath",
        "E_UNEXPECTED",
        v9,
        (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
        (const char *)v5,
        9);
      return v3;
    }
    v6 = (unsigned __int16)v11[v5 - 1] - 92;
    if ( v11[v5 - 1] == 92 )
      v6 = (unsigned __int16)v11[v5];
    if ( v6 )
      _o_wcscat_s(v11, 255, L"\\");
    _o_wcscat_s(v11, 255, L"Migrated\\");
    goto LABEL_16;
  }
  if ( PersistedRegistryLocationW > 0 )
    v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_16:
    RegistryValueWithFallbackW = GetRegistryValueWithFallbackW(
                                   -2147483646,
                                   v11,
                                   -2147483646,
                                   L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Migrated\\",
                                   L"DefaultLocationCurrentToastCount",
                                   16,
                                   0,
                                   a2,
                                   4,
                                   0);
    v3 = RegistryValueWithFallbackW;
    if ( RegistryValueWithFallbackW == 2 )
    {
      *a2 = 0;
      return 1;
    }
    else if ( RegistryValueWithFallbackW > 0 )
    {
      return (unsigned __int16)RegistryValueWithFallbackW | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180060750  mov     [rsp+arg_0], rbx
0x180060755  mov     [rsp+arg_10], rsi
0x18006075a  push    rdi
0x18006075b  sub     rsp, 260h
0x180060762  mov     rax, cs:__security_cookie
0x180060769  xor     rax, rsp
0x18006076c  mov     [rsp+268h+var_18], rax
0x180060774  mov     rdi, rdx
0x180060777  lea     rcx, [rsp+268h+var_218]; void *
0x18006077c  mov     ebx, 1FEh
0x180060781  xor     edx, edx; Val
0x180060783  mov     r8d, ebx; Size
0x180060786  call    memset_0
0x18006078b  xor     esi, esi
0x18006078d  test    rdi, rdi
0x180060790  jnz     short loc_18006079C
0x180060792  mov     ebx, 80004003h
0x180060797  jmp     loc_1800608F6
0x18006079c  mov     r9d, ebx
0x18006079f  mov     [rsp+268h+var_248], rsi
0x1800607a4  lea     r8, [rsp+268h+var_218]
0x1800607a9  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x1800607b0  lea     rcx, aLfsvc_1; "LfSvc"
0x1800607b7  call    cs:__imp_GetPersistedRegistryLocationW
0x1800607bd  mov     ebx, eax
0x1800607bf  test    eax, eax
0x1800607c1  jz      short loc_1800607D8
0x1800607c3  jle     short loc_1800607CE
0x1800607c5  movzx   ebx, ax
0x1800607c8  or      ebx, 80070000h
0x1800607ce  test    ebx, ebx
0x1800607d0  js      loc_1800608F6
0x1800607d6  jmp     short loc_180060843
0x1800607d8  lea     rax, [rsp+268h+var_218]
0x1800607dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800607e1  inc     rdx
0x1800607e4  cmp     [rax+rdx*2], si
0x1800607e8  jnz     short loc_1800607E1
0x1800607ea  lea     rax, [rdx+0Ah]
0x1800607ee  mov     ebx, 0FFh
0x1800607f3  cmp     rax, rbx
0x1800607f6  jnb     loc_1800608A7
0x1800607fc  movzx   r8d, [rsp+rdx*2+268h+var_21A]
0x180060802  sub     r8d, 5Ch ; '\'
0x180060806  jnz     short loc_180060814
0x180060808  movzx   r8d, [rsp+rdx*2+268h+var_218]
0x18006080e  movzx   ecx, si
0x180060811  sub     r8d, ecx
0x180060814  test    r8d, r8d
0x180060817  jz      short loc_18006082E
0x180060819  lea     r8, asc_18016EDDC; "\\"
0x180060820  mov     rdx, rbx
0x180060823  lea     rcx, [rsp+268h+var_218]
0x180060828  call    cs:__imp__o_wcscat_s
0x18006082e  lea     r8, aMigrated; "Migrated\\"
0x180060835  mov     rdx, rbx
0x180060838  lea     rcx, [rsp+268h+var_218]
0x18006083d  call    cs:__imp__o_wcscat_s
0x180060843  mov     [rsp+48h], rsi
0x180060848  lea     rax, aDefaultlocatio; "DefaultLocationCurrentToastCount"
0x18006084f  mov     dword ptr [rsp+268h+var_228], 4
0x180060857  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18006085e  mov     [rsp+268h+var_230], rdi
0x180060863  lea     rdx, [rsp+268h+var_218]
0x180060868  mov     rcx, 0FFFFFFFF80000002h
0x18006086f  mov     [rsp+268h+var_238], rsi
0x180060874  mov     dword ptr [rsp+268h+var_240], 10h
0x18006087c  mov     r8, rcx
0x18006087f  mov     [rsp+268h+var_248], rax
0x180060884  call    cs:__imp_GetRegistryValueWithFallbackW
0x18006088a  mov     ebx, eax
0x18006088c  cmp     eax, 2
0x18006088f  jnz     short loc_180060898
0x180060891  mov     [rdi], esi
0x180060893  lea     ebx, [rax-1]
0x180060896  jmp     short loc_1800608F6
0x180060898  test    eax, eax
0x18006089a  jle     short loc_1800608F6
0x18006089c  movzx   ebx, ax
0x18006089f  or      ebx, 80070000h
0x1800608a5  jmp     short loc_1800608F6
0x1800608a7  mov     rcx, [rsp+268h]; this
0x1800608af  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x1800608b6  mov     [rsp+268h+var_228], 9
0x1800608bf  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x1800608c6  mov     [rsp+268h+var_230], rdx; char *
0x1800608cb  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1800608d2  mov     [rsp+268h+var_238], rax; __int64
0x1800608d7  mov     ebx, 8000FFFFh
0x1800608dc  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x1800608e3  mov     dword ptr [rsp+268h+var_240], ebx; wil::details *
0x1800608e7  mov     edx, 35h ; '5'; void *
0x1800608ec  mov     [rsp+268h+var_248], rax; char *
0x1800608f1  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x1800608f6  mov     eax, ebx
0x1800608f8  mov     rcx, [rsp+268h+var_18]
0x180060900  xor     rcx, rsp; StackCookie
0x180060903  call    __security_check_cookie
0x180060908  lea     r11, [rsp+268h+var_8]
0x180060910  mov     rbx, [r11+10h]
0x180060914  mov     rsi, [r11+20h]
0x180060918  mov     rsp, r11
0x18006091b  pop     rdi
0x18006091c  retn
```
