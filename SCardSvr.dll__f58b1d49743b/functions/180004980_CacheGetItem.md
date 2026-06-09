# CacheGetItem

- ea: `0x180004980`
- end: `0x180004af2`
- name: `CacheGetItem`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800029c8`

## callees

- `0x180004980`
- `0x1800058ec`
- `0x180032696`
- `0x1800326d0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180004a05`
- `bcrypt!BCryptHashData` at `0x180004a05`
- `bcrypt!BCryptDestroyHash` at `0x180004a16`
- `bcrypt!BCryptDestroyHash` at `0x180004a3d`
- `bcrypt!BCryptDestroyHash` at `0x180004a16`
- `bcrypt!BCryptDestroyHash` at `0x180004a3d`
- `bcrypt!BCryptFinishHash` at `0x180004a30`
- `bcrypt!BCryptFinishHash` at `0x180004a30`
- `bcrypt!BCryptCreateHash` at `0x1800049d0`
- `bcrypt!BCryptCreateHash` at `0x1800049d0`
- `ntdll!RtlNtStatusToDosError` at `0x180004ab9`
- `ntdll!RtlNtStatusToDosError` at `0x180004ab9`

## pseudocode

```c
__int64 __fastcall CacheGetItem(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  ULONG v10; // eax
  int v11; // ebx
  __int64 v12; // rbx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-58h] BYREF
  UCHAR pbOutput[32]; // [rsp+48h] [rbp-50h] BYREF

  hHash = 0;
  v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0);
  if ( v7 )
  {
    v10 = WIN32_FROM_NTSTATUS(v7);
  }
  else
  {
    v8 = 2;
    while ( v8 )
    {
      --v8;
      v9 = BCryptHashData(hHash, *(PUCHAR *)(a2 + 16LL * v8 + 8), *(_DWORD *)(a2 + 16LL * v8), 0);
      if ( v9 )
      {
        BCryptDestroyHash(hHash);
        v10 = WIN32_FROM_NTSTATUS(v9);
        goto LABEL_8;
      }
    }
    v11 = BCryptFinishHash(hHash, pbOutput, 0x20u, 0);
    BCryptDestroyHash(hHash);
    if ( v11 < 0 )
    {
      v10 = RtlNtStatusToDosError(v11);
      if ( v10 == 317 )
        v10 = v11;
    }
    else
    {
      v10 = 0;
    }
  }
LABEL_8:
  if ( v10 )
    return WIN32_FROM_NTSTATUS(v10);
  v12 = *(_QWORD *)(a1 + 8LL * (pbOutput[0] & 0xF));
  if ( !v12 )
    return 1168;
  while ( memcmp_0((const void *)(v12 + 24), pbOutput, 0x20u) )
  {
    v12 = *(_QWORD *)(v12 + 16);
    if ( !v12 )
      return 1168;
  }
  if ( !*(_QWORD *)(v12 + 8) || !*(_DWORD *)v12 )
    return 1168;
  *(_DWORD *)a4 = *(_DWORD *)v12;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)(v12 + 8);
  return 0;
}

