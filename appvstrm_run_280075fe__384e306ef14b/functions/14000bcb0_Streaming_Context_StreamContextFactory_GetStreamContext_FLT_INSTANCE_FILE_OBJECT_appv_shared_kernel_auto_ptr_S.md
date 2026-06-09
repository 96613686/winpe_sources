# Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x14000bcb0`
- end: `0x14000bd2e`
- name: `?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `126`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400018d0`
- `0x140001980`
- `0x140001c70`
- `0x140001ce0`
- `0x14000ba94`
- `0x14000bbd4`
- `0x140013160`

## callees

- `0x14000bcb0`

## import_xrefs

- `FLTMGR!FltGetStreamContext` at `0x14000bccb`
- `FLTMGR!FltGetStreamContext` at `0x14000bccb`
- `FLTMGR!FltReleaseContext` at `0x14000bcf1`
- `FLTMGR!FltReleaseContext` at `0x14000bd14`
- `FLTMGR!FltReleaseContext` at `0x14000bcf1`
- `FLTMGR!FltReleaseContext` at `0x14000bd14`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamContextFactory::GetStreamContext(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        PFLT_CONTEXT *a3)
{
  NTSTATUS StreamContext; // edi
  PFLT_CONTEXT v5; // rcx
  PFLT_CONTEXT v6; // rax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+20h] BYREF

  Context = 0;
  StreamContext = FltGetStreamContext(a1, a2, &Context);
  if ( StreamContext >= 0 )
  {
    v6 = Context;
    if ( *(_BYTE *)Context )
    {
      FltReleaseContext(Context);
      return 3221225658LL;
    }
    v5 = *a3;
    Context = *a3;
    *a3 = v6;
  }
  else
  {
    v5 = Context;
  }
  if ( v5 )
    FltReleaseContext(v5);
  return (unsigned int)StreamContext;
}

```

## disassembly

```asm
0x14000bcb0  mov     [rsp+arg_0], rbx
0x14000bcb5  push    rdi
0x14000bcb6  sub     rsp, 20h
0x14000bcba  mov     rbx, r8
0x14000bcbd  mov     [rsp+28h+Context], 0
0x14000bcc6  lea     r8, [rsp+28h+Context]; Context
0x14000bccb  call    cs:__imp_FltGetStreamContext
0x14000bcd2  nop     dword ptr [rax+rax+00h]
0x14000bcd7  mov     edi, eax
0x14000bcd9  test    eax, eax
0x14000bcdb  jns     short loc_14000BCE4
0x14000bcdd  mov     rcx, [rsp+28h+Context]
0x14000bce2  jmp     short loc_14000BD0F
0x14000bce4  mov     rax, [rsp+28h+Context]
0x14000bce9  cmp     byte ptr [rax], 0
0x14000bcec  jz      short loc_14000BD04
0x14000bcee  mov     rcx, rax; Context
0x14000bcf1  call    cs:__imp_FltReleaseContext
0x14000bcf8  nop     dword ptr [rax+rax+00h]
0x14000bcfd  mov     eax, 0C00000BAh
0x14000bd02  jmp     short loc_14000BD22
0x14000bd04  mov     rcx, [rbx]; Context
0x14000bd07  mov     [rsp+28h+Context], rcx
0x14000bd0c  mov     [rbx], rax
0x14000bd0f  test    rcx, rcx
0x14000bd12  jz      short loc_14000BD20
0x14000bd14  call    cs:__imp_FltReleaseContext
0x14000bd1b  nop     dword ptr [rax+rax+00h]
0x14000bd20  mov     eax, edi
0x14000bd22  mov     rbx, [rsp+28h+arg_0]
0x14000bd27  add     rsp, 20h
0x14000bd2b  pop     rdi
0x14000bd2c  retn
```
