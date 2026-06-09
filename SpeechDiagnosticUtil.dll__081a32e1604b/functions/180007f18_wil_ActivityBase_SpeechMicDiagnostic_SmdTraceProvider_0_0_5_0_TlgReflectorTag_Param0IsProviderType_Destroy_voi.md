# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x180007f18`
- end: `0x18000802c`
- name: `?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `276`
- prototype: ``
- caller_count: `17`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007828`
- `0x180007854`
- `0x180007880`
- `0x1800078ac`
- `0x1800078d8`
- `0x180007918`
- `0x180007944`
- `0x180007970`
- `0x180007e38`
- `0x180008040`
- `0x180008190`
- `0x1800082d0`
- `0x1800084a0`
- `0x180008d10`
- `0x180008fe0`
- `0x180009330`
- `0x18000d2a0`

## callees

- `0x180002ce0`
- `0x180003290`
- `0x1800062cc`
- `0x180007588`
- `0x180007f18`
- `0x180008c58`
- `0x180011010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007fa2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007fa2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  char *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  if ( !a1[35] )
    goto LABEL_13;
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    SRWLock);
  v2 = (volatile signed __int32 *)a1[35];
  if ( v2 && *v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
      {
        v4 = (char *)a1[35];
        if ( v4 )
        {
          wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(v4 + 8);
          operator delete(v4);
        }
      }
      a1[35] = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)a1[34];
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    }
  }
}

```

## disassembly

```asm
0x180007f18  mov     [rsp+arg_8], rbx
0x180007f1d  mov     [rsp+arg_10], rsi
0x180007f22  push    rdi
0x180007f23  sub     rsp, 0D0h
0x180007f2a  mov     rbx, rcx
0x180007f2d  cmp     qword ptr [rcx+118h], 0
0x180007f35  jz      short loc_180007FB3
0x180007f37  lea     rdx, [rsp+0D8h+SRWLock]
0x180007f3c  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180007f41  mov     rcx, [rbx+118h]
0x180007f48  test    rcx, rcx
0x180007f4b  jz      short loc_180007F57
0x180007f4d  cmp     dword ptr [rcx], 1
0x180007f50  jnz     short loc_180007F57
0x180007f52  mov     sil, 1
0x180007f55  jmp     short loc_180007F98
0x180007f57  xor     sil, sil
0x180007f5a  test    rcx, rcx
0x180007f5d  jz      short loc_180007F98
0x180007f5f  or      eax, 0FFFFFFFFh
0x180007f62  lock xadd [rcx], eax
0x180007f66  cmp     eax, 1
0x180007f69  jnz     short loc_180007F8D
0x180007f6b  mov     rdi, [rbx+118h]
0x180007f72  test    rdi, rdi
0x180007f75  jz      short loc_180007F8D
0x180007f77  lea     rcx, [rdi+8]
0x180007f7b  call    ??1?$ActivityData@VSmdTraceProvider@SpeechMicDiagnostic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180007f80  mov     edx, 110h; unsigned __int64
0x180007f85  mov     rcx, rdi; void *
0x180007f88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007f8d  mov     qword ptr [rbx+118h], 0
0x180007f98  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x180007f9d  test    rcx, rcx
0x180007fa0  jz      short loc_180007FAE
0x180007fa2  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fa9  nop     dword ptr [rax+rax+00h]
0x180007fae  test    sil, sil
0x180007fb1  jz      short loc_180007FF9
0x180007fb3  mov     rcx, [rbx+110h]
0x180007fba  cmp     dword ptr [rcx], 1
0x180007fbd  jnz     short loc_180007FF9
0x180007fbf  mov     eax, 8007023Eh
0x180007fc4  cmp     dword ptr [rcx+58h], 0
0x180007fc8  cmovl   eax, [rcx+58h]
0x180007fcc  mov     edx, [rcx+0F8h]
0x180007fd2  cmp     edx, 1
0x180007fd5  jl      short loc_18000800F
0x180007fd7  cmp     dword ptr [rcx+48h], 0
0x180007fdb  jl      short loc_180007FE0
0x180007fdd  mov     [rcx+48h], eax
0x180007fe0  lea     eax, [rdx-1]
0x180007fe3  mov     [rcx+0F8h], eax
0x180007fe9  mov     rax, [rbx]
0x180007fec  mov     rcx, rbx
0x180007fef  mov     rax, [rax+8]
0x180007ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff8  nop
0x180007ff9  lea     r11, [rsp+0D8h+var_8]
0x180008001  mov     rbx, [r11+18h]
0x180008005  mov     rsi, [r11+20h]
0x180008009  mov     rsp, r11
0x18000800c  pop     rdi
0x18000800d  retn
0x18000800f  xor     edx, edx; Val
0x180008011  mov     r8d, 98h; Size
0x180008017  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18000801c  call    memset_0
0x180008021  lea     rcx, [rsp+0D8h+var_A8]; this
0x180008026  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
