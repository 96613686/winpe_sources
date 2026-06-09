# CIVIAudioFilter::EndOfStream(void)

- ea: `0x18000dcc0`
- end: `0x18000de18`
- name: `?EndOfStream@CIVIAudioFilter@@MEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000dcc0`
- `0x18001a6b0`
- `0x18001cdc0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dce4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dce4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIVIAudioFilter::EndOfStream(CIVIAudioFilter *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rcx
  int v4; // ebp
  int v5; // esi
  __int64 v6; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v8; // rcx
  void (__fastcall *v9)(__int64); // rax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( *((_DWORD *)this + 1613) == 9 && *((_QWORD *)this + 830) && !*((_DWORD *)this + 1770) )
  {
    *((_QWORD *)this + 832) = 0;
    *((_QWORD *)this + 833) = 0;
    CIVIAudioCodec::DecodeAACFrame((struct _RTL_CRITICAL_SECTION *)((char *)this + 232), 0, 0);
  }
  v3 = *((_QWORD *)this + 2073);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 2073) = 0;
  }
  *((_QWORD *)this + 2076) = 0;
  *((_QWORD *)this + 2079) = 0;
  *((_DWORD *)this + 1542) = 0;
  v4 = CIVIAudioCodec::ResetAudioDecoder((CIVIAudioFilter *)((char *)this + 232));
  v5 = 0;
  v6 = *((_QWORD *)this + 28);
  if ( v6 )
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 152LL))(v6);
  if ( v5 >= 0 )
    v5 = v4;
  CurrentThreadId = GetCurrentThreadId();
  v8 = *((_QWORD *)this + 2226);
  if ( v8 && *((_DWORD *)this + 4450) == CurrentThreadId )
  {
    if ( *((_QWORD *)this + 2156) )
    {
      if ( *((_QWORD *)this + 2157) )
      {
        v9 = (void (__fastcall *)(__int64))*((_QWORD *)this + 2158);
        if ( v9 )
        {
          if ( *((_QWORD *)this + 2159) )
            v9(v8);
        }
      }
    }
    *((_QWORD *)this + 2226) = 0;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000dcc0  mov     [rsp+arg_8], rbx
0x18000dcc5  mov     [rsp+arg_10], rbp
0x18000dcca  push    rsi
0x18000dccb  push    rdi
0x18000dccc  push    r14
0x18000dcce  sub     rsp, 30h
0x18000dcd2  mov     rbx, rcx
0x18000dcd5  lea     rdi, [rcx+0B0h]
0x18000dcdc  mov     [rsp+48h+arg_0], rdi
0x18000dce1  mov     rcx, rdi; lpCriticalSection
0x18000dce4  call    cs:__imp_EnterCriticalSection
0x18000dceb  nop     dword ptr [rax+rax+00h]
0x18000dcf0  nop
0x18000dcf1  xor     r14d, r14d
0x18000dcf4  cmp     dword ptr [rbx+1934h], 9
0x18000dcfb  jnz     short loc_18000DD36
0x18000dcfd  cmp     [rbx+19F0h], r14
0x18000dd04  jz      short loc_18000DD36
0x18000dd06  lea     rcx, [rbx+0E8h]; this
0x18000dd0d  cmp     [rcx+1AC0h], r14d
0x18000dd14  jnz     short loc_18000DD36
0x18000dd16  mov     [rcx+1918h], r14
0x18000dd1d  mov     [rcx+1920h], r14
0x18000dd24  mov     [rsp+48h+var_28], r14; unsigned __int16 *
0x18000dd29  xor     r9d, r9d; unsigned int
0x18000dd2c  xor     r8d, r8d; int
0x18000dd2f  xor     edx, edx; unsigned __int8 *
0x18000dd31  call    ?DecodeAACFrame@CIVIAudioCodec@@IEAAJPEAEJKPEAG@Z; CIVIAudioCodec::DecodeAACFrame(uchar *,long,ulong,ushort *)
0x18000dd36  mov     rcx, [rbx+40C8h]
0x18000dd3d  test    rcx, rcx
0x18000dd40  jz      short loc_18000DD56
0x18000dd42  mov     rax, [rcx]
0x18000dd45  mov     rax, [rax+10h]
0x18000dd49  call    cs:__guard_dispatch_icall_fptr
0x18000dd4f  mov     [rbx+40C8h], r14
0x18000dd56  mov     [rbx+40E0h], r14
0x18000dd5d  mov     [rbx+40F8h], r14
0x18000dd64  mov     [rbx+1818h], r14d
0x18000dd6b  lea     rcx, [rbx+0E8h]; this
0x18000dd72  call    ?ResetAudioDecoder@CIVIAudioCodec@@IEAAJXZ; CIVIAudioCodec::ResetAudioDecoder(void)
0x18000dd77  mov     ebp, eax
0x18000dd79  mov     esi, r14d
0x18000dd7c  mov     rcx, [rbx+0E0h]
0x18000dd83  test    rcx, rcx
0x18000dd86  jz      short loc_18000DD9A
0x18000dd88  mov     rdx, [rcx]
0x18000dd8b  mov     rax, [rdx+98h]
0x18000dd92  call    cs:__guard_dispatch_icall_fptr
0x18000dd98  mov     esi, eax
0x18000dd9a  test    esi, esi
0x18000dd9c  cmovns  esi, ebp
0x18000dd9f  call    cs:__imp_GetCurrentThreadId
0x18000dda6  nop     dword ptr [rax+rax+00h]
0x18000ddab  mov     rcx, [rbx+4590h]
0x18000ddb2  test    rcx, rcx
0x18000ddb5  jz      short loc_18000DDF3
0x18000ddb7  cmp     [rbx+4588h], eax
0x18000ddbd  jnz     short loc_18000DDF3
0x18000ddbf  cmp     [rbx+4360h], r14
0x18000ddc6  jz      short loc_18000DDEC
0x18000ddc8  cmp     [rbx+4368h], r14
0x18000ddcf  jz      short loc_18000DDEC
0x18000ddd1  mov     rax, [rbx+4370h]
0x18000ddd8  test    rax, rax
0x18000dddb  jz      short loc_18000DDEC
0x18000dddd  cmp     [rbx+4378h], r14
0x18000dde4  jz      short loc_18000DDEC
0x18000dde6  call    cs:__guard_dispatch_icall_fptr
0x18000ddec  mov     [rbx+4590h], r14
0x18000ddf3  mov     rcx, rdi; lpCriticalSection
0x18000ddf6  call    cs:__imp_LeaveCriticalSection
0x18000ddfd  nop     dword ptr [rax+rax+00h]
0x18000de02  mov     eax, esi
0x18000de04  mov     rbx, [rsp+48h+arg_8]
0x18000de09  mov     rbp, [rsp+48h+arg_10]
0x18000de0e  add     rsp, 30h
0x18000de12  pop     r14
0x18000de14  pop     rdi
0x18000de15  pop     rsi
0x18000de16  retn
```
