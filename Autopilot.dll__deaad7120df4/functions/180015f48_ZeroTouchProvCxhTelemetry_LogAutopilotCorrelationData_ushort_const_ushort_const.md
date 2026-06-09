# ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(ushort const *,ushort const *)

- ea: `0x180015f48`
- end: `0x1800161c0`
- name: `?LogAutopilotCorrelationData@ZeroTouchProvCxhTelemetry@@SAXPEBG0@Z`
- size: `632`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800156c8`

## callees

- `0x180001640`
- `0x1800045d0`
- `0x180015cd4`
- `0x180015f48`
- `0x1800167d8`
- `0x18001785c`
- `0x1800179b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016117`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001618b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001618b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016157`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016157`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800160bd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800160bd`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(unsigned __int16 *a1, unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rbx
  __int64 v7; // rcx
  const unsigned __int16 *AutopilotCorrelationVector; // rax
  int *v9; // r9
  __int64 v10; // rcx
  int v11; // edx
  int *v12; // r10
  __int64 v13; // r8
  int v14; // r8d
  __int64 v15; // rdx
  int v16; // ecx
  char v17; // al
  char IsStateSeparationEnabled; // al
  const WCHAR *v19; // rsi
  LSTATUS v20; // eax
  bool v21; // sf
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  char *v24[4]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v25[32]; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v26; // [rsp+A0h] [rbp-19h]
  int v27; // [rsp+A8h] [rbp-11h]
  int v28; // [rsp+ACh] [rbp-Dh]
  int *v29; // [rsp+B0h] [rbp-9h]
  int v30; // [rsp+B8h] [rbp-1h]
  int v31; // [rsp+BCh] [rbp+3h]
  int *v32; // [rsp+C0h] [rbp+7h]
  int v33; // [rsp+C8h] [rbp+Fh]
  int v34; // [rsp+CCh] [rbp+13h]
  __int64 *v35; // [rsp+D0h] [rbp+17h]
  __int64 v36; // [rsp+D8h] [rbp+1Fh]

  v4 = ZeroTouchProvCxhTelemetry::Provider();
  v6 = v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 )
  {
    v5 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v4 + 2);
    if ( (v7 & 0x800000000000LL) != 0 )
    {
      v7 = v5 & 0x800000000000LL;
      if ( (v5 & 0x800000000000LL) == v5 )
      {
        v23 = 0x2000000;
        AutopilotCorrelationVector = (const unsigned __int16 *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector((__int64)v24);
        if ( *((_QWORD *)AutopilotCorrelationVector + 3) > 0xFu )
          AutopilotCorrelationVector = *(const unsigned __int16 **)AutopilotCorrelationVector;
        v36 = 8;
        v35 = &v23;
        v9 = &dword_180037114;
        v10 = -1;
        v11 = 2;
        if ( a2 )
        {
          v12 = (int *)a2;
          v13 = -1;
          do
            ++v13;
          while ( a2[v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          v12 = &dword_180037114;
          v14 = 2;
        }
        v32 = v12;
        v33 = v14;
        v34 = 0;
        if ( a1 )
        {
          v9 = (int *)a1;
          v15 = -1;
          do
            ++v15;
          while ( a1[v15] );
          v11 = 2 * v15 + 2;
        }
        v29 = v9;
        v30 = v11;
        v31 = 0;
        if ( AutopilotCorrelationVector )
        {
          do
            ++v10;
          while ( *((_BYTE *)AutopilotCorrelationVector + v10) );
          v16 = v10 + 1;
        }
        else
        {
          AutopilotCorrelationVector = &byte_180037110;
          v16 = 1;
        }
        v26 = AutopilotCorrelationVector;
        v27 = v16;
        v28 = 0;
        tlgWriteTransfer_EventWriteTransfer(v6, byte_18003B8C5, 0, 0, 6, v25);
        std::string::_Tidy_deallocate(v24);
      }
    }
  }
  hKey = 0;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v17 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v7, v5);
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    v17 = IsStateSeparationEnabled != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v17;
  }
  v19 = L"OSData\\Software\\Microsoft\\Provisioning\\Diagnostics\\Autopilot\\EstablishedCorrelations";
  if ( !v17 )
    v19 = L"Software\\Microsoft\\Provisioning\\Diagnostics\\Autopilot\\EstablishedCorrelations";
  hKey = 0;
  v20 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v21 = v20 < 0;
  if ( v20 > 0 )
    v21 = 1;
  if ( !v21 )
    anonymous_namespace_::WriteStringValue(&hKey, a1, a2);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180015f48  mov     [rsp-8+arg_10], rbx
