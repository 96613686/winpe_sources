# RegDeleteValueW

- ea: `0x1800a6590`
- end: `0x1800a6873`
- name: `RegDeleteValueW`
- size: `739`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a5fac`
- `0x1800a62a4`
- `0x1800a64f4`
- `0x1800a6520`
- `0x18012b594`
- `0x180133220`
- `0x1801343f4`
- `0x180142420`

## callees

- `0x180049440`
- `0x18005b460`
- `0x18005bb80`
- `0x18005cf00`
- `0x18005e150`
- `0x1800a6590`
- `0x1800a6e58`
- `0x18012d578`
- `0x18012ffa4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a66aa`
- `ntdll!RtlNtStatusToDosError` at `0x1800a66aa`
- `ntdll!NtDeleteValueKey` at `0x1800a668c`
- `ntdll!NtDeleteValueKey` at `0x1800a67da`
- `ntdll!NtDeleteValueKey` at `0x1800a668c`
- `ntdll!NtDeleteValueKey` at `0x1800a67da`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800a65eb`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800a65eb`
- `ntdll!NtClose` at `0x1800a679e`
- `ntdll!NtClose` at `0x1800a679e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800a66ff`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800a66ff`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800a672f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800a672f`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegDeleteValue` at `0x1800a6855`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegDeleteValue` at `0x1800a6855`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteValue` at `0x1800a6669`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteValue` at `0x1800a6669`

## pseudocode

```c
LSTATUS __stdcall RegDeleteValueW(HKEY hKey, LPCWSTR lpValueName)
{
  LSTATUS v3; // edi
  NTSTATUS inited; // eax
  __int64 v5; // rcx
  __int16 v6; // ax
  unsigned __int64 v7; // rsi
  HKEY v8; // rdi
  HKEY v9; // r14
  void *v10; // rcx
  NTSTATUS v11; // eax
  NTSTATUS v12; // r15d
  NTSTATUS v13; // ecx
  LPWCH v14; // rsi
  HKEY *v16; // r14
  _QWORD *v18; // rax
  WCHAR *v19; // rcx
  HKEY v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r8
  LPWCH v23; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+8h] BYREF
  HKEY v26; // [rsp+90h] [rbp+18h] BYREF
  HKEY v27; // [rsp+98h] [rbp+20h] BYREF

  KeyHandle = hKey;
  DestinationString = 0;
  v27 = 0;
  v23 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  v3 = MapPredefinedHandleInternal(hKey, (HKEY *)&KeyHandle, &v27, &v23);
  if ( !v3 )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, lpValueName);
    if ( inited >= 0 )
    {
      v6 = DestinationString.Length + 2;
      DestinationString.Length += 2;
      v7 = (unsigned __int64)KeyHandle;
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
      {
        if ( (unsigned __int8)IsBaseRegCloseKeyPresent(v5) )
          v3 = BaseRegDeleteValue(v7 & 0xFFFFFFFFFFFFFFFEuLL, &DestinationString);
        goto LABEL_16;
      }
      v8 = 0;
      KeyHandle = 0;
      v9 = 0;
      v26 = 0;
      if ( (unsigned __int16)v6 < 2u || (v6 & 1) != 0 || !DestinationString.Buffer )
      {
        if ( DestinationString.Buffer || v6 != 2 || DestinationString.MaximumLength )
        {
          v3 = 87;
          goto LABEL_16;
        }
        v6 = 2;
      }
      DestinationString.Length = v6 - 2;
      if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
        TermsrvDeleteValue(v7, &DestinationString);
      if ( (v7 & 2) == 0 )
      {
LABEL_11:
        v10 = (void *)v7;
        if ( v8 && v9 )
          v10 = v8;
        v11 = NtDeleteValueKey(v10, &DestinationString);
        v12 = v11;
        if ( (v7 & 2) != 0 && v11 == -1073741772 )
        {
          if ( !v8 )
          {
LABEL_14:
            v13 = v12;
LABEL_15:
            v3 = RtlNtStatusToDosError(v13);
            goto LABEL_16;
          }
          if ( v9 )
            v12 = NtDeleteValueKey(v9, &DestinationString);
        }
        if ( v8 && v9 )
        {
          v20 = v8;
          if ( v8 == (HKEY)v7 )
            v20 = v9;
          NtClose(v20);
        }
        goto LABEL_14;
      }
      inited = BaseRegGetUserAndMachineClass(0, v7, 0x2000000, &v26, &KeyHandle);
      if ( inited >= 0 )
      {
        v8 = (HKEY)KeyHandle;
        v9 = v26;
        goto LABEL_11;
      }
    }
    v13 = inited;
    goto LABEL_15;
  }
