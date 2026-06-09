# GetPersistentRegPathFromSourceId(wchar_t const *,wchar_t const *,ulong *,wchar_t *)

- ea: `0x1800044d0`
- end: `0x1800045f8`
- name: `?GetPersistentRegPathFromSourceId@@YAKPEB_W0PEAKPEA_W@Z`
- size: `296`
- prototype: `unsigned int __fastcall(const wchar_t *, const wchar_t *, unsigned int *, wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800043fc`

## callees

- `0x1800044d0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800045ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800045ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800045e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800045e2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180004510`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180004510`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathFromSourceId(
        const wchar_t *a1,
        const wchar_t *a2,
        unsigned int *a3,
        wchar_t *a4)
{
  unsigned int PersistedRegistryLocationW; // r12d
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  unsigned __int64 v10; // rbx
  unsigned __int64 i; // rbp
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned int v15; // [rsp+30h] [rbp-58h] BYREF

  v15 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, a4, 2 * *a3, &v15);
  v8 = (unsigned __int64)v15 >> 1;
  if ( !PersistedRegistryLocationW && a2 )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    for ( i = 0; i < v10; ++i )
    {
      if ( !(unsigned int)_o__wcsnicmp(&a4[i], a2, v10 - i) )
        break;
    }
    v12 = v10 - i;
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      if ( v12 < v13 )
      {
        do
          ++v9;
        while ( a2[v12 + v9] );
        v8 += v9;
        if ( *a3 < v8 )
          PersistedRegistryLocationW = 234;
        else
          PersistedRegistryLocationW = _o_wcscat_s(a4, v8);
      }
    }
  }
  *a3 = v8;
  return PersistedRegistryLocationW;
}

```

## disassembly

```asm
0x1800044d0  push    rsi
0x1800044d2  push    rdi
0x1800044d3  push    r12
0x1800044d5  push    r13
0x1800044d7  push    r15
0x1800044d9  sub     rsp, 60h
0x1800044dd  mov     rax, cs:__security_cookie
0x1800044e4  xor     rax, rsp
0x1800044e7  mov     [rsp+88h+var_50], rax
0x1800044ec  mov     rsi, r9
0x1800044ef  mov     [rsp+88h+var_58], 0
0x1800044f7  mov     r9d, [r8]
0x1800044fa  lea     rax, [rsp+88h+var_58]
0x1800044ff  mov     r13, r8
0x180004502  mov     [rsp+88h+var_68], rax
0x180004507  add     r9d, r9d
0x18000450a  mov     r8, rsi
0x18000450d  mov     rdi, rdx
0x180004510  call    cs:__imp_GetPersistedRegistryLocationW
0x180004516  mov     r15d, [rsp+88h+var_58]
0x18000451b  mov     r12d, eax
0x18000451e  shr     r15, 1
0x180004521  test    eax, eax
0x180004523  jnz     short loc_18000457A
0x180004525  test    rdi, rdi
0x180004528  jz      short loc_18000457A
0x18000452a  mov     [rsp+88h+var_30], rbx
0x18000452f  mov     [rsp+88h+var_38], rbp
0x180004534  mov     [rsp+88h+var_40], r14
0x180004539  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180004540  mov     rbx, r14
0x180004543  inc     rbx
0x180004546  cmp     word ptr [rsi+rbx*2], 0
0x18000454b  jnz     short loc_180004543
0x18000454d  xor     ebp, ebp
0x18000454f  test    rbx, rbx
0x180004552  jnz     short loc_1800045A0
0x180004554  sub     rbx, rbp
0x180004557  mov     rbp, [rsp+88h+var_38]
0x18000455c  jz      short loc_180004570
0x18000455e  mov     rax, r14
0x180004561  inc     rax
0x180004564  cmp     word ptr [rdi+rax*2], 0
0x180004569  jnz     short loc_180004561
0x18000456b  cmp     rbx, rax
0x18000456e  jb      short loc_1800045C1
0x180004570  mov     rbx, [rsp+88h+var_30]
0x180004575  mov     r14, [rsp+88h+var_40]
0x18000457a  mov     [r13+0], r15d
0x18000457e  mov     eax, r12d
0x180004581  mov     rcx, [rsp+88h+var_50]
0x180004586  xor     rcx, rsp; StackCookie
0x180004589  call    __security_check_cookie
0x18000458e  add     rsp, 60h
0x180004592  pop     r15
0x180004594  pop     r13
0x180004596  pop     r12
0x180004598  pop     rdi
0x180004599  pop     rsi
0x18000459a  retn
0x1800045a0  mov     r8, rbx
0x1800045a3  lea     rcx, [rsi+rbp*2]
0x1800045a7  sub     r8, rbp
0x1800045aa  mov     rdx, rdi
0x1800045ad  call    cs:__imp__o__wcsnicmp
0x1800045b3  test    eax, eax
0x1800045b5  jz      short loc_180004554
0x1800045b7  inc     rbp
0x1800045ba  cmp     rbp, rbx
0x1800045bd  jb      short loc_1800045A0
0x1800045bf  jmp     short loc_180004554
0x1800045c1  lea     r8, [rdi+rbx*2]
0x1800045c5  inc     r14
0x1800045c8  cmp     word ptr [r8+r14*2], 0
0x1800045ce  jnz     short loc_1800045C5
0x1800045d0  mov     eax, [r13+0]
0x1800045d4  add     r15, r14
0x1800045d7  cmp     rax, r15
0x1800045da  jb      short loc_1800045ED
0x1800045dc  mov     rdx, r15
0x1800045df  mov     rcx, rsi
0x1800045e2  call    cs:__imp__o_wcscat_s
0x1800045e8  mov     r12d, eax
0x1800045eb  jmp     short loc_180004570
0x1800045ed  mov     r12d, 0EAh
0x1800045f3  jmp     loc_180004570
```
