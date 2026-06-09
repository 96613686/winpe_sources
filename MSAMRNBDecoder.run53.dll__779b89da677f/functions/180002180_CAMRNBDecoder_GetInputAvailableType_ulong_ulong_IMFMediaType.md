# CAMRNBDecoder::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180002180`
- end: `0x1800022f9`
- name: `?GetInputAvailableType@CAMRNBDecoder@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CAMRNBDecoder *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f8c`
- `0x180002180`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021cc`
- `MFPlat!MFCreateMediaType` at `0x1800021d7`
- `MFPlat!MFCreateMediaType` at `0x1800021d7`

## pseudocode

```c
__int64 __fastcall CAMRNBDecoder::GetInputAvailableType(
        CAMRNBDecoder *this,
        int a2,
        unsigned int a3,
        struct IMFMediaType **a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  HRESULT v8; // ebx
  const GUID *v9; // r8
  IMFMediaType *v10; // rcx
  IMFMediaType *ppMFType; // [rsp+68h] [rbp+20h] BYREF

  ppMFType = 0;
  if ( !a4 )
    return 2147942487LL;
  if ( a2 )
    return 3222091443LL;
  if ( a3 > 1 )
    return 3222091449LL;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v8 = MFCreateMediaType(&ppMFType);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
           ppMFType,
           &MF_MT_MAJOR_TYPE,
           &MFMediaType_Audio);
    if ( v8 >= 0 )
    {
      if ( a3 )
        v9 = (const GUID *)&MFMPEG4Format_SAMR;
      else
        v9 = &MFAudioFormat_AMR_NB;
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             v9);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
               ppMFType,
               &MF_MT_AUDIO_NUM_CHANNELS,
               1);
        if ( v8 >= 0 )
        {
          v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                 ppMFType,
                 &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                 8000);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_AUDIO_BITS_PER_SAMPLE,
                   16);
            if ( v8 >= 0 )
            {
              v10 = ppMFType;
              *a4 = ppMFType;
              ((void (__fastcall *)(IMFMediaType *))v10->lpVtbl->AddRef)(v10);
            }
          }
        }
      }
    }
  }
  SafeRelease<IMFMediaType>(&ppMFType);
  LeaveCriticalSection(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002180  push    rbx
0x180002182  push    rsi
0x180002183  push    rdi
0x180002184  push    r14
0x180002186  sub     rsp, 28h
0x18000218a  mov     [rsp+48h+ppMFType], 0
0x180002193  mov     r14, r9
0x180002196  mov     edi, r8d
0x180002199  test    r9, r9
0x18000219c  jnz     short loc_1800021A8
0x18000219e  mov     eax, 80070057h
0x1800021a3  jmp     loc_1800022EF
0x1800021a8  test    edx, edx
0x1800021aa  jz      short loc_1800021B6
0x1800021ac  mov     eax, 0C00D36B3h
0x1800021b1  jmp     loc_1800022EF
0x1800021b6  cmp     edi, 1
0x1800021b9  jbe     short loc_1800021C5
0x1800021bb  mov     eax, 0C00D36B9h
0x1800021c0  jmp     loc_1800022EF
0x1800021c5  lea     rsi, [rcx+30h]
0x1800021c9  mov     rcx, rsi; lpCriticalSection
0x1800021cc  call    cs:__imp_EnterCriticalSection
0x1800021d2  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x1800021d7  call    cs:__imp_MFCreateMediaType
0x1800021dd  mov     ebx, eax
0x1800021df  test    eax, eax
0x1800021e1  js      loc_1800022DA
0x1800021e7  mov     rcx, [rsp+48h+ppMFType]
0x1800021ec  lea     r8, MFMediaType_Audio
0x1800021f3  lea     rdx, MF_MT_MAJOR_TYPE
0x1800021fa  mov     rax, [rcx]
0x1800021fd  mov     rax, [rax+0C0h]
0x180002204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002209  mov     ebx, eax
0x18000220b  test    eax, eax
0x18000220d  js      loc_1800022DA
0x180002213  test    edi, edi
0x180002215  jnz     short loc_180002220
0x180002217  lea     r8, MFAudioFormat_AMR_NB
0x18000221e  jmp     short loc_18000222C
0x180002220  cmp     edi, 1
0x180002223  jnz     short loc_180002251
0x180002225  lea     r8, MFMPEG4Format_SAMR
0x18000222c  mov     rcx, [rsp+48h+ppMFType]
0x180002231  lea     rdx, MF_MT_SUBTYPE
0x180002238  mov     rax, [rcx]
0x18000223b  mov     rax, [rax+0C0h]
0x180002242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002247  mov     ebx, eax
0x180002249  test    eax, eax
0x18000224b  js      loc_1800022DA
0x180002251  mov     rcx, [rsp+48h+ppMFType]
0x180002256  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18000225d  mov     r8d, 1
0x180002263  mov     rax, [rcx]
0x180002266  mov     rax, [rax+0A8h]
0x18000226d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002272  mov     ebx, eax
0x180002274  test    eax, eax
0x180002276  js      short loc_1800022DA
0x180002278  mov     rcx, [rsp+48h+ppMFType]
0x18000227d  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180002284  mov     r8d, 1F40h
0x18000228a  mov     rax, [rcx]
0x18000228d  mov     rax, [rax+0A8h]
0x180002294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002299  mov     ebx, eax
0x18000229b  test    eax, eax
0x18000229d  js      short loc_1800022DA
0x18000229f  mov     rcx, [rsp+48h+ppMFType]
0x1800022a4  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x1800022ab  mov     r8d, 10h
0x1800022b1  mov     rax, [rcx]
0x1800022b4  mov     rax, [rax+0A8h]
0x1800022bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c0  mov     ebx, eax
0x1800022c2  test    eax, eax
0x1800022c4  js      short loc_1800022DA
0x1800022c6  mov     rcx, [rsp+48h+ppMFType]
0x1800022cb  mov     [r14], rcx
0x1800022ce  mov     rax, [rcx]
0x1800022d1  mov     rax, [rax+8]
0x1800022d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022da  lea     rcx, [rsp+48h+ppMFType]
0x1800022df  call    ??$SafeRelease@UIMFMediaType@@@@YAXPEAPEAUIMFMediaType@@@Z; SafeRelease<IMFMediaType>(IMFMediaType * *)
0x1800022e4  mov     rcx, rsi; lpCriticalSection
0x1800022e7  call    cs:__imp_LeaveCriticalSection
0x1800022ed  mov     eax, ebx
0x1800022ef  add     rsp, 28h
0x1800022f3  pop     r14
0x1800022f5  pop     rdi
0x1800022f6  pop     rsi
0x1800022f7  pop     rbx
0x1800022f8  retn
```
