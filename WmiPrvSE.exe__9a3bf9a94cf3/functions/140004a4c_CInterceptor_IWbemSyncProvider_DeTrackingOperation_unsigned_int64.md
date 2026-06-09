# CInterceptor_IWbemSyncProvider::DeTrackingOperation(unsigned __int64)

- ea: `0x140004a4c`
- end: `0x140004cb9`
- name: `?DeTrackingOperation@CInterceptor_IWbemSyncProvider@@QEAAH_K@Z`
- size: `621`
- prototype: `int(CInterceptor_IWbemSyncProvider *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140004768`

## callees

- `0x140004a4c`
- `0x140020820`
- `0x140021970`
- `0x14002a6c8`
- `0x14002ba53`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x140004b48`
- `msvcrt!_ui64tow_s` at `0x140004bee`
- `msvcrt!_ui64tow_s` at `0x140004b48`
- `msvcrt!_ui64tow_s` at `0x140004bee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004c50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004c50`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140004c7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140004c7a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140004bcb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140004bcb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140004b95`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140004bb0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140004b95`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140004bb0`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140004b5e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140004b5e`
- `OLEAUT32!__imp_SysFreeString` at `0x140004adc`
- `OLEAUT32!__imp_SysFreeString` at `0x140004adc`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140004b15`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140004b15`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CInterceptor_IWbemSyncProvider::DeTrackingOperation(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int64 a2)
{
  char *v4; // rbx
  _QWORD *v5; // r11
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  LSTATUS ValueW; // edi
  HKEY v9; // rbx
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v14; // [rsp+58h] [rbp-A8h]
  wchar_t Buffer[32]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pvData[526]; // [rsp+A2h] [rbp-5Eh] BYREF

  phkResult = (HKEY)a2;
  v4 = (char *)this + 232;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 29) + 48LL))((char *)this + 232);
  bstrString = 0;
  if ( *((_QWORD *)this + 69)
    && !(unsigned int)WmiHashTable<unsigned __int64,unsigned short *,4>::Find(
                        *((_QWORD *)this + 69),
                        &phkResult,
                        &bstrString)
    && !(unsigned int)WmiHashTable<unsigned __int64,unsigned short *,4>::Delete(v5, &phkResult) )
  {
    SysFreeString(bstrString);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 56LL))(v4);
  phkResult = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 71);
  if ( v6 )
    v6 = *(const WCHAR **)v6;
  v7 = RegOpenKeyW(HKEY_LOCAL_MACHINE, v6, &phkResult);
  ValueW = v7;
  v9 = phkResult;
  v14 = phkResult;
  if ( *((_DWORD *)this + 144) )
  {
    if ( !v7 && !_ui64tow_s(a2, Buffer, 0x1Eu, 10) )
      ValueW = RegDeleteKeyValueW(phkResult, 0, Buffer);
    if ( *((_DWORD *)this + 146) && *((_DWORD *)this + 147) )
    {
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 2u, 0);
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 3u, 0);
      PerfSetULongLongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 4u, 0);
    }
  }
  else if ( !v7 && !_ui64tow_s(a2, Buffer, 0x1Eu, 10) )
  {
    LODWORD(bstrString) = 0;
    pcbData = 260;
    memset_0(pvData, 0, 0x103u);
    strcpy((char *)Data, "*");
    ValueW = RegGetValueW(phkResult, 0, Buffer, 2u, (LPDWORD)&bstrString, pvData, &pcbData);
    if ( !ValueW )
      ValueW = RegSetValueExW(phkResult, Buffer, 0, 1u, Data, 0x104u);
  }
  DLRegCloseKey(v9);
  return ValueW == 0;
}

```

## disassembly

