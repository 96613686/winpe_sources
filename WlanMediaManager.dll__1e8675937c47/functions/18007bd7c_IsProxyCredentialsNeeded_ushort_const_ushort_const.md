# IsProxyCredentialsNeeded(ushort const *,ushort const *)

- ea: `0x18007bd7c`
- end: `0x18007be7c`
- name: `?IsProxyCredentialsNeeded@@YA_NPEBG0@Z`
- size: `256`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042a80`
- `0x180049180`
- `0x180065734`

## callees

- `0x18002a3c0`
- `0x18007bd7c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007be32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007be32`
- `WINHTTP!WinHttpCloseHandle` at `0x18007bdec`
- `WINHTTP!WinHttpCloseHandle` at `0x18007bdec`
- `WINHTTP!WinHttpProbeConnectivity` at `0x18007bde3`
- `WINHTTP!WinHttpProbeConnectivity` at `0x18007bde3`
- `WINHTTP!WinHttpOpen` at `0x18007bdaf`
- `WINHTTP!WinHttpOpen` at `0x18007bdaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IsProxyCredentialsNeeded(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v4; // bl
  void *v5; // rbp
  int v7; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v4 = 1;
  v7 = 1;
  v5 = WinHttpOpen(0, 4u, 0, 0, 0);
  if ( v5 )
  {
    WinHttpProbeConnectivity(v5, a1, a2, qword_1800B73A0, &dword_1800B7394, &v7);
    WinHttpCloseHandle(v5);
  }
  if ( !v7 )
  {
    if ( (!a1 || !*a1) && (!a2 || !*a2) )
      return 0;
    ppv = 0;
    if ( CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &ppv) >= 0 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 168LL))(ppv, 1);
    ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>((__int64 *)&ppv);
    if ( !v7 )
      return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18007bd7c  mov     rax, rsp
0x18007bd7f  mov     [rax+8], rbx
0x18007bd83  mov     [rax+10h], rbp
0x18007bd87  push    rsi
0x18007bd88  push    rdi
0x18007bd89  push    r14
0x18007bd8b  sub     rsp, 30h
0x18007bd8f  mov     rdi, rdx
0x18007bd92  mov     rsi, rcx
0x18007bd95  mov     ebx, 1
0x18007bd9a  mov     [rax+18h], ebx
0x18007bd9d  xor     r14d, r14d
0x18007bda0  mov     [rax-28h], r14d
0x18007bda4  xor     r9d, r9d; pszProxyBypassW
0x18007bda7  xor     r8d, r8d; pszProxyW
0x18007bdaa  lea     edx, [rbx+3]; dwAccessType
0x18007bdad  xor     ecx, ecx; pszAgentW
0x18007bdaf  call    cs:__imp_WinHttpOpen
0x18007bdb5  mov     rbp, rax
0x18007bdb8  test    rax, rax
0x18007bdbb  jz      short loc_18007BDF2
0x18007bdbd  lea     rax, [rsp+48h+arg_10]
0x18007bdc2  mov     [rsp+48h+var_20], rax
0x18007bdc7  lea     rax, dword_1800B7394
0x18007bdce  mov     [rsp+48h+ppv], rax
0x18007bdd3  lea     r9, qword_1800B73A0
0x18007bdda  mov     r8, rdi
0x18007bddd  mov     rdx, rsi
0x18007bde0  mov     rcx, rbp
0x18007bde3  call    cs:__imp_WinHttpProbeConnectivity
0x18007bde9  mov     rcx, rbp; hInternet
0x18007bdec  call    cs:__imp_WinHttpCloseHandle
0x18007bdf2  cmp     [rsp+48h+arg_10], r14d
0x18007bdf7  jnz     short loc_18007BE67
0x18007bdf9  test    rsi, rsi
0x18007bdfc  jz      short loc_18007BE04
0x18007bdfe  cmp     [rsi], r14w
0x18007be02  jnz     short loc_18007BE0F
0x18007be04  test    rdi, rdi
0x18007be07  jz      short loc_18007BE64
0x18007be09  cmp     [rdi], r14w
0x18007be0d  jz      short loc_18007BE64
0x18007be0f  mov     [rsp+48h+arg_18], r14
0x18007be14  lea     rax, [rsp+48h+arg_18]
0x18007be19  mov     [rsp+48h+ppv], rax; ppv
0x18007be1e  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18007be25  xor     edx, edx; pUnkOuter
0x18007be27  lea     r8d, [rdx+17h]; dwClsContext
0x18007be2b  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18007be32  call    cs:__imp_CoCreateInstance
0x18007be38  test    eax, eax
0x18007be3a  js      short loc_18007BE53
0x18007be3c  mov     rcx, [rsp+48h+arg_18]
0x18007be41  mov     rax, [rcx]
0x18007be44  mov     edx, ebx
0x18007be46  mov     rax, [rax+0A8h]
0x18007be4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be52  nop
0x18007be53  lea     rcx, [rsp+48h+arg_18]
0x18007be58  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18007be5d  cmp     [rsp+48h+arg_10], r14d
0x18007be62  jnz     short loc_18007BE67
0x18007be64  mov     bl, r14b
0x18007be67  mov     al, bl
0x18007be69  mov     rbx, [rsp+48h+arg_0]
0x18007be6e  mov     rbp, [rsp+48h+arg_8]
0x18007be73  add     rsp, 30h
0x18007be77  pop     r14
0x18007be79  pop     rdi
0x18007be7a  pop     rsi
0x18007be7b  retn
```
