# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::WakeDispatchThreadIfNecessary(void)

- ea: `0x18000adb0`
- end: `0x18000b010`
- name: `?WakeDispatchThreadIfNecessary@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAAXXZ`
- size: `608`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000aa10`

## callees

- `0x18000adb0`
- `0x18000b018`
- `0x18000b0bc`
- `0x18000ec10`
- `0x180039dbc`
- `0x18003ab2c`
- `0x18005d75c`
- `0x18008ae1c`
- `0x18009e054`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000aedb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000aedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae81`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae81`

## string_xrefs

- `0x18000afeb`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::WakeDispatchThreadIfNecessary(
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *this)
{
  __int64 v1; // rbx
  __int64 v2; // r14
  __int64 v3; // rax
  __int64 v4; // rdi
  int v5; // r14d
  char v6; // r12
  __int64 v7; // rbp
  const char16_t *v8; // rcx
  _QWORD *Value; // rsi
  struct Microsoft::CoreUI::Dispatch::DeferredUserDispatcher *v10; // rdi
  int v11; // eax
  unsigned __int64 v12; // r15
  _QWORD *v13; // rax
  int v14; // esi
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  size_t Count; // [rsp+70h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 7);
  if ( v1 )
  {
    v3 = *((_QWORD *)this + 4);
    if ( !*(_BYTE *)(v3 + 176) && *(_DWORD *)(v3 + 68) != 4 )
    {
      ++*(_DWORD *)(v1 + 16);
      v4 = *(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL);
      if ( !*(_DWORD *)(v4 + 72) || (v2 = *(_QWORD *)(v4 + 56), *(_DWORD *)(v2 + 104)) || *(_BYTE *)(v1 + 52) )
      {
        v5 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 168) + 32LL) + 56LL) + 56LL);
        if ( !v5 )
          v5 = 16;
      }
      else
      {
        if ( !*(_BYTE *)(v4 + 32) )
          goto LABEL_10;
        v5 = *(_DWORD *)(v2 + 56);
        if ( v5 < 6 )
          v5 = 6;
      }
      if ( *(_DWORD *)(v1 + 48) == 3 && (v18 = *(_QWORD *)(v4 + 48), GetCurrentThreadId() == *(_DWORD *)(v18 + 176)) )
      {
        v7 = *(_QWORD *)(v1 + 40);
        CurrentThreadId = GetCurrentThreadId();
        v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL) + 48LL);
        if ( CurrentThreadId != *(_DWORD *)(v20 + 176) )
          CFlat::Abandonment::Fail((const char16_t *)v20);
        v6 = 1;
      }
      else
      {
        v6 = 0;
        v7 = *(_QWORD *)(v1 + 40);
      }
      Value = TlsGetValue(Cn::Context::s_tlsStorage);
      if ( !Value )
        CFlat::Abandonment::Fail(v8);
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 32));
      v10 = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread();
      if ( !*((_DWORD *)v10 + 52) )
      {
        LODWORD(Count) = 0;
        v11 = ULongLongToUInt(0x20u, (unsigned int *)&Count);
        if ( v11 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x10F,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
            (const char *)(unsigned int)v11,
            v21);
        v12 = (unsigned int)Count;
        v13 = calloc((unsigned int)Count, 1u);
        if ( !v13 )
          CFlat::Abandonment::OutOfMemory(v12);
        v13[3] = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback;
        v13[2] = 0;
        *v13 = Value[10];
        *((_BYTE *)v13 + 8) = 2;
        Value[10] = v13;
      }
      v14 = 4;
      if ( (unsigned int)(*((_DWORD *)v10 + 52) + 1) > 4 )
        v14 = *((_DWORD *)v10 + 52) + 1;
      v15 = *((int *)v10 + 2);
      if ( v14 != (_DWORD)v15 )
      {
        Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(v10, (unsigned int)v14);
        if ( v14 > (int)v15 )
          memset_0((void *)(*(_QWORD *)v10 + 24 * v15), 0, 24LL * (v14 - (int)v15));
      }
      v16 = *((int *)v10 + 52);
      *((_DWORD *)v10 + 52) = v16 + 1;
      v16 *= 3;
      v17 = *(_QWORD *)v10;
      *(_DWORD *)(v17 + 8 * v16) = v5;
      *(_QWORD *)(v17 + 8 * v16 + 8) = v7;
      *(_BYTE *)(v17 + 8 * v16 + 16) = v6;
      *(_DWORD *)(v17 + 8 * v16 + 20) = 0;
      goto LABEL_10;
    }
  }
  if ( !*((_BYTE *)this + 68) )
    return;
  v1 = *((_QWORD *)this + 4);
  if ( v1 )
    ++*(_DWORD *)(v1 + 16);
  if ( !*(_DWORD *)(v1 + 180) )
    Microsoft::CoreUI::Support::Win32Event::Set(*(_QWORD *)(v1 + 144));
LABEL_10:
  System::Object::ReleaseNotFrozen$((System::Object *)v1);
}

```

