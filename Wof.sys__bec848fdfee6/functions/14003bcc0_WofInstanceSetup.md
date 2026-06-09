# WofInstanceSetup

- ea: `0x14003bcc0`
- end: `0x14003becb`
- name: `WofInstanceSetup`
- size: `523`
- prototype: `__int64 __fastcall(__int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x14000dbd8`
- `0x14000dc88`
- `0x14000dd74`
- `0x14003bcc0`
- `0x14003e324`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd20`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd3c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bda1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bead`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd20`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd3c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bda1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bead`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003be1f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003be1f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd08`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd8c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003be98`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd08`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd8c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003be98`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003be62`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003be62`
- `FLTMGR!FltReleaseContext` at `0x14003be38`
- `FLTMGR!FltReleaseContext` at `0x14003be50`
- `FLTMGR!FltReleaseContext` at `0x14003be38`
- `FLTMGR!FltReleaseContext` at `0x14003be50`

## pseudocode

```c
__int64 __fastcall WofInstanceSetup(__int64 a1, int a2, __int64 a3, int a4)
{
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  char v12; // bl
  int v13; // edx
  PFLT_CONTEXT v14; // rdi
  unsigned int v15; // ebx
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int Context; // [rsp+20h] [rbp-50h]
  PFLT_CONTEXT v20; // [rsp+40h] [rbp-30h] BYREF
  _OWORD Parameter[2]; // [rsp+48h] [rbp-28h] BYREF

  v20 = 0;
  memset(Parameter, 0, 28);
  if ( a4 != 2 && a4 != 28 )
    return 3223060495LL;
  ExAcquireFastMutexUnsafe(&FastMutex);
  if ( byte_140018464 )
  {
    ExReleaseFastMutexUnsafe(&FastMutex);
    return 3223060495LL;
  }
  ++dword_140018468;
  ExReleaseFastMutexUnsafe(&FastMutex);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_lLD(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10);
  v11 = WofAttachVolumeContext(a1, a4, &v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    ExAcquireFastMutexUnsafe(&FastMutex);
    --dword_140018468;
    ExReleaseFastMutexUnsafe(&FastMutex);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        4,
        18,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        v12);
    }
    return 3223060495LL;
  }
  v14 = v20;
  *((_QWORD *)&Parameter[0] + 1) = v20;
  LODWORD(Parameter[0]) = 0;
  *(_QWORD *)&Parameter[1] = a1;
  DWORD2(Parameter[1]) = a2;
  if ( KeExpandKernelStackAndCalloutEx(WofInstanceSetupNewStack, Parameter, 0x6000u, 0, 0) < 0
    || SLODWORD(Parameter[0]) < 0 )
  {
    v15 = -1071906801;
    FltReleaseContext(v14);
    v16 = FltDeleteInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), 0);
    if ( v16 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(WPP_GLOBAL_Control->DeviceExtension, v17, v18, 19, Context, v16);
    ExAcquireFastMutexUnsafe(&FastMutex);
    --dword_140018468;
    ExReleaseFastMutexUnsafe(&FastMutex);
  }
  else
  {
    FltReleaseContext(v14);
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x14003bcc0  push    rbp
0x14003bcc2  push    rbx
0x14003bcc3  push    rsi
0x14003bcc4  push    rdi
0x14003bcc5  push    r13
0x14003bcc7  push    r14
0x14003bcc9  push    r15
0x14003bccb  mov     rbp, rsp
0x14003bcce  sub     rsp, 70h
0x14003bcd2  xorps   xmm0, xmm0
0x14003bcd5  mov     [rbp+var_30], 0
0x14003bcdd  xor     eax, eax
0x14003bcdf  mov     ebx, r9d
0x14003bce2  mov     edi, r8d
0x14003bce5  mov     r14d, edx
0x14003bce8  mov     rsi, rcx
0x14003bceb  movups  [rbp+Parameter], xmm0
0x14003bcef  movups  [rbp+Parameter+0Ch], xmm0
0x14003bcf3  cmp     r9d, 2
0x14003bcf7  jz      short loc_14003BCFE
0x14003bcf9  cmp     ebx, 1Ch
0x14003bcfc  jnz     short loc_14003BD2C
0x14003bcfe  lea     r15, FastMutex
0x14003bd05  mov     rcx, r15; FastMutex
0x14003bd08  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003bd0f  nop     dword ptr [rax+rax+00h]
0x14003bd14  cmp     cs:byte_140018464, 0
0x14003bd1b  mov     rcx, r15; FastMutex
0x14003bd1e  jz      short loc_14003BD36
0x14003bd20  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bd27  nop     dword ptr [rax+rax+00h]
0x14003bd2c  mov     eax, 0C01C000Fh
0x14003bd31  jmp     loc_14003BEBB
0x14003bd36  inc     cs:dword_140018468
0x14003bd3c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bd43  nop     dword ptr [rax+rax+00h]
0x14003bd48  lea     r13, WPP_RECORDER_INITIALIZED
0x14003bd4f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003bd56  jz      short loc_14003BD75
0x14003bd58  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bd5f  mov     [rsp+70h+var_38], r14d
0x14003bd64  mov     [rsp+70h+var_40], ebx
0x14003bd68  mov     [rsp+70h+var_48], edi
0x14003bd6c  mov     rcx, [rcx+40h]
0x14003bd70  call    WPP_RECORDER_SF_lLD
0x14003bd75  lea     r8, [rbp+var_30]
0x14003bd79  mov     edx, ebx
0x14003bd7b  mov     rcx, rsi
0x14003bd7e  call    WofAttachVolumeContext
0x14003bd83  mov     ebx, eax
0x14003bd85  test    eax, eax
0x14003bd87  jns     short loc_14003BDEB
0x14003bd89  mov     rcx, r15; FastMutex
0x14003bd8c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003bd93  nop     dword ptr [rax+rax+00h]
0x14003bd98  dec     cs:dword_140018468
0x14003bd9e  mov     rcx, r15; FastMutex
0x14003bda1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bda8  nop     dword ptr [rax+rax+00h]
0x14003bdad  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003bdb4  jz      loc_14003BD2C
0x14003bdba  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bdc1  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003bdc8  mov     r9d, 12h
0x14003bdce  mov     [rsp+70h+var_48], ebx
0x14003bdd2  mov     dl, 2
0x14003bdd4  mov     [rsp+70h+Context], rax
0x14003bdd9  mov     rcx, [rcx+40h]
0x14003bddd  lea     r8d, [r9-0Eh]
0x14003bde1  call    WPP_RECORDER_SF_d
0x14003bde6  jmp     loc_14003BD2C
0x14003bdeb  mov     rdi, [rbp+var_30]
0x14003bdef  lea     rdx, [rbp+Parameter]; Parameter
0x14003bdf3  xor     r9d, r9d; Wait
0x14003bdf6  mov     qword ptr [rbp+Parameter+8], rdi
0x14003bdfa  mov     r8d, 6000h; Size
0x14003be00  mov     dword ptr [rbp+Parameter], 0
0x14003be07  lea     rcx, WofInstanceSetupNewStack; Callout
0x14003be0e  mov     [rbp+var_18], rsi
0x14003be12  mov     [rbp+var_10], r14d
0x14003be16  mov     [rsp+70h+Context], 0; Context
0x14003be1f  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14003be26  nop     dword ptr [rax+rax+00h]
0x14003be2b  test    eax, eax
0x14003be2d  js      short loc_14003BE48
0x14003be2f  cmp     dword ptr [rbp+Parameter], 0
0x14003be33  jl      short loc_14003BE48
0x14003be35  mov     rcx, rdi; Context
0x14003be38  call    cs:__imp_FltReleaseContext
0x14003be3f  nop     dword ptr [rax+rax+00h]
0x14003be44  xor     ebx, ebx
0x14003be46  jmp     short loc_14003BEB9
0x14003be48  mov     rcx, rdi; Context
0x14003be4b  mov     ebx, 0C01C000Fh
0x14003be50  call    cs:__imp_FltReleaseContext
0x14003be57  nop     dword ptr [rax+rax+00h]
0x14003be5c  mov     rcx, [rsi+18h]; Instance
0x14003be60  xor     edx, edx; OldContext
0x14003be62  call    cs:__imp_FltDeleteInstanceContext
0x14003be69  nop     dword ptr [rax+rax+00h]
0x14003be6e  test    eax, eax
0x14003be70  jns     short loc_14003BE95
0x14003be72  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003be79  jz      short loc_14003BE95
0x14003be7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be82  mov     r9d, 13h
0x14003be88  mov     [rsp+70h+var_48], eax
0x14003be8c  mov     rcx, [rcx+40h]
0x14003be90  call    WPP_RECORDER_SF_D
0x14003be95  mov     rcx, r15; FastMutex
0x14003be98  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003be9f  nop     dword ptr [rax+rax+00h]
0x14003bea4  dec     cs:dword_140018468
0x14003beaa  mov     rcx, r15; FastMutex
0x14003bead  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003beb4  nop     dword ptr [rax+rax+00h]
0x14003beb9  mov     eax, ebx
0x14003bebb  add     rsp, 70h
0x14003bebf  pop     r15
0x14003bec1  pop     r14
0x14003bec3  pop     r13
0x14003bec5  pop     rdi
0x14003bec6  pop     rsi
0x14003bec7  pop     rbx
0x14003bec8  pop     rbp
0x14003bec9  retn
```
