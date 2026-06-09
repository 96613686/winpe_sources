# WorkerTaskMigrationTarget::InitializeDecompressor(VmRepository *)

- ea: `0x1400f5608`
- end: `0x1400f5840`
- name: `?InitializeDecompressor@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct VmRepository *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140091c20`

## callees

- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x1400549dc`
- `0x14006af38`
- `0x140078c98`
- `0x1400d5c64`
- `0x1400f5608`
- `0x140132940`
- `0x140132cec`
- `0x14022163c`
- `0x140222208`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400f5747`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400f5747`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400f5814`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400f5814`

## string_xrefs

- `0x1400f565d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5695`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f572a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5768`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f57af`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f57e1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5676`: `/migration/compressor_buffer_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkerTaskMigrationTarget::InitializeDecompressor(
        WorkerTaskMigrationTarget *this,
        struct VmRepository *a2)
{
  unsigned int v4; // edi
  int v5; // eax
  const struct Vml::ExceptionTraceParameters *v6; // r8
  unsigned int i; // esi
  _QWORD *v8; // rcx
  int v9; // eax
  int v10; // eax
  unsigned int v12; // edx
  char *v13[2]; // [rsp+20h] [rbp-38h] BYREF
  void *Block[2]; // [rsp+30h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    *(_OWORD *)Block = 0;
    v4 = 0;
    v15 = 0;
    *(_OWORD *)v13 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v13, a2, 1);
    if ( SLODWORD(v13[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB09,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)LODWORD(v13[1]),
        (int)v13[0]);
    v5 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 120LL))(
           a2,
           L"/migration/compressor_buffer_size",
           &v15);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB0D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v5,
        (int)v13[0]);
    if ( !v15 || (v15 & 0xFFF) != 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xB12,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        (int)v13[0]);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402DB340);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB13,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        (int)v13[0]);
    }
    *((_QWORD *)this + 73) = v15;
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v13);
    for ( i = 0; i < 0x40; ++i )
    {
      *(_OWORD *)Block = 0;
      v8 = operator new(0x18u);
      *(_OWORD *)v8 = 0;
      v8[2] = 0;
      v9 = (*((_DWORD *)this + 120) >> 12) & 1;
      *(_DWORD *)v8 = 2;
      *((_DWORD *)v8 + 2) = v9;
      Block[0] = v8;
      v10 = XpressCompressor::Initialize(v8, 0);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB24,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v10,
          (int)v13[0]);
      Block[1] = _aligned_malloc(*((_QWORD *)this + 73), 0x1000u);
      if ( !Block[1] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB2C,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)0x8007000ELL,
          (int)v13[0]);
      GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO>::Enqueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &>((_DWORD)this + 496);
      *(_OWORD *)Block = 0;
      ++*((_DWORD *)this + 144);
    }
  }
  catch ( ... )
  {
    LODWORD(v15) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB420, v6);
    v4 = v15;
    if ( (int)v15 < 0 )
    {
      if ( Block[0] )
        XpressCompressor::`scalar deleting destructor'((XpressCompressor *)Block[0], v12);
      if ( Block[1] )
        _aligned_free(Block[1]);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400f5608  mov     r11, rsp
