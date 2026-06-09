# Streaming::StrmPreRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140001ce0`
- end: `0x140001d87`
- name: `?StrmPreRead@Streaming@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(Streaming *this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001ce0`
- `0x140009d98`
- `0x14000bcb0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140001d2f`
- `FLTMGR!FltReleaseContext` at `0x140001d61`
- `FLTMGR!FltReleaseContext` at `0x140001d2f`
- `FLTMGR!FltReleaseContext` at `0x140001d61`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPreRead(
        Streaming *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        void **a4)
{
  ULONG_PTR Information; // rbx
  struct _FLT_INSTANCE *Pointer; // rsi
  unsigned int File; // ebx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  if ( !this )
    return 1;
  if ( !a2 )
    return 1;
  Information = a2->IoStatus.Information;
  if ( !Information )
    return 1;
  Pointer = (struct _FLT_INSTANCE *)a2->IoStatus.Pointer;
  Context = 0;
  if ( (int)Streaming::Context::StreamContextFactory::GetStreamContext(Pointer, Information, &Context) >= 0 )
  {
    File = Streaming::Reader::ReadFile(Pointer);
    if ( Context )
      FltReleaseContext(Context);
  }
  else
  {
    if ( Context )
      FltReleaseContext(Context);
    return 1;
  }
  return File;
}

```

## disassembly

```asm
0x140001ce0  mov     rax, rsp
0x140001ce3  mov     [rax+10h], rbx
0x140001ce7  mov     [rax+18h], rsi
0x140001ceb  push    rdi
0x140001cec  sub     rsp, 20h
0x140001cf0  mov     rdi, rcx
0x140001cf3  test    rcx, rcx
0x140001cf6  jz      short loc_140001D71
0x140001cf8  test    rdx, rdx
0x140001cfb  jz      short loc_140001D71
0x140001cfd  mov     rbx, [rdx+20h]
0x140001d01  test    rbx, rbx
0x140001d04  jz      short loc_140001D71
0x140001d06  mov     rsi, [rdx+18h]
0x140001d0a  lea     r8, [rax+8]
0x140001d0e  mov     rcx, rsi
0x140001d11  mov     qword ptr [rax+8], 0
0x140001d19  mov     rdx, rbx
0x140001d1c  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140001d21  test    eax, eax
0x140001d23  jns     short loc_140001D42
0x140001d25  mov     rcx, [rsp+28h+Context]; Context
0x140001d2a  test    rcx, rcx
0x140001d2d  jz      short loc_140001D3B
0x140001d2f  call    cs:__imp_FltReleaseContext
0x140001d36  nop     dword ptr [rax+rax+00h]
0x140001d3b  mov     ebx, 1
0x140001d40  jmp     short loc_140001D6D
0x140001d42  lea     r9, [rsp+28h+Context]
0x140001d47  mov     r8, rdi
0x140001d4a  mov     rdx, rbx
0x140001d4d  mov     rcx, rsi; struct _FLT_INSTANCE *
0x140001d50  call    ?ReadFile@Reader@Streaming@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Reader::ReadFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140001d55  mov     rcx, [rsp+28h+Context]; Context
0x140001d5a  mov     ebx, eax
0x140001d5c  test    rcx, rcx
0x140001d5f  jz      short loc_140001D6D
0x140001d61  call    cs:__imp_FltReleaseContext
0x140001d68  nop     dword ptr [rax+rax+00h]
0x140001d6d  mov     eax, ebx
0x140001d6f  jmp     short loc_140001D76
0x140001d71  mov     eax, 1
0x140001d76  mov     rbx, [rsp+28h+arg_8]
0x140001d7b  mov     rsi, [rsp+28h+arg_10]
0x140001d80  add     rsp, 20h
0x140001d84  pop     rdi
0x140001d85  retn
```