LABEL_16:
  v26 = v27;
  v14 = v23;
  if ( v27 )
    BaseRegCloseKeyInternal(&v26);
  if ( v14 )
  {
    v16 = 0;
    RtlAcquireSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( (*((_DWORD *)v14 + 2))-- == 1 )
    {
      v18 = (_QWORD *)*((_QWORD *)v14 + 2);
      v19 = (WCHAR *)v18[1];
      if ( v14 != v19 || *(_QWORD *)v14 != *v18 )
      {
        v16 = (HKEY *)v14;
        v21 = RemoveUnitFromList(v19, v14, *((_QWORD *)v14 + 2));
        *(_QWORD *)(v22 + 8) = v21;
      }
    }
    RtlReleaseSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( v16 )
    {
      RegCloseKey(*v16);
      FreeEnvironmentStringsW((LPWCH)v16);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800a6590  mov     rax, rsp
0x1800a6593  mov     [rax+10h], rbx
0x1800a6597  mov     [rax+8], rcx
0x1800a659b  push    rsi
0x1800a659c  push    rdi
0x1800a659d  push    r12
0x1800a659f  push    r14
0x1800a65a1  push    r15
0x1800a65a3  sub     rsp, 50h
0x1800a65a7  mov     rsi, rdx
0x1800a65aa  xorps   xmm0, xmm0
0x1800a65ad  movups  xmmword ptr [rax-38h], xmm0
0x1800a65b1  xor     ebx, ebx
0x1800a65b3  mov     [rax+20h], rbx
0x1800a65b7  mov     [rax-40h], rbx
0x1800a65bb  cmp     rcx, 0FFFFFFFF80000004h
0x1800a65c2  jz      loc_1800A6780
0x1800a65c8  lea     r9, [rax-40h]
0x1800a65cc  lea     r8, [rax+20h]
0x1800a65d0  lea     rdx, [rax+8]
0x1800a65d4  call    MapPredefinedHandleInternal
0x1800a65d9  mov     edi, eax
0x1800a65db  test    eax, eax
0x1800a65dd  jnz     loc_1800A66B2
0x1800a65e3  mov     rdx, rsi; SourceString
0x1800a65e6  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800a65eb  call    cs:__imp_RtlInitUnicodeStringEx
0x1800a65f1  test    eax, eax
0x1800a65f3  js      loc_1800A6779
0x1800a65f9  movzx   eax, [rsp+78h+DestinationString.Length]
0x1800a65fe  lea     r15d, [rbx+2]
0x1800a6602  add     ax, r15w
0x1800a6606  mov     [rsp+78h+DestinationString.Length], ax
0x1800a660b  mov     rsi, [rsp+78h+KeyHandle]
0x1800a6613  test    sil, 1
0x1800a6617  jnz     loc_1800A683C
0x1800a661d  mov     edi, ebx
0x1800a661f  mov     [rsp+78h+KeyHandle], rbx
0x1800a6627  mov     r14d, ebx
0x1800a662a  mov     [rsp+78h+arg_10], rbx
0x1800a6632  cmp     ax, r15w
0x1800a6636  jb      loc_1800A6800
0x1800a663c  test    al, 1
0x1800a663e  jnz     loc_1800A6800
0x1800a6644  cmp     [rsp+78h+DestinationString.Buffer], rbx
0x1800a6649  jz      loc_1800A6800
0x1800a664f  sub     ax, r15w
0x1800a6653  mov     [rsp+78h+DestinationString.Length], ax
0x1800a6658  call    IsTermsrvDeleteKeyPresent
0x1800a665d  test    al, al
0x1800a665f  jz      short loc_1800A666F
0x1800a6661  lea     rdx, [rsp+78h+DestinationString]
0x1800a6666  mov     rcx, rsi
0x1800a6669  call    cs:__imp_TermsrvDeleteValue
0x1800a666f  mov     r12d, esi
0x1800a6672  and     r12d, r15d
0x1800a6675  jnz     loc_1800A674C
0x1800a667b  mov     rcx, rsi; KeyHandle
0x1800a667e  test    rdi, rdi
0x1800a6681  jnz     loc_1800A67A9
0x1800a6687  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x1800a668c  call    cs:__imp_NtDeleteValueKey
0x1800a6692  mov     r15d, eax
0x1800a6695  test    r12d, r12d
0x1800a6698  jnz     loc_1800A67B5
0x1800a669e  test    rdi, rdi
0x1800a66a1  jnz     loc_1800A678A
0x1800a66a7  mov     ecx, r15d; Status
0x1800a66aa  call    cs:__imp_RtlNtStatusToDosError
0x1800a66b0  mov     edi, eax
0x1800a66b2  mov     rax, [rsp+78h+arg_18]
0x1800a66ba  mov     [rsp+78h+arg_10], rax
0x1800a66c2  mov     rsi, [rsp+78h+var_40]
0x1800a66c7  test    rax, rax
0x1800a66ca  jz      short loc_1800A66D9
0x1800a66cc  lea     rcx, [rsp+78h+arg_10]
0x1800a66d4  call    BaseRegCloseKeyInternal
0x1800a66d9  test    rsi, rsi
0x1800a66dc  jnz     short loc_1800A66F5
0x1800a66de  mov     eax, edi
0x1800a66e0  mov     rbx, [rsp+78h+arg_8]
0x1800a66e8  add     rsp, 50h
0x1800a66ec  pop     r15
0x1800a66ee  pop     r14
0x1800a66f0  pop     r12
0x1800a66f2  pop     rdi
0x1800a66f3  pop     rsi
0x1800a66f4  retn
0x1800a66f5  mov     r14, rbx
0x1800a66f8  lea     rcx, PredefinedHandleTableSRWLock
0x1800a66ff  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800a6705  add     dword ptr [rsi+8], 0FFFFFFFFh
0x1800a6709  jnz     short loc_1800A6728
0x1800a670b  mov     rax, [rsi+10h]
0x1800a670f  mov     rcx, [rax+8]
0x1800a6713  cmp     rsi, rcx
0x1800a6716  jnz     loc_1800A67E8
0x1800a671c  mov     rax, [rax]
0x1800a671f  cmp     [rsi], rax
0x1800a6722  jnz     loc_1800A67E8
0x1800a6728  lea     rcx, PredefinedHandleTableSRWLock
0x1800a672f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800a6735  test    r14, r14
0x1800a6738  jz      short loc_1800A66DE
0x1800a673a  mov     rcx, [r14]; hKey
0x1800a673d  call    RegCloseKey
0x1800a6742  mov     rcx, r14; penv
0x1800a6745  call    FreeEnvironmentStringsW
0x1800a674a  jmp     short loc_1800A66DE
0x1800a674c  lea     rax, [rsp+78h+KeyHandle]
0x1800a6754  mov     [rsp+78h+var_58], rax
0x1800a6759  lea     r9, [rsp+78h+arg_10]
0x1800a6761  mov     r8d, 2000000h
0x1800a6767  mov     rdx, rsi
0x1800a676a  xor     ecx, ecx
0x1800a676c  call    BaseRegGetUserAndMachineClass
0x1800a6771  test    eax, eax
0x1800a6773  jns     loc_1800A6827
0x1800a6779  mov     ecx, eax
0x1800a677b  jmp     loc_1800A66AA
0x1800a6780  mov     eax, 6
0x1800a6785  jmp     loc_1800A66E0
0x1800a678a  test    r14, r14
0x1800a678d  jz      loc_1800A66A7
0x1800a6793  cmp     rdi, rsi
0x1800a6796  mov     rcx, rdi
0x1800a6799  jnz     short loc_1800A679E
0x1800a679b  mov     rcx, r14; Handle
0x1800a679e  call    cs:__imp_NtClose
0x1800a67a4  jmp     loc_1800A66A7
0x1800a67a9  test    r14, r14
0x1800a67ac  cmovnz  rcx, rdi
0x1800a67b0  jmp     loc_1800A6687
0x1800a67b5  cmp     eax, 0C0000034h
0x1800a67ba  jnz     loc_1800A669E
0x1800a67c0  test    rdi, rdi
0x1800a67c3  jz      loc_1800A66A7
0x1800a67c9  test    r14, r14
0x1800a67cc  jz      loc_1800A669E
0x1800a67d2  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x1800a67d7  mov     rcx, r14; KeyHandle
0x1800a67da  call    cs:__imp_NtDeleteValueKey
0x1800a67e0  mov     r15d, eax
0x1800a67e3  jmp     loc_1800A669E
0x1800a67e8  mov     r14, rsi
0x1800a67eb  mov     r8, [rsi+10h]
0x1800a67ef  mov     rdx, rsi
0x1800a67f2  call    RemoveUnitFromList
0x1800a67f7  mov     [r8+8], rax
0x1800a67fb  jmp     loc_1800A6728
0x1800a6800  cmp     [rsp+78h+DestinationString.Buffer], rbx
0x1800a6805  jnz     short loc_1800A681D
0x1800a6807  cmp     ax, r15w
0x1800a680b  jnz     short loc_1800A681D
0x1800a680d  cmp     [rsp+78h+DestinationString.MaximumLength], bx
0x1800a6812  jnz     short loc_1800A681D
0x1800a6814  movzx   eax, r15w
0x1800a6818  jmp     loc_1800A664F
0x1800a681d  mov     edi, 57h ; 'W'
0x1800a6822  jmp     loc_1800A66B2
0x1800a6827  mov     rdi, [rsp+78h+KeyHandle]
0x1800a682f  mov     r14, [rsp+78h+arg_10]
0x1800a6837  jmp     loc_1800A667B
0x1800a683c  call    IsBaseRegCloseKeyPresent
0x1800a6841  test    al, al
0x1800a6843  jz      loc_1800A66B2
0x1800a6849  and     rsi, 0FFFFFFFFFFFFFFFEh
0x1800a684d  lea     rdx, [rsp+78h+DestinationString]
0x1800a6852  mov     rcx, rsi
0x1800a6855  call    cs:__imp_BaseRegDeleteValue
0x1800a685b  mov     edi, eax
0x1800a685d  mov     [rsp+78h+var_48], eax
0x1800a6861  jmp     loc_1800A66B2
0x1800a6866  mov     edi, eax
0x1800a6868  mov     [rsp+78h+var_48], eax
0x1800a686c  xor     ebx, ebx
0x1800a686e  jmp     loc_1800A66B2
```
