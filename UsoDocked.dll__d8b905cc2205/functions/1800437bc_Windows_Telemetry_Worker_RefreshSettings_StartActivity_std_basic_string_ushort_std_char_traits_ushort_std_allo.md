# Windows::Telemetry::Worker::RefreshSettings::StartActivity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800437bc`
- end: `0x18004395c`
- name: `?StartActivity@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180042130`

## callees

- `0x1800019cc`
- `0x180007660`
- `0x180016180`
- `0x180041c1c`
- `0x1800437bc`
- `0x1800445d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004383d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004383d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043932`

## pseudocode

```c
int __fastcall Windows::Telemetry::Worker::RefreshSettings::StartActivity(__int64 a1, const wchar_t *a2, char a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 Local; // rax
  bool v10; // cc
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rbx
  char v18; // [rsp+30h] [rbp-59h] BYREF
  DWORD v19; // [rsp+34h] [rbp-55h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v22; // [rsp+60h] [rbp-29h]
  __int64 v23; // [rsp+68h] [rbp-21h]
  DWORD *v24; // [rsp+70h] [rbp-19h]
  __int64 v25; // [rsp+78h] [rbp-11h]
  const wchar_t *v26; // [rsp+80h] [rbp-9h]
  int v27; // [rsp+88h] [rbp-1h]
  int v28; // [rsp+8Ch] [rbp+3h]
  char *v29; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]

  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
  LODWORD(Local) = *(_DWORD *)v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    v7 = *(_QWORD *)(v8 + 24);
    v6 = 0x400000000000LL;
    Local = *(_QWORD *)(v8 + 16);
    if ( (Local & 0x400000000000LL) != 0 )
    {
      LODWORD(Local) = 0;
      if ( (v7 & 0x400000000000LL) == v7 )
      {
        v10 = *((_QWORD *)a2 + 3) <= 7u;
        v18 = a3;
        if ( !v10 )
          a2 = *(const wchar_t **)a2;
        CurrentThreadId = GetCurrentThreadId();
        v12 = *(_QWORD *)(a1 + 272);
        v19 = CurrentThreadId;
        v20 = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        v30 = 1;
        v29 = &v18;
        if ( a2 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          v15 = 2 * v14 + 2;
        }
        else
        {
          a2 = &psz;
          v15 = 2;
        }
        v27 = v15;
        v26 = a2;
        v24 = &v19;
        v28 = 0;
        v22 = &v20;
        v25 = 4;
        v23 = 8;
        LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v8, (int)&word_180081CB2, (int)v12 + 8, v13, 6u, &v21);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v16 = (__int64 *)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v6) = 1;
      Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(v7, v6);
      *v16 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *(_QWORD *)Local;
        *(_QWORD *)Local = v16;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(a1 + 312) = Local;
      }
    }
    else
    {
      *v16 = 0;
    }
  }
  return Local;
}

```

## disassembly

