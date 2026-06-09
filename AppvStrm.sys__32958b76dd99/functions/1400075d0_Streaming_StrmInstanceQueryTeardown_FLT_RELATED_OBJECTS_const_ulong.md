# Streaming::StrmInstanceQueryTeardown(_FLT_RELATED_OBJECTS const *,ulong)

- ea: `0x1400075d0`
- end: `0x1400076f8`
- name: `?StrmInstanceQueryTeardown@Streaming@@YAJPEBU_FLT_RELATED_OBJECTS@@K@Z`
- size: `296`
- prototype: `__int64 __fastcall(Streaming *this, const struct _FLT_RELATED_OBJECTS *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005e3c`
- `0x1400075d0`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14000766b`
- `FLTMGR!FltReleaseContext` at `0x1400076e3`
- `FLTMGR!FltReleaseContext` at `0x14000766b`
- `FLTMGR!FltReleaseContext` at `0x1400076e3`

## string_xrefs

- `0x14000760b`: `Streaming::StrmInstanceQueryTeardown() - Streaming Filter cannot detach. there might be a few files still opened. Please reboot the machine to detach the filter.`

## pseudocode

```c
__int64 __fastcall Streaming::StrmInstanceQueryTeardown(Streaming *this, const struct _FLT_RELATED_OBJECTS *a2)
{
  struct _FLT_INSTANCE *v2; // rdx
  GUID **CurrentActivityID; // rax
  volatile signed __int32 *v4; // rdi
  GUID **v6; // rax
  volatile signed __int32 *v7; // rdi
  GUID *v8; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-10h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _FLT_INSTANCE *)*((_QWORD *)this + 3);
  Context = 0;
  if ( (int)Streaming::InstanceContextFactory::GetContext(this, v2, &Context) < 0 )
  {
LABEL_7:
    if ( Context )
      FltReleaseContext(Context);
    return 3223060496LL;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 6, 0, 0) )
  {
    CurrentActivityID = Streaming::Utils::GetCurrentActivityID(&v8);
    LogWrite(
      3,
      *CurrentActivityID,
      L"Streaming::StrmInstanceQueryTeardown() - Streaming Filter cannot detach. there might be a few files still opened. "
       "Please reboot the machine to detach the filter.");
    v4 = v9;
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
      }
    }
    goto LABEL_7;
  }
  v6 = Streaming::Utils::GetCurrentActivityID(&v8);
  LogWrite(3, *v6, L"Streaming::StrmInstanceQueryTeardown() - Streaming Filter detached successfully.");
  v7 = v9;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  if ( Context )
    FltReleaseContext(Context);
  return 0;
}

```

## disassembly

```asm
0x1400075d0  push    rdi
0x1400075d2  sub     rsp, 30h
0x1400075d6  mov     rdx, [rcx+18h]; struct _FLT_INSTANCE *
0x1400075da  lea     r8, [rsp+38h+Context]; struct Streaming::InstanceContext *
0x1400075df  mov     [rsp+38h+Context], 0
0x1400075e8  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x1400075ed  test    eax, eax
0x1400075ef  js      short loc_140007661
0x1400075f1  mov     rdx, [rsp+38h+Context]
0x1400075f6  xor     ecx, ecx
0x1400075f8  xor     eax, eax
0x1400075fa  lock cmpxchg [rdx+18h], ecx
0x1400075ff  lea     rcx, [rsp+38h+var_18]
0x140007604  jz      short loc_14000767E
0x140007606  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000760b  lea     r8, aStreamingStrmi; "Streaming::StrmInstanceQueryTeardown() "...
0x140007612  mov     ecx, 3
0x140007617  mov     rdx, [rax]
0x14000761a  call    LogWrite
0x14000761f  mov     rdi, [rsp+38h+var_10]
0x140007624  test    rdi, rdi
0x140007627  jz      short loc_140007661
0x140007629  or      eax, 0FFFFFFFFh
0x14000762c  lock xadd [rdi+8], eax
0x140007631  cmp     eax, 1
0x140007634  jnz     short loc_140007661
0x140007636  mov     rax, [rdi]
0x140007639  mov     rcx, rdi
0x14000763c  mov     rax, [rax+8]
0x140007640  call    _guard_dispatch_icall
0x140007645  or      eax, 0FFFFFFFFh
0x140007648  lock xadd [rdi+0Ch], eax
0x14000764d  cmp     eax, 1
0x140007650  jnz     short loc_140007661
0x140007652  mov     rax, [rdi]
0x140007655  mov     rcx, rdi
0x140007658  mov     rax, [rax+10h]
0x14000765c  call    _guard_dispatch_icall
0x140007661  mov     rcx, [rsp+38h+Context]; Context
0x140007666  test    rcx, rcx
0x140007669  jz      short loc_140007677
0x14000766b  call    cs:__imp_FltReleaseContext
0x140007672  nop     dword ptr [rax+rax+00h]
0x140007677  mov     eax, 0C01C0010h
0x14000767c  jmp     short loc_1400076F1
0x14000767e  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140007683  lea     r8, aStreamingStrmi_3; "Streaming::StrmInstanceQueryTeardown() "...
0x14000768a  mov     ecx, 3
0x14000768f  mov     rdx, [rax]
0x140007692  call    LogWrite
0x140007697  mov     rdi, [rsp+38h+var_10]
0x14000769c  test    rdi, rdi
0x14000769f  jz      short loc_1400076D9
0x1400076a1  or      eax, 0FFFFFFFFh
0x1400076a4  lock xadd [rdi+8], eax
0x1400076a9  cmp     eax, 1
0x1400076ac  jnz     short loc_1400076D9
0x1400076ae  mov     rax, [rdi]
0x1400076b1  mov     rcx, rdi
0x1400076b4  mov     rax, [rax+8]
0x1400076b8  call    _guard_dispatch_icall
0x1400076bd  or      eax, 0FFFFFFFFh
0x1400076c0  lock xadd [rdi+0Ch], eax
0x1400076c5  cmp     eax, 1
0x1400076c8  jnz     short loc_1400076D9
0x1400076ca  mov     rax, [rdi]
0x1400076cd  mov     rcx, rdi
0x1400076d0  mov     rax, [rax+10h]
0x1400076d4  call    _guard_dispatch_icall
0x1400076d9  mov     rcx, [rsp+38h+Context]; Context
0x1400076de  test    rcx, rcx
0x1400076e1  jz      short loc_1400076EF
0x1400076e3  call    cs:__imp_FltReleaseContext
0x1400076ea  nop     dword ptr [rax+rax+00h]
0x1400076ef  xor     eax, eax
0x1400076f1  add     rsp, 30h
0x1400076f5  pop     rdi
0x1400076f6  retn
```
