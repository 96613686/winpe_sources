# Windows::Telemetry::Worker::RefreshSettings::StartActivity(wil::basic_zstring_view<wchar_t>,bool)

- ea: `0x18003e568`
- end: `0x18003e6f9`
- name: `?StartActivity@RefreshSettings@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@_N@Z`
- size: `401`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003ef00`

## callees

- `0x180001f60`
- `0x180035e54`
- `0x18003e044`
- `0x18003e568`
- `0x1800430e8`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e5e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e5e8`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::StartActivity(__int64 a1, const wchar_t **a2, char a3)
{
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rsi
  const wchar_t *v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  char v14; // [rsp+38h] [rbp-49h] BYREF
  DWORD v15; // [rsp+3Ch] [rbp-45h] BYREF
  __int64 v16; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+48h] [rbp-39h] BYREF
  __int64 *v18; // [rsp+68h] [rbp-19h]
  __int64 v19; // [rsp+70h] [rbp-11h]
  DWORD *v20; // [rsp+78h] [rbp-9h]
  __int64 v21; // [rsp+80h] [rbp-1h]
  const wchar_t *v22; // [rsp+88h] [rbp+7h]
  int v23; // [rsp+90h] [rbp+Fh]
  int v24; // [rsp+94h] [rbp+13h]
  char *v25; // [rsp+98h] [rbp+17h]
  __int64 v26; // [rsp+A0h] [rbp+1Fh]
  const char *v27; // [rsp+A8h] [rbp+27h]
  __int64 v28; // [rsp+B0h] [rbp+2Fh]

  *(_BYTE *)(a1 + 328) = a3;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v7 = Windows::Telemetry::Base::Provider();
  if ( *(_DWORD *)v7 > 5u
    && (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v7 + 3) & 0x400000000000LL) == *((_QWORD *)v7 + 3) )
  {
    v14 = a3;
    v8 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_QWORD *)(a1 + 272);
    v15 = CurrentThreadId;
    v16 = 0x1000000;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = (const GUID *)(v10 + 24), !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    v28 = 18;
    v27 = "1507.2603.28012.0";
    v25 = &v14;
    v26 = 1;
    if ( v8 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v8[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      v8 = &S2;
      v13 = 2;
    }
    v23 = v13;
    v22 = v8;
    v20 = &v15;
    v24 = 0;
    v18 = &v16;
    v21 = 4;
    v19 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v7,
      (unsigned __int8 *)&byte_180091859,
      (const GUID *)(v10 + 8),
      v11,
      7u,
      &v17);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v6);
}

```

## disassembly

```asm
0x18003e568  mov     rax, rsp
0x18003e56b  mov     [rax+10h], rbx
0x18003e56f  mov     [rax+18h], rsi
0x18003e573  mov     [rax+20h], rdi
0x18003e577  push    rbp
0x18003e578  push    r14
0x18003e57a  push    r15
0x18003e57c  lea     rbp, [rax-5Fh]
0x18003e580  sub     rsp, 0C0h
0x18003e587  mov     rax, cs:__security_cookie
0x18003e58e  xor     rax, rsp
0x18003e591  mov     [rbp+57h+var_20], rax
0x18003e595  mov     bl, r8b
0x18003e598  mov     r14, rdx
0x18003e59b  mov     [rcx+148h], bl
0x18003e5a1  mov     rdi, rcx
0x18003e5a4  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003e5a9  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003e5ae  xor     r15d, r15d
0x18003e5b1  mov     rsi, rax
0x18003e5b4  cmp     dword ptr [rax], 5
0x18003e5b7  jbe     loc_18003E6BE
0x18003e5bd  mov     rax, 400000000000h
0x18003e5c7  test    [rsi+10h], rax
0x18003e5cb  jz      loc_18003E6BE
0x18003e5d1  mov     rcx, [rsi+18h]
0x18003e5d5  and     rcx, rax
0x18003e5d8  cmp     rcx, [rsi+18h]
0x18003e5dc  jnz     loc_18003E6BE
0x18003e5e2  mov     [rbp+57h+var_A0], bl
0x18003e5e5  mov     rbx, [r14]
0x18003e5e8  call    cs:__imp_GetCurrentThreadId
0x18003e5ee  mov     r8, [rdi+110h]
0x18003e5f5  mov     [rbp+57h+var_9C], eax
0x18003e5f8  mov     [rbp+57h+var_98], 1000000h
0x18003e600  cmp     [r8+4], r15b
0x18003e604  jz      short loc_18003E621
0x18003e606  lea     r9, [r8+18h]
0x18003e60a  cmp     [r9], r15d
0x18003e60d  jnz     short loc_18003E624
0x18003e60f  cmp     [r9+4], r15d
0x18003e613  jnz     short loc_18003E624
0x18003e615  cmp     [r9+8], r15d
0x18003e619  jnz     short loc_18003E624
0x18003e61b  cmp     [r9+0Ch], r15d
0x18003e61f  jnz     short loc_18003E624
0x18003e621  mov     r9, r15; int
0x18003e624  mov     [rbp+57h+var_28], 12h
0x18003e62c  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18003e633  mov     [rbp+57h+var_30], rax
0x18003e637  lea     rax, [rbp+57h+var_A0]
0x18003e63b  mov     [rbp+57h+var_40], rax
0x18003e63f  mov     [rbp+57h+var_38], 1
0x18003e647  test    rbx, rbx
0x18003e64a  jz      short loc_18003E663
0x18003e64c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e650  inc     rax
0x18003e653  cmp     [rbx+rax*2], r15w
0x18003e658  jnz     short loc_18003E650
0x18003e65a  lea     eax, ds:2[rax*2]
0x18003e661  jmp     short loc_18003E66F
0x18003e663  lea     rbx, S2
0x18003e66a  mov     eax, 2
0x18003e66f  mov     [rbp+57h+var_48], eax
0x18003e672  lea     rdx, byte_180091859; int
0x18003e679  lea     rax, [rbp+57h+var_9C]
0x18003e67d  mov     [rbp+57h+var_50], rbx
0x18003e681  mov     [rbp+57h+var_60], rax
0x18003e685  add     r8, 8; int
0x18003e689  lea     rax, [rbp+57h+var_98]
0x18003e68d  mov     [rbp+57h+var_44], r15d
0x18003e691  mov     [rbp+57h+var_70], rax
0x18003e695  mov     rcx, rsi; int
0x18003e698  lea     rax, [rbp+57h+var_90]
0x18003e69c  mov     [rbp+57h+var_58], 4
0x18003e6a4  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x18003e6a9  mov     [rsp+0D0h+var_B0], 7; ULONG
0x18003e6b1  mov     [rbp+57h+var_68], 8
0x18003e6b9  call    _tlgWriteTransfer_EventWriteTransfer
0x18003e6be  lea     rcx, [rdi+120h]; this
0x18003e6c5  cmp     [rcx+18h], r15d
0x18003e6c9  jnz     short loc_18003E6D0
0x18003e6cb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18003e6d0  mov     rcx, [rbp+57h+var_20]
0x18003e6d4  xor     rcx, rsp; StackCookie
0x18003e6d7  call    __security_check_cookie
0x18003e6dc  lea     r11, [rsp+0D0h+var_10]
0x18003e6e4  mov     rbx, [r11+28h]
0x18003e6e8  mov     rsi, [r11+30h]
0x18003e6ec  mov     rdi, [r11+38h]
0x18003e6f0  mov     rsp, r11
0x18003e6f3  pop     r15
0x18003e6f5  pop     r14
0x18003e6f7  pop     rbp
0x18003e6f8  retn
```
