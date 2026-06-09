# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(EventRegistrationToken)

- ea: `0x18000da00`
- end: `0x18000dbfe`
- name: `?Remove@?$EventSource@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e150`
- `0x180010040`

## callees

- `0x18000c5a0`
- `0x18000d890`
- `0x18000da00`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dab7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000db2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dab7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000db2b`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(
        __int64 a1,
        __int64 a2)
{
  RTL_SRWLOCK *v4; // rbp
  volatile signed __int32 *v5; // rax
  volatile signed __int32 *v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // r12
  bool v9; // r15
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rcx
  int v14; // esi
  volatile signed __int32 *v15; // rax
  _QWORD *v16; // rcx
  __int64 *v17; // r14
  __int64 v18; // r13
  volatile signed __int32 *v19; // rax
  __int64 v20; // rcx
  char v21; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v22; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v23; // [rsp+78h] [rbp+10h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h]

  v4 = (RTL_SRWLOCK *)(a1 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  v5 = *(volatile signed __int32 **)a1;
  if ( !*(_QWORD *)a1 )
  {
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return 0;
  }
  v6 = 0;
  v22 = 0;
  v7 = (_QWORD *)*((_QWORD *)v5 + 2);
  v8 = ((__int64)(*((_QWORD *)v5 + 3) - (_QWORD)v7) >> 3) - 1;
  v23 = (_QWORD *)v8;
  if ( !v8 )
  {
    v9 = *v7 == a2;
LABEL_6:
    v10 = 0;
    if ( v9 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
      if ( &v21 != (char *)a1 )
      {
        v10 = *(volatile signed __int32 **)a1;
        *(_QWORD *)a1 = 0;
      }
      v11 = v6;
      v6 = 0;
      v12 = *(volatile signed __int32 **)a1;
      *(_QWORD *)a1 = v11;
      if ( v12 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v12);
      if ( a1 != -8 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
    }
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v6);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v10 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v10);
    return 0;
  }
  v14 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(
          &v22,
          &v23);
  if ( v14 >= 0 )
  {
    v9 = 0;
    v15 = *(volatile signed __int32 **)a1;
    v16 = *(_QWORD **)(*(_QWORD *)a1 + 32LL);
    v23 = v16;
    v17 = (__int64 *)*((_QWORD *)v15 + 2);
    v6 = v22;
    while ( v17 != *((__int64 **)v15 + 3) )
    {
      if ( v9 || a2 != *v17 )
      {
        if ( !v8 )
          goto LABEL_6;
        v24 = *v16;
        v18 = *v17;
        v19 = (volatile signed __int32 *)*((_QWORD *)v6 + 3);
        v22 = v19;
        if ( *(_QWORD *)v19 != v18 )
        {
          if ( v18 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
            v19 = v22;
          }
          v20 = *(_QWORD *)v19;
          *(_QWORD *)v19 = v18;
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        *(_QWORD *)(*((_QWORD *)v6 + 4) + 8 * ((__int64)(*((_QWORD *)v6 + 3) - *((_QWORD *)v6 + 2)) >> 3)) = v24;
        *((_QWORD *)v6 + 3) += 8LL;
        v16 = ++v23;
        --v8;
      }
      else
      {
        v9 = 1;
      }
      ++v17;
      v15 = *(volatile signed __int32 **)a1;
    }
    goto LABEL_6;
  }
  if ( v22 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v22);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000da00  mov     [rsp+arg_18], rbx
0x18000da05  push    rbp
0x18000da06  push    rsi
0x18000da07  push    rdi
0x18000da08  push    r12
0x18000da0a  push    r13
0x18000da0c  push    r14
0x18000da0e  push    r15
0x18000da10  sub     rsp, 30h
0x18000da14  mov     rbx, rdx
0x18000da17  mov     rdi, rcx
0x18000da1a  lea     rbp, [rcx+10h]
0x18000da1e  mov     rcx, rbp; SRWLock
0x18000da21  call    cs:__imp_AcquireSRWLockExclusive
0x18000da27  mov     rax, [rdi]
0x18000da2a  test    rax, rax
0x18000da2d  jnz     short loc_18000DA46
0x18000da2f  test    rbp, rbp
0x18000da32  jz      loc_18000DAE5
0x18000da38  mov     rcx, rbp; SRWLock
0x18000da3b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000da41  jmp     loc_18000DAE5
0x18000da46  xor     esi, esi
0x18000da48  mov     [rsp+68h+arg_0], rsi
0x18000da4d  mov     rcx, [rax+10h]
0x18000da51  mov     r12, [rax+18h]
0x18000da55  sub     r12, rcx
0x18000da58  sar     r12, 3
0x18000da5c  sub     r12, 1
0x18000da60  mov     [rsp+68h+arg_8], r12
0x18000da65  jnz     loc_18000DAFF
0x18000da6b  cmp     [rcx], rbx
0x18000da6e  setz    r15b
0x18000da72  xor     ebx, ebx
0x18000da74  test    r15b, r15b
0x18000da77  jz      short loc_18000DABD
0x18000da79  lea     r14, [rdi+8]
0x18000da7d  mov     rcx, r14; SRWLock
0x18000da80  call    cs:__imp_AcquireSRWLockExclusive
0x18000da86  lea     rax, [rsp+68h+var_48]
0x18000da8b  cmp     rax, rdi
0x18000da8e  jz      short loc_18000DA9A
0x18000da90  mov     rbx, [rdi]
0x18000da93  mov     qword ptr [rdi], 0
0x18000da9a  mov     rax, rsi
0x18000da9d  xor     esi, esi
0x18000da9f  mov     rcx, [rdi]
0x18000daa2  mov     [rdi], rax
0x18000daa5  test    rcx, rcx
0x18000daa8  jz      short loc_18000DAAF
0x18000daaa  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000daaf  test    r14, r14
0x18000dab2  jz      short loc_18000DABD
0x18000dab4  mov     rcx, r14; SRWLock
0x18000dab7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dabd  test    rsi, rsi
0x18000dac0  jz      short loc_18000DACA
0x18000dac2  mov     rcx, rsi
0x18000dac5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000daca  test    rbp, rbp
0x18000dacd  jz      short loc_18000DAD8
0x18000dacf  mov     rcx, rbp; SRWLock
0x18000dad2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dad8  test    rbx, rbx
0x18000dadb  jz      short loc_18000DAE5
0x18000dadd  mov     rcx, rbx
0x18000dae0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000dae5  xor     eax, eax
0x18000dae7  mov     rbx, [rsp+68h+arg_18]
0x18000daef  add     rsp, 30h
0x18000daf3  pop     r15
0x18000daf5  pop     r14
0x18000daf7  pop     r13
0x18000daf9  pop     r12
0x18000dafb  pop     rdi
0x18000dafc  pop     rsi
0x18000dafd  pop     rbp
0x18000dafe  retn
0x18000daff  lea     rdx, [rsp+68h+arg_8]
0x18000db04  lea     rcx, [rsp+68h+arg_0]
0x18000db09  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@AEA_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@AEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &)
0x18000db0e  mov     esi, eax
0x18000db10  test    eax, eax
0x18000db12  jns     short loc_18000DB35
0x18000db14  mov     rcx, [rsp+68h+arg_0]
0x18000db19  test    rcx, rcx
0x18000db1c  jz      short loc_18000DB23
0x18000db1e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000db23  test    rbp, rbp
0x18000db26  jz      short loc_18000DB31
0x18000db28  mov     rcx, rbp; SRWLock
0x18000db2b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000db31  mov     eax, esi
0x18000db33  jmp     short loc_18000DAE7
0x18000db35  xor     r15b, r15b
0x18000db38  mov     rax, [rdi]
0x18000db3b  mov     rcx, [rax+20h]
0x18000db3f  mov     [rsp+68h+arg_8], rcx
0x18000db44  mov     r14, [rax+10h]
0x18000db48  mov     rsi, [rsp+68h+arg_0]
0x18000db4d  cmp     r14, [rax+18h]
0x18000db51  jz      loc_18000DA72
0x18000db57  test    r15b, r15b
0x18000db5a  jnz     short loc_18000DB69
0x18000db5c  cmp     rbx, [r14]
0x18000db5f  jnz     short loc_18000DB69
0x18000db61  mov     r15b, 1
0x18000db64  jmp     loc_18000DBF2
0x18000db69  test    r12, r12
0x18000db6c  jz      loc_18000DA72
0x18000db72  mov     rax, [rcx]
0x18000db75  mov     [rsp+68h+arg_10], rax
0x18000db7d  mov     r13, [r14]
0x18000db80  mov     rax, [rsi+18h]
0x18000db84  mov     [rsp+68h+arg_0], rax
0x18000db89  cmp     [rax], r13
0x18000db8c  jz      short loc_18000DBC0
0x18000db8e  test    r13, r13
0x18000db91  jz      short loc_18000DBA8
0x18000db93  mov     rax, [r13+0]
0x18000db97  mov     rcx, r13
0x18000db9a  mov     rax, [rax+8]
0x18000db9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba3  mov     rax, [rsp+68h+arg_0]
0x18000dba8  mov     rcx, [rax]
0x18000dbab  mov     [rax], r13
0x18000dbae  test    rcx, rcx
0x18000dbb1  jz      short loc_18000DBC0
0x18000dbb3  mov     rax, [rcx]
0x18000dbb6  mov     rax, [rax+10h]
0x18000dbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbbf  nop
0x18000dbc0  mov     rcx, [rsi+18h]
0x18000dbc4  sub     rcx, [rsi+10h]
0x18000dbc8  sar     rcx, 3
0x18000dbcc  mov     rax, [rsi+20h]
0x18000dbd0  mov     rdx, [rsp+68h+arg_10]
0x18000dbd8  mov     [rax+rcx*8], rdx
0x18000dbdc  add     qword ptr [rsi+18h], 8
0x18000dbe1  mov     rcx, [rsp+68h+arg_8]
0x18000dbe6  add     rcx, 8
0x18000dbea  mov     [rsp+68h+arg_8], rcx
0x18000dbef  dec     r12
0x18000dbf2  add     r14, 8
0x18000dbf6  mov     rax, [rdi]
0x18000dbf9  jmp     loc_18000DB4D
```
