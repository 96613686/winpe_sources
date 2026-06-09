# Apx::ApfDataFormat::IsEqual(Apx::ApfDataFormat *)

- ea: `0x18001cc5c`
- end: `0x18001cec1`
- name: `?IsEqual@ApfDataFormat@Apx@@QEAAEPEAV12@@Z`
- size: `613`
- prototype: `unsigned __int8 __fastcall(Apx::ApfDataFormat *__hidden this, struct Apx::ApfDataFormat *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e500`
- `0x18001e7ec`
- `0x18001ecb4`

## callees

- `0x18000a12c`
- `0x18001cc5c`
- `0x18001cec8`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001ccd7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001ccd7`

## pseudocode

```c
unsigned __int8 __fastcall Apx::ApfDataFormat::IsEqual(Apx::ApfDataFormat *this, struct Apx::ApfDataFormat *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  _WORD *v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rdx
  unsigned __int8 IsEqualCompressed; // si
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // r10
  bool v14; // r8
  __int64 *v15; // rdx
  bool v16; // al
  __int64 v17; // rdx
  __int64 v18; // r8
  bool v19; // zf

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)this + 3);
  if ( !v5 || (v6 = (_WORD *)*((_QWORD *)a2 + 3)) == 0 || *(_WORD *)v5 == *v6 )
  {
    v7 = (_DWORD *)*((_QWORD *)this + 2);
    v8 = (_DWORD *)*((_QWORD *)a2 + 2);
    if ( *v7 == *v8 )
    {
      IsEqualCompressed = RtlCompareMemory(v7, v8, (unsigned int)*v7) == **((unsigned int **)this + 2);
LABEL_10:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_50;
    }
  }
  v10 = *((_QWORD *)this + 2);
  IsEqualCompressed = 0;
  v11 = *((_QWORD *)a2 + 2);
  if ( *(_QWORD *)(v10 + 16) != *(_QWORD *)(v11 + 16)
    || *(_QWORD *)(v10 + 24) != *(_QWORD *)(v11 + 24)
    || *(_QWORD *)(v10 + 32) != *(_QWORD *)(v11 + 32)
    || *(_QWORD *)(v10 + 40) != *(_QWORD *)(v11 + 40)
    || *(_QWORD *)(v10 + 48) != *(_QWORD *)(v11 + 48)
    || *(_QWORD *)(v10 + 56) != *(_QWORD *)(v11 + 56) )
  {
    goto LABEL_50;
  }
  if ( *(_DWORD *)v10 == 64 || *(_DWORD *)v11 == 64 )
    goto LABEL_49;
  if ( !v5 )
    goto LABEL_50;
  v12 = *((_QWORD *)a2 + 3);
  if ( !v12 )
    goto LABEL_50;
  if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 != *(_QWORD *)(v10 + 32)
    || *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 != *(_QWORD *)(v10 + 40) )
  {
    IsEqualCompressed = Apx::ApfDataFormat::IsEqualCompressed(this, a2);
    goto LABEL_10;
  }
  if ( *(_WORD *)v5 == 0xFFFE )
  {
    v13 = *((_QWORD *)this + 4);
  }
  else
  {
    v13 = 0;
    if ( *(_WORD *)v12 == 0xFFFE )
      v13 = *((_QWORD *)a2 + 4);
  }
  if ( *(_WORD *)(v5 + 2) != *(_WORD *)(v12 + 2)
    || *(_DWORD *)(v5 + 4) != *(_DWORD *)(v12 + 4)
    || *(_DWORD *)(v5 + 8) != *(_DWORD *)(v12 + 8)
    || *(_WORD *)(v5 + 12) != *(_WORD *)(v12 + 12)
    || *(_WORD *)(v5 + 14) != *(_WORD *)(v12 + 14) )
  {
    goto LABEL_50;
  }
  v14 = *(_WORD *)v5 == 0xFFFE && *((_QWORD *)this + 4);
  v15 = (__int64 *)((char *)a2 + 32);
  v16 = *(_WORD *)v12 == 0xFFFE && *v15;
  if ( !v14 )
  {
    if ( !v16 )
      goto LABEL_49;
    goto LABEL_47;
  }
  if ( !v16 )
  {
LABEL_47:
    v19 = *(_WORD *)(v13 + 18) == *(_WORD *)(v13 + 14);
LABEL_48:
    if ( !v19 )
      goto LABEL_50;
LABEL_49:
    IsEqualCompressed = 1;
    goto LABEL_50;
  }
  v17 = *v15;
  v18 = *((_QWORD *)this + 4);
  if ( *(_DWORD *)(v18 + 20) == *(_DWORD *)(v17 + 20)
    && *(_QWORD *)(v18 + 24) == *(_QWORD *)(v17 + 24)
    && *(_QWORD *)(v18 + 32) == *(_QWORD *)(v17 + 32) )
  {
    v19 = *(_WORD *)(v18 + 18) == *(_WORD *)(v17 + 18);
    goto LABEL_48;
  }
