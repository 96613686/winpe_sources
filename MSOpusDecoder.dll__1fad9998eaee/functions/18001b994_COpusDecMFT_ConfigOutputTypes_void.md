# COpusDecMFT::ConfigOutputTypes(void)

- ea: `0x18001b994`
- end: `0x18001bc71`
- name: `?ConfigOutputTypes@COpusDecMFT@@AEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(COpusDecMFT *this, __int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001dda0`

## callees

- `0x1800010c8`
- `0x18001b994`
- `0x18001ed1c`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001b9fd`
- `MFPlat!MFCreateMediaType` at `0x18001b9fd`

## pseudocode

```c
__int64 __fastcall COpusDecMFT::ConfigOutputTypes(COpusDecMFT *this, __int64 a2, int a3, int a4)
{
  HRESULT inited; // ebx
  int v6; // eax
  __int64 v7; // r8
  IMFMediaType *v8; // rsi
  __int64 v9; // rcx
  int v11; // [rsp+58h] [rbp+28h] BYREF
  IMFMediaType *ppMFType; // [rsp+60h] [rbp+30h] BYREF
  COpusDecMFT *v13; // [rsp+68h] [rbp+38h] BYREF

  if ( (unsigned int)dword_180035090 > 4 )
  {
    v11 = 0;
    v13 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&word_1800309CE,
      a3,
      a4,
      (__int64)&v13,
      (__int64)&v11);
  }
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableOutputTypeArray(this, 1u);
  if ( inited >= 0 )
  {
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Audio);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_Float);
        if ( inited >= 0 )
        {
          if ( !*((_DWORD *)this + 49) || !*((_DWORD *)this + 48) )
          {
            inited = -1072875852;
            goto LABEL_27;
          }
          if ( !*((_QWORD *)this + 5) )
          {
LABEL_22:
            if ( *((_DWORD *)this + 6) )
            {
              v8 = ppMFType;
              v9 = **((_QWORD **)this + 4);
              if ( v9 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                **((_QWORD **)this + 4) = 0;
              }
              **((_QWORD **)this + 4) = v8;
              (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 4) + 8LL))(**((_QWORD **)this + 4));
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 1;
            }
            goto LABEL_27;
          }
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_SAMPLES_PER_SECOND);
          if ( inited < 0 )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_NUM_CHANNELS,
                     *((unsigned int *)this + 48));
          if ( inited < 0 )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_BITS_PER_SAMPLE,
                     32);
          if ( inited < 0 )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_VALID_BITS_PER_SAMPLE,
                     32);
          if ( inited < 0 )
            goto LABEL_27;
          v6 = *((_DWORD *)this + 48);
          if ( v6 == 2 )
          {
            v7 = 3;
          }
          else
          {
            if ( v6 != 1 )
              goto LABEL_19;
            v7 = 4;
          }
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_CHANNEL_MASK,
                     v7);
          if ( inited < 0 )
            goto LABEL_27;
LABEL_19:
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                     (unsigned int)(4 * *((_DWORD *)this + 48) * *((_DWORD *)this + 49)));
          if ( inited < 0 )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                     (unsigned int)(4 * *((_DWORD *)this + 48)));
          if ( inited < 0 )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_ALL_SAMPLES_INDEPENDENT,
                     1);
          if ( inited < 0 )
            goto LABEL_27;
          goto LABEL_22;
        }
      }
    }
  }
