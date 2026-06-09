# Microsoft::WRL::Details::MakeAndInitialize<CMFRawTelemetrySession,IMFTelemetrySession,_GUID &,_GUID const &>(IMFTelemetrySession * *,_GUID &,_GUID const &)

- ea: `0x180097494`
- end: `0x1800975c8`
- name: `??$MakeAndInitialize@VCMFRawTelemetrySession@@UIMFTelemetrySession@@AEAU_GUID@@AEBU3@@Details@WRL@Microsoft@@YAJPEAPEAUIMFTelemetrySession@@AEAU_GUID@@AEBU4@@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009c120`

## callees

- `0x180002a24`
- `0x180095b58`
- `0x1800970ec`
- `0x180097494`
- `0x180098360`
- `0x18009d1c0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180097519`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180097519`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CMFRawTelemetrySession,IMFTelemetrySession,_GUID &,_GUID const &>(
        CMFRawTelemetrySession **a1,
        _QWORD *a2,
        _OWORD *a3)
{
  CMFRawTelemetrySession *v6; // rax
  HRESULT Guid; // edi
  CMFRawTelemetrySession *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  CMFRawTelemetrySession *v12; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v6 = (CMFRawTelemetrySession *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v6;
  if ( v6 )
  {
    v8 = CMFRawTelemetrySession::CMFRawTelemetrySession(v6);
    v12 = 0;
    v9 = *a2 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( *a2 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
      v9 = a2[1] - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v9 )
    {
      *((_OWORD *)v8 + 5) = *(_OWORD *)a2;
    }
    else
    {
      Guid = CoCreateGuid((GUID *)v8 + 5);
      if ( Guid < 0 )
      {
        if ( !v8 )
          goto LABEL_16;
LABEL_15:
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>>::Release(v8);
        goto LABEL_16;
      }
    }
    *((_OWORD *)v8 + 6) = *a3;
    *a1 = 0;
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
                         &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a1 = v8;
      (*(void (__fastcall **)(CMFRawTelemetrySession *))(*(_QWORD *)v8 + 8LL))(v8);
      Guid = 0;
    }
    else if ( (unsigned int)InlineIsEqualGUID(v10, v10) )
    {
      *a1 = v8;
      Guid = 0;
      (*(void (__fastcall **)(CMFRawTelemetrySession *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    else
    {
      Guid = -2147467262;
    }
    goto LABEL_15;
  }
  Guid = -2147024882;
LABEL_16:
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(&v12);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x180097494  mov     rax, rsp
0x180097497  push    rdi
0x180097498  sub     rsp, 30h
0x18009749c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800974a4  mov     [rax+10h], rbx
0x1800974a8  mov     [rax+18h], rbp
0x1800974ac  mov     [rax+20h], rsi
0x1800974b0  mov     rbp, r8
0x1800974b3  mov     rdi, rdx
0x1800974b6  mov     rsi, rcx
0x1800974b9  mov     qword ptr [rcx], 0
0x1800974c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800974c7  mov     ecx, 88h; unsigned __int64
0x1800974cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800974d1  mov     [rsp+38h+arg_0], rax
0x1800974d6  test    rax, rax
0x1800974d9  jnz     short loc_1800974E5
0x1800974db  mov     edi, 8007000Eh
0x1800974e0  jmp     loc_1800975A6
0x1800974e5  mov     rcx, rax; this
0x1800974e8  call    ??0CMFRawTelemetrySession@@QEAA@XZ; CMFRawTelemetrySession::CMFRawTelemetrySession(void)
0x1800974ed  mov     rbx, rax
0x1800974f0  mov     [rsp+38h+arg_0], 0
0x1800974f9  mov     rax, [rdi]
0x1800974fc  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180097503  jnz     short loc_180097510
0x180097505  mov     rax, [rdi+8]
0x180097509  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180097510  test    rax, rax
0x180097513  jnz     short loc_180097532
0x180097515  lea     rcx, [rbx+50h]; pguid
0x180097519  call    cs:__imp_CoCreateGuid
0x180097520  nop     dword ptr [rax+rax+00h]
0x180097525  mov     edi, eax
0x180097527  test    eax, eax
0x180097529  jns     short loc_18009753A
0x18009752b  test    rbx, rbx
0x18009752e  jz      short loc_1800975A6
0x180097530  jmp     short loc_18009759E
0x180097532  movups  xmm0, xmmword ptr [rdi]
0x180097535  movdqu  xmmword ptr [rbx+50h], xmm0
0x18009753a  movups  xmm0, xmmword ptr [rbp+0]
0x18009753e  movdqu  xmmword ptr [rbx+60h], xmm0
0x180097543  mov     qword ptr [rsi], 0
0x18009754a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180097551  lea     rcx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x180097558  call    InlineIsEqualGUID
0x18009755d  test    eax, eax
0x18009755f  jnz     short loc_18009758A
0x180097561  mov     rdx, rcx
0x180097564  call    InlineIsEqualGUID
0x180097569  test    eax, eax
0x18009756b  jz      short loc_180097583
0x18009756d  mov     [rsi], rbx
0x180097570  xor     edi, edi
0x180097572  mov     rax, [rbx]
0x180097575  mov     rcx, rbx
0x180097578  mov     rax, [rax+8]
0x18009757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097581  jmp     short loc_18009759E
0x180097583  mov     edi, 80004002h
0x180097588  jmp     short loc_18009759E
0x18009758a  mov     [rsi], rbx
0x18009758d  mov     rax, [rbx]
0x180097590  mov     rcx, rbx
0x180097593  mov     rax, [rax+8]
0x180097597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009759c  xor     edi, edi
0x18009759e  mov     rcx, rbx
0x1800975a1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@V?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>>::Release(void)
0x1800975a6  lea     rcx, [rsp+38h+arg_0]
0x1800975ab  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x1800975b0  mov     eax, edi
0x1800975b2  mov     rbx, [rsp+38h+arg_8]
0x1800975b7  mov     rbp, [rsp+38h+arg_10]
0x1800975bc  mov     rsi, [rsp+38h+arg_18]
0x1800975c1  add     rsp, 30h
0x1800975c5  pop     rdi
0x1800975c6  retn
```
