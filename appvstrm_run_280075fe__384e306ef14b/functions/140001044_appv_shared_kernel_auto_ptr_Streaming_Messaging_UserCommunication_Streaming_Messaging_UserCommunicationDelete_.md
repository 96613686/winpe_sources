# appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(void)

- ea: `0x140001044`
- end: `0x1400010a8`
- name: `??1?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001104`
- `0x140013d84`

## callees

- `0x140001044`
- `0x1400053a4`
- `0x140013a18`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001089`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001089`
- `FLTMGR!FltCloseCommunicationPort` at `0x140001069`
- `FLTMGR!FltCloseCommunicationPort` at `0x140001069`

## pseudocode

```c
void __fastcall appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(
        Streaming::Messaging::UserCommunication **a1)
{
  Streaming::Messaging::UserCommunication *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Streaming::Messaging::UserCommunication::DisconnectClient(*a1);
    if ( *(_QWORD *)v1 )
    {
      FltCloseCommunicationPort(*(PFLT_PORT *)v1);
      *(_QWORD *)v1 = 0;
    }
    Streaming::Messaging::UserCommunication::~UserCommunication(v1);
    ExFreePoolWithTag(v1, 0);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140001044  mov     [rsp+arg_0], rbx
0x140001049  push    rdi
0x14000104a  sub     rsp, 20h
0x14000104e  mov     rbx, [rcx]
0x140001051  mov     rdi, rcx
0x140001054  test    rbx, rbx
0x140001057  jz      short loc_14000109C
0x140001059  mov     rcx, rbx; this
0x14000105c  call    ?DisconnectClient@UserCommunication@Messaging@Streaming@@QEAAXXZ; Streaming::Messaging::UserCommunication::DisconnectClient(void)
0x140001061  mov     rcx, [rbx]; ServerPort
0x140001064  test    rcx, rcx
0x140001067  jz      short loc_14000107C
0x140001069  call    cs:__imp_FltCloseCommunicationPort
0x140001070  nop     dword ptr [rax+rax+00h]
0x140001075  mov     qword ptr [rbx], 0
0x14000107c  mov     rcx, rbx; this
0x14000107f  call    ??1UserCommunication@Messaging@Streaming@@QEAA@XZ; Streaming::Messaging::UserCommunication::~UserCommunication(void)
0x140001084  xor     edx, edx; Tag
0x140001086  mov     rcx, rbx; P
0x140001089  call    cs:__imp_ExFreePoolWithTag
0x140001090  nop     dword ptr [rax+rax+00h]
0x140001095  mov     qword ptr [rdi], 0
0x14000109c  mov     rbx, [rsp+28h+arg_0]
0x1400010a1  add     rsp, 20h
0x1400010a5  pop     rdi
0x1400010a6  retn
```
