# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x18002c7f0`
- end: `0x18002c859`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `105`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002c7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c80b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c80b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c848`
- `msdmo!MoCopyMediaType` at `0x18002c83d`
- `msdmo!MoCopyMediaType` at `0x18002c83d`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetInputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
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
    if ( *((_DWORD *)this + 2) )
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 16));
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
0x18002c7f0  push    rbx
0x18002c7f2  push    rbp
0x18002c7f3  push    rsi
0x18002c7f4  push    rdi
0x18002c7f5  sub     rsp, 28h
0x18002c7f9  lea     rbp, [rcx+0D8h]
0x18002c800  mov     rdi, rcx
0x18002c803  mov     rcx, rbp; lpCriticalSection
0x18002c806  mov     rsi, r8
0x18002c809  mov     ebx, edx
0x18002c80b  call    cs:__imp_EnterCriticalSection
0x18002c811  cmp     ebx, 1
0x18002c814  jb      short loc_18002C81D
0x18002c816  mov     ebx, 80040201h
0x18002c81b  jmp     short loc_18002C845
0x18002c81d  test    rsi, rsi
0x18002c820  jnz     short loc_18002C829
0x18002c822  mov     ebx, 80004003h
0x18002c827  jmp     short loc_18002C845
0x18002c829  cmp     dword ptr [rdi+8], 0
0x18002c82d  jnz     short loc_18002C836
0x18002c82f  mov     ebx, 80040203h
0x18002c834  jmp     short loc_18002C845
0x18002c836  lea     rdx, [rdi+10h]; pmtSrc
0x18002c83a  mov     rcx, rsi; pmtDest
0x18002c83d  call    cs:__imp_MoCopyMediaType
0x18002c843  mov     ebx, eax
0x18002c845  mov     rcx, rbp; lpCriticalSection
0x18002c848  call    cs:__imp_LeaveCriticalSection
0x18002c84e  mov     eax, ebx
0x18002c850  add     rsp, 28h
0x18002c854  pop     rdi
0x18002c855  pop     rsi
0x18002c856  pop     rbp
0x18002c857  pop     rbx
0x18002c858  retn
```
