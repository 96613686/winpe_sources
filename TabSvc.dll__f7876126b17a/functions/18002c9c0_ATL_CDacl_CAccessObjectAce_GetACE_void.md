# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x18002c9c0`
- end: `0x18002cacf`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `271`
- prototype: `char *__fastcall(ATL::CDacl::CAccessObjectAce *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017f50`
- `0x180019e00`
- `0x18001c684`
- `0x18002c334`
- `0x18002c9c0`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c9ec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c9ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ca9a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ca9a`

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
  char *v8; // rbp
  int v9; // ecx
  __int128 v10; // xmm0
  __int128 *v11; // rax
  __int128 v12; // xmm0
  DWORD LengthSid; // eax
  errno_t v14; // eax

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
    v8 = v1 + 44;
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
      v8 = v1 + 28;
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
      v8 -= 16;
    }
    LengthSid = GetLengthSid((char *)this + 16);
    v14 = memcpy_s(v8, v8 - v1, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v14);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18002c9c0  push    rbx
0x18002c9c2  push    rbp
0x18002c9c3  push    rsi
0x18002c9c4  push    rdi
0x18002c9c5  sub     rsp, 28h
0x18002c9c9  mov     rdi, [rcx+88h]
0x18002c9d0  mov     rsi, rcx
0x18002c9d3  test    rdi, rdi
0x18002c9d6  jnz     loc_18002CAC3
0x18002c9dc  mov     rax, [rcx]
0x18002c9df  mov     rax, [rax+10h]
0x18002c9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9e8  mov     ecx, eax; Size
0x18002c9ea  mov     ebx, eax
0x18002c9ec  call    cs:__imp_malloc
0x18002c9f2  mov     rdi, rax
0x18002c9f5  test    rax, rax
0x18002c9f8  jnz     short loc_18002CA05
0x18002c9fa  mov     ecx, 8007000Eh; int
0x18002c9ff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ca05  mov     r8, rbx; Size
0x18002ca08  xor     edx, edx; Val
0x18002ca0a  mov     rcx, rdi; void *
0x18002ca0d  call    memset_0
0x18002ca12  mov     al, [rsi+84h]
0x18002ca18  mov     rcx, rsi
0x18002ca1b  mov     [rdi+1], al
0x18002ca1e  mov     rax, [rsi]
0x18002ca21  mov     [rdi+2], bx
0x18002ca25  mov     rax, [rax+18h]
0x18002ca29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca2e  mov     rdx, [rsi+98h]
0x18002ca35  lea     rbp, [rdi+2Ch]
0x18002ca39  mov     [rdi], al
0x18002ca3b  mov     eax, [rsi+80h]
0x18002ca41  mov     [rdi+4], eax
0x18002ca44  mov     dword ptr [rdi+8], 0
0x18002ca4b  test    rdx, rdx
0x18002ca4e  jnz     short loc_18002CA59
0x18002ca50  add     rbp, 0FFFFFFFFFFFFFFF0h
0x18002ca54  lea     ecx, [rdx+2]
0x18002ca57  jmp     short loc_18002CA6D
0x18002ca59  movups  xmm0, xmmword ptr [rdx]
0x18002ca5c  mov     dword ptr [rdi+8], 1
0x18002ca63  mov     ecx, 3
0x18002ca68  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18002ca6d  mov     rax, [rsi+0A0h]
0x18002ca74  test    rax, rax
0x18002ca77  jnz     short loc_18002CA7F
0x18002ca79  sub     rbp, 10h
0x18002ca7d  jmp     short loc_18002CA96
0x18002ca7f  movups  xmm0, xmmword ptr [rax]
0x18002ca82  test    rdx, rdx
0x18002ca85  jz      short loc_18002CA8E
0x18002ca87  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x18002ca8c  jmp     short loc_18002CA93
0x18002ca8e  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18002ca93  mov     [rdi+8], ecx
0x18002ca96  lea     rcx, [rsi+10h]; pSid
0x18002ca9a  call    cs:__imp_GetLengthSid
0x18002caa0  mov     rdx, rbp
0x18002caa3  mov     r9d, eax; SourceSize
0x18002caa6  sub     rdx, rdi; DestinationSize
0x18002caa9  lea     r8, [rsi+10h]; Source
0x18002caad  mov     rcx, rbp; Destination
0x18002cab0  call    memcpy_s
0x18002cab5  mov     ecx, eax; int
0x18002cab7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002cabc  mov     [rsi+88h], rdi
0x18002cac3  mov     rax, rdi
0x18002cac6  add     rsp, 28h
0x18002caca  pop     rdi
0x18002cacb  pop     rsi
0x18002cacc  pop     rbp
0x18002cacd  pop     rbx
0x18002cace  retn
```
