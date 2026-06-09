# CServiceModule::SetServiceStatusHelper(ulong)

- ea: `0x180014890`
- end: `0x180014a78`
- name: `?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z`
- size: `488`
- prototype: `void __fastcall(CServiceModule *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180012700`
- `0x18001fcbc`
- `0x180025bbc`

## callees

- `0x180014890`
- `0x18001bbe0`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800149ce`
- `ntdll!EtwEventWriteTransfer` at `0x1800149ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149fb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149df`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149df`

## string_xrefs

- `0x1800148d3`: `PENSERVICE_CServiceModule::SetServiceStatusHelper`
- `0x180014a08`: `PENSERVICE_CServiceModule::SetServiceStatusHelper`
- `0x180014a3e`: `PENSERVICE_CServiceModule::SetServiceStatusHelper`

## pseudocode

```c
void __fastcall CServiceModule::SetServiceStatusHelper(CServiceModule *this, int a2)
{
  SERVICE_STATUS_HANDLE v4; // rcx
  struct _GUID *v5; // rcx
  char LastError; // al
  _DWORD v7[2]; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v8[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v9; // [rsp+40h] [rbp-48h]
  __int16 *v10; // [rsp+48h] [rbp-40h] BYREF
  int v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+54h] [rbp-34h]
  char *v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+60h] [rbp-28h]
  int v15; // [rsp+64h] [rbp-24h]
  _DWORD *v16; // [rsp+68h] [rbp-20h]
  __int64 v17; // [rsp+70h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      95,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::SetServiceStatusHelper",
      a2);
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    v7[0] = a2;
    v16 = v7;
    v8[1] = 5;
    v10 = (__int16 *)off_1800411B0;
    v17 = 4;
    v8[0] = 184549376;
    v9 = 0x4000000;
    v11 = *(unsigned __int16 *)off_1800411B0;
    v13 = byte_180039789;
    v12 = 2;
    v14 = 69;
    v15 = 1;
    v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_1800411C8, v8, 0, 0, 3, &v10);
  }
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 1);
  *((_DWORD *)this + 5) = a2;
  if ( SetServiceStatus(v4, (LPSERVICE_STATUS)((char *)this + 16)) )
    goto LABEL_12;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control )
    return;
  if ( (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      96,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::SetServiceStatusHelper",
      LastError);
LABEL_12:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (struct _GUID *)&WPP_GLOBAL_Control && (v5[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v5[1].Data1,
      97,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::SetServiceStatusHelper");
}

```

## disassembly

