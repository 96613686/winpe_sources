# CMFAttributesImpl<IMFActivate,CMFCSLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x180032a30`
- end: `0x180032aa8`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180032a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a4d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032a87`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032a87`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::GetItemByIndex(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        PROPVARIANT *a4)
{
  __int64 v5; // r14
  unsigned int v8; // ebx

  v5 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (unsigned int)v5 < *(_DWORD *)(a1 + 60) )
  {
    v8 = 0;
    *a3 = *(_OWORD *)(*(_QWORD *)(a1 + 48) + 40 * v5);
    if ( a4 )
      v8 = PropVariantCopy(a4, (const PROPVARIANT *)(*(_QWORD *)(a1 + 48) + 16LL + 40 * v5));
  }
  else
  {
    v8 = -2147024809;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x180032a30  push    rbx
0x180032a32  push    rbp
0x180032a33  push    rsi
0x180032a34  push    rdi
0x180032a35  push    r14
0x180032a37  push    r15
0x180032a39  sub     rsp, 28h
0x180032a3d  mov     rdi, rcx
0x180032a40  mov     r14d, edx
0x180032a43  add     rcx, 8; lpCriticalSection
0x180032a47  mov     rbp, r9
0x180032a4a  mov     r15, r8
0x180032a4d  call    cs:__imp_EnterCriticalSection
0x180032a53  cmp     r14d, [rdi+3Ch]
0x180032a57  jb      short loc_180032A60
0x180032a59  mov     ebx, 80070057h
0x180032a5e  jmp     short loc_180032A8F
0x180032a60  mov     rax, [rdi+30h]
0x180032a64  lea     rcx, [r14+r14*4]
0x180032a68  xor     ebx, ebx
0x180032a6a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180032a6e  movdqu  xmmword ptr [r15], xmm0
0x180032a73  test    rbp, rbp
0x180032a76  jz      short loc_180032A8F
0x180032a78  mov     rax, [rdi+30h]
0x180032a7c  add     rax, 10h
0x180032a80  lea     rdx, [rax+rcx*8]; pvarSrc
0x180032a84  mov     rcx, rbp; pvarDest
0x180032a87  call    cs:__imp_PropVariantCopy
0x180032a8d  mov     ebx, eax
0x180032a8f  lea     rcx, [rdi+8]; lpCriticalSection
0x180032a93  call    cs:__imp_LeaveCriticalSection
0x180032a99  mov     eax, ebx
0x180032a9b  add     rsp, 28h
0x180032a9f  pop     r15
0x180032aa1  pop     r14
0x180032aa3  pop     rdi
0x180032aa4  pop     rsi
0x180032aa5  pop     rbp
0x180032aa6  pop     rbx
0x180032aa7  retn
```
