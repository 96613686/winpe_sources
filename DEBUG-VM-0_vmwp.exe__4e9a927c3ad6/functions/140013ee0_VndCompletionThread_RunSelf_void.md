# VndCompletionThread::RunSelf(void)

- ea: `0x140013ee0`
- end: `0x140014084`
- name: `?RunSelf@VndCompletionThread@@MEAAIXZ`
- size: `420`
- prototype: `unsigned int __fastcall(VndCompletionThread *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140013ee0`
- `0x14001408c`
- `0x140132940`
- `0x14027e7c8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014040`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140013fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140013fed`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001402f`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001402f`
- `vid!VidMessageSlotHandleAndGetNext` at `0x140013f5a`
- `vid!VidMessageSlotHandleAndGetNext` at `0x140013f5a`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014004`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014004`

## pseudocode

```c
__int64 __fastcall VndCompletionThread::RunSelf(VndCompletionThread *this)
{
  int v2; // r8d
  VndCompletionHandler *v3; // r14
  int v4; // edi
  void *v5; // rsi
  int v6; // eax
  __int64 v7; // rdx
  int NextMessage; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // [rsp+20h] [rbp-68h]
  struct _VID_MSG_RETURN_DATA *v15; // [rsp+30h] [rbp-58h] BYREF
  struct _VID_MSG_DATA *v16; // [rsp+38h] [rbp-50h] BYREF
  GROUP_AFFINITY GroupAffinity; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = *((_DWORD *)this + 36);
  v3 = *(VndCompletionHandler **)(*((_QWORD *)this + 15) + 120LL);
  v16 = 0;
  v15 = 0;
  if ( v2 >= 0 )
  {
    v16 = (struct _VID_MSG_DATA *)*((_QWORD *)this + 16);
    v15 = (struct _VID_MSG_DATA *)((char *)v16 + 320);
    (*(void (__fastcall **)(_QWORD, GROUP_AFFINITY *))(**(_QWORD **)(*(_QWORD *)v3 + 56LL) + 64LL))(
      *(_QWORD *)(*(_QWORD *)v3 + 56LL),
      &GroupAffinity);
    if ( GroupAffinity.Mask )
    {
      CurrentThread = GetCurrentThread();
      SetThreadGroupAffinity(CurrentThread, &GroupAffinity, 0);
    }
  }
  v4 = 0;
  v5 = *(void **)(*(_QWORD *)v3 + 40LL);
  while ( *((_BYTE *)this + 112) )
  {
    v6 = *((_DWORD *)this + 36);
    v7 = v4 != 0 ? 3 : 1;
    if ( v6 < 0 )
    {
      v14 = -1;
      NextMessage = VidHandleMessageAndGetNextMessage(v5, v7, &v15, &v16);
    }
    else
    {
      NextMessage = VidMessageSlotHandleAndGetNext(v5, (unsigned int)v6, (unsigned int)v7, *((_QWORD *)this + 19));
    }
    if ( NextMessage )
    {
      v4 = VndCompletionHandler::HandleVndCallback(v3, v5, v16, v15, *((void **)this + 19));
    }
    else
    {
      LastError = GetLastError();
      v4 = 0;
      if ( *((_BYTE *)this + 112) && LastError != 258 && LastError != 995 )
        wil::details::in1diag3::Log_Win32(retaddr, v12, v13, (const char *)LastError, v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140013ee0  push    rbx
0x140013ee2  push    rsi
0x140013ee3  push    rdi
0x140013ee4  push    r14
0x140013ee6  sub     rsp, 68h
0x140013eea  mov     rax, cs:__security_cookie
0x140013ef1  xor     rax, rsp
0x140013ef4  mov     [rsp+88h+var_38], rax
0x140013ef9  mov     rax, [rcx+78h]
0x140013efd  mov     rbx, rcx
0x140013f00  mov     r8d, [rcx+90h]
0x140013f07  mov     r14, [rax+78h]
0x140013f0b  mov     [rsp+88h+var_50], 0
0x140013f14  mov     [rsp+88h+var_58], 0
0x140013f1d  test    r8d, r8d
0x140013f20  jns     loc_140013FB2
0x140013f26  mov     rax, [r14]
0x140013f29  xor     edi, edi
0x140013f2b  mov     rsi, [rax+28h]
0x140013f2f  jmp     short loc_140013F91
0x140013f31  mov     eax, [rbx+90h]
0x140013f37  neg     edi
0x140013f39  mov     rcx, [rbx+98h]
0x140013f40  sbb     edx, edx
0x140013f42  and     edx, 2
0x140013f45  inc     edx
0x140013f47  test    eax, eax
0x140013f49  js      loc_140014015
0x140013f4f  mov     r9, rcx
0x140013f52  mov     r8d, edx
0x140013f55  mov     edx, eax
0x140013f57  mov     rcx, rsi
0x140013f5a  call    cs:__imp_VidMessageSlotHandleAndGetNext
0x140013f61  nop     dword ptr [rax+rax+00h]
0x140013f66  test    eax, eax
0x140013f68  jz      loc_140014040
0x140013f6e  mov     rax, [rbx+98h]
0x140013f75  mov     rdx, rsi; void *
0x140013f78  mov     r9, [rsp+88h+var_58]; struct _VID_MSG_RETURN_DATA *
0x140013f7d  mov     rcx, r14; this
0x140013f80  mov     r8, [rsp+88h+var_50]; struct _VID_MSG_DATA *
0x140013f85  mov     [rsp+88h+var_68], rax; unsigned int
0x140013f8a  call    ?HandleVndCallback@VndCompletionHandler@@AEAAHPEAXPEAU_VID_MSG_DATA@@PEAU_VID_MSG_RETURN_DATA@@0@Z; VndCompletionHandler::HandleVndCallback(void *,_VID_MSG_DATA *,_VID_MSG_RETURN_DATA *,void *)
0x140013f8f  mov     edi, eax
0x140013f91  mov     al, [rbx+70h]
0x140013f94  test    al, al
0x140013f96  jnz     short loc_140013F31
0x140013f98  xor     eax, eax
0x140013f9a  mov     rcx, [rsp+88h+var_38]
0x140013f9f  xor     rcx, rsp; StackCookie
0x140013fa2  call    __security_check_cookie
0x140013fa7  add     rsp, 68h
0x140013fab  pop     r14
0x140013fad  pop     rdi
0x140013fae  pop     rsi
0x140013faf  pop     rbx
0x140013fb0  retn
0x140013fb2  mov     rax, [rcx+80h]
0x140013fb9  lea     rdx, [rsp+88h+GroupAffinity]
0x140013fbe  mov     [rsp+88h+var_50], rax
0x140013fc3  add     rax, 140h
0x140013fc9  mov     [rsp+88h+var_58], rax
0x140013fce  mov     rax, [r14]
0x140013fd1  mov     rcx, [rax+38h]
0x140013fd5  mov     rax, [rcx]
0x140013fd8  mov     rax, [rax+40h]
0x140013fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013fe1  cmp     [rsp+88h+GroupAffinity.Mask], 0
0x140013fe7  jz      loc_140013F26
0x140013fed  call    cs:__imp_GetCurrentThread
0x140013ff4  nop     dword ptr [rax+rax+00h]
0x140013ff9  xor     r8d, r8d; PreviousGroupAffinity
0x140013ffc  lea     rdx, [rsp+88h+GroupAffinity]; GroupAffinity
0x140014001  mov     rcx, rax; hThread
0x140014004  call    cs:__imp_SetThreadGroupAffinity
0x14001400b  nop     dword ptr [rax+rax+00h]
0x140014010  jmp     loc_140013F26
0x140014015  mov     [rsp+88h+var_60], rcx
0x14001401a  lea     r9, [rsp+88h+var_50]
0x14001401f  mov     rcx, rsi
0x140014022  mov     dword ptr [rsp+88h+var_68], 0FFFFFFFFh
0x14001402a  lea     r8, [rsp+88h+var_58]
0x14001402f  call    cs:__imp_VidHandleMessageAndGetNextMessage
0x140014036  nop     dword ptr [rax+rax+00h]
0x14001403b  jmp     loc_140013F66
0x140014040  call    cs:__imp_GetLastError
0x140014047  nop     dword ptr [rax+rax+00h]
0x14001404c  mov     cl, [rbx+70h]
0x14001404f  xor     edi, edi
0x140014051  test    cl, cl
0x140014053  jz      loc_140013F91
0x140014059  cmp     eax, 102h
0x14001405e  jz      loc_140013F91
0x140014064  cmp     eax, 3E3h
0x140014069  jz      loc_140013F91
0x14001406f  mov     rcx, [rsp+88h]; this
0x140014077  mov     r9d, eax; char *
0x14001407a  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x14001407f  jmp     loc_140013F91
```
