# DloadProtectSection(void *,unsigned __int64,ulong,ulong *)

- ea: `0x140001f00`
- end: `0x140001ff7`
- name: `?DloadProtectSection@@YAXPEAX_KKPEAK@Z`
- size: `247`
- prototype: `void __fastcall(void *lpAddress, SIZE_T dwSize, DWORD flNewProtect, PDWORD lpflOldProtect)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000194c`
- `0x140001e10`
- `0x140002090`

## callees

- `0x1400014a0`
- `0x140001f00`
- `0x140001ff8`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x140001fce`
- `KERNEL32!VirtualProtect` at `0x140001fce`

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
0x140001f00  mov     rax, rsp
0x140001f03  mov     [rax+8], rbx
0x140001f07  mov     [rax+10h], rsi
0x140001f0b  mov     [rax+18h], rdi
0x140001f0f  push    r12
0x140001f11  push    r14
0x140001f13  push    r15
0x140001f15  sub     rsp, 30h
0x140001f19  mov     rsi, rdx
0x140001f1c  mov     rbx, rcx
0x140001f1f  lea     rdx, [rax-24h]; unsigned int *
0x140001f23  mov     r14, r9
0x140001f26  lea     rcx, [rax-28h]; unsigned int *
0x140001f2a  mov     r15d, r8d
0x140001f2d  call    ?DloadObtainSection@@YAPEAXPEAK0@Z; DloadObtainSection(ulong *,ulong *)
0x140001f32  mov     rdi, rax
0x140001f35  test    rax, rax
0x140001f38  jnz     short loc_140001F46
0x140001f3a  mov     dword ptr [r14], 4
0x140001f41  jmp     loc_140001FDD
0x140001f46  cmp     cs:?DloadSectionCommitPermanent@@3KA, 0; ulong DloadSectionCommitPermanent
0x140001f4d  mov     r12d, 19h
0x140001f53  jnz     short loc_140001F7A
0x140001f55  test    dword ptr [rsp+48h+var_28+4], 80000000h
0x140001f5d  mov     cs:?DloadSectionCommitPermanent@@3KA, 1; ulong DloadSectionCommitPermanent
0x140001f67  jnz     short loc_140001F6E
0x140001f69  mov     ecx, r12d
0x140001f6c  int     29h; Win8: RtlFailFast(ecx)
0x140001f6e  mov     edx, dword ptr [rsp+48h+var_28]; unsigned __int64
0x140001f72  mov     rcx, rdi; void *
0x140001f75  call    ?DloadMakePermanentImageCommit@@YAXPEAX_K@Z; DloadMakePermanentImageCommit(void *,unsigned __int64)
0x140001f7a  test    rbx, rbx
0x140001f7d  jz      short loc_140001F86
0x140001f7f  test    rsi, rsi
0x140001f82  jz      short loc_140001F8B
0x140001f84  jmp     short loc_140001F95
0x140001f86  test    rsi, rsi
0x140001f89  jz      short loc_140001FBB
0x140001f8b  mov     rcx, r12
0x140001f8e  int     29h; Win8: RtlFailFast(ecx)
0x140001f90  test    rbx, rbx
0x140001f93  jz      short loc_140001FBB
0x140001f95  mov     ecx, dword ptr [rsp+48h+var_28]
0x140001f99  lea     rax, [rbx+rsi]
0x140001f9d  add     rcx, rdi
0x140001fa0  cmp     rcx, rdi
0x140001fa3  jbe     short loc_140001FB4
0x140001fa5  cmp     rax, rbx
0x140001fa8  jbe     short loc_140001FB4
0x140001faa  cmp     rbx, rdi
0x140001fad  jb      short loc_140001FB4
0x140001faf  cmp     rax, rcx
0x140001fb2  jbe     short loc_140001FC2
0x140001fb4  mov     rcx, r12
0x140001fb7  int     29h; Win8: RtlFailFast(ecx)
0x140001fb9  jmp     short loc_140001FC2
0x140001fbb  mov     esi, dword ptr [rsp+48h+var_28]
0x140001fbf  mov     rbx, rdi
0x140001fc2  mov     r9, r14; lpflOldProtect
0x140001fc5  mov     r8d, r15d; flNewProtect
0x140001fc8  mov     rdx, rsi; dwSize
0x140001fcb  mov     rcx, rbx; lpAddress
0x140001fce  call    cs:__imp_VirtualProtect
0x140001fd4  test    eax, eax
0x140001fd6  jnz     short loc_140001FDD
0x140001fd8  mov     rcx, r12
0x140001fdb  int     29h; Win8: RtlFailFast(ecx)
0x140001fdd  mov     rbx, [rsp+48h+arg_0]
0x140001fe2  mov     rsi, [rsp+48h+arg_8]
0x140001fe7  mov     rdi, [rsp+48h+arg_10]
0x140001fec  add     rsp, 30h
0x140001ff0  pop     r15
0x140001ff2  pop     r14
0x140001ff4  pop     r12
0x140001ff6  retn
```
