# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180004180`
- end: `0x1800041dd`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000419b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000419b`
- `msdmo!MoCopyMediaType` at `0x1800041ba`
- `msdmo!MoCopyMediaType` at `0x1800041ba`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetInputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( *((_DWORD *)this + 2) )
  {
    v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 16));
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
0x180004180  push    rbx
0x180004182  push    rbp
0x180004183  push    rsi
0x180004184  push    rdi
0x180004185  sub     rsp, 28h
0x180004189  lea     rsi, [rcx+0C8h]
0x180004190  mov     rdi, rcx
0x180004193  mov     rcx, rsi; lpCriticalSection
0x180004196  mov     rbp, r8
0x180004199  mov     ebx, edx
0x18000419b  call    cs:__imp_EnterCriticalSection
0x1800041a1  cmp     ebx, 1
0x1800041a4  jb      short loc_1800041AD
0x1800041a6  mov     ebx, 80040201h
0x1800041ab  jmp     short loc_1800041C9
0x1800041ad  cmp     dword ptr [rdi+8], 0
0x1800041b1  jz      short loc_1800041C4
0x1800041b3  lea     rdx, [rdi+10h]; pmtSrc
0x1800041b7  mov     rcx, rbp; pmtDest
0x1800041ba  call    cs:__imp_MoCopyMediaType
0x1800041c0  mov     ebx, eax
0x1800041c2  jmp     short loc_1800041C9
0x1800041c4  mov     ebx, 80040203h
0x1800041c9  mov     rcx, rsi; lpCriticalSection
0x1800041cc  call    cs:__imp_LeaveCriticalSection
0x1800041d2  mov     eax, ebx
0x1800041d4  add     rsp, 28h
0x1800041d8  pop     rdi
0x1800041d9  pop     rsi
0x1800041da  pop     rbp
0x1800041db  pop     rbx
0x1800041dc  retn
```
