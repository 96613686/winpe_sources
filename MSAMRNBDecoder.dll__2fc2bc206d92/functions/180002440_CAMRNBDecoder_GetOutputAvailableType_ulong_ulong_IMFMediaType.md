# CAMRNBDecoder::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180002440`
- end: `0x180002642`
- name: `?GetOutputAvailableType@CAMRNBDecoder@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(CAMRNBDecoder *this, int, int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f8c`
- `0x180002440`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002627`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002493`
- `MFPlat!MFCreateMediaType` at `0x1800024ae`
- `MFPlat!MFCreateMediaType` at `0x1800024ae`

## pseudocode

```c
__int64 __fastcall CAMRNBDecoder::GetOutputAvailableType(CAMRNBDecoder *this, int a2, int a3, struct IMFMediaType **a4)
{
  HRESULT v7; // ebx
  IMFMediaType *v8; // rcx
  IMFMediaType *ppMFType; // [rsp+58h] [rbp+38h] BYREF

  ppMFType = 0;
  if ( !a4 )
    return 2147942487LL;
  if ( a2 )
    return 3222091443LL;
  if ( a3 )
    return 3222091449LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_QWORD *)this + 3) )
  {
    v7 = MFCreateMediaType(&ppMFType);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MFMediaType_Audio);
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
               ppMFType,
               &MF_MT_SUBTYPE,
               &MFAudioFormat_PCM);
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                 ppMFType,
                 &MF_MT_AUDIO_NUM_CHANNELS,
                 *((unsigned int *)this + 29));
          if ( v7 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                   *((unsigned int *)this + 28));
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                     (unsigned int)(2 * *((_DWORD *)this + 28) * *((_DWORD *)this + 29)));
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_AUDIO_BITS_PER_SAMPLE,
                       16);
                if ( v7 >= 0 )
                {
                  v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                         ppMFType,
                         &MF_MT_ALL_SAMPLES_INDEPENDENT,
                         1);
                  if ( v7 >= 0 )
                  {
                    v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                           (unsigned int)(2 * *((_DWORD *)this + 29)));
                    if ( v7 >= 0 )
                    {
                      v8 = ppMFType;
                      *a4 = ppMFType;
                      ((void (__fastcall *)(IMFMediaType *))v8->lpVtbl->AddRef)(v8);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -1072861856;
  }
  SafeRelease<IMFMediaType>(&ppMFType);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002440  mov     [rsp-18h+arg_0], rbx
0x180002445  mov     [rsp-18h+arg_8], rsi
0x18000244a  push    rbp
0x18000244b  push    rdi
0x18000244c  push    r14
0x18000244e  mov     rbp, rsp
0x180002451  sub     rsp, 20h
0x180002455  mov     [rbp+ppMFType], 0
0x18000245d  mov     r14, r9
0x180002460  mov     rdi, rcx
0x180002463  test    r9, r9
0x180002466  jnz     short loc_180002472
0x180002468  mov     eax, 80070057h
0x18000246d  jmp     loc_18000262F
0x180002472  test    edx, edx
0x180002474  jz      short loc_180002480
0x180002476  mov     eax, 0C00D36B3h
0x18000247b  jmp     loc_18000262F
0x180002480  test    r8d, r8d
0x180002483  jz      short loc_18000248F
0x180002485  mov     eax, 0C00D36B9h
0x18000248a  jmp     loc_18000262F
0x18000248f  add     rcx, 30h ; '0'; lpCriticalSection
0x180002493  call    cs:__imp_EnterCriticalSection
0x180002499  cmp     qword ptr [rdi+18h], 0
0x18000249e  jnz     short loc_1800024AA
0x1800024a0  mov     ebx, 0C00D6D60h
0x1800024a5  jmp     loc_18000261A
0x1800024aa  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800024ae  call    cs:__imp_MFCreateMediaType
0x1800024b4  mov     ebx, eax
0x1800024b6  test    eax, eax
0x1800024b8  js      loc_18000261A
0x1800024be  mov     rcx, [rbp+ppMFType]
0x1800024c2  lea     r8, MFMediaType_Audio
0x1800024c9  lea     rdx, MF_MT_MAJOR_TYPE
0x1800024d0  mov     rax, [rcx]
0x1800024d3  mov     rax, [rax+0C0h]
0x1800024da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024df  mov     ebx, eax
0x1800024e1  test    eax, eax
0x1800024e3  js      loc_18000261A
0x1800024e9  mov     rcx, [rbp+ppMFType]
0x1800024ed  lea     r8, MFAudioFormat_PCM
0x1800024f4  lea     rdx, MF_MT_SUBTYPE
0x1800024fb  mov     rax, [rcx]
0x1800024fe  mov     rax, [rax+0C0h]
0x180002505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000250a  mov     ebx, eax
0x18000250c  test    eax, eax
0x18000250e  js      loc_18000261A
0x180002514  mov     rcx, [rbp+ppMFType]
0x180002518  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18000251f  mov     r8d, [rdi+74h]
0x180002523  mov     rax, [rcx]
0x180002526  mov     rax, [rax+0A8h]
0x18000252d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002532  mov     ebx, eax
0x180002534  test    eax, eax
0x180002536  js      loc_18000261A
0x18000253c  mov     rcx, [rbp+ppMFType]
0x180002540  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180002547  mov     r8d, [rdi+70h]
0x18000254b  mov     rax, [rcx]
0x18000254e  mov     rax, [rax+0A8h]
0x180002555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255a  mov     ebx, eax
0x18000255c  test    eax, eax
0x18000255e  js      loc_18000261A
0x180002564  mov     rcx, [rbp+ppMFType]
0x180002568  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x18000256f  mov     r8d, [rdi+74h]
0x180002573  imul    r8d, [rdi+70h]
0x180002578  mov     rax, [rcx]
0x18000257b  add     r8d, r8d
0x18000257e  mov     rax, [rax+0A8h]
0x180002585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258a  mov     ebx, eax
0x18000258c  test    eax, eax
0x18000258e  js      loc_18000261A
0x180002594  mov     rcx, [rbp+ppMFType]
0x180002598  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18000259f  mov     r8d, 10h
0x1800025a5  mov     rax, [rcx]
0x1800025a8  mov     rax, [rax+0A8h]
0x1800025af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b4  mov     ebx, eax
0x1800025b6  test    eax, eax
0x1800025b8  js      short loc_18000261A
0x1800025ba  mov     rcx, [rbp+ppMFType]
0x1800025be  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x1800025c5  mov     r8d, 1
0x1800025cb  mov     rax, [rcx]
0x1800025ce  mov     rax, [rax+0A8h]
0x1800025d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025da  mov     ebx, eax
0x1800025dc  test    eax, eax
0x1800025de  js      short loc_18000261A
0x1800025e0  mov     rcx, [rbp+ppMFType]
0x1800025e4  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x1800025eb  mov     r8d, [rdi+74h]
0x1800025ef  add     r8d, r8d
0x1800025f2  mov     rax, [rcx]
0x1800025f5  mov     rax, [rax+0A8h]
0x1800025fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002601  mov     ebx, eax
0x180002603  test    eax, eax
0x180002605  js      short loc_18000261A
0x180002607  mov     rcx, [rbp+ppMFType]
0x18000260b  mov     [r14], rcx
0x18000260e  mov     rax, [rcx]
0x180002611  mov     rax, [rax+8]
0x180002615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261a  lea     rcx, [rbp+ppMFType]
0x18000261e  call    ??$SafeRelease@UIMFMediaType@@@@YAXPEAPEAUIMFMediaType@@@Z; SafeRelease<IMFMediaType>(IMFMediaType * *)
0x180002623  lea     rcx, [rdi+30h]; lpCriticalSection
0x180002627  call    cs:__imp_LeaveCriticalSection
0x18000262d  mov     eax, ebx
0x18000262f  mov     rbx, [rsp+20h+arg_0]
0x180002634  mov     rsi, [rsp+20h+arg_8]
0x180002639  add     rsp, 20h
0x18000263d  pop     r14
0x18000263f  pop     rdi
0x180002640  pop     rbp
0x180002641  retn
```
