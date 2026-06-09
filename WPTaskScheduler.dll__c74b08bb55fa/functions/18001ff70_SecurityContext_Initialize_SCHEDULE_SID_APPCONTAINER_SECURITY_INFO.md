# SecurityContext::Initialize(_SCHEDULE_SID *,_APPCONTAINER_SECURITY_INFO *)

- ea: `0x18001ff70`
- end: `0x18001ffb9`
- name: `?Initialize@SecurityContext@@QEAAJPEAU_SCHEDULE_SID@@PEAU_APPCONTAINER_SECURITY_INFO@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(SecurityContext *__hidden this, struct _SCHEDULE_SID *, struct _APPCONTAINER_SECURITY_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003fa0`

## callees

- `0x18001ff70`
- `0x18002005c`
- `0x1800201a8`

## pseudocode

```c
__int64 __fastcall SecurityContext::Initialize(
        SecurityContext *this,
        struct _SCHEDULE_SID *a2,
        struct _APPCONTAINER_SECURITY_INFO *a3)
{
  if ( *((_BYTE *)this + 16) )
    return 2147500036LL;
  if ( a2 )
    TsiCreateUserSid();
  if ( a3 )
    TsiCreateAppContainerSecurityInfo((char *)this + 8, a3);
  *((_BYTE *)this + 16) = 1;
  return 0;
}

```

## disassembly

```asm
0x18001ff70  mov     [rsp+arg_0], rbx
0x18001ff75  push    rdi
0x18001ff76  sub     rsp, 20h
0x18001ff7a  cmp     byte ptr [rcx+10h], 0
0x18001ff7e  mov     rdi, r8
0x18001ff81  mov     rbx, rcx
0x18001ff84  jz      short loc_18001FF8D
0x18001ff86  mov     eax, 80004004h
0x18001ff8b  jmp     short loc_18001FFAE
0x18001ff8d  test    rdx, rdx
0x18001ff90  jz      short loc_18001FF97
0x18001ff92  call    TsiCreateUserSid
0x18001ff97  test    rdi, rdi
0x18001ff9a  jz      short loc_18001FFA8
0x18001ff9c  lea     rcx, [rbx+8]
0x18001ffa0  mov     rdx, rdi
0x18001ffa3  call    TsiCreateAppContainerSecurityInfo
0x18001ffa8  mov     byte ptr [rbx+10h], 1
0x18001ffac  xor     eax, eax
0x18001ffae  mov     rbx, [rsp+28h+arg_0]
0x18001ffb3  add     rsp, 20h
0x18001ffb7  pop     rdi
0x18001ffb8  retn
```
