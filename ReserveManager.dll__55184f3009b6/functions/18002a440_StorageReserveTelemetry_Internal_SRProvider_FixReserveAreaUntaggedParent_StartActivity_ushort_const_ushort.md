# StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StartActivity(ushort const *,ushort)

- ea: `0x18002a440`
- end: `0x18002a642`
- name: `?StartActivity@FixReserveAreaUntaggedParent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGG@Z`
- size: `514`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *this, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180027414`

## callees

- `0x1800013b4`
- `0x180003870`
- `0x1800042dc`
- `0x1800042f4`
- `0x180007990`
- `0x180028ac8`
- `0x18002939c`
- `0x18002a440`
- `0x18002cfdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a4f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a60e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a4f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a60e`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *this,
        const unsigned __int16 *a2,
        __int16 a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // eax
  __int64 v15; // rax
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v18; // rbx
  _QWORD *Local; // rax
  __int16 v20; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v21; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  DWORD *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  __int16 *v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, a2);
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v6 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  v7 = (int)v6;
  v8 = *(unsigned int *)v6;
  if ( (unsigned int)v8 > 5 )
  {
    v9 = *((_QWORD *)v6 + 3);
    v8 = *((_QWORD *)v6 + 2);
    if ( (v8 & 0x400000000000LL) != 0 )
    {
      v8 = v9 & 0x400000000000LL;
      if ( (v9 & 0x400000000000LL) == v9 )
      {
        v20 = a3;
        v10 = *StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                 (unsigned __int16 **)&lpMem,
                 Destination);
        CurrentThreadId = GetCurrentThreadId();
        v12 = *((_QWORD *)this + 34);
        v21 = CurrentThreadId;
        v22 = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        v32 = &v20;
        v14 = 2;
        v33 = 2;
        if ( v10 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v10[v15] );
          v14 = 2 * v15 + 2;
        }
        else
        {
          v10 = (unsigned __int16 *)&qword_18003A1F8;
        }
        v30 = v14;
        v29 = v10;
        v27 = &v21;
        v31 = 0;
        v25 = &v22;
        v28 = 4;
        v26 = 8;
        tlgWriteTransfer_EventWriteTransfer(v7, (int)&dword_180044D44, v12 + 8, v13, 6u, &v24);
        v16 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v16);
        }
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v18 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v8,
                          1);
      *v18 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v18;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v18 = 0;
    }
  }
}

```

## disassembly

