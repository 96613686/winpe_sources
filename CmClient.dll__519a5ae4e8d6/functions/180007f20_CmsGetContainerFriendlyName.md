# CmsGetContainerFriendlyName

- ea: `0x180007f20`
- end: `0x180008036`
- name: `CmsGetContainerFriendlyName`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a170`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180007f20`
- `0x18000db50`
- `0x18000ee00`

## string_xrefs

- `0x180007f8d`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008008`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsGetContainerFriendlyName(__int64 a1, void *a2, unsigned int a3, unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  void *v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // eax
  int v13[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v14[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *Src; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 || a3 && !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x80070057LL,
      v13[0]);
    return v8;
  }
  Src = 0;
  *(_QWORD *)v13 = &Src;
  v14[0] = *(_QWORD *)(a1 + 24);
  v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_GetContainerFriendlyName,
         v14,
         v13);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v13[0]);
    if ( Src )
      MIDL_user_free(Src);
    return v8;
  }
  v9 = Src;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)Src + v10) );
  v11 = v10 + 1;
  *a4 = v11;
  if ( a3 >= v11 )
  {
    memcpy_0(a2, v9, 2LL * v11);
    if ( v9 )
      MIDL_user_free(v9);
    return 0;
  }
  else
  {
    if ( v9 )
      MIDL_user_free(v9);
    return 2147942522LL;
  }
}

```

## disassembly

```asm
0x180007f20  mov     [rsp+arg_0], rbx
0x180007f25  mov     [rsp+arg_8], rbp
0x180007f2a  push    rsi
0x180007f2b  push    rdi
0x180007f2c  push    r14
0x180007f2e  sub     rsp, 30h
0x180007f32  xor     ebp, ebp
0x180007f34  mov     r14, r9
0x180007f37  mov     edi, r8d
0x180007f3a  mov     rsi, rdx
0x180007f3d  test    r9, r9
0x180007f40  jz      loc_180008003
0x180007f46  test    r8d, r8d
0x180007f49  jz      short loc_180007F54
0x180007f4b  test    rdx, rdx
0x180007f4e  jz      loc_180008003
0x180007f54  lea     rax, [rsp+48h+Src]
0x180007f59  mov     [rsp+48h+Src], rbp
0x180007f5e  mov     qword ptr [rsp+48h+var_28], rax; int
0x180007f63  lea     r8, [rsp+48h+var_28]
0x180007f68  mov     rax, [rcx+18h]
0x180007f6c  lea     rdx, [rsp+48h+var_20]
0x180007f71  lea     rcx, CmsRpcClt_GetContainerFriendlyName
0x180007f78  mov     [rsp+48h+var_20], rax
0x180007f7d  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180007f82  mov     ebx, eax
0x180007f84  test    eax, eax
0x180007f86  jns     short loc_180007FB2
0x180007f88  mov     rcx, [rsp+48h]; this
0x180007f8d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007f94  mov     r9d, eax; char *
0x180007f97  mov     edx, 1C4h; void *
0x180007f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fa1  mov     rcx, [rsp+48h+Src]; void *
0x180007fa6  test    rcx, rcx
0x180007fa9  jz      short loc_180008021
0x180007fab  call    MIDL_user_free
0x180007fb0  jmp     short loc_180008021
0x180007fb2  mov     rbx, [rsp+48h+Src]
0x180007fb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007fbb  inc     rax
0x180007fbe  cmp     [rbx+rax*2], bp
0x180007fc2  jnz     short loc_180007FBB
0x180007fc4  inc     eax
0x180007fc6  mov     [r14], eax
0x180007fc9  cmp     edi, eax
0x180007fcb  jnb     short loc_180007FE1
0x180007fcd  test    rbx, rbx
0x180007fd0  jz      short loc_180007FDA
0x180007fd2  mov     rcx, rbx; void *
0x180007fd5  call    MIDL_user_free
0x180007fda  mov     eax, 8007007Ah
0x180007fdf  jmp     short loc_180008023
0x180007fe1  mov     r8d, eax
0x180007fe4  mov     rdx, rbx; Src
0x180007fe7  add     r8, r8; Size
0x180007fea  mov     rcx, rsi; void *
0x180007fed  call    memcpy_0
0x180007ff2  test    rbx, rbx
0x180007ff5  jz      short loc_180007FFF
0x180007ff7  mov     rcx, rbx; void *
0x180007ffa  call    MIDL_user_free
0x180007fff  xor     eax, eax
0x180008001  jmp     short loc_180008023
0x180008003  mov     rcx, [rsp+48h]; this
0x180008008  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000800f  mov     ebx, 80070057h
0x180008014  mov     edx, 1B8h; void *
0x180008019  mov     r9d, ebx; char *
0x18000801c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008021  mov     eax, ebx
0x180008023  mov     rbx, [rsp+48h+arg_0]
0x180008028  mov     rbp, [rsp+48h+arg_8]
0x18000802d  add     rsp, 30h
0x180008031  pop     r14
0x180008033  pop     rdi
0x180008034  pop     rsi
0x180008035  retn
```
