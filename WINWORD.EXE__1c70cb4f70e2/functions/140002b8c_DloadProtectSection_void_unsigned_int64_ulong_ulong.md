# DloadProtectSection(void *,unsigned __int64,ulong,ulong *)

- ea: `0x140002b8c`
- end: `0x140002c83`
- name: `?DloadProtectSection@@YAXPEAX_KKPEAK@Z`
- size: `247`
- prototype: `void __fastcall(void *lpAddress, SIZE_T dwSize, DWORD flNewProtect, PDWORD lpflOldProtect)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002810`
- `0x1400028fc`
- `0x140002c84`

## callees

- `0x140002a58`
- `0x140002af0`
- `0x140002b8c`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x140002c5a`
- `KERNEL32!VirtualProtect` at `0x140002c5a`

## pseudocode

```c
void __fastcall DloadProtectSection(char *lpAddress, SIZE_T dwSize, DWORD flNewProtect, PDWORD lpflOldProtect)
{
  char *v8; // rax
  char *v9; // rdi
  char *v10; // rax
  char *v11; // rcx
  unsigned int v12; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+24h] [rbp-24h] BYREF

  v8 = (char *)DloadObtainSection(&v12, (unsigned int *)&v13);
  v9 = v8;
  if ( !v8 )
  {
    *lpflOldProtect = 4;
    return;
  }
  if ( !DloadSectionCommitPermanent )
  {
    DloadSectionCommitPermanent = 1;
    if ( v13 >= 0 )
      __fastfail(0x19u);
    DloadMakePermanentImageCommit((unsigned __int64)v8, v12);
  }
  if ( lpAddress )
  {
    if ( dwSize )
    {
      v10 = &lpAddress[dwSize];
      v11 = &v9[v12];
      if ( v11 <= v9 || v10 <= lpAddress || lpAddress < v9 || v10 > v11 )
        __fastfail(0x19u);
      goto LABEL_18;
    }
LABEL_11:
    __fastfail(0x19u);
  }
  if ( dwSize )
    goto LABEL_11;
  dwSize = v12;
  lpAddress = v9;
LABEL_18:
  if ( !VirtualProtect(lpAddress, dwSize, flNewProtect, lpflOldProtect) )
    __fastfail(0x19u);
}

```

## disassembly

```asm
0x140002b8c  mov     rax, rsp
0x140002b8f  mov     [rax+8], rbx
0x140002b93  mov     [rax+10h], rsi
0x140002b97  mov     [rax+18h], rdi
0x140002b9b  push    r12
0x140002b9d  push    r14
0x140002b9f  push    r15
0x140002ba1  sub     rsp, 30h
0x140002ba5  mov     rsi, rdx
0x140002ba8  mov     rbx, rcx
0x140002bab  lea     rdx, [rax-24h]; unsigned int *
0x140002baf  mov     r14, r9
0x140002bb2  lea     rcx, [rax-28h]; unsigned int *
0x140002bb6  mov     r15d, r8d
0x140002bb9  call    ?DloadObtainSection@@YAPEAXPEAK0@Z; DloadObtainSection(ulong *,ulong *)
0x140002bbe  mov     rdi, rax
0x140002bc1  test    rax, rax
0x140002bc4  jnz     short loc_140002BD2
0x140002bc6  mov     dword ptr [r14], 4
0x140002bcd  jmp     loc_140002C69
0x140002bd2  cmp     cs:?DloadSectionCommitPermanent@@3KA, 0; ulong DloadSectionCommitPermanent
0x140002bd9  mov     r12d, 19h
0x140002bdf  jnz     short loc_140002C06
0x140002be1  test    dword ptr [rsp+48h+var_28+4], 80000000h
0x140002be9  mov     cs:?DloadSectionCommitPermanent@@3KA, 1; ulong DloadSectionCommitPermanent
0x140002bf3  jnz     short loc_140002BFA
0x140002bf5  mov     ecx, r12d
0x140002bf8  int     29h; Win8: RtlFailFast(ecx)
0x140002bfa  mov     edx, dword ptr [rsp+48h+var_28]; unsigned __int64
0x140002bfe  mov     rcx, rdi; void *
0x140002c01  call    ?DloadMakePermanentImageCommit@@YAXPEAX_K@Z; DloadMakePermanentImageCommit(void *,unsigned __int64)
0x140002c06  test    rbx, rbx
0x140002c09  jz      short loc_140002C12
0x140002c0b  test    rsi, rsi
0x140002c0e  jz      short loc_140002C17
0x140002c10  jmp     short loc_140002C21
0x140002c12  test    rsi, rsi
0x140002c15  jz      short loc_140002C47
0x140002c17  mov     rcx, r12
0x140002c1a  int     29h; Win8: RtlFailFast(ecx)
0x140002c1c  test    rbx, rbx
0x140002c1f  jz      short loc_140002C47
0x140002c21  mov     ecx, dword ptr [rsp+48h+var_28]
0x140002c25  lea     rax, [rbx+rsi]
0x140002c29  add     rcx, rdi
0x140002c2c  cmp     rcx, rdi
0x140002c2f  jbe     short loc_140002C40
0x140002c31  cmp     rax, rbx
0x140002c34  jbe     short loc_140002C40
0x140002c36  cmp     rbx, rdi
0x140002c39  jb      short loc_140002C40
0x140002c3b  cmp     rax, rcx
0x140002c3e  jbe     short loc_140002C4E
0x140002c40  mov     rcx, r12
0x140002c43  int     29h; Win8: RtlFailFast(ecx)
0x140002c45  jmp     short loc_140002C4E
0x140002c47  mov     esi, dword ptr [rsp+48h+var_28]
0x140002c4b  mov     rbx, rdi
0x140002c4e  mov     r9, r14; lpflOldProtect
0x140002c51  mov     r8d, r15d; flNewProtect
0x140002c54  mov     rdx, rsi; dwSize
0x140002c57  mov     rcx, rbx; lpAddress
0x140002c5a  call    cs:__imp_VirtualProtect
0x140002c60  test    eax, eax
0x140002c62  jnz     short loc_140002C69
0x140002c64  mov     rcx, r12
0x140002c67  int     29h; Win8: RtlFailFast(ecx)
0x140002c69  mov     rbx, [rsp+48h+arg_0]
0x140002c6e  mov     rsi, [rsp+48h+arg_8]
0x140002c73  mov     rdi, [rsp+48h+arg_10]
0x140002c78  add     rsp, 30h
0x140002c7c  pop     r15
0x140002c7e  pop     r14
0x140002c80  pop     r12
0x140002c82  retn
```
