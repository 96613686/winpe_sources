# BtGenerateDWORD64HashWithHandle

- ea: `0x14015ef9c`
- end: `0x14015f140`
- name: `BtGenerateDWORD64HashWithHandle`
- size: `420`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14015ef1c`

## callees

- `0x14015ef9c`
- `0x14015f148`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14015f10c`
- `ntoskrnl!ExFreePool` at `0x14015f120`
- `ntoskrnl!ExFreePool` at `0x14015f10c`
- `ntoskrnl!ExFreePool` at `0x14015f120`
- `ksecdd!BCryptGetProperty` at `0x14015eff1`
- `ksecdd!BCryptGetProperty` at `0x14015f08c`
- `ksecdd!BCryptGetProperty` at `0x14015eff1`
- `ksecdd!BCryptGetProperty` at `0x14015f08c`
- `ksecdd!BCryptCreateHash` at `0x14015f038`
- `ksecdd!BCryptCreateHash` at `0x14015f038`
- `ksecdd!BCryptHashData` at `0x14015f05b`
- `ksecdd!BCryptHashData` at `0x14015f05b`
- `ksecdd!BCryptFinishHash` at `0x14015f0c3`
- `ksecdd!BCryptFinishHash` at `0x14015f0c3`
- `ksecdd!BCryptDestroyHash` at `0x14015f0f0`
- `ksecdd!BCryptDestroyHash` at `0x14015f0f0`

## pseudocode