0x180015f4d  mov     [rsp-8+arg_18], rsi
0x180015f52  push    rbp
0x180015f53  push    rdi
0x180015f54  push    r12
0x180015f56  push    r14
0x180015f58  push    r15
0x180015f5a  lea     rbp, [rsp-37h]
0x180015f5f  sub     rsp, 0F0h
0x180015f66  mov     rax, cs:__security_cookie
0x180015f6d  xor     rax, rsp
0x180015f70  mov     [rbp+57h+var_30], rax
0x180015f74  mov     r15, rdx
0x180015f77  mov     r14, rcx
0x180015f7a  xor     r12d, r12d
0x180015f7d  call    ?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ; ZeroTouchProvCxhTelemetry::Provider(void)
0x180015f82  mov     rbx, rax
0x180015f85  mov     ecx, [rax]
0x180015f87  cmp     ecx, 5
0x180015f8a  jbe     loc_1800160A5
0x180015f90  mov     rdx, [rax+18h]
0x180015f94  mov     rcx, [rax+10h]
0x180015f98  mov     rax, 800000000000h
0x180015fa2  test    rax, rcx
0x180015fa5  jz      loc_1800160A5
0x180015fab  mov     rcx, rdx
0x180015fae  and     rcx, rax
0x180015fb1  cmp     rcx, rdx
0x180015fb4  jnz     loc_1800160A5
0x180015fba  lea     rcx, [rbp+57h+var_B0]
0x180015fbe  mov     [rbp+57h+var_B8], 2000000h
0x180015fc6  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180015fcb  cmp     qword ptr [rax+18h], 0Fh
0x180015fd0  jbe     short loc_180015FD5
0x180015fd2  mov     rax, [rax]
0x180015fd5  lea     rcx, [rbp+57h+var_B8]
0x180015fd9  mov     [rbp+57h+var_38], 8
0x180015fe1  mov     [rbp+57h+var_40], rcx
0x180015fe5  lea     r9, dword_180037114
0x180015fec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015ff0  mov     edx, 2
0x180015ff5  test    r15, r15
0x180015ff8  jz      short loc_180016014
0x180015ffa  mov     r10, r15
0x180015ffd  mov     r8, rcx
0x180016000  inc     r8
0x180016003  cmp     [r15+r8*2], r12w
0x180016008  jnz     short loc_180016000
0x18001600a  lea     r8d, ds:2[r8*2]
0x180016012  jmp     short loc_18001601A
0x180016014  mov     r10, r9
0x180016017  mov     r8d, edx
0x18001601a  mov     [rbp+57h+var_50], r10
0x18001601e  mov     [rbp+57h+var_48], r8d
0x180016022  mov     [rbp+57h+var_44], r12d
0x180016026  test    r14, r14
0x180016029  jz      short loc_180016042
0x18001602b  mov     r9, r14
0x18001602e  mov     rdx, rcx
0x180016031  inc     rdx
0x180016034  cmp     [r14+rdx*2], r12w
0x180016039  jnz     short loc_180016031
0x18001603b  lea     edx, ds:2[rdx*2]
0x180016042  mov     [rbp+57h+var_60], r9
0x180016046  mov     [rbp+57h+var_58], edx
0x180016049  mov     [rbp+57h+var_54], r12d
0x18001604d  test    rax, rax
0x180016050  jz      short loc_18001605F
0x180016052  inc     rcx
0x180016055  cmp     [rax+rcx], r12b
0x180016059  jnz     short loc_180016052
0x18001605b  inc     ecx
0x18001605d  jmp     short loc_18001606B
0x18001605f  lea     rax, byte_180037110
0x180016066  mov     ecx, 1
0x18001606b  mov     [rbp+57h+var_70], rax
0x18001606f  lea     rdx, byte_18003B8C5
0x180016076  lea     rax, [rbp+57h+var_90]
0x18001607a  mov     [rbp+57h+var_68], ecx
0x18001607d  mov     qword ptr [rsp+110h+samDesired], rax
0x180016082  xor     r9d, r9d
0x180016085  xor     r8d, r8d
0x180016088  mov     [rsp+110h+dwOptions], 6
0x180016090  mov     rcx, rbx
0x180016093  mov     [rbp+57h+var_64], r12d
0x180016097  call    _tlgWriteTransfer_EventWriteTransfer
0x18001609c  lea     rcx, [rbp+57h+var_B0]
0x1800160a0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800160a5  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800160ac  mov     rdi, r12
0x1800160af  mov     [rbp+57h+hKey], r12
0x1800160b3  jz      short loc_1800160BD
0x1800160b5  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800160bb  jmp     short loc_1800160DF
0x1800160bd  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800160c4  nop     dword ptr [rax+rax+00h]
0x1800160c9  mov     rdi, [rbp+57h+hKey]
0x1800160cd  test    al, al
0x1800160cf  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800160d6  setnz   al
0x1800160d9  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800160df  test    al, al
0x1800160e1  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Diag"...
0x1800160e8  lea     rsi, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800160ef  cmovz   rsi, rcx
0x1800160f3  test    rdi, rdi
0x1800160f6  jz      short loc_180016123
0x1800160f8  call    cs:__imp_GetLastError
0x1800160ff  nop     dword ptr [rax+rax+00h]
0x180016104  mov     rcx, rdi; hKey
0x180016107  mov     ebx, eax
0x180016109  call    cs:__imp_RegCloseKey
0x180016110  nop     dword ptr [rax+rax+00h]
0x180016115  mov     ecx, ebx; dwErrCode
0x180016117  call    cs:__imp_SetLastError
0x18001611e  nop     dword ptr [rax+rax+00h]
0x180016123  mov     [rsp+110h+lpdwDisposition], r12; lpdwDisposition
0x180016128  lea     rax, [rbp+57h+hKey]
0x18001612c  mov     [rsp+110h+phkResult], rax; phkResult
0x180016131  xor     r9d, r9d; lpClass
0x180016134  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180016139  xor     r8d, r8d; Reserved
0x18001613c  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x180016144  mov     rdx, rsi; lpSubKey
0x180016147  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001614e  mov     [rsp+110h+dwOptions], r12d; dwOptions
0x180016153  mov     [rbp+57h+hKey], r12
0x180016157  call    cs:__imp_RegCreateKeyExW
0x18001615e  nop     dword ptr [rax+rax+00h]
0x180016163  test    eax, eax
0x180016165  jle     short loc_180016171
0x180016167  movzx   eax, ax
0x18001616a  or      eax, 80070000h
0x18001616f  test    eax, eax
0x180016171  js      short loc_180016182
0x180016173  mov     r8, r15
0x180016176  lea     rcx, [rbp+57h+hKey]
0x18001617a  mov     rdx, r14
0x18001617d  call    _anonymous_namespace___WriteStringValue
0x180016182  mov     rcx, [rbp+57h+hKey]; hKey
0x180016186  test    rcx, rcx
0x180016189  jz      short loc_180016197
0x18001618b  call    cs:__imp_RegCloseKey
0x180016192  nop     dword ptr [rax+rax+00h]
0x180016197  mov     rcx, [rbp+57h+var_30]
0x18001619b  xor     rcx, rsp; StackCookie
0x18001619e  call    __security_check_cookie
0x1800161a3  lea     r11, [rsp+110h+var_20]
0x1800161ab  mov     rbx, [r11+40h]
0x1800161af  mov     rsi, [r11+48h]
0x1800161b3  mov     rsp, r11
0x1800161b6  pop     r15
0x1800161b8  pop     r14
0x1800161ba  pop     r12
0x1800161bc  pop     rdi
0x1800161bd  pop     rbp
0x1800161be  retn
```
