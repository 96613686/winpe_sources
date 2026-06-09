# WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(ushort const *,ushort const *,long)

- ea: `0x140011128`
- end: `0x14001123c`
- name: `?ReportRegUtilQueryValueFailed@TelemetryProvider@WaasMedic@@SAXPEBG0J@Z`
- size: `276`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1400104c0`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x14000885c`
- `0x14000b470`
- `0x140011128`

## string_xrefs

- `0x14001115f`: `RegUtil: Error when attempting to query %s registry value: %s. hr=0x%08X`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // r10
  __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 near **v10; // [rsp+60h] [rbp-19h]
  int v11; // [rsp+68h] [rbp-11h]
  int v12; // [rsp+6Ch] [rbp-Dh]
  const wchar_t *v13; // [rsp+70h] [rbp-9h]
  __int64 v14; // [rsp+78h] [rbp-1h]
  const WCHAR *v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  int *v17; // [rsp+90h] [rbp+17h]
  __int64 v18; // [rsp+98h] [rbp+1Fh]

  LogLevelW(
    2u,
    L"RegUtil: Error when attempting to query %s registry value: %s. hr=0x%08X",
    L"DWORD",
    L"WorkerDelay",
    a3);
  v4 = WaasMedic::TelemetryProvider::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x200000000000LL) == *((_QWORD *)v4 + 3) )
  {
    v8 = a3;
    v17 = &v8;
    v6 = -1;
    v18 = 4;
    v15 = L"WorkerDelay";
    v16 = 24;
    v13 = L"DWORD";
    v14 = 12;
    do
      ++v6;
    while ( *((_WORD *)&gc_pszVersionString + v6) );
    v10 = &gc_pszVersionString;
    v11 = 2 * v6 + 2;
    v12 = 0;
    tlgWriteTransfer_EventWriteTransfer(v5, &dword_14001A30C, 0, 0, 6, v9);
  }
}

```

## disassembly

```asm
0x140011128  push    rbp
0x14001112a  push    rbx
0x14001112b  push    rsi
0x14001112c  push    rdi
0x14001112d  lea     rbp, [rsp-3Fh]
0x140011132  sub     rsp, 0B8h
0x140011139  mov     rax, cs:__security_cookie
0x140011140  xor     rax, rsp
0x140011143  mov     [rbp+57h+var_30], rax
0x140011147  mov     ebx, r8d
0x14001114a  lea     rdi, ValueName; "WorkerDelay"
0x140011151  lea     rsi, aDword; "DWORD"
0x140011158  mov     [rsp+0D0h+var_B0], ebx
0x14001115c  mov     r9, rdi
0x14001115f  lea     rdx, aRegutilErrorWh; "RegUtil: Error when attempting to query"...
0x140011166  mov     r8, rsi
0x140011169  mov     ecx, 2; unsigned __int8
0x14001116e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140011173  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x140011178  mov     r10, rax
0x14001117b  mov     ecx, [rax]
0x14001117d  cmp     ecx, 5
0x140011180  jbe     loc_140011224
0x140011186  mov     rdx, [rax+18h]
0x14001118a  mov     rcx, [rax+10h]
0x14001118e  mov     rax, 200000000000h
0x140011198  test    rax, rcx
0x14001119b  jz      loc_140011224
0x1400111a1  mov     rcx, rdx
0x1400111a4  and     rcx, rax
0x1400111a7  cmp     rcx, rdx
0x1400111aa  jnz     short loc_140011224
0x1400111ac  lea     rax, [rbp+57h+var_A0]
0x1400111b0  mov     [rbp+57h+var_A0], ebx
0x1400111b3  xor     ecx, ecx
0x1400111b5  mov     [rbp+57h+var_40], rax
0x1400111b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400111bd  mov     [rbp+57h+var_38], 4
0x1400111c5  mov     [rbp+57h+var_50], rdi
0x1400111c9  lea     rdx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1400111d0  mov     [rbp+57h+var_48], 18h
0x1400111d8  mov     [rbp+57h+var_60], rsi
0x1400111dc  mov     [rbp+57h+var_58], 0Ch
0x1400111e4  inc     rax
0x1400111e7  cmp     [rdx+rax*2], cx
0x1400111eb  jnz     short loc_1400111E4
0x1400111ed  lea     eax, ds:2[rax*2]
0x1400111f4  mov     [rbp+57h+var_70], rdx
0x1400111f8  mov     [rbp+57h+var_68], eax
0x1400111fb  lea     rdx, dword_14001A30C
0x140011202  lea     rax, [rbp+57h+var_90]
0x140011206  mov     [rbp+57h+var_64], ecx
0x140011209  mov     [rsp+0D0h+var_A8], rax
0x14001120e  xor     r9d, r9d
0x140011211  xor     r8d, r8d
0x140011214  mov     [rsp+0D0h+var_B0], 6
0x14001121c  mov     rcx, r10
0x14001121f  call    _tlgWriteTransfer_EventWriteTransfer
0x140011224  mov     rcx, [rbp+57h+var_30]
0x140011228  xor     rcx, rsp; StackCookie
0x14001122b  call    __security_check_cookie
0x140011230  add     rsp, 0B8h
0x140011237  pop     rdi
0x140011238  pop     rsi
0x140011239  pop     rbx
0x14001123a  pop     rbp
0x14001123b  retn
```
