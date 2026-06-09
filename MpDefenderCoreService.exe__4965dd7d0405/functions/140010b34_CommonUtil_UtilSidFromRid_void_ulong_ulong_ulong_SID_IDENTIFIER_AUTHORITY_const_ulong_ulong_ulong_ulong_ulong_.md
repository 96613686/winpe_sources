# CommonUtil::UtilSidFromRid(void * *,ulong,ulong,ulong,_SID_IDENTIFIER_AUTHORITY const *,ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x140010b34`
- end: `0x140010c48`
- name: `?UtilSidFromRid@CommonUtil@@YAJPEAPEAXKKKPEBU_SID_IDENTIFIER_AUTHORITY@@KKKKKK@Z`
- size: `276`
- prototype: `__int64 __usercall@<rax>(CommonUtil *__hidden this@<rcx>, void **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, DWORD, DWORD, DWORD, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fce0`

## callees

- `0x1400106fc`
- `0x140010b34`
- `0x140017738`
- `0x14003a5c0`
- `0x14007d210`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x140010c25`
- `ADVAPI32!FreeSid` at `0x140010c25`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010bcd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140010bcd`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSidFromRid(
        CommonUtil *this,
        void **a2,
        DWORD a3,
        DWORD a4,
        struct _SID_IDENTIFIER_AUTHORITY *a5,
        DWORD nSubAuthority2,
        DWORD nSubAuthority3,
        DWORD nSubAuthority4,
        DWORD nSubAuthority5,
        DWORD nSubAuthority6,
        DWORD nSubAuthority7)
{
  struct _SID_IDENTIFIER_AUTHORITY *p_pIdentifierAuthority; // rcx
  void *v13; // r8
  unsigned int LastFailure; // ebx
  PSID pSid; // [rsp+60h] [rbp-11h] BYREF
  int v17; // [rsp+68h] [rbp-9h] BYREF
  __int16 v18; // [rsp+6Ch] [rbp-5h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-1h] BYREF

  p_pIdentifierAuthority = a5;
  if ( (unsigned int)((_DWORD)a2 - 1) > 7 )
    return 2147942487LL;
  v17 = 0;
  v18 = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  if ( !a5 )
  {
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v17;
    if ( !a3 )
      p_pIdentifierAuthority = &pIdentifierAuthority;
  }
  pSid = 0;
  if ( AllocateAndInitializeSid(
         p_pIdentifierAuthority,
         (BYTE)a2,
         a3,
         a4,
         nSubAuthority2,
         nSubAuthority3,
         nSubAuthority4,
         nSubAuthority5,
         nSubAuthority6,
         nSubAuthority7,
         &pSid) )
  {
    LastFailure = CommonUtil::UtilDuplicateSid(this, (void **)pSid, v13);
    FreeSid(pSid);
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids, LastFailure);
  }
  return LastFailure;
}

```

## disassembly

```asm
0x140010b34  push    rbp
0x140010b36  push    rbx
0x140010b37  lea     rbp, [rsp-17h]
0x140010b3c  sub     rsp, 88h
0x140010b43  mov     rax, cs:__security_cookie
0x140010b4a  xor     rax, rsp
0x140010b4d  mov     [rbp+1Fh+var_18], rax
0x140010b51  lea     eax, [rdx-1]
0x140010b54  mov     rbx, rcx
0x140010b57  mov     rcx, [rbp+1Fh+arg_20]
0x140010b5b  cmp     eax, 7
0x140010b5e  ja      loc_140010C2D
0x140010b64  mov     [rbp+1Fh+var_28], 0
0x140010b6b  mov     [rbp+1Fh+var_24], 500h
0x140010b71  mov     dword ptr [rbp+1Fh+pIdentifierAuthority.Value], 0
0x140010b78  mov     word ptr [rbp+1Fh+pIdentifierAuthority.Value+4], 100h
0x140010b7e  test    rcx, rcx
0x140010b81  jnz     short loc_140010B92
0x140010b83  test    r8d, r8d
0x140010b86  lea     rcx, [rbp+1Fh+var_28]
0x140010b8a  lea     rax, [rbp+1Fh+pIdentifierAuthority]
0x140010b8e  cmovz   rcx, rax; pIdentifierAuthority
0x140010b92  lea     rax, [rbp+1Fh+var_30]
0x140010b96  mov     [rbp+1Fh+var_30], 0
0x140010b9e  mov     [rsp+90h+pSid], rax; pSid
0x140010ba3  mov     eax, [rbp+1Fh+arg_50]
0x140010ba6  mov     [rsp+90h+nSubAuthority7], eax; nSubAuthority7
0x140010baa  mov     eax, [rbp+1Fh+arg_48]
0x140010bad  mov     [rsp+90h+nSubAuthority6], eax; nSubAuthority6
0x140010bb1  mov     eax, [rbp+1Fh+arg_40]
0x140010bb4  mov     [rsp+90h+nSubAuthority5], eax; nSubAuthority5
0x140010bb8  mov     eax, [rbp+1Fh+arg_38]
0x140010bbb  mov     [rsp+90h+nSubAuthority4], eax; nSubAuthority4
0x140010bbf  mov     eax, [rbp+1Fh+arg_30]
0x140010bc2  mov     [rsp+90h+nSubAuthority3], eax; nSubAuthority3
0x140010bc6  mov     eax, [rbp+1Fh+arg_28]
0x140010bc9  mov     [rsp+90h+nSubAuthority2], eax; nSubAuthority2
0x140010bcd  call    cs:__imp_AllocateAndInitializeSid
0x140010bd3  test    eax, eax
0x140010bd5  jnz     short loc_140010C13
0x140010bd7  call    HrGetLastFailure
0x140010bdc  mov     ebx, eax
0x140010bde  mov     rcx, cs:WPP_GLOBAL_Control
0x140010be5  lea     rax, WPP_GLOBAL_Control
0x140010bec  cmp     rcx, rax
0x140010bef  jz      short loc_140010C0F
0x140010bf1  test    byte ptr [rcx+1Ch], 1
0x140010bf5  jz      short loc_140010C0F
0x140010bf7  mov     rcx, [rcx+10h]
0x140010bfb  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010c02  mov     edx, 0Dh
0x140010c07  mov     r9d, ebx
0x140010c0a  call    WPP_SF_d
0x140010c0f  mov     eax, ebx
0x140010c11  jmp     short loc_140010C32
0x140010c13  mov     rdx, [rbp+1Fh+var_30]; void **
0x140010c17  mov     rcx, rbx; this
0x140010c1a  call    ?UtilDuplicateSid@CommonUtil@@YAJPEAPEAXPEAX@Z; CommonUtil::UtilDuplicateSid(void * *,void *)
0x140010c1f  mov     rcx, [rbp+1Fh+var_30]; pSid
0x140010c23  mov     ebx, eax
0x140010c25  call    cs:__imp_FreeSid
0x140010c2b  jmp     short loc_140010C0F
0x140010c2d  mov     eax, 80070057h
0x140010c32  mov     rcx, [rbp+1Fh+var_18]
0x140010c36  xor     rcx, rsp; StackCookie
0x140010c39  call    __security_check_cookie
0x140010c3e  add     rsp, 88h
0x140010c45  pop     rbx
0x140010c46  pop     rbp
0x140010c47  retn
```
