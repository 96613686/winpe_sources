# Streaming::Writer::WriteFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x140014ff0`
- end: `0x140015112`
- name: `?WriteFile@Writer@Streaming@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001980`
- `0x140013160`

## callees

- `0x140005e3c`
- `0x14000de2c`
- `0x140014ff0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140015041`
- `ntoskrnl!DbgPrint` at `0x14001505e`
- `ntoskrnl!DbgPrint` at `0x140015041`
- `ntoskrnl!DbgPrint` at `0x14001505e`
- `FLTMGR!FltReleaseContext` at `0x1400150a2`
- `FLTMGR!FltReleaseContext` at `0x1400150fa`
- `FLTMGR!FltReleaseContext` at `0x1400150a2`
- `FLTMGR!FltReleaseContext` at `0x1400150fa`

## string_xrefs

- `0x14001503a`: `safe write file %wZ \n`
- `0x140015057`: `start write file %wZ \n`

## pseudocode

```c
__int64 __fastcall Streaming::Writer::WriteFile(struct _FLT_INSTANCE *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int128 v9; // xmm1
  bool v10; // zf
  Streaming::InstanceContextFactory *v11; // rcx
  int v12; // eax
  __int64 v13; // r9
  PFLT_CONTEXT v14; // rcx
  unsigned int v15; // ebx
  __int128 v16; // [rsp+20h] [rbp-48h] BYREF
  __int128 v17; // [rsp+30h] [rbp-38h]
  PFLT_CONTEXT Context; // [rsp+80h] [rbp+18h] BYREF

  if ( (*(_DWORD *)a3 & 2) != 0 )
    return 3;
  v9 = *(_OWORD *)(*(_QWORD *)a4 + 64LL);
  v10 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a4 + 88LL) + 56LL) == 0;
  v16 = *(_OWORD *)(*(_QWORD *)a4 + 48LL);
  v17 = v9;
  if ( v10 )
  {
    DbgPrint("start write file %wZ \n", &v16);
    Context = 0;
    v12 = Streaming::InstanceContextFactory::GetContext(v11, a1, (struct Streaming::InstanceContext *)&Context);
    if ( v12 >= 0 )
    {
      if ( (*(_DWORD *)(a2 + 80) & 2) != 0 || *(_BYTE *)(*(_QWORD *)(a3 + 16) + 4LL) != 4 )
        LOBYTE(v13) = 0;
      else
        v13 = 1;
      v15 = Streaming::StreamFaultManager::CreateWriteFault(
              *((_QWORD *)Context + 31),
              a3,
              a4,
              v13,
              v16,
              *((_QWORD *)&v16 + 1),
              v17,
              *((_QWORD *)&v17 + 1));
      if ( Context )
        FltReleaseContext(Context);
      return v15;
    }
    else
    {
      v14 = Context;
      *(_DWORD *)(a3 + 24) = v12;
      *(_QWORD *)(a3 + 32) = 0;
      if ( v14 )
        FltReleaseContext(v14);
      return 4;
    }
  }
  else
  {
    DbgPrint("safe write file %wZ \n", &v16);
    return 1;
  }
}

```

## disassembly

```asm
0x140014ff0  push    rbx
0x140014ff2  push    rbp
0x140014ff3  push    rsi
0x140014ff4  push    rdi
0x140014ff5  sub     rsp, 48h
0x140014ff9  mov     eax, [r8]
0x140014ffc  mov     rdi, r9
0x140014fff  mov     rbx, r8
0x140015002  mov     rsi, rdx
0x140015005  mov     rbp, rcx
0x140015008  test    al, 2
0x14001500a  jz      short loc_140015016
0x14001500c  mov     eax, 3
0x140015011  jmp     loc_140015108
0x140015016  mov     rcx, [r9]
0x140015019  lea     rdx, [rsp+68h+var_48]
0x14001501e  mov     rax, [rcx+58h]
0x140015022  movups  xmm0, xmmword ptr [rcx+30h]
0x140015026  movups  xmm1, xmmword ptr [rcx+40h]
0x14001502a  cmp     byte ptr [rax+38h], 0
0x14001502e  movaps  [rsp+68h+var_48], xmm0
0x140015033  movaps  [rsp+68h+var_38], xmm1
0x140015038  jz      short loc_140015057
0x14001503a  lea     rcx, aSafeWriteFileW; "safe write file %wZ \n"
0x140015041  call    cs:__imp_DbgPrint
0x140015048  nop     dword ptr [rax+rax+00h]
0x14001504d  mov     eax, 1
0x140015052  jmp     loc_140015108
0x140015057  lea     rcx, aStartWriteFile; "start write file %wZ \n"
0x14001505e  call    cs:__imp_DbgPrint
0x140015065  nop     dword ptr [rax+rax+00h]
0x14001506a  lea     r8, [rsp+68h+Context]; struct Streaming::InstanceContext *
0x140015072  mov     [rsp+68h+Context], 0
0x14001507e  mov     rdx, rbp; struct _FLT_INSTANCE *
0x140015081  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x140015086  test    eax, eax
0x140015088  jns     short loc_1400150B5
0x14001508a  mov     rcx, [rsp+68h+Context]; Context
0x140015092  mov     [rbx+18h], eax
0x140015095  mov     qword ptr [rbx+20h], 0
0x14001509d  test    rcx, rcx
0x1400150a0  jz      short loc_1400150AE
0x1400150a2  call    cs:__imp_FltReleaseContext
0x1400150a9  nop     dword ptr [rax+rax+00h]
0x1400150ae  mov     eax, 4
0x1400150b3  jmp     short loc_140015108
0x1400150b5  mov     rax, [rsp+68h+Context]
0x1400150bd  mov     rcx, [rax+0F8h]
0x1400150c4  mov     eax, [rsi+50h]
0x1400150c7  test    al, 2
0x1400150c9  jnz     short loc_1400150DD
0x1400150cb  mov     rax, [rbx+10h]
0x1400150cf  cmp     byte ptr [rax+4], 4
0x1400150d3  jnz     short loc_1400150DD
0x1400150d5  mov     r9d, 1
0x1400150db  jmp     short loc_1400150E0
0x1400150dd  xor     r9b, r9b
0x1400150e0  mov     r8, rdi
0x1400150e3  mov     rdx, rbx
0x1400150e6  call    ?CreateWriteFault@StreamFaultManager@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@_N@Z; Streaming::StreamFaultManager::CreateWriteFault(_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,bool)
0x1400150eb  mov     rcx, [rsp+68h+Context]; Context
0x1400150f3  mov     ebx, eax
0x1400150f5  test    rcx, rcx
0x1400150f8  jz      short loc_140015106
0x1400150fa  call    cs:__imp_FltReleaseContext
0x140015101  nop     dword ptr [rax+rax+00h]
0x140015106  mov     eax, ebx
0x140015108  add     rsp, 48h
0x14001510c  pop     rdi
0x14001510d  pop     rsi
0x14001510e  pop     rbp
0x14001510f  pop     rbx
0x140015110  retn
```
