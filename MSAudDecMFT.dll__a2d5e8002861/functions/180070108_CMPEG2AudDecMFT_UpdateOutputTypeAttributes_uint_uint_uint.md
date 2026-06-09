# CMPEG2AudDecMFT::UpdateOutputTypeAttributes(uint,uint,uint)

- ea: `0x180070108`
- end: `0x180070367`
- name: `?UpdateOutputTypeAttributes@CMPEG2AudDecMFT@@AEAAJIII@Z`
- size: `607`
- prototype: `__int64 __fastcall(CMPEG2AudDecMFT *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18006e230`
- `0x18006e770`

## callees

- `0x180070108`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall CMPEG2AudDecMFT::UpdateOutputTypeAttributes(
        CMPEG2AudDecMFT *this,
        unsigned int a2,
        int a3,
        unsigned int a4)
{
  int v4; // esi
  _QWORD *v5; // rbx
  unsigned int v6; // edi
  unsigned int v9; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v23; // [rsp+20h] [rbp-58h] BYREF
  _DWORD v24[21]; // [rsp+24h] [rbp-54h] BYREF
  int v25; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v5 = (_QWORD *)((char *)this + 152);
  v23 = 0;
  v6 = 0;
  v25 = 0;
  v24[0] = 0;
  v9 = *((_DWORD *)this + 36);
  if ( !v9 )
  {
LABEL_6:
    v15 = 0;
    if ( a3 != 1 )
    {
      if ( v9 )
      {
        do
        {
          v20 = *(_QWORD *)(*v5 + 16LL * v15);
          v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v20 + 56LL))(
                 v20,
                 &MF_MT_AUDIO_NUM_CHANNELS,
                 &v25);
          if ( v4 < 0 )
            break;
          if ( v25 == 2 )
          {
            v21 = *(_QWORD *)(*v5 + 16LL * v15);
            v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v21 + 168LL))(
                   v21,
                   &MF_MT_AUDIO_CHANNEL_MASK,
                   a4);
            if ( v4 < 0 )
              return (unsigned int)v4;
            if ( v15 < *((_DWORD *)this + 36) )
              *(_DWORD *)(*v5 + 16LL * v15 + 8) = 1;
          }
          else if ( v15 < *((_DWORD *)this + 36) )
          {
            *(_DWORD *)(*v5 + 16LL * v15 + 8) = 0;
          }
          ++v15;
        }
        while ( v15 < *((_DWORD *)this + 36) );
      }
      return (unsigned int)v4;
    }
    if ( !v9 )
      return (unsigned int)v4;
    while ( 1 )
    {
      v16 = *(_QWORD *)(*v5 + 16LL * v15);
      v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v16 + 56LL))(
             v16,
             &MF_MT_AUDIO_NUM_CHANNELS,
             &v25);
      if ( v4 < 0 )
        return (unsigned int)v4;
      v17 = *(__int64 **)(*v5 + 16LL * v15);
      v18 = *v17;
      if ( v25 == 1 )
        break;
      if ( (*(int (__fastcall **)(__int64 *, const GUID *, _DWORD *))(v18 + 56))(v17, &MF_MT_AUDIO_CHANNEL_MASK, v24) < 0 )
      {
        v19 = 3;
        v17 = *(__int64 **)(*v5 + 16LL * v15);
        v18 = *v17;
LABEL_13:
        v4 = (*(__int64 (__fastcall **)(__int64 *, const GUID *, __int64))(v18 + 168))(
               v17,
               &MF_MT_AUDIO_CHANNEL_MASK,
               v19);
        if ( v4 < 0 )
          return (unsigned int)v4;
      }
      if ( v15 < *((_DWORD *)this + 36) )
        *(_DWORD *)(*v5 + 16LL * v15 + 8) = 1;
      if ( ++v15 >= *((_DWORD *)this + 36) )
        return (unsigned int)v4;
    }
    v19 = a4;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v12 = *(_QWORD *)(*v5 + 16LL * v6);
    v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v12 + 56LL))(
           v12,
           &MF_MT_AUDIO_BLOCK_ALIGNMENT,
           &v23);
    if ( v4 < 0 )
      break;
    v13 = *(_QWORD *)(*v5 + 16LL * v6);
    v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v13 + 168LL))(
           v13,
           &MF_MT_AUDIO_SAMPLES_PER_SECOND,
           a2);
    if ( v4 < 0 )
      break;
    v14 = *(_QWORD *)(*v5 + 16LL * v6);
    v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v14 + 168LL))(
           v14,
           &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
           a2 * v23);
    if ( v4 < 0 )
      break;
    v9 = *((_DWORD *)this + 36);
    if ( ++v6 >= v9 )
      goto LABEL_6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180070108  mov     rax, rsp