LABEL_27:
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001b994  mov     [rsp-18h+arg_0], rbx
0x18001b999  push    rbp
0x18001b99a  push    rsi
0x18001b99b  push    rdi
0x18001b99c  mov     rbp, rsp
0x18001b99f  sub     rsp, 30h
0x18001b9a3  mov     rdi, rcx
0x18001b9a6  mov     eax, cs:dword_180035090
0x18001b9ac  cmp     eax, 4
0x18001b9af  jbe     short loc_18001B9DA
0x18001b9b1  mov     [rbp+arg_8], 0
0x18001b9b8  mov     [rbp+arg_18], rcx
0x18001b9bc  lea     rax, [rbp+arg_8]
0x18001b9c0  mov     [rsp+30h+var_8], rax
0x18001b9c5  lea     rax, [rbp+arg_18]
0x18001b9c9  mov     [rsp+30h+var_10], rax
0x18001b9ce  lea     rdx, word_1800309CE
0x18001b9d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001b9da  mov     [rbp+ppMFType], 0
0x18001b9e2  mov     edx, 1; unsigned int
0x18001b9e7  mov     rcx, rdi; this
0x18001b9ea  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x18001b9ef  mov     ebx, eax
0x18001b9f1  test    eax, eax
0x18001b9f3  js      loc_18001BC4C
0x18001b9f9  lea     rcx, [rbp+ppMFType]; ppMFType
0x18001b9fd  call    cs:__imp_MFCreateMediaType
0x18001ba03  mov     ebx, eax
0x18001ba05  test    eax, eax
0x18001ba07  js      loc_18001BC4C
0x18001ba0d  mov     rcx, [rbp+ppMFType]
0x18001ba11  mov     rax, [rcx]
0x18001ba14  lea     r8, MFMediaType_Audio
0x18001ba1b  lea     rdx, MF_MT_MAJOR_TYPE
0x18001ba22  mov     rax, [rax+0C0h]
0x18001ba29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba2e  mov     ebx, eax
0x18001ba30  test    eax, eax
0x18001ba32  js      loc_18001BC4C
0x18001ba38  mov     rcx, [rbp+ppMFType]
0x18001ba3c  mov     rax, [rcx]
0x18001ba3f  lea     r8, MFAudioFormat_Float
0x18001ba46  lea     rdx, MF_MT_SUBTYPE
0x18001ba4d  mov     rax, [rax+0C0h]
0x18001ba54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba59  mov     ebx, eax
0x18001ba5b  test    eax, eax
0x18001ba5d  js      loc_18001BC4C
0x18001ba63  mov     r8d, [rdi+0C4h]
0x18001ba6a  test    r8d, r8d
0x18001ba6d  jz      loc_18001BC47
0x18001ba73  cmp     dword ptr [rdi+0C0h], 0
0x18001ba7a  jz      loc_18001BC47
0x18001ba80  cmp     qword ptr [rdi+28h], 0
0x18001ba85  jz      loc_18001BBF3
0x18001ba8b  mov     rcx, [rbp+ppMFType]
0x18001ba8f  mov     rax, [rcx]
0x18001ba92  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x18001ba99  mov     rax, [rax+0A8h]
0x18001baa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa5  mov     ebx, eax
0x18001baa7  test    eax, eax
0x18001baa9  js      loc_18001BC4C
0x18001baaf  mov     rcx, [rbp+ppMFType]
0x18001bab3  mov     rax, [rcx]
0x18001bab6  mov     r8d, [rdi+0C0h]
0x18001babd  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18001bac4  mov     rax, [rax+0A8h]
0x18001bacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad0  mov     ebx, eax
0x18001bad2  test    eax, eax
0x18001bad4  js      loc_18001BC4C
0x18001bada  mov     rcx, [rbp+ppMFType]
0x18001bade  mov     rax, [rcx]
0x18001bae1  mov     esi, 20h ; ' '
0x18001bae6  mov     r8d, esi
0x18001bae9  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18001baf0  mov     rax, [rax+0A8h]
0x18001baf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bafc  mov     ebx, eax
0x18001bafe  test    eax, eax
0x18001bb00  js      loc_18001BC4C
0x18001bb06  mov     rcx, [rbp+ppMFType]
0x18001bb0a  mov     rax, [rcx]
0x18001bb0d  mov     r8d, esi
0x18001bb10  lea     rdx, MF_MT_AUDIO_VALID_BITS_PER_SAMPLE
0x18001bb17  mov     rax, [rax+0A8h]
0x18001bb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb23  mov     ebx, eax
0x18001bb25  test    eax, eax
0x18001bb27  js      loc_18001BC4C
0x18001bb2d  mov     eax, [rdi+0C0h]
0x18001bb33  cmp     eax, 2
0x18001bb36  jnz     short loc_18001BB3E
0x18001bb38  lea     r8d, [rsi-1Dh]
0x18001bb3c  jmp     short loc_18001BB47
0x18001bb3e  cmp     eax, 1
0x18001bb41  jnz     short loc_18001BB6B
0x18001bb43  lea     r8d, [rax+3]
0x18001bb47  mov     rcx, [rbp+ppMFType]
0x18001bb4b  mov     rax, [rcx]
0x18001bb4e  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x18001bb55  mov     rax, [rax+0A8h]
0x18001bb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb61  test    eax, eax
0x18001bb63  mov     ebx, eax
0x18001bb65  js      loc_18001BC4C
0x18001bb6b  mov     rcx, [rbp+ppMFType]
0x18001bb6f  mov     rax, [rcx]
0x18001bb72  mov     r8d, [rdi+0C4h]
0x18001bb79  imul    r8d, [rdi+0C0h]
0x18001bb81  shl     r8d, 2
0x18001bb85  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x18001bb8c  mov     rax, [rax+0A8h]
0x18001bb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb98  mov     ebx, eax
0x18001bb9a  test    eax, eax
0x18001bb9c  js      loc_18001BC4C
0x18001bba2  mov     rcx, [rbp+ppMFType]
0x18001bba6  mov     rax, [rcx]
0x18001bba9  mov     r8d, [rdi+0C0h]
0x18001bbb0  shl     r8d, 2
0x18001bbb4  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18001bbbb  mov     rax, [rax+0A8h]
0x18001bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc7  mov     ebx, eax
0x18001bbc9  test    eax, eax
0x18001bbcb  js      short loc_18001BC4C
0x18001bbcd  mov     rcx, [rbp+ppMFType]
0x18001bbd1  mov     rax, [rcx]
0x18001bbd4  mov     r8d, 1
0x18001bbda  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18001bbe1  mov     rax, [rax+0A8h]
0x18001bbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbed  mov     ebx, eax
0x18001bbef  test    eax, eax
0x18001bbf1  js      short loc_18001BC4C
0x18001bbf3  cmp     dword ptr [rdi+18h], 0
0x18001bbf7  jbe     short loc_18001BC4C
0x18001bbf9  mov     rsi, [rbp+ppMFType]
0x18001bbfd  mov     rax, [rdi+20h]
0x18001bc01  mov     rcx, [rax]
0x18001bc04  test    rcx, rcx
0x18001bc07  jz      short loc_18001BC20
0x18001bc09  mov     rax, [rcx]
0x18001bc0c  mov     rax, [rax+10h]
0x18001bc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc15  mov     rax, [rdi+20h]
0x18001bc19  mov     qword ptr [rax], 0
0x18001bc20  mov     rax, [rdi+20h]
0x18001bc24  mov     [rax], rsi
0x18001bc27  mov     rax, [rdi+20h]
0x18001bc2b  mov     rcx, [rax]
0x18001bc2e  mov     rax, [rcx]
0x18001bc31  mov     rax, [rax+8]
0x18001bc35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc3a  mov     rax, [rdi+20h]
0x18001bc3e  mov     dword ptr [rax+8], 1
0x18001bc45  jmp     short loc_18001BC4C
0x18001bc47  mov     ebx, 0C00D36B4h
0x18001bc4c  mov     rcx, [rbp+ppMFType]
0x18001bc50  test    rcx, rcx
0x18001bc53  jz      short loc_18001BC62
0x18001bc55  mov     rax, [rcx]
0x18001bc58  mov     rax, [rax+10h]
0x18001bc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc61  nop
0x18001bc62  mov     eax, ebx
0x18001bc64  mov     rbx, [rsp+30h+arg_0]
0x18001bc69  add     rsp, 30h
0x18001bc6d  pop     rdi
0x18001bc6e  pop     rsi
0x18001bc6f  pop     rbp
0x18001bc70  retn
```
