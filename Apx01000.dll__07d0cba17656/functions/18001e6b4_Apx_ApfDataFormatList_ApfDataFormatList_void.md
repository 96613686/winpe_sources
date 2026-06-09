# Apx::ApfDataFormatList::~ApfDataFormatList(void)

- ea: `0x18001e6b4`
- end: `0x18001e7a7`
- name: `??1ApfDataFormatList@Apx@@EEAA@XZ`
- size: `243`
- prototype: `void __fastcall(Apx::ApfDataFormatList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001e7b0`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000d2f0`
- `0x18001e6b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e761`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e761`

## pseudocode

```c
void __fastcall Apx::ApfDataFormatList::~ApfDataFormatList(Apx::ApfDataFormatList *this)
{
  _QWORD **v2; // rsi
  _QWORD *v3; // rdi
  _QWORD *v4; // rax

  *(_QWORD *)this = &Apx::ApfDataFormatList::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  }
  v2 = (_QWORD **)((char *)this + 56);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    --*((_DWORD *)this + 18);
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~v3[2]);
    operator delete(v3, (const struct std::nothrow_t *)0x18);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x18001e6b4  push    rbx
0x18001e6b6  push    rbp
0x18001e6b7  push    rsi
0x18001e6b8  push    rdi
0x18001e6b9  sub     rsp, 38h
0x18001e6bd  lea     rax, ??_7ApfDataFormatList@Apx@@6B@; const Apx::ApfDataFormatList::`vftable'
0x18001e6c4  mov     rbx, rcx
0x18001e6c7  mov     [rcx], rax
0x18001e6ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6d1  lea     rbp, WPP_GLOBAL_Control
0x18001e6d8  cmp     rcx, rbp
0x18001e6db  jz      short loc_18001E6FE
0x18001e6dd  test    byte ptr [rcx+1Ch], 1
0x18001e6e1  jz      short loc_18001E6FE
0x18001e6e3  cmp     byte ptr [rcx+19h], 5
0x18001e6e7  jb      short loc_18001E6FE
0x18001e6e9  mov     rcx, [rcx+10h]
0x18001e6ed  lea     r8, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001e6f4  mov     edx, 0Fh
0x18001e6f9  call    WPP_SF_
0x18001e6fe  lea     rsi, [rbx+38h]
0x18001e702  mov     rdi, [rsi]
0x18001e705  cmp     rdi, rsi
0x18001e708  jz      short loc_18001E75D
0x18001e70a  cmp     [rdi+8], rsi
0x18001e70e  jnz     short loc_18001E756
0x18001e710  mov     rax, [rdi]
0x18001e713  cmp     [rax+8], rdi
0x18001e717  jnz     short loc_18001E756
0x18001e719  mov     [rsi], rax
0x18001e71c  xor     ecx, ecx; this
0x18001e71e  mov     [rax+8], rsi
0x18001e722  mov     r8, rbx
0x18001e725  dec     dword ptr [rbx+48h]
0x18001e728  lea     rax, aOnecoreuapDriv_8; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18001e72f  mov     rdx, [rdi+10h]
0x18001e733  not     r8
0x18001e736  not     rdx; Apx::ApfVerify *
0x18001e739  mov     [rsp+58h+var_38], rax
0x18001e73e  lea     r9d, [rcx+5Dh]
0x18001e742  call    imp_ApxObjectDereferenceActual
0x18001e747  mov     edx, 18h; struct std::nothrow_t *
0x18001e74c  mov     rcx, rdi; void *
0x18001e74f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e754  jmp     short loc_18001E702
0x18001e756  mov     ecx, 3
0x18001e75b  int     29h; Win8: RtlFailFast(ecx)
0x18001e75d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001e761  call    cs:__imp_DeleteCriticalSection
0x18001e767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e76e  cmp     rcx, rbp
0x18001e771  jz      short loc_18001E794
0x18001e773  test    byte ptr [rcx+1Ch], 1
0x18001e777  jz      short loc_18001E794
0x18001e779  cmp     byte ptr [rcx+19h], 5
0x18001e77d  jb      short loc_18001E794
0x18001e77f  mov     rcx, [rcx+10h]
0x18001e783  lea     r8, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001e78a  mov     edx, 10h
0x18001e78f  call    WPP_SF_
0x18001e794  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x18001e79b  mov     [rbx], rax
0x18001e79e  add     rsp, 38h
0x18001e7a2  pop     rdi
0x18001e7a3  pop     rsi
0x18001e7a4  pop     rbp
0x18001e7a5  pop     rbx
0x18001e7a6  retn
```
