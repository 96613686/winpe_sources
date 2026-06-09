# COpusDecMFT::ConfigInputTypes(void)

- ea: `0x18001b838`
- end: `0x18001b98d`
- name: `?ConfigInputTypes@COpusDecMFT@@AEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(COpusDecMFT *this, __int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c3c0`

## callees

- `0x1800010c8`
- `0x18001b838`
- `0x18001ec68`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001b89d`
- `MFPlat!MFCreateMediaType` at `0x18001b89d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall COpusDecMFT::ConfigInputTypes(COpusDecMFT *this, __int64 a2, int a3, int a4)
{
  HRESULT inited; // edi
  IMFMediaType *v6; // rsi
  __int64 v7; // rcx
  int v9; // [rsp+58h] [rbp+10h] BYREF
  IMFMediaType *ppMFType; // [rsp+60h] [rbp+18h] BYREF
  COpusDecMFT *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180035090 > 4 )
  {
    v9 = 0;
    v11 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&unk_180030840,
      a3,
      a4,
      (__int64)&v11,
      (__int64)&v9);
  }
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableInputTypeArray(this, 1u);
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
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_Opus);
        if ( inited >= 0 )
        {
          if ( *((_DWORD *)this + 2) )
          {
            v6 = ppMFType;
            v7 = **((_QWORD **)this + 2);
            if ( v7 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              **((_QWORD **)this + 2) = 0;
            }
            **((_QWORD **)this + 2) = v6;
            (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 2) + 8LL))(**((_QWORD **)this + 2));
            *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) = 1;
          }
          *((_DWORD *)this + 36) = 0;
          *((_DWORD *)this + 13) = 0x10000;
          *((_DWORD *)this + 23) = 0x80000;
        }
      }
    }
  }
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001b838  mov     r11, rsp
0x18001b83b  push    rbx
0x18001b83c  push    rsi
0x18001b83d  push    rdi
0x18001b83e  sub     rsp, 30h
0x18001b842  mov     rbx, rcx
0x18001b845  mov     eax, cs:dword_180035090
0x18001b84b  cmp     eax, 4
0x18001b84e  jbe     short loc_18001B878
0x18001b850  mov     [rsp+48h+arg_8], 0
0x18001b858  mov     [r11+20h], rcx
0x18001b85c  lea     rax, [r11+10h]
0x18001b860  mov     [r11-20h], rax
0x18001b864  lea     rax, [r11+20h]
0x18001b868  mov     [r11-28h], rax
0x18001b86c  lea     rdx, unk_180030840
0x18001b873  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001b878  mov     [rsp+48h+ppMFType], 0
0x18001b881  mov     edx, 1; unsigned int
0x18001b886  mov     rcx, rbx; this
0x18001b889  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18001b88e  mov     edi, eax
0x18001b890  test    eax, eax
0x18001b892  js      loc_18001B96C
0x18001b898  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x18001b89d  call    cs:__imp_MFCreateMediaType
0x18001b8a3  mov     edi, eax
0x18001b8a5  test    eax, eax
0x18001b8a7  js      loc_18001B96C
0x18001b8ad  mov     rcx, [rsp+48h+ppMFType]
0x18001b8b2  mov     rax, [rcx]
0x18001b8b5  lea     r8, MFMediaType_Audio
0x18001b8bc  lea     rdx, MF_MT_MAJOR_TYPE
0x18001b8c3  mov     rax, [rax+0C0h]
0x18001b8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8cf  mov     edi, eax
0x18001b8d1  test    eax, eax
0x18001b8d3  js      loc_18001B96C
0x18001b8d9  mov     rcx, [rsp+48h+ppMFType]
0x18001b8de  mov     rax, [rcx]
0x18001b8e1  lea     r8, MFAudioFormat_Opus
0x18001b8e8  lea     rdx, MF_MT_SUBTYPE
0x18001b8ef  mov     rax, [rax+0C0h]
0x18001b8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8fb  mov     edi, eax
0x18001b8fd  test    eax, eax
0x18001b8ff  js      short loc_18001B96C
0x18001b901  cmp     dword ptr [rbx+8], 0
0x18001b905  jbe     short loc_18001B954
0x18001b907  mov     rsi, [rsp+48h+ppMFType]
0x18001b90c  mov     rax, [rbx+10h]
0x18001b910  mov     rcx, [rax]
0x18001b913  test    rcx, rcx
0x18001b916  jz      short loc_18001B92F
0x18001b918  mov     rax, [rcx]
0x18001b91b  mov     rax, [rax+10h]
0x18001b91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b924  mov     rax, [rbx+10h]
0x18001b928  mov     qword ptr [rax], 0
0x18001b92f  mov     rax, [rbx+10h]
0x18001b933  mov     [rax], rsi
0x18001b936  mov     rax, [rbx+10h]
0x18001b93a  mov     rcx, [rax]
0x18001b93d  mov     rax, [rcx]
0x18001b940  mov     rax, [rax+8]
0x18001b944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b949  mov     rax, [rbx+10h]
0x18001b94d  mov     dword ptr [rax+8], 1
0x18001b954  mov     dword ptr [rbx+90h], 0
0x18001b95e  mov     dword ptr [rbx+34h], 10000h
0x18001b965  mov     dword ptr [rbx+5Ch], 80000h
0x18001b96c  mov     rcx, [rsp+48h+ppMFType]
0x18001b971  test    rcx, rcx
0x18001b974  jz      short loc_18001B983
0x18001b976  mov     rax, [rcx]
0x18001b979  mov     rax, [rax+10h]
0x18001b97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b982  nop
0x18001b983  mov     eax, edi
0x18001b985  add     rsp, 30h
0x18001b989  pop     rdi
0x18001b98a  pop     rsi
0x18001b98b  pop     rbx
0x18001b98c  retn
```
