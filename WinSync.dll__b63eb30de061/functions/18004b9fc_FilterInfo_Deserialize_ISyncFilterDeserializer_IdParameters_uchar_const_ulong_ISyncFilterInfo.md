# FilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)

- ea: `0x18004b9fc`
- end: `0x18004bbcf`
- name: `?Deserialize@FilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct ISyncFilterDeserializer *, struct IdParameters *, const unsigned __int8 *, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cba0`
- `0x18004e754`
- `0x18005e830`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18004afb8`
- `0x18004b9fc`
- `0x18004bc90`
- `0x18005e250`
- `0x18005e830`

## string_xrefs

- `0x18004ba3c`: `FilterInfo::Deserialize`
- `0x18004bba0`: `FilterInfo::Deserialize`

## pseudocode

```c
__int64 __fastcall FilterInfo::Deserialize(
        struct ISyncFilterDeserializer *a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct ISyncFilterInfo **a5)
{
  __int64 v5; // rbp
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // ebx

  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_0976fd36ef013270fe9fdf996a13cf1d_Traceguids,
      "FilterInfo::Deserialize");
  }
  if ( !a2 || !a3 || !a5 )
  {
    v11 = -2147467261;
    goto LABEL_23;
  }
  if ( &a3[v5] >= a3 && (unsigned int)v5 >= 0xC )
  {
    v9 = a3[11] | ((a3[10] | (((a3[8] << 8) | a3[9]) << 8)) << 8);
    if ( (unsigned int)FilterInfo::IsValid(
                         (a3[7] | ((a3[6] | ((((unsigned __int64)a3[4] << 8) | a3[5]) << 8)) << 8))
                       + ((a3[3] | ((a3[2] | ((a3[1] | ((unsigned __int64)*a3 << 8)) << 8)) << 8)) << 32),
                         v9) )
    {
      if ( !v9 || (v9 & 3) != 0 )
      {
        v10 = ListBasedFilterInfo::Deserialize(v9, a2, a3 + 12, (int)v5 - 12, a5);
        goto LABEL_20;
      }
      if ( (v9 & 4) != 0 )
      {
        if ( a1 )
        {
          v10 = CustomFilterInfo::Deserialize(a1, a2, a3 + 12, v5 - 12, a5);
LABEL_20:
          v11 = v10;
          goto LABEL_23;
        }
      }
      else
      {
        v11 = 0;
        if ( (v9 & 8) == 0 )
          goto LABEL_23;
        if ( a1 )
        {
          v10 = CombinedFilterInfo::Deserialize(a1, a2, a3 + 12, (int)v5 - 12, a5);
          goto LABEL_20;
        }
      }
    }
  }
  v11 = -2147217396;
