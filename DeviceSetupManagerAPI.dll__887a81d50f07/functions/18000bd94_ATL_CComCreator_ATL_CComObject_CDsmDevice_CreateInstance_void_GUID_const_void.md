# ATL::CComCreator<ATL::CComObject<CDsmDevice>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bd94`
- end: `0x18000bf26`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDsmDevice@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bbf0`

## callees

- `0x18000137c`
- `0x18000bd94`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000beac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000beac`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000be1e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000be1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bebf`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDsmDevice>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  char *v8; // rdi
  int v9; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v12; // sf
  HANDLE v13; // rax
  int v14; // eax
  char *v17; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x70u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_DWORD *)v7 + 4) = 3;
      *((_QWORD *)v7 + 3) = 0;
      *((_QWORD *)v7 + 11) = 0;
      *((_QWORD *)v7 + 13) = 0;
      *(_OWORD *)(v7 + 72) = 0;
      InitializeSRWLock((PSRWLOCK)v7 + 8);
      *(_QWORD *)v8 = &ATL::CComObject<CDsmDevice>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v17 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v17;
  }
  if ( v8 )
  {
    v9 = *((_DWORD *)v8 + 2);
    if ( v9 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 2) = v9 + 1;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v8 + 9) = EventW;
    if ( EventW )
      goto LABEL_13;
    LastError = GetLastError();
    v12 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v12 = LastError < 0;
    }
    if ( !v12 )
    {
LABEL_13:
      v13 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v8 + 10) = v13;
      if ( v13 )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
    }
    v6 = 0;
    if ( LastError < 0 )
      v6 = LastError;
    v14 = *((_DWORD *)v8 + 2);
    if ( v14 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 2) = v14 - 1;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000bd94  mov     [rsp+arg_10], r8
0x18000bd99  mov     [rsp+arg_8], rdx
0x18000bd9e  mov     [rsp+arg_0], rcx
0x18000bda3  push    rsi
0x18000bda4  push    rdi
0x18000bda5  push    r14
0x18000bda7  push    r15
0x18000bda9  sub     rsp, 28h
0x18000bdad  mov     r14, r8
0x18000bdb0  mov     r15, rdx
0x18000bdb3  test    r8, r8
0x18000bdb6  jnz     short loc_18000BDC2
0x18000bdb8  mov     eax, 80004003h
0x18000bdbd  jmp     loc_18000BF1B
0x18000bdc2  mov     qword ptr [r8], 0
0x18000bdc9  mov     esi, 8007000Eh
0x18000bdce  mov     dword ptr [rsp+48h+arg_0], esi
0x18000bdd2  mov     [rsp+48h+arg_18], 0
0x18000bddb  mov     ecx, 70h ; 'p'; Size
0x18000bde0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bde5  mov     rdi, rax
0x18000bde8  test    rdi, rdi
0x18000bdeb  jz      short loc_18000BE41
0x18000bded  mov     dword ptr [rax+8], 0
0x18000bdf4  mov     dword ptr [rax+10h], 3
0x18000bdfb  mov     qword ptr [rax+18h], 0
0x18000be03  mov     qword ptr [rax+58h], 0
0x18000be0b  mov     qword ptr [rax+68h], 0
0x18000be13  xorps   xmm0, xmm0
0x18000be16  movups  xmmword ptr [rax+48h], xmm0
0x18000be1a  lea     rcx, [rax+40h]; SRWLock
0x18000be1e  call    cs:__imp_InitializeSRWLock
0x18000be24  lea     rax, ??_7?$CComObject@VCDsmDevice@@@ATL@@6B@; const ATL::CComObject<CDsmDevice>::`vftable'
0x18000be2b  mov     [rdi], rax
0x18000be2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000be35  mov     rax, [rcx]
0x18000be38  mov     rax, [rax+8]
0x18000be3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be41  mov     [rsp+48h+arg_18], rdi
0x18000be46  jmp     short loc_18000BE5B
0x18000be48  mov     r14, [rsp+48h+arg_10]
0x18000be4d  mov     r15, [rsp+48h+arg_8]
0x18000be52  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000be56  mov     rdi, [rsp+48h+arg_18]
0x18000be5b  test    rdi, rdi
0x18000be5e  jz      loc_18000BF19
0x18000be64  mov     eax, [rdi+8]
0x18000be67  cmp     eax, 7FFFFFFFh
0x18000be6c  jz      short loc_18000BE73
0x18000be6e  inc     eax
0x18000be70  mov     [rdi+8], eax
0x18000be73  xor     r9d, r9d; lpName
0x18000be76  xor     r8d, r8d; bInitialState
0x18000be79  xor     edx, edx; bManualReset
0x18000be7b  xor     ecx, ecx; lpEventAttributes
0x18000be7d  call    cs:__imp_CreateEventW
0x18000be83  mov     [rdi+48h], rax
0x18000be87  test    rax, rax
0x18000be8a  jnz     short loc_18000BEA2
0x18000be8c  call    cs:__imp_GetLastError
0x18000be92  test    eax, eax
0x18000be94  jle     short loc_18000BEA0
0x18000be96  movzx   eax, ax
0x18000be99  or      eax, 80070000h
0x18000be9e  test    eax, eax
0x18000bea0  js      short loc_18000BED1
0x18000bea2  xor     r9d, r9d; lpName
0x18000bea5  xor     r8d, r8d; bInitialState
0x18000bea8  xor     edx, edx; bManualReset
0x18000beaa  xor     ecx, ecx; lpEventAttributes
0x18000beac  call    cs:__imp_CreateEventW
0x18000beb2  mov     [rdi+50h], rax
0x18000beb6  test    rax, rax
0x18000beb9  jz      short loc_18000BEBF
0x18000bebb  xor     eax, eax
0x18000bebd  jmp     short loc_18000BED1
0x18000bebf  call    cs:__imp_GetLastError
0x18000bec5  test    eax, eax
0x18000bec7  jle     short loc_18000BED1
0x18000bec9  movzx   eax, ax
0x18000becc  or      eax, 80070000h
0x18000bed1  xor     esi, esi
0x18000bed3  test    eax, eax
0x18000bed5  cmovs   esi, eax
0x18000bed8  mov     eax, [rdi+8]
0x18000bedb  cmp     eax, 7FFFFFFFh
0x18000bee0  jz      short loc_18000BEE7
0x18000bee2  dec     eax
0x18000bee4  mov     [rdi+8], eax
0x18000bee7  test    esi, esi
0x18000bee9  jnz     short loc_18000BF05
0x18000beeb  mov     rax, [rdi]
0x18000beee  mov     r8, r14
0x18000bef1  mov     rdx, r15
0x18000bef4  mov     rcx, rdi
0x18000bef7  mov     rax, [rax]
0x18000befa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beff  mov     esi, eax
0x18000bf01  test    eax, eax
0x18000bf03  jz      short loc_18000BF19
0x18000bf05  mov     rdx, [rdi]
0x18000bf08  mov     rax, [rdx+48h]
0x18000bf0c  mov     edx, 1
0x18000bf11  mov     rcx, rdi
0x18000bf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf19  mov     eax, esi
0x18000bf1b  add     rsp, 28h
0x18000bf1f  pop     r15
0x18000bf21  pop     r14
0x18000bf23  pop     rdi
0x18000bf24  pop     rsi
0x18000bf25  retn
```
