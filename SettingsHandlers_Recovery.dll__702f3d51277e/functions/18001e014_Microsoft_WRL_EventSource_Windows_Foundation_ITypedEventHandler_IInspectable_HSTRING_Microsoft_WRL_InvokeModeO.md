# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x18001e014`
- end: `0x18001e212`
- name: `?Remove@?$EventSource@U?$ITypedEventHandler@PEAUIInspectable@@PEAUHSTRING__@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `510`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f688`
- `0x180023460`
- `0x1800234a0`

## callees

- `0x18000fca4`
- `0x18001dd30`
- `0x18001e014`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e035`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e094`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e035`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e094`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e04f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e13f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e04f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e13f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
        RTL_SRWLOCK *a1,
        __int64 a2)
{
  RTL_SRWLOCK *v4; // rbp
  RTL_SRWLOCK v5; // rax
  _QWORD *v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // r12
  bool v9; // r15
  RTL_SRWLOCK v10; // rbx
  _QWORD *v11; // rax
  RTL_SRWLOCK v12; // rcx
  int v14; // esi
  RTL_SRWLOCK v15; // rax
  _QWORD *v16; // rcx
  __int64 *v17; // r14
  __int64 v18; // r13
  _QWORD *v19; // rax
  __int64 v20; // rcx
  char v21; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v22; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v23; // [rsp+78h] [rbp+10h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h]

  v4 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v5.Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return 0;
  }
  v6 = 0;
  v22 = 0;
  v7 = (_QWORD *)*((_QWORD *)v5.Ptr + 2);
  v8 = ((__int64)(*((_QWORD *)v5.Ptr + 3) - (_QWORD)v7) >> 3) - 1;
  v23 = (_QWORD *)v8;
  if ( !v8 )
  {
    v9 = *v7 == a2;
LABEL_6:
    v10.Ptr = 0;
    if ( v9 )
    {
      AcquireSRWLockExclusive(a1 + 1);
      if ( &v21 != (char *)a1 )
      {
        v10.Ptr = a1->Ptr;
        a1->Ptr = 0;
      }
      v11 = v6;
      v6 = 0;
      v12.Ptr = a1->Ptr;
      a1->Ptr = v11;
      if ( v12.Ptr )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v12.Ptr);
      if ( a1 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(a1 + 1);
    }
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v6);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v10.Ptr )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v10.Ptr);
    return 0;
  }
  v14 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v22,
          &v23);
  if ( v14 >= 0 )
  {
    v9 = 0;
    v15.Ptr = a1->Ptr;
    v16 = (_QWORD *)*((_QWORD *)a1->Ptr + 4);
    v23 = v16;
    v17 = (__int64 *)*((_QWORD *)v15.Ptr + 2);
    v6 = v22;
    while ( v17 != *((__int64 **)v15.Ptr + 3) )
    {
      if ( v9 || a2 != *v17 )
      {
        if ( !v8 )
          goto LABEL_6;
        v24 = *v16;
        v18 = *v17;
        v19 = (_QWORD *)v6[3];
        v22 = v19;
        if ( *v19 != v18 )
        {
          if ( v18 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
            v19 = v22;
          }
          v20 = *v19;
          *v19 = v18;
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        *(_QWORD *)(v6[4] + 8 * ((__int64)(v6[3] - v6[2]) >> 3)) = v24;
        v6[3] += 8LL;
        v16 = ++v23;
        --v8;
      }
      else
      {
        v9 = 1;
      }
      ++v17;
      v15.Ptr = a1->Ptr;
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
0x18001e014  mov     [rsp+arg_18], rbx
0x18001e019  push    rbp
0x18001e01a  push    rsi
0x18001e01b  push    rdi
0x18001e01c  push    r12
0x18001e01e  push    r13
0x18001e020  push    r14
0x18001e022  push    r15
0x18001e024  sub     rsp, 30h
0x18001e028  mov     rbx, rdx
0x18001e02b  mov     rdi, rcx
0x18001e02e  lea     rbp, [rcx+10h]
0x18001e032  mov     rcx, rbp; SRWLock
0x18001e035  call    cs:__imp_AcquireSRWLockExclusive
0x18001e03b  mov     rax, [rdi]
0x18001e03e  test    rax, rax
0x18001e041  jnz     short loc_18001E05A
0x18001e043  test    rbp, rbp
0x18001e046  jz      loc_18001E0F9
0x18001e04c  mov     rcx, rbp; SRWLock
0x18001e04f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e055  jmp     loc_18001E0F9
0x18001e05a  xor     esi, esi
0x18001e05c  mov     [rsp+68h+arg_0], rsi
0x18001e061  mov     rcx, [rax+10h]
0x18001e065  mov     r12, [rax+18h]
0x18001e069  sub     r12, rcx
0x18001e06c  sar     r12, 3
0x18001e070  sub     r12, 1
0x18001e074  mov     [rsp+68h+arg_8], r12
0x18001e079  jnz     loc_18001E113
0x18001e07f  cmp     [rcx], rbx
0x18001e082  setz    r15b
0x18001e086  xor     ebx, ebx
0x18001e088  test    r15b, r15b
0x18001e08b  jz      short loc_18001E0D1
0x18001e08d  lea     r14, [rdi+8]
0x18001e091  mov     rcx, r14; SRWLock
0x18001e094  call    cs:__imp_AcquireSRWLockExclusive
0x18001e09a  lea     rax, [rsp+68h+var_48]
0x18001e09f  cmp     rax, rdi
0x18001e0a2  jz      short loc_18001E0AE
0x18001e0a4  mov     rbx, [rdi]
0x18001e0a7  mov     qword ptr [rdi], 0
0x18001e0ae  mov     rax, rsi
0x18001e0b1  xor     esi, esi
0x18001e0b3  mov     rcx, [rdi]
0x18001e0b6  mov     [rdi], rax
0x18001e0b9  test    rcx, rcx
0x18001e0bc  jz      short loc_18001E0C3
0x18001e0be  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e0c3  test    r14, r14
0x18001e0c6  jz      short loc_18001E0D1
0x18001e0c8  mov     rcx, r14; SRWLock
0x18001e0cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e0d1  test    rsi, rsi
0x18001e0d4  jz      short loc_18001E0DE
0x18001e0d6  mov     rcx, rsi
0x18001e0d9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e0de  test    rbp, rbp
0x18001e0e1  jz      short loc_18001E0EC
0x18001e0e3  mov     rcx, rbp; SRWLock
0x18001e0e6  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e0ec  test    rbx, rbx
0x18001e0ef  jz      short loc_18001E0F9
0x18001e0f1  mov     rcx, rbx
0x18001e0f4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e0f9  xor     eax, eax
0x18001e0fb  mov     rbx, [rsp+68h+arg_18]
0x18001e103  add     rsp, 30h
0x18001e107  pop     r15
0x18001e109  pop     r14
0x18001e10b  pop     r13
0x18001e10d  pop     r12
0x18001e10f  pop     rdi
0x18001e110  pop     rsi
0x18001e111  pop     rbp
0x18001e112  retn
0x18001e113  lea     rdx, [rsp+68h+arg_8]
0x18001e118  lea     rcx, [rsp+68h+arg_0]
0x18001e11d  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x18001e122  mov     esi, eax
0x18001e124  test    eax, eax
0x18001e126  jns     short loc_18001E149
0x18001e128  mov     rcx, [rsp+68h+arg_0]
0x18001e12d  test    rcx, rcx
0x18001e130  jz      short loc_18001E137
0x18001e132  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e137  test    rbp, rbp
0x18001e13a  jz      short loc_18001E145
0x18001e13c  mov     rcx, rbp; SRWLock
0x18001e13f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e145  mov     eax, esi
0x18001e147  jmp     short loc_18001E0FB
0x18001e149  xor     r15b, r15b
0x18001e14c  mov     rax, [rdi]
0x18001e14f  mov     rcx, [rax+20h]
0x18001e153  mov     [rsp+68h+arg_8], rcx
0x18001e158  mov     r14, [rax+10h]
0x18001e15c  mov     rsi, [rsp+68h+arg_0]
0x18001e161  cmp     r14, [rax+18h]
0x18001e165  jz      loc_18001E086
0x18001e16b  test    r15b, r15b
0x18001e16e  jnz     short loc_18001E17D
0x18001e170  cmp     rbx, [r14]
0x18001e173  jnz     short loc_18001E17D
0x18001e175  mov     r15b, 1
0x18001e178  jmp     loc_18001E206
0x18001e17d  test    r12, r12
0x18001e180  jz      loc_18001E086
0x18001e186  mov     rax, [rcx]
0x18001e189  mov     [rsp+68h+arg_10], rax
0x18001e191  mov     r13, [r14]
0x18001e194  mov     rax, [rsi+18h]
0x18001e198  mov     [rsp+68h+arg_0], rax
0x18001e19d  cmp     [rax], r13
0x18001e1a0  jz      short loc_18001E1D4
0x18001e1a2  test    r13, r13
0x18001e1a5  jz      short loc_18001E1BC
0x18001e1a7  mov     rax, [r13+0]
0x18001e1ab  mov     rcx, r13
0x18001e1ae  mov     rax, [rax+8]
0x18001e1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1b7  mov     rax, [rsp+68h+arg_0]
0x18001e1bc  mov     rcx, [rax]
0x18001e1bf  mov     [rax], r13
0x18001e1c2  test    rcx, rcx
0x18001e1c5  jz      short loc_18001E1D4
0x18001e1c7  mov     rax, [rcx]
0x18001e1ca  mov     rax, [rax+10h]
0x18001e1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d3  nop
0x18001e1d4  mov     rcx, [rsi+18h]
0x18001e1d8  sub     rcx, [rsi+10h]
0x18001e1dc  sar     rcx, 3
0x18001e1e0  mov     rax, [rsi+20h]
0x18001e1e4  mov     rdx, [rsp+68h+arg_10]
0x18001e1ec  mov     [rax+rcx*8], rdx
0x18001e1f0  add     qword ptr [rsi+18h], 8
0x18001e1f5  mov     rcx, [rsp+68h+arg_8]
0x18001e1fa  add     rcx, 8
0x18001e1fe  mov     [rsp+68h+arg_8], rcx
0x18001e203  dec     r12
0x18001e206  add     r14, 8
0x18001e20a  mov     rax, [rdi]
0x18001e20d  jmp     loc_18001E161
```