```asm
0x140004a4c  mov     [rsp-8+arg_10], rbx
0x140004a51  mov     [rsp-8+arg_18], rsi
0x140004a56  push    rbp
0x140004a57  push    rdi
0x140004a58  push    r14
0x140004a5a  lea     rbp, [rsp-1C0h]
0x140004a62  sub     rsp, 2C0h
0x140004a69  mov     rax, cs:__security_cookie
0x140004a70  xor     rax, rsp
0x140004a73  mov     [rbp+1D0h+var_20], rax
0x140004a7a  mov     r14, rdx
0x140004a7d  mov     rsi, rcx
0x140004a80  mov     [rsp+2D0h+phkResult], rdx
0x140004a85  lea     rbx, [rcx+0E8h]
0x140004a8c  mov     rax, [rbx]
0x140004a8f  mov     rcx, rbx
0x140004a92  mov     rax, [rax+30h]
0x140004a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a9b  mov     [rsp+2D0h+bstrString], 0
0x140004aa4  mov     r11, [rsi+228h]
0x140004aab  test    r11, r11
0x140004aae  jz      short loc_140004AE2
0x140004ab0  lea     r8, [rsp+2D0h+bstrString]
0x140004ab5  lea     rdx, [rsp+2D0h+phkResult]
0x140004aba  mov     rcx, r11
0x140004abd  call    ?Find@?$WmiHashTable@_KPEAG$03@@QEAA?AW4WmiStatusCode@@AEB_KAEAPEAG@Z; WmiHashTable<unsigned __int64,ushort *,4>::Find(unsigned __int64 const &,ushort * &)
0x140004ac2  test    eax, eax
0x140004ac4  jnz     short loc_140004AE2
0x140004ac6  lea     rdx, [rsp+2D0h+phkResult]
0x140004acb  mov     rcx, r11
0x140004ace  call    ?Delete@?$WmiHashTable@_KPEAG$03@@QEAA?AW4WmiStatusCode@@AEB_K@Z; WmiHashTable<unsigned __int64,ushort *,4>::Delete(unsigned __int64 const &)
0x140004ad3  test    eax, eax
0x140004ad5  jnz     short loc_140004AE2
0x140004ad7  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x140004adc  call    cs:__imp_SysFreeString
0x140004ae2  mov     rax, [rbx]
0x140004ae5  mov     rcx, rbx
0x140004ae8  mov     rax, [rax+38h]
0x140004aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004af1  mov     [rsp+2D0h+phkResult], 0
0x140004afa  mov     rdx, [rsi+238h]
0x140004b01  test    rdx, rdx
0x140004b04  jz      short loc_140004B09
0x140004b06  mov     rdx, [rdx]; lpSubKey
0x140004b09  lea     r8, [rsp+2D0h+phkResult]; phkResult
0x140004b0e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004b15  call    cs:__imp_RegOpenKeyW
0x140004b1b  mov     edi, eax
0x140004b1d  mov     rbx, [rsp+2D0h+phkResult]
0x140004b22  mov     [rsp+2D0h+var_278], rbx
0x140004b27  cmp     dword ptr [rsi+240h], 0
0x140004b2e  jz      loc_140004BD6
0x140004b34  test    eax, eax
0x140004b36  jnz     short loc_140004B66
0x140004b38  lea     r9d, [rax+0Ah]; Radix
0x140004b3c  lea     r8d, [rax+1Eh]; BufferCount
0x140004b40  lea     rdx, [rsp+2D0h+Buffer]; Buffer
0x140004b45  mov     rcx, r14; Value
0x140004b48  call    cs:__imp__ui64tow_s
0x140004b4e  test    eax, eax
0x140004b50  jnz     short loc_140004B66
0x140004b52  lea     r8, [rsp+2D0h+Buffer]; lpValueName
0x140004b57  xor     edx, edx; lpSubKey
0x140004b59  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x140004b5e  call    cs:__imp_RegDeleteKeyValueW
0x140004b64  mov     edi, eax
0x140004b66  cmp     dword ptr [rsi+248h], 0
0x140004b6d  jz      loc_140004C82
0x140004b73  cmp     dword ptr [rsi+24Ch], 0
0x140004b7a  jz      loc_140004C82
0x140004b80  xor     r9d, r9d; Value
0x140004b83  lea     r8d, [r9+2]; CounterId
0x140004b87  mov     rdx, [rsi+220h]; Instance
0x140004b8e  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140004b95  call    cs:__imp_PerfSetULongCounterValue
0x140004b9b  xor     r9d, r9d; Value
0x140004b9e  lea     r8d, [r9+3]; CounterId
0x140004ba2  mov     rdx, [rsi+220h]; Instance
0x140004ba9  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140004bb0  call    cs:__imp_PerfSetULongCounterValue
0x140004bb6  xor     r9d, r9d; Value
0x140004bb9  lea     r8d, [r9+4]; CounterId
0x140004bbd  mov     rdx, [rsi+220h]; Instance
0x140004bc4  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140004bcb  call    cs:__imp_PerfSetULongLongCounterValue
0x140004bd1  jmp     loc_140004C82
0x140004bd6  test    eax, eax
0x140004bd8  jnz     loc_140004C82
0x140004bde  lea     r9d, [rax+0Ah]; Radix
0x140004be2  lea     r8d, [rax+1Eh]; BufferCount
0x140004be6  lea     rdx, [rsp+2D0h+Buffer]; Buffer
0x140004beb  mov     rcx, r14; Value
0x140004bee  call    cs:__imp__ui64tow_s
0x140004bf4  test    eax, eax
0x140004bf6  jnz     loc_140004C82
0x140004bfc  mov     dword ptr [rsp+2D0h+bstrString], eax
0x140004c00  mov     esi, 104h
0x140004c05  mov     [rsp+2D0h+var_280], esi
0x140004c09  xor     edx, edx; Val
0x140004c0b  lea     r8d, [rsi-1]; Size
0x140004c0f  lea     rcx, [rbp+1D0h+var_22E]; void *
0x140004c13  call    memset_0
0x140004c18  mov     eax, 2Ah ; '*'
0x140004c1d  mov     word ptr [rbp+1D0h+Data], ax
0x140004c21  lea     rax, [rsp+2D0h+var_280]
0x140004c26  mov     [rsp+2D0h+pcbData], rax; pcbData
0x140004c2b  lea     rax, [rbp+1D0h+var_22E]
0x140004c2f  mov     [rsp+2D0h+pvData], rax; pvData
0x140004c34  lea     rax, [rsp+2D0h+bstrString]
0x140004c39  mov     [rsp+2D0h+pdwType], rax; pdwType
0x140004c3e  mov     r9d, 2; dwFlags
0x140004c44  lea     r8, [rsp+2D0h+Buffer]; lpValue
0x140004c49  xor     edx, edx; lpSubKey
0x140004c4b  mov     rcx, [rsp+2D0h+phkResult]; hkey
0x140004c50  call    cs:__imp_RegGetValueW
0x140004c56  mov     edi, eax
0x140004c58  test    eax, eax
0x140004c5a  jnz     short loc_140004C82
0x140004c5c  mov     dword ptr [rsp+2D0h+pvData], esi; cbData
0x140004c60  lea     rax, [rbp+1D0h+Data]
0x140004c64  mov     [rsp+2D0h+pdwType], rax; lpData
0x140004c69  lea     r9d, [rdi+1]; dwType
0x140004c6d  xor     r8d, r8d; Reserved
0x140004c70  lea     rdx, [rsp+2D0h+Buffer]; lpValueName
0x140004c75  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x140004c7a  call    cs:__imp_RegSetValueExW
0x140004c80  mov     edi, eax
0x140004c82  mov     rcx, rbx
0x140004c85  call    DLRegCloseKey
0x140004c8a  nop
0x140004c8b  xor     eax, eax
0x140004c8d  test    edi, edi
0x140004c8f  setz    al
0x140004c92  mov     rcx, [rbp+1D0h+var_20]
0x140004c99  xor     rcx, rsp; StackCookie
0x140004c9c  call    __security_check_cookie
0x140004ca1  lea     r11, [rsp+2D0h+var_10]
0x140004ca9  mov     rbx, [r11+30h]
0x140004cad  mov     rsi, [r11+38h]
0x140004cb1  mov     rsp, r11
0x140004cb4  pop     r14
0x140004cb6  pop     rdi
0x140004cb7  pop     rbp
0x140004cb8  retn
```
