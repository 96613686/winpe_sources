# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x1800257d0`
- end: `0x180025839`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `105`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800257d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800257eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800257eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025813`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025813`
- `msdmo!MoCopyMediaType` at `0x180025808`
- `msdmo!MoCopyMediaType` at `0x180025808`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetOutputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( a3 )
  {
    if ( *((_DWORD *)this + 3) )
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 104));
    else
      v7 = -2147220989;
  }
  else
  {
    v7 = -2147467261;
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x1800257d0  push    rbx
0x1800257d2  push    rbp
0x1800257d3  push    rsi
0x1800257d4  push    rdi
0x1800257d5  sub     rsp, 28h
0x1800257d9  lea     rbp, [rcx+0D8h]
0x1800257e0  mov     rdi, rcx
0x1800257e3  mov     rcx, rbp; lpCriticalSection
0x1800257e6  mov     rsi, r8
0x1800257e9  mov     ebx, edx
0x1800257eb  call    cs:__imp_EnterCriticalSection
0x1800257f1  cmp     ebx, 1
0x1800257f4  jnb     short loc_180025824
0x1800257f6  test    rsi, rsi
0x1800257f9  jz      short loc_18002582B
0x1800257fb  cmp     dword ptr [rdi+0Ch], 0
0x1800257ff  jz      short loc_180025832
0x180025801  lea     rdx, [rdi+68h]; pmtSrc
0x180025805  mov     rcx, rsi; pmtDest
0x180025808  call    cs:__imp_MoCopyMediaType
0x18002580e  mov     ebx, eax
0x180025810  mov     rcx, rbp; lpCriticalSection
0x180025813  call    cs:__imp_LeaveCriticalSection
0x180025819  mov     eax, ebx
0x18002581b  add     rsp, 28h
0x18002581f  pop     rdi
0x180025820  pop     rsi
0x180025821  pop     rbp
0x180025822  pop     rbx
0x180025823  retn
0x180025824  mov     ebx, 80040201h
0x180025829  jmp     short loc_180025810
0x18002582b  mov     ebx, 80004003h
0x180025830  jmp     short loc_180025810
0x180025832  mov     ebx, 80040203h
0x180025837  jmp     short loc_180025810
```
