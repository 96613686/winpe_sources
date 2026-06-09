# GuidCreateFromInput(uchar const *,ulong,_GUID &)

- ea: `0x1800b6e3c`
- end: `0x1800b7103`
- name: `?GuidCreateFromInput@@YAKPEBEKAEAU_GUID@@@Z`
- size: `711`
- prototype: `unsigned int __fastcall(PUCHAR pbInput, ULONG cbInput, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b5a8`
- `0x1800863f8`

## callees

- `0x1800b6a40`
- `0x1800b6ac0`
- `0x1800b6e3c`
- `0x1800b710c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b6e99`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6efd`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6f6b`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6fc9`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7006`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7044`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6e99`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6efd`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6f6b`
- `ntdll!RtlNtStatusToDosError` at `0x1800b6fc9`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7006`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7044`
- `bcrypt!BCryptGetProperty` at `0x1800b6eee`
- `bcrypt!BCryptGetProperty` at `0x1800b6f5c`
- `bcrypt!BCryptGetProperty` at `0x1800b6eee`
- `bcrypt!BCryptGetProperty` at `0x1800b6f5c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6e8a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6e8a`
- `bcrypt!BCryptCreateHash` at `0x1800b6fba`
- `bcrypt!BCryptCreateHash` at `0x1800b6fba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b70cc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b70cc`
- `bcrypt!BCryptDestroyHash` at `0x1800b70b7`
- `bcrypt!BCryptDestroyHash` at `0x1800b70b7`
- `bcrypt!BCryptHashData` at `0x1800b6ff7`
- `bcrypt!BCryptHashData` at `0x1800b6ff7`
- `bcrypt!BCryptFinishHash` at `0x1800b7035`
- `bcrypt!BCryptFinishHash` at `0x1800b7035`

## pseudocode

```c
__int64 __fastcall GuidCreateFromInput(PUCHAR pbInput, ULONG cbInput, struct _GUID *a3)
{
  UCHAR *v6; // rsi
  __int64 v7; // rdi
  NTSTATUS v8; // eax
  NTSTATUS v9; // r14d
  ULONG v10; // eax
  int v11; // ecx
  int v12; // r8d
  unsigned int v13; // ebx
  __int64 *v14; // rdx
  NTSTATUS Property; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // edx
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // r8
  int v23; // eax
  __int16 v24; // r10
  unsigned __int8 v25; // r11
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  UCHAR v28[4]; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+C8h] [rbp+60h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v28 = 0;
  pcbResult = 0;
  v6 = 0;
  v7 = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = RtlNtStatusToDosError(v8);
    v13 = v10;
    if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) == 0 )
      goto LABEL_24;
    v14 = WwIntfUtils_c97;
    goto LABEL_4;
  }
  pcbResult = 4;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v9 = Property;
  if ( Property )
  {
    v10 = RtlNtStatusToDosError(Property);
    v13 = v10;
    if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
    {
      v14 = WwIntfUtils_c106;
LABEL_4:
      McTemplateU0sdq_EventWriteTransfer(v11, (_DWORD)v14, v12, v9, v10);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  v6 = (UCHAR *)WwanMemAlloc(*(unsigned int *)pbOutput);
  if ( !v6 )
  {
LABEL_9:
    v13 = 8;
    goto LABEL_24;
  }
  pcbResult = 4;
  v16 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v28, 4u, &pcbResult, 0);
  v9 = v16;
  if ( !v16 )
  {
    v7 = WwanMemAlloc(*(unsigned int *)v28);
    if ( v7 )
    {
      v17 = BCryptCreateHash(phAlgorithm, &phHash, v6, *(ULONG *)pbOutput, 0, 0, 0);
      v9 = v17;
      if ( v17 )
      {
        v10 = RtlNtStatusToDosError(v17);
        v13 = v10;
        if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
        {
          v14 = WwIntfUtils_c140;
          goto LABEL_4;
        }
      }
      else
      {
        v18 = BCryptHashData(phHash, pbInput, cbInput, 0);
        v9 = v18;
        if ( v18 )
        {
          v10 = RtlNtStatusToDosError(v18);
          v13 = v10;
          if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
          {
            v14 = WwIntfUtils_c149;
            goto LABEL_4;
          }
        }
        else
        {
          v19 = BCryptFinishHash(phHash, (PUCHAR)v7, *(ULONG *)v28, 0);
          v9 = v19;
          if ( v19 )
          {
            v10 = RtlNtStatusToDosError(v19);
            v13 = v10;
            if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
            {
              v14 = WwIntfUtils_c158;
              goto LABEL_4;
            }
          }
          else
          {
            v20 = *(_DWORD *)v7;
            v21 = *(_WORD *)(v7 + 6) & 0xFFF | 0x5000;
            v22 = *(_WORD *)(v7 + 4);
            v23 = *(_BYTE *)(v7 + 8) & 0x3F | 0x80;
            v24 = *(_WORD *)(v7 + 13);
            v13 = 0;
            v25 = *(_BYTE *)(v7 + 15);
            *(_DWORD *)&a3->Data4[1] = *(_DWORD *)(v7 + 9);
            a3->Data1 = v20;
            *(_WORD *)&a3->Data4[5] = v24;
            a3->Data4[0] = v23;
            a3->Data2 = v22;
            a3->Data3 = v21;
            a3->Data4[7] = v25;
          }
        }
      }
      goto LABEL_24;
    }
    goto LABEL_9;
  }
  v10 = RtlNtStatusToDosError(v16);
  v13 = v10;
  if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
  {
    v14 = WwIntfUtils_c123;
    goto LABEL_4;
  }
LABEL_24:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( v7 )
    WwanMemFree(v7);
  if ( v6 )
    WwanMemFree(v6);
  return v13;
}

```

