# CMapi2DirFilter::AddURL(TLMString<192,64,32767> const &,int,int)

- ea: `0x180022bcc`
- end: `0x180022cca`
- name: `?AddURL@CMapi2DirFilter@@QEAAJAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HH@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180022cd0`
- `0x180024824`

## callees

- `0x180002780`
- `0x18000da40`
- `0x180017efc`
- `0x18002295c`
- `0x180022bcc`
- `0x18002b784`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022bf5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022bf5`

## string_xrefs

- `0x180022cb8`: `onecoreuap\base\appmodel\Search\common\include\tpslist.hxx`

## pseudocode

```c
__int64 __fastcall CMapi2DirFilter::AddURL(__int64 a1, __int64 a2, int a3, int a4)
{
  _DWORD *v7; // rax
  unsigned int v8; // edx
  _DWORD *v9; // rbx
  _QWORD *v11; // rax
  unsigned int v12; // edx
  int v13[2]; // [rsp+20h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-40h] BYREF
  _QWORD *v15; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a3 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v7 = operator new(0x1B0u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v7;
    *(_QWORD *)v13 = v7;
    if ( v7 )
    {
      CLinkWithTime::CLinkWithTime((__int64)v7, a2, &SystemTimeAsFileTime);
      v9[106] = a4;
    }
    else
    {
      v9 = 0;
    }
    *(_QWORD *)v13 = v9;
    if ( !v9 )
    {
      TPointer<CMapiDirLinkWithTime>::~TPointer<CMapiDirLinkWithTime>((CMapiDirLinkWithTime **)v13, v8);
      return 2147942414LL;
    }
    v11 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v11;
    if ( !v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\tpslist.hxx",
        (const char *)0x8007000ELL,
        v13[0]);
    *v11 = 0;
    v11[1] = 0;
    v11[1] = v9;
    CLnkList::InsertAfter((CLnkList *)(a1 + 9272), *(struct CSingleLink **)(a1 + 9288), (struct CSingleLink *)v11);
    *(_QWORD *)v13 = 0;
    TPointer<CMapiDirLinkWithTime>::~TPointer<CMapiDirLinkWithTime>((CMapiDirLinkWithTime **)v13, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180022bcc  push    rbx
0x180022bce  push    rbp
0x180022bcf  push    rsi
0x180022bd0  push    rdi
0x180022bd1  sub     rsp, 48h
0x180022bd5  mov     edi, r9d
0x180022bd8  mov     rsi, rdx
0x180022bdb  mov     rbp, rcx
0x180022bde  test    r8d, r8d
0x180022be1  jz      loc_180022CA2
0x180022be7  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180022bf0  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022bf5  call    cs:__imp_GetSystemTimeAsFileTime
0x180022bfb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022c02  mov     ecx, 1B0h; unsigned __int64
0x180022c07  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022c0c  mov     rbx, rax
0x180022c0f  mov     qword ptr [rsp+68h+var_48], rax
0x180022c14  test    rax, rax
0x180022c17  jz      short loc_180022C31
0x180022c19  lea     r8, [rsp+68h+SystemTimeAsFileTime]
0x180022c1e  mov     rdx, rsi
0x180022c21  mov     rcx, rax
0x180022c24  call    ??0CLinkWithTime@@QEAA@AEBV?$TLMString@$0MA@$0EA@$0HPPP@@@PEBU_FILETIME@@@Z; CLinkWithTime::CLinkWithTime(TLMString<192,64,32767> const &,_FILETIME const *)
0x180022c29  mov     [rbx+1A8h], edi
0x180022c2f  jmp     short loc_180022C33
0x180022c31  xor     ebx, ebx
0x180022c33  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180022c38  test    rbx, rbx
0x180022c3b  jnz     short loc_180022C4E
0x180022c3d  lea     rcx, [rsp+68h+var_48]
0x180022c42  call    ??1?$TPointer@VCMapiDirLinkWithTime@@@@QEAA@XZ; TPointer<CMapiDirLinkWithTime>::~TPointer<CMapiDirLinkWithTime>(void)
0x180022c47  mov     eax, 8007000Eh
0x180022c4c  jmp     short loc_180022CA4
0x180022c4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022c55  mov     ecx, 10h; unsigned __int64
0x180022c5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022c5f  mov     [rsp+68h+var_38], rax
0x180022c64  test    rax, rax
0x180022c67  jz      short loc_180022CAD
0x180022c69  mov     qword ptr [rax], 0
0x180022c70  mov     qword ptr [rax+8], 0
0x180022c78  lea     rcx, [rbp+2438h]; this
0x180022c7f  mov     [rax+8], rbx
0x180022c83  mov     r8, rax; struct CSingleLink *
0x180022c86  mov     rdx, [rcx+10h]; struct CSingleLink *
0x180022c8a  call    ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x180022c8f  mov     qword ptr [rsp+68h+var_48], 0
0x180022c98  lea     rcx, [rsp+68h+var_48]
0x180022c9d  call    ??1?$TPointer@VCMapiDirLinkWithTime@@@@QEAA@XZ; TPointer<CMapiDirLinkWithTime>::~TPointer<CMapiDirLinkWithTime>(void)
0x180022ca2  xor     eax, eax
0x180022ca4  add     rsp, 48h
0x180022ca8  pop     rdi
0x180022ca9  pop     rsi
0x180022caa  pop     rbp
0x180022cab  pop     rbx
0x180022cac  retn
0x180022cad  mov     rcx, [rsp+68h]; this
0x180022cb2  mov     r9d, 8007000Eh; char *
0x180022cb8  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180022cbf  mov     edx, 13Dh; void *
0x180022cc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
