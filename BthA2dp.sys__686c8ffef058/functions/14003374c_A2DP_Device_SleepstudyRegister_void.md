# A2DP_Device::SleepstudyRegister(void)

- ea: `0x14003374c`
- end: `0x1400338d7`
- name: `?SleepstudyRegister@A2DP_Device@@AEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400320a8`

## callees

- `0x1400205f4`
- `0x14002efec`
- `0x14003332c`
- `0x14003374c`
- `0x14005c7d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003389e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003389e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003387e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003387e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x140033866`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x140033866`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14003381b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14003381b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x1400337d6`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x1400337d6`

## pseudocode

```c
__int64 __fastcall A2DP_Device::SleepstudyRegister(A2DP_Device *this)
{
  int PdoFriendlyName; // ebx
  KIRQL v3; // al
  __int64 v5; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING v6; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v7[8]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v8[8]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v9; // [rsp+58h] [rbp-21h]
  _BYTE v10[16]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v11; // [rsp+70h] [rbp-9h] BYREF
  GUID v12; // [rsp+80h] [rbp+7h] BYREF
  __int128 v13; // [rsp+90h] [rbp+17h] BYREF

  v13 = 0;
  UnicodeString::UnicodeString((UnicodeString *)v8, 0x100u);
  if ( v9 )
  {
    UnicodeString::UnicodeString((UnicodeString *)&v6, 0x200u);
    if ( v6.Buffer )
    {
      if ( g_SleepstudyLibraryHandle )
      {
        PdoFriendlyName = SleepstudyHelper_GetPdoFriendlyName(*(_QWORD *)(*((_QWORD *)this + 46) + 32LL), v8);
        if ( PdoFriendlyName >= 0 )
        {
          PdoFriendlyName = RtlUnicodeStringPrintf(&v6, L"%wZ (A2DP Streaming)", v8);
          if ( PdoFriendlyName >= 0 )
          {
            PdoFriendlyName = SleepstudyHelper_GenerateGuid(0, *(_QWORD *)(*((_QWORD *)this + 46) + 32LL), &v13);
            if ( PdoFriendlyName >= 0 )
            {
              v5 = 0;
              v11 = v13;
              v12 = GUID_SLEEPSTUDY_BLUETOOTH_CONTROLLER_FDO;
              PdoFriendlyName = SleepstudyHelper_RegisterComponentEx(g_SleepstudyLibraryHandle, &v12, &v11, &v6, &v5);
              v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
              if ( PdoFriendlyName >= 0 )
                *((_QWORD *)this + 410) = v5;
              KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v3);
            }
          }
        }
      }
      else
      {
        PdoFriendlyName = -1073741811;
      }
    }
    else
    {
      PdoFriendlyName = -1073741670;
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(v7);
  }
  else
  {
    PdoFriendlyName = -1073741670;
  }
  utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(v10);
  return (unsigned int)PdoFriendlyName;
}

