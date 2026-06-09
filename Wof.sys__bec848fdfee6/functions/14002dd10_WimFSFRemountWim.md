# WimFSFRemountWim

- ea: `0x14002dd10`
- end: `0x14002def9`
- name: `WimFSFRemountWim`
- size: `489`
- prototype: `void __fastcall(_QWORD *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000d9cc`
- `0x140011560`
- `0x1400119c0`
- `0x14002c58c`
- `0x14002d844`
- `0x14002da7c`
- `0x14002dd10`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14002deb3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002deb3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ddfd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002de8a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ddfd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002de8a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002ddeb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002de61`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002ddeb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002de61`
- `FLTMGR!FltReleaseContext` at `0x14002de0c`
- `FLTMGR!FltReleaseContext` at `0x14002de99`
- `FLTMGR!FltReleaseContext` at `0x14002de0c`
- `FLTMGR!FltReleaseContext` at `0x14002de99`

## pseudocode

```c
void __fastcall WimFSFRemountWim(_QWORD *Parameter)
{
  __int64 v1; // r14
  __int64 v3; // r15
  int v4; // eax
  struct _FAST_MUTEX *v5; // rdi
  char *v6; // rsi
  int v7; // eax
  __int64 v8; // rcx
  PFAST_MUTEX FastMutex; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR Buffer[208]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = Parameter[1];
  v3 = (unsigned int)dword_14001A2FC;
  FastMutex = 0;
  v11 = 0;
  v10 = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v4 = WimFSFLockSystemBackingVolume(Parameter[2] + 56LL, &FastMutex);
  *((_DWORD *)Parameter + 6) = v4;
  if ( v4 >= 0 )
  {
    v5 = FastMutex;
    WofWakeFromDormant(FastMutex);
    v6 = (char *)v5 + (unsigned int)dword_14001A2FC;
    v7 = WimFSFOpenWimFile(
           *Parameter,
           v1 - v3,
           (__int64)v5,
           (struct _UNICODE_STRING *)(Parameter[2] + 56LL),
           Parameter[2] + 72LL,
           &v11,
           (PFILE_OBJECT *)&v10,
           Buffer);
    *((_DWORD *)Parameter + 6) = v7;
    if ( v7 >= 0 )
    {
      *((_DWORD *)Parameter + 6) = WimFSFAddFileOverlay(
                                     *Parameter,
                                     Parameter[1],
                                     (int)v6,
                                     (unsigned int)Parameter[2] + 72,
                                     Buffer,
                                     v11,
                                     v10,
                                     Parameter[2] + 88LL);
      ExAcquireFastMutexUnsafe(v5);
      if ( *((int *)Parameter + 6) >= 0 && (v8 = Parameter[2], (*(_DWORD *)(v8 + 40) & 8) != 0) )
        *(_QWORD *)(v8 + 32) = v6;
      else
        --*((_DWORD *)v6 + 1);
      ExReleaseFastMutexUnsafe(v5);
      FltReleaseContext(v5);
      if ( *((int *)Parameter + 6) >= 0 )
      {
        if ( ExAcquireRundownProtection(*(PEX_RUNDOWN_REF *)(Parameter[2] + 96LL)) )
        {
          _InterlockedAnd((volatile signed __int32 *)(Parameter[2] + 40LL), 0xFFFFFFFE);
          *((_DWORD *)Parameter + 6) = 0;
        }
        else
        {
          *((_DWORD *)Parameter + 6) = -1073741823;
        }
      }
    }
    else
    {
      ExAcquireFastMutexUnsafe(v5);
      --*((_DWORD *)v6 + 1);
      ExReleaseFastMutexUnsafe(v5);
      FltReleaseContext(v5);
    }
  }
}

```

## disassembly

