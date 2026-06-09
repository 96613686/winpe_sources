# CTemplate::CFileMap::GetSecurityDescriptor(void)

- ea: `0x180014bf0`
- end: `0x180014cca`
- name: `?GetSecurityDescriptor@CFileMap@CTemplate@@QEAAHXZ`
- size: `218`
- prototype: `__int64 __fastcall(CTemplate::CFileMap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013d7c`

## callees

- `0x180014bf0`
- `0x180016918`
- `0x180017a8c`

## import_xrefs

- `ADVAPI32!GetKernelObjectSecurity` at `0x180014c21`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180014ca7`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180014c21`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180014ca7`
- `KERNEL32!HeapFree` at `0x18002c501`
- `KERNEL32!HeapFree` at `0x18002c501`
- `KERNEL32!HeapAlloc` at `0x180014c76`
- `KERNEL32!HeapAlloc` at `0x180014c76`
- `KERNEL32!RaiseException` at `0x18002c54a`
- `KERNEL32!RaiseException` at `0x18002c5a0`
- `KERNEL32!RaiseException` at `0x18002c54a`
- `KERNEL32!RaiseException` at `0x18002c5a0`
- `KERNEL32!GetLastError` at `0x180014c27`
- `KERNEL32!GetLastError` at `0x18002c55d`
- `KERNEL32!GetLastError` at `0x180014c27`
- `KERNEL32!GetLastError` at `0x18002c55d`

## pseudocode

```c
_BOOL8 __fastcall CTemplate::CFileMap::GetSecurityDescriptor(HANDLE *this)
{
  DWORD LastError; // eax
  HANDLE v3; // rcx
  DWORD v4; // edi
  int v5; // eax
  DWORD v6; // edi
  int v7; // ecx
  SIZE_T v8; // rax
  LPVOID i; // rax
  void *v11; // rax
  HANDLE v12; // rcx
  DWORD nLengthNeeded; // [rsp+40h] [rbp+8h] BYREF

  nLengthNeeded = 0;
  GetKernelObjectSecurity(this[4], 7u, 0, 0, &nLengthNeeded);
  LastError = GetLastError();
  v3 = this[8];
  v4 = LastError;
  if ( LastError == 122 )
  {
    v5 = *((_DWORD *)this + 18);
    v6 = (nLengthNeeded + 127) & 0xFFFFFF80;
    if ( v3 )
    {
      if ( (v5 & 0x3FFFFFFFu) < v6 )
      {
        v11 = CTemplate::SmallReAlloc(v3, v6);
        this[8] = v11;
        if ( !v11 )
          RaiseException(0x8007000E, 0, 0, 0);
        *((_DWORD *)this + 18) ^= (*((_DWORD *)this + 18) ^ v6) & 0x3FFFFFFF;
      }
      goto LABEL_6;
    }
    v7 = v5 ^ (v6 ^ v5) & 0x3FFFFFFF;
    *((_DWORD *)this + 18) = v7;
    v8 = _RoundUp(v7 & 0x3FFFFFFF);
    for ( i = HeapAlloc(CTemplate::sm_hSmallHeap, 0, v8); ; i = CTemplate::SmallReAlloc(
                                                                  v12,
                                                                  (_DWORD)this[9] & 0x3FFFFFFF) )
    {
      this[8] = i;
      if ( !i )
        RaiseException(0x8007000E, 0, 0, 0);
LABEL_6:
      if ( GetKernelObjectSecurity(this[4], 7u, this[8], (_DWORD)this[9] & 0x3FFFFFFF, &nLengthNeeded) )
        return 1;
      if ( GetLastError() != 122 )
        break;
      *((_DWORD *)this + 18) &= 0xC0000000;
      v12 = this[8];
      *((_DWORD *)this + 18) |= (nLengthNeeded + 127) & 0x3FFFFF80;
    }
    return 0;
  }
  else
  {
    if ( v3 )
      HeapFree(CTemplate::sm_hSmallHeap, 0, this[8]);
    *((_DWORD *)this + 18) &= 0xC0000000;
    this[8] = 0;
    return v4 == 50;
  }
}

