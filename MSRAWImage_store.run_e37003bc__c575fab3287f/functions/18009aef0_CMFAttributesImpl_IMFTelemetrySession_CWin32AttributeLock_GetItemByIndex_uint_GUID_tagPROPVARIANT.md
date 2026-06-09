# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x18009aef0`
- end: `0x18009af92`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009aef0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009af58`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009af58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009af6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009af6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009af1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009af1a`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetItemByIndex(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        PROPVARIANT *a4)
{
  __int64 v5; // r14
  unsigned int v8; // ebx

  v5 = a2;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (unsigned int)v5 < *(_DWORD *)(a1 + 60) )
  {
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
0x18009aef0  mov     [rsp+arg_0], rbx
0x18009aef5  mov     [rsp+arg_8], rbp
0x18009aefa  mov     [rsp+arg_10], rsi
0x18009aeff  push    rdi
0x18009af00  push    r14
0x18009af02  push    r15
0x18009af04  sub     rsp, 20h
0x18009af08  mov     rdi, rcx
0x18009af0b  mov     r14d, edx
0x18009af0e  add     rcx, 8; lpCriticalSection
0x18009af12  mov     rbp, r9
0x18009af15  mov     r15, r8
0x18009af18  xor     ebx, ebx
0x18009af1a  call    cs:__imp_EnterCriticalSection
0x18009af21  nop     dword ptr [rax+rax+00h]
0x18009af26  cmp     r14d, [rdi+3Ch]
0x18009af2a  jb      short loc_18009AF33
0x18009af2c  mov     ebx, 80070057h
0x18009af31  jmp     short loc_18009AF66
0x18009af33  mov     rax, [rdi+30h]
0x18009af37  lea     rcx, [r14+r14*4]
0x18009af3b  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18009af3f  movdqu  xmmword ptr [r15], xmm0
0x18009af44  test    rbp, rbp
0x18009af47  jz      short loc_18009AF66
0x18009af49  mov     rax, [rdi+30h]
0x18009af4d  add     rax, 10h
0x18009af51  lea     rdx, [rax+rcx*8]; pvarSrc
0x18009af55  mov     rcx, rbp; pvarDest
0x18009af58  call    cs:__imp_PropVariantCopy
0x18009af5f  nop     dword ptr [rax+rax+00h]
0x18009af64  mov     ebx, eax
0x18009af66  lea     rcx, [rdi+8]; lpCriticalSection
0x18009af6a  call    cs:__imp_LeaveCriticalSection
0x18009af71  nop     dword ptr [rax+rax+00h]
0x18009af76  mov     rbp, [rsp+38h+arg_8]
0x18009af7b  mov     eax, ebx
0x18009af7d  mov     rbx, [rsp+38h+arg_0]
0x18009af82  mov     rsi, [rsp+38h+arg_10]
0x18009af87  add     rsp, 20h
0x18009af8b  pop     r15
0x18009af8d  pop     r14
0x18009af8f  pop     rdi
0x18009af90  retn
```
