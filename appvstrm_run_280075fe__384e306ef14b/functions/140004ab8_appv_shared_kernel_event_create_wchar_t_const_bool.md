# appv::shared::kernel::event::create(wchar_t const *,bool)

- ea: `0x140004ab8`
- end: `0x140004b72`
- name: `?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(appv::shared::kernel::event *__hidden this, const wchar_t *, bool)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ef8`
- `0x140006710`
- `0x140006864`
- `0x14000e088`
- `0x14000e1dc`
- `0x14000f078`
- `0x14000f244`

## callees

- `0x140004ab8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140004aed`
- `ntoskrnl!ZwClose` at `0x140004aed`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140004b39`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140004b39`
- `ntoskrnl!KeClearEvent` at `0x140004b58`
- `ntoskrnl!KeClearEvent` at `0x140004b58`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004b25`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004b25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ad5`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::event::create(appv::shared::kernel::event *this, const wchar_t *a2)
{
  void *v3; // rcx
  void **v4; // rdi
  void *v5; // rcx
  struct _KEVENT *v6; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    if ( *(_BYTE *)this )
      ExFreePoolWithTag(v3, 0);
    v4 = (void **)((char *)this + 16);
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
      ZwClose(v5);
    *((_QWORD *)this + 1) = 0;
    *v4 = 0;
  }
  else
  {
    v4 = (void **)((char *)this + 16);
  }
  *(_BYTE *)this = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, &SourceString);
  v6 = IoCreateNotificationEvent(&DestinationString, v4);
  *((_QWORD *)this + 1) = v6;
  if ( !v6 )
    return 3221225626LL;
  KeClearEvent(v6);
  return 0;
}

```

## disassembly

```asm
0x140004ab8  mov     [rsp+arg_0], rbx
0x140004abd  push    rdi
0x140004abe  sub     rsp, 30h
0x140004ac2  mov     rbx, rcx
0x140004ac5  mov     rcx, [rcx+8]; P
0x140004ac9  test    rcx, rcx
0x140004acc  jz      short loc_140004B0A
0x140004ace  cmp     byte ptr [rbx], 0
0x140004ad1  jz      short loc_140004AE1
0x140004ad3  xor     edx, edx; Tag
0x140004ad5  call    cs:__imp_ExFreePoolWithTag
0x140004adc  nop     dword ptr [rax+rax+00h]
0x140004ae1  lea     rdi, [rbx+10h]
0x140004ae5  mov     rcx, [rdi]; Handle
0x140004ae8  test    rcx, rcx
0x140004aeb  jz      short loc_140004AF9
0x140004aed  call    cs:__imp_ZwClose
0x140004af4  nop     dword ptr [rax+rax+00h]
0x140004af9  mov     qword ptr [rbx+8], 0
0x140004b01  mov     qword ptr [rdi], 0
0x140004b08  jmp     short loc_140004B0E
0x140004b0a  lea     rdi, [rbx+10h]
0x140004b0e  xorps   xmm0, xmm0
0x140004b11  mov     byte ptr [rbx], 0
0x140004b14  lea     rdx, SourceString; SourceString
0x140004b1b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140004b20  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140004b25  call    cs:__imp_RtlInitUnicodeString
0x140004b2c  nop     dword ptr [rax+rax+00h]
0x140004b31  mov     rdx, rdi; EventHandle
0x140004b34  lea     rcx, [rsp+38h+DestinationString]; EventName
0x140004b39  call    cs:__imp_IoCreateNotificationEvent
0x140004b40  nop     dword ptr [rax+rax+00h]
0x140004b45  mov     [rbx+8], rax
0x140004b49  test    rax, rax
0x140004b4c  jnz     short loc_140004B55
0x140004b4e  mov     eax, 0C000009Ah
0x140004b53  jmp     short loc_140004B66
0x140004b55  mov     rcx, rax; Event
0x140004b58  call    cs:__imp_KeClearEvent
0x140004b5f  nop     dword ptr [rax+rax+00h]
0x140004b64  xor     eax, eax
0x140004b66  mov     rbx, [rsp+38h+arg_0]
0x140004b6b  add     rsp, 30h
0x140004b6f  pop     rdi
0x140004b70  retn
```
