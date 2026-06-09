# Concurrency::details::SchedulerProxy::SchedulerProxy(Concurrency::IScheduler *,Concurrency::details::ResourceManager *,Concurrency::SchedulerPolicy const &)

- ea: `0x18031dc94`
- end: `0x18031df29`
- name: `??0SchedulerProxy@details@Concurrency@@QEAA@PEAUIScheduler@2@PEAVResourceManager@12@AEBVSchedulerPolicy@2@@Z`
- size: `661`
- prototype: `__int64 __fastcall(Concurrency::details::SchedulerProxy *__hidden this, struct Concurrency::IScheduler *, struct Concurrency::details::ResourceManager *, const struct Concurrency::SchedulerPolicy *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180310f60`

## callees

- `0x1802f0fb0`
- `0x18030c490`
- `0x18030d7a0`
- `0x18030fccc`
- `0x180312844`
- `0x180312b88`
- `0x180314060`
- `0x18031cf04`
- `0x18031d5c0`
- `0x18031dc94`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18031dd83`
- `KERNEL32!GetCurrentThread` at `0x18031dd83`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Concurrency::details::SchedulerProxy *__fastcall Concurrency::details::SchedulerProxy::SchedulerProxy(
        Concurrency::details::SchedulerProxy *this,
        struct Concurrency::IScheduler *a2,
        struct Concurrency::details::ResourceManager *a3,
        const struct Concurrency::SchedulerPolicy *a4)
{
  unsigned int v7; // ebp
  HANDLE CurrentThread; // rax
  unsigned int CoreCount; // ebx
  unsigned int v10; // ecx
  unsigned int v11; // r10d
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  unsigned int v18; // ecx
  unsigned int v19; // eax
  Concurrency::details::HillClimbing *v20; // rax
  __int64 v21; // rax
  unsigned int ProcessorNodeCount; // eax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // kr00_8

  *(_QWORD *)this = &Concurrency::details::SchedulerProxy::`vftable';
  v7 = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 3) = a3;
  Concurrency::details::_ReentrantBlockingLock::_ReentrantBlockingLock((Concurrency::details::SchedulerProxy *)((char *)this + 64));
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 42) = 0;
  *(_QWORD *)((char *)this + 204) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_DWORD *)this + 62) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 2) = a2;
  *((_DWORD *)this + 47) = Concurrency::SchedulerPolicy::GetPolicyValue(a4, 1);
  *((_DWORD *)this + 46) = Concurrency::SchedulerPolicy::GetPolicyValue(a4, 2);
  *((_DWORD *)this + 48) = Concurrency::SchedulerPolicy::GetPolicyValue(a4, 3);
  *((_DWORD *)this + 49) = Concurrency::SchedulerPolicy::GetPolicyValue(a4, 5);
  *((_DWORD *)this + 50) = Concurrency::SchedulerPolicy::GetPolicyValue(a4, 6);
  *((_BYTE *)this + 264) = (unsigned int)Concurrency::SchedulerPolicy::GetPolicyValue(a4, 8) == 1;
  if ( *((_DWORD *)this + 50) == 61440 )
  {
    CurrentThread = GetCurrentThread();
    *((_DWORD *)this + 50) = (char)Concurrency::details::platform::__GetThreadPriority(CurrentThread);
  }
  *((_DWORD *)this + 43) = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
  CoreCount = Concurrency::details::ResourceManager::GetCoreCount();
  *((_DWORD *)this + 59) = CoreCount;
  v10 = *((_DWORD *)this + 48);
  v11 = *((_DWORD *)this + 47);
  v12 = (CoreCount + v11 - 1) / CoreCount;
  if ( v10 >= v12 )
  {
    v13 = (v11 + v10 - 1) / v10;
    *((_DWORD *)this + 44) = v13;
  }
  else
  {
    *((_DWORD *)this + 48) = v12;
    *((_DWORD *)this + 44) = CoreCount;
    v13 = CoreCount;
  }
  if ( v11 % v13 )
  {
    v15 = (v13 + v11 - 1) / v13;
    *((_DWORD *)this + 48) = v15;
    v16 = v11 + v13 * (1 - v15);
    *((_DWORD *)this + 53) = v16;
    v17 = v13 - v16;
    v18 = v17 * (v15 - 1);
    v19 = *((_DWORD *)this + 46);
    if ( v18 < v19 )
      v14 = v17 + (v15 + v19 - v18 - 1) / v15;
    else
      v14 = (v15 + v19 - 2) / (v15 - 1);
  }
  else
  {
    *((_DWORD *)this + 48) = v11 / v13;
    *((_DWORD *)this + 53) = v13;
    v14 = (v11 / v13 + *((_DWORD *)this + 46) - 1) / (v11 / v13);
  }
  *((_DWORD *)this + 45) = v14;
  Concurrency::details::ResourceManager::Reference(*((Concurrency::details::ResourceManager **)this + 3));
  if ( *((_BYTE *)this + 264) )
  {
    v20 = (Concurrency::details::HillClimbing *)operator new(0x838u);
    if ( v20 )
      v21 = Concurrency::details::HillClimbing::HillClimbing(v20, *((_DWORD *)this + 43), CoreCount, this);
    else
      v21 = 0;
    *((_QWORD *)this + 13) = v21;
  }
  ProcessorNodeCount = Concurrency::GetProcessorNodeCount();
  *((_DWORD *)this + 60) = ProcessorNodeCount;
  *((_QWORD *)this + 4) = 0;
  v24 = ProcessorNodeCount;
  v23 = 4LL * ProcessorNodeCount;
  if ( !is_mul_ok(v24, 4u) )
    v23 = -1;
  *((_QWORD *)this + 5) = operator new[](v23);
  if ( *((_DWORD *)this + 60) )
  {
    do
    {
      *(_DWORD *)(*((_QWORD *)this + 5) + 4LL * v7) = v7;
      ++v7;
    }
    while ( v7 < *((_DWORD *)this + 60) );
  }
  return this;
}

