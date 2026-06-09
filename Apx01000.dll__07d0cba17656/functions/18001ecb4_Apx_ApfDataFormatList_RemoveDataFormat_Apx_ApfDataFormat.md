# Apx::ApfDataFormatList::RemoveDataFormat(Apx::ApfDataFormat *)

- ea: `0x18001ecb4`
- end: `0x18001ee27`
- name: `?RemoveDataFormat@ApfDataFormatList@Apx@@QEAAJPEAVApfDataFormat@2@@Z`
- size: `371`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct Apx::ApfDataFormat *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001f430`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000d2f0`
- `0x18001051c`
- `0x18001cc5c`
- `0x18001ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed02`

## pseudocode

```c
__int64 __fastcall Apx::ApfDataFormatList::RemoveDataFormat(unsigned __int64 this, struct Apx::ApfDataFormat *a2)
{
  Apx::ApfDataFormat *v4; // rsi
  Apx::ApfDataFormat *i; // rbx
  unsigned int v6; // ebp
  Apx::ApfDataFormat *v8; // rax
  void **v9; // rcx
  _QWORD *v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v4 = (Apx::ApfDataFormat *)(this + 56);
  for ( i = *(Apx::ApfDataFormat **)(this + 56); ; i = *(Apx::ApfDataFormat **)i )
  {
    if ( i == v4 )
    {
      i = 0;
      v6 = -805305819;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids,
          ~this,
          -805305819);
      }
      goto LABEL_13;
    }
    if ( Apx::ApfDataFormat::IsEqual(*((Apx::ApfDataFormat **)i + 2), a2) )
      break;
  }
  v8 = *(Apx::ApfDataFormat **)i;
  if ( *(Apx::ApfDataFormat **)(*(_QWORD *)i + 8LL) != i || (v9 = (void **)*((_QWORD *)i + 1), *v9 != i) )
    __fastfail(3u);
  *v9 = v8;
  *((_QWORD *)v8 + 1) = v9;
  --*(_DWORD *)(this + 72);
  v6 = 0;
  imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~*((_QWORD *)i + 2));
  if ( i == *(Apx::ApfDataFormat **)(this + 80) )
  {
    v10 = 0;
    if ( *(Apx::ApfDataFormat **)v4 != v4 )
      v10 = *(_QWORD **)v4;
    *(_QWORD *)(this + 80) = v10;
  }
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( i )
    operator delete(i, (const struct std::nothrow_t *)0x18);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18001ecb4  push    rbx
0x18001ecb6  push    rbp
0x18001ecb7  push    rsi
0x18001ecb8  push    rdi
0x18001ecb9  push    r14
0x18001ecbb  push    r15
0x18001ecbd  sub     rsp, 38h
0x18001ecc1  mov     rbp, rdx
0x18001ecc4  mov     rdi, rcx
0x18001ecc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecce  lea     r15, WPP_GLOBAL_Control
0x18001ecd5  cmp     rcx, r15
0x18001ecd8  jz      short loc_18001ECFB
0x18001ecda  test    byte ptr [rcx+1Ch], 1
0x18001ecde  jz      short loc_18001ECFB
0x18001ece0  cmp     byte ptr [rcx+19h], 5
0x18001ece4  jb      short loc_18001ECFB
0x18001ece6  mov     rcx, [rcx+10h]
0x18001ecea  lea     r8, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001ecf1  mov     edx, 19h
0x18001ecf6  call    WPP_SF_
0x18001ecfb  lea     r14, [rdi+10h]
0x18001ecff  mov     rcx, r14; lpCriticalSection
0x18001ed02  call    cs:__imp_EnterCriticalSection
0x18001ed08  lea     rsi, [rdi+38h]
0x18001ed0c  mov     rbx, [rsi]
0x18001ed0f  jmp     short loc_18001ED28
0x18001ed11  mov     rcx, [rbx+10h]; this
0x18001ed15  mov     rdx, rbp; struct Apx::ApfDataFormat *
0x18001ed18  call    ?IsEqual@ApfDataFormat@Apx@@QEAAEPEAV12@@Z; Apx::ApfDataFormat::IsEqual(Apx::ApfDataFormat *)
0x18001ed1d  test    al, al
0x18001ed1f  jnz     loc_18001EDC0
0x18001ed25  mov     rbx, [rbx]
0x18001ed28  cmp     rbx, rsi
0x18001ed2b  jnz     short loc_18001ED11
0x18001ed2d  xor     ebx, ebx
0x18001ed2f  mov     ebp, 0D0000225h
0x18001ed34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed3b  cmp     rcx, r15
0x18001ed3e  jz      short loc_18001ED69
0x18001ed40  test    byte ptr [rcx+1Ch], 20h
0x18001ed44  jz      short loc_18001ED69
0x18001ed46  cmp     byte ptr [rcx+19h], 2
0x18001ed4a  jb      short loc_18001ED69
0x18001ed4c  mov     rcx, [rcx+10h]
0x18001ed50  lea     edx, [rbx+1Ah]
0x18001ed53  not     rdi
0x18001ed56  mov     dword ptr [rsp+68h+var_48], ebp
0x18001ed5a  mov     r9, rdi
0x18001ed5d  lea     r8, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001ed64  call    WPP_SF_qd
0x18001ed69  mov     rcx, r14; lpCriticalSection
0x18001ed6c  call    cs:__imp_LeaveCriticalSection
0x18001ed72  test    rbx, rbx
0x18001ed75  jz      short loc_18001ED84
0x18001ed77  mov     edx, 18h; struct std::nothrow_t *
0x18001ed7c  mov     rcx, rbx; void *
0x18001ed7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ed84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed8b  cmp     rcx, r15
0x18001ed8e  jz      short loc_18001EDB1
0x18001ed90  test    byte ptr [rcx+1Ch], 1
0x18001ed94  jz      short loc_18001EDB1
0x18001ed96  cmp     byte ptr [rcx+19h], 5
0x18001ed9a  jb      short loc_18001EDB1
0x18001ed9c  mov     rcx, [rcx+10h]
0x18001eda0  lea     r8, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001eda7  mov     edx, 1Bh
0x18001edac  call    WPP_SF_
0x18001edb1  mov     eax, ebp
0x18001edb3  add     rsp, 38h
0x18001edb7  pop     r15
0x18001edb9  pop     r14
0x18001edbb  pop     rdi
0x18001edbc  pop     rsi
0x18001edbd  pop     rbp
0x18001edbe  pop     rbx
0x18001edbf  retn
0x18001edc0  mov     rax, [rbx]
0x18001edc3  cmp     [rax+8], rbx
0x18001edc7  jnz     short loc_18001EE20
0x18001edc9  mov     rcx, [rbx+8]
0x18001edcd  cmp     [rcx], rbx
0x18001edd0  jnz     short loc_18001EE20
0x18001edd2  mov     [rcx], rax
0x18001edd5  mov     r8, rdi
0x18001edd8  mov     [rax+8], rcx
0x18001eddc  not     r8
0x18001eddf  dec     dword ptr [rdi+48h]
0x18001ede2  lea     rax, aOnecoreuapDriv_8; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18001ede9  mov     rdx, [rbx+10h]
0x18001eded  xor     ecx, ecx; this
0x18001edef  not     rdx; Apx::ApfVerify *
0x18001edf2  mov     [rsp+68h+var_48], rax
0x18001edf7  mov     r9d, 114h
0x18001edfd  xor     ebp, ebp
0x18001edff  call    imp_ApxObjectDereferenceActual
0x18001ee04  cmp     rbx, [rdi+50h]
0x18001ee08  jnz     loc_18001ED69
0x18001ee0e  xor     eax, eax
0x18001ee10  cmp     [rsi], rsi
0x18001ee13  cmovnz  rax, [rsi]
0x18001ee17  mov     [rdi+50h], rax
0x18001ee1b  jmp     loc_18001ED69
0x18001ee20  mov     ecx, 3
0x18001ee25  int     29h; Win8: RtlFailFast(ecx)
```
