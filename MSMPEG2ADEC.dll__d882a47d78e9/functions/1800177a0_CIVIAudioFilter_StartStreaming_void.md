# CIVIAudioFilter::StartStreaming(void)

- ea: `0x1800177a0`
- end: `0x180017942`
- name: `?StartStreaming@CIVIAudioFilter@@MEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800177a0`
- `0x18001cdc0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001782f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001788b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001789b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001782f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001788b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001789b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177fd`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001781f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001781f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIVIAudioFilter::StartStreaming(CIVIAudioFilter *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rcx
  int v4; // edi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( this != (CIVIAudioFilter *)-256LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
    if ( !*((_DWORD *)this + 64) )
      EventWrite(*((_QWORD *)this + 33), &MSMPEG2ADEC_PLAYBACK_START, 0, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  }
  v3 = *((_QWORD *)this + 2073);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 2073) = 0;
  }
  *((_QWORD *)this + 2076) = 0;
  *((_QWORD *)this + 2079) = 0;
  *((_DWORD *)this + 60) = 1;
  v4 = CIVIAudioCodec::ResetAudioDecoder((CIVIAudioFilter *)((char *)this + 232));
  if ( v4 < 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    LeaveCriticalSection(v2);
    return (unsigned int)v4;
  }
  *((_DWORD *)this + 3863) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 1932) = 0;
  *((_DWORD *)this + 3866) = 0;
  *((_DWORD *)this + 1610) = 0;
  *((_QWORD *)this + 2077) = 0;
  *((_QWORD *)this + 2078) = 0;
  if ( *((_DWORD *)this + 63) != 1 )
  {
    if ( *((_DWORD *)this + 63) != 4 || *((_DWORD *)this + 1544) == 6 )
      goto LABEL_15;
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 1544) != 2 )
LABEL_14:
    *((_DWORD *)this + 1610) = 1;
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x1800177a0  mov     [rsp+arg_10], rbx
0x1800177a5  mov     [rsp+arg_18], rbp
0x1800177aa  push    rsi
0x1800177ab  push    rdi
0x1800177ac  push    r14
0x1800177ae  sub     rsp, 20h
0x1800177b2  mov     rbx, rcx
0x1800177b5  lea     rsi, [rcx+88h]
0x1800177bc  mov     [rsp+38h+arg_0], rsi
0x1800177c1  mov     rcx, rsi; lpCriticalSection
0x1800177c4  call    cs:__imp_EnterCriticalSection
0x1800177cb  nop     dword ptr [rax+rax+00h]
0x1800177d0  nop
0x1800177d1  lea     rbp, [rbx+0B0h]
0x1800177d8  mov     [rsp+38h+arg_8], rbp
0x1800177dd  mov     rcx, rbp; lpCriticalSection
0x1800177e0  call    cs:__imp_EnterCriticalSection
0x1800177e7  nop     dword ptr [rax+rax+00h]
0x1800177ec  nop
0x1800177ed  lea     rdi, [rbx+100h]
0x1800177f4  test    rdi, rdi
0x1800177f7  jz      short loc_18001783B
0x1800177f9  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800177fd  call    cs:__imp_EnterCriticalSection
0x180017804  nop     dword ptr [rax+rax+00h]
0x180017809  cmp     dword ptr [rdi], 0
0x18001780c  jnz     short loc_18001782B
0x18001780e  xor     r9d, r9d; UserData
0x180017811  xor     r8d, r8d; UserDataCount
0x180017814  lea     rdx, MSMPEG2ADEC_PLAYBACK_START; EventDescriptor
0x18001781b  mov     rcx, [rdi+8]; RegHandle
0x18001781f  call    cs:__imp_EventWrite
0x180017826  nop     dword ptr [rax+rax+00h]
0x18001782b  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001782f  call    cs:__imp_LeaveCriticalSection
0x180017836  nop     dword ptr [rax+rax+00h]
0x18001783b  mov     rcx, [rbx+40C8h]
0x180017842  xor     r14d, r14d
0x180017845  test    rcx, rcx
0x180017848  jz      short loc_18001785E
0x18001784a  mov     rax, [rcx]
0x18001784d  mov     rax, [rax+10h]
0x180017851  call    cs:__guard_dispatch_icall_fptr
0x180017857  mov     [rbx+40C8h], r14
0x18001785e  mov     [rbx+40E0h], r14
0x180017865  mov     [rbx+40F8h], r14
0x18001786c  mov     dword ptr [rbx+0F0h], 1
0x180017876  lea     rcx, [rbx+0E8h]; this
0x18001787d  call    ?ResetAudioDecoder@CIVIAudioCodec@@IEAAJXZ; CIVIAudioCodec::ResetAudioDecoder(void)
0x180017882  mov     edi, eax
0x180017884  test    eax, eax
0x180017886  jns     short loc_1800178AE
0x180017888  mov     rcx, rbp; lpCriticalSection
0x18001788b  call    cs:__imp_LeaveCriticalSection
0x180017892  nop     dword ptr [rax+rax+00h]
0x180017897  nop
0x180017898  mov     rcx, rsi; lpCriticalSection
0x18001789b  call    cs:__imp_LeaveCriticalSection
0x1800178a2  nop     dword ptr [rax+rax+00h]
0x1800178a7  mov     eax, edi
0x1800178a9  jmp     loc_18001792E
0x1800178ae  mov     [rbx+3C5Ch], r14d
0x1800178b5  mov     [rbx+158h], r14
0x1800178bc  mov     [rbx+3C60h], r14
0x1800178c3  mov     [rbx+3C68h], r14d
0x1800178ca  mov     [rbx+1928h], r14d
0x1800178d1  mov     [rbx+40E8h], r14
0x1800178d8  mov     [rbx+40F0h], r14
0x1800178df  mov     ecx, [rbx+0FCh]
0x1800178e5  sub     ecx, 1
0x1800178e8  jz      short loc_1800178FA
0x1800178ea  cmp     ecx, 3
0x1800178ed  jnz     short loc_18001790D
0x1800178ef  cmp     dword ptr [rbx+1820h], 6
0x1800178f6  jnz     short loc_180017903
0x1800178f8  jmp     short loc_18001790D
0x1800178fa  cmp     dword ptr [rbx+1820h], 2
0x180017901  jz      short loc_18001790D
0x180017903  mov     dword ptr [rbx+1928h], 1
0x18001790d  mov     rcx, rbp; lpCriticalSection
0x180017910  call    cs:__imp_LeaveCriticalSection
0x180017917  nop     dword ptr [rax+rax+00h]
0x18001791c  nop
0x18001791d  mov     rcx, rsi; lpCriticalSection
0x180017920  call    cs:__imp_LeaveCriticalSection
0x180017927  nop     dword ptr [rax+rax+00h]
0x18001792c  xor     eax, eax
0x18001792e  mov     rbx, [rsp+38h+arg_10]
0x180017933  mov     rbp, [rsp+38h+arg_18]
0x180017938  add     rsp, 20h
0x18001793c  pop     r14
0x18001793e  pop     rdi
0x18001793f  pop     rsi
0x180017940  retn
```
