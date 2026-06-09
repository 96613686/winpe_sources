# Streaming::Messaging::UserCommunication::InitializeConnection(appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete> &,_UNICODE_STRING &,bool)

- ea: `0x140013d84`
- end: `0x140013e75`
- name: `?InitializeConnection@UserCommunication@Messaging@Streaming@@SAJAEAV?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@AEAU_UNICODE_STRING@@_N@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001204`

## callees

- `0x140001044`
- `0x140013c74`
- `0x140013d84`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140013e0b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140013e0b`
- `ntoskrnl!ExAllocatePool2` at `0x140013daf`
- `ntoskrnl!ExAllocatePool2` at `0x140013dec`
- `ntoskrnl!ExAllocatePool2` at `0x140013daf`
- `ntoskrnl!ExAllocatePool2` at `0x140013dec`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::UserCommunication::InitializeConnection(
        Streaming::Messaging::UserCommunication **a1,
        struct _UNICODE_STRING *a2,
        char a3)
{
  __int64 Pool2; // rax
  __int64 v7; // rdi
  struct _ERESOURCE *v8; // rax
  int v9; // ebx
  Streaming::Messaging::UserCommunication *v11; // [rsp+58h] [rbp+20h] BYREF

  Pool2 = ExAllocatePool2(64, 40, 1684891251);
  v7 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_DWORD *)(Pool2 + 16) = 1684891251;
    *(_QWORD *)(Pool2 + 24) = 0;
    v8 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1684891251);
    *(_QWORD *)(v7 + 24) = v8;
    if ( v8 )
      v9 = ExInitializeResourceLite(v8);
    else
      v9 = -1073741670;
    *(_BYTE *)(v7 + 32) = 0;
    v11 = (Streaming::Messaging::UserCommunication *)v7;
    if ( v9 >= 0 )
    {
      v9 = Streaming::Messaging::UserCommunication::Initialize((PFLT_PORT *)v7, a2, a3);
      if ( v9 >= 0 )
      {
        v11 = *a1;
        *a1 = (Streaming::Messaging::UserCommunication *)v7;
      }
    }
  }
  else
  {
    v11 = 0;
    v9 = -1073741670;
  }
  appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(&v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140013d84  mov     [rsp+arg_0], rbx
0x140013d89  mov     [rsp+arg_8], rbp
0x140013d8e  push    rsi
0x140013d8f  push    rdi
0x140013d90  push    r14
0x140013d92  sub     rsp, 20h
0x140013d96  mov     r14, rdx
0x140013d99  mov     bpl, r8b
0x140013d9c  mov     edx, 28h ; '('
0x140013da1  mov     rsi, rcx
0x140013da4  mov     ebx, 646D6673h
0x140013da9  mov     r8d, ebx
0x140013dac  lea     ecx, [rdx+18h]
0x140013daf  call    cs:__imp_ExAllocatePool2
0x140013db6  nop     dword ptr [rax+rax+00h]
0x140013dbb  mov     rdi, rax
0x140013dbe  test    rax, rax
0x140013dc1  jz      loc_140013E47
0x140013dc7  mov     edx, 68h ; 'h'
0x140013dcc  mov     qword ptr [rax], 0
0x140013dd3  mov     qword ptr [rax+8], 0
0x140013ddb  mov     r8d, ebx
0x140013dde  mov     [rax+10h], ebx
0x140013de1  mov     qword ptr [rax+18h], 0
0x140013de9  lea     ecx, [rdx-28h]
0x140013dec  call    cs:__imp_ExAllocatePool2
0x140013df3  nop     dword ptr [rax+rax+00h]
0x140013df8  mov     [rdi+18h], rax
0x140013dfc  test    rax, rax
0x140013dff  jnz     short loc_140013E08
0x140013e01  mov     ebx, 0C000009Ah
0x140013e06  jmp     short loc_140013E19
0x140013e08  mov     rcx, rax; Resource
0x140013e0b  call    cs:__imp_ExInitializeResourceLite
0x140013e12  nop     dword ptr [rax+rax+00h]
0x140013e17  mov     ebx, eax
0x140013e19  mov     byte ptr [rdi+20h], 0
0x140013e1d  mov     [rsp+38h+arg_18], rdi
0x140013e22  test    ebx, ebx
0x140013e24  js      short loc_140013E55
0x140013e26  mov     r8b, bpl; bool
0x140013e29  mov     rdx, r14; struct _UNICODE_STRING *
0x140013e2c  mov     rcx, rdi; ServerPort
0x140013e2f  call    ?Initialize@UserCommunication@Messaging@Streaming@@QEAAJAEAU_UNICODE_STRING@@_N@Z; Streaming::Messaging::UserCommunication::Initialize(_UNICODE_STRING &,bool)
0x140013e34  mov     ebx, eax
0x140013e36  test    eax, eax
0x140013e38  js      short loc_140013E55
0x140013e3a  mov     rax, [rsi]
0x140013e3d  mov     [rsp+38h+arg_18], rax
0x140013e42  mov     [rsi], rdi
0x140013e45  jmp     short loc_140013E55
0x140013e47  mov     [rsp+38h+arg_18], 0
0x140013e50  mov     ebx, 0C000009Ah
0x140013e55  lea     rcx, [rsp+38h+arg_18]
0x140013e5a  call    ??1?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(void)
0x140013e5f  mov     rbp, [rsp+38h+arg_8]
0x140013e64  mov     eax, ebx
0x140013e66  mov     rbx, [rsp+38h+arg_0]
0x140013e6b  add     rsp, 20h
0x140013e6f  pop     r14
0x140013e71  pop     rdi
0x140013e72  pop     rsi
0x140013e73  retn
```
