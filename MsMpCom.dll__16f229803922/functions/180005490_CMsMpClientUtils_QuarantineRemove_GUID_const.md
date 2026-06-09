# CMsMpClientUtils::QuarantineRemove(_GUID const &)

- ea: `0x180005490`
- end: `0x18000551f`
- name: `?QuarantineRemove@CMsMpClientUtils@@UEAAJAEBU_GUID@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(CMsMpClientUtils *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005490`
- `0x180005b0c`
- `0x180009440`

## import_xrefs

- `mpclient!MpQuarantineRequest` at `0x180005501`
- `mpclient!MpQuarantineRequest` at `0x180005501`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CMsMpClientUtils::QuarantineRemove(CMsMpClientUtils *this, const struct _GUID *a2)
{
  __int64 v4; // rcx
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  v4 = *((_QWORD *)this + 1);
  v6 = (__int128)*a2;
  return MpQuarantineRequest(v4, &v6, 1);
}

```

## disassembly

```asm
0x180005490  mov     [rsp+arg_10], rbx
0x180005495  push    rdi
0x180005496  sub     rsp, 50h
0x18000549a  mov     rax, cs:__security_cookie
0x1800054a1  xor     rax, rsp
0x1800054a4  mov     [rsp+58h+var_18], rax
0x1800054a9  mov     rdi, rdx
0x1800054ac  mov     rbx, rcx
0x1800054af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054b6  lea     rax, WPP_GLOBAL_Control
0x1800054bd  cmp     rcx, rax
0x1800054c0  jz      short loc_1800054DF
0x1800054c2  test    byte ptr [rcx+1Ch], 8
0x1800054c6  jz      short loc_1800054DF
0x1800054c8  mov     rcx, [rcx+10h]
0x1800054cc  lea     rax, [rbx-40h]
0x1800054d0  mov     edx, 0Bh
0x1800054d5  mov     [rsp+58h+var_38], rax
0x1800054da  call    WPP_SF_sq
0x1800054df  movups  xmm0, xmmword ptr [rdi]
0x1800054e2  mov     rcx, [rbx+8]
0x1800054e6  lea     rdx, [rsp+58h+var_28]
0x1800054eb  xor     r9d, r9d
0x1800054ee  mov     [rsp+58h+var_38], 0
0x1800054f7  movdqu  [rsp+58h+var_28], xmm0
0x1800054fd  lea     r8d, [r9+1]
0x180005501  call    cs:__imp_MpQuarantineRequest
0x180005507  mov     rcx, [rsp+58h+var_18]
0x18000550c  xor     rcx, rsp; StackCookie
0x18000550f  call    __security_check_cookie
0x180005514  mov     rbx, [rsp+58h+arg_10]
0x180005519  add     rsp, 50h
0x18000551d  pop     rdi
0x18000551e  retn
```