```

## disassembly

```asm
0x14003374c  push    rbp
0x14003374e  push    rbx
0x14003374f  push    rsi
0x140033750  push    rdi
0x140033751  lea     rbp, [rsp-3Fh]
0x140033756  sub     rsp, 0B8h
0x14003375d  mov     rax, cs:__security_cookie
0x140033764  xor     rax, rsp
0x140033767  mov     [rbp+57h+var_30], rax
0x14003376b  mov     rdi, rcx
0x14003376e  xorps   xmm0, xmm0
0x140033771  lea     rcx, [rbp+57h+var_80]; this
0x140033775  mov     edx, 100h; unsigned __int16
0x14003377a  movups  [rbp+57h+var_40], xmm0
0x14003377e  call    ??0UnicodeString@@QEAA@G@Z; UnicodeString::UnicodeString(ushort)
0x140033783  cmp     [rbp+57h+var_78], 0
0x140033788  jnz     short loc_140033794
0x14003378a  mov     ebx, 0C000009Ah
0x14003378f  jmp     loc_1400338B3
0x140033794  mov     edx, 200h; unsigned __int16
0x140033799  lea     rcx, [rbp+57h+var_98]; this
0x14003379d  call    ??0UnicodeString@@QEAA@G@Z; UnicodeString::UnicodeString(ushort)
0x1400337a2  cmp     [rbp+57h+var_98.Buffer], 0
0x1400337a7  jnz     short loc_1400337B3
0x1400337a9  mov     ebx, 0C000009Ah
0x1400337ae  jmp     loc_1400338AA
0x1400337b3  cmp     cs:?g_SleepstudyLibraryHandle@@3PEAUSS_LIBRARY__@@EA, 0; SS_LIBRARY__ * g_SleepstudyLibraryHandle
0x1400337bb  jnz     short loc_1400337C7
0x1400337bd  mov     ebx, 0C000000Dh
0x1400337c2  jmp     loc_1400338AA
0x1400337c7  mov     rcx, [rdi+170h]
0x1400337ce  lea     rdx, [rbp+57h+var_80]
0x1400337d2  mov     rcx, [rcx+20h]
0x1400337d6  call    cs:__imp_SleepstudyHelper_GetPdoFriendlyName
0x1400337dd  nop     dword ptr [rax+rax+00h]
0x1400337e2  mov     ebx, eax
0x1400337e4  test    eax, eax
0x1400337e6  js      loc_1400338AA
0x1400337ec  lea     r8, [rbp+57h+var_80]
0x1400337f0  lea     rdx, aWzA2dpStreamin; "%wZ (A2DP Streaming)"
0x1400337f7  lea     rcx, [rbp+57h+var_98]; struct _UNICODE_STRING *
0x1400337fb  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x140033800  mov     ebx, eax
0x140033802  test    eax, eax
0x140033804  js      loc_1400338AA
0x14003380a  mov     rdx, [rdi+170h]
0x140033811  lea     r8, [rbp+57h+var_40]
0x140033815  xor     ecx, ecx
0x140033817  mov     rdx, [rdx+20h]
0x14003381b  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x140033822  nop     dword ptr [rax+rax+00h]
0x140033827  mov     ebx, eax
0x140033829  test    eax, eax
0x14003382b  js      short loc_1400338AA
0x14003382d  movups  xmm1, xmmword ptr cs:GUID_SLEEPSTUDY_BLUETOOTH_CONTROLLER_FDO.Data1
0x140033834  lea     rax, [rbp+57h+var_A0]
0x140033838  mov     rcx, cs:?g_SleepstudyLibraryHandle@@3PEAUSS_LIBRARY__@@EA; SS_LIBRARY__ * g_SleepstudyLibraryHandle
0x14003383f  movaps  xmm0, [rbp+57h+var_40]
0x140033843  lea     r9, [rbp+57h+var_98]
0x140033847  lea     r8, [rbp+57h+var_60]
0x14003384b  mov     [rbp+57h+var_A0], 0
0x140033853  lea     rdx, [rbp+57h+var_50]
0x140033857  movdqa  [rbp+57h+var_60], xmm0
0x14003385c  movdqu  [rbp+57h+var_50], xmm1
0x140033861  mov     [rsp+0D0h+var_B0], rax
0x140033866  call    cs:__imp_SleepstudyHelper_RegisterComponentEx
0x14003386d  nop     dword ptr [rax+rax+00h]
0x140033872  lea     rsi, [rdi+2B8h]
0x140033879  mov     ebx, eax
0x14003387b  mov     rcx, rsi; SpinLock
0x14003387e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140033885  nop     dword ptr [rax+rax+00h]
0x14003388a  test    ebx, ebx
0x14003388c  js      short loc_140033899
0x14003388e  mov     rdx, [rbp+57h+var_A0]
0x140033892  mov     [rdi+0CD0h], rdx
0x140033899  mov     dl, al; NewIrql
0x14003389b  mov     rcx, rsi; SpinLock
0x14003389e  call    cs:__imp_KeReleaseSpinLock
0x1400338a5  nop     dword ptr [rax+rax+00h]
0x1400338aa  lea     rcx, [rbp+57h+var_88]
0x1400338ae  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x1400338b3  lea     rcx, [rbp+57h+var_70]
0x1400338b7  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x1400338bc  mov     eax, ebx
0x1400338be  mov     rcx, [rbp+57h+var_30]
0x1400338c2  xor     rcx, rsp; StackCookie
0x1400338c5  call    __security_check_cookie
0x1400338ca  add     rsp, 0B8h
0x1400338d1  pop     rdi
0x1400338d2  pop     rsi
0x1400338d3  pop     rbx
0x1400338d4  pop     rbp
0x1400338d5  retn
```
