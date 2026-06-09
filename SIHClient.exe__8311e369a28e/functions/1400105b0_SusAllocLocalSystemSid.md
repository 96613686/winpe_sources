# SusAllocLocalSystemSid

- ea: `0x1400105b0`
- end: `0x140010690`
- name: `SusAllocLocalSystemSid`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140010698`

## callees

- `0x140008de4`
- `0x14001048c`
- `0x1400105b0`
- `0x14001096c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140010670`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140010670`

## string_xrefs

- `0x1400105d6`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x14001061b`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x140010653`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall SusAllocLocalSystemSid(_QWORD *a1)
{
  unsigned int v2; // ebx
  int Sid; // eax
  __int64 v4; // rdx
  PSID pSid; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a1 )
  {
    v2 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      (int)pSid);
    return v2;
  }
  pSid = 0;
  Sid = CreateSid((volatile signed __int64 *)&pSid, 1u, 0x12u, 0);
  v2 = Sid;
  if ( Sid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)(unsigned int)Sid,
      (int)pSid);
    v4 = 375;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)v2,
      (int)pSid);
    goto LABEL_9;
  }
  v2 = CopySidAlloc(pSid, a1);
  if ( (v2 & 0x80000000) != 0 )
  {
    v4 = 376;
    goto LABEL_7;
  }
  v2 = 0;
LABEL_9:
  if ( pSid )
    FreeSid(pSid);
  return v2;
}

```

## disassembly

```asm
0x1400105b0  mov     [rsp+arg_8], rbx
0x1400105b5  push    rdi
0x1400105b6  sub     rsp, 30h
0x1400105ba  mov     rax, cs:__security_cookie
0x1400105c1  xor     rax, rsp
0x1400105c4  mov     [rsp+38h+var_10], rax
0x1400105c9  mov     rdi, rcx
0x1400105cc  test    rcx, rcx
0x1400105cf  jnz     short loc_1400105F4
0x1400105d1  mov     rcx, [rsp+38h]; this
0x1400105d6  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400105dd  mov     ebx, 80004003h
0x1400105e2  mov     edx, 173h; void *
0x1400105e7  mov     r9d, ebx; char *
0x1400105ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400105ef  jmp     loc_140010676
0x1400105f4  xor     r9d, r9d
0x1400105f7  mov     [rsp+38h+pSid], 0; int
0x140010600  mov     dl, 1
0x140010602  lea     rcx, [rsp+38h+pSid]
0x140010607  lea     r8d, [r9+12h]
0x14001060b  call    CreateSid
0x140010610  mov     ebx, eax
0x140010612  test    eax, eax
0x140010614  jns     short loc_140010636
0x140010616  mov     rcx, [rsp+38h]; this
0x14001061b  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010622  mov     r9d, eax; char *
0x140010625  mov     edx, 19h; void *
0x14001062a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001062f  mov     edx, 177h
0x140010634  jmp     short loc_14001064E
0x140010636  mov     rcx, [rsp+38h+pSid]; pSourceSid
0x14001063b  mov     rdx, rdi
0x14001063e  call    CopySidAlloc
0x140010643  mov     ebx, eax
0x140010645  test    eax, eax
0x140010647  jns     short loc_140010664
0x140010649  mov     edx, 178h; void *
0x14001064e  mov     rcx, [rsp+38h]; this
0x140010653  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001065a  mov     r9d, ebx; char *
0x14001065d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010662  jmp     short loc_140010666
0x140010664  xor     ebx, ebx
0x140010666  mov     rcx, [rsp+38h+pSid]; pSid
0x14001066b  test    rcx, rcx
0x14001066e  jz      short loc_140010676
0x140010670  call    cs:__imp_FreeSid
0x140010676  mov     eax, ebx
0x140010678  mov     rcx, [rsp+38h+var_10]
0x14001067d  xor     rcx, rsp; StackCookie
0x140010680  call    __security_check_cookie
0x140010685  mov     rbx, [rsp+38h+arg_8]
0x14001068a  add     rsp, 30h
0x14001068e  pop     rdi
0x14001068f  retn
```
