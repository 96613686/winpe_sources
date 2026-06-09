# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180008840`
- end: `0x18000889d`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008840`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x180008873`
- `msdmo!MoCopyMediaType` at `0x180008873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000887e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000887e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000885b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000885b`

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
0x180008840  push    rbx
0x180008842  push    rbp
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  sub     rsp, 28h
0x180008849  lea     rsi, [rcx+0C8h]
0x180008850  mov     rdi, rcx
0x180008853  mov     rcx, rsi; lpCriticalSection
0x180008856  mov     rbp, r8
0x180008859  mov     ebx, edx
0x18000885b  call    cs:__imp_EnterCriticalSection
0x180008861  cmp     ebx, 1
0x180008864  jnb     short loc_18000888F
0x180008866  cmp     dword ptr [rdi+0Ch], 0
0x18000886a  jz      short loc_180008896
0x18000886c  lea     rdx, [rdi+68h]; pmtSrc
0x180008870  mov     rcx, rbp; pmtDest
0x180008873  call    cs:__imp_MoCopyMediaType
0x180008879  mov     ebx, eax
0x18000887b  mov     rcx, rsi; lpCriticalSection
0x18000887e  call    cs:__imp_LeaveCriticalSection
0x180008884  mov     eax, ebx
0x180008886  add     rsp, 28h
0x18000888a  pop     rdi
0x18000888b  pop     rsi
0x18000888c  pop     rbp
0x18000888d  pop     rbx
0x18000888e  retn
0x18000888f  mov     ebx, 80040201h
0x180008894  jmp     short loc_18000887B
0x180008896  mov     ebx, 80040203h
0x18000889b  jmp     short loc_18000887B
```
