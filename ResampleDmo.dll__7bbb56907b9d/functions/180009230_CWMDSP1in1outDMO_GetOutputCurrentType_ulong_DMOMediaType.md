# CWMDSP1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180009230`
- end: `0x18000928d`
- name: `?GetOutputCurrentType@CWMDSP1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(CWMDSP1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009230`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x18000926a`
- `msdmo!MoCopyMediaType` at `0x18000926a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000927c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000927c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000924b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000924b`

## pseudocode

```c
__int64 __fastcall CWMDSP1in1outDMO::GetOutputCurrentType(CWMDSP1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( *((_DWORD *)this + 3) )
  {
    v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 104));
  }
  else
  {
    v7 = -2147220989;
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x180009230  push    rbx
0x180009232  push    rbp
0x180009233  push    rsi
0x180009234  push    rdi
0x180009235  sub     rsp, 28h
0x180009239  lea     rsi, [rcx+0D0h]
0x180009240  mov     rdi, rcx
0x180009243  mov     rcx, rsi; lpCriticalSection
0x180009246  mov     rbp, r8
0x180009249  mov     ebx, edx
0x18000924b  call    cs:__imp_EnterCriticalSection
0x180009251  cmp     ebx, 1
0x180009254  jb      short loc_18000925D
0x180009256  mov     ebx, 80040201h
0x18000925b  jmp     short loc_180009279
0x18000925d  cmp     dword ptr [rdi+0Ch], 0
0x180009261  jz      short loc_180009274
0x180009263  lea     rdx, [rdi+68h]; pmtSrc
0x180009267  mov     rcx, rbp; pmtDest
0x18000926a  call    cs:__imp_MoCopyMediaType
0x180009270  mov     ebx, eax
0x180009272  jmp     short loc_180009279
0x180009274  mov     ebx, 80040203h
0x180009279  mov     rcx, rsi; lpCriticalSection
0x18000927c  call    cs:__imp_LeaveCriticalSection
0x180009282  mov     eax, ebx
0x180009284  add     rsp, 28h
0x180009288  pop     rdi
0x180009289  pop     rsi
0x18000928a  pop     rbp
0x18000928b  pop     rbx
0x18000928c  retn
```
