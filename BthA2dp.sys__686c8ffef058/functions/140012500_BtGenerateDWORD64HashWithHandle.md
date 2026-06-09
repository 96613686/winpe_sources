# BtGenerateDWORD64HashWithHandle

- ea: `0x140012500`
- end: `0x1400126a4`
- name: `BtGenerateDWORD64HashWithHandle`
- size: `420`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d83c`

## callees

- `0x140012500`
- `0x14004560c`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x140012670`
- `ntoskrnl!ExFreePool` at `0x140012684`
- `ntoskrnl!ExFreePool` at `0x140012670`
- `ntoskrnl!ExFreePool` at `0x140012684`
- `ksecdd!BCryptFinishHash` at `0x140012627`
- `ksecdd!BCryptFinishHash` at `0x140012627`
- `ksecdd!BCryptGetProperty` at `0x140012555`
- `ksecdd!BCryptGetProperty` at `0x1400125f0`
- `ksecdd!BCryptGetProperty` at `0x140012555`
- `ksecdd!BCryptGetProperty` at `0x1400125f0`
- `ksecdd!BCryptHashData` at `0x1400125bf`
- `ksecdd!BCryptHashData` at `0x1400125bf`
- `ksecdd!BCryptDestroyHash` at `0x140012654`
- `ksecdd!BCryptDestroyHash` at `0x140012654`
- `ksecdd!BCryptCreateHash` at `0x14001259c`
- `ksecdd!BCryptCreateHash` at `0x14001259c`

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
0x140012500  push    rbp
0x140012502  push    rbx
0x140012503  push    rsi
0x140012504  push    rdi
0x140012505  push    r12
0x140012507  push    r13
0x140012509  push    r14
0x14001250b  push    r15
0x14001250d  mov     rbp, rsp
0x140012510  sub     rsp, 68h
0x140012514  xor     eax, eax
0x140012516  mov     r14, r8
0x140012519  mov     edi, eax
0x14001251b  mov     [r9], rax
0x14001251e  mov     [rsp+68h+dwFlags], eax; dwFlags
0x140012522  lea     r8, [rbp+pbOutput]; pbOutput
0x140012526  mov     [rbp+phHash], rax
0x14001252a  mov     esi, eax
0x14001252c  mov     [rbp+pbOutput], eax
0x14001252f  mov     r15, r9
0x140012532  mov     dword ptr [rbp+var_28], eax
0x140012535  lea     r9d, [rdi+4]; cbOutput
0x140012539  mov     [rbp+var_24], eax
0x14001253c  mov     r12d, edx
0x14001253f  mov     r13, rcx
0x140012542  lea     rax, [rbp+var_24]
0x140012546  lea     rdx, pszProperty; "ObjectLength"
0x14001254d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140012552  mov     rcx, r14; hObject
0x140012555  call    cs:__imp_BCryptGetProperty
0x14001255c  nop     dword ptr [rax+rax+00h]
0x140012561  mov     ebx, eax
0x140012563  test    eax, eax
0x140012565  js      loc_14001264B
0x14001256b  mov     edx, [rbp+pbOutput]
0x14001256e  call    BthHashingLibAllocatePoolEx
0x140012573  mov     rsi, rax
0x140012576  xor     eax, eax
0x140012578  test    rsi, rsi
0x14001257b  jz      loc_140012612
0x140012581  mov     r9d, [rbp+pbOutput]; cbHashObject
0x140012585  lea     rdx, [rbp+phHash]; phHash
0x140012589  mov     [rsp+68h+var_38], eax; dwFlags
0x14001258d  mov     r8, rsi; pbHashObject
0x140012590  mov     [rsp+68h+dwFlags], eax; cbSecret
0x140012594  mov     rcx, r14; hAlgorithm
0x140012597  mov     [rsp+68h+pcbResult], rax; pbSecret
0x14001259c  call    cs:__imp_BCryptCreateHash
0x1400125a3  nop     dword ptr [rax+rax+00h]
0x1400125a8  mov     ebx, eax
0x1400125aa  test    eax, eax
0x1400125ac  js      loc_14001264B
0x1400125b2  mov     rcx, [rbp+phHash]; hHash
0x1400125b6  xor     r9d, r9d; dwFlags
0x1400125b9  mov     r8d, r12d; cbInput
0x1400125bc  mov     rdx, r13; pbInput
0x1400125bf  call    cs:__imp_BCryptHashData
0x1400125c6  nop     dword ptr [rax+rax+00h]
0x1400125cb  mov     ebx, eax
0x1400125cd  test    eax, eax
0x1400125cf  js      short loc_14001264B
0x1400125d1  lea     rax, [rbp+var_24]
0x1400125d5  mov     [rsp+68h+dwFlags], edi; dwFlags
0x1400125d9  lea     r9d, [rdi+4]; cbOutput
0x1400125dd  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1400125e2  lea     r8, [rbp+var_28]; pbOutput
0x1400125e6  mov     rcx, r14; hObject
0x1400125e9  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400125f0  call    cs:__imp_BCryptGetProperty
0x1400125f7  nop     dword ptr [rax+rax+00h]
0x1400125fc  mov     ebx, eax
0x1400125fe  test    eax, eax
0x140012600  js      short loc_14001264B
0x140012602  mov     edx, dword ptr [rbp+var_28]
0x140012605  call    BthHashingLibAllocatePoolEx
0x14001260a  mov     rdi, rax
0x14001260d  test    rax, rax
0x140012610  jnz     short loc_140012619
0x140012612  mov     ebx, 0C000009Ah
0x140012617  jmp     short loc_14001264B
0x140012619  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x14001261d  xor     r9d, r9d; dwFlags
0x140012620  mov     rcx, [rbp+phHash]; hHash
0x140012624  mov     rdx, rdi; pbOutput
0x140012627  call    cs:__imp_BCryptFinishHash
0x14001262e  nop     dword ptr [rax+rax+00h]
0x140012633  mov     ebx, eax
0x140012635  test    eax, eax
0x140012637  js      short loc_14001264B
0x140012639  mov     eax, [rdi+4]
0x14001263c  mov     dword ptr [rbp+var_18], eax
0x14001263f  mov     eax, [rdi]
0x140012641  mov     dword ptr [rbp+var_18+4], eax
0x140012644  mov     rax, [rbp+var_18]
0x140012648  mov     [r15], rax
0x14001264b  mov     rcx, [rbp+phHash]; hHash
0x14001264f  test    rcx, rcx
0x140012652  jz      short loc_140012668
0x140012654  call    cs:__imp_BCryptDestroyHash
0x14001265b  nop     dword ptr [rax+rax+00h]
0x140012660  mov     [rbp+phHash], 0
0x140012668  test    rsi, rsi
0x14001266b  jz      short loc_14001267C
0x14001266d  mov     rcx, rsi; P
0x140012670  call    cs:__imp_ExFreePool
0x140012677  nop     dword ptr [rax+rax+00h]
0x14001267c  test    rdi, rdi
0x14001267f  jz      short loc_140012690
0x140012681  mov     rcx, rdi; P
0x140012684  call    cs:__imp_ExFreePool
0x14001268b  nop     dword ptr [rax+rax+00h]
0x140012690  mov     eax, ebx
0x140012692  add     rsp, 68h
0x140012696  pop     r15
0x140012698  pop     r14
0x14001269a  pop     r13
0x14001269c  pop     r12
0x14001269e  pop     rdi
0x14001269f  pop     rsi
0x1400126a0  pop     rbx
0x1400126a1  pop     rbp
0x1400126a2  retn
```