```asm
0x1800437bc  push    rbp
0x1800437be  push    rbx
0x1800437bf  push    rsi
0x1800437c0  push    rdi
0x1800437c1  push    r14
0x1800437c3  push    r15
0x1800437c5  lea     rbp, [rsp-2Fh]
0x1800437ca  sub     rsp, 0B8h
0x1800437d1  mov     rax, cs:__security_cookie
0x1800437d8  xor     rax, rsp
0x1800437db  mov     [rbp+57h+var_40], rax
0x1800437df  mov     sil, r8b
0x1800437e2  mov     rbx, rdx
0x1800437e5  mov     rdi, rcx
0x1800437e8  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800437ed  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800437f2  xor     r15d, r15d
0x1800437f5  mov     r14, [rax+8]
0x1800437f9  mov     eax, [r14]
0x1800437fc  cmp     eax, 5
0x1800437ff  jbe     loc_180043900
0x180043805  mov     rcx, [r14+18h]
0x180043809  mov     rdx, 400000000000h
0x180043813  mov     rax, [r14+10h]
0x180043817  test    rdx, rax
0x18004381a  jz      loc_180043900
0x180043820  mov     rax, rcx
0x180043823  and     rax, rdx
0x180043826  cmp     rax, rcx
0x180043829  jnz     loc_180043900
0x18004382f  cmp     qword ptr [rbx+18h], 7
0x180043834  mov     [rbp+57h+var_B0], sil
0x180043838  jbe     short loc_18004383D
0x18004383a  mov     rbx, [rbx]
0x18004383d  call    cs:__imp_GetCurrentThreadId
0x180043843  mov     r8, [rdi+110h]
0x18004384a  mov     [rbp+57h+var_AC], eax
0x18004384d  mov     [rbp+57h+var_A8], 1000000h
0x180043855  cmp     [r8+4], r15b
0x180043859  jz      short loc_180043876
0x18004385b  lea     r9, [r8+18h]
0x18004385f  cmp     [r9], r15d
0x180043862  jnz     short loc_180043879
0x180043864  cmp     [r9+4], r15d
0x180043868  jnz     short loc_180043879
0x18004386a  cmp     [r9+8], r15d
0x18004386e  jnz     short loc_180043879
0x180043870  cmp     [r9+0Ch], r15d
0x180043874  jnz     short loc_180043879
0x180043876  mov     r9, r15; int
0x180043879  mov     [rbp+57h+var_48], 1
0x180043881  lea     rax, [rbp+57h+var_B0]
0x180043885  mov     [rbp+57h+var_50], rax
0x180043889  test    rbx, rbx
0x18004388c  jz      short loc_1800438A5
0x18004388e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043892  inc     rax
0x180043895  cmp     [rbx+rax*2], r15w
0x18004389a  jnz     short loc_180043892
0x18004389c  lea     eax, ds:2[rax*2]
0x1800438a3  jmp     short loc_1800438B1
0x1800438a5  lea     rbx, psz
0x1800438ac  mov     eax, 2
0x1800438b1  mov     [rbp+57h+var_58], eax
0x1800438b4  lea     rdx, word_180081CB2; int
0x1800438bb  lea     rax, [rbp+57h+var_AC]
0x1800438bf  mov     [rbp+57h+var_60], rbx
0x1800438c3  mov     [rbp+57h+var_70], rax
0x1800438c7  add     r8, 8; int
0x1800438cb  lea     rax, [rbp+57h+var_A8]
0x1800438cf  mov     [rbp+57h+var_54], r15d
0x1800438d3  mov     [rbp+57h+var_80], rax
0x1800438d7  mov     rcx, r14; int
0x1800438da  lea     rax, [rbp+57h+var_A0]
0x1800438de  mov     [rbp+57h+var_68], 4
0x1800438e6  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1800438eb  mov     [rsp+0E0h+var_C0], 6; ULONG
0x1800438f3  mov     [rbp+57h+var_78], 8
0x1800438fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180043900  cmp     [rdi+138h], r15d
0x180043907  jnz     short loc_180043940
0x180043909  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180043910  lea     rbx, [rdi+120h]
0x180043917  jz      short loc_18004393D
0x180043919  mov     dl, 1
0x18004391b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180043920  mov     [rbx], rax
0x180043923  test    rax, rax
0x180043926  jz      short loc_180043940
0x180043928  mov     rcx, [rax]
0x18004392b  mov     [rbx+10h], rcx
0x18004392f  mov     [rax], rbx
0x180043932  call    cs:__imp_GetCurrentThreadId
0x180043938  mov     [rbx+18h], eax
0x18004393b  jmp     short loc_180043940
0x18004393d  mov     [rbx], r15
0x180043940  mov     rcx, [rbp+57h+var_40]
0x180043944  xor     rcx, rsp; StackCookie
0x180043947  call    __security_check_cookie
0x18004394c  add     rsp, 0B8h
0x180043953  pop     r15
0x180043955  pop     r14
0x180043957  pop     rdi
0x180043958  pop     rsi
0x180043959  pop     rbx
0x18004395a  pop     rbp
0x18004395b  retn
```