```

## disassembly

```asm
0x180014bf0  mov     rax, rsp
0x180014bf3  mov     [rax+10h], rbx
0x180014bf7  mov     [rax+18h], rsi
0x180014bfb  push    rdi
0x180014bfc  sub     rsp, 30h
0x180014c00  xor     r9d, r9d; nLength
0x180014c03  mov     dword ptr [rax+8], 0
0x180014c0a  mov     rbx, rcx
0x180014c0d  lea     rax, [rax+8]
0x180014c11  mov     rcx, [rcx+20h]; Handle
0x180014c15  xor     r8d, r8d; pSecurityDescriptor
0x180014c18  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180014c1d  lea     edx, [r9+7]; RequestedInformation
0x180014c21  call    cs:__imp_GetKernelObjectSecurity
0x180014c27  call    cs:__imp_GetLastError
0x180014c2d  mov     rcx, [rbx+40h]; void *
0x180014c31  mov     edi, eax
0x180014c33  cmp     eax, 7Ah ; 'z'
0x180014c36  jnz     loc_18002C4F0
0x180014c3c  mov     edi, [rsp+38h+nLengthNeeded]
0x180014c40  mov     esi, 3FFFFFFFh
0x180014c45  mov     eax, [rbx+48h]
0x180014c48  add     edi, 7Fh
0x180014c4b  and     edi, 0FFFFFF80h
0x180014c4e  test    rcx, rcx
0x180014c51  jnz     loc_18002C523
0x180014c57  mov     ecx, eax
0x180014c59  xor     ecx, edi
0x180014c5b  and     ecx, esi
0x180014c5d  xor     ecx, eax
0x180014c5f  mov     [rbx+48h], ecx
0x180014c62  and     rcx, rsi; unsigned __int64
0x180014c65  call    ?_RoundUp@@YA_K_K@Z; _RoundUp(unsigned __int64)
0x180014c6a  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x180014c71  mov     r8, rax; dwBytes
0x180014c74  xor     edx, edx; dwFlags
0x180014c76  call    cs:__imp_HeapAlloc
0x180014c7c  mov     [rbx+40h], rax
0x180014c80  test    rax, rax
0x180014c83  jz      loc_18002C593
0x180014c89  mov     r9d, [rbx+48h]
0x180014c8d  lea     rax, [rsp+38h+nLengthNeeded]
0x180014c92  mov     r8, [rbx+40h]; pSecurityDescriptor
0x180014c96  and     r9d, esi; nLength
0x180014c99  mov     rcx, [rbx+20h]; Handle
0x180014c9d  mov     edx, 7; RequestedInformation
0x180014ca2  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180014ca7  call    cs:__imp_GetKernelObjectSecurity
0x180014cad  test    eax, eax
0x180014caf  jz      loc_18002C55D
0x180014cb5  mov     eax, 1
0x180014cba  mov     rbx, [rsp+38h+arg_8]
0x180014cbf  mov     rsi, [rsp+38h+arg_10]
0x180014cc4  add     rsp, 30h
0x180014cc8  pop     rdi
0x180014cc9  retn
0x18002c4f0  test    rcx, rcx
0x18002c4f3  jz      short loc_18002C507
0x18002c4f5  mov     r8, rcx; lpMem
0x18002c4f8  xor     edx, edx; dwFlags
0x18002c4fa  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x18002c501  call    cs:__imp_HeapFree
0x18002c507  and     dword ptr [rbx+48h], 0C0000000h
0x18002c50e  xor     eax, eax
0x18002c510  cmp     edi, 32h ; '2'
0x18002c513  mov     qword ptr [rbx+40h], 0
0x18002c51b  setz    al
0x18002c51e  jmp     loc_180014CBA
0x18002c523  and     eax, esi
0x18002c525  cmp     eax, edi
0x18002c527  jnb     loc_180014C89
0x18002c52d  mov     edx, edi; unsigned __int64
0x18002c52f  call    ?SmallReAlloc@CTemplate@@SAPEAXPEAX_K@Z; CTemplate::SmallReAlloc(void *,unsigned __int64)
0x18002c534  mov     [rbx+40h], rax
0x18002c538  test    rax, rax
0x18002c53b  jnz     short loc_18002C550
0x18002c53d  xor     r9d, r9d; lpArguments
0x18002c540  xor     r8d, r8d; nNumberOfArguments
0x18002c543  xor     edx, edx; dwExceptionFlags
0x18002c545  mov     ecx, 8007000Eh; dwExceptionCode
0x18002c54a  call    cs:__imp_RaiseException
0x18002c550  xor     edi, [rbx+48h]
0x18002c553  and     edi, esi
0x18002c555  xor     [rbx+48h], edi
0x18002c558  jmp     loc_180014C89
0x18002c55d  call    cs:__imp_GetLastError
0x18002c563  cmp     eax, 7Ah ; 'z'
0x18002c566  jnz     short loc_18002C5AC
0x18002c568  and     dword ptr [rbx+48h], 0C0000000h
0x18002c56f  mov     eax, [rsp+38h+nLengthNeeded]
0x18002c573  mov     rcx, [rbx+40h]; void *
0x18002c577  add     eax, 7Fh
0x18002c57a  and     eax, 3FFFFF80h
0x18002c57f  or      [rbx+48h], eax
0x18002c582  mov     edx, [rbx+48h]
0x18002c585  and     rdx, rsi; unsigned __int64
0x18002c588  call    ?SmallReAlloc@CTemplate@@SAPEAXPEAX_K@Z; CTemplate::SmallReAlloc(void *,unsigned __int64)
0x18002c58d  nop
0x18002c58e  jmp     loc_180014C7C
0x18002c593  xor     r9d, r9d; lpArguments
0x18002c596  xor     r8d, r8d; nNumberOfArguments
0x18002c599  xor     edx, edx; dwExceptionFlags
0x18002c59b  mov     ecx, 8007000Eh; dwExceptionCode
0x18002c5a0  call    cs:__imp_RaiseException
0x18002c5a6  nop
0x18002c5a7  jmp     loc_180014C89
0x18002c5ac  xor     eax, eax
0x18002c5ae  jmp     loc_180014CBA
```
