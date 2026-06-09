# MStringRemove(ushort const *,ushort const *,CBuffer &)

- ea: `0x18002a118`
- end: `0x18002a27f`
- name: `?MStringRemove@@YAKPEBG0AEAVCBuffer@@@Z`
- size: `359`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct CBuffer *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ad8c`
- `0x18002b2d8`

## callees

- `0x180003fc0`
- `0x18000a290`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000e3d0`
- `0x18002a118`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a1a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a1a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MStringRemove(const unsigned __int16 *a1, const unsigned __int16 *a2, struct CBuffer *a3)
{
  unsigned int v5; // edi
  unsigned __int16 *v6; // rcx
  const unsigned __int16 *String; // rbx
  unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // rax
  int v10; // eax
  __int64 v11; // r8
  const WCHAR *v12; // rsi
  __int64 v13; // r8
  unsigned int v14; // r8d
  const int *v16; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v17; // [rsp+28h] [rbp-28h]
  __int64 v18; // [rsp+30h] [rbp-20h]
  const int *v19; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-10h]
  __int64 v21; // [rsp+48h] [rbp-8h]

  v19 = &CBuffer::`vftable';
  v20 = 0;
  v21 = 0;
  v16 = &CBuffer::`vftable';
  v17 = 0;
  v18 = 0;
  v5 = 0;
  *((_DWORD *)a3 + 4) = 0;
  MStringSort(a1, (struct CBuffer *)&v19);
  MStringSort(a2, (struct CBuffer *)&v16);
  v6 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v21) )
    v6 = v20;
  String = FirstString(v6);
  v8 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v18) )
    v8 = v17;
  v9 = FirstString(v8);
LABEL_14:
  v12 = v9;
  while ( String )
  {
    if ( !v12 )
    {
      do
      {
        v13 = -1;
        do
          ++v13;
        while ( String[v13] );
        CBuffer::Append(a3, (const unsigned __int8 *const)String, 2 * v13 + 2);
        String = NextString(String);
        ++v5;
      }
      while ( String );
      break;
    }
    v10 = lstrcmpiW(String, v12);
    if ( v10 >= 0 )
    {
      if ( v10 <= 0 )
        String = NextString(String);
      v9 = NextString(v12);
      goto LABEL_14;
    }
    v11 = -1;
    do
      ++v11;
    while ( String[v11] );
    CBuffer::Append(a3, (const unsigned __int8 *const)String, 2 * v11 + 2);
    String = NextString(String);
    ++v5;
  }
  v14 = 4;
  if ( v5 )
    v14 = 2;
  CBuffer::Append(a3, (const unsigned __int8 *const)&WideCharStr, v14);
  v16 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v16);
  v19 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v19);
  return v5;
}

