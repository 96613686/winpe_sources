# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x1800044f0`
- end: `0x18000454d`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800044f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000453c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000453c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000450b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000450b`
- `msdmo!MoCopyMediaType` at `0x18000452a`
- `msdmo!MoCopyMediaType` at `0x18000452a`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetOutputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
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
0x1800044f0  push    rbx
0x1800044f2  push    rbp
0x1800044f3  push    rsi
0x1800044f4  push    rdi
0x1800044f5  sub     rsp, 28h
0x1800044f9  lea     rsi, [rcx+0C8h]
0x180004500  mov     rdi, rcx
0x180004503  mov     rcx, rsi; lpCriticalSection
0x180004506  mov     rbp, r8
0x180004509  mov     ebx, edx
0x18000450b  call    cs:__imp_EnterCriticalSection
0x180004511  cmp     ebx, 1
0x180004514  jb      short loc_18000451D
0x180004516  mov     ebx, 80040201h
0x18000451b  jmp     short loc_180004539
0x18000451d  cmp     dword ptr [rdi+0Ch], 0
0x180004521  jz      short loc_180004534
0x180004523  lea     rdx, [rdi+68h]; pmtSrc
0x180004527  mov     rcx, rbp; pmtDest
0x18000452a  call    cs:__imp_MoCopyMediaType
0x180004530  mov     ebx, eax
0x180004532  jmp     short loc_180004539
0x180004534  mov     ebx, 80040203h
0x180004539  mov     rcx, rsi; lpCriticalSection
0x18000453c  call    cs:__imp_LeaveCriticalSection
0x180004542  mov     eax, ebx
0x180004544  add     rsp, 28h
0x180004548  pop     rdi
0x180004549  pop     rsi
0x18000454a  pop     rbp
0x18000454b  pop     rbx
0x18000454c  retn
```