0x1400f560b  mov     [r11+18h], rbx
0x1400f560f  mov     [r11+20h], rsi
0x1400f5613  push    rdi
0x1400f5614  sub     rsp, 50h
0x1400f5618  mov     rax, cs:__security_cookie
0x1400f561f  xor     rax, rsp
0x1400f5622  mov     [rsp+58h+var_10], rax
0x1400f5627  mov     rsi, rdx
0x1400f562a  mov     rbx, rcx
0x1400f562d  xorps   xmm0, xmm0
0x1400f5630  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400f5635  xor     edi, edi
0x1400f5637  mov     [r11-18h], rdi
0x1400f563b  movups  xmmword ptr [rsp+58h+var_38], xmm0; int
0x1400f5640  lea     r8d, [rdi+1]
0x1400f5644  lea     rcx, [r11-38h]
0x1400f5648  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400f564d  nop
0x1400f564e  mov     r9d, dword ptr [rsp+58h+var_38+8]; char *
0x1400f5653  mov     rcx, [rsp+58h]; this
0x1400f5658  test    r9d, r9d
0x1400f565b  jns     short loc_1400F566E
0x1400f565d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f5664  mov     edx, 0B09h; void *
0x1400f5669  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f566e  mov     rax, [rsi]
0x1400f5671  lea     r8, [rsp+58h+var_18]
0x1400f5676  lea     rdx, ?VM_MIGRATION_COMPRESSOR_BUFFER_SIZE_XPATH@@3QBGB; "/migration/compressor_buffer_size"
0x1400f567d  mov     rcx, rsi
0x1400f5680  mov     rax, [rax+78h]
0x1400f5684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f5689  mov     rcx, [rsp+58h]; this
0x1400f568e  test    eax, eax
0x1400f5690  jns     short loc_1400F56A6
0x1400f5692  mov     r9d, eax; char *
0x1400f5695  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f569c  mov     edx, 0B0Dh; void *
0x1400f56a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f56a6  mov     rax, [rsp+58h+var_18]
0x1400f56ab  test    rax, rax
0x1400f56ae  jz      loc_1400F57A2
0x1400f56b4  test    rax, 0FFFh
0x1400f56ba  jnz     loc_1400F57A2
0x1400f56c0  mov     [rbx+248h], rax
0x1400f56c7  lea     rcx, [rsp+58h+var_38]; this
0x1400f56cc  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400f56d1  xor     esi, esi
0x1400f56d3  cmp     esi, 40h ; '@'
0x1400f56d6  jnb     loc_1400F57A0
0x1400f56dc  xorps   xmm0, xmm0
0x1400f56df  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400f56e4  mov     ecx, 18h; Size
0x1400f56e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400f56ee  mov     rcx, rax
0x1400f56f1  xorps   xmm0, xmm0
0x1400f56f4  xor     eax, eax
0x1400f56f6  movups  xmmword ptr [rcx], xmm0
0x1400f56f9  mov     [rcx+10h], rax
0x1400f56fd  mov     eax, [rbx+1E0h]
0x1400f5703  shr     eax, 0Ch
0x1400f5706  and     eax, 1
0x1400f5709  mov     dword ptr [rcx], 2
0x1400f570f  mov     [rcx+8], eax
0x1400f5712  mov     [rsp+58h+Block], rcx
0x1400f5717  xor     edx, edx
0x1400f5719  call    ?Initialize@XpressCompressor@@QEAAJW4XpressCompressorFlags@@@Z; XpressCompressor::Initialize(XpressCompressorFlags)
0x1400f571e  mov     rcx, [rsp+58h]; this
0x1400f5723  test    eax, eax
0x1400f5725  jns     short loc_1400F573B
0x1400f5727  mov     r9d, eax; char *
0x1400f572a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f5731  mov     edx, 0B24h; void *
0x1400f5736  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f573b  mov     edx, 1000h; Alignment
0x1400f5740  mov     rcx, [rbx+248h]; Size
0x1400f5747  call    cs:__imp__aligned_malloc
0x1400f574e  nop     dword ptr [rax+rax+00h]
0x1400f5753  mov     [rsp+58h+Block+8], rax
0x1400f5758  test    rax, rax
0x1400f575b  jnz     short loc_1400F5779
0x1400f575d  mov     rcx, [rsp+58h]; this
0x1400f5762  mov     r9d, 8007000Eh; char *
0x1400f5768  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f576f  mov     edx, 0B2Ch; void *
0x1400f5774  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f5779  lea     rcx, [rbx+1F0h]; int
0x1400f5780  lea     rdx, [rsp+58h+Block]
0x1400f5785  call    ??$Enqueue@AEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@?$GmoMigrationQueue@UDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@@QEAAXAEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@Z; GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO>::Enqueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &>(WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &)
0x1400f578a  xorps   xmm0, xmm0
0x1400f578d  movdqa  xmmword ptr [rsp+58h+Block], xmm0
0x1400f5793  inc     dword ptr [rbx+240h]
0x1400f5799  inc     esi
0x1400f579b  jmp     loc_1400F56D3
0x1400f57a0  jmp     short loc_1400F5820
0x1400f57a2  mov     rcx, [rsp+58h]; this
0x1400f57a7  mov     ebx, 8000FFFFh
0x1400f57ac  mov     r9d, ebx; char *
0x1400f57af  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f57b6  mov     edx, 0B12h; void *
0x1400f57bb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400f57c0  xor     ecx, ecx
0x1400f57c2  call    VmlIsDebugTraceEnabled
0x1400f57c7  test    eax, eax
0x1400f57c9  jz      short loc_1400F57D9
0x1400f57cb  lea     rdx, off_1402DB340; "Unexpected error.\n"
0x1400f57d2  xor     ecx, ecx
0x1400f57d4  call    VmlDebugTraceEx
0x1400f57d9  mov     rcx, [rsp+58h]; this
0x1400f57de  mov     r9d, ebx; char *
0x1400f57e1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f57e8  mov     edx, 0B13h; void *
0x1400f57ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f57f3  mov     edi, dword ptr [rsp+58h+var_18]
0x1400f57f7  test    edi, edi
0x1400f57f9  jns     short loc_1400F5820
0x1400f57fb  mov     rcx, [rsp+58h+Block]; this
0x1400f5800  test    rcx, rcx
0x1400f5803  jz      short loc_1400F580A
0x1400f5805  call    ??_GXpressCompressor@@QEAAPEAXI@Z; XpressCompressor::`scalar deleting destructor'(uint)
0x1400f580a  mov     rcx, [rsp+58h+Block+8]; Block
0x1400f580f  test    rcx, rcx
0x1400f5812  jz      short loc_1400F5820
0x1400f5814  call    cs:__imp__aligned_free
0x1400f581b  nop     dword ptr [rax+rax+00h]
0x1400f5820  mov     eax, edi
0x1400f5822  mov     rcx, [rsp+58h+var_10]
0x1400f5827  xor     rcx, rsp; StackCookie
0x1400f582a  call    __security_check_cookie
0x1400f582f  mov     rbx, [rsp+58h+arg_10]
0x1400f5834  mov     rsi, [rsp+58h+arg_18]
0x1400f5839  add     rsp, 50h
0x1400f583d  pop     rdi
0x1400f583e  retn
```