```c
__int64 __fastcall BtGenerateDWORD64HashWithHandle(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject, _QWORD *a4)
{
  UCHAR *v5; // rdi
  UCHAR *Pool; // rsi
  __int64 v10; // rcx
  NTSTATUS Property; // ebx
  __int64 v12; // rcx
  UCHAR *v13; // rax
  UCHAR v15[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-18h]
  ULONG pbOutput; // [rsp+C8h] [rbp+60h] BYREF

  v5 = 0;
  *a4 = 0;
  phHash = 0;
  Pool = 0;
  pbOutput = 0;
  *(_DWORD *)v15 = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    Pool = (UCHAR *)BthHashingLibAllocatePoolEx(v10, pbOutput);
    if ( !Pool )
    {
LABEL_7:
      Property = -1073741670;
      goto LABEL_10;
    }
    Property = BCryptCreateHash(hObject, &phHash, Pool, pbOutput, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(hObject, L"HashDigestLength", v15, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          v13 = (UCHAR *)BthHashingLibAllocatePoolEx(v12, *(unsigned int *)v15);
          v5 = v13;
          if ( !v13 )
            goto LABEL_7;
          Property = BCryptFinishHash(phHash, v13, *(ULONG *)v15, 0);
          if ( Property >= 0 )
          {
            LODWORD(v18) = *((_DWORD *)v5 + 1);
            HIDWORD(v18) = *(_DWORD *)v5;
            *a4 = v18;
          }
        }
      }
    }
  }
LABEL_10:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( Pool )
    ExFreePool(Pool);
  if ( v5 )
    ExFreePool(v5);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14015ef9c  push    rbp
0x14015ef9e  push    rbx
0x14015ef9f  push    rsi
0x14015efa0  push    rdi
0x14015efa1  push    r12
0x14015efa3  push    r13
0x14015efa5  push    r14
0x14015efa7  push    r15
0x14015efa9  mov     rbp, rsp
0x14015efac  sub     rsp, 68h
0x14015efb0  xor     eax, eax
0x14015efb2  mov     r14, r8
0x14015efb5  mov     edi, eax
0x14015efb7  mov     [r9], rax
0x14015efba  mov     [rsp+68h+dwFlags], eax; dwFlags
0x14015efbe  lea     r8, [rbp+pbOutput]; pbOutput
0x14015efc2  mov     [rbp+phHash], rax
0x14015efc6  mov     esi, eax
0x14015efc8  mov     [rbp+pbOutput], eax
0x14015efcb  mov     r15, r9
0x14015efce  mov     dword ptr [rbp+var_28], eax
0x14015efd1  lea     r9d, [rdi+4]; cbOutput
0x14015efd5  mov     [rbp+var_24], eax
0x14015efd8  mov     r12d, edx
0x14015efdb  mov     r13, rcx
0x14015efde  lea     rax, [rbp+var_24]
0x14015efe2  lea     rdx, pszProperty; "ObjectLength"
0x14015efe9  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14015efee  mov     rcx, r14; hObject
0x14015eff1  call    cs:__imp_BCryptGetProperty
0x14015eff8  nop     dword ptr [rax+rax+00h]
0x14015effd  mov     ebx, eax
0x14015efff  test    eax, eax
0x14015f001  js      loc_14015F0E7
0x14015f007  mov     edx, [rbp+pbOutput]
0x14015f00a  call    BthHashingLibAllocatePoolEx
0x14015f00f  mov     rsi, rax
0x14015f012  xor     eax, eax
0x14015f014  test    rsi, rsi
0x14015f017  jz      loc_14015F0AE
0x14015f01d  mov     r9d, [rbp+pbOutput]; cbHashObject
0x14015f021  lea     rdx, [rbp+phHash]; phHash
0x14015f025  mov     [rsp+68h+var_38], eax; dwFlags
0x14015f029  mov     r8, rsi; pbHashObject
0x14015f02c  mov     [rsp+68h+dwFlags], eax; cbSecret
0x14015f030  mov     rcx, r14; hAlgorithm
0x14015f033  mov     [rsp+68h+pcbResult], rax; pbSecret
0x14015f038  call    cs:__imp_BCryptCreateHash
0x14015f03f  nop     dword ptr [rax+rax+00h]
0x14015f044  mov     ebx, eax
0x14015f046  test    eax, eax
0x14015f048  js      loc_14015F0E7
0x14015f04e  mov     rcx, [rbp+phHash]; hHash
0x14015f052  xor     r9d, r9d; dwFlags
0x14015f055  mov     r8d, r12d; cbInput
0x14015f058  mov     rdx, r13; pbInput
0x14015f05b  call    cs:__imp_BCryptHashData
0x14015f062  nop     dword ptr [rax+rax+00h]
0x14015f067  mov     ebx, eax
0x14015f069  test    eax, eax
0x14015f06b  js      short loc_14015F0E7
0x14015f06d  lea     rax, [rbp+var_24]
0x14015f071  mov     [rsp+68h+dwFlags], edi; dwFlags
0x14015f075  lea     r9d, [rdi+4]; cbOutput
0x14015f079  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14015f07e  lea     r8, [rbp+var_28]; pbOutput
0x14015f082  mov     rcx, r14; hObject
0x14015f085  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14015f08c  call    cs:__imp_BCryptGetProperty
0x14015f093  nop     dword ptr [rax+rax+00h]
0x14015f098  mov     ebx, eax
0x14015f09a  test    eax, eax
0x14015f09c  js      short loc_14015F0E7
0x14015f09e  mov     edx, dword ptr [rbp+var_28]
0x14015f0a1  call    BthHashingLibAllocatePoolEx
0x14015f0a6  mov     rdi, rax
0x14015f0a9  test    rax, rax
0x14015f0ac  jnz     short loc_14015F0B5
0x14015f0ae  mov     ebx, 0C000009Ah
0x14015f0b3  jmp     short loc_14015F0E7
0x14015f0b5  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x14015f0b9  xor     r9d, r9d; dwFlags
0x14015f0bc  mov     rcx, [rbp+phHash]; hHash
0x14015f0c0  mov     rdx, rdi; pbOutput
0x14015f0c3  call    cs:__imp_BCryptFinishHash
0x14015f0ca  nop     dword ptr [rax+rax+00h]
0x14015f0cf  mov     ebx, eax
0x14015f0d1  test    eax, eax
0x14015f0d3  js      short loc_14015F0E7
0x14015f0d5  mov     eax, [rdi+4]
0x14015f0d8  mov     dword ptr [rbp+var_18], eax
0x14015f0db  mov     eax, [rdi]
0x14015f0dd  mov     dword ptr [rbp+var_18+4], eax
0x14015f0e0  mov     rax, [rbp+var_18]
0x14015f0e4  mov     [r15], rax
0x14015f0e7  mov     rcx, [rbp+phHash]; hHash
0x14015f0eb  test    rcx, rcx
0x14015f0ee  jz      short loc_14015F104
0x14015f0f0  call    cs:__imp_BCryptDestroyHash
0x14015f0f7  nop     dword ptr [rax+rax+00h]
0x14015f0fc  mov     [rbp+phHash], 0
0x14015f104  test    rsi, rsi
0x14015f107  jz      short loc_14015F118
0x14015f109  mov     rcx, rsi; P
0x14015f10c  call    cs:__imp_ExFreePool
0x14015f113  nop     dword ptr [rax+rax+00h]
0x14015f118  test    rdi, rdi
0x14015f11b  jz      short loc_14015F12C
0x14015f11d  mov     rcx, rdi; P
0x14015f120  call    cs:__imp_ExFreePool
0x14015f127  nop     dword ptr [rax+rax+00h]
0x14015f12c  mov     eax, ebx
0x14015f12e  add     rsp, 68h
0x14015f132  pop     r15
0x14015f134  pop     r14
0x14015f136  pop     r13
0x14015f138  pop     r12
0x14015f13a  pop     rdi
0x14015f13b  pop     rsi
0x14015f13c  pop     rbx
0x14015f13d  pop     rbp
0x14015f13e  retn
```
