# Microsoft::CoreUI::Dispatch::WaitController::TryRemoveIocpCompletion(uint,uint)

- ea: `0x180009930`
- end: `0x180009c4f`
- name: `?TryRemoveIocpCompletion@WaitController@Dispatch@CoreUI@Microsoft@@AEAA?AUWakeRecord@234@II@Z`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800091b0`

## callees

- `0x180009930`
- `0x18000a98c`
- `0x18000ec10`
- `0x180010ed0`
- `0x18008ae1c`
- `0x18008cb30`
- `0x18008cc78`
- `0x18008f3cc`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009a0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009ad7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009bb3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009a0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009ad7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009bb3`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800099ab`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800099ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::CoreUI::Dispatch::WaitController::TryRemoveIocpCompletion(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  int v4; // ebx
  int v7; // eax
  const char16_t *v8; // rcx
  __int64 v9; // r8
  System::Object *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // r13
  System::Object *v15; // rdi
  __int64 v16; // rax
  System::Object *v17; // r15
  int v18; // esi
  System::Object *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  char *Value; // rax
  System::Object *v24; // rbx
  int v25; // eax
  __int64 i; // rax
  int v27; // [rsp+30h] [rbp-49h]
  __int64 v28; // [rsp+38h] [rbp-41h] BYREF
  struct Cn::Engine::GCHandleLocalEntry *v29; // [rsp+40h] [rbp-39h] BYREF
  __int64 v30; // [rsp+48h] [rbp-31h]
  __int64 v31; // [rsp+50h] [rbp-29h]
  int v32; // [rsp+58h] [rbp-21h]
  unsigned int v33[4]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v34; // [rsp+70h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+80h] [rbp+7h] BYREF

  v4 = a4;
  v32 = a3;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  LODWORD(v28) = 0;
  v30 = 0;
  v31 = 0;
  v29 = 0;
  v7 = ((__int64 (__fastcall *)(_QWORD, unsigned int *, __int64, __int64 *, struct Cn::Engine::GCHandleLocalEntry **, _BYTE, int))NtRemoveIoCompletionEx)(
         *(_QWORD *)(a1 + 88),
         v33,
         1,
         &v28,
         &v29,
         0,
         a4);
  if ( v7 )
  {
    if ( v7 != 258 )
      Cn::FailFast::ForNtStatus(v7);
LABEL_3:
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    *(_BYTE *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    v10 = *(System::Object **)a2;
    *(_QWORD *)a2 = 0;
    if ( v10 )
      System::Object::ReleaseNotFrozen$(v10);
    *(_DWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_DWORD *)(a2 + 24) = a3;
    *(_DWORD *)(a2 + 28) = v4;
    *(_BYTE *)(a2 + 32) = 1;
    v11 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
    v12 = *(unsigned int *)(v11 + 72);
    if ( (v12 & 0x80000000) != 0 )
      CFlat::Abandonment::Fail((const char16_t *)v11);
    *(_QWORD *)(a2 + 40) = v12;
    *(_QWORD *)(a2 + 48) = 0;
    return a2;
  }
  v13 = v33[2];
  v14 = *(_QWORD *)v33;
  if ( (v33[2] & 0x80000000) == 0 && !*(_QWORD *)v33 )
  {
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (__int64)v8,
        (const EVENT_DESCRIPTOR *)IoCompletionPort_RemovedEndOfBatch,
        v9,
        1u,
        &v35);
    v4 = v27;
    goto LABEL_3;
  }
  v30 = *(_QWORD *)&v33[2];
  v31 = *(_QWORD *)v33;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
  {
    McTemplateU0pp_EventWriteTransfer(v8, IoCompletionPort_RemovedCompletion, *(_QWORD *)&v33[2], *(_QWORD *)v33);
    v14 = v31;
    v13 = v30;
  }
  v15 = 0;
  v35.Ptr = 0;
  if ( v13 < 0 )
  {
    v16 = 0;
    v17 = 0;
  }
  else
  {
    if ( !v14 )
      CFlat::Abandonment::Fail(v8);
    v29 = 0;
    Value = (char *)TlsGetValue(Cn::Context::s_tlsStorage);
    Cn::Engine::GCHandleTable::LocalValidateValue(
      (Cn::Engine::GCHandleTable *)(Value + 248),
      v14,
      &v29,
      (struct Cn::Engine::GCHandleEntryID *)&v28);
    v24 = *(System::Object **)v29;
    v15 = *(System::Object **)v29;
    if ( *(_QWORD *)v29 )
    {
      v25 = *((_DWORD *)v24 + 4);
      if ( v25 > 0 )
        *((_DWORD *)v24 + 4) = v25 + 1;
      for ( i = *((_QWORD *)v24 + 1); ; i = *(_QWORD *)(i + 24) )
      {
        if ( !i )
          CFlat::Abandonment::Fail(&Microsoft::CoreUI::Dispatch::RegisteredWait::TypeId$);
        if ( (const char16_t *)i == &Microsoft::CoreUI::Dispatch::RegisteredWait::TypeId$ )
          break;
      }
      ++*((_DWORD *)v24 + 4);
      System::Object::Release$(v24);
    }
    v17 = v15;
    v16 = *((_QWORD *)v24 + 6);
    *((_BYTE *)v24 + 56) = 0;
    v14 = v31;
    v13 = v30;
  }
  v28 = v16;
  v18 = HIDWORD(v30);
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_BYTE *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 40) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  if ( v17 )
    ++*((_DWORD *)v17 + 4);
  v19 = *(System::Object **)a2;
  *(_QWORD *)a2 = v17;
  if ( v19 )
  {
    System::Object::ReleaseNotFrozen$(v19);
    v16 = v28;
  }
  *(_DWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = v16;
  *(_DWORD *)(a2 + 24) = v32;
  *(_DWORD *)(a2 + 28) = v27;
  *(_BYTE *)(a2 + 32) = 1;
  v20 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
  v21 = *(unsigned int *)(v20 + 72);
  if ( (v21 & 0x80000000) != 0 )
    CFlat::Abandonment::Fail((const char16_t *)v20);
  *(_QWORD *)(a2 + 40) = v21;
  *(_QWORD *)(a2 + 48) = 0;
  if ( v13 < 0 && (v17 || v28) )
    CFlat::Abandonment::Fail((const char16_t *)v20);
  *(_DWORD *)(a2 + 40) = v13;
  *(_DWORD *)(a2 + 44) = v18;
  *(_QWORD *)(a2 + 48) = v14;
  if ( v15 )
    System::Object::ReleaseNotFrozen$(v15);
  return a2;
}

```

