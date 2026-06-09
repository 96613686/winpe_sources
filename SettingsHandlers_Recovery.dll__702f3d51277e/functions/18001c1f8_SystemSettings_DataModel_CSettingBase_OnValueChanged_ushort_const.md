# SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)

- ea: `0x18001c1f8`
- end: `0x18001c328`
- name: `?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z`
- size: `304`
- prototype: `void(SystemSettings::DataModel::CSettingBase *__hidden this, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013f54`
- `0x180014070`
- `0x180014820`
- `0x18001ae50`
- `0x18001afb0`
- `0x18001afe0`
- `0x18001f3a0`
- `0x18001f470`
- `0x18001faf0`

## callees

- `0x180002350`
- `0x18000f688`
- `0x18001c1f8`
- `0x18001d6bc`
- `0x18001dd30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c282`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c282`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c254`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::DataModel::CSettingBase::OnValueChanged(
        SystemSettings::DataModel::CSettingBase *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned __int64 v5; // rdx
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  RTL_SRWLOCK *v9; // rsi
  PVOID v10; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v12; // eax
  SystemSettings::DataModel::CSettingBase *v13; // [rsp+20h] [rbp-68h] BYREF
  HSTRING v14; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-48h] BYREF
  HSTRING string; // [rsp+58h] [rbp-30h] BYREF

  string = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, a3);
    __debugbreak();
  }
  if ( (int)v5 + 1 < (unsigned int)v5 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, a3);
    __debugbreak();
  }
  v6 = WindowsCreateStringReference(a2, v5, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x18001C327LL);
  }
  v9 = (RTL_SRWLOCK *)((char *)this + 128);
  v14 = string;
  v13 = this;
  v10 = 0;
  AcquireSRWLockExclusive(v9 + 1);
  Ptr = v9->Ptr;
  if ( v9->Ptr )
  {
    v10 = v9->Ptr;
    do
      v12 = Ptr[3];
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange(Ptr + 3, v12 + 1, v12) );
  }
  if ( v9 != (RTL_SRWLOCK *)-8LL )
    ReleaseSRWLockExclusive(v9 + 1);
  if ( v10 )
  {
    v15[0] = &v13;
    v15[1] = &v14;
    Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_4e612a9762e57b409773b94865ca5506_,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>(
      v15,
      v10,
      v9);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v10);
  }
}

```

## disassembly

```asm
0x18001c1f8  mov     [rsp+arg_10], rbx
0x18001c1fd  push    rbp
0x18001c1fe  push    rsi
0x18001c1ff  push    rdi
0x18001c200  sub     rsp, 70h
0x18001c204  mov     rax, cs:__security_cookie
0x18001c20b  xor     rax, rsp
0x18001c20e  mov     [rsp+88h+var_28], rax
0x18001c213  mov     r10, rdx
0x18001c216  mov     rbx, rcx
0x18001c219  xor     ebp, ebp
0x18001c21b  mov     [rsp+88h+string], rbp
0x18001c220  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c224  inc     rdx; int
0x18001c227  cmp     [r10+rdx*2], bp
0x18001c22c  jnz     short loc_18001C224
0x18001c22e  mov     eax, 0FFFFFFFFh
0x18001c233  cmp     rdx, rax
0x18001c236  ja      loc_18001C315
0x18001c23c  lea     eax, [rdx+1]
0x18001c23f  cmp     eax, edx
0x18001c241  jb      loc_18001C30A
0x18001c247  lea     r9, [rsp+88h+string]; string
0x18001c24c  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x18001c251  mov     rcx, r10; sourceString
0x18001c254  call    cs:__imp_WindowsCreateStringReference
0x18001c25a  test    eax, eax
0x18001c25c  js      loc_18001C320
0x18001c262  lea     rsi, [rbx+80h]
0x18001c269  mov     rax, [rsp+88h+string]
0x18001c26e  mov     [rsp+88h+var_60], rax
0x18001c273  mov     [rsp+88h+var_68], rbx
0x18001c278  mov     rbx, rbp
0x18001c27b  lea     rdi, [rsi+8]
0x18001c27f  mov     rcx, rdi; SRWLock
0x18001c282  call    cs:__imp_AcquireSRWLockExclusive
0x18001c288  mov     rdx, [rsi]
0x18001c28b  test    rdx, rdx
0x18001c28e  jz      short loc_18001C2AD
0x18001c290  mov     rbx, rdx
0x18001c293  mov     r8d, 7FFFFFFFh
0x18001c299  jmp     short loc_18001C2A5
0x18001c29b  lea     ecx, [rax+1]
0x18001c29e  lock cmpxchg [rdx+0Ch], ecx
0x18001c2a3  jz      short loc_18001C2AD
0x18001c2a5  mov     eax, [rdx+0Ch]
0x18001c2a8  cmp     eax, r8d
0x18001c2ab  jnz     short loc_18001C29B
0x18001c2ad  test    rdi, rdi
0x18001c2b0  jz      short loc_18001C2BB
0x18001c2b2  mov     rcx, rdi; SRWLock
0x18001c2b5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c2bb  test    rbx, rbx
0x18001c2be  jz      short loc_18001C2ED
0x18001c2c0  lea     rax, [rsp+88h+var_68]
0x18001c2c5  mov     [rsp+88h+var_58], rax
0x18001c2ca  lea     rax, [rsp+88h+var_60]
0x18001c2cf  mov     [rsp+88h+var_50], rax
0x18001c2d4  mov     r8, rsi
0x18001c2d7  mov     rdx, rbx
0x18001c2da  lea     rcx, [rsp+88h+var_58]
0x18001c2df  call    ??$InvokeDelegates@V_lambda_4e612a9762e57b409773b94865ca5506_@@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_4e612a9762e57b409773b94865ca5506_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_4e612a9762e57b409773b94865ca5506_,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_4e612a9762e57b409773b94865ca5506_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001c2e4  mov     rcx, rbx
0x18001c2e7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001c2ec  nop
0x18001c2ed  mov     rcx, [rsp+88h+var_28]
0x18001c2f2  xor     rcx, rsp; StackCookie
0x18001c2f5  call    __security_check_cookie
0x18001c2fa  mov     rbx, [rsp+88h+arg_10]
0x18001c302  add     rsp, 70h
0x18001c306  pop     rdi
0x18001c307  pop     rsi
0x18001c308  pop     rbp
0x18001c309  retn
0x18001c30a  mov     ecx, 80070216h; this
0x18001c30f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001c314  int     3; Trap to Debugger
0x18001c315  mov     ecx, 80070216h; this
0x18001c31a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001c31f  int     3; Trap to Debugger
0x18001c320  mov     ecx, eax; this
0x18001c322  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
