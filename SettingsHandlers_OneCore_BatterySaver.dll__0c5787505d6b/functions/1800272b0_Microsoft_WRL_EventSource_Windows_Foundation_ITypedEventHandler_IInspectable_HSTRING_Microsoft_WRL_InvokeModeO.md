# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<IInspectable *,HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x1800272b0`
- end: `0x180027426`
- name: `?Remove@?$EventSource@U?$ITypedEventHandler@PEAUIInspectable@@PEAUHSTRING__@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `374`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180015da8`
- `0x18002c570`
- `0x18002c5b0`

## callees

- `0x180016c9c`
- `0x18001af38`
- `0x18001c300`
- `0x180026fb0`
- `0x1800272b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800272d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800273bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800272d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800273bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800273e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027400`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800273e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027400`

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
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v15, (char *)a1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=((__int64 *)a1, (char *)&v14);
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
0x1800272b0  push    rbx
0x1800272b2  push    rbp
0x1800272b3  push    rsi
0x1800272b4  push    rdi
0x1800272b5  push    r12
0x1800272b7  push    r14
0x1800272b9  push    r15
0x1800272bb  sub     rsp, 20h
0x1800272bf  lea     rdi, [rcx+10h]
0x1800272c3  mov     [rsp+58h+arg_8], 0
0x1800272cc  mov     rsi, rcx
0x1800272cf  mov     rbx, rdx
0x1800272d2  mov     rcx, rdi; SRWLock
0x1800272d5  call    cs:__imp_AcquireSRWLockExclusive
0x1800272db  mov     rax, [rsi]
0x1800272de  test    rax, rax
0x1800272e1  jnz     short loc_1800272FA
0x1800272e3  test    rdi, rdi
0x1800272e6  jz      loc_180027415
0x1800272ec  mov     rcx, rdi; SRWLock
0x1800272ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800272f5  jmp     loc_180027415
0x1800272fa  mov     rcx, [rax+10h]
0x1800272fe  mov     r15, [rax+18h]
0x180027302  sub     r15, rcx
0x180027305  mov     [rsp+58h+arg_0], 0
0x18002730e  sar     r15, 3
0x180027312  sub     r15, 1
0x180027316  mov     [rsp+58h+arg_10], r15
0x18002731b  jnz     short loc_180027329
0x18002731d  cmp     [rcx], rbx
0x180027320  setz    bpl
0x180027324  jmp     loc_1800273AF
0x180027329  lea     rdx, [rsp+58h+arg_10]
0x18002732e  lea     rcx, [rsp+58h+arg_0]
0x180027333  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x180027338  mov     ebp, eax
0x18002733a  test    eax, eax
0x18002733c  jns     short loc_180027362
0x18002733e  mov     rcx, [rsp+58h+arg_0]
0x180027343  test    rcx, rcx
0x180027346  jz      short loc_18002734D
0x180027348  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18002734d  test    rdi, rdi
0x180027350  jz      short loc_18002735B
0x180027352  mov     rcx, rdi; SRWLock
0x180027355  call    cs:__imp_ReleaseSRWLockExclusive
0x18002735b  mov     eax, ebp
0x18002735d  jmp     loc_180027417
0x180027362  mov     rax, [rsi]
0x180027365  xor     bpl, bpl
0x180027368  mov     r14, [rax+10h]
0x18002736c  mov     r12, [rax+20h]
0x180027370  cmp     r14, [rax+18h]
0x180027374  jz      short loc_1800273E9
0x180027376  test    bpl, bpl
0x180027379  jnz     short loc_180027385
0x18002737b  cmp     rbx, [r14]
0x18002737e  jnz     short loc_180027385
0x180027380  mov     bpl, 1
0x180027383  jmp     short loc_1800273A2
0x180027385  test    r15, r15
0x180027388  jz      short loc_1800273AF
0x18002738a  mov     r8, [r12]; void *
0x18002738e  mov     rdx, [r14]; struct IUnknown *
0x180027391  mov     rcx, [rsp+58h+arg_0]; this
0x180027396  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18002739b  add     r12, 8
0x18002739f  dec     r15
0x1800273a2  mov     rax, [rsi]
0x1800273a5  add     r14, 8
0x1800273a9  cmp     r14, [rax+18h]
0x1800273ad  jnz     short loc_180027376
0x1800273af  test    bpl, bpl
0x1800273b2  jz      short loc_1800273E9
0x1800273b4  lea     rbx, [rsi+8]
0x1800273b8  mov     rcx, rbx; SRWLock
0x1800273bb  call    cs:__imp_AcquireSRWLockExclusive
0x1800273c1  mov     rdx, rsi
0x1800273c4  lea     rcx, [rsp+58h+arg_8]
0x1800273c9  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x1800273ce  lea     rdx, [rsp+58h+arg_0]
0x1800273d3  mov     rcx, rsi
0x1800273d6  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x1800273db  test    rbx, rbx
0x1800273de  jz      short loc_1800273E9
0x1800273e0  mov     rcx, rbx; SRWLock
0x1800273e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800273e9  mov     rcx, [rsp+58h+arg_0]
0x1800273ee  test    rcx, rcx
0x1800273f1  jz      short loc_1800273F8
0x1800273f3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800273f8  test    rdi, rdi
0x1800273fb  jz      short loc_180027406
0x1800273fd  mov     rcx, rdi; SRWLock
0x180027400  call    cs:__imp_ReleaseSRWLockExclusive
0x180027406  mov     rcx, [rsp+58h+arg_8]
0x18002740b  test    rcx, rcx
0x18002740e  jz      short loc_180027415
0x180027410  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180027415  xor     eax, eax
0x180027417  add     rsp, 20h
0x18002741b  pop     r15
0x18002741d  pop     r14
0x18002741f  pop     r12
0x180027421  pop     rdi
0x180027422  pop     rsi
0x180027423  pop     rbp
0x180027424  pop     rbx
0x180027425  retn
```
