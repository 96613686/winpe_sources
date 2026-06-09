# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)

- ea: `0x180010ca0`
- end: `0x180010d89`
- name: `?Add@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_KAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@@Z`
- size: `233`
- prototype: `unsigned __int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002c264`

## callees

- `0x180010ca0`
- `0x180019e00`
- `0x18002c334`
- `0x18002dc3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010d21`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010d70`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010d21`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010d70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010d4f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010d4f`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(
        __int64 a1,
        __int64 *a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // rcx
  unsigned __int64 result; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  size_t v9; // rdx
  size_t v10; // rbp
  void *v11; // rax
  void *v12; // r14
  errno_t v13; // eax
  void *v14; // rax

  v2 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(a1 + 16);
  if ( v2 >= v4 )
  {
    v9 = v2 + 1;
    if ( v2 + 1 > v4 )
    {
      v10 = *(int *)(a1 + 24);
      if ( *(_QWORD *)a1 )
      {
        if ( !*(_DWORD *)(a1 + 24) )
        {
          v10 = v4 >> 1;
          if ( v9 - v4 > v4 >> 1 )
            v10 = v9 - v4;
        }
        v10 += v4;
        if ( v9 >= v10 )
          v10 = v2 + 1;
        v11 = calloc(v10, 8u);
        v12 = v11;
        if ( v11 )
        {
          v13 = memmove_s(v11, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
          ATL::AtlCrtErrorCheck(v13);
          free(*(void **)a1);
          *(_QWORD *)a1 = v12;
LABEL_12:
          *(_QWORD *)(a1 + 16) = v10;
          goto LABEL_2;
        }
      }
      else
      {
        if ( v10 <= v9 )
          v10 = v2 + 1;
        v14 = calloc(v10, 8u);
        *(_QWORD *)a1 = v14;
        if ( v14 )
          goto LABEL_12;
      }
      ATL::AtlThrowImpl(-2147024882);
    }
  }
LABEL_2:
  result = v2;
  v7 = (_QWORD *)(*(_QWORD *)a1 + 8 * v2);
  v8 = *a2;
  *a2 = 0;
  *v7 = v8;
  ++*(_QWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x180010ca0  push    rbx
0x180010ca2  push    rbp
0x180010ca3  push    rsi
0x180010ca4  push    rdi
0x180010ca5  push    r14
0x180010ca7  sub     rsp, 20h
0x180010cab  mov     rdi, [rcx+8]
0x180010caf  mov     rbx, rcx
0x180010cb2  mov     rcx, [rcx+10h]
0x180010cb6  mov     rsi, rdx
0x180010cb9  cmp     rdi, rcx
0x180010cbc  jnb     short loc_180010CE4
0x180010cbe  mov     rcx, [rbx]
0x180010cc1  mov     rax, rdi
0x180010cc4  lea     rdx, [rcx+rdi*8]
0x180010cc8  mov     rcx, [rsi]
0x180010ccb  mov     qword ptr [rsi], 0
0x180010cd2  mov     [rdx], rcx
0x180010cd5  inc     qword ptr [rbx+8]
0x180010cd9  add     rsp, 20h
0x180010cdd  pop     r14
0x180010cdf  pop     rdi
0x180010ce0  pop     rsi
0x180010ce1  pop     rbp
0x180010ce2  pop     rbx
0x180010ce3  retn
0x180010ce4  lea     rdx, [rdi+1]
0x180010ce8  cmp     rdx, rcx
0x180010ceb  jbe     short loc_180010CBE
0x180010ced  cmp     qword ptr [rbx], 0
0x180010cf1  movsxd  rbp, dword ptr [rbx+18h]
0x180010cf5  jz      short loc_180010D61
0x180010cf7  test    rbp, rbp
0x180010cfa  jnz     short loc_180010D0F
0x180010cfc  mov     rbp, rcx
0x180010cff  mov     rax, rdx
0x180010d02  shr     rbp, 1
0x180010d05  sub     rax, rcx
0x180010d08  cmp     rax, rbp
0x180010d0b  cmova   rbp, rax
0x180010d0f  add     rbp, rcx
0x180010d12  cmp     rdx, rbp
0x180010d15  cmovnb  rbp, rdx
0x180010d19  mov     edx, 8; Size
0x180010d1e  mov     rcx, rbp; Count
0x180010d21  call    cs:__imp_calloc
0x180010d27  mov     r14, rax
0x180010d2a  test    rax, rax
0x180010d2d  jz      short loc_180010D7E
0x180010d2f  mov     rdx, [rbx+8]
0x180010d33  mov     rcx, rax; Destination
0x180010d36  mov     r8, [rbx]; Source
0x180010d39  shl     rdx, 3; DestinationSize
0x180010d3d  mov     r9, rdx; SourceSize
0x180010d40  call    memmove_s
0x180010d45  mov     ecx, eax; int
0x180010d47  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180010d4c  mov     rcx, [rbx]; Block
0x180010d4f  call    cs:__imp_free
0x180010d55  mov     [rbx], r14
0x180010d58  mov     [rbx+10h], rbp
0x180010d5c  jmp     loc_180010CBE
0x180010d61  cmp     rbp, rdx
0x180010d64  cmovbe  rbp, rdx
0x180010d68  mov     edx, 8; Size
0x180010d6d  mov     rcx, rbp; Count
0x180010d70  call    cs:__imp_calloc
0x180010d76  mov     [rbx], rax
0x180010d79  test    rax, rax
0x180010d7c  jnz     short loc_180010D58
0x180010d7e  mov     ecx, 8007000Eh; int
0x180010d83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
