# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x1800091a0`
- end: `0x1800091fd`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800091a0`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x1800091d3`
- `msdmo!MoCopyMediaType` at `0x1800091d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091bb`

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
0x1800091a0  push    rbx
0x1800091a2  push    rbp
0x1800091a3  push    rsi
0x1800091a4  push    rdi
0x1800091a5  sub     rsp, 28h
0x1800091a9  lea     rsi, [rcx+0C8h]
0x1800091b0  mov     rdi, rcx
0x1800091b3  mov     rcx, rsi; lpCriticalSection
0x1800091b6  mov     rbp, r8
0x1800091b9  mov     ebx, edx
0x1800091bb  call    cs:__imp_EnterCriticalSection
0x1800091c1  cmp     ebx, 1
0x1800091c4  jnb     short loc_1800091F6
0x1800091c6  cmp     dword ptr [rdi+8], 0
0x1800091ca  jz      short loc_1800091EF
0x1800091cc  lea     rdx, [rdi+10h]; pmtSrc
0x1800091d0  mov     rcx, rbp; pmtDest
0x1800091d3  call    cs:__imp_MoCopyMediaType
0x1800091d9  mov     ebx, eax
0x1800091db  mov     rcx, rsi; lpCriticalSection
0x1800091de  call    cs:__imp_LeaveCriticalSection
0x1800091e4  mov     eax, ebx
0x1800091e6  add     rsp, 28h
0x1800091ea  pop     rdi
0x1800091eb  pop     rsi
0x1800091ec  pop     rbp
0x1800091ed  pop     rbx
0x1800091ee  retn
0x1800091ef  mov     ebx, 80040203h
0x1800091f4  jmp     short loc_1800091DB
0x1800091f6  mov     ebx, 80040201h
0x1800091fb  jmp     short loc_1800091DB
```