## disassembly

```asm
0x18000adb0  push    rbx
0x18000adb2  push    rbp
0x18000adb3  push    rsi
0x18000adb4  push    rdi
0x18000adb5  push    r12
0x18000adb7  push    r13
0x18000adb9  push    r14
0x18000adbb  push    r15
0x18000adbd  sub     rsp, 28h
0x18000adc1  mov     rbx, [rcx+38h]
0x18000adc5  test    rbx, rbx
0x18000adc8  jnz     short loc_18000AE27
0x18000adca  cmp     byte ptr [rcx+44h], 0
0x18000adce  jz      short loc_18000AE16
0x18000add0  mov     rbx, [rcx+20h]
0x18000add4  test    rbx, rbx
0x18000add7  jz      short loc_18000ADDC
0x18000add9  inc     dword ptr [rbx+10h]
0x18000addc  cmp     dword ptr [rbx+0B4h], 0
0x18000ade3  ja      short loc_18000AE0E
0x18000ade5  mov     rcx, [rbx+90h]
0x18000adec  call    ?Set@Win32Event@Support@CoreUI@Microsoft@@SAXUWin32Handle@234@@Z; Microsoft::CoreUI::Support::Win32Event::Set(Microsoft::CoreUI::Support::Win32Handle)
0x18000adf1  jmp     short loc_18000AE0E
0x18000adf3  mov     r14, [rdi+38h]
0x18000adf7  cmp     dword ptr [r14+68h], 0
0x18000adfc  jnz     short loc_18000AE4B
0x18000adfe  cmp     byte ptr [rbx+34h], 0
0x18000ae02  jnz     short loc_18000AE4B
0x18000ae04  cmp     byte ptr [rdi+20h], 0
0x18000ae08  jnz     loc_18000AFCF
0x18000ae0e  mov     rcx, rbx; this
0x18000ae11  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000ae16  add     rsp, 28h
0x18000ae1a  pop     r15
0x18000ae1c  pop     r14
0x18000ae1e  pop     r13
0x18000ae20  pop     r12
0x18000ae22  pop     rdi
0x18000ae23  pop     rsi
0x18000ae24  pop     rbp
0x18000ae25  pop     rbx
0x18000ae26  retn
0x18000ae27  mov     rax, [rcx+20h]
0x18000ae2b  cmp     byte ptr [rax+0B0h], 0
0x18000ae32  jnz     short loc_18000ADCA
0x18000ae34  cmp     dword ptr [rax+44h], 4
0x18000ae38  jz      short loc_18000ADCA
0x18000ae3a  inc     dword ptr [rbx+10h]
0x18000ae3d  mov     rax, [rbx+20h]
0x18000ae41  mov     rdi, [rax+20h]
0x18000ae45  cmp     dword ptr [rdi+48h], 0
0x18000ae49  jnz     short loc_18000ADF3
0x18000ae4b  mov     rax, [rdi+0A8h]
0x18000ae52  mov     rcx, [rax+20h]
0x18000ae56  mov     rax, [rcx+38h]
0x18000ae5a  mov     r14d, [rax+38h]
0x18000ae5e  mov     eax, 10h
0x18000ae63  test    r14d, r14d
0x18000ae66  cmovz   r14d, eax
0x18000ae6a  cmp     dword ptr [rbx+30h], 3
0x18000ae6e  jz      loc_18000AF55
0x18000ae74  xor     r12b, r12b
0x18000ae77  mov     rbp, [rbx+28h]
0x18000ae7b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000ae81  call    cs:__imp_TlsGetValue
0x18000ae87  mov     rsi, rax
0x18000ae8a  test    rax, rax
0x18000ae8d  jnz     short loc_18000AE95
0x18000ae8f  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000ae95  lock inc dword ptr [rbp+20h]
0x18000ae99  call    ?GetForCurrentThread@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAPEAV1234@XZ; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread(void)
0x18000ae9e  mov     rdi, rax
0x18000aea1  xor     r13d, r13d
0x18000aea4  cmp     [rax+0D0h], r13d
0x18000aeab  jnz     short loc_18000AF0B
0x18000aead  mov     dword ptr [rsp+68h+Count], r13d
0x18000aeb2  lea     rdx, [rsp+68h+Count]; unsigned int *
0x18000aeb7  mov     ecx, 20h ; ' '; unsigned __int64
0x18000aebc  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000aec1  mov     rcx, [rsp+68h]; this
0x18000aec6  test    eax, eax
0x18000aec8  js      loc_18000AFE8
0x18000aece  mov     r15d, dword ptr [rsp+68h+Count]
0x18000aed3  mov     edx, 1; Size
0x18000aed8  mov     ecx, r15d; Count
0x18000aedb  call    cs:__imp_calloc
0x18000aee1  mov     rdx, rax
0x18000aee4  test    rax, rax
0x18000aee7  jz      loc_18000AFFD
0x18000aeed  lea     rax, ?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)
0x18000aef4  mov     [rdx+18h], rax
0x18000aef8  mov     [rdx+10h], r13
0x18000aefc  mov     rax, [rsi+50h]
0x18000af00  mov     [rdx], rax
0x18000af03  mov     byte ptr [rdx+8], 2
0x18000af07  mov     [rsi+50h], rdx
0x18000af0b  mov     eax, [rdi+0D0h]
0x18000af11  inc     eax
0x18000af13  mov     esi, 4
0x18000af18  cmp     eax, esi
0x18000af1a  cmova   esi, eax
0x18000af1d  movsxd  r15, dword ptr [rdi+8]
0x18000af21  cmp     esi, r15d
0x18000af24  jnz     short loc_18000AF8F
0x18000af26  movsxd  rcx, dword ptr [rdi+0D0h]
0x18000af2d  lea     eax, [rcx+1]
0x18000af30  mov     [rdi+0D0h], eax
0x18000af36  lea     rcx, [rcx+rcx*2]
0x18000af3a  mov     rax, [rdi]
0x18000af3d  mov     [rax+rcx*8], r14d
0x18000af41  mov     [rax+rcx*8+8], rbp
0x18000af46  mov     [rax+rcx*8+10h], r12b
0x18000af4b  mov     [rax+rcx*8+14h], r13d
0x18000af50  jmp     loc_18000AE0E
0x18000af55  mov     rdi, [rdi+30h]
0x18000af59  call    cs:__imp_GetCurrentThreadId
0x18000af5f  cmp     eax, [rdi+0B0h]
0x18000af65  jnz     loc_18000AE74
0x18000af6b  mov     rbp, [rbx+28h]
0x18000af6f  call    cs:__imp_GetCurrentThreadId
0x18000af75  mov     rcx, [rbx+20h]
0x18000af79  mov     rdx, [rcx+20h]
0x18000af7d  mov     rcx, [rdx+30h]; char16_t *
0x18000af81  cmp     eax, [rcx+0B0h]
0x18000af87  jz      short loc_18000AFC7
0x18000af89  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000af8f  mov     rcx, rdi
0x18000af92  test    esi, esi
0x18000af94  jz      short loc_18000B006
0x18000af96  mov     edx, esi
0x18000af98  call    ?Resize@?$GlobalVectorF@UDeferredUserCall@Dispatch@CoreUI@Microsoft@@@Engine@Cn@@IEAAXH@Z; Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(int)
0x18000af9d  cmp     esi, r15d
0x18000afa0  jle     short loc_18000AF26
0x18000afa2  sub     esi, r15d
0x18000afa5  movsxd  rax, esi
0x18000afa8  lea     r8, [rax+rax*2]
0x18000afac  shl     r8, 3; Size
0x18000afb0  lea     rcx, [r15+r15*2]
0x18000afb4  mov     rax, [rdi]
0x18000afb7  lea     rcx, [rax+rcx*8]; void *
0x18000afbb  xor     edx, edx; Val
0x18000afbd  call    memset_0
0x18000afc2  jmp     loc_18000AF26
0x18000afc7  mov     r12b, 1
0x18000afca  jmp     loc_18000AE7B
0x18000afcf  mov     r14d, [r14+38h]
0x18000afd3  cmp     r14d, 6
0x18000afd7  jge     loc_18000AE6A
0x18000afdd  mov     r14d, 6
0x18000afe3  jmp     loc_18000AE6A
0x18000afe8  mov     r9d, eax; char *
0x18000afeb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aff2  mov     edx, 10Fh; void *
0x18000aff7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000affd  mov     rcx, r15; unsigned __int64
0x18000b000  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
0x18000b006  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18000b00b  jmp     loc_18000AF26
```
