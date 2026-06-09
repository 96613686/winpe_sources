# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x18001bb54`
- end: `0x18001bcef`
- name: `?Remove@?$EventSource@U?$ITypedEventHandler@PEAUIInspectable@@PEAUHSTRING__@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000c6a8`
- `0x180021ca0`
- `0x180021ce0`

## callees

- `0x18000d410`
- `0x1800113a8`
- `0x180012510`
- `0x18001b730`
- `0x18001bb54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bcc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bcc2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2)
{
  RTL_SRWLOCK *v2; // rdi
  _QWORD *Ptr; // rax
  struct IUnknown **v6; // rcx
  __int64 v7; // r15
  __int64 v8; // r15
  bool v9; // bp
  int v10; // ebp
  struct IUnknown **v12; // r14
  void **v13; // r12
  Microsoft::WRL::Details::EventTargetArray *v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v2 = a1 + 2;
  v15 = 0;
  AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  v6 = (struct IUnknown **)Ptr[2];
  v7 = Ptr[3] - (_QWORD)v6;
  v14 = 0;
  v8 = (v7 >> 3) - 1;
  v16 = v8;
  if ( !v8 )
  {
    v9 = *v6 == a2;
    goto LABEL_19;
  }
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v14,
          &v16);
  if ( v10 >= 0 )
  {
    v9 = 0;
    v12 = (struct IUnknown **)*((_QWORD *)a1->Ptr + 2);
    v13 = (void **)*((_QWORD *)a1->Ptr + 4);
    if ( v12 == *((struct IUnknown ***)a1->Ptr + 3) )
    {
LABEL_22:
      if ( v14 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      if ( v15 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
      return 0;
    }
    do
    {
      if ( v9 || a2 != *v12 )
      {
        if ( !v8 )
          break;
        Microsoft::WRL::Details::EventTargetArray::AddTail(v14, *v12, *v13++);
        --v8;
      }
      else
      {
        v9 = 1;
      }
      ++v12;
    }
    while ( v12 != *((struct IUnknown ***)a1->Ptr + 3) );
LABEL_19:
    if ( v9 )
    {
      AcquireSRWLockExclusive(a1 + 1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v15, a1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(a1, &v14);
      if ( a1 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(a1 + 1);
    }
    goto LABEL_22;
  }
  if ( v14 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001bb54  push    rbx
0x18001bb56  push    rbp
0x18001bb57  push    rsi
0x18001bb58  push    rdi
0x18001bb59  push    r12
0x18001bb5b  push    r14
0x18001bb5d  push    r15
0x18001bb5f  sub     rsp, 20h
0x18001bb63  lea     rdi, [rcx+10h]
0x18001bb67  mov     [rsp+58h+arg_8], 0
0x18001bb70  mov     rsi, rcx
0x18001bb73  mov     rbx, rdx
0x18001bb76  mov     rcx, rdi; SRWLock
0x18001bb79  call    cs:__imp_AcquireSRWLockExclusive
0x18001bb80  nop     dword ptr [rax+rax+00h]
0x18001bb85  mov     rax, [rsi]
0x18001bb88  test    rax, rax
0x18001bb8b  jnz     short loc_18001BBAA
0x18001bb8d  test    rdi, rdi
0x18001bb90  jz      loc_18001BCDD
0x18001bb96  mov     rcx, rdi; SRWLock
0x18001bb99  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bba0  nop     dword ptr [rax+rax+00h]
0x18001bba5  jmp     loc_18001BCDD
0x18001bbaa  mov     rcx, [rax+10h]
0x18001bbae  mov     r15, [rax+18h]
0x18001bbb2  sub     r15, rcx
0x18001bbb5  mov     [rsp+58h+arg_0], 0
0x18001bbbe  sar     r15, 3
0x18001bbc2  sub     r15, 1
0x18001bbc6  mov     [rsp+58h+arg_10], r15
0x18001bbcb  jnz     short loc_18001BBD9
0x18001bbcd  cmp     [rcx], rbx
0x18001bbd0  setz    bpl
0x18001bbd4  jmp     loc_18001BC65
0x18001bbd9  lea     rdx, [rsp+58h+arg_10]
0x18001bbde  lea     rcx, [rsp+58h+arg_0]
0x18001bbe3  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x18001bbe8  mov     ebp, eax
0x18001bbea  test    eax, eax
0x18001bbec  jns     short loc_18001BC18
0x18001bbee  mov     rcx, [rsp+58h+arg_0]
0x18001bbf3  test    rcx, rcx
0x18001bbf6  jz      short loc_18001BBFD
0x18001bbf8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001bbfd  test    rdi, rdi
0x18001bc00  jz      short loc_18001BC11
0x18001bc02  mov     rcx, rdi; SRWLock
0x18001bc05  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bc0c  nop     dword ptr [rax+rax+00h]
0x18001bc11  mov     eax, ebp
0x18001bc13  jmp     loc_18001BCDF
0x18001bc18  mov     rax, [rsi]
0x18001bc1b  xor     bpl, bpl
0x18001bc1e  mov     r14, [rax+10h]
0x18001bc22  mov     r12, [rax+20h]
0x18001bc26  cmp     r14, [rax+18h]
0x18001bc2a  jz      short loc_18001BCAB
0x18001bc2c  test    bpl, bpl
0x18001bc2f  jnz     short loc_18001BC3B
0x18001bc31  cmp     rbx, [r14]
0x18001bc34  jnz     short loc_18001BC3B
0x18001bc36  mov     bpl, 1
0x18001bc39  jmp     short loc_18001BC58
0x18001bc3b  test    r15, r15
0x18001bc3e  jz      short loc_18001BC65
0x18001bc40  mov     r8, [r12]; void *
0x18001bc44  mov     rdx, [r14]; struct IUnknown *
0x18001bc47  mov     rcx, [rsp+58h+arg_0]; this
0x18001bc4c  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18001bc51  add     r12, 8
0x18001bc55  dec     r15
0x18001bc58  mov     rax, [rsi]
0x18001bc5b  add     r14, 8
0x18001bc5f  cmp     r14, [rax+18h]
0x18001bc63  jnz     short loc_18001BC2C
0x18001bc65  test    bpl, bpl
0x18001bc68  jz      short loc_18001BCAB
0x18001bc6a  lea     rbx, [rsi+8]
0x18001bc6e  mov     rcx, rbx; SRWLock
0x18001bc71  call    cs:__imp_AcquireSRWLockExclusive
0x18001bc78  nop     dword ptr [rax+rax+00h]
0x18001bc7d  mov     rdx, rsi
0x18001bc80  lea     rcx, [rsp+58h+arg_8]
0x18001bc85  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18001bc8a  lea     rdx, [rsp+58h+arg_0]
0x18001bc8f  mov     rcx, rsi
0x18001bc92  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18001bc97  test    rbx, rbx
0x18001bc9a  jz      short loc_18001BCAB
0x18001bc9c  mov     rcx, rbx; SRWLock
0x18001bc9f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bca6  nop     dword ptr [rax+rax+00h]
0x18001bcab  mov     rcx, [rsp+58h+arg_0]
0x18001bcb0  test    rcx, rcx
0x18001bcb3  jz      short loc_18001BCBA
0x18001bcb5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001bcba  test    rdi, rdi
0x18001bcbd  jz      short loc_18001BCCE
0x18001bcbf  mov     rcx, rdi; SRWLock
0x18001bcc2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bcc9  nop     dword ptr [rax+rax+00h]
0x18001bcce  mov     rcx, [rsp+58h+arg_8]
0x18001bcd3  test    rcx, rcx
0x18001bcd6  jz      short loc_18001BCDD
0x18001bcd8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001bcdd  xor     eax, eax
0x18001bcdf  add     rsp, 20h
0x18001bce3  pop     r15
0x18001bce5  pop     r14
0x18001bce7  pop     r12
0x18001bce9  pop     rdi
0x18001bcea  pop     rsi
0x18001bceb  pop     rbp
0x18001bcec  pop     rbx
0x18001bced  retn
```
