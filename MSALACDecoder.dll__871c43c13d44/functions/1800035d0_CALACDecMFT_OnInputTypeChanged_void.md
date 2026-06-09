# CALACDecMFT::OnInputTypeChanged(void)

- ea: `0x1800035d0`
- end: `0x18000391b`
- name: `?OnInputTypeChanged@CALACDecMFT@@MEAAJXZ`
- size: `843`
- prototype: `__int64 __fastcall(ALACDecoder **this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001144`
- `0x180001150`
- `0x1800035d0`
- `0x180008848`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800036d2`
- `MFPlat!MFCreateMediaType` at `0x1800036d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CALACDecMFT::OnInputTypeChanged(ALACDecoder **this)
{
  void *v2; // rsi
  HRESULT v3; // ebx
  __int64 (__fastcall *v4)(CALACDecMFT *, _QWORD, __int64 *); // rbx
  __int64 v5; // rcx
  IMFMediaType *v6; // rcx
  ALACDecoder *v7; // rdx
  int v8; // r12d
  int v9; // r14d
  unsigned int v10; // r15d
  unsigned int v11; // r14d
  IMFMediaType *v12; // r14
  __int64 v13; // rcx
  IMFMediaType *v14; // rcx
  __int64 v15; // rcx
  unsigned int v17; // [rsp+78h] [rbp+48h] BYREF
  IMFMediaType *ppMFType; // [rsp+80h] [rbp+50h] BYREF
  __int64 v19; // [rsp+88h] [rbp+58h] BYREF

  v19 = 0;
  ppMFType = 0;
  v2 = operator new[](0x30u);
  if ( v2 )
  {
    v4 = (__int64 (__fastcall *)(CALACDecMFT *, _QWORD, __int64 *))*((_QWORD *)*this + 17);
    v5 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v3 = v4((CALACDecMFT *)this, 0, &v19);
    if ( v3 >= 0 )
    {
      v17 = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, const GUID *, void *, __int64, unsigned int *))(*(_QWORD *)v19 + 120LL))(
             v19,
             &MF_MT_USER_DATA,
             v2,
             48,
             &v17);
      if ( v3 >= 0 )
      {
        if ( (unsigned int)ALACDecoder::Init(this[22], v2, v17) )
        {
          v3 = -1072875852;
        }
        else
        {
          v6 = ppMFType;
          if ( ppMFType )
          {
            ppMFType = 0;
            ((void (__fastcall *)(IMFMediaType *))v6->lpVtbl->Release)(v6);
          }
          v3 = MFCreateMediaType(&ppMFType);
          if ( v3 >= 0 )
          {
            v7 = this[22];
            v8 = *((unsigned __int8 *)v7 + 9);
            *((_DWORD *)this + 48) = v8;
            v9 = ((*((_BYTE *)v7 + 5) & 7) != 0) + (*((unsigned __int8 *)v7 + 5) >> 3);
            *((_DWORD *)this + 49) = v9;
            *((_DWORD *)this + 50) = *(_DWORD *)v7;
            v10 = *((_DWORD *)v7 + 5);
            v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_MAJOR_TYPE,
                   &MFMediaType_Audio);
            if ( v3 >= 0 )
            {
              v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                     ppMFType,
                     &MF_MT_SUBTYPE,
                     &MFAudioFormat_PCM);
              if ( v3 >= 0 )
              {
                v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_AUDIO_NUM_CHANNELS,
                       *((unsigned int *)this + 48));
                if ( v3 >= 0 )
                {
                  v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                         ppMFType,
                         &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                         v10);
                  if ( v3 >= 0 )
                  {
                    v11 = v8 * v9;
                    v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                           v11);
                    if ( v3 >= 0 )
                    {
                      v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                             ppMFType,
                             &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                             v10 * v11);
                      if ( v3 >= 0 )
                      {
                        v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                               ppMFType,
                               &MF_MT_AUDIO_BITS_PER_SAMPLE,
                               (unsigned int)(8 * *((_DWORD *)this + 49)));
                        if ( v3 >= 0 )
                        {
                          v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                                 ppMFType,
                                 &MF_MT_AUDIO_VALID_BITS_PER_SAMPLE,
                                 *((unsigned __int8 *)this[22] + 5));
                          if ( v3 >= 0 )
                          {
                            if ( *((_DWORD *)this + 6) )
                            {
                              v12 = ppMFType;
                              v13 = *(_QWORD *)this[4];
                              if ( v13 )
                              {
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                                *(_QWORD *)this[4] = 0;
                              }
                              *(_QWORD *)this[4] = v12;
                              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this[4] + 8LL))(*(_QWORD *)this[4]);
                              *((_DWORD *)this[4] + 2) = 1;
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
        }
      }
    }
    operator delete(v2);
  }
  else
  {
    v3 = -2147024882;
  }
  v14 = ppMFType;
  if ( ppMFType )
  {
    ppMFType = 0;
    ((void (__fastcall *)(IMFMediaType *))v14->lpVtbl->Release)(v14);
  }
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800035d0  push    rbp
0x1800035d2  push    rbx
0x1800035d3  push    rsi
0x1800035d4  push    rdi
0x1800035d5  push    r12
0x1800035d7  push    r14
0x1800035d9  push    r15
0x1800035db  mov     rbp, rsp
0x1800035de  sub     rsp, 30h
0x1800035e2  mov     rdi, rcx
0x1800035e5  mov     [rbp+arg_18], 0
0x1800035ed  mov     [rbp+ppMFType], 0
0x1800035f5  mov     r14d, 30h ; '0'
0x1800035fb  mov     ecx, r14d; unsigned __int64
0x1800035fe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003603  mov     rsi, rax
0x180003606  test    rax, rax
0x180003609  jnz     short loc_180003615
0x18000360b  mov     ebx, 8007000Eh
0x180003610  jmp     loc_1800038CE
0x180003615  mov     rax, [rdi]
0x180003618  mov     rbx, [rax+88h]
0x18000361f  mov     rcx, [rbp+arg_18]
0x180003623  test    rcx, rcx
0x180003626  jz      short loc_18000363D
0x180003628  mov     [rbp+arg_18], 0
0x180003630  mov     rdx, [rcx]
0x180003633  mov     rax, [rdx+10h]
0x180003637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363c  nop
0x18000363d  lea     r8, [rbp+arg_18]
0x180003641  xor     edx, edx
0x180003643  mov     rcx, rdi
0x180003646  mov     rax, rbx
0x180003649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364e  mov     ebx, eax
0x180003650  test    eax, eax
0x180003652  js      loc_1800038C5
0x180003658  mov     [rbp+arg_8], 0
0x18000365f  mov     rcx, [rbp+arg_18]
0x180003663  mov     rax, [rcx]
0x180003666  lea     rdx, [rbp+arg_8]
0x18000366a  mov     [rsp+30h+var_10], rdx
0x18000366f  mov     r9d, r14d
0x180003672  mov     r8, rsi
0x180003675  lea     rdx, MF_MT_USER_DATA
0x18000367c  mov     rax, [rax+78h]
0x180003680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003685  mov     ebx, eax
0x180003687  test    eax, eax
0x180003689  js      loc_1800038C5
0x18000368f  mov     r8d, [rbp+arg_8]; unsigned int
0x180003693  mov     rdx, rsi; void *
0x180003696  mov     rcx, [rdi+0B0h]; this
0x18000369d  call    ?Init@ALACDecoder@@QEAAHPEAXI@Z; ALACDecoder::Init(void *,uint)
0x1800036a2  test    eax, eax
0x1800036a4  jz      short loc_1800036B0
0x1800036a6  mov     ebx, 0C00D36B4h
0x1800036ab  jmp     loc_1800038C5
0x1800036b0  mov     rcx, [rbp+ppMFType]
0x1800036b4  test    rcx, rcx
0x1800036b7  jz      short loc_1800036CE
0x1800036b9  mov     [rbp+ppMFType], 0
0x1800036c1  mov     rax, [rcx]
0x1800036c4  mov     rax, [rax+10h]
0x1800036c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036cd  nop
0x1800036ce  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800036d2  call    cs:__imp_MFCreateMediaType
0x1800036d8  mov     ebx, eax
0x1800036da  test    eax, eax
0x1800036dc  js      loc_1800038C5
0x1800036e2  mov     rdx, [rdi+0B0h]
0x1800036e9  movzx   r12d, byte ptr [rdx+9]
0x1800036ee  mov     [rdi+0C0h], r12d
0x1800036f5  movzx   ecx, byte ptr [rdx+5]
0x1800036f9  test    cl, 7
0x1800036fc  mov     eax, 0
0x180003701  setnz   al
0x180003704  shr     ecx, 3
0x180003707  lea     r14d, [rax+rcx]
0x18000370b  mov     [rdi+0C4h], r14d
0x180003712  mov     eax, [rdx]
0x180003714  mov     [rdi+0C8h], eax
0x18000371a  mov     r15d, [rdx+14h]
0x18000371e  mov     rcx, [rbp+ppMFType]
0x180003722  mov     rax, [rcx]
0x180003725  lea     r8, MFMediaType_Audio
0x18000372c  lea     rdx, MF_MT_MAJOR_TYPE
0x180003733  mov     rax, [rax+0C0h]
0x18000373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373f  mov     ebx, eax
0x180003741  test    eax, eax
0x180003743  js      loc_1800038C5
0x180003749  mov     rcx, [rbp+ppMFType]
0x18000374d  mov     rax, [rcx]
0x180003750  lea     r8, MFAudioFormat_PCM
0x180003757  lea     rdx, MF_MT_SUBTYPE
0x18000375e  mov     rax, [rax+0C0h]
0x180003765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376a  mov     ebx, eax
0x18000376c  test    eax, eax
0x18000376e  js      loc_1800038C5
0x180003774  mov     rcx, [rbp+ppMFType]
0x180003778  mov     rax, [rcx]
0x18000377b  mov     r8d, [rdi+0C0h]
0x180003782  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x180003789  mov     rax, [rax+0A8h]
0x180003790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003795  mov     ebx, eax
0x180003797  test    eax, eax
0x180003799  js      loc_1800038C5
0x18000379f  mov     rcx, [rbp+ppMFType]
0x1800037a3  mov     rax, [rcx]
0x1800037a6  mov     r8d, r15d
0x1800037a9  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x1800037b0  mov     rax, [rax+0A8h]
0x1800037b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bc  mov     ebx, eax
0x1800037be  test    eax, eax
0x1800037c0  js      loc_1800038C5
0x1800037c6  imul    r14d, r12d
0x1800037ca  mov     rcx, [rbp+ppMFType]
0x1800037ce  mov     rax, [rcx]
0x1800037d1  mov     r8d, r14d
0x1800037d4  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x1800037db  mov     rax, [rax+0A8h]
0x1800037e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e7  mov     ebx, eax
0x1800037e9  test    eax, eax
0x1800037eb  js      loc_1800038C5
0x1800037f1  mov     rcx, [rbp+ppMFType]
0x1800037f5  mov     rax, [rcx]
0x1800037f8  imul    r14d, r15d
0x1800037fc  mov     r8d, r14d
0x1800037ff  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x180003806  mov     rax, [rax+0A8h]
0x18000380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003812  mov     ebx, eax
0x180003814  test    eax, eax
0x180003816  js      loc_1800038C5
0x18000381c  mov     rcx, [rbp+ppMFType]
0x180003820  mov     rax, [rcx]
0x180003823  mov     r8d, [rdi+0C4h]
0x18000382a  shl     r8d, 3
0x18000382e  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x180003835  mov     rax, [rax+0A8h]
0x18000383c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003841  mov     ebx, eax
0x180003843  test    eax, eax
0x180003845  js      short loc_1800038C5
0x180003847  mov     rcx, [rbp+ppMFType]
0x18000384b  mov     rdx, [rcx]
0x18000384e  mov     rax, [rdi+0B0h]
0x180003855  movzx   r8d, byte ptr [rax+5]
0x18000385a  mov     rax, [rdx+0A8h]
0x180003861  lea     rdx, MF_MT_AUDIO_VALID_BITS_PER_SAMPLE
0x180003868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386d  mov     ebx, eax
0x18000386f  test    eax, eax
0x180003871  js      short loc_1800038C5
0x180003873  cmp     dword ptr [rdi+18h], 0
0x180003877  jbe     short loc_1800038C5
0x180003879  mov     r14, [rbp+ppMFType]
0x18000387d  mov     rax, [rdi+20h]
0x180003881  mov     rcx, [rax]
0x180003884  test    rcx, rcx
0x180003887  jz      short loc_1800038A0
0x180003889  mov     rax, [rcx]
0x18000388c  mov     rax, [rax+10h]
0x180003890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003895  mov     rax, [rdi+20h]
0x180003899  mov     qword ptr [rax], 0
0x1800038a0  mov     rax, [rdi+20h]
0x1800038a4  mov     [rax], r14
0x1800038a7  mov     rax, [rdi+20h]
0x1800038ab  mov     rcx, [rax]
0x1800038ae  mov     rax, [rcx]
0x1800038b1  mov     rax, [rax+8]
0x1800038b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ba  mov     rax, [rdi+20h]
0x1800038be  mov     dword ptr [rax+8], 1
0x1800038c5  mov     rcx, rsi; Block
0x1800038c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038cd  nop
0x1800038ce  mov     rcx, [rbp+ppMFType]
0x1800038d2  test    rcx, rcx
0x1800038d5  jz      short loc_1800038EC
0x1800038d7  mov     [rbp+ppMFType], 0
0x1800038df  mov     rax, [rcx]
0x1800038e2  mov     rax, [rax+10h]
0x1800038e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038eb  nop
0x1800038ec  mov     rcx, [rbp+arg_18]
0x1800038f0  test    rcx, rcx
0x1800038f3  jz      short loc_18000390A
0x1800038f5  mov     [rbp+arg_18], 0
0x1800038fd  mov     rax, [rcx]
0x180003900  mov     rax, [rax+10h]
0x180003904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003909  nop
0x18000390a  mov     eax, ebx
0x18000390c  add     rsp, 30h
0x180003910  pop     r15
0x180003912  pop     r14
0x180003914  pop     r12
0x180003916  pop     rdi
0x180003917  pop     rsi
0x180003918  pop     rbx
0x180003919  pop     rbp
0x18000391a  retn
```
