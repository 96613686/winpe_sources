# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x1800040c0`
- end: `0x18000411d`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800040c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000410c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000410c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040db`
- `msdmo!MoCopyMediaType` at `0x1800040fa`
- `msdmo!MoCopyMediaType` at `0x1800040fa`

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
0x1800040c0  push    rbx
0x1800040c2  push    rbp
0x1800040c3  push    rsi
0x1800040c4  push    rdi
0x1800040c5  sub     rsp, 28h
0x1800040c9  lea     rsi, [rcx+0C8h]
0x1800040d0  mov     rdi, rcx
0x1800040d3  mov     rcx, rsi; lpCriticalSection
0x1800040d6  mov     rbp, r8
0x1800040d9  mov     ebx, edx
0x1800040db  call    cs:__imp_EnterCriticalSection
0x1800040e1  cmp     ebx, 1
0x1800040e4  jb      short loc_1800040ED
0x1800040e6  mov     ebx, 80040201h
0x1800040eb  jmp     short loc_180004109
0x1800040ed  cmp     dword ptr [rdi+8], 0
0x1800040f1  jz      short loc_180004104
0x1800040f3  lea     rdx, [rdi+10h]; pmtSrc
0x1800040f7  mov     rcx, rbp; pmtDest
0x1800040fa  call    cs:__imp_MoCopyMediaType
0x180004100  mov     ebx, eax
0x180004102  jmp     short loc_180004109
0x180004104  mov     ebx, 80040203h
0x180004109  mov     rcx, rsi; lpCriticalSection
0x18000410c  call    cs:__imp_LeaveCriticalSection
0x180004112  mov     eax, ebx
0x180004114  add     rsp, 28h
0x180004118  pop     rdi
0x180004119  pop     rsi
0x18000411a  pop     rbp
0x18000411b  pop     rbx
0x18000411c  retn
```