LABEL_50:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_(v4[2], 26, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
  return IsEqualCompressed;
}

```

## disassembly

```asm
0x18001cc5c  push    rbx
0x18001cc5e  push    rbp
0x18001cc5f  push    rsi
0x18001cc60  push    rdi
0x18001cc61  sub     rsp, 28h
0x18001cc65  mov     rbx, rdx
0x18001cc68  mov     rdi, rcx
0x18001cc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc72  lea     rbp, WPP_GLOBAL_Control
0x18001cc79  cmp     rcx, rbp
0x18001cc7c  jz      short loc_18001CCA6
0x18001cc7e  test    byte ptr [rcx+1Ch], 1
0x18001cc82  jz      short loc_18001CCA6
0x18001cc84  cmp     byte ptr [rcx+19h], 5
0x18001cc88  jb      short loc_18001CCA6
0x18001cc8a  mov     rcx, [rcx+10h]
0x18001cc8e  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cc95  mov     edx, 19h
0x18001cc9a  call    WPP_SF_
0x18001cc9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cca6  mov     r8, [rdi+18h]
0x18001ccaa  test    r8, r8
0x18001ccad  jz      short loc_18001CCC1
0x18001ccaf  mov     rax, [rbx+18h]
0x18001ccb3  test    rax, rax
0x18001ccb6  jz      short loc_18001CCC1
0x18001ccb8  movzx   eax, word ptr [rax]
0x18001ccbb  cmp     [r8], ax
0x18001ccbf  jnz     short loc_18001CCF6
0x18001ccc1  mov     rax, [rdi+10h]
0x18001ccc5  mov     rdx, [rbx+10h]; Source2
0x18001ccc9  mov     r9d, [rax]
0x18001cccc  cmp     r9d, [rdx]
0x18001cccf  jnz     short loc_18001CCF6
0x18001ccd1  mov     r8d, r9d; Length
0x18001ccd4  mov     rcx, rax; Source1
0x18001ccd7  call    cs:__imp_RtlCompareMemory
0x18001ccdd  mov     rcx, [rdi+10h]
0x18001cce1  mov     edx, [rcx]
0x18001cce3  cmp     rax, rdx
0x18001cce6  setz    sil
0x18001ccea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccf1  jmp     loc_18001CE7C
0x18001ccf6  mov     rdx, [rdi+10h]
0x18001ccfa  xor     sil, sil
0x18001ccfd  mov     r9, [rbx+10h]
0x18001cd01  mov     rax, [rdx+10h]
0x18001cd05  cmp     rax, [r9+10h]
0x18001cd09  jnz     loc_18001CE7C
0x18001cd0f  mov     rax, [rdx+18h]
0x18001cd13  cmp     rax, [r9+18h]
0x18001cd17  jnz     loc_18001CE7C
0x18001cd1d  mov     rax, [rdx+20h]
0x18001cd21  cmp     rax, [r9+20h]
0x18001cd25  jnz     loc_18001CE7C
0x18001cd2b  mov     rax, [rdx+28h]
0x18001cd2f  cmp     rax, [r9+28h]
0x18001cd33  jnz     loc_18001CE7C
0x18001cd39  mov     rax, [rdx+30h]
0x18001cd3d  cmp     rax, [r9+30h]
0x18001cd41  jnz     loc_18001CE7C
0x18001cd47  mov     rax, [rdx+38h]
0x18001cd4b  cmp     rax, [r9+38h]
0x18001cd4f  jnz     loc_18001CE7C
0x18001cd55  cmp     dword ptr [rdx], 40h ; '@'
0x18001cd58  jz      loc_18001CE79
0x18001cd5e  cmp     dword ptr [r9], 40h ; '@'
0x18001cd62  jz      loc_18001CE79
0x18001cd68  test    r8, r8
0x18001cd6b  jz      loc_18001CE7C
0x18001cd71  mov     r9, [rbx+18h]
0x18001cd75  test    r9, r9
0x18001cd78  jz      loc_18001CE7C
0x18001cd7e  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x18001cd85  cmp     rax, [rdx+20h]
0x18001cd89  jnz     loc_18001CEAE
0x18001cd8f  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x18001cd96  cmp     rax, [rdx+28h]
0x18001cd9a  jnz     loc_18001CEAE
0x18001cda0  mov     edx, 0FFFEh
0x18001cda5  cmp     [r8], dx
0x18001cda9  jnz     short loc_18001CDB1
0x18001cdab  mov     r10, [rdi+20h]
0x18001cdaf  jmp     short loc_18001CDBE
0x18001cdb1  xor     r10d, r10d
0x18001cdb4  cmp     [r9], dx
0x18001cdb8  jnz     short loc_18001CDBE
0x18001cdba  mov     r10, [rbx+20h]
0x18001cdbe  movzx   eax, word ptr [r9+2]
0x18001cdc3  cmp     [r8+2], ax
0x18001cdc8  jnz     loc_18001CE7C
0x18001cdce  mov     eax, [r9+4]
0x18001cdd2  cmp     [r8+4], eax
0x18001cdd6  jnz     loc_18001CE7C
0x18001cddc  mov     eax, [r9+8]
0x18001cde0  cmp     [r8+8], eax
0x18001cde4  jnz     loc_18001CE7C
0x18001cdea  movzx   eax, word ptr [r9+0Ch]
0x18001cdef  cmp     [r8+0Ch], ax
0x18001cdf4  jnz     loc_18001CE7C
0x18001cdfa  movzx   eax, word ptr [r9+0Eh]
0x18001cdff  cmp     [r8+0Eh], ax
0x18001ce04  jnz     short loc_18001CE7C
0x18001ce06  cmp     [r8], dx
0x18001ce0a  jnz     short loc_18001CE18
0x18001ce0c  cmp     qword ptr [rdi+20h], 0
0x18001ce11  jz      short loc_18001CE18
0x18001ce13  mov     r8b, 1
0x18001ce16  jmp     short loc_18001CE1B
0x18001ce18  xor     r8b, r8b
0x18001ce1b  cmp     [r9], dx
0x18001ce1f  lea     rdx, [rbx+20h]
0x18001ce23  jnz     short loc_18001CE2F
0x18001ce25  cmp     qword ptr [rdx], 0
0x18001ce29  jz      short loc_18001CE2F
0x18001ce2b  mov     al, 1
0x18001ce2d  jmp     short loc_18001CE31
0x18001ce2f  xor     al, al
0x18001ce31  test    r8b, r8b
0x18001ce34  jz      short loc_18001CE69
0x18001ce36  test    al, al
0x18001ce38  jz      short loc_18001CE6D
0x18001ce3a  mov     rdx, [rdx]
0x18001ce3d  mov     r8, [rdi+20h]
0x18001ce41  mov     eax, [rdx+14h]
0x18001ce44  cmp     [r8+14h], eax
0x18001ce48  jnz     short loc_18001CE7C
0x18001ce4a  mov     rax, [r8+18h]
0x18001ce4e  cmp     rax, [rdx+18h]
0x18001ce52  jnz     short loc_18001CE7C
0x18001ce54  mov     rax, [r8+20h]
0x18001ce58  cmp     rax, [rdx+20h]
0x18001ce5c  jnz     short loc_18001CE7C
0x18001ce5e  movzx   eax, word ptr [rdx+12h]
0x18001ce62  cmp     [r8+12h], ax
0x18001ce67  jmp     short loc_18001CE77
0x18001ce69  test    al, al
0x18001ce6b  jz      short loc_18001CE79
0x18001ce6d  movzx   eax, word ptr [r10+0Eh]
0x18001ce72  cmp     [r10+12h], ax
0x18001ce77  jnz     short loc_18001CE7C
0x18001ce79  mov     sil, 1
0x18001ce7c  cmp     rcx, rbp
0x18001ce7f  jz      short loc_18001CEA2
0x18001ce81  test    byte ptr [rcx+1Ch], 1
0x18001ce85  jz      short loc_18001CEA2
0x18001ce87  cmp     byte ptr [rcx+19h], 5
0x18001ce8b  jb      short loc_18001CEA2
0x18001ce8d  mov     rcx, [rcx+10h]
0x18001ce91  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001ce98  mov     edx, 1Ah
0x18001ce9d  call    WPP_SF_
0x18001cea2  mov     al, sil
0x18001cea5  add     rsp, 28h
0x18001cea9  pop     rdi
0x18001ceaa  pop     rsi
0x18001ceab  pop     rbp
0x18001ceac  pop     rbx
0x18001cead  retn
0x18001ceae  mov     rdx, rbx; struct Apx::ApfDataFormat *
0x18001ceb1  mov     rcx, rdi; this
0x18001ceb4  call    ?IsEqualCompressed@ApfDataFormat@Apx@@AEAAEPEAV12@@Z; Apx::ApfDataFormat::IsEqualCompressed(Apx::ApfDataFormat *)
0x18001ceb9  mov     sil, al
0x18001cebc  jmp     loc_18001CCEA
```
