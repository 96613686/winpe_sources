# Streaming::StrmPreMDLRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140001c70`
- end: `0x140001cd1`
- name: `?StrmPreMDLRead@Streaming@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `97`
- prototype: `__int64 __fastcall(Streaming *this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001c70`
- `0x14000bcb0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140001cb0`
- `FLTMGR!FltReleaseContext` at `0x140001cb0`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPreMDLRead(
        Streaming *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        void **a4)
{
  struct _FILE_OBJECT *Information; // rdx
  struct _FLT_INSTANCE *Pointer; // rcx
  bool v7; // bl
  __int64 result; // rax
  PFLT_CONTEXT Context; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 1;
  Information = (struct _FILE_OBJECT *)a2->IoStatus.Information;
  if ( !Information )
    return 1;
  Pointer = (struct _FLT_INSTANCE *)a2->IoStatus.Pointer;
  Context = 0;
  v7 = (int)Streaming::Context::StreamContextFactory::GetStreamContext(Pointer, Information, &Context) >= 0;
  if ( Context )
    FltReleaseContext(Context);
  result = 3;
  if ( !v7 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140001c70  push    rbx
0x140001c72  sub     rsp, 20h
0x140001c76  mov     rax, rdx
0x140001c79  test    rdx, rdx
0x140001c7c  jz      short loc_140001CC5
0x140001c7e  mov     rdx, [rdx+20h]
0x140001c82  test    rdx, rdx
0x140001c85  jz      short loc_140001CC5
0x140001c87  mov     rcx, [rax+18h]
0x140001c8b  lea     r8, [rsp+28h+Context]
0x140001c90  mov     [rsp+28h+Context], 0
0x140001c99  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140001c9e  mov     rcx, [rsp+28h+Context]; Context
0x140001ca3  mov     ebx, eax
0x140001ca5  shr     ebx, 1Fh
0x140001ca8  xor     bl, 1
0x140001cab  test    rcx, rcx
0x140001cae  jz      short loc_140001CBC
0x140001cb0  call    cs:__imp_FltReleaseContext
0x140001cb7  nop     dword ptr [rax+rax+00h]
0x140001cbc  mov     eax, 3
0x140001cc1  test    bl, bl
0x140001cc3  jnz     short loc_140001CCA
0x140001cc5  mov     eax, 1
0x140001cca  add     rsp, 20h
0x140001cce  pop     rbx
0x140001ccf  retn
```
