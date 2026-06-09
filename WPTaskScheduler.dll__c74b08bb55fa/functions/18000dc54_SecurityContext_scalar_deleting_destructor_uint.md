# SecurityContext::`scalar deleting destructor'(uint)

- ea: `0x18000dc54`
- end: `0x18000dc8e`
- name: `??_GSecurityContext@@QEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(SecurityContext *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001ef0`
- `0x180003fa0`

## callees

- `0x180002c04`
- `0x180005400`
- `0x18000dc54`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc71`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc71`

## pseudocode

```c
SecurityContext *__fastcall SecurityContext::`scalar deleting destructor'(SecurityContext *this)
{
  void **v2; // rcx
  struct _APPCONTAINER_SECURITY_INFO *v3; // rcx

  v2 = *(void ***)this;
  if ( v2 )
    TsiFreeScheduleSid(v2);
  v3 = (struct _APPCONTAINER_SECURITY_INFO *)*((_QWORD *)this + 1);
  if ( v3 )
    TsiFreeAppContainerSecurityInfo(v3);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000dc54  push    rbx
0x18000dc56  sub     rsp, 20h
0x18000dc5a  mov     rbx, rcx
0x18000dc5d  mov     rcx, [rcx]; struct _SCHEDULE_SID *
0x18000dc60  test    rcx, rcx
0x18000dc63  jnz     short loc_18000DC80
0x18000dc65  mov     rcx, [rbx+8]; struct _APPCONTAINER_SECURITY_INFO *
0x18000dc69  test    rcx, rcx
0x18000dc6c  jnz     short loc_18000DC87
0x18000dc6e  mov     rcx, rbx
0x18000dc71  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dc77  mov     rax, rbx
0x18000dc7a  add     rsp, 20h
0x18000dc7e  pop     rbx
0x18000dc7f  retn
0x18000dc80  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x18000dc85  jmp     short loc_18000DC65
0x18000dc87  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x18000dc8c  jmp     short loc_18000DC6E
```
