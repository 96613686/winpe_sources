# Streaming::StrmFltInterface::WriteFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &)

- ea: `0x140013160`
- end: `0x1400131f3`
- name: `?WriteFile@StrmFltInterface@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@@Z`
- size: `147`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS(Streaming::StrmFltInterface *__hidden this, struct _FLT_INSTANCE *, struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001a50`
- `0x140001c00`
- `0x140001d90`

## callees

- `0x14000bcb0`
- `0x140013160`
- `0x140014ff0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400131a2`
- `FLTMGR!FltReleaseContext` at `0x1400131d4`
- `FLTMGR!FltReleaseContext` at `0x1400131a2`
- `FLTMGR!FltReleaseContext` at `0x1400131d4`

## pseudocode

```c
__int64 __fastcall Streaming::StrmFltInterface::WriteFile(
        Streaming::StrmFltInterface *this,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_CALLBACK_DATA *a4)
{
  unsigned int v8; // ebx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  Context = 0;
  if ( (int)Streaming::Context::StreamContextFactory::GetStreamContext(a2, a3, &Context) >= 0 )
  {
    v8 = Streaming::Writer::WriteFile(a2, (__int64)a3, (__int64)a4, (__int64)&Context);
    if ( Context )
      FltReleaseContext(Context);
    return v8;
  }
  else
  {
    if ( Context )
      FltReleaseContext(Context);
    return 1;
  }
}

```

## disassembly

```asm
0x140013160  mov     rax, rsp
0x140013163  mov     [rax+10h], rbx
0x140013167  mov     [rax+18h], rsi
0x14001316b  mov     [rax+8], rcx
0x14001316f  push    rdi
0x140013170  sub     rsp, 20h
0x140013174  mov     rbx, r8
0x140013177  mov     qword ptr [rax+8], 0
0x14001317f  mov     rdi, rdx
0x140013182  lea     r8, [rax+8]
0x140013186  mov     rdx, rbx
0x140013189  mov     rcx, rdi
0x14001318c  mov     rsi, r9
0x14001318f  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140013194  test    eax, eax
0x140013196  jns     short loc_1400131B5
0x140013198  mov     rcx, [rsp+28h+Context]; Context
0x14001319d  test    rcx, rcx
0x1400131a0  jz      short loc_1400131AE
0x1400131a2  call    cs:__imp_FltReleaseContext
0x1400131a9  nop     dword ptr [rax+rax+00h]
0x1400131ae  mov     eax, 1
0x1400131b3  jmp     short loc_1400131E2
0x1400131b5  lea     r9, [rsp+28h+Context]
0x1400131ba  mov     r8, rsi
0x1400131bd  mov     rdx, rbx
0x1400131c0  mov     rcx, rdi; struct _FLT_INSTANCE *
0x1400131c3  call    ?WriteFile@Writer@Streaming@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Writer::WriteFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x1400131c8  mov     rcx, [rsp+28h+Context]; Context
0x1400131cd  mov     ebx, eax
0x1400131cf  test    rcx, rcx
0x1400131d2  jz      short loc_1400131E0
0x1400131d4  call    cs:__imp_FltReleaseContext
0x1400131db  nop     dword ptr [rax+rax+00h]
0x1400131e0  mov     eax, ebx
0x1400131e2  mov     rbx, [rsp+28h+arg_8]
0x1400131e7  mov     rsi, [rsp+28h+arg_10]
0x1400131ec  add     rsp, 20h
0x1400131f0  pop     rdi
0x1400131f1  retn
```