0x18007010b  push    rbx
0x18007010c  push    rbp
0x18007010d  push    rsi
0x18007010e  push    rdi
0x18007010f  push    r12
0x180070111  push    r13
0x180070113  push    r14
0x180070115  push    r15
0x180070117  sub     rsp, 38h
0x18007011b  xor     esi, esi
0x18007011d  lea     rbx, [rcx+98h]
0x180070124  mov     [rax-58h], esi
0x180070127  xor     edi, edi
0x180070129  mov     [rax+8], esi
0x18007012c  mov     r13d, r9d
0x18007012f  mov     [rax-54h], esi
0x180070132  mov     r15d, r8d
0x180070135  mov     eax, [rcx+90h]
0x18007013b  mov     r12d, edx
0x18007013e  mov     rbp, rcx
0x180070141  test    eax, eax
0x180070143  jz      loc_1800701E5
0x180070149  mov     rax, [rbx]
0x18007014c  lea     r8, [rsp+78h+var_58]
0x180070151  mov     r14d, edi
0x180070154  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18007015b  add     r14, r14
0x18007015e  mov     rcx, [rax+r14*8]
0x180070162  mov     rax, [rcx]
0x180070165  mov     rax, [rax+38h]
0x180070169  call    cs:__guard_dispatch_icall_fptr
0x18007016f  mov     esi, eax
0x180070171  test    eax, eax
0x180070173  js      loc_180070353
0x180070179  mov     rax, [rbx]
0x18007017c  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180070183  mov     r8d, r12d
0x180070186  mov     rcx, [rax+r14*8]
0x18007018a  mov     rax, [rcx]
0x18007018d  mov     rax, [rax+0A8h]
0x180070194  call    cs:__guard_dispatch_icall_fptr
0x18007019a  mov     esi, eax
0x18007019c  test    eax, eax
0x18007019e  js      loc_180070353
0x1800701a4  mov     rax, [rbx]
0x1800701a7  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x1800701ae  mov     r8d, [rsp+78h+var_58]
0x1800701b3  imul    r8d, r12d
0x1800701b7  mov     rcx, [rax+r14*8]
0x1800701bb  mov     rax, [rcx]
0x1800701be  mov     rax, [rax+0A8h]
0x1800701c5  call    cs:__guard_dispatch_icall_fptr
0x1800701cb  mov     esi, eax
0x1800701cd  test    eax, eax
0x1800701cf  js      loc_180070353
0x1800701d5  mov     eax, [rbp+90h]
0x1800701db  inc     edi
0x1800701dd  cmp     edi, eax
0x1800701df  jb      loc_180070149
0x1800701e5  mov     r12d, 1
0x1800701eb  xor     edi, edi
0x1800701ed  cmp     r15d, r12d
0x1800701f0  jnz     loc_1800702B6
0x1800701f6  test    eax, eax
0x1800701f8  jz      loc_180070353
0x1800701fe  mov     rax, [rbx]
0x180070201  lea     r8, [rsp+78h+arg_0]
0x180070209  mov     r14d, edi
0x18007020c  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x180070213  add     r14, r14
0x180070216  mov     rcx, [rax+r14*8]
0x18007021a  mov     rax, [rcx]
0x18007021d  mov     rax, [rax+38h]
0x180070221  call    cs:__guard_dispatch_icall_fptr
0x180070227  mov     esi, eax
0x180070229  test    eax, eax
0x18007022b  js      loc_180070353
0x180070231  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x180070238  mov     rax, [rbx]
0x18007023b  mov     rcx, [rax+r14*8]
0x18007023f  mov     rax, [rcx]
0x180070242  cmp     [rsp+78h+arg_0], r12d
0x18007024a  jnz     short loc_180070251
0x18007024c  mov     r8d, r13d
0x18007024f  jmp     short loc_18007027B
0x180070251  mov     rax, [rax+38h]
0x180070255  lea     r8, [rsp+78h+var_54]
0x18007025a  call    cs:__guard_dispatch_icall_fptr
0x180070260  test    eax, eax
0x180070262  jns     short loc_180070292
0x180070264  mov     rax, [rbx]
0x180070267  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x18007026e  mov     r8d, 3
0x180070274  mov     rcx, [rax+r14*8]
0x180070278  mov     rax, [rcx]
0x18007027b  mov     rax, [rax+0A8h]
0x180070282  call    cs:__guard_dispatch_icall_fptr
0x180070288  mov     esi, eax
0x18007028a  test    eax, eax
0x18007028c  js      loc_180070353
0x180070292  cmp     edi, [rbp+90h]
0x180070298  jnb     short loc_1800702A2
0x18007029a  mov     rax, [rbx]
0x18007029d  mov     [rax+r14*8+8], r12d
0x1800702a2  add     edi, r12d
0x1800702a5  cmp     edi, [rbp+90h]
0x1800702ab  jb      loc_1800701FE
0x1800702b1  jmp     loc_180070353
0x1800702b6  test    eax, eax
0x1800702b8  jz      loc_180070353
0x1800702be  mov     rax, [rbx]
0x1800702c1  lea     r8, [rsp+78h+arg_0]
0x1800702c9  mov     r14d, edi
0x1800702cc  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x1800702d3  add     r14, r14
0x1800702d6  mov     rcx, [rax+r14*8]
0x1800702da  mov     rax, [rcx]
0x1800702dd  mov     rax, [rax+38h]
0x1800702e1  call    cs:__guard_dispatch_icall_fptr
0x1800702e7  mov     esi, eax
0x1800702e9  test    eax, eax
0x1800702eb  js      short loc_180070353
0x1800702ed  cmp     [rsp+78h+arg_0], 2
0x1800702f5  jnz     short loc_180070330
0x1800702f7  mov     rax, [rbx]
0x1800702fa  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x180070301  mov     r8d, r13d
0x180070304  mov     rcx, [rax+r14*8]
0x180070308  mov     rax, [rcx]
0x18007030b  mov     rax, [rax+0A8h]
0x180070312  call    cs:__guard_dispatch_icall_fptr
0x180070318  mov     esi, eax
0x18007031a  test    eax, eax
0x18007031c  js      short loc_180070353
0x18007031e  cmp     edi, [rbp+90h]
0x180070324  jnb     short loc_180070344
0x180070326  mov     rax, [rbx]
0x180070329  mov     [rax+r14*8+8], r12d
0x18007032e  jmp     short loc_180070344
0x180070330  cmp     edi, [rbp+90h]
0x180070336  jnb     short loc_180070344
0x180070338  mov     rax, [rbx]
0x18007033b  mov     dword ptr [rax+r14*8+8], 0
0x180070344  add     edi, r12d
0x180070347  cmp     edi, [rbp+90h]
0x18007034d  jb      loc_1800702BE
0x180070353  mov     eax, esi
0x180070355  add     rsp, 38h
0x180070359  pop     r15
0x18007035b  pop     r14
0x18007035d  pop     r13
0x18007035f  pop     r12
0x180070361  pop     rdi
0x180070362  pop     rsi
0x180070363  pop     rbp
0x180070364  pop     rbx
0x180070365  retn
```
