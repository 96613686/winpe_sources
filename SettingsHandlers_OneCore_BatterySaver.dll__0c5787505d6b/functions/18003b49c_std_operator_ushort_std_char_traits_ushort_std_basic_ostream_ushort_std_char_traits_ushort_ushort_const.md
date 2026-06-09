# std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const *)

- ea: `0x18003b49c`
- end: `0x18003b5d9`
- name: `??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z`
- size: `317`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003c144`

## callees

- `0x18003b49c`
- `0x18003b938`
- `0x18003bb50`

## import_xrefs

- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18003b551`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18003b551`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003b527`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003b573`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003b527`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003b573`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003b5b7`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003b5b7`

## string_xrefs

- `0x18003b545`: `AdaptiveEnergySaverRegistry `

## pseudocode

```c
__int64 *__fastcall std::operator<<<unsigned short,std::char_traits<unsigned short>>(__int64 *a1)
{
  __int64 *v1; // rdi
  unsigned int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rax
  __int16 v7; // ax
  __int64 v8; // r8
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF

  v1 = a1;
  v2 = 0;
  v3 = *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40);
  if ( v3 < 29 )
    v4 = 0;
  else
    v4 = v3 - 28;
  std::basic_ostream<unsigned short>::sentry::sentry(v10, a1);
  if ( v10[8] )
  {
    v5 = *v1;
    v6 = *(int *)(*v1 + 4);
    if ( (*(_DWORD *)((_BYTE *)v1 + v6 + 24) & 0x1C0) != 0x40 )
    {
      while ( v4 > 0 )
      {
        try
        {
          v7 = std::basic_streambuf<unsigned short>::sputc(
                 *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 72),
                 *(unsigned __int16 *)((char *)v1 + *(int *)(*v1 + 4) + 88));
        }
        catch ( ... )
        {
          LOBYTE(v8) = 1;
          std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), 4, v8);
          v1 = a1;
          v2 = 0;
          goto LABEL_18;
        }
        if ( v7 == -1 )
          goto LABEL_15;
        --v4;
      }
      v5 = *v1;
    }
    if ( std::basic_streambuf<unsigned short>::sputn(
           *(__int64 *)((char *)v1 + *(int *)(v5 + 4) + 72),
           L"AdaptiveEnergySaverRegistry ",
           28) == 28 )
    {
      while ( v4 > 0 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 72),
                                 *(unsigned __int16 *)((char *)v1 + *(int *)(*v1 + 4) + 88)) == 0xFFFF )
          goto LABEL_15;
        --v4;
      }
    }
    else
    {
LABEL_15:
      v2 = 4;
    }
    *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 40) = 0;
  }
  else
  {
    v2 = 4;
  }
LABEL_18:
  std::basic_ios<unsigned short>::setstate((char *)v1 + *(int *)(*v1 + 4), v2, 0);
  std::basic_ostream<unsigned short>::sentry::~sentry(v10);
  return v1;
}

