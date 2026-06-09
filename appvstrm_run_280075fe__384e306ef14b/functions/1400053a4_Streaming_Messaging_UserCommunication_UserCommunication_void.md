# Streaming::Messaging::UserCommunication::~UserCommunication(void)

- ea: `0x1400053a4`
- end: `0x1400053e0`
- name: `??1UserCommunication@Messaging@Streaming@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(Streaming::Messaging::UserCommunication *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001044`
- `0x140001104`
- `0x140001204`

## callees

- `0x1400053a4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400053b6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400053b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053cd`

## pseudocode

```c
void __fastcall Streaming::Messaging::UserCommunication::~UserCommunication(
        Streaming::Messaging::UserCommunication *this)
{
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx

  v2 = (struct _ERESOURCE *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    ExDeleteResourceLite(v2);
    v3 = (void *)*((_QWORD *)this + 3);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
  }
}

```

## disassembly

```asm
0x1400053a4  push    rbx
0x1400053a6  sub     rsp, 20h
0x1400053aa  mov     rbx, rcx
0x1400053ad  mov     rcx, [rcx+18h]; Resource
0x1400053b1  test    rcx, rcx
0x1400053b4  jz      short loc_1400053D9
0x1400053b6  call    cs:__imp_ExDeleteResourceLite
0x1400053bd  nop     dword ptr [rax+rax+00h]
0x1400053c2  mov     rcx, [rbx+18h]; P
0x1400053c6  test    rcx, rcx
0x1400053c9  jz      short loc_1400053D9
0x1400053cb  xor     edx, edx; Tag
0x1400053cd  call    cs:__imp_ExFreePoolWithTag
0x1400053d4  nop     dword ptr [rax+rax+00h]
0x1400053d9  add     rsp, 20h
0x1400053dd  pop     rbx
0x1400053de  retn
```
