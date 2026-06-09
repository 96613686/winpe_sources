# Csl::OfflineHive::GetWideStringValueCommon(ushort const * const,ushort const * const,ulong,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong &)

- ea: `0x18002b814`
- end: `0x18002b99f`
- name: `?GetWideStringValueCommon@OfflineHive@Csl@@QEBAJQEBG0KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@AEAK@Z`
- size: `395`
- prototype: `int __fastcall(__int64, int, int, __int64, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002b5e0`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b4c`
- `0x18002b814`
- `0x18002dc24`

## string_xrefs

- `0x18002b87b`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b926`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002b97a`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
int __fastcall Csl::OfflineHive::GetWideStringValueCommon(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        void **a5,
        unsigned int *a6)
{
  unsigned int v9; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned __int64 v14; // rbx
  void *v15; // rax
  void *v16; // rdi
  unsigned int v17; // eax
  const struct std::nothrow_t *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  void *v20; // rcx
  unsigned int v21; // [rsp+20h] [rbp-38h]
  unsigned int v22; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v24; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v25; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v24 = 0;
  v9 = ORGetValue(*(_QWORD *)(a1 + 8), a2, a3, (unsigned int)&v24, 0, (__int64)&v25);
  if ( v9 == 2 )
    return -2147024894;
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x23D,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             (const char *)v9,
             v21);
  if ( v24 != 7 )
  {
    v11 = -2147023267;
    v12 = 575;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)v11,
      v21);
    return v11;
  }
  v13 = (v25 >> 1) + 2;
  v14 = 2LL * v13;
  if ( !is_mul_ok(v13, 2u) )
    v14 = -1;
  v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v11 = -2147024882;
    v12 = 587;
    goto LABEL_16;
  }
  memset_0(v15, 0, v14);
  v25 = 2 * v13;
  v17 = ORGetValue(*(_QWORD *)(a1 + 8), a2, a3, (unsigned int)&v24, (__int64)v16, (__int64)&v25);
  if ( v17 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x254,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v17,
            v22);
    operator delete(v16, v19);
    return v11;
  }
  v20 = *a5;
  *a5 = v16;
  if ( v20 )
    operator delete(v20, v18);
  *a6 = v25;
  return 0;
}

```

## disassembly

```asm
0x18002b814  mov     r11, rsp
0x18002b817  mov     [r11+10h], rbx
0x18002b81b  mov     [r11+20h], r9d
0x18002b81f  push    rbp
0x18002b820  push    rsi
0x18002b821  push    rdi
0x18002b822  push    r14
0x18002b824  push    r15
0x18002b826  sub     rsp, 30h
0x18002b82a  mov     rbp, r8
0x18002b82d  mov     r14, rdx
0x18002b830  mov     r15, rcx
0x18002b833  mov     [rsp+58h+arg_18], 0
0x18002b83b  mov     [rsp+58h+arg_0], 0
0x18002b843  lea     rax, [r11+20h]
0x18002b847  mov     [r11-30h], rax
0x18002b84b  mov     qword ptr [r11-38h], 0
0x18002b853  lea     r9, [r11+8]
0x18002b857  mov     rcx, [rcx+8]
0x18002b85b  call    ORGetValue
0x18002b860  cmp     eax, 2
0x18002b863  jnz     short loc_18002B86F
0x18002b865  mov     eax, 80070002h
0x18002b86a  jmp     loc_18002B98D
0x18002b86f  test    eax, eax
0x18002b871  jz      short loc_18002B891
0x18002b873  mov     rcx, [rsp+58h]; this
0x18002b878  mov     r9d, eax; char *
0x18002b87b  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b882  mov     edx, 23Dh; void *
0x18002b887  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b88c  jmp     loc_18002B98D
0x18002b891  cmp     [rsp+58h+arg_0], 7
0x18002b896  jz      short loc_18002B8A7
0x18002b898  mov     ebx, 8007065Dh
0x18002b89d  mov     edx, 23Fh
0x18002b8a2  jmp     loc_18002B977
0x18002b8a7  mov     esi, [rsp+58h+arg_18]
0x18002b8ab  shr     esi, 1
0x18002b8ad  add     esi, 2
0x18002b8b0  mov     ecx, esi
0x18002b8b2  mov     eax, 2
0x18002b8b7  mul     rcx
0x18002b8ba  mov     rbx, rax
0x18002b8bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002b8c4  cmovb   rbx, rax
0x18002b8c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b8cf  mov     rcx, rbx; unsigned __int64
0x18002b8d2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b8d7  mov     rdi, rax
0x18002b8da  test    rax, rax
0x18002b8dd  jz      loc_18002B96D
0x18002b8e3  mov     r8, rbx; Size
0x18002b8e6  xor     edx, edx; Val
0x18002b8e8  mov     rcx, rax; void *
0x18002b8eb  call    memset_0
0x18002b8f0  lea     ecx, [rsi+rsi]
0x18002b8f3  mov     [rsp+58h+arg_18], ecx
0x18002b8f7  lea     rax, [rsp+58h+arg_18]
0x18002b8fc  mov     [rsp+58h+var_30], rax
0x18002b901  mov     qword ptr [rsp+58h+var_38], rdi; unsigned int
0x18002b906  lea     r9, [rsp+58h+arg_0]
0x18002b90b  mov     r8, rbp
0x18002b90e  mov     rdx, r14
0x18002b911  mov     rcx, [r15+8]
0x18002b915  call    ORGetValue
0x18002b91a  test    eax, eax
0x18002b91c  jz      short loc_18002B943
0x18002b91e  mov     rcx, [rsp+58h]; this
0x18002b923  mov     r9d, eax; char *
0x18002b926  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b92d  mov     edx, 254h; void *
0x18002b932  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b937  mov     ebx, eax
0x18002b939  mov     rcx, rdi; void *
0x18002b93c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b941  jmp     short loc_18002B98B
0x18002b943  mov     rax, [rsp+58h+arg_20]
0x18002b94b  mov     rcx, [rax]; void *
0x18002b94e  mov     [rax], rdi
0x18002b951  test    rcx, rcx
0x18002b954  jz      short loc_18002B95B
0x18002b956  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b95b  mov     ecx, [rsp+58h+arg_18]
0x18002b95f  mov     rax, [rsp+58h+arg_28]
0x18002b967  mov     [rax], ecx
0x18002b969  xor     eax, eax
0x18002b96b  jmp     short loc_18002B98D
0x18002b96d  mov     ebx, 8007000Eh
0x18002b972  mov     edx, 24Bh; void *
0x18002b977  mov     r9d, ebx; char *
0x18002b97a  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002b981  mov     rcx, [rsp+58h]; this
0x18002b986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b98b  mov     eax, ebx
0x18002b98d  mov     rbx, [rsp+58h+arg_8]
0x18002b992  add     rsp, 30h
0x18002b996  pop     r15
0x18002b998  pop     r14
0x18002b99a  pop     rdi
0x18002b99b  pop     rsi
0x18002b99c  pop     rbp
0x18002b99d  retn
```
