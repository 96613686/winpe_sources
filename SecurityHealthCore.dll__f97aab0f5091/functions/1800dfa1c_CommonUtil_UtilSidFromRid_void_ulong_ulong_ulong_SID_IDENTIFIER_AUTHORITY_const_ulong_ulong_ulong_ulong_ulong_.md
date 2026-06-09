# CommonUtil::UtilSidFromRid(void * *,ulong,ulong,ulong,_SID_IDENTIFIER_AUTHORITY const *,ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x1800dfa1c`
- end: `0x1800dfb14`
- name: `?UtilSidFromRid@CommonUtil@@YAJPEAPEAXKKKPEBU_SID_IDENTIFIER_AUTHORITY@@KKKKKK@Z`
- size: `248`
- prototype: `__int64 __usercall@<rax>(CommonUtil *__hidden this@<rcx>, void **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cee78`
- `0x1800de940`
- `0x1800df118`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x1800df368`
- `0x1800dfa1c`
- `0x1800e1690`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800dfa98`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800dfa98`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800dfaf0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800dfaf0`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSidFromRid(
        CommonUtil *this,
        void **a2,
        DWORD a3,
        DWORD a4,
        struct _SID_IDENTIFIER_AUTHORITY *a5)
{
  struct _SID_IDENTIFIER_AUTHORITY *p_pIdentifierAuthority; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // r8
  unsigned int LastFailure; // ebx
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  int v13; // [rsp+68h] [rbp-18h] BYREF
  __int16 v14; // [rsp+6Ch] [rbp-14h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  p_pIdentifierAuthority = a5;
  if ( (unsigned int)((_DWORD)a2 - 1) > 7 )
    return 2147942487LL;
  v14 = 1280;
  v13 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  if ( !a5 )
  {
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v13;
    if ( !a3 )
      p_pIdentifierAuthority = &pIdentifierAuthority;
  }
  pSid = 0;
  if ( AllocateAndInitializeSid(p_pIdentifierAuthority, (BYTE)a2, a3, a4, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastFailure = CommonUtil::UtilDuplicateSid(this, (void **)pSid, v9);
    FreeSid(pSid);
  }
  else
  {
    LastFailure = HrGetLastFailure(v8, v7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids, LastFailure);
  }
  return LastFailure;
}

```

## disassembly

```asm
0x1800dfa1c  push    rbp
0x1800dfa1e  push    rbx
0x1800dfa1f  push    rdi
0x1800dfa20  mov     rbp, rsp
0x1800dfa23  sub     rsp, 80h
0x1800dfa2a  mov     rax, cs:__security_cookie
0x1800dfa31  xor     rax, rsp
0x1800dfa34  mov     [rbp+var_8], rax
0x1800dfa38  lea     eax, [rdx-1]
0x1800dfa3b  mov     rbx, rcx
0x1800dfa3e  mov     rcx, qword ptr [rbp+arg_20]
0x1800dfa42  cmp     eax, 7
0x1800dfa45  ja      loc_1800DFAF8
0x1800dfa4b  xor     edi, edi
0x1800dfa4d  mov     [rbp+var_14], 500h
0x1800dfa53  mov     [rbp+var_18], edi
0x1800dfa56  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800dfa59  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x1800dfa5f  test    rcx, rcx
0x1800dfa62  jnz     short loc_1800DFA73
0x1800dfa64  test    r8d, r8d
0x1800dfa67  lea     rcx, [rbp+var_18]
0x1800dfa6b  lea     rax, [rbp+pIdentifierAuthority]
0x1800dfa6f  cmovz   rcx, rax; pIdentifierAuthority
0x1800dfa73  lea     rax, [rbp+var_20]
0x1800dfa77  mov     [rbp+var_20], rdi
0x1800dfa7b  mov     [rsp+80h+pSid], rax; pSid
0x1800dfa80  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800dfa84  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800dfa88  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800dfa8c  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800dfa90  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800dfa94  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800dfa98  call    cs:__imp_AllocateAndInitializeSid
0x1800dfa9e  test    eax, eax
0x1800dfaa0  jnz     short loc_1800DFADE
0x1800dfaa2  call    HrGetLastFailure
0x1800dfaa7  mov     ebx, eax
0x1800dfaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfab0  lea     rax, WPP_GLOBAL_Control
0x1800dfab7  cmp     rcx, rax
0x1800dfaba  jz      short loc_1800DFADA
0x1800dfabc  test    byte ptr [rcx+1Ch], 1
0x1800dfac0  jz      short loc_1800DFADA
0x1800dfac2  mov     rcx, [rcx+10h]
0x1800dfac6  lea     r8, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids
0x1800dfacd  mov     edx, 0Dh
0x1800dfad2  mov     r9d, ebx
0x1800dfad5  call    WPP_SF_d
0x1800dfada  mov     eax, ebx
0x1800dfadc  jmp     short loc_1800DFAFD
0x1800dfade  mov     rdx, [rbp+var_20]; void **
0x1800dfae2  mov     rcx, rbx; this
0x1800dfae5  call    ?UtilDuplicateSid@CommonUtil@@YAJPEAPEAXPEAX@Z; CommonUtil::UtilDuplicateSid(void * *,void *)
0x1800dfaea  mov     rcx, [rbp+var_20]; pSid
0x1800dfaee  mov     ebx, eax
0x1800dfaf0  call    cs:__imp_FreeSid
0x1800dfaf6  jmp     short loc_1800DFADA
0x1800dfaf8  mov     eax, 80070057h
0x1800dfafd  mov     rcx, [rbp+var_8]
0x1800dfb01  xor     rcx, rsp; StackCookie
0x1800dfb04  call    __security_check_cookie
0x1800dfb09  add     rsp, 80h
0x1800dfb10  pop     rdi
0x1800dfb11  pop     rbx
0x1800dfb12  pop     rbp
0x1800dfb13  retn
```
