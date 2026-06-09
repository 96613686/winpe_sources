# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::AbandonEventLoopIfExternalWorkHasPrecedence(Microsoft::CoreUI::Dispatch::InternalPriority,int)

- ea: `0x18005d400`
- end: `0x18005d753`
- name: `?AbandonEventLoopIfExternalWorkHasPrecedence@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAA_NW4InternalPriority@234@H@Z`
- size: `851`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b018`
- `0x18000b0e0`
- `0x18000b9d0`
- `0x18000ec10`
- `0x180039dbc`
- `0x18005d400`
- `0x18005d75c`
- `0x18008ae1c`
- `0x18009e054`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d5af`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d5af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d689`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d69f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d689`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d69f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d571`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d571`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18005d4be`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18005d4be`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::AbandonEventLoopIfExternalWorkHasPrecedence(
        __int64 a1,
        int a2,
        __int16 a3)
{
  __int64 v6; // rbx
  const char16_t *v7; // rcx
  __int64 v8; // rax
  bool v9; // si
  __int64 v10; // rbx
  int v12; // ecx
  unsigned int v13; // eax
  __int16 v14; // dx
  __int16 v15; // cx
  __int16 v16; // ax
  Microsoft::CoreUI::Dispatch::Dispatcher *v17; // rdi
  char v18; // r13
  __int64 v19; // r15
  const char16_t *v20; // rcx
  _QWORD *Value; // r14
  struct Microsoft::CoreUI::Dispatch::DeferredUserDispatcher *v22; // rdi
  size_t v23; // r12
  _QWORD *v24; // rax
  int v25; // r14d
  __int64 v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // ecx
  int v30; // ecx
  const char16_t *v31; // rcx
  __int64 v32; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v34; // rcx

  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 48LL);
  if ( GetCurrentThreadId() != *(_DWORD *)(v6 + 176) )
    CFlat::Abandonment::Fail(v7);
  v8 = *(_QWORD *)(a1 + 32);
  if ( !*(_DWORD *)(v8 + 72) )
    CFlat::Abandonment::Fail(v7);
  v9 = 0;
  v10 = *(_QWORD *)(a1 + 56);
  if ( v10 && !*(_BYTE *)(v8 + 176) && *(_DWORD *)(v8 + 68) != 4 && a2 > 2 )
  {
    ++*(_DWORD *)(v10 + 16);
    v12 = *(_DWORD *)(v10 + 48);
    if ( !v12 || *(_BYTE *)(v10 + 80) )
    {
      v9 = 0;
      goto LABEL_27;
    }
    if ( v12 == 4 )
    {
      if ( a2 <= 6 )
      {
        v9 = 1;
        goto LABEL_28;
      }
    }
    else
    {
      v29 = v12 - 1;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          v31 = (const char16_t *)(unsigned int)(v30 - 1);
          if ( (_DWORD)v31 )
          {
            if ( (_DWORD)v31 != 2 )
              CFlat::Abandonment::Fail(v31);
            v9 = a2 <= 10;
            if ( a2 <= 10 )
            {
LABEL_26:
              if ( !v9 )
              {
LABEL_27:
                System::Object::ReleaseNotFrozen$((System::Object *)v10);
                return v9;
              }
LABEL_28:
              v17 = *(Microsoft::CoreUI::Dispatch::Dispatcher **)(*(_QWORD *)(*(_QWORD *)(v10 + 32) + 32LL) + 56LL);
              if ( v17 )
                ++*((_DWORD *)v17 + 4);
              Microsoft::CoreUI::Dispatch::Dispatcher::CancelCurrentItem(v17);
              if ( *((_DWORD *)v17 + 26) != 4 )
                *((_DWORD *)v17 + 26) = 3;
              if ( v17 )
                System::Object::ReleaseNotFrozen$(v17);
              if ( *(_DWORD *)(v10 + 48) == 3
                && (v32 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 32) + 32LL) + 48LL),
                    GetCurrentThreadId() == *(_DWORD *)(v32 + 176)) )
              {
                v19 = *(_QWORD *)(v10 + 40);
                CurrentThreadId = GetCurrentThreadId();
                v34 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 32) + 32LL) + 48LL);
                if ( CurrentThreadId != *(_DWORD *)(v34 + 176) )
                  CFlat::Abandonment::Fail((const char16_t *)v34);
                v18 = 1;
              }
              else
              {
                v18 = 0;
                v19 = *(_QWORD *)(v10 + 40);
              }
              Value = TlsGetValue(Cn::Context::s_tlsStorage);
              if ( !Value )
                CFlat::Abandonment::Fail(v20);
              _InterlockedIncrement((volatile signed __int32 *)(v19 + 32));
              v22 = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread();
              if ( !*((_DWORD *)v22 + 52) )
              {
                v23 = (unsigned int)wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(32);
                v24 = calloc(v23, 1u);
                if ( !v24 )
                  CFlat::Abandonment::OutOfMemory(v23);
                v24[3] = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback;
                v24[2] = 0;
                *v24 = Value[10];
                *((_BYTE *)v24 + 8) = 2;
                Value[10] = v24;
              }
              v25 = 4;
              if ( (unsigned int)(*((_DWORD *)v22 + 52) + 1) > 4 )
                v25 = *((_DWORD *)v22 + 52) + 1;
              v26 = *((int *)v22 + 2);
              if ( v25 != (_DWORD)v26 )
              {
                Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(v22, (unsigned int)v25);
                if ( v25 > (int)v26 )
                  memset_0((void *)(*(_QWORD *)v22 + 24 * v26), 0, 24LL * (v25 - (int)v26));
              }
              v27 = *((int *)v22 + 52);
              *((_DWORD *)v22 + 52) = v27 + 1;
              v27 *= 3;
              v28 = *(_QWORD *)v22;
              *(_DWORD *)(v28 + 8 * v27) = a2;
              *(_QWORD *)(v28 + 8 * v27 + 8) = v19;
              *(_BYTE *)(v28 + 8 * v27 + 16) = v18;
              *(_DWORD *)(v28 + 8 * v27 + 20) = 0;
              *(_BYTE *)(v10 + 79) = a2 > 4;
              goto LABEL_27;
            }
