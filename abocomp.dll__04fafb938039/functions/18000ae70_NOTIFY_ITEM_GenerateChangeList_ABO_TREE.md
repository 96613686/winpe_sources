# NOTIFY_ITEM::GenerateChangeList(ABO_TREE *)

- ea: `0x18000ae70`
- end: `0x18000b0ab`
- name: `?GenerateChangeList@NOTIFY_ITEM@@QEAAJPEAVABO_TREE@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(NOTIFY_ITEM *__hidden this, struct ABO_TREE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000e99c`

## callees

- `0x180002990`
- `0x1800029d0`
- `0x180003402`
- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x180007ac8`
- `0x18000ae70`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000aee5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000aee5`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18000af91`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18000af91`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000af60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000afb7`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000af60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000afb7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b005`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b005`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000aed3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000aed3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b079`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b079`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af0c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af9e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af0c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af9e`

## pseudocode

```c
__int64 __fastcall NOTIFY_ITEM::GenerateChangeList(NOTIFY_ITEM *this, struct ABO_TREE *a2)
{
  int v3; // edi
  ABO_NODE *v4; // rbx
  const unsigned __int16 *Str; // rax
  ABO_NODE *v7[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v8[64]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v9[256]; // [rsp+70h] [rbp-90h] BYREF

  v7[1] = this;
  v7[0] = 0;
  memset_0(v9, 0, sizeof(v9));
  STRU::STRU((STRU *)v8, v9, 0x100u);
  v3 = STRU::Copy((STRU *)v8, L"/LM/W3SVC");
  if ( v3 >= 0 && a2 )
  {
    v4 = (ABO_NODE *)*((_QWORD *)a2 + 2);
    Str = STRU::QueryStr((STRU *)v8);
    ABO_NODE::FindNode(v4, Str, v7);
  }
  STRU::~STRU((STRU *)v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ae70  mov     [rsp-8+arg_10], rbx
0x18000ae75  push    rbp
0x18000ae76  push    rsi
0x18000ae77  push    rdi
0x18000ae78  push    r12
0x18000ae7a  push    r13
0x18000ae7c  push    r14
0x18000ae7e  push    r15
0x18000ae80  lea     rbp, [rsp-180h]
0x18000ae88  sub     rsp, 280h
0x18000ae8f  mov     rax, cs:__security_cookie
0x18000ae96  xor     rax, rsp
0x18000ae99  mov     [rbp+1B0h+var_40], rax
0x18000aea0  mov     rbx, rdx
0x18000aea3  mov     [rsp+2B0h+var_288], rcx
0x18000aea8  xor     edx, edx; Val
0x18000aeaa  mov     [rsp+2B0h+var_290], 0
0x18000aeb3  lea     rcx, [rsp+2B0h+var_240]; void *
0x18000aeb8  mov     r8d, 200h; Size
0x18000aebe  call    memset_0
0x18000aec3  mov     r8d, 100h
0x18000aec9  lea     rdx, [rsp+2B0h+var_240]
0x18000aece  lea     rcx, [rsp+2B0h+var_280]
0x18000aed3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000aed9  lea     rdx, aLmW3svc_0; "/LM/W3SVC"
0x18000aee0  lea     rcx, [rsp+2B0h+var_280]
0x18000aee5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000aeeb  mov     edi, eax
0x18000aeed  test    eax, eax
0x18000aeef  js      loc_18000B074
0x18000aef5  test    rbx, rbx
0x18000aef8  jz      loc_18000B074
0x18000aefe  mov     rbx, [rbx+10h]
0x18000af02  lea     rcx, [rsp+2B0h+var_280]
0x18000af07  xor     esi, esi
0x18000af09  xor     r14d, r14d
0x18000af0c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000af12  lea     r8, [rsp+2B0h+var_290]; struct ABO_NODE **
0x18000af17  mov     rcx, rbx; this
0x18000af1a  mov     rdx, rax; unsigned __int16 *
0x18000af1d  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000af22  mov     r15, [rsp+2B0h+var_290]
0x18000af27  mov     edi, eax
0x18000af29  test    eax, eax
0x18000af2b  js      loc_18000B04D
0x18000af31  mov     r12d, [r15+0C8h]
0x18000af38  test    r12d, r12d
0x18000af3b  jz      loc_18000B04D
0x18000af41  lea     ecx, [rsi+18h]; Size
0x18000af44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af49  mov     rsi, rax
0x18000af4c  test    rax, rax
0x18000af4f  jnz     short loc_18000AF5B
0x18000af51  mov     edi, 80070008h
0x18000af56  jmp     loc_18000B04D
0x18000af5b  lea     rcx, [rsp+2B0h+var_280]
0x18000af60  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000af66  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000af6d  lea     ecx, [rax+1]
0x18000af70  mov     eax, 2
0x18000af75  mul     rcx
0x18000af78  cmovb   rax, r13
0x18000af7c  mov     rcx, rax; Size
0x18000af7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af84  mov     r14, rax
0x18000af87  test    rax, rax
0x18000af8a  jz      short loc_18000AF51
0x18000af8c  lea     rcx, [rsp+2B0h+var_280]
0x18000af91  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18000af97  lea     rcx, [rsp+2B0h+var_280]
0x18000af9c  mov     ebx, eax
0x18000af9e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000afa4  mov     r8d, ebx; Size
0x18000afa7  mov     rcx, r14; void *
0x18000afaa  mov     rdx, rax; Src
0x18000afad  call    memcpy_0
0x18000afb2  lea     rcx, [rsp+2B0h+var_280]
0x18000afb7  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000afbd  mov     ecx, eax
0x18000afbf  xor     eax, eax
0x18000afc1  mov     [r14+rcx*2], ax
0x18000afc6  lea     eax, [r13+5]
0x18000afca  mul     r12
0x18000afcd  cmovb   rax, r13
0x18000afd1  mov     rcx, rax; Size
0x18000afd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000afd9  mov     [rsp+2B0h+var_290], rax
0x18000afde  test    rax, rax
0x18000afe1  jz      loc_18000AF51
0x18000afe7  xor     r13d, r13d
0x18000afea  xor     ebx, ebx
0x18000afec  test    r12d, r12d
0x18000afef  jz      short loc_18000B027
0x18000aff1  cmp     ebx, 64h ; 'd'
0x18000aff4  jge     short loc_18000B022
0x18000aff6  mov     rax, [r15+0C0h]
0x18000affd  mov     rcx, [rax+rbx*8]
0x18000b001  add     rcx, 10h
0x18000b005  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b00b  mov     rdx, [rsp+2B0h+var_290]
0x18000b010  inc     r13d
0x18000b013  movsxd  rcx, ebx
0x18000b016  inc     ebx
0x18000b018  mov     eax, [rax]
0x18000b01a  mov     [rdx+rcx*4], eax
0x18000b01d  cmp     ebx, r12d
0x18000b020  jb      short loc_18000AFF1
0x18000b022  mov     rax, [rsp+2B0h+var_290]
0x18000b027  mov     [rsi+10h], rax
0x18000b02b  mov     rax, [rsp+2B0h+var_288]
0x18000b030  mov     [rsi], r14
0x18000b033  mov     dword ptr [rsi+8], 10h
0x18000b03a  mov     [rsi+0Ch], r13d
0x18000b03e  mov     [rax+8], rsi
0x18000b042  xor     esi, esi
0x18000b044  xor     r14d, r14d
0x18000b047  mov     dword ptr [rax], 1
0x18000b04d  test    r15, r15
0x18000b050  jz      short loc_18000B05A
0x18000b052  mov     rcx, r15; this
0x18000b055  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000b05a  test    r14, r14
0x18000b05d  jz      short loc_18000B067
0x18000b05f  mov     rcx, r14; Block
0x18000b062  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b067  test    rsi, rsi
0x18000b06a  jz      short loc_18000B074
0x18000b06c  mov     rcx, rsi; Block
0x18000b06f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b074  lea     rcx, [rsp+2B0h+var_280]
0x18000b079  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b07f  mov     eax, edi
0x18000b081  mov     rcx, [rbp+1B0h+var_40]
0x18000b088  xor     rcx, rsp; StackCookie
0x18000b08b  call    __security_check_cookie
0x18000b090  mov     rbx, [rsp+2B0h+arg_10]
0x18000b098  add     rsp, 280h
0x18000b09f  pop     r15
0x18000b0a1  pop     r14
0x18000b0a3  pop     r13
0x18000b0a5  pop     r12
0x18000b0a7  pop     rdi
0x18000b0a8  pop     rsi
0x18000b0a9  pop     rbp
0x18000b0aa  retn
```
