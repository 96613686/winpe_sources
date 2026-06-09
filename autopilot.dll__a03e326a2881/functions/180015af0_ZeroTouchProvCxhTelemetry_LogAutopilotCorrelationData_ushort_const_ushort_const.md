# ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(ushort const *,ushort const *)

- ea: `0x180015af0`
- end: `0x180015d43`
- name: `?LogAutopilotCorrelationData@ZeroTouchProvCxhTelemetry@@SAXPEBG0@Z`
- size: `595`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800152c0`

## callees

- `0x18000163c`
- `0x1800045b0`
- `0x180015898`
- `0x180015af0`
- `0x180016344`
- `0x180017334`
- `0x180017488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ca5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ca5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015ce7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015ce7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015c65`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015c65`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(unsigned __int16 *a1, const BYTE *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rbx
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
  _BYTE v24[32]; // [rsp+60h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+80h] [rbp-39h] BYREF
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
  v6 = (__int64)v4;
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
        AutopilotCorrelationVector = (const unsigned __int16 *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v24);
        if ( *((_QWORD *)AutopilotCorrelationVector + 3) > 0xFu )
          AutopilotCorrelationVector = *(const unsigned __int16 **)AutopilotCorrelationVector;
        v36 = 8;
        v35 = &v23;
        v9 = &dword_1800360F4;
        v10 = -1;
        v11 = 2;
        if ( a2 )
        {
          v12 = (int *)a2;
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&a2[2 * v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          v12 = &dword_1800360F4;
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
          AutopilotCorrelationVector = &byte_1800360F0;
          v16 = 1;
        }
        v26 = AutopilotCorrelationVector;
        v27 = v16;
        v28 = 0;
        tlgWriteTransfer_EventWriteTransfer(v6, (unsigned __int8 *)byte_18003A8C5, 0, 0, 6u, &v25);
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
0x180015af0  mov     [rsp-8+arg_10], rbx
0x180015af5  mov     [rsp-8+arg_18], rsi
0x180015afa  push    rbp
0x180015afb  push    rdi
0x180015afc  push    r12
0x180015afe  push    r14
0x180015b00  push    r15
0x180015b02  lea     rbp, [rsp-37h]
0x180015b07  sub     rsp, 0F0h
0x180015b0e  mov     rax, cs:__security_cookie
0x180015b15  xor     rax, rsp
0x180015b18  mov     [rbp+57h+var_30], rax
0x180015b1c  mov     r15, rdx
0x180015b1f  mov     r14, rcx
0x180015b22  xor     r12d, r12d
0x180015b25  call    ?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ; ZeroTouchProvCxhTelemetry::Provider(void)
0x180015b2a  mov     rbx, rax
0x180015b2d  mov     ecx, [rax]
0x180015b2f  cmp     ecx, 5
0x180015b32  jbe     loc_180015C4D
0x180015b38  mov     rdx, [rax+18h]
0x180015b3c  mov     rcx, [rax+10h]
0x180015b40  mov     rax, 800000000000h
0x180015b4a  test    rax, rcx
0x180015b4d  jz      loc_180015C4D
0x180015b53  mov     rcx, rdx
0x180015b56  and     rcx, rax
0x180015b59  cmp     rcx, rdx
0x180015b5c  jnz     loc_180015C4D
0x180015b62  lea     rcx, [rbp+57h+var_B0]
0x180015b66  mov     [rbp+57h+var_B8], 2000000h
0x180015b6e  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180015b73  cmp     qword ptr [rax+18h], 0Fh
0x180015b78  jbe     short loc_180015B7D
0x180015b7a  mov     rax, [rax]
0x180015b7d  lea     rcx, [rbp+57h+var_B8]
0x180015b81  mov     [rbp+57h+var_38], 8
0x180015b89  mov     [rbp+57h+var_40], rcx
0x180015b8d  lea     r9, dword_1800360F4
0x180015b94  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015b98  mov     edx, 2
0x180015b9d  test    r15, r15
0x180015ba0  jz      short loc_180015BBC
0x180015ba2  mov     r10, r15
0x180015ba5  mov     r8, rcx
0x180015ba8  inc     r8
0x180015bab  cmp     [r15+r8*2], r12w
0x180015bb0  jnz     short loc_180015BA8
0x180015bb2  lea     r8d, ds:2[r8*2]
0x180015bba  jmp     short loc_180015BC2
0x180015bbc  mov     r10, r9
0x180015bbf  mov     r8d, edx
0x180015bc2  mov     [rbp+57h+var_50], r10
0x180015bc6  mov     [rbp+57h+var_48], r8d
0x180015bca  mov     [rbp+57h+var_44], r12d
0x180015bce  test    r14, r14
0x180015bd1  jz      short loc_180015BEA
0x180015bd3  mov     r9, r14
0x180015bd6  mov     rdx, rcx
0x180015bd9  inc     rdx
0x180015bdc  cmp     [r14+rdx*2], r12w
0x180015be1  jnz     short loc_180015BD9
0x180015be3  lea     edx, ds:2[rdx*2]
0x180015bea  mov     [rbp+57h+var_60], r9
0x180015bee  mov     [rbp+57h+var_58], edx
0x180015bf1  mov     [rbp+57h+var_54], r12d
0x180015bf5  test    rax, rax
0x180015bf8  jz      short loc_180015C07
0x180015bfa  inc     rcx
0x180015bfd  cmp     [rax+rcx], r12b
0x180015c01  jnz     short loc_180015BFA
0x180015c03  inc     ecx
0x180015c05  jmp     short loc_180015C13
0x180015c07  lea     rax, byte_1800360F0
0x180015c0e  mov     ecx, 1
0x180015c13  mov     [rbp+57h+var_70], rax
0x180015c17  lea     rdx, byte_18003A8C5
0x180015c1e  lea     rax, [rbp+57h+var_90]
0x180015c22  mov     [rbp+57h+var_68], ecx
0x180015c25  mov     qword ptr [rsp+110h+samDesired], rax
0x180015c2a  xor     r9d, r9d
0x180015c2d  xor     r8d, r8d
0x180015c30  mov     [rsp+110h+dwOptions], 6
0x180015c38  mov     rcx, rbx
0x180015c3b  mov     [rbp+57h+var_64], r12d
0x180015c3f  call    _tlgWriteTransfer_EventWriteTransfer
0x180015c44  lea     rcx, [rbp+57h+var_B0]
0x180015c48  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015c4d  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015c54  mov     rdi, r12
0x180015c57  mov     [rbp+57h+hKey], r12
0x180015c5b  jz      short loc_180015C65
0x180015c5d  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015c63  jmp     short loc_180015C81
0x180015c65  call    cs:__imp_RtlIsStateSeparationEnabled
0x180015c6b  mov     rdi, [rbp+57h+hKey]
0x180015c6f  test    al, al
0x180015c71  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015c78  setnz   al
0x180015c7b  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015c81  test    al, al
0x180015c83  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Diag"...
0x180015c8a  lea     rsi, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x180015c91  cmovz   rsi, rcx
0x180015c95  test    rdi, rdi
0x180015c98  jz      short loc_180015CB3
0x180015c9a  call    cs:__imp_GetLastError
0x180015ca0  mov     rcx, rdi; hKey
0x180015ca3  mov     ebx, eax
0x180015ca5  call    cs:__imp_RegCloseKey
0x180015cab  mov     ecx, ebx; dwErrCode
0x180015cad  call    cs:__imp_SetLastError
0x180015cb3  mov     [rsp+110h+lpdwDisposition], r12; lpdwDisposition
0x180015cb8  lea     rax, [rbp+57h+hKey]
0x180015cbc  mov     [rsp+110h+phkResult], rax; phkResult
0x180015cc1  xor     r9d, r9d; lpClass
0x180015cc4  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180015cc9  xor     r8d, r8d; Reserved
0x180015ccc  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x180015cd4  mov     rdx, rsi; lpSubKey
0x180015cd7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015cde  mov     [rsp+110h+dwOptions], r12d; dwOptions
0x180015ce3  mov     [rbp+57h+hKey], r12
0x180015ce7  call    cs:__imp_RegCreateKeyExW
0x180015ced  test    eax, eax
0x180015cef  jle     short loc_180015CFB
0x180015cf1  movzx   eax, ax
0x180015cf4  or      eax, 80070000h
0x180015cf9  test    eax, eax
0x180015cfb  js      short loc_180015D0C
0x180015cfd  mov     r8, r15
0x180015d00  lea     rcx, [rbp+57h+hKey]
0x180015d04  mov     rdx, r14
0x180015d07  call    _anonymous_namespace___WriteStringValue
0x180015d0c  mov     rcx, [rbp+57h+hKey]; hKey
0x180015d10  test    rcx, rcx
0x180015d13  jz      short loc_180015D1B
0x180015d15  call    cs:__imp_RegCloseKey
0x180015d1b  mov     rcx, [rbp+57h+var_30]
0x180015d1f  xor     rcx, rsp; StackCookie
0x180015d22  call    __security_check_cookie
0x180015d27  lea     r11, [rsp+110h+var_20]
0x180015d2f  mov     rbx, [r11+40h]
0x180015d33  mov     rsi, [r11+48h]
0x180015d37  mov     rsp, r11
0x180015d3a  pop     r15
0x180015d3c  pop     r14
0x180015d3e  pop     r12
0x180015d40  pop     rdi
0x180015d41  pop     rbp
0x180015d42  retn
```