```asm
0x180014890  mov     [rsp+arg_8], rbx
0x180014895  mov     [rsp+arg_10], rsi
0x18001489a  push    rdi
0x18001489b  sub     rsp, 80h
0x1800148a2  mov     rax, cs:__security_cookie
0x1800148a9  xor     rax, rsp
0x1800148ac  mov     [rsp+88h+var_10], rax
0x1800148b1  mov     ebx, edx
0x1800148b3  mov     rdi, rcx
0x1800148b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148bd  lea     rsi, WPP_GLOBAL_Control
0x1800148c4  cmp     rcx, rsi
0x1800148c7  jz      short loc_1800148EF
0x1800148c9  test    byte ptr [rcx+1Ch], 10h
0x1800148cd  jz      short loc_1800148EF
0x1800148cf  mov     rcx, [rcx+10h]
0x1800148d3  lea     r9, aPenserviceCser_7; "PENSERVICE_CServiceModule::SetServiceSt"...
0x1800148da  mov     edx, 5Fh ; '_'
0x1800148df  mov     [rsp+88h+var_68], ebx
0x1800148e3  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800148ea  call    WPP_SF_sd
0x1800148ef  mov     eax, cs:dword_1800411A8
0x1800148f5  cmp     eax, 5
0x1800148f8  jbe     loc_1800149D4
0x1800148fe  mov     rcx, cs:qword_1800411C0
0x180014905  mov     rax, cs:qword_1800411B8
0x18001490c  bt      rax, 1Ah
0x180014911  jnb     loc_1800149D4
0x180014917  mov     rax, rcx
0x18001491a  and     eax, 4000000h
0x18001491f  cmp     rax, rcx
0x180014922  jnz     loc_1800149D4
0x180014928  lea     rax, [rsp+88h+var_58]
0x18001492d  mov     [rsp+88h+var_58], ebx
0x180014931  mov     [rsp+88h+var_20], rax
0x180014936  lea     rcx, _TraceLoggingMetadata
0x18001493d  movzx   eax, cs:word_18003977F
0x180014944  lea     rdx, [rsp+88h+var_50]
0x180014949  mov     [rsp+88h+var_4C], eax
0x18001494d  xor     r9d, r9d
0x180014950  mov     rax, cs:off_1800411B0
0x180014957  xor     r8d, r8d
0x18001495a  mov     [rsp+88h+var_40], rax
0x18001495f  mov     [rsp+88h+var_18], 4
0x180014968  mov     [rsp+88h+var_50], 0B000000h
0x180014970  mov     [rsp+88h+var_48], 4000000h
0x180014979  movzx   eax, word ptr [rax]
0x18001497c  mov     [rsp+88h+var_38], eax
0x180014980  lea     rax, byte_180039789
0x180014987  mov     [rsp+88h+var_30], rax
0x18001498c  lea     rax, _TraceLoggingMetadataEnd
0x180014993  sub     eax, ecx
0x180014995  mov     [rsp+88h+var_34], 2
0x18001499d  mov     [rsp+88h+var_28], 45h ; 'E'
0x1800149a5  mov     [rsp+88h+var_24], 1
0x1800149ad  mov     [rsp+88h+var_54], eax
0x1800149b1  mov     eax, [rsp+88h+var_54]
0x1800149b5  mov     rcx, cs:qword_1800411C8
0x1800149bc  lea     rax, [rsp+88h+var_40]
0x1800149c1  mov     [rsp+88h+var_60], rax
0x1800149c6  mov     [rsp+88h+var_68], 3
0x1800149ce  call    cs:__imp_EtwEventWriteTransfer
0x1800149d4  mov     rcx, [rdi+8]; hServiceStatus
0x1800149d8  lea     rdx, [rdi+10h]; lpServiceStatus
0x1800149dc  mov     [rdx+4], ebx
0x1800149df  call    cs:__imp_SetServiceStatus
0x1800149e5  test    eax, eax
0x1800149e7  jnz     short loc_180014A28
0x1800149e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149f0  cmp     rcx, rsi
0x1800149f3  jz      short loc_180014A56
0x1800149f5  test    byte ptr [rcx+1Ch], 4
0x1800149f9  jz      short loc_180014A2F
0x1800149fb  call    cs:__imp_GetLastError
0x180014a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a08  lea     r9, aPenserviceCser_7; "PENSERVICE_CServiceModule::SetServiceSt"...
0x180014a0f  mov     edx, 60h ; '`'
0x180014a14  mov     [rsp+88h+var_68], eax
0x180014a18  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014a1f  mov     rcx, [rcx+10h]
0x180014a23  call    WPP_SF_sd
0x180014a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a2f  cmp     rcx, rsi
0x180014a32  jz      short loc_180014A56
0x180014a34  test    byte ptr [rcx+1Ch], 10h
0x180014a38  jz      short loc_180014A56
0x180014a3a  mov     rcx, [rcx+10h]
0x180014a3e  lea     r9, aPenserviceCser_7; "PENSERVICE_CServiceModule::SetServiceSt"...
0x180014a45  mov     edx, 61h ; 'a'
0x180014a4a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014a51  call    WPP_SF_s
0x180014a56  mov     rcx, [rsp+88h+var_10]
0x180014a5b  xor     rcx, rsp; StackCookie
0x180014a5e  call    __security_check_cookie
0x180014a63  lea     r11, [rsp+88h+var_8]
0x180014a6b  mov     rbx, [r11+18h]
0x180014a6f  mov     rsi, [r11+20h]
0x180014a73  mov     rsp, r11
0x180014a76  pop     rdi
0x180014a77  retn
```