LABEL_15:
            if ( *(_BYTE *)(v10 + 77) )
            {
              v13 = (unsigned int)GetQueueStatusReadonly(7423) >> 16;
              v14 = v13 & 0xFFBF;
              if ( (a3 & 0x2000) != 0 )
                v14 = v13;
              v15 = v14 & 0xE370;
              if ( (a3 & 0x80u) != 0 )
                v15 = v14;
              v16 = v15 & 0xFFCF;
              if ( (a3 & 0x10) != 0 )
                v16 = v15;
              if ( (v16 & 0x40) != 0 )
              {
                v9 = a2 <= 10;
              }
              else if ( (v16 & 8) != 0 )
              {
                v9 = a2 <= 6;
              }
              else
              {
                v9 = (v16 & 0x1C87) != 0 && a2 <= 4;
              }
            }
            goto LABEL_26;
          }
        }
      }
    }
    v9 = 0;
    goto LABEL_15;
  }
  return v9;
}

```

## disassembly

```asm
0x18005d400  mov     [rsp+arg_8], rbx
0x18005d405  push    rbp
0x18005d406  push    rsi
0x18005d407  push    rdi
0x18005d408  push    r12
0x18005d40a  push    r13
0x18005d40c  push    r14
0x18005d40e  push    r15
0x18005d410  sub     rsp, 20h
0x18005d414  mov     r14d, r8d
0x18005d417  mov     ebp, edx
0x18005d419  mov     rdi, rcx
0x18005d41c  mov     rax, [rcx+20h]
0x18005d420  mov     rbx, [rax+30h]
0x18005d424  call    cs:__imp_GetCurrentThreadId
0x18005d42a  cmp     eax, [rbx+0B0h]
0x18005d430  jz      short loc_18005D438
0x18005d432  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d438  mov     rax, [rdi+20h]
0x18005d43c  cmp     dword ptr [rax+48h], 0
0x18005d440  jnz     short loc_18005D448
0x18005d442  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d448  xor     sil, sil
0x18005d44b  mov     rbx, [rdi+38h]
0x18005d44f  test    rbx, rbx
0x18005d452  jnz     short loc_18005D46D
0x18005d454  movzx   eax, sil
0x18005d458  mov     rbx, [rsp+58h+arg_8]
0x18005d45d  add     rsp, 20h
0x18005d461  pop     r15
0x18005d463  pop     r14
0x18005d465  pop     r13
0x18005d467  pop     r12
0x18005d469  pop     rdi
0x18005d46a  pop     rsi
0x18005d46b  pop     rbp
0x18005d46c  retn
0x18005d46d  cmp     [rax+0B0h], sil
0x18005d474  jnz     short loc_18005D454
0x18005d476  cmp     dword ptr [rax+44h], 4
0x18005d47a  jz      short loc_18005D454
0x18005d47c  cmp     ebp, 2
0x18005d47f  jle     short loc_18005D454
0x18005d481  mov     [rsp+58h+arg_0], rbx
0x18005d486  inc     dword ptr [rbx+10h]
0x18005d489  mov     ecx, [rbx+30h]; char16_t *
0x18005d48c  test    ecx, ecx
0x18005d48e  jz      loc_18005D6BF
0x18005d494  cmp     byte ptr [rbx+50h], 0
0x18005d498  jnz     loc_18005D6BF
0x18005d49e  cmp     ecx, 4
0x18005d4a1  jnz     loc_18005D63F
0x18005d4a7  cmp     ebp, 6
0x18005d4aa  jle     loc_18005D737
0x18005d4b0  xor     sil, sil
0x18005d4b3  cmp     byte ptr [rbx+4Dh], 0
0x18005d4b7  jz      short loc_18005D50D
0x18005d4b9  mov     ecx, 1CFFh
0x18005d4be  call    cs:__imp_GetQueueStatusReadonly
0x18005d4c4  shr     eax, 10h
0x18005d4c7  mov     edx, eax
0x18005d4c9  and     edx, 0FFFFFFBFh
0x18005d4cc  bt      r14d, 0Dh
0x18005d4d1  cmovb   edx, eax
0x18005d4d4  mov     ecx, edx
0x18005d4d6  and     ecx, 0FFFFE370h
0x18005d4dc  test    r14b, 80h
0x18005d4e0  cmovnz  ecx, edx
0x18005d4e3  mov     eax, ecx
0x18005d4e5  and     eax, 0FFFFFFCFh
0x18005d4e8  test    r14b, 10h
0x18005d4ec  cmovnz  eax, ecx
0x18005d4ef  test    al, 40h
0x18005d4f1  jnz     loc_18005D705
0x18005d4f7  test    al, 8
0x18005d4f9  jnz     loc_18005D711
0x18005d4ff  test    eax, 1C87h
0x18005d504  jnz     loc_18005D71D
0x18005d50a  xor     sil, sil
0x18005d50d  test    sil, sil
0x18005d510  jnz     short loc_18005D51F
0x18005d512  mov     rcx, rbx; this
0x18005d515  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005d51a  jmp     loc_18005D454
0x18005d51f  mov     rax, [rbx+20h]
0x18005d523  mov     rcx, [rax+20h]
0x18005d527  mov     rdi, [rcx+38h]
0x18005d52b  mov     [rsp+58h+arg_18], rdi
0x18005d530  test    rdi, rdi
0x18005d533  jz      short loc_18005D538
0x18005d535  inc     dword ptr [rdi+10h]
0x18005d538  mov     rcx, rdi; this
0x18005d53b  call    ?CancelCurrentItem@Dispatcher@Dispatch@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Dispatch::Dispatcher::CancelCurrentItem(void)
0x18005d540  cmp     dword ptr [rdi+68h], 4
0x18005d544  jz      short loc_18005D54D
0x18005d546  mov     dword ptr [rdi+68h], 3
0x18005d54d  test    rdi, rdi
0x18005d550  jz      short loc_18005D55A
0x18005d552  mov     rcx, rdi; this
0x18005d555  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005d55a  cmp     dword ptr [rbx+30h], 3
0x18005d55e  jz      loc_18005D67D
0x18005d564  xor     r13b, r13b
0x18005d567  mov     r15, [rbx+28h]
0x18005d56b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005d571  call    cs:__imp_TlsGetValue
0x18005d577  mov     r14, rax
0x18005d57a  test    rax, rax
0x18005d57d  jnz     short loc_18005D585
0x18005d57f  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d585  lock inc dword ptr [r15+20h]
0x18005d58a  call    ?GetForCurrentThread@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAPEAV1234@XZ; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread(void)
0x18005d58f  mov     rdi, rax
0x18005d592  cmp     dword ptr [rax+0D0h], 0
0x18005d599  jnz     short loc_18005D5E3
0x18005d59b  mov     ecx, 20h ; ' '
0x18005d5a0  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18005d5a5  mov     r12d, eax
0x18005d5a8  mov     edx, 1; Size
0x18005d5ad  mov     ecx, eax; Count
0x18005d5af  call    cs:__imp_calloc
0x18005d5b5  mov     rdx, rax
0x18005d5b8  test    rax, rax
0x18005d5bb  jz      loc_18005D73F
0x18005d5c1  lea     rax, ?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)
0x18005d5c8  mov     [rdx+18h], rax
0x18005d5cc  mov     qword ptr [rdx+10h], 0
0x18005d5d4  mov     rax, [r14+50h]
0x18005d5d8  mov     [rdx], rax
0x18005d5db  mov     byte ptr [rdx+8], 2
0x18005d5df  mov     [r14+50h], rdx
0x18005d5e3  mov     eax, [rdi+0D0h]
0x18005d5e9  inc     eax
0x18005d5eb  mov     r14d, 4
0x18005d5f1  cmp     eax, r14d
0x18005d5f4  cmova   r14d, eax
0x18005d5f8  movsxd  r12, dword ptr [rdi+8]
0x18005d5fc  cmp     r14d, r12d
0x18005d5ff  jnz     loc_18005D6C7
0x18005d605  movsxd  rcx, dword ptr [rdi+0D0h]
0x18005d60c  lea     eax, [rcx+1]
0x18005d60f  mov     [rdi+0D0h], eax
0x18005d615  lea     rcx, [rcx+rcx*2]
0x18005d619  mov     rax, [rdi]
0x18005d61c  mov     [rax+rcx*8], ebp
0x18005d61f  mov     [rax+rcx*8+8], r15
0x18005d624  mov     [rax+rcx*8+10h], r13b
0x18005d629  mov     dword ptr [rax+rcx*8+14h], 0
0x18005d631  cmp     ebp, 4
0x18005d634  setnle  cl
0x18005d637  mov     [rbx+4Fh], cl
0x18005d63a  jmp     loc_18005D512
0x18005d63f  test    ecx, ecx
0x18005d641  jz      loc_18005D731
0x18005d647  sub     ecx, 1
0x18005d64a  jz      loc_18005D4B0
0x18005d650  sub     ecx, 1
0x18005d653  jz      loc_18005D4B0
0x18005d659  sub     ecx, 1
0x18005d65c  jz      loc_18005D4B0
0x18005d662  cmp     ecx, 2
0x18005d665  jnz     loc_18005D731
0x18005d66b  cmp     ebp, 0Ah
0x18005d66e  setle   sil
0x18005d672  jg      loc_18005D4B3
0x18005d678  jmp     loc_18005D50D
0x18005d67d  mov     rax, [rbx+20h]
0x18005d681  mov     rcx, [rax+20h]
0x18005d685  mov     rdi, [rcx+30h]
0x18005d689  call    cs:__imp_GetCurrentThreadId
0x18005d68f  cmp     eax, [rdi+0B0h]
0x18005d695  jnz     loc_18005D564
0x18005d69b  mov     r15, [rbx+28h]
0x18005d69f  call    cs:__imp_GetCurrentThreadId
0x18005d6a5  mov     rcx, [rbx+20h]
0x18005d6a9  mov     rdx, [rcx+20h]
0x18005d6ad  mov     rcx, [rdx+30h]; char16_t *
0x18005d6b1  cmp     eax, [rcx+0B0h]
0x18005d6b7  jz      short loc_18005D729
0x18005d6b9  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d6bf  xor     sil, sil
0x18005d6c2  jmp     loc_18005D512
0x18005d6c7  mov     rcx, rdi
0x18005d6ca  test    r14d, r14d
0x18005d6cd  jz      short loc_18005D748
0x18005d6cf  mov     edx, r14d
0x18005d6d2  call    ?Resize@?$GlobalVectorF@UDeferredUserCall@Dispatch@CoreUI@Microsoft@@@Engine@Cn@@IEAAXH@Z; Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(int)
0x18005d6d7  cmp     r14d, r12d
0x18005d6da  jle     loc_18005D605
0x18005d6e0  sub     r14d, r12d
0x18005d6e3  movsxd  rax, r14d
0x18005d6e6  lea     r8, [rax+rax*2]
0x18005d6ea  shl     r8, 3; Size
0x18005d6ee  lea     rcx, [r12+r12*2]
0x18005d6f2  mov     rax, [rdi]
0x18005d6f5  lea     rcx, [rax+rcx*8]; void *
0x18005d6f9  xor     edx, edx; Val
0x18005d6fb  call    memset_0
0x18005d700  jmp     loc_18005D605
0x18005d705  cmp     ebp, 0Ah
0x18005d708  setle   sil
0x18005d70c  jmp     loc_18005D50D
0x18005d711  cmp     ebp, 6
0x18005d714  setle   sil
0x18005d718  jmp     loc_18005D50D
0x18005d71d  cmp     ebp, 4
0x18005d720  setle   sil
0x18005d724  jmp     loc_18005D50D
0x18005d729  mov     r13b, 1
0x18005d72c  jmp     loc_18005D56B
0x18005d731  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d737  mov     sil, 1
0x18005d73a  jmp     loc_18005D51F
0x18005d73f  mov     rcx, r12; unsigned __int64
0x18005d742  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
0x18005d748  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18005d74d  jmp     loc_18005D605
```
