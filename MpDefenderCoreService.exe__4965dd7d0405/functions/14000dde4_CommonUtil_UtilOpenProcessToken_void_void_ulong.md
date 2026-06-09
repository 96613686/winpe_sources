# CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)

- ea: `0x14000dde4`
- end: `0x14000de79`
- name: `?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z`
- size: `149`
- prototype: `int(CommonUtil *__hidden this, void **, void *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140088000`
- `0x14008a040`

## callees

- `0x14000dde4`
- `0x140017738`
- `0x14003a5c0`
- `0x14007d210`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14000de16`
- `ADVAPI32!OpenProcessToken` at `0x14000de16`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilOpenProcessToken(CommonUtil *this, void **a2, void *a3)
{
  unsigned int LastFailure; // ebx
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  if ( OpenProcessToken(a2, (DWORD)a3, &TokenHandle) )
  {
    *(_QWORD *)this = TokenHandle;
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_02054f1da1d13c5db2ae787d1a5da12f_Traceguids, LastFailure);
    return LastFailure;
  }
}

```

## disassembly

```asm
0x14000dde4  push    rbx
0x14000dde6  sub     rsp, 30h
0x14000ddea  mov     rax, cs:__security_cookie
0x14000ddf1  xor     rax, rsp
0x14000ddf4  mov     [rsp+38h+var_10], rax
0x14000ddf9  mov     r9d, r8d
0x14000ddfc  mov     [rsp+38h+TokenHandle], 0
0x14000de05  mov     rax, rdx
0x14000de08  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x14000de0d  mov     rbx, rcx
0x14000de10  mov     edx, r9d; DesiredAccess
0x14000de13  mov     rcx, rax; ProcessHandle
0x14000de16  call    cs:__imp_OpenProcessToken
0x14000de1c  test    eax, eax
0x14000de1e  jnz     short loc_14000DE5C
0x14000de20  call    HrGetLastFailure
0x14000de25  mov     ebx, eax
0x14000de27  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de2e  lea     rax, WPP_GLOBAL_Control
0x14000de35  cmp     rcx, rax
0x14000de38  jz      short loc_14000DE58
0x14000de3a  test    byte ptr [rcx+1Ch], 1
0x14000de3e  jz      short loc_14000DE58
0x14000de40  mov     rcx, [rcx+10h]
0x14000de44  lea     r8, WPP_02054f1da1d13c5db2ae787d1a5da12f_Traceguids
0x14000de4b  mov     edx, 0Eh
0x14000de50  mov     r9d, ebx
0x14000de53  call    WPP_SF_d
0x14000de58  mov     eax, ebx
0x14000de5a  jmp     short loc_14000DE66
0x14000de5c  mov     rax, [rsp+38h+TokenHandle]
0x14000de61  mov     [rbx], rax
0x14000de64  xor     eax, eax
0x14000de66  mov     rcx, [rsp+38h+var_10]
0x14000de6b  xor     rcx, rsp; StackCookie
0x14000de6e  call    __security_check_cookie
0x14000de73  add     rsp, 30h
0x14000de77  pop     rbx
0x14000de78  retn
```
