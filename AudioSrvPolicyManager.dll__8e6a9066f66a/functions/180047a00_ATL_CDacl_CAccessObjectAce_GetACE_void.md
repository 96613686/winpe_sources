# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x180047a00`
- end: `0x180047b08`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `264`
- prototype: `void *__fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800202f4`
- `0x18002bd9c`
- `0x1800327f8`
- `0x180047a00`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047a2c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047a2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047ada`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047ada`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessObjectAce::GetACE(ATL::CDacl::CAccessObjectAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  char v6; // al
  __int128 *v7; // rdx
  ATL::Checked *v8; // rbp
  int v9; // ecx
  __int128 v10; // xmm0
  __int128 *v11; // rax
  __int128 v12; // xmm0
  DWORD LengthSid; // eax
  unsigned __int64 v15; // [rsp+20h] [rbp-28h]

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    v6 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(v5 + 24))(this);
    v7 = (__int128 *)*((_QWORD *)this + 19);
    v8 = (ATL::Checked *)(v1 + 44);
    *v1 = v6;
    *(_QWORD *)(v1 + 4) = *((unsigned int *)this + 32);
    if ( v7 )
    {
      v10 = *v7;
      *((_DWORD *)v1 + 2) = 1;
      v9 = 3;
      *(_OWORD *)(v1 + 12) = v10;
    }
    else
    {
      v8 = (ATL::Checked *)(v1 + 28);
      v9 = 2;
    }
    v11 = (__int128 *)*((_QWORD *)this + 20);
    if ( v11 )
    {
      v12 = *v11;
      if ( v7 )
        *(_OWORD *)(v1 + 28) = v12;
      else
        *(_OWORD *)(v1 + 12) = v12;
      *((_DWORD *)v1 + 2) = v9;
    }
    else
    {
      v8 = (ATL::Checked *)((char *)v8 - 16);
    }
    LengthSid = GetLengthSid((char *)this + 16);
    ATL::Checked::memcpy_s(
      v8,
      (void *)(v8 - (ATL::Checked *)v1),
      (unsigned __int64)this + 16,
      (const void *)LengthSid,
      v15);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x180047a00  push    rbx
0x180047a02  push    rbp
0x180047a03  push    rsi
0x180047a04  push    rdi
0x180047a05  sub     rsp, 28h
0x180047a09  mov     rdi, [rcx+88h]
0x180047a10  mov     rsi, rcx
0x180047a13  test    rdi, rdi
0x180047a16  jnz     loc_180047AFC
0x180047a1c  mov     rax, [rcx]
0x180047a1f  mov     rax, [rax+10h]
0x180047a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a28  mov     ecx, eax; Size
0x180047a2a  mov     ebx, eax
0x180047a2c  call    cs:__imp_malloc
0x180047a32  mov     rdi, rax
0x180047a35  test    rax, rax
0x180047a38  jnz     short loc_180047A45
0x180047a3a  mov     ecx, 8007000Eh; int
0x180047a3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180047a45  mov     r8, rbx; Size
0x180047a48  xor     edx, edx; Val
0x180047a4a  mov     rcx, rdi; void *
0x180047a4d  call    memset_0
0x180047a52  mov     al, [rsi+84h]
0x180047a58  mov     rcx, rsi
0x180047a5b  mov     [rdi+1], al
0x180047a5e  mov     rax, [rsi]
0x180047a61  mov     [rdi+2], bx
0x180047a65  mov     rax, [rax+18h]
0x180047a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a6e  mov     rdx, [rsi+98h]
0x180047a75  lea     rbp, [rdi+2Ch]
0x180047a79  mov     [rdi], al
0x180047a7b  mov     eax, [rsi+80h]
0x180047a81  mov     [rdi+4], eax
0x180047a84  mov     dword ptr [rdi+8], 0
0x180047a8b  test    rdx, rdx
0x180047a8e  jnz     short loc_180047A99
0x180047a90  add     rbp, 0FFFFFFFFFFFFFFF0h
0x180047a94  lea     ecx, [rdx+2]
0x180047a97  jmp     short loc_180047AAD
0x180047a99  movups  xmm0, xmmword ptr [rdx]
0x180047a9c  mov     dword ptr [rdi+8], 1
0x180047aa3  mov     ecx, 3
0x180047aa8  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180047aad  mov     rax, [rsi+0A0h]
0x180047ab4  test    rax, rax
0x180047ab7  jnz     short loc_180047ABF
0x180047ab9  sub     rbp, 10h
0x180047abd  jmp     short loc_180047AD6
0x180047abf  movups  xmm0, xmmword ptr [rax]
0x180047ac2  test    rdx, rdx
0x180047ac5  jz      short loc_180047ACE
0x180047ac7  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x180047acc  jmp     short loc_180047AD3
0x180047ace  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180047ad3  mov     [rdi+8], ecx
0x180047ad6  lea     rcx, [rsi+10h]; pSid
0x180047ada  call    cs:__imp_GetLengthSid
0x180047ae0  mov     rdx, rbp
0x180047ae3  mov     r9d, eax; void *
0x180047ae6  sub     rdx, rdi; void *
0x180047ae9  lea     r8, [rsi+10h]; unsigned __int64
0x180047aed  mov     rcx, rbp; this
0x180047af0  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180047af5  mov     [rsi+88h], rdi
0x180047afc  mov     rax, rdi
0x180047aff  add     rsp, 28h
0x180047b03  pop     rdi
0x180047b04  pop     rsi
0x180047b05  pop     rbp
0x180047b06  pop     rbx
0x180047b07  retn
```