```

## disassembly

```asm
0x18031dc94  mov     [rsp+arg_0], rcx
0x18031dc99  push    rbp
0x18031dc9a  push    rsi
0x18031dc9b  push    rdi
0x18031dc9c  sub     rsp, 30h
0x18031dca0  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18031dca9  mov     [rsp+48h+arg_10], rbx
0x18031dcae  mov     rdi, r9
0x18031dcb1  mov     rbx, rdx
0x18031dcb4  mov     rsi, rcx
0x18031dcb7  lea     rax, ??_7SchedulerProxy@details@Concurrency@@6B@
0x18031dcbe  mov     [rcx], rax
0x18031dcc1  xor     ebp, ebp
0x18031dcc3  mov     [rcx+8], rbp
0x18031dcc7  mov     [rcx+18h], r8
0x18031dccb  add     rcx, 40h ; '@'; this
0x18031dccf  call    ??0_ReentrantBlockingLock@details@Concurrency@@QEAA@XZ
0x18031dcd4  nop
0x18031dcd5  mov     [rsi+68h], rbp
0x18031dcd9  mov     [rsi+0A8h], ebp
0x18031dcdf  mov     [rsi+0CCh], rbp
0x18031dce6  mov     [rsi+0D8h], rbp
0x18031dced  mov     [rsi+0E0h], rbp
0x18031dcf4  mov     [rsi+0E8h], ebp
0x18031dcfa  mov     [rsi+0F8h], ebp
0x18031dd00  mov     [rsi+100h], rbp
0x18031dd07  mov     [rsi+10h], rbx
0x18031dd0b  lea     edx, [rbp+1]
0x18031dd0e  mov     rcx, rdi
0x18031dd11  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd16  mov     [rsi+0BCh], eax
0x18031dd1c  lea     edx, [rbp+2]
0x18031dd1f  mov     rcx, rdi
0x18031dd22  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd27  mov     [rsi+0B8h], eax
0x18031dd2d  lea     edx, [rbp+3]
0x18031dd30  mov     rcx, rdi
0x18031dd33  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd38  mov     [rsi+0C0h], eax
0x18031dd3e  lea     edx, [rbp+5]
0x18031dd41  mov     rcx, rdi
0x18031dd44  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd49  mov     [rsi+0C4h], eax
0x18031dd4f  lea     edx, [rbp+6]
0x18031dd52  mov     rcx, rdi
0x18031dd55  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd5a  mov     [rsi+0C8h], eax
0x18031dd60  lea     edx, [rbp+8]
0x18031dd63  mov     rcx, rdi
0x18031dd66  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z
0x18031dd6b  cmp     eax, 1
0x18031dd6e  setz    al
0x18031dd71  mov     [rsi+108h], al
0x18031dd77  cmp     dword ptr [rsi+0C8h], 0F000h
0x18031dd81  jnz     short loc_18031DD9A
0x18031dd83  call    cs:__imp_GetCurrentThread
0x18031dd89  mov     rcx, rax; hThread
0x18031dd8c  call    ?__GetThreadPriority@platform@details@Concurrency@@YAHPEAX@Z
0x18031dd91  movsx   ecx, al
0x18031dd94  mov     [rsi+0C8h], ecx
0x18031dd9a  mov     rcx, [rsi+10h]
0x18031dd9e  mov     rax, [rcx]
0x18031dda1  mov     rax, [rax]
0x18031dda4  call    cs:__guard_dispatch_icall_fptr
0x18031ddaa  mov     [rsi+0ACh], eax
0x18031ddb0  call    ?GetCoreCount@ResourceManager@details@Concurrency@@SAIXZ
0x18031ddb5  mov     ebx, eax
0x18031ddb7  mov     [rsi+0ECh], eax
0x18031ddbd  mov     ecx, [rsi+0C0h]
0x18031ddc3  mov     r10d, [rsi+0BCh]
0x18031ddca  lea     eax, [r10-1]
0x18031ddce  add     eax, ebx
0x18031ddd0  xor     edx, edx
0x18031ddd2  div     ebx
0x18031ddd4  cmp     ecx, eax
0x18031ddd6  jnb     short loc_18031DDE9
0x18031ddd8  mov     [rsi+0C0h], eax
0x18031ddde  mov     [rsi+0B0h], ebx
0x18031dde4  mov     r8d, ebx
0x18031dde7  jmp     short loc_18031DDFC
0x18031dde9  lea     eax, [rcx-1]
0x18031ddec  add     eax, r10d
0x18031ddef  xor     edx, edx
0x18031ddf1  div     ecx
0x18031ddf3  mov     r8d, eax
0x18031ddf6  mov     [rsi+0B0h], eax
0x18031ddfc  xor     edx, edx
0x18031ddfe  mov     eax, r10d
0x18031de01  div     r8d
0x18031de04  mov     r9d, eax
0x18031de07  test    edx, edx
0x18031de09  jnz     short loc_18031DE2A
0x18031de0b  mov     [rsi+0C0h], eax
0x18031de11  mov     [rsi+0D4h], r8d
0x18031de18  mov     eax, [rsi+0B8h]
0x18031de1e  dec     eax
0x18031de20  add     eax, r9d
0x18031de23  xor     edx, edx
0x18031de25  div     r9d
0x18031de28  jmp     short loc_18031DE85
0x18031de2a  lea     eax, [r10-1]
0x18031de2e  add     eax, r8d
0x18031de31  xor     edx, edx
0x18031de33  div     r8d
0x18031de36  mov     r9d, eax
0x18031de39  mov     [rsi+0C0h], eax
0x18031de3f  mov     ecx, 1
0x18031de44  sub     ecx, eax
0x18031de46  imul    ecx, r8d
0x18031de4a  add     ecx, r10d
0x18031de4d  mov     [rsi+0D4h], ecx
0x18031de53  sub     r8d, ecx
0x18031de56  lea     r10d, [rax-1]
0x18031de5a  mov     ecx, r10d
0x18031de5d  imul    ecx, r8d
0x18031de61  mov     eax, [rsi+0B8h]
0x18031de67  xor     edx, edx
0x18031de69  cmp     ecx, eax
0x18031de6b  jb      short loc_18031DE78
0x18031de6d  add     eax, 0FFFFFFFEh
0x18031de70  add     eax, r9d
0x18031de73  div     r10d
0x18031de76  jmp     short loc_18031DE85
0x18031de78  sub     eax, ecx
0x18031de7a  dec     eax
0x18031de7c  add     eax, r9d
0x18031de7f  div     r9d
0x18031de82  add     eax, r8d
0x18031de85  mov     [rsi+0B4h], eax
0x18031de8b  mov     rcx, [rsi+18h]; this
0x18031de8f  call    ?Reference@ResourceManager@details@Concurrency@@UEAAIXZ
0x18031de94  cmp     [rsi+108h], bpl
0x18031de9b  jz      short loc_18031DECE
0x18031de9d  mov     ecx, 838h; Size
0x18031dea2  call    ??2@YAPEAX_K@Z
0x18031dea7  mov     [rsp+48h+arg_8], rax
0x18031deac  test    rax, rax
0x18031deaf  jz      short loc_18031DEC7
0x18031deb1  mov     r9, rsi; struct Concurrency::details::SchedulerProxy *
0x18031deb4  mov     r8d, ebx; unsigned int
0x18031deb7  mov     edx, [rsi+0ACh]; unsigned int
0x18031debd  mov     rcx, rax; this
0x18031dec0  call    ??0HillClimbing@details@Concurrency@@QEAA@IIPEAVSchedulerProxy@12@@Z
0x18031dec5  jmp     short loc_18031DECA
0x18031dec7  mov     rax, rbp
0x18031deca  mov     [rsi+68h], rax
0x18031dece  call    ?GetProcessorNodeCount@Concurrency@@YAIXZ
0x18031ded3  mov     ecx, eax
0x18031ded5  mov     [rsi+0F0h], ecx
0x18031dedb  mov     [rsi+20h], rbp
0x18031dedf  mov     eax, 4
0x18031dee4  mul     rcx
0x18031dee7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18031deee  cmovo   rax, rcx
0x18031def2  mov     rcx, rax; unsigned __int64
0x18031def5  call    ??_U@YAPEAX_K@Z
0x18031defa  mov     [rsi+28h], rax
0x18031defe  cmp     [rsi+0F0h], ebp
0x18031df04  jbe     short loc_18031DF19
0x18031df06  mov     ecx, ebp
0x18031df08  mov     rax, [rsi+28h]
0x18031df0c  mov     [rax+rcx*4], ebp
0x18031df0f  inc     ebp
0x18031df11  cmp     ebp, [rsi+0F0h]
0x18031df17  jb      short loc_18031DF06
0x18031df19  mov     rax, rsi
0x18031df1c  mov     rbx, [rsp+48h+arg_10]
0x18031df21  add     rsp, 30h
0x18031df25  pop     rdi
0x18031df26  pop     rsi
0x18031df27  pop     rbp
0x18031df28  retn
```