```asm
0x14002dd10  push    rbp
0x14002dd12  push    rbx
0x14002dd13  push    rsi
0x14002dd14  push    rdi
0x14002dd15  push    r14
0x14002dd17  push    r15
0x14002dd19  lea     rbp, [rsp-48h]
0x14002dd1e  sub     rsp, 148h
0x14002dd25  mov     rax, cs:__security_cookie
0x14002dd2c  xor     rax, rsp
0x14002dd2f  mov     [rbp+70h+var_40], rax
0x14002dd33  mov     r14, [rcx+8]
0x14002dd37  mov     rbx, rcx
0x14002dd3a  mov     r15d, cs:dword_14001A2FC
0x14002dd41  lea     rcx, [rsp+170h+var_110]; void *
0x14002dd46  xor     edx, edx; Val
0x14002dd48  mov     [rsp+170h+FastMutex], 0
0x14002dd51  mov     r8d, 0D0h; Size
0x14002dd57  mov     [rsp+170h+var_120], 0
0x14002dd60  mov     [rsp+170h+var_128], 0
0x14002dd69  call    memset
0x14002dd6e  mov     rcx, [rbx+10h]
0x14002dd72  lea     rdx, [rsp+170h+FastMutex]
0x14002dd77  add     rcx, 38h ; '8'
0x14002dd7b  call    WimFSFLockSystemBackingVolume
0x14002dd80  mov     [rbx+18h], eax
0x14002dd83  test    eax, eax
0x14002dd85  js      loc_14002DEDC
0x14002dd8b  mov     rdi, [rsp+170h+FastMutex]
0x14002dd90  mov     rcx, rdi
0x14002dd93  call    WofWakeFromDormant
0x14002dd98  mov     r9, [rbx+10h]
0x14002dd9c  lea     rcx, [rsp+170h+var_110]
0x14002dda1  mov     esi, cs:dword_14001A2FC
0x14002dda7  sub     r14, r15
0x14002ddaa  mov     [rsp+170h+Buffer], rcx; Buffer
0x14002ddaf  mov     r8, rdi; int
0x14002ddb2  lea     rcx, [rsp+170h+var_128]
0x14002ddb7  mov     rdx, r14; int
0x14002ddba  mov     [rsp+170h+var_140], rcx; __int64
0x14002ddbf  lea     rax, [r9+48h]
0x14002ddc3  lea     rcx, [rsp+170h+var_120]
0x14002ddc8  add     r9, 38h ; '8'; int
0x14002ddcc  mov     [rsp+170h+var_148], rcx; __int64
0x14002ddd1  add     rsi, rdi
0x14002ddd4  mov     rcx, [rbx]; int
0x14002ddd7  mov     [rsp+170h+pbInput], rax; __int64
0x14002dddc  call    WimFSFOpenWimFile
0x14002dde1  mov     [rbx+18h], eax
0x14002dde4  test    eax, eax
0x14002dde6  jns     short loc_14002DE1D
0x14002dde8  mov     rcx, rdi; FastMutex
0x14002ddeb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002ddf2  nop     dword ptr [rax+rax+00h]
0x14002ddf7  dec     dword ptr [rsi+4]
0x14002ddfa  mov     rcx, rdi; FastMutex
0x14002ddfd  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002de04  nop     dword ptr [rax+rax+00h]
0x14002de09  mov     rcx, rdi; Context
0x14002de0c  call    cs:__imp_FltReleaseContext
0x14002de13  nop     dword ptr [rax+rax+00h]
0x14002de18  jmp     loc_14002DEDC
0x14002de1d  mov     r9, [rbx+10h]
0x14002de21  mov     r8, rsi; int
0x14002de24  mov     rdx, [rbx+8]; int
0x14002de28  mov     rcx, [rbx]; int
0x14002de2b  lea     rax, [r9+58h]
0x14002de2f  add     r9, 48h ; 'H'; int
0x14002de33  mov     [rsp+170h+Buffer], rax; __int64
0x14002de38  mov     rax, [rsp+170h+var_128]
0x14002de3d  mov     [rsp+170h+var_140], rax; __int64
0x14002de42  mov     rax, [rsp+170h+var_120]
0x14002de47  mov     [rsp+170h+var_148], rax; __int64
0x14002de4c  lea     rax, [rsp+170h+var_110]
0x14002de51  mov     [rsp+170h+pbInput], rax; pbInput
0x14002de56  call    WimFSFAddFileOverlay
0x14002de5b  mov     rcx, rdi; FastMutex
0x14002de5e  mov     [rbx+18h], eax
0x14002de61  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002de68  nop     dword ptr [rax+rax+00h]
0x14002de6d  cmp     dword ptr [rbx+18h], 0
0x14002de71  jl      short loc_14002DE84
0x14002de73  mov     rcx, [rbx+10h]
0x14002de77  mov     eax, [rcx+28h]
0x14002de7a  test    al, 8
0x14002de7c  jz      short loc_14002DE84
0x14002de7e  mov     [rcx+20h], rsi
0x14002de82  jmp     short loc_14002DE87
0x14002de84  dec     dword ptr [rsi+4]
0x14002de87  mov     rcx, rdi; FastMutex
0x14002de8a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002de91  nop     dword ptr [rax+rax+00h]
0x14002de96  mov     rcx, rdi; Context
0x14002de99  call    cs:__imp_FltReleaseContext
0x14002dea0  nop     dword ptr [rax+rax+00h]
0x14002dea5  cmp     dword ptr [rbx+18h], 0
0x14002dea9  jl      short loc_14002DEDC
0x14002deab  mov     rcx, [rbx+10h]
0x14002deaf  mov     rcx, [rcx+60h]; RunRef
0x14002deb3  call    cs:__imp_ExAcquireRundownProtection
0x14002deba  nop     dword ptr [rax+rax+00h]
0x14002debf  test    al, al
0x14002dec1  jz      short loc_14002DED5
0x14002dec3  mov     rax, [rbx+10h]
0x14002dec7  lock and dword ptr [rax+28h], 0FFFFFFFEh
0x14002decc  mov     dword ptr [rbx+18h], 0
0x14002ded3  jmp     short loc_14002DEDC
0x14002ded5  mov     dword ptr [rbx+18h], 0C0000001h
0x14002dedc  mov     rcx, [rbp+70h+var_40]
0x14002dee0  xor     rcx, rsp; StackCookie
0x14002dee3  call    __security_check_cookie
0x14002dee8  add     rsp, 148h
0x14002deef  pop     r15
0x14002def1  pop     r14
0x14002def3  pop     rdi
0x14002def4  pop     rsi
0x14002def5  pop     rbx
0x14002def6  pop     rbp
0x14002def7  retn
```
