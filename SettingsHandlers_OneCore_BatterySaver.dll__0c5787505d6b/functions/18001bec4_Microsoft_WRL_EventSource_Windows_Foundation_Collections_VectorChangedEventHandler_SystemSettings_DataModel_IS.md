# Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)

- ea: `0x18001bec4`
- end: `0x18001c02d`
- name: `?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, struct IUnknown *, void *, struct IUnknown **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b4e0`
- `0x18002b560`
- `0x18002b600`

## callees

- `0x180016c9c`
- `0x18001af38`
- `0x18001bec4`
- `0x18001c300`
- `0x180026fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001befd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bfba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001befd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bfba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bf60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bfe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bfff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bf60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bfe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bfff`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        __int64 a1,
        struct IUnknown *a2,
        void *a3,
        struct IUnknown **a4)
{
  RTL_SRWLOCK *v4; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  int v11; // esi
  _QWORD *v13; // rax
  void **v14; // r14
  struct IUnknown **i; // rsi
  Microsoft::WRL::Details::EventTargetArray *v16; // rcx
  __int64 v17[7]; // [rsp+20h] [rbp-38h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v18; // [rsp+60h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+20h] BYREF

  v4 = (RTL_SRWLOCK *)(a1 + 16);
  *a4 = 0;
  v19 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  v9 = *(_QWORD **)a1;
  v18 = 0;
  if ( v9 )
    v10 = ((__int64)(v9[3] - v9[2]) >> 3) + 1;
  else
    v10 = 1;
  v17[0] = v10;
  v11 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v18,
          v17);
  if ( v11 >= 0 )
  {
    v13 = *(_QWORD **)a1;
    if ( *(_QWORD *)a1 )
    {
      v14 = (void **)v13[4];
      for ( i = (struct IUnknown **)v13[2]; i != (struct IUnknown **)v13[3]; ++i )
      {
        Microsoft::WRL::Details::EventTargetArray::AddTail(v18, *i, *v14);
        v13 = *(_QWORD **)a1;
        ++v14;
      }
    }
    v16 = v18;
    *a4 = a2;
    Microsoft::WRL::Details::EventTargetArray::AddTail(v16, a2, a3);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v19, (char *)a1);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=((__int64 *)a1, (char *)&v18);
    if ( a1 != -8 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
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
0x18001bec4  mov     [rsp+arg_8], rbx
0x18001bec9  mov     [rsp+arg_10], rbp
0x18001bece  push    rsi
0x18001becf  push    rdi
0x18001bed0  push    r12
0x18001bed2  push    r14
0x18001bed4  push    r15
0x18001bed6  sub     rsp, 30h
0x18001beda  lea     rbx, [rcx+10h]
0x18001bede  mov     qword ptr [r9], 0
0x18001bee5  mov     rdi, rcx
0x18001bee8  mov     [rsp+58h+arg_18], 0
0x18001bef1  mov     rcx, rbx; SRWLock
0x18001bef4  mov     r15, r9
0x18001bef7  mov     r12, r8
0x18001befa  mov     rbp, rdx
0x18001befd  call    cs:__imp_AcquireSRWLockExclusive
0x18001bf03  mov     rcx, [rdi]
0x18001bf06  mov     [rsp+58h+arg_0], 0
0x18001bf0f  test    rcx, rcx
0x18001bf12  jnz     short loc_18001BF1B
0x18001bf14  mov     ecx, 1
0x18001bf19  jmp     short loc_18001BF2F
0x18001bf1b  mov     rax, [rcx+18h]
0x18001bf1f  sub     rax, [rcx+10h]
0x18001bf23  mov     ecx, 1
0x18001bf28  sar     rax, 3
0x18001bf2c  add     rcx, rax
0x18001bf2f  mov     [rsp+58h+var_38], rcx
0x18001bf34  lea     rdx, [rsp+58h+var_38]
0x18001bf39  lea     rcx, [rsp+58h+arg_0]
0x18001bf3e  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x18001bf43  mov     esi, eax
0x18001bf45  test    eax, eax
0x18001bf47  jns     short loc_18001BF6D
0x18001bf49  mov     rcx, [rsp+58h+arg_0]
0x18001bf4e  test    rcx, rcx
0x18001bf51  jz      short loc_18001BF58
0x18001bf53  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001bf58  test    rbx, rbx
0x18001bf5b  jz      short loc_18001BF66
0x18001bf5d  mov     rcx, rbx; SRWLock
0x18001bf60  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bf66  mov     eax, esi
0x18001bf68  jmp     loc_18001C016
0x18001bf6d  mov     rax, [rdi]
0x18001bf70  test    rax, rax
0x18001bf73  jz      short loc_18001BFA0
0x18001bf75  mov     r14, [rax+20h]
0x18001bf79  mov     rsi, [rax+10h]
0x18001bf7d  jmp     short loc_18001BF9A
0x18001bf7f  mov     r8, [r14]; void *
0x18001bf82  mov     rdx, [rsi]; struct IUnknown *
0x18001bf85  mov     rcx, [rsp+58h+arg_0]; this
0x18001bf8a  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18001bf8f  mov     rax, [rdi]
0x18001bf92  lea     r14, [r14+8]
0x18001bf96  add     rsi, 8
0x18001bf9a  cmp     rsi, [rax+18h]
0x18001bf9e  jnz     short loc_18001BF7F
0x18001bfa0  mov     rcx, [rsp+58h+arg_0]; this
0x18001bfa5  mov     r8, r12; void *
0x18001bfa8  mov     rdx, rbp; struct IUnknown *
0x18001bfab  mov     [r15], rbp
0x18001bfae  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18001bfb3  lea     rsi, [rdi+8]
0x18001bfb7  mov     rcx, rsi; SRWLock
0x18001bfba  call    cs:__imp_AcquireSRWLockExclusive
0x18001bfc0  mov     rdx, rdi
0x18001bfc3  lea     rcx, [rsp+58h+arg_18]
0x18001bfc8  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18001bfcd  lea     rdx, [rsp+58h+arg_0]
0x18001bfd2  mov     rcx, rdi
0x18001bfd5  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18001bfda  test    rsi, rsi
0x18001bfdd  jz      short loc_18001BFE8
0x18001bfdf  mov     rcx, rsi; SRWLock
0x18001bfe2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bfe8  mov     rcx, [rsp+58h+arg_0]
0x18001bfed  test    rcx, rcx
0x18001bff0  jz      short loc_18001BFF7
0x18001bff2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001bff7  test    rbx, rbx
0x18001bffa  jz      short loc_18001C005
0x18001bffc  mov     rcx, rbx; SRWLock
0x18001bfff  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c005  mov     rcx, [rsp+58h+arg_18]
0x18001c00a  test    rcx, rcx
0x18001c00d  jz      short loc_18001C014
0x18001c00f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001c014  xor     eax, eax
0x18001c016  mov     rbx, [rsp+58h+arg_8]
0x18001c01b  mov     rbp, [rsp+58h+arg_10]
0x18001c020  add     rsp, 30h
0x18001c024  pop     r15
0x18001c026  pop     r14
0x18001c028  pop     r12
0x18001c02a  pop     rdi
0x18001c02b  pop     rsi
0x18001c02c  retn
```