LABEL_23:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_0976fd36ef013270fe9fdf996a13cf1d_Traceguids,
      (unsigned int)"FilterInfo::Deserialize",
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18004b9fc  push    rbx
0x18004b9fe  push    rbp
0x18004b9ff  push    rsi
0x18004ba00  push    rdi
0x18004ba01  push    r12
0x18004ba03  push    r13
0x18004ba05  push    r14
0x18004ba07  push    r15
0x18004ba09  sub     rsp, 38h
0x18004ba0d  mov     ebp, r9d
0x18004ba10  mov     rdi, r8
0x18004ba13  mov     r12, rdx
0x18004ba16  mov     r15, rcx
0x18004ba19  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba20  lea     r13, WPP_GLOBAL_Control
0x18004ba27  cmp     rcx, r13
0x18004ba2a  jz      short loc_18004BA54
0x18004ba2c  test    byte ptr [rcx+1Ch], 40h
0x18004ba30  jz      short loc_18004BA54
0x18004ba32  cmp     byte ptr [rcx+19h], 5
0x18004ba36  jb      short loc_18004BA54
0x18004ba38  mov     rcx, [rcx+10h]
0x18004ba3c  lea     r9, aFilterinfoDese; "FilterInfo::Deserialize"
0x18004ba43  mov     edx, 10h
0x18004ba48  lea     r8, WPP_0976fd36ef013270fe9fdf996a13cf1d_Traceguids
0x18004ba4f  call    WPP_SF_s
0x18004ba54  test    r12, r12
0x18004ba57  jz      loc_18004BB7F
0x18004ba5d  test    rdi, rdi
0x18004ba60  jz      loc_18004BB7F
0x18004ba66  mov     r14, [rsp+78h+arg_20]
0x18004ba6e  test    r14, r14
0x18004ba71  jz      loc_18004BB7F
0x18004ba77  lea     rax, [rdi+rbp]
0x18004ba7b  cmp     rax, rdi
0x18004ba7e  jb      loc_18004BB36
0x18004ba84  cmp     ebp, 0Ch
0x18004ba87  jb      loc_18004BB36
0x18004ba8d  movzx   eax, byte ptr [rdi+8]
0x18004ba91  movzx   esi, byte ptr [rdi+9]
0x18004ba95  movzx   ecx, byte ptr [rdi]
0x18004ba98  movzx   edx, byte ptr [rdi+5]
0x18004ba9c  shl     eax, 8
0x18004ba9f  or      esi, eax
0x18004baa1  shl     rcx, 8
0x18004baa5  movzx   eax, byte ptr [rdi+0Ah]
0x18004baa9  shl     esi, 8
0x18004baac  or      esi, eax
0x18004baae  movzx   eax, byte ptr [rdi+0Bh]
0x18004bab2  shl     esi, 8
0x18004bab5  or      esi, eax
0x18004bab7  movzx   eax, byte ptr [rdi+1]
0x18004babb  or      rcx, rax
0x18004babe  movzx   eax, byte ptr [rdi+2]
0x18004bac2  shl     rcx, 8
0x18004bac6  or      rcx, rax
0x18004bac9  movzx   eax, byte ptr [rdi+3]
0x18004bacd  shl     rcx, 8
0x18004bad1  or      rcx, rax
0x18004bad4  movzx   eax, byte ptr [rdi+4]
0x18004bad8  shl     rax, 8
0x18004badc  or      rdx, rax
0x18004badf  shl     rcx, 20h
0x18004bae3  movzx   eax, byte ptr [rdi+6]
0x18004bae7  shl     rdx, 8
0x18004baeb  or      rdx, rax
0x18004baee  movzx   eax, byte ptr [rdi+7]
0x18004baf2  shl     rdx, 8
0x18004baf6  or      rdx, rax
0x18004baf9  add     rcx, rdx; unsigned __int64
0x18004bafc  mov     edx, esi; unsigned int
0x18004bafe  call    ?IsValid@FilterInfo@@CAH_KK@Z; FilterInfo::IsValid(unsigned __int64,ulong)
0x18004bb03  test    eax, eax
0x18004bb05  jz      short loc_18004BB36
0x18004bb07  test    esi, esi
0x18004bb09  jz      short loc_18004BB66
0x18004bb0b  test    sil, 3
0x18004bb0f  jnz     short loc_18004BB66
0x18004bb11  test    sil, 4
0x18004bb15  jz      short loc_18004BB3D
0x18004bb17  test    r15, r15
0x18004bb1a  jz      short loc_18004BB36
0x18004bb1c  lea     r9d, [rbp-0Ch]; unsigned int
0x18004bb20  mov     [rsp+78h+var_58], r14; struct ISyncFilterInfo **
0x18004bb25  lea     r8, [rdi+0Ch]; unsigned __int8 *
0x18004bb29  mov     rdx, r12; struct IdParameters *
0x18004bb2c  mov     rcx, r15; struct ISyncFilterDeserializer *
0x18004bb2f  call    ?Deserialize@CustomFilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; CustomFilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18004bb34  jmp     short loc_18004BB62
0x18004bb36  mov     ebx, 8004100Ch
0x18004bb3b  jmp     short loc_18004BB84
0x18004bb3d  xor     ebx, ebx
0x18004bb3f  test    sil, 8
0x18004bb43  jz      short loc_18004BB84
0x18004bb45  test    r15, r15
0x18004bb48  jz      short loc_18004BB36
0x18004bb4a  lea     r9d, [rbp-0Ch]; unsigned int
0x18004bb4e  mov     [rsp+78h+var_58], r14; struct ISyncFilterInfo **
0x18004bb53  lea     r8, [rdi+0Ch]; unsigned __int8 *
0x18004bb57  mov     rdx, r12; struct IdParameters *
0x18004bb5a  mov     rcx, r15; struct ISyncFilterDeserializer *
0x18004bb5d  call    ?Deserialize@CombinedFilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; CombinedFilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18004bb62  mov     ebx, eax
0x18004bb64  jmp     short loc_18004BB84
0x18004bb66  lea     r9d, [rbp-0Ch]; unsigned int
0x18004bb6a  mov     [rsp+78h+var_58], r14; struct ISyncFilterInfo **
0x18004bb6f  lea     r8, [rdi+0Ch]; unsigned __int8 *
0x18004bb73  mov     rdx, r12; struct IdParameters *
0x18004bb76  mov     ecx, esi; unsigned int
0x18004bb78  call    ?Deserialize@ListBasedFilterInfo@@SAJKPEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; ListBasedFilterInfo::Deserialize(ulong,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18004bb7d  jmp     short loc_18004BB62
0x18004bb7f  mov     ebx, 80004003h
0x18004bb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb8b  cmp     rcx, r13
0x18004bb8e  jz      short loc_18004BBBC
0x18004bb90  test    byte ptr [rcx+1Ch], 40h
0x18004bb94  jz      short loc_18004BBBC
0x18004bb96  cmp     byte ptr [rcx+19h], 5
0x18004bb9a  jb      short loc_18004BBBC
0x18004bb9c  mov     rcx, [rcx+10h]
0x18004bba0  lea     r9, aFilterinfoDese; "FilterInfo::Deserialize"
0x18004bba7  mov     edx, 11h
0x18004bbac  mov     dword ptr [rsp+78h+var_58], ebx
0x18004bbb0  lea     r8, WPP_0976fd36ef013270fe9fdf996a13cf1d_Traceguids
0x18004bbb7  call    WPP_SF_sD
0x18004bbbc  mov     eax, ebx
0x18004bbbe  add     rsp, 38h
0x18004bbc2  pop     r15
0x18004bbc4  pop     r14
0x18004bbc6  pop     r13
0x18004bbc8  pop     r12
0x18004bbca  pop     rdi
0x18004bbcb  pop     rsi
0x18004bbcc  pop     rbp
0x18004bbcd  pop     rbx
0x18004bbce  retn
```