```asm
0x18002a440  mov     [rsp-8+arg_10], rbx
0x18002a445  push    rbp
0x18002a446  push    rsi
0x18002a447  push    rdi
0x18002a448  push    r14
0x18002a44a  push    r15
0x18002a44c  lea     rbp, [rsp-1D0h]
0x18002a454  sub     rsp, 2D0h
0x18002a45b  mov     rax, cs:__security_cookie
0x18002a462  xor     rax, rsp
0x18002a465  mov     [rbp+1F0h+var_30], rax
0x18002a46c  movzx   r14d, r8w
0x18002a470  mov     rbx, rdx
0x18002a473  mov     rdi, rcx
0x18002a476  xor     edx, edx; Val
0x18002a478  mov     r8d, 208h; Size
0x18002a47e  lea     rcx, [rbp+1F0h+Destination]; void *
0x18002a482  call    memset_0
0x18002a487  mov     r8, rbx; Source
0x18002a48a  lea     rcx, [rbp+1F0h+Destination]; Destination
0x18002a48e  mov     edx, 104h; SizeInWords
0x18002a493  call    wcscpy_s
0x18002a498  mov     rcx, rdi
0x18002a49b  call    ?zInternalStart@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002a4a0  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a4a5  xor     r15d, r15d
0x18002a4a8  mov     rsi, rax
0x18002a4ab  mov     ecx, [rax]
0x18002a4ad  cmp     ecx, 5
0x18002a4b0  jbe     loc_18002A5DC
0x18002a4b6  mov     rdx, [rax+18h]
0x18002a4ba  mov     rcx, [rax+10h]
0x18002a4be  mov     rax, 400000000000h
0x18002a4c8  test    rax, rcx
0x18002a4cb  jz      loc_18002A5DC
0x18002a4d1  mov     rcx, rdx
0x18002a4d4  and     rcx, rax
0x18002a4d7  cmp     rcx, rdx
0x18002a4da  jnz     loc_18002A5DC
0x18002a4e0  lea     rdx, [rbp+1F0h+Destination]
0x18002a4e4  mov     [rsp+2F0h+var_2C0], r14w
0x18002a4ea  lea     rcx, [rsp+2F0h+lpMem]
0x18002a4ef  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002a4f4  mov     rbx, [rax]
0x18002a4f7  call    cs:__imp_GetCurrentThreadId
0x18002a4fd  mov     r8, [rdi+110h]
0x18002a504  mov     [rsp+2F0h+var_2BC], eax
0x18002a508  mov     [rsp+2F0h+var_2B8], 1000000h
0x18002a511  cmp     [r8+4], r15b
0x18002a515  jz      short loc_18002A532
0x18002a517  lea     r9, [r8+18h]
0x18002a51b  cmp     [r9], r15d
0x18002a51e  jnz     short loc_18002A535
0x18002a520  cmp     [r9+4], r15d
0x18002a524  jnz     short loc_18002A535
0x18002a526  cmp     [r9+8], r15d
0x18002a52a  jnz     short loc_18002A535
0x18002a52c  cmp     [r9+0Ch], r15d
0x18002a530  jnz     short loc_18002A535
0x18002a532  mov     r9, r15; int
0x18002a535  lea     rax, [rsp+2F0h+var_2C0]
0x18002a53a  mov     [rbp+1F0h+var_250], rax
0x18002a53e  mov     eax, 2
0x18002a543  mov     [rbp+1F0h+var_248], rax
0x18002a547  test    rbx, rbx
0x18002a54a  jz      short loc_18002A563
0x18002a54c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a550  inc     rax
0x18002a553  cmp     [rbx+rax*2], r15w
0x18002a558  jnz     short loc_18002A550
0x18002a55a  lea     eax, ds:2[rax*2]
0x18002a561  jmp     short loc_18002A56A
0x18002a563  lea     rbx, qword_18003A1F8
0x18002a56a  mov     [rbp+1F0h+var_258], eax
0x18002a56d  lea     rdx, dword_180044D44; int
0x18002a574  lea     rax, [rsp+2F0h+var_2BC]
0x18002a579  mov     [rbp+1F0h+var_260], rbx
0x18002a57d  mov     [rbp+1F0h+var_270], rax
0x18002a581  add     r8, 8; int
0x18002a585  lea     rax, [rsp+2F0h+var_2B8]
0x18002a58a  mov     [rbp+1F0h+var_254], r15d
0x18002a58e  mov     [rsp+2F0h+var_280], rax
0x18002a593  mov     rcx, rsi; int
0x18002a596  lea     rax, [rsp+2F0h+var_2A0]
0x18002a59b  mov     [rbp+1F0h+var_268], 4
0x18002a5a3  mov     [rsp+2F0h+var_2C8], rax; PEVENT_DATA_DESCRIPTOR
0x18002a5a8  mov     [rsp+2F0h+var_2D0], 6; ULONG
0x18002a5b0  mov     [rsp+2F0h+var_278], 8
0x18002a5b9  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a5be  mov     rbx, [rsp+2F0h+lpMem]
0x18002a5c3  test    rbx, rbx
0x18002a5c6  jz      short loc_18002A5DC
0x18002a5c8  call    cs:__imp_GetProcessHeap
0x18002a5ce  mov     r8, rbx; lpMem
0x18002a5d1  xor     edx, edx; dwFlags
0x18002a5d3  mov     rcx, rax; hHeap
0x18002a5d6  call    cs:__imp_HeapFree
0x18002a5dc  cmp     [rdi+138h], r15d
0x18002a5e3  jnz     short loc_18002A61C
0x18002a5e5  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a5ec  lea     rbx, [rdi+120h]
0x18002a5f3  jz      short loc_18002A619
0x18002a5f5  mov     dl, 1
0x18002a5f7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002a5fc  mov     [rbx], rax
0x18002a5ff  test    rax, rax
0x18002a602  jz      short loc_18002A61C
0x18002a604  mov     rcx, [rax]
0x18002a607  mov     [rbx+10h], rcx
0x18002a60b  mov     [rax], rbx
0x18002a60e  call    cs:__imp_GetCurrentThreadId
0x18002a614  mov     [rbx+18h], eax
0x18002a617  jmp     short loc_18002A61C
0x18002a619  mov     [rbx], r15
0x18002a61c  mov     rcx, [rbp+1F0h+var_30]
0x18002a623  xor     rcx, rsp; StackCookie
0x18002a626  call    __security_check_cookie
0x18002a62b  mov     rbx, [rsp+2F0h+arg_10]
0x18002a633  add     rsp, 2D0h
0x18002a63a  pop     r15
0x18002a63c  pop     r14
0x18002a63e  pop     rdi
0x18002a63f  pop     rsi
0x18002a640  pop     rbp
0x18002a641  retn
```
