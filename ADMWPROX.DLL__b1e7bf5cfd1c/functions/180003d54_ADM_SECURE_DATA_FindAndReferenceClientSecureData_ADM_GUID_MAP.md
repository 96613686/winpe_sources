# ADM_SECURE_DATA::FindAndReferenceClientSecureData(ADM_GUID_MAP *)

- ea: `0x180003d54`
- end: `0x180003dcf`
- name: `?FindAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAVADM_GUID_MAP@@@Z`
- size: `123`
- prototype: `struct ADM_SECURE_DATA *__fastcall(struct ADM_GUID_MAP *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000313c`
- `0x180003f60`

## callees

- `0x180003d54`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003d6a`
- `KERNEL32!EnterCriticalSection` at `0x180003d6a`
- `KERNEL32!LeaveCriticalSection` at `0x180003db5`
- `KERNEL32!LeaveCriticalSection` at `0x180003db5`

## pseudocode

```c
struct ADM_SECURE_DATA *__fastcall ADM_SECURE_DATA::FindAndReferenceClientSecureData(struct ADM_GUID_MAP *a1)
{
  ADM_SECURE_DATA *i; // rbx

  i = 0;
  EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  if ( a1 )
  {
    for ( i = ADM_SECURE_DATA::sm_ClientSecureDataListHead; ; i = *(ADM_SECURE_DATA **)i )
    {
      if ( i == (ADM_SECURE_DATA *)&ADM_SECURE_DATA::sm_ClientSecureDataListHead )
      {
        i = 0;
        goto LABEL_8;
      }
      if ( *(_QWORD *)((char *)i + 108) == *(_QWORD *)((char *)a1 + 76)
        && *(_QWORD *)((char *)i + 116) == _mm_srli_si128(*(__m128i *)((char *)a1 + 76), 8).m128i_u64[0] )
      {
        break;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)i + 6);
  }
LABEL_8:
  LeaveCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  return i;
}

```

## disassembly

```asm
0x180003d54  mov     [rsp+arg_0], rbx
0x180003d59  push    rdi
0x180003d5a  sub     rsp, 20h
0x180003d5e  mov     rdi, rcx
0x180003d61  xor     ebx, ebx
0x180003d63  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003d6a  call    cs:__imp_EnterCriticalSection
0x180003d70  test    rdi, rdi
0x180003d73  jz      short loc_180003DAE
0x180003d75  mov     rbx, cs:?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x180003d7c  lea     rcx, ?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x180003d83  jmp     short loc_180003DA7
0x180003d85  movups  xmm0, xmmword ptr [rdi+4Ch]
0x180003d89  movq    rax, xmm0
0x180003d8e  cmp     [rbx+6Ch], rax
0x180003d92  jnz     short loc_180003DA4
0x180003d94  psrldq  xmm0, 8
0x180003d99  movq    rax, xmm0
0x180003d9e  cmp     [rbx+74h], rax
0x180003da2  jz      short loc_180003DC9
0x180003da4  mov     rbx, [rbx]
0x180003da7  cmp     rbx, rcx
0x180003daa  jnz     short loc_180003D85
0x180003dac  xor     ebx, ebx
0x180003dae  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003db5  call    cs:__imp_LeaveCriticalSection
0x180003dbb  mov     rax, rbx
0x180003dbe  mov     rbx, [rsp+28h+arg_0]
0x180003dc3  add     rsp, 20h
0x180003dc7  pop     rdi
0x180003dc8  retn
0x180003dc9  lock inc dword ptr [rbx+18h]
0x180003dcd  jmp     short loc_180003DAE
```
