# CommonUtil::UtilCreateEmptyAcl(_ACL * *)

- ea: `0x140010648`
- end: `0x1400106fc`
- name: `?UtilCreateEmptyAcl@CommonUtil@@YAJPEAPEAU_ACL@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140010258`

## callees

- `0x140010648`
- `0x140015574`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x1400106b5`
- `ADVAPI32!InitializeAcl` at `0x1400106b5`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCreateEmptyAcl(CommonUtil *this, struct _ACL **a2, unsigned __int64 a3)
{
  int v4; // ebx
  PACL v6; // rbx
  unsigned int LastFailure; // edi
  PACL pAcl; // [rsp+20h] [rbp-18h] BYREF

  pAcl = 0;
  v4 = CommonUtil::MpNewAlloc((CommonUtil *)&pAcl, (void **)8, a3);
  if ( v4 >= 0 )
  {
    v6 = pAcl;
    if ( InitializeAcl(pAcl, 8u, 2u) )
    {
      *(_QWORD *)this = v6;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure();
      if ( v6 )
        operator delete(v6, (const struct std::nothrow_t *)8);
      return LastFailure;
    }
  }
  else
  {
    if ( pAcl )
      operator delete(pAcl, (const struct std::nothrow_t *)8);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x140010648  mov     r11, rsp
0x14001064b  mov     [r11+10h], rbx
0x14001064f  mov     [r11+18h], rsi
0x140010653  push    rdi
0x140010654  sub     rsp, 30h
0x140010658  mov     rax, cs:__security_cookie
0x14001065f  xor     rax, rsp
0x140010662  mov     [rsp+38h+var_10], rax
0x140010667  mov     rdi, rcx
0x14001066a  mov     qword ptr [r11-18h], 0
0x140010672  mov     esi, 8
0x140010677  lea     rcx, [r11-18h]; this
0x14001067b  mov     edx, esi; void **
0x14001067d  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x140010682  mov     r8d, eax
0x140010685  mov     ebx, eax
0x140010687  shr     r8d, 1Fh
0x14001068b  test    r8b, r8b
0x14001068e  jz      short loc_1400106A5
0x140010690  mov     rcx, [rsp+38h+pAcl]; void *
0x140010695  test    rcx, rcx
0x140010698  jz      short loc_1400106A1
0x14001069a  mov     edx, esi; struct std::nothrow_t *
0x14001069c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400106a1  mov     eax, ebx
0x1400106a3  jmp     short loc_1400106DF
0x1400106a5  mov     rbx, [rsp+38h+pAcl]
0x1400106aa  mov     r8d, 2; dwAclRevision
0x1400106b0  mov     rcx, rbx; pAcl
0x1400106b3  mov     edx, esi; nAclLength
0x1400106b5  call    cs:__imp_InitializeAcl
0x1400106bb  test    eax, eax
0x1400106bd  jnz     short loc_1400106DA
0x1400106bf  call    HrGetLastFailure
0x1400106c4  mov     edi, eax
0x1400106c6  test    rbx, rbx
0x1400106c9  jz      short loc_1400106D6
0x1400106cb  mov     rdx, rsi; struct std::nothrow_t *
0x1400106ce  mov     rcx, rbx; void *
0x1400106d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400106d6  mov     eax, edi
0x1400106d8  jmp     short loc_1400106DF
0x1400106da  mov     [rdi], rbx
0x1400106dd  xor     eax, eax
0x1400106df  mov     rcx, [rsp+38h+var_10]
0x1400106e4  xor     rcx, rsp; StackCookie
0x1400106e7  call    __security_check_cookie
0x1400106ec  mov     rbx, [rsp+38h+arg_8]
0x1400106f1  mov     rsi, [rsp+38h+arg_10]
0x1400106f6  add     rsp, 30h
0x1400106fa  pop     rdi
0x1400106fb  retn
```
