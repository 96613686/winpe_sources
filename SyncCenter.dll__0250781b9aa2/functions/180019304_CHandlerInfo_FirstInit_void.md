# CHandlerInfo::_FirstInit(void)

- ea: `0x180019304`
- end: `0x1800193be`
- name: `?_FirstInit@CHandlerInfo@@AEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(CHandlerInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800074e8`

## callees

- `0x180005360`
- `0x180008a90`
- `0x180012e54`
- `0x180019304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019367`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019398`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019367`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019398`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::_FirstInit(CHandlerInfo *this)
{
  HDPA v2; // rax
  int Error; // ebx
  HANDLE v4; // rax
  HANDLE EventW; // rax

  if ( (*((_QWORD *)this + 254) || (v2 = DPA_Create(4), (*((_QWORD *)this + 254) = v2) != 0))
    && (*((_QWORD *)this + 255)
     || (unsigned int)CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create(
                        (char *)this + 2040,
                        4)) )
  {
    Error = 0;
    if ( *((_QWORD *)this + 257)
      || (v4 = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 257) = v4) != 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( !*((_QWORD *)this + 258) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 258) = EventW;
        if ( !EventW )
          return (unsigned int)ResultFromKnownLastError();
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180019304  mov     [rsp+arg_0], rbx
0x180019309  push    rdi
0x18001930a  sub     rsp, 20h
0x18001930e  cmp     qword ptr [rcx+7F0h], 0
0x180019316  mov     rdi, rcx
0x180019319  mov     ebx, 4
0x18001931e  jnz     short loc_180019333
0x180019320  mov     ecx, ebx; cItemGrow
0x180019322  call    DPA_Create
0x180019327  mov     [rdi+7F0h], rax
0x18001932e  test    rax, rax
0x180019331  jz      short loc_18001934B
0x180019333  lea     rcx, [rdi+7F8h]
0x18001933a  cmp     qword ptr [rcx], 0
0x18001933e  jnz     short loc_180019352
0x180019340  mov     edx, ebx
0x180019342  call    ?Create@?$CDPA_Base@USYNCMGR_EVENTINFO@@V?$CTContainer_PolicyUnOwned@USYNCMGR_EVENTINFO@@@@@@QEAAHH@Z; CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create(int)
0x180019347  test    eax, eax
0x180019349  jnz     short loc_180019352
0x18001934b  mov     ebx, 8007000Eh
0x180019350  jmp     short loc_1800193B1
0x180019352  xor     ebx, ebx
0x180019354  cmp     [rdi+808h], rbx
0x18001935b  jnz     short loc_180019384
0x18001935d  xor     r9d, r9d; lpName
0x180019360  xor     r8d, r8d; bInitialState
0x180019363  xor     edx, edx; bManualReset
0x180019365  xor     ecx, ecx; lpEventAttributes
0x180019367  call    cs:__imp_CreateEventW
0x18001936d  mov     [rdi+808h], rax
0x180019374  test    rax, rax
0x180019377  jnz     short loc_180019384
0x180019379  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001937e  mov     ebx, eax
0x180019380  test    eax, eax
0x180019382  js      short loc_1800193B1
0x180019384  cmp     qword ptr [rdi+810h], 0
0x18001938c  jnz     short loc_1800193B1
0x18001938e  xor     r9d, r9d; lpName
0x180019391  xor     r8d, r8d; bInitialState
0x180019394  xor     edx, edx; bManualReset
0x180019396  xor     ecx, ecx; lpEventAttributes
0x180019398  call    cs:__imp_CreateEventW
0x18001939e  mov     [rdi+810h], rax
0x1800193a5  test    rax, rax
0x1800193a8  jnz     short loc_1800193B1
0x1800193aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800193af  mov     ebx, eax
0x1800193b1  mov     eax, ebx
0x1800193b3  mov     rbx, [rsp+28h+arg_0]
0x1800193b8  add     rsp, 20h
0x1800193bc  pop     rdi
0x1800193bd  retn
```
