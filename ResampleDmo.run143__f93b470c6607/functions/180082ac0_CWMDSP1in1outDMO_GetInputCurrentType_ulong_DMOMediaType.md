# CWMDSP1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180082ac0`
- end: `0x180082b1d`
- name: `?GetInputCurrentType@CWMDSP1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(CWMDSP1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180082ac0`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x180082afa`
- `msdmo!MoCopyMediaType` at `0x180082afa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082b0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082b0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082adb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082adb`

## pseudocode

```c
__int64 __fastcall CWMDSP1in1outDMO::GetInputCurrentType(CWMDSP1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
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
0x180082ac0  push    rbx
0x180082ac2  push    rbp
0x180082ac3  push    rsi
0x180082ac4  push    rdi
0x180082ac5  sub     rsp, 28h
0x180082ac9  lea     rsi, [rcx+0D0h]
0x180082ad0  mov     rdi, rcx
0x180082ad3  mov     rcx, rsi; lpCriticalSection
0x180082ad6  mov     rbp, r8
0x180082ad9  mov     ebx, edx
0x180082adb  call    cs:__imp_EnterCriticalSection
0x180082ae1  cmp     ebx, 1
0x180082ae4  jb      short loc_180082AED
0x180082ae6  mov     ebx, 80040201h
0x180082aeb  jmp     short loc_180082B09
0x180082aed  cmp     dword ptr [rdi+8], 0
0x180082af1  jz      short loc_180082B04
0x180082af3  lea     rdx, [rdi+10h]; pmtSrc
0x180082af7  mov     rcx, rbp; pmtDest
0x180082afa  call    cs:__imp_MoCopyMediaType
0x180082b00  mov     ebx, eax
0x180082b02  jmp     short loc_180082B09
0x180082b04  mov     ebx, 80040203h
0x180082b09  mov     rcx, rsi; lpCriticalSection
0x180082b0c  call    cs:__imp_LeaveCriticalSection
0x180082b12  mov     eax, ebx
0x180082b14  add     rsp, 28h
0x180082b18  pop     rdi
0x180082b19  pop     rsi
0x180082b1a  pop     rbp
0x180082b1b  pop     rbx
0x180082b1c  retn
```
