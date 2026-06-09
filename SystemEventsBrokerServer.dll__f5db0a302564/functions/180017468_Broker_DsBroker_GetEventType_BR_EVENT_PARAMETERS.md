# Broker::DsBroker::GetEventType(_BR_EVENT_PARAMETERS *)

- ea: `0x180017468`
- end: `0x1800175b5`
- name: `?GetEventType@DsBroker@Broker@@CA?AW4_DSB_EVENT_TYPE@2@PEAU_BR_EVENT_PARAMETERS@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021920`

## callees

- `0x180017468`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017500`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017500`

## pseudocode

```c
__int64 __fastcall Broker::DsBroker::GetEventType(unsigned __int16 *a1)
{
  unsigned int v2; // r15d
  char v3; // si
  unsigned int i; // edi
  __int64 v5; // r14
  const WCHAR *v6; // r8
  void **pExceptionObject; // [rsp+30h] [rbp-20h] BYREF
  __int128 v9; // [rsp+38h] [rbp-18h]
  int v10; // [rsp+48h] [rbp-8h]

  if ( *a1 && !*((_QWORD *)a1 + 1) )
  {
    v10 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v9 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  v2 = 1;
  v3 = 0;
  for ( i = 0; i < *a1; ++i )
  {
    v5 = 32LL * i;
    v6 = *(const WCHAR **)(v5 + *((_QWORD *)a1 + 1));
    if ( !v6 )
    {
      v10 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v9 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( CompareStringW(0x7Fu, 1u, v6, -1, L"Type", -1) == 2 )
    {
      if ( v3 )
      {
        v10 = 4;
        pExceptionObject = &Broker::InvalidParameter::`vftable';
        v9 = 0;
        throw (Broker::InvalidParameter *)&pExceptionObject;
      }
      v3 = 1;
      v2 = *(_DWORD *)(*((_QWORD *)a1 + 1) + v5 + 16);
    }
  }
  if ( !v3 )
  {
    v10 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v9 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  return v2;
}

```

## disassembly

```asm
0x180017468  push    rbp
0x18001746a  push    rbx
0x18001746b  push    rsi
0x18001746c  push    rdi
0x18001746d  push    r12
0x18001746f  push    r14
0x180017471  push    r15
0x180017473  mov     rbp, rsp
0x180017476  sub     rsp, 50h
0x18001747a  xor     r12d, r12d
0x18001747d  mov     rbx, rcx
0x180017480  cmp     [rcx], r12w
0x180017484  jz      short loc_1800174B6
0x180017486  cmp     [rcx+8], r12
0x18001748a  jnz     short loc_1800174B6
0x18001748c  xorps   xmm0, xmm0
0x18001748f  mov     [rbp+var_8], 4
0x180017496  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001749d  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800174a4  mov     [rbp+pExceptionObject], rax
0x1800174a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800174ac  movups  [rbp+var_18], xmm0
0x1800174b0  call    _CxxThrowException_0
0x1800174b6  mov     r15d, 1
0x1800174bc  mov     sil, r12b
0x1800174bf  mov     edi, r12d
0x1800174c2  movzx   eax, word ptr [rbx]
0x1800174c5  cmp     edi, eax
0x1800174c7  jnb     loc_180017574
0x1800174cd  mov     rax, [rbx+8]
0x1800174d1  mov     r14d, edi
0x1800174d4  shl     r14, 5
0x1800174d8  mov     r8, [r14+rax]; lpString1
0x1800174dc  test    r8, r8
0x1800174df  jz      short loc_18001754A
0x1800174e1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800174e5  mov     [rsp+50h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800174ed  lea     rax, aType_1; "Type"
0x1800174f4  mov     [rsp+50h+lpString2], rax; lpString2
0x1800174f9  lea     edx, [r9+2]; dwCmpFlags
0x1800174fd  lea     ecx, [rdx+7Eh]; Locale
0x180017500  call    cs:__imp_CompareStringW
0x180017506  cmp     eax, 2
0x180017509  jnz     short loc_18001751C
0x18001750b  test    sil, sil
0x18001750e  jnz     short loc_180017520
0x180017510  mov     rax, [rbx+8]
0x180017514  mov     sil, 1
0x180017517  mov     r15d, [rax+r14+10h]
0x18001751c  inc     edi
0x18001751e  jmp     short loc_1800174C2
0x180017520  xorps   xmm0, xmm0
0x180017523  mov     [rbp+var_8], 4
0x18001752a  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180017531  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180017538  mov     [rbp+pExceptionObject], rax
0x18001753c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017540  movups  [rbp+var_18], xmm0
0x180017544  call    _CxxThrowException_0
0x18001754a  xorps   xmm0, xmm0
0x18001754d  mov     [rbp+var_8], 4
0x180017554  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001755b  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180017562  mov     [rbp+pExceptionObject], rax
0x180017566  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001756a  movups  [rbp+var_18], xmm0
0x18001756e  call    _CxxThrowException_0
0x180017574  test    sil, sil
0x180017577  jnz     short loc_1800175A3
0x180017579  xorps   xmm0, xmm0
0x18001757c  mov     [rbp+var_8], 4
0x180017583  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001758a  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180017591  mov     [rbp+pExceptionObject], rax
0x180017595  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017599  movups  [rbp+var_18], xmm0
0x18001759d  call    _CxxThrowException_0
0x1800175a3  mov     eax, r15d
0x1800175a6  add     rsp, 50h
0x1800175aa  pop     r15
0x1800175ac  pop     r14
0x1800175ae  pop     r12
0x1800175b0  pop     rdi
0x1800175b1  pop     rsi
0x1800175b2  pop     rbx
0x1800175b3  pop     rbp
0x1800175b4  retn
```
