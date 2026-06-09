# Windows::Sms::Common::recursive_mutex::`scalar deleting destructor'(uint)

- ea: `0x18000f340`
- end: `0x18000f383`
- name: `??_Grecursive_mutex@Common@Sms@Windows@@UEAAPEAXI@Z`
- size: `67`
- prototype: `Windows::Sms::Common::recursive_mutex *__fastcall(Windows::Sms::Common::recursive_mutex *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003f50`
- `0x18000f340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f35d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f35d`

## pseudocode

```c
Windows::Sms::Common::recursive_mutex *__fastcall Windows::Sms::Common::recursive_mutex::`scalar deleting destructor'(
        Windows::Sms::Common::recursive_mutex *this,
        char a2)
{
  *(_QWORD *)this = &Windows::Sms::Common::recursive_mutex::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000f340  mov     [rsp+arg_0], rbx
0x18000f345  push    rdi
0x18000f346  sub     rsp, 20h
0x18000f34a  lea     rax, ??_7recursive_mutex@Common@Sms@Windows@@6B@; const Windows::Sms::Common::recursive_mutex::`vftable'
0x18000f351  mov     rdi, rcx
0x18000f354  mov     [rcx], rax
0x18000f357  mov     ebx, edx
0x18000f359  add     rcx, 8; lpCriticalSection
0x18000f35d  call    cs:__imp_DeleteCriticalSection
0x18000f363  test    bl, 1
0x18000f366  jz      short loc_18000F375
0x18000f368  mov     edx, 30h ; '0'
0x18000f36d  mov     rcx, rdi; Block
0x18000f370  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f375  mov     rbx, [rsp+28h+arg_0]
0x18000f37a  mov     rax, rdi
0x18000f37d  add     rsp, 20h
0x18000f381  pop     rdi
0x18000f382  retn
```
