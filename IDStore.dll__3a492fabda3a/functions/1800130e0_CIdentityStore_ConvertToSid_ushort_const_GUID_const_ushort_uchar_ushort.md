# CIdentityStore::ConvertToSid(ushort const *,_GUID const &,ushort,uchar *,ushort *)

- ea: `0x1800130e0`
- end: `0x180013169`
- name: `?ConvertToSid@CIdentityStore@@UEAAJPEBGAEBU_GUID@@GPEAEPEAG@Z`
- size: `137`
- prototype: `__int64 __fastcall(CIdentityStore *this, const unsigned __int16 *, const struct _GUID *, unsigned __int16, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180003560`
- `0x18000acb0`
- `0x18000e660`
- `0x1800130e0`

## string_xrefs

- `0x180013101`: `CIdentityStore::ConvertToSid`

## pseudocode

```c
__int64 __fastcall CIdentityStore::ConvertToSid(
        CIdentityStore *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned __int16 a4,
        unsigned __int8 *a5,
        unsigned __int16 *a6)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v14; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-20h] BYREF

  v14 = -2147467259;
  CLogBlock::CLogBlock((CLogBlock *)v15, "CIdentityStore::ConvertToSid", (int *)&v14);
  if ( a6 )
  {
    *a6 = a4;
    v12 = ConvertIdentityToSid(a2, (__int64)a3, a5, a6);
    v11 = v12;
    if ( v12 > 0 )
      v11 = (unsigned __int16)v12 | 0x80070000;
  }
  else
  {
    v11 = -2147024809;
  }
  v14 = v11;
  CLogBlock::~CLogBlock((CLogBlock *)v15, v9, v10);
  return v11;
}

```

## disassembly

```asm
0x1800130e0  mov     rax, rsp
0x1800130e3  mov     [rax+8], rbx
0x1800130e7  mov     [rax+10h], rsi
0x1800130eb  push    rdi
0x1800130ec  sub     rsp, 40h
0x1800130f0  mov     rdi, r8
0x1800130f3  mov     dword ptr [rax-28h], 80004005h
0x1800130fa  mov     rsi, rdx
0x1800130fd  lea     r8, [rax-28h]; int *
0x180013101  lea     rdx, aCidentitystore_11; "CIdentityStore::ConvertToSid"
0x180013108  movzx   ebx, r9w
0x18001310c  lea     rcx, [rax-20h]; this
0x180013110  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x180013115  mov     r9, [rsp+48h+arg_28]; unsigned __int16 *
0x18001311a  test    r9, r9
0x18001311d  jnz     short loc_180013126
0x18001311f  mov     ebx, 80070057h
0x180013124  jmp     short loc_180013149
0x180013126  mov     r8, [rsp+48h+arg_20]; unsigned __int8 *
0x18001312b  mov     rdx, rdi; struct _GUID *
0x18001312e  mov     rcx, rsi; unsigned __int16 *
0x180013131  mov     [r9], bx
0x180013135  call    ?ConvertIdentityToSid@@YAKPEBGAEBU_GUID@@PEAEPEAG@Z; ConvertIdentityToSid(ushort const *,_GUID const &,uchar *,ushort *)
0x18001313a  mov     ebx, eax
0x18001313c  test    eax, eax
0x18001313e  jle     short loc_180013149
0x180013140  movzx   ebx, ax
0x180013143  or      ebx, 80070000h
0x180013149  lea     rcx, [rsp+48h+var_20]; this
0x18001314e  mov     [rsp+48h+var_28], ebx
0x180013152  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180013157  mov     rsi, [rsp+48h+arg_8]
0x18001315c  mov     eax, ebx
0x18001315e  mov     rbx, [rsp+48h+arg_0]
0x180013163  add     rsp, 40h
0x180013167  pop     rdi
0x180013168  retn
```
