# Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)

- ea: `0x140005e3c`
- end: `0x140005ecf`
- name: `?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z`
- size: `147`
- prototype: `int(Streaming::InstanceContextFactory *__hidden this, struct _FLT_INSTANCE *, struct Streaming::InstanceContext *)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x140005640`
- `0x1400075d0`
- `0x1400078a0`
- `0x140009d98`
- `0x14000a310`
- `0x14000b748`
- `0x14000ba94`
- `0x14000be10`
- `0x14000f078`
- `0x140012b18`
- `0x140014ff0`

## callees

- `0x140005e3c`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltGetInstanceContext` at `0x140005e4c`
- `FLTMGR!FltGetInstanceContext` at `0x140005e4c`

## pseudocode

```c
__int64 __fastcall Streaming::InstanceContextFactory::GetContext(
        Streaming::InstanceContextFactory *this,
        struct _FLT_INSTANCE *a2,
        PFLT_CONTEXT *a3)
{
  NTSTATUS InstanceContext; // edi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v5; // rbx
  GUID *v7; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  InstanceContext = FltGetInstanceContext(a2, a3);
  if ( InstanceContext < 0 )
  {
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v7);
    LogWrite(
      1,
      *CurrentActivityID,
      L"InstanceContextFactory::GetContext() - Could not get an instance. Failure code 0x%08X.",
      (unsigned int)InstanceContext);
    v5 = v8;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 16LL))(v5);
      }
    }
  }
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x140005e3c  mov     [rsp+arg_0], rbx
0x140005e41  push    rdi
0x140005e42  sub     rsp, 30h
0x140005e46  mov     rcx, rdx; Instance
0x140005e49  mov     rdx, r8; Context
0x140005e4c  call    cs:__imp_FltGetInstanceContext
0x140005e53  nop     dword ptr [rax+rax+00h]
0x140005e58  mov     edi, eax
0x140005e5a  test    eax, eax
0x140005e5c  jns     short loc_140005EC1
0x140005e5e  lea     rcx, [rsp+38h+var_18]
0x140005e63  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140005e68  mov     r9d, edi
0x140005e6b  lea     r8, aInstancecontex_2; "InstanceContextFactory::GetContext() - "...
0x140005e72  mov     ecx, 1
0x140005e77  mov     rdx, [rax]
0x140005e7a  call    LogWrite
0x140005e7f  mov     rbx, [rsp+38h+var_10]
0x140005e84  test    rbx, rbx
0x140005e87  jz      short loc_140005EC1
0x140005e89  or      eax, 0FFFFFFFFh
0x140005e8c  lock xadd [rbx+8], eax
0x140005e91  cmp     eax, 1
0x140005e94  jnz     short loc_140005EC1
0x140005e96  mov     rax, [rbx]
0x140005e99  mov     rcx, rbx
0x140005e9c  mov     rax, [rax+8]
0x140005ea0  call    _guard_dispatch_icall
0x140005ea5  or      eax, 0FFFFFFFFh
0x140005ea8  lock xadd [rbx+0Ch], eax
0x140005ead  cmp     eax, 1
0x140005eb0  jnz     short loc_140005EC1
0x140005eb2  mov     rax, [rbx]
0x140005eb5  mov     rcx, rbx
0x140005eb8  mov     rax, [rax+10h]
0x140005ebc  call    _guard_dispatch_icall
0x140005ec1  mov     rbx, [rsp+38h+arg_0]
0x140005ec6  mov     eax, edi
0x140005ec8  add     rsp, 30h
0x140005ecc  pop     rdi
0x140005ecd  retn
```
