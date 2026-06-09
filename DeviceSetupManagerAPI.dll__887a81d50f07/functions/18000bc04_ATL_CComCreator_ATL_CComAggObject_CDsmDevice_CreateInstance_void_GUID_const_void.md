# ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bc04`
- end: `0x18000bd8c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDsmDevice@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bbf0`

## callees

- `0x18000137c`
- `0x18000bc04`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bcf4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bcf4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd23`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000bc9f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000bc9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd32`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  _QWORD *v9; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v12; // sf
  HANDLE v13; // rax
  _QWORD *v14; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x80u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDsmDevice>::`vftable';
      *((_DWORD *)v8 + 6) = 0;
      *((_DWORD *)v8 + 8) = 3;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 15) = 0;
      *(_OWORD *)(v8 + 88) = 0;
      InitializeSRWLock((PSRWLOCK)v8 + 10);
      v9[2] = &ATL::CComContainedObject<CDsmDevice>::`vftable';
      v9[3] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v14 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v14;
  }
  if ( !v9 )
    return v7;
  EventW = CreateEventW(0, 0, 0, 0);
  v9[11] = EventW;
  if ( EventW )
    goto LABEL_11;
  LastError = GetLastError();
  v12 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = LastError < 0;
  }
  if ( !v12 )
  {
LABEL_11:
    v13 = CreateEventW(0, 0, 0, 0);
    v9[12] = v13;
    if ( v13 )
      goto LABEL_17;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v7 = 0;
  if ( LastError < 0 )
    v7 = LastError;
  if ( v7 )
    goto LABEL_18;
LABEL_17:
  v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3);
  if ( v7 )
LABEL_18:
    (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  return v7;
}

```

## disassembly

```asm
0x18000bc04  mov     [rsp+arg_10], r8
0x18000bc09  mov     [rsp+arg_8], rdx
0x18000bc0e  push    rsi
0x18000bc0f  push    rdi
0x18000bc10  push    r12
0x18000bc12  push    r14
0x18000bc14  push    r15
0x18000bc16  sub     rsp, 30h
0x18000bc1a  mov     r14, r8
0x18000bc1d  mov     r15, rdx
0x18000bc20  mov     r12, rcx
0x18000bc23  test    r8, r8
0x18000bc26  jnz     short loc_18000BC32
0x18000bc28  mov     eax, 80004003h
0x18000bc2d  jmp     loc_18000BD7F
0x18000bc32  mov     qword ptr [r8], 0
0x18000bc39  mov     esi, 8007000Eh
0x18000bc3e  mov     [rsp+58h+arg_18], esi
0x18000bc42  mov     [rsp+58h+var_38], 0
0x18000bc4b  mov     ecx, 80h; Size
0x18000bc50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc55  mov     rdi, rax
0x18000bc58  test    rdi, rdi
0x18000bc5b  jz      short loc_18000BCC7
0x18000bc5d  mov     dword ptr [rax+8], 0
0x18000bc64  lea     rax, ??_7?$CComAggObject@VCDsmDevice@@@ATL@@6B@; const ATL::CComAggObject<CDsmDevice>::`vftable'
0x18000bc6b  mov     [rdi], rax
0x18000bc6e  mov     dword ptr [rdi+18h], 0
0x18000bc75  mov     dword ptr [rdi+20h], 3
0x18000bc7c  mov     qword ptr [rdi+28h], 0
0x18000bc84  mov     qword ptr [rdi+68h], 0
0x18000bc8c  mov     qword ptr [rdi+78h], 0
0x18000bc94  xorps   xmm0, xmm0
0x18000bc97  movups  xmmword ptr [rdi+58h], xmm0
0x18000bc9b  lea     rcx, [rdi+50h]; SRWLock
0x18000bc9f  call    cs:__imp_InitializeSRWLock
0x18000bca5  lea     rax, ??_7?$CComContainedObject@VCDsmDevice@@@ATL@@6B@; const ATL::CComContainedObject<CDsmDevice>::`vftable'
0x18000bcac  mov     [rdi+10h], rax
0x18000bcb0  mov     [rdi+18h], r12
0x18000bcb4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bcbb  mov     rax, [rcx]
0x18000bcbe  mov     rax, [rax+8]
0x18000bcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc7  mov     [rsp+58h+var_38], rdi
0x18000bccc  jmp     short loc_18000BCE1
0x18000bcce  mov     r14, [rsp+58h+arg_10]
0x18000bcd3  mov     r15, [rsp+58h+arg_8]
0x18000bcd8  mov     esi, [rsp+58h+arg_18]
0x18000bcdc  mov     rdi, [rsp+58h+var_38]
0x18000bce1  test    rdi, rdi
0x18000bce4  jz      loc_18000BD7D
0x18000bcea  xor     r9d, r9d; lpName
0x18000bced  xor     r8d, r8d; bInitialState
0x18000bcf0  xor     edx, edx; bManualReset
0x18000bcf2  xor     ecx, ecx; lpEventAttributes
0x18000bcf4  call    cs:__imp_CreateEventW
0x18000bcfa  mov     [rdi+58h], rax
0x18000bcfe  test    rax, rax
0x18000bd01  jnz     short loc_18000BD19
0x18000bd03  call    cs:__imp_GetLastError
0x18000bd09  test    eax, eax
0x18000bd0b  jle     short loc_18000BD17
0x18000bd0d  movzx   eax, ax
0x18000bd10  or      eax, 80070000h
0x18000bd15  test    eax, eax
0x18000bd17  js      short loc_18000BD44
0x18000bd19  xor     r9d, r9d; lpName
0x18000bd1c  xor     r8d, r8d; bInitialState
0x18000bd1f  xor     edx, edx; bManualReset
0x18000bd21  xor     ecx, ecx; lpEventAttributes
0x18000bd23  call    cs:__imp_CreateEventW
0x18000bd29  mov     [rdi+60h], rax
0x18000bd2d  test    rax, rax
0x18000bd30  jnz     short loc_18000BD4F
0x18000bd32  call    cs:__imp_GetLastError
0x18000bd38  test    eax, eax
0x18000bd3a  jle     short loc_18000BD44
0x18000bd3c  movzx   eax, ax
0x18000bd3f  or      eax, 80070000h
0x18000bd44  xor     esi, esi
0x18000bd46  test    eax, eax
0x18000bd48  cmovs   esi, eax
0x18000bd4b  test    esi, esi
0x18000bd4d  jnz     short loc_18000BD69
0x18000bd4f  mov     rax, [rdi]
0x18000bd52  mov     r8, r14
0x18000bd55  mov     rdx, r15
0x18000bd58  mov     rcx, rdi
0x18000bd5b  mov     rax, [rax]
0x18000bd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd63  mov     esi, eax
0x18000bd65  test    eax, eax
0x18000bd67  jz      short loc_18000BD7D
0x18000bd69  mov     rdx, [rdi]
0x18000bd6c  mov     rax, [rdx+18h]
0x18000bd70  mov     edx, 1
0x18000bd75  mov     rcx, rdi
0x18000bd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7d  mov     eax, esi
0x18000bd7f  add     rsp, 30h
0x18000bd83  pop     r15
0x18000bd85  pop     r14
0x18000bd87  pop     r12
0x18000bd89  pop     rdi
0x18000bd8a  pop     rsi
0x18000bd8b  retn
```
