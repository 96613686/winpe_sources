# SCardAudit

- ea: `0x180022de0`
- end: `0x180022f12`
- name: `SCardAudit`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015540`
- `0x1800195c8`
- `0x18001e75c`
- `0x180022d44`
- `0x180022de0`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180022e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180022e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022e13`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180022e72`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180022e72`

## pseudocode

```c
__int64 __fastcall SCardAudit(SCARDCONTEXT a1, int a2)
{
  LONG IsValidContext; // eax
  HANDLE CurrentProcess; // r14
  DWORD ProcessId; // esi
  WCHAR *v6; // rax
  WCHAR *v7; // rbx
  __int64 v8; // rcx
  __int64 *v9; // rdx
  ulong v10; // eax
  ulong v12; // [rsp+20h] [rbp-48h]
  LONG pExceptionObject; // [rsp+24h] [rbp-44h] BYREF
  ulong v14; // [rsp+28h] [rbp-40h] BYREF
  ulong LastError; // [rsp+2Ch] [rbp-3Ch] BYREF
  ulong v16; // [rsp+30h] [rbp-38h] BYREF
  ulong v17; // [rsp+34h] [rbp-34h] BYREF
  WCHAR *v18; // [rsp+38h] [rbp-30h]
  DWORD dwSize; // [rsp+80h] [rbp+18h] BYREF

  v18 = 0;
  try
  {
    IsValidContext = SCardIsValidContext(a1);
    if ( IsValidContext )
    {
      pExceptionObject = IsValidContext;
      throw (ulong *)&pExceptionObject;
    }
    CurrentProcess = GetCurrentProcess();
    ProcessId = GetProcessId(CurrentProcess);
    dwSize = 261;
    v6 = (WCHAR *)AllocH(0x20Au);
    v7 = v6;
    v18 = v6;
    if ( !v6 )
    {
      v14 = -2146435066;
      throw &v14;
    }
    if ( !QueryFullProcessImageNameW(CurrentProcess, 0, v6, &dwSize) )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        v16 = -2146435068;
        throw &v16;
      }
      if ( (Microsoft_Windows_SmartCard_AuditEnableBits & 2) != 0 )
      {
        v9 = AUDIT_CHV_SUCCESS;
LABEL_15:
        v10 = McTemplateU0zq_EventWriteTransfer(v8, v9, v7, ProcessId);
LABEL_17:
        v12 = v10;
        goto LABEL_25;
      }
    }
    else if ( (Microsoft_Windows_SmartCard_AuditEnableBits & 1) != 0 )
    {
      v9 = AUDIT_CHV_FAILURE;
      goto LABEL_15;
    }
    v10 = 0;
    goto LABEL_17;
  }
  catch ( ulong v17 )
  {
    v12 = v17;
    v7 = v18;
  }
  catch ( ... )
  {
    v12 = -2146435068;
    v7 = v18;
  }
LABEL_25:
  if ( v7 )
    I_CidUtilFreeH(v7);
  return v12;
}

```

## disassembly

```asm
0x180022de0  push    rbx
0x180022de2  push    rsi
0x180022de3  push    rdi
0x180022de4  push    r14
0x180022de6  sub     rsp, 48h
0x180022dea  mov     edi, edx
0x180022dec  mov     [rsp+68h+var_30], 0
0x180022df5  call    SCardIsValidContext
0x180022dfa  test    eax, eax
0x180022dfc  jz      short loc_180022E13
0x180022dfe  mov     [rsp+68h+pExceptionObject], eax
0x180022e02  lea     rdx, _TI1K; pThrowInfo
0x180022e09  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180022e0e  call    _CxxThrowException_0
0x180022e13  call    cs:__imp_GetCurrentProcess
0x180022e19  mov     r14, rax
0x180022e1c  mov     rcx, rax; Process
0x180022e1f  call    cs:__imp_GetProcessId
0x180022e25  mov     esi, eax
0x180022e27  mov     [rsp+68h+dwSize], 105h
0x180022e32  mov     ecx, 20Ah; unsigned __int64
0x180022e37  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x180022e3c  mov     rbx, rax
0x180022e3f  mov     [rsp+68h+var_30], rax
0x180022e44  test    rax, rax
0x180022e47  jnz     short loc_180022E62
0x180022e49  mov     [rsp+68h+var_40], 80100006h
0x180022e51  lea     rdx, _TI1K; pThrowInfo
0x180022e58  lea     rcx, [rsp+68h+var_40]; pExceptionObject
0x180022e5d  call    _CxxThrowException_0
0x180022e62  lea     r9, [rsp+68h+dwSize]; lpdwSize
0x180022e6a  mov     r8, rbx; lpExeName
0x180022e6d  xor     edx, edx; dwFlags
0x180022e6f  mov     rcx, r14; hProcess
0x180022e72  call    cs:__imp_QueryFullProcessImageNameW
0x180022e78  test    eax, eax
0x180022e7a  jnz     short loc_180022E97
0x180022e7c  call    cs:__imp_GetLastError
0x180022e82  mov     [rsp+68h+var_3C], eax
0x180022e86  lea     rdx, _TI1K; pThrowInfo
0x180022e8d  lea     rcx, [rsp+68h+var_3C]; pExceptionObject
0x180022e92  call    _CxxThrowException_0
0x180022e97  test    edi, edi
0x180022e99  jz      short loc_180022ECB
0x180022e9b  cmp     edi, 1
0x180022e9e  jz      short loc_180022EB9
0x180022ea0  mov     [rsp+68h+var_38], 80100004h
0x180022ea8  lea     rdx, _TI1K; pThrowInfo
0x180022eaf  lea     rcx, [rsp+68h+var_38]; pExceptionObject
0x180022eb4  call    _CxxThrowException_0
0x180022eb9  test    cs:Microsoft_Windows_SmartCard_AuditEnableBits, 2
0x180022ec0  jz      short loc_180022EE8
0x180022ec2  lea     rdx, AUDIT_CHV_SUCCESS
0x180022ec9  jmp     short loc_180022EDB
0x180022ecb  test    cs:Microsoft_Windows_SmartCard_AuditEnableBits, 1
0x180022ed2  jz      short loc_180022EE8
0x180022ed4  lea     rdx, AUDIT_CHV_FAILURE
0x180022edb  mov     r8, rbx
0x180022ede  mov     r9d, esi
0x180022ee1  call    McTemplateU0zq_EventWriteTransfer
0x180022ee6  jmp     short loc_180022EEA
0x180022ee8  xor     eax, eax
0x180022eea  mov     [rsp+68h+var_48], eax
0x180022eee  jmp     short loc_180022EF7
0x180022ef0  jmp     short $+2
0x180022ef2  mov     rbx, [rsp+68h+var_30]
0x180022ef7  test    rbx, rbx
0x180022efa  jz      short loc_180022F04
0x180022efc  mov     rcx, rbx
0x180022eff  call    I_CidUtilFreeH
0x180022f04  mov     eax, [rsp+68h+var_48]
0x180022f08  add     rsp, 48h
0x180022f0c  pop     r14
0x180022f0e  pop     rdi
0x180022f0f  pop     rsi
0x180022f10  pop     rbx
0x180022f11  retn
```
