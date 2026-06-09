# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::QueryDeferYieldCheck(void)

- ea: `0x18000ab00`
- end: `0x18000ada7`
- name: `?QueryDeferYieldCheck@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAA_NXZ`
- size: `679`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000ab00`
- `0x18000b018`
- `0x18000b0e0`
- `0x18000b9d0`
- `0x18000ec10`
- `0x180039dbc`
- `0x18005d75c`
- `0x18008ae1c`
- `0x18009e054`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000ac3e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000ac3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ace6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000acfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ace6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000acfc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000abfe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000abfe`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18000ab6e`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18000ab6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::QueryDeferYieldCheck(
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *this)
{
  unsigned __int8 v1; // di
  __int64 v2; // rbx
  __int64 v4; // rax
  char v5; // cl
  unsigned int v6; // eax
  Microsoft::CoreUI::Dispatch::Dispatcher *v7; // rdi
  char v8; // r14
  __int64 v9; // rbp
  const char16_t *v10; // rcx
  _QWORD *Value; // rsi
  struct Microsoft::CoreUI::Dispatch::DeferredUserDispatcher *v12; // rdi
  size_t v13; // r15
  _QWORD *v14; // rax
  int v15; // esi
  __int64 v16; // r15
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v22; // rcx

  v1 = 0;
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    v4 = *((_QWORD *)this + 4);
    if ( !*(_BYTE *)(v4 + 176) && *(_DWORD *)(v4 + 68) != 4 )
    {
      ++*(_DWORD *)(v2 + 16);
      v5 = *(_BYTE *)(v2 + 78);
      if ( v5 )
      {
        v19 = *(_DWORD *)(v2 + 48);
        if ( v19 == 3 || (*(_BYTE *)(*(_QWORD *)(v2 + 40) + 24LL) & 8) != 0 && v19 == 1 )
        {
          *(_BYTE *)(v2 + 78) = 0;
          v5 = 0;
        }
      }
      else
      {
        if ( !*(_BYTE *)(v2 + 77) )
        {
LABEL_12:
          v1 = *(_BYTE *)(v2 + 78);
          System::Object::ReleaseNotFrozen$((System::Object *)v2);
          return v1;
        }
        v6 = (unsigned int)GetQueueStatusReadonly(7423) >> 16;
        v5 = (v6 & 0x40) != 0 || (v6 & 8) != 0 || (v6 & 0x1C87) != 0;
        *(_BYTE *)(v2 + 78) = v5;
      }
      if ( v5 )
      {
        v7 = *(Microsoft::CoreUI::Dispatch::Dispatcher **)(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 32LL) + 56LL);
        if ( v7 )
          ++*((_DWORD *)v7 + 4);
        Microsoft::CoreUI::Dispatch::Dispatcher::CancelCurrentItem(v7);
        if ( *((_DWORD *)v7 + 26) != 4 )
          *((_DWORD *)v7 + 26) = 3;
        if ( v7 )
          System::Object::ReleaseNotFrozen$(v7);
        if ( *(_DWORD *)(v2 + 48) == 3
          && (v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 32LL) + 48LL),
              GetCurrentThreadId() == *(_DWORD *)(v20 + 176)) )
        {
          v9 = *(_QWORD *)(v2 + 40);
          CurrentThreadId = GetCurrentThreadId();
          v22 = *(_QWORD *)(*(_QWORD *)(v2 + 32) + 32LL);
          if ( CurrentThreadId != *(_DWORD *)(*(_QWORD *)(v22 + 48) + 176LL) )
            CFlat::Abandonment::Fail((const char16_t *)v22);
          v8 = 1;
        }
        else
        {
          v8 = 0;
          v9 = *(_QWORD *)(v2 + 40);
        }
        Value = TlsGetValue(Cn::Context::s_tlsStorage);
        if ( !Value )
          CFlat::Abandonment::Fail(v10);
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 32));
        v12 = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread();
        if ( !*((_DWORD *)v12 + 52) )
        {
          v13 = (unsigned int)wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(32);
          v14 = calloc(v13, 1u);
          if ( !v14 )
            CFlat::Abandonment::OutOfMemory(v13);
          v14[3] = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback;
          v14[2] = 0;
          *v14 = Value[10];
          *((_BYTE *)v14 + 8) = 2;
          Value[10] = v14;
        }
        v15 = 4;
        if ( (unsigned int)(*((_DWORD *)v12 + 52) + 1) > 4 )
          v15 = *((_DWORD *)v12 + 52) + 1;
        v16 = *((int *)v12 + 2);
        if ( v15 != (_DWORD)v16 )
        {
          Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(v12, (unsigned int)v15);
          if ( v15 > (int)v16 )
            memset_0((void *)(*(_QWORD *)v12 + 24 * v16), 0, 24LL * (v15 - (int)v16));
        }
        v17 = *((int *)v12 + 52);
        *((_DWORD *)v12 + 52) = v17 + 1;
        v17 *= 3;
        v18 = *(_QWORD *)v12;
        *(_DWORD *)(v18 + 8 * v17) = 4;
        *(_QWORD *)(v18 + 8 * v17 + 8) = v9;
        *(_BYTE *)(v18 + 8 * v17 + 16) = v8;
        *(_DWORD *)(v18 + 8 * v17 + 20) = 0;
        *(_BYTE *)(v2 + 79) = 0;
      }
      goto LABEL_12;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000ab00  mov     [rsp+arg_10], rbx
0x18000ab05  mov     [rsp+arg_18], rbp
0x18000ab0a  push    rsi
0x18000ab0b  push    rdi
0x18000ab0c  push    r12
0x18000ab0e  push    r14
0x18000ab10  push    r15
0x18000ab12  sub     rsp, 20h
0x18000ab16  xor     dil, dil
0x18000ab19  mov     rbx, [rcx+38h]
0x18000ab1d  test    rbx, rbx
0x18000ab20  jnz     short loc_18000AB3D
0x18000ab22  movzx   eax, dil
0x18000ab26  mov     rbx, [rsp+48h+arg_10]
0x18000ab2b  mov     rbp, [rsp+48h+arg_18]
0x18000ab30  add     rsp, 20h
0x18000ab34  pop     r15
0x18000ab36  pop     r14
0x18000ab38  pop     r12
0x18000ab3a  pop     rdi
0x18000ab3b  pop     rsi
0x18000ab3c  retn
0x18000ab3d  mov     rax, [rcx+20h]
0x18000ab41  cmp     [rax+0B0h], dil
0x18000ab48  jnz     short loc_18000AB22
0x18000ab4a  cmp     dword ptr [rax+44h], 4
0x18000ab4e  jz      short loc_18000AB22
0x18000ab50  mov     [rsp+48h+arg_0], rbx
0x18000ab55  inc     dword ptr [rbx+10h]
0x18000ab58  movzx   ecx, byte ptr [rbx+4Eh]
0x18000ab5c  test    cl, cl
0x18000ab5e  jnz     loc_18000ACC3
0x18000ab64  cmp     [rbx+4Dh], cl
0x18000ab67  jz      short loc_18000AB9B
0x18000ab69  mov     ecx, 1CFFh
0x18000ab6e  call    cs:__imp_GetQueueStatusReadonly
0x18000ab74  shr     eax, 10h
0x18000ab77  test    al, 40h
0x18000ab79  jnz     loc_18000AD1E
0x18000ab7f  test    al, 8
0x18000ab81  jnz     loc_18000AD7D
0x18000ab87  test    eax, 1C87h
0x18000ab8c  jnz     loc_18000AD84
0x18000ab92  xor     cl, cl
0x18000ab94  mov     [rbx+4Eh], cl
0x18000ab97  test    cl, cl
0x18000ab99  jnz     short loc_18000ABAC
0x18000ab9b  movzx   edi, byte ptr [rbx+4Eh]
0x18000ab9f  mov     rcx, rbx; this
0x18000aba2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000aba7  jmp     loc_18000AB22
0x18000abac  mov     rax, [rbx+20h]
0x18000abb0  mov     rcx, [rax+20h]
0x18000abb4  mov     rdi, [rcx+38h]
0x18000abb8  mov     [rsp+48h+arg_8], rdi
0x18000abbd  test    rdi, rdi
0x18000abc0  jz      short loc_18000ABC5
0x18000abc2  inc     dword ptr [rdi+10h]
0x18000abc5  mov     rcx, rdi; this
0x18000abc8  call    ?CancelCurrentItem@Dispatcher@Dispatch@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Dispatch::Dispatcher::CancelCurrentItem(void)
0x18000abcd  cmp     dword ptr [rdi+68h], 4
0x18000abd1  jz      short loc_18000ABDA
0x18000abd3  mov     dword ptr [rdi+68h], 3
0x18000abda  test    rdi, rdi
0x18000abdd  jz      short loc_18000ABE7
0x18000abdf  mov     rcx, rdi; this
0x18000abe2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000abe7  cmp     dword ptr [rbx+30h], 3
0x18000abeb  jz      loc_18000ACDA
0x18000abf1  xor     r14b, r14b
0x18000abf4  mov     rbp, [rbx+28h]
0x18000abf8  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000abfe  call    cs:__imp_TlsGetValue
0x18000ac04  mov     rsi, rax
0x18000ac07  test    rax, rax
0x18000ac0a  jnz     short loc_18000AC12
0x18000ac0c  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000ac12  lock inc dword ptr [rbp+20h]
0x18000ac16  call    ?GetForCurrentThread@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAPEAV1234@XZ; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread(void)
0x18000ac1b  mov     rdi, rax
0x18000ac1e  xor     r12d, r12d
0x18000ac21  cmp     [rax+0D0h], r12d
0x18000ac28  jnz     short loc_18000AC6E
0x18000ac2a  mov     ecx, 20h ; ' '
0x18000ac2f  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18000ac34  mov     r15d, eax
0x18000ac37  mov     edx, 1; Size
0x18000ac3c  mov     ecx, eax; Count
0x18000ac3e  call    cs:__imp_calloc
0x18000ac44  mov     rdx, rax
0x18000ac47  test    rax, rax
0x18000ac4a  jz      loc_18000AD93
0x18000ac50  lea     rax, ?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)
0x18000ac57  mov     [rdx+18h], rax
0x18000ac5b  mov     [rdx+10h], r12
0x18000ac5f  mov     rax, [rsi+50h]
0x18000ac63  mov     [rdx], rax
0x18000ac66  mov     byte ptr [rdx+8], 2
0x18000ac6a  mov     [rsi+50h], rdx
0x18000ac6e  mov     eax, [rdi+0D0h]
0x18000ac74  inc     eax
0x18000ac76  mov     esi, 4
0x18000ac7b  cmp     eax, esi
0x18000ac7d  cmova   esi, eax
0x18000ac80  movsxd  r15, dword ptr [rdi+8]
0x18000ac84  cmp     esi, r15d
0x18000ac87  jnz     loc_18000AD25
0x18000ac8d  movsxd  rcx, dword ptr [rdi+0D0h]
0x18000ac94  lea     eax, [rcx+1]
0x18000ac97  mov     [rdi+0D0h], eax
0x18000ac9d  lea     rcx, [rcx+rcx*2]
0x18000aca1  mov     rax, [rdi]
0x18000aca4  mov     dword ptr [rax+rcx*8], 4
0x18000acab  mov     [rax+rcx*8+8], rbp
0x18000acb0  mov     [rax+rcx*8+10h], r14b
0x18000acb5  mov     [rax+rcx*8+14h], r12d
0x18000acba  mov     byte ptr [rbx+4Fh], 0
0x18000acbe  jmp     loc_18000AB9B
0x18000acc3  mov     edx, [rbx+30h]
0x18000acc6  cmp     edx, 3
0x18000acc9  jnz     loc_18000AD61
0x18000accf  mov     byte ptr [rbx+4Eh], 0
0x18000acd3  xor     cl, cl
0x18000acd5  jmp     loc_18000AB97
0x18000acda  mov     rax, [rbx+20h]
0x18000acde  mov     rcx, [rax+20h]
0x18000ace2  mov     rdi, [rcx+30h]
0x18000ace6  call    cs:__imp_GetCurrentThreadId
0x18000acec  cmp     eax, [rdi+0B0h]
0x18000acf2  jnz     loc_18000ABF1
0x18000acf8  mov     rbp, [rbx+28h]
0x18000acfc  call    cs:__imp_GetCurrentThreadId
0x18000ad02  mov     edx, eax
0x18000ad04  mov     rax, [rbx+20h]
0x18000ad08  mov     rcx, [rax+20h]; char16_t *
0x18000ad0c  mov     rax, [rcx+30h]
0x18000ad10  cmp     edx, [rax+0B0h]
0x18000ad16  jz      short loc_18000AD8B
0x18000ad18  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000ad1e  mov     cl, 1
0x18000ad20  jmp     loc_18000AB94
0x18000ad25  mov     rcx, rdi
0x18000ad28  test    esi, esi
0x18000ad2a  jz      short loc_18000AD9C
0x18000ad2c  mov     edx, esi
0x18000ad2e  call    ?Resize@?$GlobalVectorF@UDeferredUserCall@Dispatch@CoreUI@Microsoft@@@Engine@Cn@@IEAAXH@Z; Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(int)
0x18000ad33  cmp     esi, r15d
0x18000ad36  jle     loc_18000AC8D
0x18000ad3c  sub     esi, r15d
0x18000ad3f  movsxd  rax, esi
0x18000ad42  lea     r8, [rax+rax*2]
0x18000ad46  shl     r8, 3; Size
0x18000ad4a  lea     rcx, [r15+r15*2]
0x18000ad4e  mov     rax, [rdi]
0x18000ad51  lea     rcx, [rax+rcx*8]; void *
0x18000ad55  xor     edx, edx; Val
0x18000ad57  call    memset_0
0x18000ad5c  jmp     loc_18000AC8D
0x18000ad61  mov     rax, [rbx+28h]
0x18000ad65  test    byte ptr [rax+18h], 8
0x18000ad69  jz      loc_18000AB97
0x18000ad6f  cmp     edx, 1
0x18000ad72  jz      loc_18000ACCF
0x18000ad78  jmp     loc_18000AB97
0x18000ad7d  mov     cl, 1
0x18000ad7f  jmp     loc_18000AB94
0x18000ad84  mov     cl, 1
0x18000ad86  jmp     loc_18000AB94
0x18000ad8b  mov     r14b, 1
0x18000ad8e  jmp     loc_18000ABF8
0x18000ad93  mov     rcx, r15; unsigned __int64
0x18000ad96  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
0x18000ad9c  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18000ada1  jmp     loc_18000AC8D
```