## disassembly

```asm
0x1800b6e3c  push    rbp
0x1800b6e3e  push    rbx
0x1800b6e3f  push    rsi
0x1800b6e40  push    rdi
0x1800b6e41  push    r12
0x1800b6e43  push    r13
0x1800b6e45  push    r14
0x1800b6e47  push    r15
0x1800b6e49  mov     rbp, rsp
0x1800b6e4c  sub     rsp, 68h
0x1800b6e50  xor     r13d, r13d
0x1800b6e53  mov     r15, r8
0x1800b6e56  mov     ebx, edx
0x1800b6e58  mov     [rbp+phAlgorithm], r13
0x1800b6e5c  mov     r12, rcx
0x1800b6e5f  mov     [rbp+phHash], r13
0x1800b6e63  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800b6e6a  mov     dword ptr [rbp+pbOutput], r13d
0x1800b6e6e  lea     rdx, pszAlgId; "SHA1"
0x1800b6e75  mov     dword ptr [rbp+var_24], r13d
0x1800b6e79  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800b6e7d  mov     [rbp+arg_18], r13d
0x1800b6e81  xor     r9d, r9d; dwFlags
0x1800b6e84  mov     esi, r13d
0x1800b6e87  mov     edi, r13d
0x1800b6e8a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800b6e90  mov     r14d, eax
0x1800b6e93  test    eax, eax
0x1800b6e95  jz      short loc_1800B6EC6
0x1800b6e97  mov     ecx, eax; Status
0x1800b6e99  call    cs:__imp_RtlNtStatusToDosError
0x1800b6e9f  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b6ea6  mov     ebx, eax
0x1800b6ea8  jz      loc_1800B70AE
0x1800b6eae  lea     rdx, WwIntfUtils_c97
0x1800b6eb5  mov     r9d, r14d
0x1800b6eb8  mov     dword ptr [rsp+68h+pcbResult], eax
0x1800b6ebc  call    McTemplateU0sdq_EventWriteTransfer
0x1800b6ec1  jmp     loc_1800B70AE
0x1800b6ec6  mov     ecx, 4
0x1800b6ecb  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x1800b6ed0  mov     [rbp+arg_18], ecx
0x1800b6ed3  lea     rax, [rbp+arg_18]
0x1800b6ed7  mov     r9d, ecx; cbOutput
0x1800b6eda  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800b6edf  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b6ee3  lea     r8, [rbp+pbOutput]; pbOutput
0x1800b6ee7  lea     rdx, pszProperty; "ObjectLength"
0x1800b6eee  call    cs:__imp_BCryptGetProperty
0x1800b6ef4  mov     r14d, eax
0x1800b6ef7  test    eax, eax
0x1800b6ef9  jz      short loc_1800B6F1B
0x1800b6efb  mov     ecx, eax; Status
0x1800b6efd  call    cs:__imp_RtlNtStatusToDosError
0x1800b6f03  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b6f0a  mov     ebx, eax
0x1800b6f0c  jz      loc_1800B70AE
0x1800b6f12  lea     rdx, WwIntfUtils_c106
0x1800b6f19  jmp     short loc_1800B6EB5
0x1800b6f1b  mov     ecx, dword ptr [rbp+pbOutput]; Size
0x1800b6f1e  call    WwanMemAlloc
0x1800b6f23  mov     rsi, rax
0x1800b6f26  test    rax, rax
0x1800b6f29  jnz     short loc_1800B6F35
0x1800b6f2b  mov     ebx, 8
0x1800b6f30  jmp     loc_1800B70AE
0x1800b6f35  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b6f39  lea     rax, [rbp+arg_18]
0x1800b6f3d  mov     r9d, 4; cbOutput
0x1800b6f43  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x1800b6f48  lea     r8, [rbp+var_24]; pbOutput
0x1800b6f4c  mov     [rbp+arg_18], r9d
0x1800b6f50  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800b6f57  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800b6f5c  call    cs:__imp_BCryptGetProperty
0x1800b6f62  mov     r14d, eax
0x1800b6f65  test    eax, eax
0x1800b6f67  jz      short loc_1800B6F8C
0x1800b6f69  mov     ecx, eax; Status
0x1800b6f6b  call    cs:__imp_RtlNtStatusToDosError
0x1800b6f71  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b6f78  mov     ebx, eax
0x1800b6f7a  jz      loc_1800B70AE
0x1800b6f80  lea     rdx, WwIntfUtils_c123
0x1800b6f87  jmp     loc_1800B6EB5
0x1800b6f8c  mov     ecx, dword ptr [rbp+var_24]; Size
0x1800b6f8f  call    WwanMemAlloc
0x1800b6f94  mov     rdi, rax
0x1800b6f97  test    rax, rax
0x1800b6f9a  jz      short loc_1800B6F2B
0x1800b6f9c  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x1800b6fa0  lea     rdx, [rbp+phHash]; phHash
0x1800b6fa4  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b6fa8  mov     r8, rsi; pbHashObject
0x1800b6fab  mov     [rsp+68h+var_38], r13d; dwFlags
0x1800b6fb0  mov     [rsp+68h+dwFlags], r13d; cbSecret
0x1800b6fb5  mov     [rsp+68h+pcbResult], r13; pbSecret
0x1800b6fba  call    cs:__imp_BCryptCreateHash
0x1800b6fc0  mov     r14d, eax
0x1800b6fc3  test    eax, eax
0x1800b6fc5  jz      short loc_1800B6FEA
0x1800b6fc7  mov     ecx, eax; Status
0x1800b6fc9  call    cs:__imp_RtlNtStatusToDosError
0x1800b6fcf  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b6fd6  mov     ebx, eax
0x1800b6fd8  jz      loc_1800B70AE
0x1800b6fde  lea     rdx, WwIntfUtils_c140
0x1800b6fe5  jmp     loc_1800B6EB5
0x1800b6fea  mov     rcx, [rbp+phHash]; hHash
0x1800b6fee  xor     r9d, r9d; dwFlags
0x1800b6ff1  mov     r8d, ebx; cbInput
0x1800b6ff4  mov     rdx, r12; pbInput
0x1800b6ff7  call    cs:__imp_BCryptHashData
0x1800b6ffd  mov     r14d, eax
0x1800b7000  test    eax, eax
0x1800b7002  jz      short loc_1800B7027
0x1800b7004  mov     ecx, eax; Status
0x1800b7006  call    cs:__imp_RtlNtStatusToDosError
0x1800b700c  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b7013  mov     ebx, eax
0x1800b7015  jz      loc_1800B70AE
0x1800b701b  lea     rdx, WwIntfUtils_c149
0x1800b7022  jmp     loc_1800B6EB5
0x1800b7027  mov     r8d, dword ptr [rbp+var_24]; cbOutput
0x1800b702b  xor     r9d, r9d; dwFlags
0x1800b702e  mov     rcx, [rbp+phHash]; hHash
0x1800b7032  mov     rdx, rdi; pbOutput
0x1800b7035  call    cs:__imp_BCryptFinishHash
0x1800b703b  mov     r14d, eax
0x1800b703e  test    eax, eax
0x1800b7040  jz      short loc_1800B7061
0x1800b7042  mov     ecx, eax; Status
0x1800b7044  call    cs:__imp_RtlNtStatusToDosError
0x1800b704a  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x1800b7051  mov     ebx, eax
0x1800b7053  jz      short loc_1800B70AE
0x1800b7055  lea     rdx, WwIntfUtils_c158
0x1800b705c  jmp     loc_1800B6EB5
0x1800b7061  movzx   ecx, word ptr [rdi+6]
0x1800b7065  mov     eax, 0FFFh
0x1800b706a  mov     edx, [rdi]
0x1800b706c  and     cx, ax
0x1800b706f  mov     al, [rdi+8]
0x1800b7072  or      cx, 5000h
0x1800b7077  movzx   r8d, word ptr [rdi+4]
0x1800b707c  and     al, 3Fh
0x1800b707e  mov     r9d, [rdi+9]
0x1800b7082  or      al, 80h
0x1800b7084  movzx   r10d, word ptr [rdi+0Dh]
0x1800b7089  mov     ebx, r13d
0x1800b708c  mov     r11b, [rdi+0Fh]
0x1800b7090  mov     [r15+9], r9d
0x1800b7094  mov     [r15], edx
0x1800b7097  mov     [r15+0Dh], r10w
0x1800b709c  mov     [r15+8], al
0x1800b70a0  mov     [r15+4], r8w
0x1800b70a5  mov     [r15+6], cx
0x1800b70aa  mov     [r15+0Fh], r11b
0x1800b70ae  mov     rcx, [rbp+phHash]; hHash
0x1800b70b2  test    rcx, rcx
0x1800b70b5  jz      short loc_1800B70C1
0x1800b70b7  call    cs:__imp_BCryptDestroyHash
0x1800b70bd  mov     [rbp+phHash], r13
0x1800b70c1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b70c5  test    rcx, rcx
0x1800b70c8  jz      short loc_1800B70D6
0x1800b70ca  xor     edx, edx; dwFlags
0x1800b70cc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b70d2  mov     [rbp+phAlgorithm], r13
0x1800b70d6  test    rdi, rdi
0x1800b70d9  jz      short loc_1800B70E3
0x1800b70db  mov     rcx, rdi
0x1800b70de  call    WwanMemFree
0x1800b70e3  test    rsi, rsi
0x1800b70e6  jz      short loc_1800B70F0
0x1800b70e8  mov     rcx, rsi
0x1800b70eb  call    WwanMemFree
0x1800b70f0  mov     eax, ebx
0x1800b70f2  add     rsp, 68h
0x1800b70f6  pop     r15
0x1800b70f8  pop     r14
0x1800b70fa  pop     r13
0x1800b70fc  pop     r12
0x1800b70fe  pop     rdi
0x1800b70ff  pop     rsi
0x1800b7100  pop     rbx
0x1800b7101  pop     rbp
0x1800b7102  retn
```
