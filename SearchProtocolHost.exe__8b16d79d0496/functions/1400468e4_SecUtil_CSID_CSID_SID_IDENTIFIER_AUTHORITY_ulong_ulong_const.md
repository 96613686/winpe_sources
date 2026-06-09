# SecUtil::CSID::CSID(_SID_IDENTIFIER_AUTHORITY *,ulong,ulong const *)

- ea: `0x1400468e4`
- end: `0x140046986`
- name: `??0CSID@SecUtil@@QEAA@PEAU_SID_IDENTIFIER_AUTHORITY@@KPEBK@Z`
- size: `162`
- prototype: `_QWORD(SecUtil::CSID *__hidden this, struct _SID_IDENTIFIER_AUTHORITY *, unsigned int, const unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004698c`
- `0x1400469c0`
- `0x1400469f4`

## callees

- `0x140005918`
- `0x14000ea6c`
- `0x1400468e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x140046937`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x140046937`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140046919`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140046919`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140046951`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140046951`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SecUtil::CSID *__fastcall SecUtil::CSID::CSID(
        SecUtil::CSID *this,
        struct _SID_IDENTIFIER_AUTHORITY *a2,
        unsigned int a3,
        const unsigned int *a4)
{
  unsigned __int64 SidLengthRequired; // rcx
  void *v9; // rbp
  __int64 i; // rdi
  DWORD v11; // ebx
  void *v13; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  v13 = 0;
  SidLengthRequired = GetSidLengthRequired(a3);
  v9 = operator new[](SidLengthRequired);
  v13 = v9;
  if ( InitializeSid(v9, a2, a3) )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v11 = a4[i];
      *GetSidSubAuthority(v9, i) = v11;
    }
    v13 = 0;
    *(_QWORD *)this = v9;
  }
  TPointer<unsigned char>::~TPointer<unsigned char>(&v13);
  return this;
}

```

## disassembly

```asm
0x1400468e4  push    rbx
0x1400468e6  push    rbp
0x1400468e7  push    rsi
0x1400468e8  push    rdi
0x1400468e9  push    r14
0x1400468eb  push    r15
0x1400468ed  sub     rsp, 38h
0x1400468f1  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1400468fa  mov     r15, r9
0x1400468fd  mov     r14d, r8d
0x140046900  mov     rbx, rdx
0x140046903  mov     rsi, rcx
0x140046906  mov     qword ptr [rcx], 0
0x14004690d  mov     [rsp+68h+arg_0], 0
0x140046916  mov     cl, r8b; nSubAuthorityCount
0x140046919  call    cs:__imp_GetSidLengthRequired
0x14004691f  mov     ecx, eax; unsigned __int64
0x140046921  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140046926  mov     rbp, rax
0x140046929  mov     [rsp+68h+arg_0], rax
0x14004692e  mov     r8b, r14b; nSubAuthorityCount
0x140046931  mov     rdx, rbx; pIdentifierAuthority
0x140046934  mov     rcx, rax; Sid
0x140046937  call    cs:__imp_InitializeSid
0x14004693d  test    eax, eax
0x14004693f  jz      short loc_14004696C
0x140046941  xor     edi, edi
0x140046943  test    r14d, r14d
0x140046946  jz      short loc_140046960
0x140046948  mov     ebx, [r15+rdi*4]
0x14004694c  mov     edx, edi; nSubAuthority
0x14004694e  mov     rcx, rbp; pSid
0x140046951  call    cs:__imp_GetSidSubAuthority
0x140046957  mov     [rax], ebx
0x140046959  inc     edi
0x14004695b  cmp     edi, r14d
0x14004695e  jb      short loc_140046948
0x140046960  mov     [rsp+68h+arg_0], 0
0x140046969  mov     [rsi], rbp
0x14004696c  lea     rcx, [rsp+68h+arg_0]
0x140046971  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x140046976  mov     rax, rsi
0x140046979  add     rsp, 38h
0x14004697d  pop     r15
0x14004697f  pop     r14
0x140046981  pop     rdi
0x140046982  pop     rsi
0x140046983  pop     rbp
0x140046984  pop     rbx
0x140046985  retn
```
