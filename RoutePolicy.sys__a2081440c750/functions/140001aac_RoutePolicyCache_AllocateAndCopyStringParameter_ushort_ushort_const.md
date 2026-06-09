# RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)

- ea: `0x140001aac`
- end: `0x140001bf3`
- name: `?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z`
- size: `327`
- prototype: `int(RoutePolicyCache *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400016a0`
- `0x140001bfc`
- `0x140001ed8`
- `0x1400037a4`

## callees

- `0x140001008`
- `0x140001aac`
- `0x14000a780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001b3e`
- `ntoskrnl!ExAllocatePool2` at `0x140001b3e`

## string_xrefs

- `0x140001bad`: `Failed to compute string size`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::AllocateAndCopyStringParameter(
        const char **this,
        unsigned __int16 **a2,
        __int64 a3,
        int a4)
{
  const char **v5; // r14
  unsigned __int16 **v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  size_t v9; // rsi
  char *Pool2; // rax
  char *v11; // rdx
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF
  const char *v14; // [rsp+58h] [rbp+10h] BYREF

  *this = 0;
  v5 = this;
  if ( a2 )
  {
    v6 = a2;
    a3 = 0x7FFFFFFF;
    do
    {
      if ( !*(_WORD *)v6 )
        break;
      v6 = (unsigned __int16 **)((char *)v6 + 2);
      --a3;
    }
    while ( a3 );
    v7 = a3 == 0 ? 0xC000000D : 0;
    if ( a3 )
    {
      v8 = 2 * (0x7FFFFFFF - a3);
      a3 = -a3;
      v9 = -1;
      this = (const char **)(v8 & -(__int64)(a3 != 0));
      if ( (const char **)((char *)this + 2) >= this )
        v9 = (size_t)this + 2;
      v7 = (const char **)((char *)this + 2) < this ? 0xC0000095 : 0;
      if ( (const char **)((char *)this + 2) >= this )
      {
        Pool2 = (char *)ExAllocatePool2(64, v9, 1684435058);
        *v5 = Pool2;
        if ( Pool2 )
        {
          memmove(Pool2, a2, v9);
          return 0;
        }
        v7 = -1073741670;
        if ( (unsigned int)dword_140012050 > 2 )
        {
          v14 = "Failed to allocate string";
          v11 = byte_14000E879;
          this = &v14;
LABEL_16:
          v13 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)this,
            (_DWORD)v11,
            a3,
            a4,
            (__int64)&v14,
            (__int64)&v13);
          return v7;
        }
        return v7;
      }
    }
  }
  else
  {
    v7 = -1073741811;
  }
  if ( (unsigned int)dword_140012050 > 2 )
  {
    v14 = "Failed to compute string size";
    v11 = byte_14000E011;
    goto LABEL_16;
  }
  return v7;
}

```

## disassembly

```asm
0x140001aac  mov     [rsp+arg_10], rbx
0x140001ab1  mov     [rsp+arg_18], rbp
0x140001ab6  push    rsi
0x140001ab7  push    rdi
0x140001ab8  push    r14
0x140001aba  sub     rsp, 30h
0x140001abe  xor     ebp, ebp
0x140001ac0  mov     rdi, rdx
0x140001ac3  mov     [rcx], rbp
0x140001ac6  mov     r14, rcx
0x140001ac9  test    rdx, rdx
0x140001acc  jz      loc_140001B9D
0x140001ad2  mov     edx, 7FFFFFFFh
0x140001ad7  mov     rax, rdi
0x140001ada  mov     r8d, edx
0x140001add  cmp     [rax], bp
0x140001ae0  jz      short loc_140001AEC
0x140001ae2  add     rax, 2
0x140001ae6  sub     r8, 1
0x140001aea  jnz     short loc_140001ADD
0x140001aec  mov     rax, r8
0x140001aef  neg     rax
0x140001af2  sbb     ebx, ebx
0x140001af4  not     ebx
0x140001af6  and     ebx, 0C000000Dh
0x140001afc  test    r8, r8
0x140001aff  jz      loc_140001BA2
0x140001b05  sub     rdx, r8
0x140001b08  add     rdx, rdx
0x140001b0b  neg     r8
0x140001b0e  sbb     rcx, rcx
0x140001b11  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001b15  and     rcx, rdx
0x140001b18  lea     rax, [rcx+2]
0x140001b1c  cmp     rax, rcx
0x140001b1f  cmovnb  rsi, rax
0x140001b23  sbb     ebx, ebx
0x140001b25  and     ebx, 0C0000095h
0x140001b2b  cmp     rax, rcx
0x140001b2e  jb      short loc_140001BA2
0x140001b30  mov     r8d, 64667072h
0x140001b36  mov     rdx, rsi
0x140001b39  mov     ecx, 40h ; '@'
0x140001b3e  call    cs:__imp_ExAllocatePool2
0x140001b45  nop     dword ptr [rax+rax+00h]
0x140001b4a  mov     [r14], rax
0x140001b4d  test    rax, rax
0x140001b50  jnz     short loc_140001B8B
0x140001b52  mov     eax, cs:dword_140012050
0x140001b58  mov     ebx, 0C000009Ah
0x140001b5d  cmp     eax, 2
0x140001b60  jbe     short loc_140001BDD
0x140001b62  lea     rcx, aFailedToAlloca_0; "Failed to allocate string"
0x140001b69  mov     [rsp+48h+arg_8], rcx
0x140001b6e  lea     rdx, byte_14000E879
0x140001b75  lea     rcx, [rsp+48h+arg_0]
0x140001b7a  mov     [rsp+48h+var_20], rcx
0x140001b7f  lea     rcx, [rsp+48h+arg_8]
0x140001b84  mov     [rsp+48h+var_28], rcx
0x140001b89  jmp     short loc_140001BD4
0x140001b8b  mov     r8, rsi; Size
0x140001b8e  mov     rdx, rdi; Src
0x140001b91  mov     rcx, rax; void *
0x140001b94  call    memmove
0x140001b99  xor     eax, eax
0x140001b9b  jmp     short loc_140001BDF
0x140001b9d  mov     ebx, 0C000000Dh
0x140001ba2  mov     eax, cs:dword_140012050
0x140001ba8  cmp     eax, 2
0x140001bab  jbe     short loc_140001BDD
0x140001bad  lea     rax, aFailedToComput; "Failed to compute string size"
0x140001bb4  mov     [rsp+48h+arg_8], rax
0x140001bb9  lea     rdx, byte_14000E011
0x140001bc0  lea     rax, [rsp+48h+arg_0]
0x140001bc5  mov     [rsp+48h+var_20], rax
0x140001bca  lea     rax, [rsp+48h+arg_8]
0x140001bcf  mov     [rsp+48h+var_28], rax
0x140001bd4  mov     [rsp+48h+arg_0], ebx
0x140001bd8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001bdd  mov     eax, ebx
0x140001bdf  mov     rbx, [rsp+48h+arg_10]
0x140001be4  mov     rbp, [rsp+48h+arg_18]
0x140001be9  add     rsp, 30h
0x140001bed  pop     r14
0x140001bef  pop     rdi
0x140001bf0  pop     rsi
0x140001bf1  retn
```
