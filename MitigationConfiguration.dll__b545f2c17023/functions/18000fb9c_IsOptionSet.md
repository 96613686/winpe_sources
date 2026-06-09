# IsOptionSet

- ea: `0x18000fb9c`
- end: `0x18000fc7e`
- name: `IsOptionSet`
- size: `226`
- prototype: `__int64 __fastcall(__int64 *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a5f0`

## callees

- `0x180005db4`
- `0x18000fb9c`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fbff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fc29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fc53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fbff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fc29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fc53`

## string_xrefs

- `0x18000fbdb`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall IsOptionSet(__int64 *a1, _BYTE *a2, _BYTE *a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // esi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v3 + 128))(a1, &v10, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v6);
    return v7;
  }
  if ( !(unsigned int)_o__wcsicmp(v10, L"true") )
  {
    if ( a2 )
    {
      *a2 = 2;
    }
    else if ( a3 )
    {
      *a3 = 1;
    }
    return 0;
  }
  if ( (unsigned int)_o__wcsicmp(v10, L"false") )
  {
    if ( (unsigned int)_o__wcsicmp(v10, L"notset") )
    {
      if ( !a2 )
        return 0;
    }
    else if ( !a2 )
    {
LABEL_11:
      if ( a3 )
        *a3 = 0;
      return 0;
    }
    *a2 = 1;
    return 0;
  }
  if ( !a2 )
    goto LABEL_11;
  *a2 = 4;
  return 0;
}

```

## disassembly

```asm
0x18000fb9c  mov     r11, rsp
0x18000fb9f  mov     [r11+10h], rbx
0x18000fba3  mov     [r11+18h], rsi
0x18000fba7  push    rdi; int
0x18000fba8  sub     rsp, 20h
0x18000fbac  mov     rax, [rcx]
0x18000fbaf  mov     rdi, r8
0x18000fbb2  mov     rbx, rdx
0x18000fbb5  mov     qword ptr [r11+8], 0
0x18000fbbd  xor     r8d, r8d
0x18000fbc0  lea     rdx, [r11+8]
0x18000fbc4  mov     rax, [rax+80h]
0x18000fbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbd0  mov     esi, eax
0x18000fbd2  test    eax, eax
0x18000fbd4  jns     short loc_18000FBF3
0x18000fbd6  mov     rcx, [rsp+28h]; this
0x18000fbdb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000fbe2  mov     r9d, eax; char *
0x18000fbe5  mov     edx, 0C3h; void *
0x18000fbea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fbef  mov     eax, esi
0x18000fbf1  jmp     short loc_18000FC6E
0x18000fbf3  mov     rcx, [rsp+28h+arg_0]
0x18000fbf8  lea     rdx, aTrue; "true"
0x18000fbff  call    cs:__imp__o__wcsicmp
0x18000fc05  test    eax, eax
0x18000fc07  jnz     short loc_18000FC1D
0x18000fc09  test    rbx, rbx
0x18000fc0c  jz      short loc_18000FC13
0x18000fc0e  mov     byte ptr [rbx], 2
0x18000fc11  jmp     short loc_18000FC6C
0x18000fc13  test    rdi, rdi
0x18000fc16  jz      short loc_18000FC6C
0x18000fc18  mov     byte ptr [rdi], 1
0x18000fc1b  jmp     short loc_18000FC6C
0x18000fc1d  mov     rcx, [rsp+28h+arg_0]
0x18000fc22  lea     rdx, aFalse; "false"
0x18000fc29  call    cs:__imp__o__wcsicmp
0x18000fc2f  test    eax, eax
0x18000fc31  jnz     short loc_18000FC47
0x18000fc33  test    rbx, rbx
0x18000fc36  jz      short loc_18000FC3D
0x18000fc38  mov     byte ptr [rbx], 4
0x18000fc3b  jmp     short loc_18000FC6C
0x18000fc3d  test    rdi, rdi
0x18000fc40  jz      short loc_18000FC6C
0x18000fc42  mov     byte ptr [rdi], 0
0x18000fc45  jmp     short loc_18000FC6C
0x18000fc47  mov     rcx, [rsp+28h+arg_0]
0x18000fc4c  lea     rdx, aNotset; "notset"
0x18000fc53  call    cs:__imp__o__wcsicmp
0x18000fc59  test    eax, eax
0x18000fc5b  jnz     short loc_18000FC64
0x18000fc5d  test    rbx, rbx
0x18000fc60  jnz     short loc_18000FC69
0x18000fc62  jmp     short loc_18000FC3D
0x18000fc64  test    rbx, rbx
0x18000fc67  jz      short loc_18000FC6C
0x18000fc69  mov     byte ptr [rbx], 1
0x18000fc6c  xor     eax, eax
0x18000fc6e  mov     rbx, [rsp+28h+arg_8]
0x18000fc73  mov     rsi, [rsp+28h+arg_10]
0x18000fc78  add     rsp, 20h
0x18000fc7c  pop     rdi
0x18000fc7d  retn
```