```

## disassembly

```asm
0x18002a118  push    rbp
0x18002a11a  push    rbx
0x18002a11b  push    rsi
0x18002a11c  push    rdi
0x18002a11d  push    r13
0x18002a11f  push    r14
0x18002a121  push    r15
0x18002a123  mov     rbp, rsp
0x18002a126  sub     rsp, 50h
0x18002a12a  mov     r14, r8
0x18002a12d  mov     rbx, rdx
0x18002a130  lea     r13, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002a137  mov     [rbp+var_18], r13
0x18002a13b  xor     r15d, r15d
0x18002a13e  mov     [rbp+var_10], r15
0x18002a142  mov     [rbp+var_8], r15
0x18002a146  mov     [rbp+var_30], r13
0x18002a14a  mov     [rbp+var_28], r15
0x18002a14e  mov     [rbp+var_20], r15
0x18002a152  mov     edi, r15d
0x18002a155  mov     [r8+10h], r15d
0x18002a159  lea     rdx, [rbp+var_18]; struct CBuffer *
0x18002a15d  call    ?MStringSort@@YAKPEBGAEAVCBuffer@@@Z; MStringSort(ushort const *,CBuffer &)
0x18002a162  lea     rdx, [rbp+var_30]; struct CBuffer *
0x18002a166  mov     rcx, rbx; unsigned __int16 *
0x18002a169  call    ?MStringSort@@YAKPEBGAEAVCBuffer@@@Z; MStringSort(ushort const *,CBuffer &)
0x18002a16e  lea     rcx, WideCharStr
0x18002a175  cmp     dword ptr [rbp+var_8+4], r15d
0x18002a179  cmova   rcx, [rbp+var_10]; unsigned __int16 *
0x18002a17e  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18002a183  mov     rbx, rax
0x18002a186  lea     rcx, WideCharStr
0x18002a18d  cmp     dword ptr [rbp+var_20+4], r15d
0x18002a191  cmova   rcx, [rbp+var_28]; unsigned __int16 *
0x18002a196  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18002a19b  jmp     short loc_18002A1F7
0x18002a19d  test    rsi, rsi
0x18002a1a0  jz      short loc_18002A201
0x18002a1a2  mov     rdx, rsi; lpString2
0x18002a1a5  mov     rcx, rbx; lpString1
0x18002a1a8  call    cs:__imp_lstrcmpiW
0x18002a1ae  test    eax, eax
0x18002a1b0  jns     short loc_18002A1E2
0x18002a1b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a1b6  inc     r8
0x18002a1b9  cmp     [rbx+r8*2], r15w
0x18002a1be  jnz     short loc_18002A1B6
0x18002a1c0  lea     r8d, ds:2[r8*2]; unsigned int
0x18002a1c8  mov     rdx, rbx; unsigned __int8 *
0x18002a1cb  mov     rcx, r14; this
0x18002a1ce  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002a1d3  mov     rcx, rbx; unsigned __int16 *
0x18002a1d6  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002a1db  mov     rbx, rax
0x18002a1de  inc     edi
0x18002a1e0  jmp     short loc_18002A1FA
0x18002a1e2  jg      short loc_18002A1EF
0x18002a1e4  mov     rcx, rbx; unsigned __int16 *
0x18002a1e7  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002a1ec  mov     rbx, rax
0x18002a1ef  mov     rcx, rsi; unsigned __int16 *
0x18002a1f2  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002a1f7  mov     rsi, rax
0x18002a1fa  test    rbx, rbx
0x18002a1fd  jnz     short loc_18002A19D
0x18002a1ff  jmp     short loc_18002A234
0x18002a201  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a205  inc     r8
0x18002a208  cmp     [rbx+r8*2], r15w
0x18002a20d  jnz     short loc_18002A205
0x18002a20f  lea     r8d, ds:2[r8*2]; unsigned int
0x18002a217  mov     rdx, rbx; unsigned __int8 *
0x18002a21a  mov     rcx, r14; this
0x18002a21d  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002a222  mov     rcx, rbx; unsigned __int16 *
0x18002a225  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002a22a  mov     rbx, rax
0x18002a22d  inc     edi
0x18002a22f  test    rax, rax
0x18002a232  jnz     short loc_18002A201
0x18002a234  mov     eax, 2
0x18002a239  lea     r8d, [rax+2]
0x18002a23d  test    edi, edi
0x18002a23f  cmovnz  r8d, eax; unsigned int
0x18002a243  lea     rdx, WideCharStr; unsigned __int8 *
0x18002a24a  mov     rcx, r14; this
0x18002a24d  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002a252  nop
0x18002a253  mov     [rbp+var_30], r13
0x18002a257  lea     rcx, [rbp+var_30]; this
0x18002a25b  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002a260  nop
0x18002a261  mov     [rbp+var_18], r13
0x18002a265  lea     rcx, [rbp+var_18]; this
0x18002a269  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002a26e  mov     eax, edi
0x18002a270  add     rsp, 50h
0x18002a274  pop     r15
0x18002a276  pop     r14
0x18002a278  pop     r13
0x18002a27a  pop     rdi
0x18002a27b  pop     rsi
0x18002a27c  pop     rbx
0x18002a27d  pop     rbp
0x18002a27e  retn
```
