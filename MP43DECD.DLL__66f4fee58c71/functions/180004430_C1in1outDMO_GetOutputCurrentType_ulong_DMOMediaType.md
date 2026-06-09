# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180004430`
- end: `0x18000448d`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000447c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000447c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000444b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000444b`
- `msdmo!MoCopyMediaType` at `0x18000446a`
- `msdmo!MoCopyMediaType` at `0x18000446a`

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
0x180004430  push    rbx
0x180004432  push    rbp
0x180004433  push    rsi
0x180004434  push    rdi
0x180004435  sub     rsp, 28h
0x180004439  lea     rsi, [rcx+0C8h]
0x180004440  mov     rdi, rcx
0x180004443  mov     rcx, rsi; lpCriticalSection
0x180004446  mov     rbp, r8
0x180004449  mov     ebx, edx
0x18000444b  call    cs:__imp_EnterCriticalSection
0x180004451  cmp     ebx, 1
0x180004454  jb      short loc_18000445D
0x180004456  mov     ebx, 80040201h
0x18000445b  jmp     short loc_180004479
0x18000445d  cmp     dword ptr [rdi+0Ch], 0
0x180004461  jz      short loc_180004474
0x180004463  lea     rdx, [rdi+68h]; pmtSrc
0x180004467  mov     rcx, rbp; pmtDest
0x18000446a  call    cs:__imp_MoCopyMediaType
0x180004470  mov     ebx, eax
0x180004472  jmp     short loc_180004479
0x180004474  mov     ebx, 80040203h
0x180004479  mov     rcx, rsi; lpCriticalSection
0x18000447c  call    cs:__imp_LeaveCriticalSection
0x180004482  mov     eax, ebx
0x180004484  add     rsp, 28h
0x180004488  pop     rdi
0x180004489  pop     rsi
0x18000448a  pop     rbp
0x18000448b  pop     rbx
0x18000448c  retn
```