```

## disassembly

```asm
0x18003b49c  mov     [rsp+arg_10], rbx
0x18003b4a1  mov     [rsp+arg_8], rdx
0x18003b4a6  mov     [rsp+arg_0], rcx
0x18003b4ab  push    rsi
0x18003b4ac  push    rdi
0x18003b4ad  push    r14
0x18003b4af  sub     rsp, 30h
0x18003b4b3  mov     rdi, rcx
0x18003b4b6  xor     ebx, ebx
0x18003b4b8  mov     dword ptr [rsp+48h+arg_8], ebx
0x18003b4bc  mov     rax, [rcx]
0x18003b4bf  movsxd  rdx, dword ptr [rax+4]
0x18003b4c3  mov     rsi, [rdx+rcx+28h]
0x18003b4c8  cmp     rsi, 1Dh
0x18003b4cc  jl      short loc_18003B4D4
0x18003b4ce  add     rsi, 0FFFFFFFFFFFFFFE4h
0x18003b4d2  jmp     short loc_18003B4D6
0x18003b4d4  xor     esi, esi
0x18003b4d6  mov     rdx, rdi
0x18003b4d9  lea     rcx, [rsp+48h+var_28]
0x18003b4de  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x18003b4e3  nop
0x18003b4e4  cmp     [rsp+48h+var_20], 0
0x18003b4e9  jnz     short loc_18003B4F5
0x18003b4eb  mov     ebx, 4
0x18003b4f0  jmp     loc_18003B5A8
0x18003b4f5  mov     rdx, [rdi]
0x18003b4f8  movsxd  rax, dword ptr [rdx+4]
0x18003b4fc  mov     ecx, [rax+rdi+18h]
0x18003b500  and     ecx, 1C0h
0x18003b506  mov     r14d, 0FFFFh
0x18003b50c  cmp     ecx, 40h ; '@'
0x18003b50f  jz      short loc_18003B53B
0x18003b511  test    rsi, rsi
0x18003b514  jle     short loc_18003B538
0x18003b516  mov     rax, [rdi]
0x18003b519  movsxd  rcx, dword ptr [rax+4]
0x18003b51d  movzx   edx, word ptr [rcx+rdi+58h]
0x18003b522  mov     rcx, [rcx+rdi+48h]
0x18003b527  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18003b52d  cmp     r14w, ax
0x18003b531  jz      short loc_18003B57F
0x18003b533  dec     rsi
0x18003b536  jmp     short loc_18003B511
0x18003b538  mov     rdx, [rdi]
0x18003b53b  movsxd  rcx, dword ptr [rdx+4]
0x18003b53f  mov     r8d, 1Ch
0x18003b545  lea     rdx, aAdaptiveenergy; "AdaptiveEnergySaverRegistry "
0x18003b54c  mov     rcx, [rcx+rdi+48h]
0x18003b551  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x18003b557  cmp     rax, 1Ch
0x18003b55b  jnz     short loc_18003B57F
0x18003b55d  test    rsi, rsi
0x18003b560  jle     short loc_18003B588
0x18003b562  mov     rax, [rdi]
0x18003b565  movsxd  rcx, dword ptr [rax+4]
0x18003b569  movzx   edx, word ptr [rcx+rdi+58h]
0x18003b56e  mov     rcx, [rcx+rdi+48h]
0x18003b573  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18003b579  cmp     r14w, ax
0x18003b57d  jnz     short loc_18003B59A
0x18003b57f  mov     ebx, 4
0x18003b584  mov     dword ptr [rsp+48h+arg_8], ebx
0x18003b588  mov     rax, [rdi]
0x18003b58b  movsxd  rcx, dword ptr [rax+4]
0x18003b58f  mov     qword ptr [rcx+rdi+28h], 0
0x18003b598  jmp     short loc_18003B5A8
0x18003b59a  dec     rsi
0x18003b59d  jmp     short loc_18003B55D
0x18003b59f  mov     rdi, [rsp+48h+arg_0]
0x18003b5a4  mov     ebx, dword ptr [rsp+48h+arg_8]
0x18003b5a8  mov     rax, [rdi]
0x18003b5ab  movsxd  rcx, dword ptr [rax+4]
0x18003b5af  add     rcx, rdi
0x18003b5b2  xor     r8d, r8d
0x18003b5b5  mov     edx, ebx
0x18003b5b7  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18003b5bd  nop
0x18003b5be  lea     rcx, [rsp+48h+var_28]
0x18003b5c3  call    ??1sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@XZ; std::basic_ostream<ushort>::sentry::~sentry(void)
0x18003b5c8  mov     rax, rdi
0x18003b5cb  mov     rbx, [rsp+48h+arg_10]
0x18003b5d0  add     rsp, 30h
0x18003b5d4  pop     r14
0x18003b5d6  pop     rdi
0x18003b5d7  pop     rsi
0x18003b5d8  retn
```