```

## disassembly

```asm
0x180004980  mov     r11, rsp
0x180004983  push    rbx
0x180004984  push    rsi
0x180004985  push    r14
0x180004987  sub     rsp, 80h
0x18000498e  mov     rax, cs:__security_cookie
0x180004995  xor     rax, rsp
0x180004998  mov     [rsp+98h+var_30], rax
0x18000499d  mov     [r11+8], rbp
0x1800049a1  mov     r14, r9
0x1800049a4  mov     [r11-28h], r15
0x1800049a8  mov     rbp, rdx
0x1800049ab  xor     r15d, r15d
0x1800049ae  lea     rdx, [r11-58h]; phHash
0x1800049b2  mov     [r11-68h], r15d
0x1800049b6  mov     rsi, rcx
0x1800049b9  mov     [r11-70h], r15d
0x1800049bd  xor     r9d, r9d; cbHashObject
0x1800049c0  xor     r8d, r8d; pbHashObject
0x1800049c3  mov     [r11-78h], r15
0x1800049c7  mov     ecx, 41h ; 'A'; hAlgorithm
0x1800049cc  mov     [r11-58h], r15
0x1800049d0  call    cs:__imp_BCryptCreateHash
0x1800049d6  test    eax, eax
0x1800049d8  jnz     loc_180004AAE
0x1800049de  mov     ebx, 2
0x1800049e3  mov     [rsp+98h+var_20], rdi
0x1800049e8  mov     rcx, [rsp+98h+hHash]; hHash
0x1800049ed  xor     r9d, r9d; dwFlags
0x1800049f0  test    ebx, ebx
0x1800049f2  jz      short loc_180004A25
0x1800049f4  dec     ebx
0x1800049f6  mov     eax, ebx
0x1800049f8  add     rax, rax
0x1800049fb  mov     r8d, [rbp+rax*8+0]; cbInput
0x180004a00  mov     rdx, [rbp+rax*8+8]; pbInput
0x180004a05  call    cs:__imp_BCryptHashData
0x180004a0b  mov     edi, eax
0x180004a0d  test    eax, eax
0x180004a0f  jz      short loc_1800049E8
0x180004a11  mov     rcx, [rsp+98h+hHash]; hHash
0x180004a16  call    cs:__imp_BCryptDestroyHash
0x180004a1c  mov     ecx, edi
0x180004a1e  call    WIN32_FROM_NTSTATUS
0x180004a23  jmp     short loc_180004A4A
0x180004a25  mov     r8d, 20h ; ' '; cbOutput
0x180004a2b  lea     rdx, [rsp+98h+pbOutput]; pbOutput
0x180004a30  call    cs:__imp_BCryptFinishHash
0x180004a36  mov     rcx, [rsp+98h+hHash]; hHash
0x180004a3b  mov     ebx, eax
0x180004a3d  call    cs:__imp_BCryptDestroyHash
0x180004a43  test    ebx, ebx
0x180004a45  js      short loc_180004AB7
0x180004a47  mov     eax, r15d
0x180004a4a  mov     rdi, [rsp+98h+var_20]
0x180004a4f  mov     r15, [rsp+98h+var_28]
0x180004a54  mov     rbp, [rsp+98h+arg_0]
0x180004a5c  test    eax, eax
0x180004a5e  jnz     short loc_180004AC9
0x180004a60  movzx   eax, [rsp+98h+pbOutput]
0x180004a65  and     eax, 0Fh
0x180004a68  mov     rbx, [rsi+rax*8]
0x180004a6c  test    rbx, rbx
0x180004a6f  jz      short loc_180004A90
0x180004a71  lea     rcx, [rbx+18h]; Buf1
0x180004a75  mov     r8d, 20h ; ' '; Size
0x180004a7b  lea     rdx, [rsp+98h+pbOutput]; Buf2
0x180004a80  call    memcmp_0
0x180004a85  test    eax, eax
0x180004a87  jnz     short loc_180004AD2
0x180004a89  cmp     qword ptr [rbx+8], 0
0x180004a8e  jnz     short loc_180004ADD
0x180004a90  mov     eax, 490h
0x180004a95  mov     rcx, [rsp+98h+var_30]
0x180004a9a  xor     rcx, rsp; StackCookie
0x180004a9d  call    __security_check_cookie
0x180004aa2  add     rsp, 80h
0x180004aa9  pop     r14
0x180004aab  pop     rsi
0x180004aac  pop     rbx
0x180004aad  retn
0x180004aae  mov     ecx, eax
0x180004ab0  call    WIN32_FROM_NTSTATUS
0x180004ab5  jmp     short loc_180004A4F
0x180004ab7  mov     ecx, ebx; Status
0x180004ab9  call    cs:__imp_RtlNtStatusToDosError
0x180004abf  cmp     eax, 13Dh
0x180004ac4  cmovz   eax, ebx
0x180004ac7  jmp     short loc_180004A4A
0x180004ac9  mov     ecx, eax
0x180004acb  call    WIN32_FROM_NTSTATUS
0x180004ad0  jmp     short loc_180004A95
0x180004ad2  mov     rbx, [rbx+10h]
0x180004ad6  test    rbx, rbx
0x180004ad9  jnz     short loc_180004A71
0x180004adb  jmp     short loc_180004A90
0x180004add  mov     eax, [rbx]
0x180004adf  test    eax, eax
0x180004ae1  jz      short loc_180004A90
0x180004ae3  mov     [r14], eax
0x180004ae6  mov     rax, [rbx+8]
0x180004aea  mov     [r14+8], rax
0x180004aee  xor     eax, eax
0x180004af0  jmp     short loc_180004A95
```
