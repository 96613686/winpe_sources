# Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)

- ea: `0x1800120c0`
- end: `0x180012248`
- name: `?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `392`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fd20`
- `0x18001fda0`
- `0x18001fe40`

## callees

- `0x18000d410`
- `0x1800113a8`
- `0x1800120c0`
- `0x180012510`
- `0x18001b730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800120f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800121c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800120f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800121c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800121f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800121f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012213`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2,
        void *a3,
        struct IUnknown **a4)
{
  RTL_SRWLOCK *v4; // rbx
  _QWORD *Ptr; // rcx
  __int64 v10; // rcx
  int v11; // esi
  _QWORD *v13; // rax
  void **v14; // r14
  struct IUnknown **i; // rsi
  Microsoft::WRL::Details::EventTargetArray *v16; // rcx
  __int64 v17[7]; // [rsp+20h] [rbp-38h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v18; // [rsp+60h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+20h] BYREF

  v4 = a1 + 2;
  *a4 = 0;
  v19 = 0;
  AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1->Ptr;
  v18 = 0;
  if ( Ptr )
    v10 = ((__int64)(Ptr[3] - Ptr[2]) >> 3) + 1;
  else
    v10 = 1;
  v17[0] = v10;
  v11 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v18,
          v17);
  if ( v11 >= 0 )
  {
    v13 = a1->Ptr;
    if ( a1->Ptr )
    {
      v14 = (void **)v13[4];
      for ( i = (struct IUnknown **)v13[2]; i != (struct IUnknown **)v13[3]; ++i )
      {
        Microsoft::WRL::Details::EventTargetArray::AddTail(v18, *i, *v14);
        v13 = a1->Ptr;
        ++v14;
      }
    }
    v16 = v18;
    *a4 = a2;
    Microsoft::WRL::Details::EventTargetArray::AddTail(v16, a2, a3);
    AcquireSRWLockExclusive(a1 + 1);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v19, a1);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(a1, &v18);
    if ( a1 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(a1 + 1);
    if ( v18 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v19 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    return 0;
  }
  else
  {
    if ( v18 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x1800120c0  mov     [rsp+arg_8], rbx
0x1800120c5  mov     [rsp+arg_10], rbp
0x1800120ca  push    rsi
0x1800120cb  push    rdi
0x1800120cc  push    r12
0x1800120ce  push    r14
0x1800120d0  push    r15
0x1800120d2  sub     rsp, 30h
0x1800120d6  lea     rbx, [rcx+10h]
0x1800120da  mov     qword ptr [r9], 0
0x1800120e1  mov     rdi, rcx
0x1800120e4  mov     [rsp+58h+arg_18], 0
0x1800120ed  mov     rcx, rbx; SRWLock
0x1800120f0  mov     r15, r9
0x1800120f3  mov     r12, r8
0x1800120f6  mov     rbp, rdx
0x1800120f9  call    cs:__imp_AcquireSRWLockExclusive
0x180012100  nop     dword ptr [rax+rax+00h]
0x180012105  mov     rcx, [rdi]
0x180012108  mov     [rsp+58h+arg_0], 0
0x180012111  test    rcx, rcx
0x180012114  jnz     short loc_18001211D
0x180012116  mov     ecx, 1
0x18001211b  jmp     short loc_180012131
0x18001211d  mov     rax, [rcx+18h]
0x180012121  sub     rax, [rcx+10h]
0x180012125  mov     ecx, 1
0x18001212a  sar     rax, 3
0x18001212e  add     rcx, rax
0x180012131  mov     [rsp+58h+var_38], rcx
0x180012136  lea     rdx, [rsp+58h+var_38]
0x18001213b  lea     rcx, [rsp+58h+arg_0]
0x180012140  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x180012145  mov     esi, eax
0x180012147  test    eax, eax
0x180012149  jns     short loc_180012175
0x18001214b  mov     rcx, [rsp+58h+arg_0]
0x180012150  test    rcx, rcx
0x180012153  jz      short loc_18001215A
0x180012155  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001215a  test    rbx, rbx
0x18001215d  jz      short loc_18001216E
0x18001215f  mov     rcx, rbx; SRWLock
0x180012162  call    cs:__imp_ReleaseSRWLockExclusive
0x180012169  nop     dword ptr [rax+rax+00h]
0x18001216e  mov     eax, esi
0x180012170  jmp     loc_180012230
0x180012175  mov     rax, [rdi]
0x180012178  test    rax, rax
0x18001217b  jz      short loc_1800121A8
0x18001217d  mov     r14, [rax+20h]
0x180012181  mov     rsi, [rax+10h]
0x180012185  jmp     short loc_1800121A2
0x180012187  mov     r8, [r14]; void *
0x18001218a  mov     rdx, [rsi]; struct IUnknown *
0x18001218d  mov     rcx, [rsp+58h+arg_0]; this
0x180012192  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180012197  mov     rax, [rdi]
0x18001219a  lea     r14, [r14+8]
0x18001219e  add     rsi, 8
0x1800121a2  cmp     rsi, [rax+18h]
0x1800121a6  jnz     short loc_180012187
0x1800121a8  mov     rcx, [rsp+58h+arg_0]; this
0x1800121ad  mov     r8, r12; void *
0x1800121b0  mov     rdx, rbp; struct IUnknown *
0x1800121b3  mov     [r15], rbp
0x1800121b6  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x1800121bb  lea     rsi, [rdi+8]
0x1800121bf  mov     rcx, rsi; SRWLock
0x1800121c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800121c9  nop     dword ptr [rax+rax+00h]
0x1800121ce  mov     rdx, rdi
0x1800121d1  lea     rcx, [rsp+58h+arg_18]
0x1800121d6  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x1800121db  lea     rdx, [rsp+58h+arg_0]
0x1800121e0  mov     rcx, rdi
0x1800121e3  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x1800121e8  test    rsi, rsi
0x1800121eb  jz      short loc_1800121FC
0x1800121ed  mov     rcx, rsi; SRWLock
0x1800121f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800121f7  nop     dword ptr [rax+rax+00h]
0x1800121fc  mov     rcx, [rsp+58h+arg_0]
0x180012201  test    rcx, rcx
0x180012204  jz      short loc_18001220B
0x180012206  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001220b  test    rbx, rbx
0x18001220e  jz      short loc_18001221F
0x180012210  mov     rcx, rbx; SRWLock
0x180012213  call    cs:__imp_ReleaseSRWLockExclusive
0x18001221a  nop     dword ptr [rax+rax+00h]
0x18001221f  mov     rcx, [rsp+58h+arg_18]
0x180012224  test    rcx, rcx
0x180012227  jz      short loc_18001222E
0x180012229  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001222e  xor     eax, eax
0x180012230  mov     rbx, [rsp+58h+arg_8]
0x180012235  mov     rbp, [rsp+58h+arg_10]
0x18001223a  add     rsp, 30h
0x18001223e  pop     r15
0x180012240  pop     r14
0x180012242  pop     r12
0x180012244  pop     rdi
0x180012245  pop     rsi
0x180012246  retn
```