## disassembly

```asm
0x180009930  mov     [rsp-8+arg_10], rbx
0x180009935  push    rbp
0x180009936  push    rsi
0x180009937  push    rdi
0x180009938  push    r12
0x18000993a  push    r13
0x18000993c  push    r14
0x18000993e  push    r15
0x180009940  lea     rbp, [rsp-27h]
0x180009945  sub     rsp, 0A0h
0x18000994c  mov     rax, cs:__security_cookie
0x180009953  xor     rax, rsp
0x180009956  mov     [rbp+57h+var_40], rax
0x18000995a  mov     ebx, r9d
0x18000995d  mov     [rbp+57h+var_A0], ebx
0x180009960  mov     edi, r8d
0x180009963  mov     [rbp+57h+var_78], r8d
0x180009967  mov     r14, rdx
0x18000996a  mov     [rbp+57h+var_90], rdx
0x18000996e  xor     esi, esi
0x180009970  xor     eax, eax
0x180009972  xorps   xmm0, xmm0
0x180009975  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180009979  movups  [rbp+57h+var_60], xmm0
0x18000997d  mov     dword ptr [rbp+57h+var_98], esi
0x180009980  mov     [rbp+57h+var_88], rsi
0x180009984  mov     [rbp+57h+var_80], rsi
0x180009988  mov     [rbp+57h+var_90], rsi
0x18000998c  mov     [rsp+0D0h+var_A8], al
0x180009990  lea     rax, [rbp+57h+var_90]
0x180009994  mov     [rsp+0D0h+var_B0], rax
0x180009999  lea     r9, [rbp+57h+var_98]
0x18000999d  mov     r8d, 1
0x1800099a3  lea     rdx, [rbp+57h+var_70]
0x1800099a7  mov     rcx, [rcx+58h]
0x1800099ab  call    cs:__imp_NtRemoveIoCompletionEx
0x1800099b1  test    eax, eax
0x1800099b3  jz      short loc_180009A2F
0x1800099b5  cmp     eax, 102h
0x1800099ba  jnz     loc_180009BA1
0x1800099c0  mov     r12d, 80000000h
0x1800099c6  mov     [r14], rsi
0x1800099c9  mov     [r14+8], esi
0x1800099cd  mov     [r14+10h], rsi
0x1800099d1  mov     [r14+18h], rsi
0x1800099d5  mov     [r14+20h], sil
0x1800099d9  mov     [r14+28h], rsi
0x1800099dd  mov     [r14+30h], rsi
0x1800099e1  mov     rcx, [r14]; this
0x1800099e4  mov     [r14], rsi
0x1800099e7  test    rcx, rcx
0x1800099ea  jz      short loc_1800099F1
0x1800099ec  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800099f1  mov     [r14+8], esi
0x1800099f5  mov     [r14+10h], rsi
0x1800099f9  mov     [r14+18h], edi
0x1800099fd  mov     [r14+1Ch], ebx
0x180009a01  mov     byte ptr [r14+20h], 1
0x180009a06  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009a0c  call    cs:__imp_TlsGetValue
0x180009a12  mov     rcx, [rax+30h]; char16_t *
0x180009a16  mov     eax, [rcx+48h]
0x180009a19  test    r12, rax
0x180009a1c  jnz     loc_180009B5E
0x180009a22  mov     [r14+28h], rax
0x180009a26  mov     [r14+30h], rsi
0x180009a2a  jmp     loc_180009B23
0x180009a2f  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x180009a33  mov     r13, qword ptr [rbp+57h+var_70]
0x180009a37  mov     r12d, 80000000h
0x180009a3d  test    r12d, ebx
0x180009a40  jz      loc_180009B64
0x180009a46  mov     [rbp+57h+var_88], rbx
0x180009a4a  mov     [rbp+57h+var_80], r13
0x180009a4e  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x180009a55  jnz     loc_180009B82
0x180009a5b  mov     rdi, rsi
0x180009a5e  mov     qword ptr [rbp+57h+var_50], rsi
0x180009a62  test    r12d, ebx
0x180009a65  jz      loc_180009B4D
0x180009a6b  mov     rax, rsi
0x180009a6e  mov     r15, rsi
0x180009a71  mov     [rbp+57h+var_98], rax
0x180009a75  mov     esi, dword ptr [rbp+57h+var_88+4]
0x180009a78  xor     ecx, ecx
0x180009a7a  mov     [r14], rcx
0x180009a7d  mov     [r14+8], ecx
0x180009a81  mov     [r14+10h], rcx
0x180009a85  mov     [r14+18h], rcx
0x180009a89  mov     [r14+20h], cl
0x180009a8d  mov     [r14+28h], rcx
0x180009a91  mov     [r14+30h], rcx
0x180009a95  test    r15, r15
0x180009a98  jz      short loc_180009A9E
0x180009a9a  inc     dword ptr [r15+10h]
0x180009a9e  mov     rcx, [r14]; this
0x180009aa1  mov     [r14], r15
0x180009aa4  test    rcx, rcx
0x180009aa7  jz      short loc_180009AB2
0x180009aa9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009aae  mov     rax, [rbp+57h+var_98]
0x180009ab2  mov     dword ptr [r14+8], 0
0x180009aba  mov     [r14+10h], rax
0x180009abe  mov     eax, [rbp+57h+var_78]
0x180009ac1  mov     [r14+18h], eax
0x180009ac5  mov     eax, [rbp+57h+var_A0]
0x180009ac8  mov     [r14+1Ch], eax
0x180009acc  mov     byte ptr [r14+20h], 1
0x180009ad1  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009ad7  call    cs:__imp_TlsGetValue
0x180009add  mov     rcx, [rax+30h]; char16_t *
0x180009ae1  mov     eax, [rcx+48h]
0x180009ae4  test    r12, rax
0x180009ae7  jnz     short loc_180009B58
0x180009ae9  mov     [r14+28h], rax
0x180009aed  mov     qword ptr [r14+30h], 0
0x180009af5  test    ebx, ebx
0x180009af7  jns     short loc_180009B0A
0x180009af9  test    r15, r15
0x180009afc  jnz     short loc_180009B04
0x180009afe  cmp     [rbp+57h+var_98], r15
0x180009b02  jz      short loc_180009B0A
0x180009b04  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009b0a  mov     [r14+28h], ebx
0x180009b0e  mov     [r14+2Ch], esi
0x180009b12  mov     [r14+30h], r13
0x180009b16  test    rdi, rdi
0x180009b19  jz      short loc_180009B23
0x180009b1b  mov     rcx, rdi; this
0x180009b1e  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009b23  mov     rax, r14
0x180009b26  mov     rcx, [rbp+57h+var_40]
0x180009b2a  xor     rcx, rsp; StackCookie
0x180009b2d  call    __security_check_cookie
0x180009b32  mov     rbx, [rsp+0D0h+arg_10]
0x180009b3a  add     rsp, 0A0h
0x180009b41  pop     r15
0x180009b43  pop     r14
0x180009b45  pop     r13
0x180009b47  pop     r12
0x180009b49  pop     rdi
0x180009b4a  pop     rsi
0x180009b4b  pop     rbp
0x180009b4c  retn
0x180009b4d  test    r13, r13
0x180009b50  jnz     short loc_180009BA9
0x180009b52  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009b58  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009b5e  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009b64  test    r13, r13
0x180009b67  jnz     loc_180009A46
0x180009b6d  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x180009b74  jnz     loc_180009C2F
0x180009b7a  mov     ebx, [rbp+57h+var_A0]
0x180009b7d  jmp     loc_1800099C6
0x180009b82  mov     r9, r13
0x180009b85  mov     r8, rbx
0x180009b88  lea     rdx, IoCompletionPort_RemovedCompletion
0x180009b8f  call    McTemplateU0pp_EventWriteTransfer
0x180009b94  mov     r13, [rbp+57h+var_80]
0x180009b98  mov     rbx, [rbp+57h+var_88]
0x180009b9c  jmp     loc_180009A5B
0x180009ba1  mov     ecx, eax; int
0x180009ba3  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
0x180009ba9  mov     [rbp+57h+var_90], rsi
0x180009bad  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009bb3  call    cs:__imp_TlsGetValue
0x180009bb9  lea     rcx, [rax+0F8h]; this
0x180009bc0  lea     r9, [rbp+57h+var_98]; struct Cn::Engine::GCHandleEntryID *
0x180009bc4  lea     r8, [rbp+57h+var_90]; struct Cn::Engine::GCHandleLocalEntry **
0x180009bc8  mov     edx, r13d; unsigned int
0x180009bcb  call    ?LocalValidateValue@GCHandleTable@Engine@Cn@@AEAAXIPEAPEAUGCHandleLocalEntry@23@PEAUGCHandleEntryID@23@@Z; Cn::Engine::GCHandleTable::LocalValidateValue(uint,Cn::Engine::GCHandleLocalEntry * *,Cn::Engine::GCHandleEntryID *)
0x180009bd0  mov     rax, [rbp+57h+var_90]
0x180009bd4  mov     rbx, [rax]
0x180009bd7  mov     rdi, rbx
0x180009bda  test    rbx, rbx
0x180009bdd  jz      short loc_180009C11
0x180009bdf  mov     eax, [rbx+10h]
0x180009be2  test    eax, eax
0x180009be4  jle     short loc_180009BEB
0x180009be6  inc     eax
0x180009be8  mov     [rbx+10h], eax
0x180009beb  mov     rax, [rbx+8]
0x180009bef  lea     rcx, ?TypeId$@RegisteredWait@Dispatch@CoreUI@Microsoft@@2U?$ObjectTypeIdField@VRegisteredWait@Dispatch@CoreUI@Microsoft@@$0A@$0A@@CFlat@@B; char16_t *
0x180009bf6  test    rax, rax
0x180009bf9  jz      short loc_180009C29
0x180009bfb  cmp     rax, rcx
0x180009bfe  jz      short loc_180009C06
0x180009c00  mov     rax, [rax+18h]
0x180009c04  jmp     short loc_180009BF6
0x180009c06  inc     dword ptr [rbx+10h]
0x180009c09  mov     rcx, rbx; this
0x180009c0c  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180009c11  mov     r15, rdi
0x180009c14  mov     rax, [rbx+30h]
0x180009c18  mov     byte ptr [rbx+38h], 0
0x180009c1c  mov     r13, [rbp+57h+var_80]
0x180009c20  mov     rbx, [rbp+57h+var_88]
0x180009c24  jmp     loc_180009A71
0x180009c29  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009c2f  lea     rax, [rbp+57h+var_50]
0x180009c33  mov     [rsp+0D0h+var_B0], rax
0x180009c38  mov     r9d, 1
0x180009c3e  lea     rdx, IoCompletionPort_RemovedEndOfBatch
0x180009c45  call    McGenEventWrite_EventWriteTransfer
0x180009c4a  jmp     loc_180009B7A
```
