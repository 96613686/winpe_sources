# CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)

- ea: `0x18000f9d0`
- end: `0x18000fb3d`
- name: `?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z`
- size: `365`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f5c8`
- `0x18001764c`

## callees

- `0x18000f9d0`
- `0x1800104b0`
- `0x1800458c4`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18000fb07`
- `bcrypt!BCryptFinishHash` at `0x18000fb07`
- `bcrypt!BCryptHashData` at `0x18000fa82`
- `bcrypt!BCryptHashData` at `0x18000fa82`
- `bcrypt!BCryptGetProperty` at `0x18000fa25`
- `bcrypt!BCryptGetProperty` at `0x18000faaf`
- `bcrypt!BCryptGetProperty` at `0x18000fa25`
- `bcrypt!BCryptGetProperty` at `0x18000faaf`
- `bcrypt!BCryptCreateHash` at `0x18000fa69`
- `bcrypt!BCryptCreateHash` at `0x18000fa69`
- `bcrypt!BCryptDestroyHash` at `0x18000fac4`
- `bcrypt!BCryptDestroyHash` at `0x18000fac4`

## pseudocode

```c
__int64 __fastcall CameraGenerateDWORD64HashWithHandle(
        PUCHAR pbInput,
        ULONG cbInput,
        BCRYPT_HANDLE hObject,
        unsigned __int64 *a4)
{
  UCHAR *v5; // rdi
  UCHAR *Pool; // rsi
  bool v10; // cl
  NTSTATUS Property; // ebx
  unsigned int v12; // r8d
  bool v13; // cl
  unsigned int v14; // r8d
  UCHAR *v16; // rax
  UCHAR v17[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-18h]
  ULONG pbOutput; // [rsp+C8h] [rbp+60h] BYREF

  v5 = 0;
  *a4 = 0;
  phHash = 0;
  Pool = 0;
  pbOutput = 0;
  *(_DWORD *)v17 = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    Pool = (UCHAR *)CameraHashingUtilsAllocatePoolEx(v10, pbOutput, v12);
    if ( !Pool )
    {
LABEL_3:
      Property = -1073741670;
      goto LABEL_7;
    }
    Property = BCryptCreateHash(hObject, &phHash, Pool, pbOutput, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(hObject, L"HashDigestLength", v17, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          v16 = (UCHAR *)CameraHashingUtilsAllocatePoolEx(v13, *(unsigned int *)v17, v14);
          v5 = v16;
          if ( !v16 )
            goto LABEL_3;
          Property = BCryptFinishHash(phHash, v16, *(ULONG *)v17, 0);
          if ( Property >= 0 )
          {
            LODWORD(v20) = *((_DWORD *)v5 + 1);
            HIDWORD(v20) = *(_DWORD *)v5;
            *a4 = v20;
          }
        }
      }
    }
  }
LABEL_7:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Pool )
    free(Pool);
  if ( v5 )
    free(v5);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18000f9d0  push    rbp
0x18000f9d2  push    rbx
0x18000f9d3  push    rsi
0x18000f9d4  push    rdi
0x18000f9d5  push    r12
0x18000f9d7  push    r13
0x18000f9d9  push    r14
0x18000f9db  push    r15
0x18000f9dd  mov     rbp, rsp
0x18000f9e0  sub     rsp, 68h
0x18000f9e4  xor     eax, eax
0x18000f9e6  mov     r14, r8
0x18000f9e9  mov     edi, eax
0x18000f9eb  mov     [r9], rax
0x18000f9ee  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18000f9f2  lea     r8, [rbp+pbOutput]; pbOutput
0x18000f9f6  mov     [rbp+phHash], rax
0x18000f9fa  mov     esi, eax
0x18000f9fc  mov     [rbp+pbOutput], eax
0x18000f9ff  mov     r15, r9
0x18000fa02  mov     dword ptr [rbp+var_28], eax
0x18000fa05  lea     r9d, [rdi+4]; cbOutput
0x18000fa09  mov     [rbp+var_24], eax
0x18000fa0c  mov     r12d, edx
0x18000fa0f  mov     r13, rcx
0x18000fa12  lea     rax, [rbp+var_24]
0x18000fa16  lea     rdx, aObjectlength; "ObjectLength"
0x18000fa1d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000fa22  mov     rcx, r14; hObject
0x18000fa25  call    cs:__imp_BCryptGetProperty
0x18000fa2b  mov     ebx, eax
0x18000fa2d  test    eax, eax
0x18000fa2f  js      loc_18000FABB
0x18000fa35  mov     edx, [rbp+pbOutput]; unsigned __int64
0x18000fa38  call    ?CameraHashingUtilsAllocatePoolEx@@YAPEAX_N_KK@Z; CameraHashingUtilsAllocatePoolEx(bool,unsigned __int64,ulong)
0x18000fa3d  mov     rsi, rax
0x18000fa40  xor     eax, eax
0x18000fa42  test    rsi, rsi
0x18000fa45  jnz     short loc_18000FA4E
0x18000fa47  mov     ebx, 0C000009Ah
0x18000fa4c  jmp     short loc_18000FABB
0x18000fa4e  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18000fa52  lea     rdx, [rbp+phHash]; phHash
0x18000fa56  mov     [rsp+68h+var_38], eax; dwFlags
0x18000fa5a  mov     r8, rsi; pbHashObject
0x18000fa5d  mov     [rsp+68h+dwFlags], eax; cbSecret
0x18000fa61  mov     rcx, r14; hAlgorithm
0x18000fa64  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18000fa69  call    cs:__imp_BCryptCreateHash
0x18000fa6f  mov     ebx, eax
0x18000fa71  test    eax, eax
0x18000fa73  js      short loc_18000FABB
0x18000fa75  mov     rcx, [rbp+phHash]; hHash
0x18000fa79  xor     r9d, r9d; dwFlags
0x18000fa7c  mov     r8d, r12d; cbInput
0x18000fa7f  mov     rdx, r13; pbInput
0x18000fa82  call    cs:__imp_BCryptHashData
0x18000fa88  mov     ebx, eax
0x18000fa8a  test    eax, eax
0x18000fa8c  js      short loc_18000FABB
0x18000fa8e  lea     rax, [rbp+var_24]
0x18000fa92  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18000fa96  mov     r9d, 4; cbOutput
0x18000fa9c  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000faa1  lea     r8, [rbp+var_28]; pbOutput
0x18000faa5  mov     rcx, r14; hObject
0x18000faa8  lea     rdx, pszProperty; "HashDigestLength"
0x18000faaf  call    cs:__imp_BCryptGetProperty
0x18000fab5  mov     ebx, eax
0x18000fab7  test    eax, eax
0x18000fab9  jns     short loc_18000FB27
0x18000fabb  mov     rcx, [rbp+phHash]; hHash
0x18000fabf  test    rcx, rcx
0x18000fac2  jz      short loc_18000FACA
0x18000fac4  call    cs:__imp_BCryptDestroyHash
0x18000faca  test    rsi, rsi
0x18000facd  jnz     short loc_18000FAEF
0x18000facf  test    rdi, rdi
0x18000fad2  jz      short loc_18000FADC
0x18000fad4  mov     rcx, rdi; Block
0x18000fad7  call    free
0x18000fadc  mov     eax, ebx
0x18000fade  add     rsp, 68h
0x18000fae2  pop     r15
0x18000fae4  pop     r14
0x18000fae6  pop     r13
0x18000fae8  pop     r12
0x18000faea  pop     rdi
0x18000faeb  pop     rsi
0x18000faec  pop     rbx
0x18000faed  pop     rbp
0x18000faee  retn
0x18000faef  mov     rcx, rsi; Block
0x18000faf2  call    free
0x18000faf7  jmp     short loc_18000FACF
0x18000faf9  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x18000fafd  xor     r9d, r9d; dwFlags
0x18000fb00  mov     rcx, [rbp+phHash]; hHash
0x18000fb04  mov     rdx, rdi; pbOutput
0x18000fb07  call    cs:__imp_BCryptFinishHash
0x18000fb0d  mov     ebx, eax
0x18000fb0f  test    eax, eax
0x18000fb11  js      short loc_18000FABB
0x18000fb13  mov     eax, [rdi+4]
0x18000fb16  mov     dword ptr [rbp+var_18], eax
0x18000fb19  mov     eax, [rdi]
0x18000fb1b  mov     dword ptr [rbp+var_18+4], eax
0x18000fb1e  mov     rax, [rbp+var_18]
0x18000fb22  mov     [r15], rax
0x18000fb25  jmp     short loc_18000FABB
0x18000fb27  mov     edx, dword ptr [rbp+var_28]; unsigned __int64
0x18000fb2a  call    ?CameraHashingUtilsAllocatePoolEx@@YAPEAX_N_KK@Z; CameraHashingUtilsAllocatePoolEx(bool,unsigned __int64,ulong)
0x18000fb2f  mov     rdi, rax
0x18000fb32  test    rax, rax
0x18000fb35  jz      loc_18000FA47
0x18000fb3b  jmp     short loc_18000FAF9
```
