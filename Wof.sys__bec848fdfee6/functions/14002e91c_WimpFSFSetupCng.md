# WimpFSFSetupCng

- ea: `0x14002e91c`
- end: `0x14002ea34`
- name: `WimpFSFSetupCng`
- size: `280`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400298d0`

## callees

- `0x140029758`
- `0x14002e91c`

## import_xrefs

- `cng!BCryptCloseAlgorithmProvider` at `0x14002ea1e`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002ea1e`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002e967`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002e967`
- `cng!BCryptGetProperty` at `0x14002e9a3`
- `cng!BCryptGetProperty` at `0x14002e9db`
- `cng!BCryptGetProperty` at `0x14002e9a3`
- `cng!BCryptGetProperty` at `0x14002e9db`

## pseudocode

```c
__int64 WimpFSFSetupCng()
{
  int Property; // ebx
  BCRYPT_ALG_HANDLE v1; // r8
  ULONG pcbResult; // [rsp+50h] [rbp+18h] BYREF
  int pbOutput; // [rsp+58h] [rbp+20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp+28h] BYREF
  __int64 v6; // [rsp+68h] [rbp+30h] BYREF

  pcbResult = 0;
  phAlgorithm = 0;
  pbOutput = 0;
  v6 = 0;
  Property = WimpFSFGetCngExtensions();
  if ( Property < 0
    || (Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0x60u), Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0),
        Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"MultiObjectLength", (PUCHAR)&v6, 8u, &pcbResult, 0), Property < 0) )
  {
    v1 = phAlgorithm;
  }
  else
  {
    v1 = 0;
    g_WimIntegrityHashAlgorithmHandle = (__int64)phAlgorithm;
    phAlgorithm = 0;
    g_WimIntegrityMultiHashObjectLength = v6 + 4 * HIDWORD(v6);
  }
  if ( v1 )
    BCryptCloseAlgorithmProvider(v1, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14002e91c  push    rbp
0x14002e91e  push    rbx
0x14002e91f  mov     rbp, rsp
0x14002e922  sub     rsp, 38h
0x14002e926  mov     [rbp+arg_0], 0
0x14002e92d  mov     [rbp+phAlgorithm], 0
0x14002e935  mov     [rbp+pbOutput], 0
0x14002e93c  mov     [rbp+arg_18], 0
0x14002e944  call    WimpFSFGetCngExtensions
0x14002e949  mov     ebx, eax
0x14002e94b  test    eax, eax
0x14002e94d  js      loc_14002EA10
0x14002e953  mov     r9d, 60h ; '`'; dwFlags
0x14002e959  lea     rdx, pszAlgId; "SHA256"
0x14002e960  xor     r8d, r8d; pszImplementation
0x14002e963  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14002e967  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002e96e  nop     dword ptr [rax+rax+00h]
0x14002e973  mov     ebx, eax
0x14002e975  test    eax, eax
0x14002e977  js      loc_14002EA10
0x14002e97d  mov     rcx, [rbp+phAlgorithm]; hObject
0x14002e981  lea     rax, [rbp+arg_0]
0x14002e985  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002e98d  lea     r8, [rbp+pbOutput]; pbOutput
0x14002e991  mov     r9d, 4; cbOutput
0x14002e997  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14002e99c  lea     rdx, pszProperty; "HashDigestLength"
0x14002e9a3  call    cs:__imp_BCryptGetProperty
0x14002e9aa  nop     dword ptr [rax+rax+00h]
0x14002e9af  mov     ebx, eax
0x14002e9b1  test    eax, eax
0x14002e9b3  js      short loc_14002EA10
0x14002e9b5  mov     rcx, [rbp+phAlgorithm]; hObject
0x14002e9b9  lea     rax, [rbp+arg_0]
0x14002e9bd  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002e9c5  lea     r8, [rbp+arg_18]; pbOutput
0x14002e9c9  mov     r9d, 8; cbOutput
0x14002e9cf  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14002e9d4  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x14002e9db  call    cs:__imp_BCryptGetProperty
0x14002e9e2  nop     dword ptr [rax+rax+00h]
0x14002e9e7  mov     ebx, eax
0x14002e9e9  test    eax, eax
0x14002e9eb  js      short loc_14002EA10
0x14002e9ed  mov     rax, [rbp+phAlgorithm]
0x14002e9f1  xor     r8d, r8d
0x14002e9f4  mov     ecx, dword ptr [rbp+arg_18]
0x14002e9f7  mov     cs:g_WimIntegrityHashAlgorithmHandle, rax
0x14002e9fe  mov     eax, dword ptr [rbp+arg_18+4]
0x14002ea01  mov     [rbp+phAlgorithm], r8
0x14002ea05  lea     ecx, [rcx+rax*4]
0x14002ea08  mov     cs:g_WimIntegrityMultiHashObjectLength, ecx
0x14002ea0e  jmp     short loc_14002EA14
0x14002ea10  mov     r8, [rbp+phAlgorithm]
0x14002ea14  test    r8, r8
0x14002ea17  jz      short loc_14002EA2A
0x14002ea19  xor     edx, edx; dwFlags
0x14002ea1b  mov     rcx, r8; hAlgorithm
0x14002ea1e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002ea25  nop     dword ptr [rax+rax+00h]
0x14002ea2a  mov     eax, ebx
0x14002ea2c  add     rsp, 38h
0x14002ea30  pop     rbx
0x14002ea31  pop     rbp
0x14002ea32  retn
```
