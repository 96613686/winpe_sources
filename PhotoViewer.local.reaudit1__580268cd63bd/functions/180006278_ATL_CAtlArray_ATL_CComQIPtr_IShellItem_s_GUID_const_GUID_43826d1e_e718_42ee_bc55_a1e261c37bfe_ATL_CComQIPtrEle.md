# ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::GrowBuffer(unsigned __int64)

- ea: `0x180006278`
- end: `0x180006340`
- name: `?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f1c0`

## callees

- `0x1800046f8`
- `0x180006278`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180006311`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180006311`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800062b3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800062ee`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800062b3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800062ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006321`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006321`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
      if ( !v5 )
      {
        v5 = v4 >> 1;
        if ( a2 - v4 > v4 >> 1 )
          v5 = a2 - v4;
      }
      if ( a2 < v4 + v5 )
        a2 = v4 + v5;
      v7 = calloc(a2, 8u);
      v8 = v7;
      if ( !v7 )
        return 0;
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v10);
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 8u);
      *(_QWORD *)a1 = v6;
      if ( !v6 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180006278  mov     [rsp+arg_0], rbx
0x18000627d  mov     [rsp+arg_8], rsi
0x180006282  push    rdi
0x180006283  sub     rsp, 20h
0x180006287  mov     rdi, rdx
0x18000628a  mov     rbx, rcx
0x18000628d  mov     rdx, [rcx+10h]
0x180006291  cmp     rdi, rdx
0x180006294  jbe     loc_18000632E
0x18000629a  cmp     qword ptr [rbx], 0
0x18000629e  movsxd  rcx, dword ptr [rcx+18h]
0x1800062a2  jnz     short loc_1800062C3
0x1800062a4  cmp     rcx, rdi
0x1800062a7  mov     edx, 8; Size
0x1800062ac  cmova   rdi, rcx
0x1800062b0  mov     rcx, rdi; Count
0x1800062b3  call    cs:__imp_calloc
0x1800062b9  mov     [rbx], rax
0x1800062bc  test    rax, rax
0x1800062bf  jnz     short loc_18000632A
0x1800062c1  jmp     short loc_1800062FC
0x1800062c3  test    rcx, rcx
0x1800062c6  jnz     short loc_1800062DB
0x1800062c8  mov     rcx, rdx
0x1800062cb  mov     rax, rdi
0x1800062ce  shr     rcx, 1
0x1800062d1  sub     rax, rdx
0x1800062d4  cmp     rax, rcx
0x1800062d7  cmova   rcx, rax
0x1800062db  lea     rax, [rdx+rcx]
0x1800062df  mov     edx, 8; Size
0x1800062e4  cmp     rdi, rax
0x1800062e7  cmovb   rdi, rax
0x1800062eb  mov     rcx, rdi; Count
0x1800062ee  call    cs:__imp_calloc
0x1800062f4  mov     rsi, rax
0x1800062f7  test    rax, rax
0x1800062fa  jnz     short loc_180006300
0x1800062fc  xor     al, al
0x1800062fe  jmp     short loc_180006330
0x180006300  mov     rdx, [rbx+8]
0x180006304  mov     rcx, rsi; Destination
0x180006307  mov     r8, [rbx]; Source
0x18000630a  shl     rdx, 3; DestinationSize
0x18000630e  mov     r9, rdx; SourceSize
0x180006311  call    cs:__imp_memmove_s
0x180006317  mov     ecx, eax; int
0x180006319  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000631e  mov     rcx, [rbx]; Block
0x180006321  call    cs:__imp_free
0x180006327  mov     [rbx], rsi
0x18000632a  mov     [rbx+10h], rdi
0x18000632e  mov     al, 1
0x180006330  mov     rbx, [rsp+28h+arg_0]
0x180006335  mov     rsi, [rsp+28h+arg_8]
0x18000633a  add     rsp, 20h
0x18000633e  pop     rdi
0x18000633f  retn
```
