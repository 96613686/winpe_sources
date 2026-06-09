# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x18006db10`
- end: `0x18006db9b`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18006db10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006db7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006db7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006db2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006db2d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006db6d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006db6d`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItemByIndex(
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
0x18006db10  push    rbx
0x18006db12  push    rbp
0x18006db13  push    rsi
0x18006db14  push    rdi
0x18006db15  push    r14
0x18006db17  push    r15
0x18006db19  sub     rsp, 28h
0x18006db1d  mov     rdi, rcx
0x18006db20  mov     r14d, edx
0x18006db23  add     rcx, 8; lpCriticalSection
0x18006db27  mov     rbp, r9
0x18006db2a  mov     r15, r8
0x18006db2d  call    cs:__imp_EnterCriticalSection
0x18006db34  nop     dword ptr [rax+rax+00h]
0x18006db39  cmp     r14d, [rdi+3Ch]
0x18006db3d  jb      short loc_18006DB46
0x18006db3f  mov     ebx, 80070057h
0x18006db44  jmp     short loc_18006DB7B
0x18006db46  mov     rax, [rdi+30h]
0x18006db4a  lea     rcx, [r14+r14*4]
0x18006db4e  xor     ebx, ebx
0x18006db50  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18006db54  movdqu  xmmword ptr [r15], xmm0
0x18006db59  test    rbp, rbp
0x18006db5c  jz      short loc_18006DB7B
0x18006db5e  mov     rax, [rdi+30h]
0x18006db62  add     rax, 10h
0x18006db66  lea     rdx, [rax+rcx*8]; pvarSrc
0x18006db6a  mov     rcx, rbp; pvarDest
0x18006db6d  call    cs:__imp_PropVariantCopy
0x18006db74  nop     dword ptr [rax+rax+00h]
0x18006db79  mov     ebx, eax
0x18006db7b  lea     rcx, [rdi+8]; lpCriticalSection
0x18006db7f  call    cs:__imp_LeaveCriticalSection
0x18006db86  nop     dword ptr [rax+rax+00h]
0x18006db8b  mov     eax, ebx
0x18006db8d  add     rsp, 28h
0x18006db91  pop     r15
0x18006db93  pop     r14
0x18006db95  pop     rdi
0x18006db96  pop     rsi
0x18006db97  pop     rbp
0x18006db98  pop     rbx
0x18006db99  retn
```
