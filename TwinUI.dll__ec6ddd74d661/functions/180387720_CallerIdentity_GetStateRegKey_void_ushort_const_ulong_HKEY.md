# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180387720`
- end: `0x1803878e3`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `451`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801164c0`
- `0x18013f984`
- `0x1802cccd8`

## callees

- `0x18002fc18`
- `0x18006137c`
- `0x18006a240`
- `0x180387720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180387899`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180387899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18038780d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387848`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18038780d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180387794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803878c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180387794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803878c6`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180387754`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1803877d6`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180387754`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1803877d6`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetStateRegKey(
        CallerIdentity *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        HKEY *a4)
{
  REGSAM samDesired; // r12d
  int Error; // edi
  int v9; // edx
  int v10; // ecx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS Key; // eax
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  HKEY v16[3]; // [rsp+60h] [rbp-18h] BYREF
  int v17; // [rsp+C8h] [rbp+50h] BYREF

  *a4 = 0;
  samDesired = (unsigned int)a3;
  v17 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v17) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v17 )
    {
      CoTaskMemFree(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, v17);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, 0, &v17) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( a2 )
          {
            v16[0] = 0;
            v12 = RegOpenKeyExW(hKey, 0, 0, 0x2001Fu, v16);
            Error = v12;
            if ( v12 > 0 )
              Error = (unsigned __int16)v12 | 0x80070000;
            if ( Error >= 0 )
            {
              Key = RegCreateKeyExW(v16[0], a2, 0, 0, 0, samDesired, 0, a4, 0);
              Error = Key;
              if ( Key > 0 )
                Error = (unsigned __int16)Key | 0x80070000;
            }
            CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(v16);
          }
          else
          {
            v11 = RegOpenKeyExW(hKey, 0, 0, samDesired, a4);
            Error = v11;
            if ( v11 > 0 )
              Error = (unsigned __int16)v11 | 0x80070000;
          }
        }
        CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(&hKey);
      }
      CoTaskMemFree(0);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180387720  push    rbp
0x180387722  push    rsi
0x180387723  push    rdi
0x180387724  push    r12
0x180387726  push    r14
0x180387728  push    r15
0x18038772a  mov     rbp, rsp
0x18038772d  sub     rsp, 78h
0x180387731  mov     r15, r9
0x180387734  mov     qword ptr [r9], 0
0x18038773b  mov     r12d, r8d
0x18038773e  mov     [rbp+arg_18], 0
0x180387745  mov     r14, rdx
0x180387748  lea     r9, [rbp+arg_18]
0x18038774c  xor     r8d, r8d
0x18038774f  xor     edx, edx
0x180387751  mov     rsi, rcx
0x180387754  call    cs:__imp_GetSystemAppDataKey
0x18038775b  nop     dword ptr [rax+rax+00h]
0x180387760  test    eax, eax
0x180387762  jz      short loc_18038776E
0x180387764  mov     edi, 8000FFFFh
0x180387769  jmp     loc_1803878D2
0x18038776e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180387773  mov     edi, eax
0x180387775  cmp     eax, 8007007Ah
0x18038777a  jnz     loc_1803878D2
0x180387780  cmp     [rbp+arg_18], 0
0x180387784  jbe     loc_1803878D2
0x18038778a  xor     ecx, ecx; pv
0x18038778c  mov     [rbp+lpSubKey], 0
0x180387794  call    cs:__imp_CoTaskMemFree
0x18038779b  nop     dword ptr [rax+rax+00h]
0x1803877a0  mov     r9d, [rbp+arg_18]
0x1803877a4  lea     rax, [rbp+lpSubKey]
0x1803877a8  xor     r8d, r8d
0x1803877ab  mov     qword ptr [rsp+78h+samDesired], rax
0x1803877b0  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1803877b5  mov     edi, eax
0x1803877b7  test    eax, eax
0x1803877b9  js      loc_1803878C2
0x1803877bf  mov     r8, [rbp+lpSubKey]
0x1803877c3  lea     r9, [rbp+arg_18]
0x1803877c7  lea     rdx, [rbp+hKey]
0x1803877cb  mov     [rbp+hKey], 0
0x1803877d3  mov     rcx, rsi
0x1803877d6  call    cs:__imp_GetSystemAppDataKey
0x1803877dd  nop     dword ptr [rax+rax+00h]
0x1803877e2  test    eax, eax
0x1803877e4  jnz     short loc_1803877F5
0x1803877e6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1803877eb  mov     edi, eax
0x1803877ed  test    eax, eax
0x1803877ef  js      loc_1803878B9
0x1803877f5  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1803877f9  xor     r8d, r8d; ulOptions
0x1803877fc  mov     rcx, [rbp+hKey]; hKey
0x180387800  test    r14, r14
0x180387803  jnz     short loc_180387831
0x180387805  mov     r9d, r12d; samDesired
0x180387808  mov     [rsp+78h+phkResult], r15; phkResult
0x18038780d  call    cs:__imp_RegOpenKeyExW
0x180387814  nop     dword ptr [rax+rax+00h]
0x180387819  mov     edi, eax
0x18038781b  test    eax, eax
0x18038781d  jle     loc_1803878B9
0x180387823  movzx   edi, ax
0x180387826  or      edi, 80070000h
0x18038782c  jmp     loc_1803878B9
0x180387831  lea     rax, [rbp+var_18]
0x180387835  mov     [rbp+var_18], 0
0x18038783d  mov     r9d, 2001Fh; samDesired
0x180387843  mov     [rsp+78h+phkResult], rax; phkResult
0x180387848  call    cs:__imp_RegOpenKeyExW
0x18038784f  nop     dword ptr [rax+rax+00h]
0x180387854  mov     edi, eax
0x180387856  mov     esi, 80070000h
0x18038785b  test    eax, eax
0x18038785d  jle     short loc_180387864
0x18038785f  movzx   edi, ax
0x180387862  or      edi, esi
0x180387864  test    edi, edi
0x180387866  js      short loc_1803878B0
0x180387868  mov     rcx, [rbp+var_18]; hKey
0x18038786c  xor     r9d, r9d; lpClass
0x18038786f  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180387878  xor     r8d, r8d; Reserved
0x18038787b  mov     [rsp+78h+var_40], r15; phkResult
0x180387880  mov     rdx, r14; lpSubKey
0x180387883  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18038788c  mov     [rsp+78h+samDesired], r12d; samDesired
0x180387891  mov     dword ptr [rsp+78h+phkResult], 0; dwOptions
0x180387899  call    cs:__imp_RegCreateKeyExW
0x1803878a0  nop     dword ptr [rax+rax+00h]
0x1803878a5  mov     edi, eax
0x1803878a7  test    eax, eax
0x1803878a9  jle     short loc_1803878B0
0x1803878ab  movzx   edi, ax
0x1803878ae  or      edi, esi
0x1803878b0  lea     rcx, [rbp+var_18]
0x1803878b4  call    ??1?$CAutoHandle@PEAUHKEY__@@@@QEAA@XZ; CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(void)
0x1803878b9  lea     rcx, [rbp+hKey]
0x1803878bd  call    ??1?$CAutoHandle@PEAUHKEY__@@@@QEAA@XZ; CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(void)
0x1803878c2  mov     rcx, [rbp+lpSubKey]; pv
0x1803878c6  call    cs:__imp_CoTaskMemFree
0x1803878cd  nop     dword ptr [rax+rax+00h]
0x1803878d2  mov     eax, edi
0x1803878d4  add     rsp, 78h
0x1803878d8  pop     r15
0x1803878da  pop     r14
0x1803878dc  pop     r12
0x1803878de  pop     rdi
0x1803878df  pop     rsi
0x1803878e0  pop     rbp
0x1803878e1  retn
```
