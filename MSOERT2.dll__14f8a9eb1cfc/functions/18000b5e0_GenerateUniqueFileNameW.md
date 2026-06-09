# GenerateUniqueFileNameW

- ea: `0x18000b5e0`
- end: `0x18000b75f`
- name: `GenerateUniqueFileNameW`
- size: `383`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ab80`
- `0x18000b390`

## callees

- `0x180004640`
- `0x1800092d4`
- `0x180009378`
- `0x18000a220`
- `0x18000b5e0`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18000b6fc`
- `RPCRT4!RpcStringFreeW` at `0x18000b6fc`
- `RPCRT4!UuidToStringW` at `0x18000b6ad`
- `RPCRT4!UuidToStringW` at `0x18000b6ad`
- `RPCRT4!UuidCreate` at `0x18000b690`
- `RPCRT4!UuidCreate` at `0x18000b690`

## pseudocode

```c
__int64 __fastcall GenerateUniqueFileNameW(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  int UniqueFileName; // eax
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rax
  unsigned __int16 *v14; // r8
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp-C0h]
  UUID Uuid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v20[264]; // [rsp+70h] [rbp-90h] BYREF

  STRW::STRW((STRW *)&v17, v20, 0x104u);
  UniqueFileName = _GenerateUniqueFileName(a1, a2, a3, a4, (struct STRW *)&v17);
  v11 = v17;
  v12 = UniqueFileName;
  if ( UniqueFileName < 0 || (unsigned int)a6 <= v17 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    if ( (int)v13 + 1 > 39 )
    {
      Uuid = 0;
      if ( UuidCreate(&Uuid) || (StringUuid = 0, UuidToStringW(&Uuid, &StringUuid)) )
      {
        v12 = -2147024882;
        goto LABEL_14;
      }
      memset_0(v18, 0, 2 * v11);
      v17 = 0;
      v12 = _GenerateUniqueFileName(a1, StringUuid, a3, a4, (struct STRW *)&v17);
      RpcStringFreeW(&StringUuid);
      LODWORD(v11) = v17;
    }
    if ( v12 < 0 )
      goto LABEL_14;
  }
  v14 = (unsigned __int16 *)&ExistingFileName;
  if ( (_DWORD)v11 )
    v14 = v18;
  v12 = StringCchCopyW(a5, (unsigned int)a6, v14);
LABEL_14:
  STRW::~STRW((STRW *)&v17);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b5e0  mov     [rsp-8+arg_18], rbx
0x18000b5e5  push    rbp
0x18000b5e6  push    rsi
0x18000b5e7  push    rdi
0x18000b5e8  push    r12
0x18000b5ea  push    r13
0x18000b5ec  push    r14
0x18000b5ee  push    r15
0x18000b5f0  lea     rbp, [rsp-190h]
0x18000b5f8  sub     rsp, 290h
0x18000b5ff  mov     rax, cs:__security_cookie
0x18000b606  xor     rax, rsp
0x18000b609  mov     [rbp+1C0h+var_40], rax
0x18000b610  mov     r14, [rbp+1C0h+arg_20]
0x18000b617  mov     r13, r8
0x18000b61a  mov     r12, rcx
0x18000b61d  mov     rsi, rdx
0x18000b620  mov     r8d, 104h; unsigned int
0x18000b626  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18000b62b  lea     rcx, [rsp+2C0h+var_288]; this
0x18000b630  mov     r15d, r9d
0x18000b633  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000b638  lea     rdx, [rsp+2C0h+var_288]
0x18000b63d  mov     r9d, r15d; int
0x18000b640  mov     [rsp+2C0h+var_2A0], rdx; struct STRW *
0x18000b645  mov     r8, r13; unsigned __int16 *
0x18000b648  mov     rdx, rsi; unsigned __int16 *
0x18000b64b  mov     rcx, r12; unsigned __int16 *
0x18000b64e  call    ?_GenerateUniqueFileName@@YAJPEBG00HPEAVSTRW@@@Z; _GenerateUniqueFileName(ushort const *,ushort const *,ushort const *,int,STRW *)
0x18000b653  mov     edi, [rsp+2C0h+var_288]
0x18000b657  xor     ecx, ecx
0x18000b659  mov     ebx, eax
0x18000b65b  test    eax, eax
0x18000b65d  js      short loc_18000B66B
0x18000b65f  cmp     dword ptr [rbp+1C0h+arg_28], edi
0x18000b665  ja      loc_18000B70A
0x18000b66b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b66f  inc     rax
0x18000b672  cmp     [rsi+rax*2], cx
0x18000b676  jnz     short loc_18000B66F
0x18000b678  inc     eax
0x18000b67a  cmp     eax, 27h ; '''
0x18000b67d  jle     loc_18000B706
0x18000b683  xorps   xmm0, xmm0
0x18000b686  lea     rcx, [rsp+2C0h+Uuid]; Uuid
0x18000b68b  movups  xmmword ptr [rsp+2C0h+Uuid.Data1], xmm0
0x18000b690  call    cs:__imp_UuidCreate
0x18000b696  test    eax, eax
0x18000b698  jnz     short loc_18000B6B7
0x18000b69a  lea     rdx, [rsp+2C0h+StringUuid]; StringUuid
0x18000b69f  mov     [rsp+2C0h+StringUuid], 0
0x18000b6a8  lea     rcx, [rsp+2C0h+Uuid]; Uuid
0x18000b6ad  call    cs:__imp_UuidToStringW
0x18000b6b3  test    eax, eax
0x18000b6b5  jz      short loc_18000B6BE
0x18000b6b7  mov     ebx, 8007000Eh
0x18000b6bc  jmp     short loc_18000B729
0x18000b6be  mov     rcx, [rsp+2C0h+var_280]; void *
0x18000b6c3  mov     r8, rdi
0x18000b6c6  add     r8, r8; Size
0x18000b6c9  xor     edx, edx; Val
0x18000b6cb  call    memset_0
0x18000b6d0  mov     rdx, [rsp+2C0h+StringUuid]; unsigned __int16 *
0x18000b6d5  lea     rax, [rsp+2C0h+var_288]
0x18000b6da  mov     r9d, r15d; int
0x18000b6dd  mov     [rsp+2C0h+var_2A0], rax; struct STRW *
0x18000b6e2  mov     r8, r13; unsigned __int16 *
0x18000b6e5  mov     [rsp+2C0h+var_288], 0
0x18000b6ed  mov     rcx, r12; unsigned __int16 *
0x18000b6f0  call    ?_GenerateUniqueFileName@@YAJPEBG00HPEAVSTRW@@@Z; _GenerateUniqueFileName(ushort const *,ushort const *,ushort const *,int,STRW *)
0x18000b6f5  lea     rcx, [rsp+2C0h+StringUuid]; String
0x18000b6fa  mov     ebx, eax
0x18000b6fc  call    cs:__imp_RpcStringFreeW
0x18000b702  mov     edi, [rsp+2C0h+var_288]
0x18000b706  test    ebx, ebx
0x18000b708  js      short loc_18000B729
0x18000b70a  mov     edx, dword ptr [rbp+1C0h+arg_28]; unsigned __int64
0x18000b710  lea     r8, ExistingFileName
0x18000b717  test    edi, edi
0x18000b719  mov     rcx, r14; unsigned __int16 *
0x18000b71c  cmovnz  r8, [rsp+2C0h+var_280]; unsigned __int16 *
0x18000b722  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b727  mov     ebx, eax
0x18000b729  lea     rcx, [rsp+2C0h+var_288]; this
0x18000b72e  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000b733  mov     eax, ebx
0x18000b735  mov     rcx, [rbp+1C0h+var_40]
0x18000b73c  xor     rcx, rsp; StackCookie
0x18000b73f  call    __security_check_cookie
0x18000b744  mov     rbx, [rsp+2C0h+arg_18]
0x18000b74c  add     rsp, 290h
0x18000b753  pop     r15
0x18000b755  pop     r14
0x18000b757  pop     r13
0x18000b759  pop     r12
0x18000b75b  pop     rdi
0x18000b75c  pop     rsi
0x18000b75d  pop     rbp
0x18000b75e  retn
```
