# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)

- ea: `0x140003ea0`
- end: `0x140003fbd`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z`
- size: `285`
- prototype: `LPWSTR *__fastcall(LPWSTR *, const CHAR *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b250`
- `0x14000ced0`
- `0x14000ea38`
- `0x140011a40`

## callees

- `0x140003ea0`
- `0x140004890`
- `0x140007560`
- `0x140017010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140003eda`
- `KERNEL32!MultiByteToWideChar` at `0x140003f1d`
- `KERNEL32!MultiByteToWideChar` at `0x140003eda`
- `KERNEL32!MultiByteToWideChar` at `0x140003f1d`

## pseudocode

```c
LPWSTR *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        LPWSTR *a1,
        const CHAR *a2)
{
  int cchWideChar; // edi
  LPWSTR v5; // rax
  volatile signed __int32 *v6; // rdx
  __int64 v7; // rdi

  if ( a2 )
  {
    cchWideChar = MultiByteToWideChar(3u, 0, a2, -1, 0, 0) - 1;
    v5 = *a1;
    if ( cchWideChar > 0 )
    {
      if ( ((*((_DWORD *)v5 - 3) - cchWideChar) | (1 - *((_DWORD *)v5 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)cchWideChar);
      MultiByteToWideChar(3u, 0, a2, -1, *a1, cchWideChar);
      if ( cchWideChar <= *((_DWORD *)*a1 - 3) )
      {
        *((_DWORD *)*a1 - 4) = cchWideChar;
        (*a1)[cchWideChar] = 0;
        return a1;
      }
LABEL_16:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  else
  {
    v5 = *a1;
  }
  v6 = (volatile signed __int32 *)(v5 - 12);
  if ( !*((_DWORD *)v5 - 4) )
    return a1;
  if ( *((int *)v6 + 4) < 0 )
  {
    if ( *((int *)v5 - 3) >= 0 )
    {
      *((_DWORD *)v5 - 4) = 0;
      **a1 = 0;
      return a1;
    }
    goto LABEL_16;
  }
  v7 = *(_QWORD *)v6;
  if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  *a1 = (LPWSTR)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  return a1;
}

```

## disassembly

```asm
0x140003ea0  mov     rax, rsp
0x140003ea3  mov     [rax+8], rbx
0x140003ea7  mov     [rax+10h], rsi
0x140003eab  push    rdi
0x140003eac  sub     rsp, 30h
0x140003eb0  mov     rsi, rdx
0x140003eb3  mov     rbx, rcx
0x140003eb6  test    rdx, rdx
0x140003eb9  jz      loc_140003F40
0x140003ebf  mov     r8, rdx; lpMultiByteStr
0x140003ec2  mov     dword ptr [rax-10h], 0
0x140003ec9  xor     edx, edx; dwFlags
0x140003ecb  mov     qword ptr [rax-18h], 0
0x140003ed3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140003ed7  lea     ecx, [rdx+3]; CodePage
0x140003eda  call    cs:__imp_MultiByteToWideChar
0x140003ee0  lea     edi, [rax-1]
0x140003ee3  mov     rax, [rbx]
0x140003ee6  test    edi, edi
0x140003ee8  jle     short loc_140003F43
0x140003eea  mov     edx, 1
0x140003eef  sub     edx, [rax-8]
0x140003ef2  mov     eax, [rax-0Ch]
0x140003ef5  sub     eax, edi
0x140003ef7  or      edx, eax
0x140003ef9  jge     short loc_140003F05
0x140003efb  mov     edx, edi
0x140003efd  mov     rcx, rbx
0x140003f00  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140003f05  mov     rax, [rbx]
0x140003f08  xor     edx, edx; dwFlags
0x140003f0a  mov     [rsp+38h+cchWideChar], edi; cchWideChar
0x140003f0e  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140003f12  mov     r8, rsi; lpMultiByteStr
0x140003f15  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x140003f1a  lea     ecx, [rdx+3]; CodePage
0x140003f1d  call    cs:__imp_MultiByteToWideChar
0x140003f23  mov     rax, [rbx]
0x140003f26  cmp     edi, [rax-0Ch]
0x140003f29  jg      loc_140003FB2
0x140003f2f  mov     [rax-10h], edi
0x140003f32  xor     eax, eax
0x140003f34  mov     rcx, [rbx]
0x140003f37  movsxd  rdx, edi
0x140003f3a  mov     [rcx+rdx*2], ax
0x140003f3e  jmp     short loc_140003F9F
0x140003f40  mov     rax, [rcx]
0x140003f43  lea     rdx, [rax-18h]
0x140003f47  cmp     dword ptr [rdx+8], 0
0x140003f4b  jz      short loc_140003F9F
0x140003f4d  cmp     dword ptr [rdx+10h], 0
0x140003f51  jge     short loc_140003F6A
0x140003f53  cmp     dword ptr [rax-0Ch], 0
0x140003f57  jl      short loc_140003FB2
0x140003f59  mov     dword ptr [rax-10h], 0
0x140003f60  xor     eax, eax
0x140003f62  mov     rcx, [rbx]
0x140003f65  mov     [rcx], ax
0x140003f68  jmp     short loc_140003F9F
0x140003f6a  mov     rdi, [rdx]
0x140003f6d  or      eax, 0FFFFFFFFh
0x140003f70  lock xadd [rdx+10h], eax
0x140003f75  sub     eax, 1
0x140003f78  jg      short loc_140003F89
0x140003f7a  mov     rcx, [rdx]
0x140003f7d  mov     rax, [rcx]
0x140003f80  mov     rax, [rax+8]
0x140003f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f89  mov     rax, [rdi]
0x140003f8c  mov     rcx, rdi
0x140003f8f  mov     rax, [rax+18h]
0x140003f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f98  add     rax, 18h
0x140003f9c  mov     [rbx], rax
0x140003f9f  mov     rsi, [rsp+38h+arg_8]
0x140003fa4  mov     rax, rbx
0x140003fa7  mov     rbx, [rsp+38h+arg_0]
0x140003fac  add     rsp, 30h
0x140003fb0  pop     rdi
0x140003fb1  retn
0x140003fb2  mov     ecx, 80070057h; int
0x140003fb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
