# CASTraceProvider::ExecuteCustomAction::StartActivity(_GUID,ushort const *,ushort const *,uint)

- ea: `0x14000abc0`
- end: `0x14000ac9a`
- name: `?StartActivity@ExecuteCustomAction@CASTraceProvider@@QEAAXU_GUID@@PEBG1I@Z`
- size: `218`
- prototype: `void __fastcall(CASTraceProvider::ExecuteCustomAction *this, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140008bc4`

## callees

- `0x140001b5c`
- `0x14000258c`
- `0x140008ba0`
- `0x14000a594`
- `0x14000abc0`
- `0x14000ba4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ac1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ac1e`

## pseudocode

```c
void __fastcall CASTraceProvider::ExecuteCustomAction::StartActivity(
        CASTraceProvider::ExecuteCustomAction *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD a5)
{
  __int128 v5; // xmm0
  unsigned int v6; // eax
  __int64 v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF

  v5 = (__int128)*a2;
  v6 = a5;
  *((_QWORD *)this + 44) = a3;
  *((_OWORD *)this + 21) = v5;
  *((_QWORD *)this + 45) = a4;
  *((_DWORD *)this + 92) = v6;
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v9 = CASTraceProvider::Provider(v8);
  v12 = (__int64)v9;
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10, v11) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v14 = *((_QWORD *)this + 34);
    a5 = CurrentThreadId;
    v16 = 0x1000000;
    if ( !*(_BYTE *)(v14 + 4)
      || (v15 = v14 + 24, !*(_DWORD *)(v14 + 24))
      && !*(_DWORD *)(v14 + 28)
      && !*(_DWORD *)(v14 + 32)
      && !*(_DWORD *)(v14 + 36) )
    {
      v15 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)byte_140011CED,
      v14 + 8,
      v15,
      (__int64)&v16,
      (__int64)&a5);
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000abc0  mov     [rsp+arg_8], rbx
0x14000abc5  push    rdi
0x14000abc6  sub     rsp, 30h
0x14000abca  movups  xmm0, xmmword ptr [rdx]
0x14000abcd  mov     eax, [rsp+38h+arg_20]
0x14000abd1  mov     rbx, rcx
0x14000abd4  mov     [rcx+160h], r8
0x14000abdb  movdqu  xmmword ptr [rcx+150h], xmm0
0x14000abe3  mov     [rcx+168h], r9
0x14000abea  mov     [rcx+170h], eax
0x14000abf0  call    ?zInternalStart@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000abf5  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000abfa  mov     rdi, rax
0x14000abfd  mov     edx, [rax]
0x14000abff  cmp     edx, 5
0x14000ac02  jbe     loc_14000AC88
0x14000ac08  mov     rdx, 400000000000h
0x14000ac12  mov     rcx, rax
0x14000ac15  call    _tlgKeywordOn
0x14000ac1a  test    al, al
0x14000ac1c  jz      short loc_14000AC88
0x14000ac1e  call    cs:__imp_GetCurrentThreadId
0x14000ac24  mov     r8, [rbx+110h]
0x14000ac2b  mov     [rsp+38h+arg_20], eax
0x14000ac2f  mov     [rsp+38h+arg_0], 1000000h
0x14000ac38  cmp     byte ptr [r8+4], 0
0x14000ac3d  jz      short loc_14000AC5E
0x14000ac3f  lea     r9, [r8+18h]
0x14000ac43  cmp     dword ptr [r9], 0
0x14000ac47  jnz     short loc_14000AC61
0x14000ac49  cmp     dword ptr [r9+4], 0
0x14000ac4e  jnz     short loc_14000AC61
0x14000ac50  cmp     dword ptr [r9+8], 0
0x14000ac55  jnz     short loc_14000AC61
0x14000ac57  cmp     dword ptr [r9+0Ch], 0
0x14000ac5c  jnz     short loc_14000AC61
0x14000ac5e  xor     r9d, r9d
0x14000ac61  lea     rax, [rsp+38h+arg_20]
0x14000ac66  add     r8, 8
0x14000ac6a  mov     [rsp+38h+var_10], rax
0x14000ac6f  lea     rdx, byte_140011CED
0x14000ac76  lea     rax, [rsp+38h+arg_0]
0x14000ac7b  mov     rcx, rdi
0x14000ac7e  mov     [rsp+38h+var_18], rax
0x14000ac83  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000ac88  mov     rcx, rbx
0x14000ac8b  mov     rbx, [rsp+38h+arg_8]
0x14000ac90  add     rsp, 30h
0x14000ac94  pop     rdi
0x14000ac95  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
