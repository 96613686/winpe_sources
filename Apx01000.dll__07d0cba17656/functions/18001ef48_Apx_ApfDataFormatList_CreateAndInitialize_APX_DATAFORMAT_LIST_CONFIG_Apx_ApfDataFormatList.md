# Apx::ApfDataFormatList::_CreateAndInitialize(_APX_DATAFORMAT_LIST_CONFIG *,Apx::ApfDataFormatList * *)

- ea: `0x18001ef48`
- end: `0x18001f078`
- name: `?_CreateAndInitialize@ApfDataFormatList@Apx@@SAJPEAU_APX_DATAFORMAT_LIST_CONFIG@@PEAPEAV12@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct _APX_DATAFORMAT_LIST_CONFIG *, struct Apx::ApfDataFormatList **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001f1d0`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18001e5fc`
- `0x18001ef48`

## pseudocode

```c
__int64 __fastcall Apx::ApfDataFormatList::_CreateAndInitialize(
        struct _APX_DATAFORMAT_LIST_CONFIG *a1,
        struct Apx::ApfDataFormatList **a2)
{
  Apx::ApfDataFormatList *v3; // rax
  struct Apx::ApfDataFormatList *v4; // rbx
  _QWORD *v5; // rcx
  unsigned int v6; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  }
  v3 = (Apx::ApfDataFormatList *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 && (v4 = (struct Apx::ApfDataFormatList *)Apx::ApfDataFormatList::ApfDataFormatList(v3)) != 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 5u )
      {
        WPP_SF_(v5[2], 18, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
        v5 = WPP_GLOBAL_Control;
      }
    }
    *a2 = v4;
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 5u )
    WPP_SF_(v5[2], 12, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x18001ef48  push    rbx
0x18001ef4a  push    rsi
0x18001ef4b  push    rdi
0x18001ef4c  push    r15
0x18001ef4e  sub     rsp, 28h
0x18001ef52  mov     rdi, rdx
0x18001ef55  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef5c  lea     rsi, WPP_GLOBAL_Control
0x18001ef63  lea     r15, WPP_48429167f7a835f80a7c5fb5ed8b8902_Traceguids
0x18001ef6a  cmp     rcx, rsi
0x18001ef6d  jz      short loc_18001EF8C
0x18001ef6f  test    byte ptr [rcx+1Ch], 1
0x18001ef73  jz      short loc_18001EF8C
0x18001ef75  cmp     byte ptr [rcx+19h], 5
0x18001ef79  jb      short loc_18001EF8C
0x18001ef7b  mov     rcx, [rcx+10h]
0x18001ef7f  mov     edx, 0Ah
0x18001ef84  mov     r8, r15
0x18001ef87  call    WPP_SF_
0x18001ef8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ef93  mov     ecx, 60h ; '`'; unsigned __int64
0x18001ef98  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ef9d  test    rax, rax
0x18001efa0  jz      short loc_18001F012
0x18001efa2  mov     rcx, rax; this
0x18001efa5  call    ??0ApfDataFormatList@Apx@@AEAA@XZ; Apx::ApfDataFormatList::ApfDataFormatList(void)
0x18001efaa  mov     rbx, rax
0x18001efad  test    rax, rax
0x18001efb0  jz      short loc_18001F012
0x18001efb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efb9  cmp     rcx, rsi
0x18001efbc  jz      short loc_18001F00B
0x18001efbe  test    byte ptr [rcx+1Ch], 1
0x18001efc2  jz      short loc_18001EFE2
0x18001efc4  cmp     byte ptr [rcx+19h], 5
0x18001efc8  jb      short loc_18001EFE2
0x18001efca  mov     rcx, [rcx+10h]
0x18001efce  mov     edx, 11h
0x18001efd3  mov     r8, r15
0x18001efd6  call    WPP_SF_
0x18001efdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efe2  cmp     rcx, rsi
0x18001efe5  jz      short loc_18001F00B
0x18001efe7  test    byte ptr [rcx+1Ch], 1
0x18001efeb  jz      short loc_18001F00B
0x18001efed  cmp     byte ptr [rcx+19h], 5
0x18001eff1  jb      short loc_18001F00B
0x18001eff3  mov     rcx, [rcx+10h]
0x18001eff7  mov     edx, 12h
0x18001effc  mov     r8, r15
0x18001efff  call    WPP_SF_
0x18001f004  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f00b  mov     [rdi], rbx
0x18001f00e  xor     ebx, ebx
0x18001f010  jmp     short loc_18001F04A
0x18001f012  mov     ebx, 8007000Eh
0x18001f017  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f01e  cmp     rcx, rsi
0x18001f021  jz      short loc_18001F06C
0x18001f023  test    byte ptr [rcx+1Ch], 20h
0x18001f027  jz      short loc_18001F04A
0x18001f029  cmp     byte ptr [rcx+19h], 2
0x18001f02d  jb      short loc_18001F04A
0x18001f02f  mov     rcx, [rcx+10h]
0x18001f033  mov     edx, 0Bh
0x18001f038  mov     r9d, ebx
0x18001f03b  mov     r8, r15
0x18001f03e  call    WPP_SF_d
0x18001f043  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f04a  cmp     rcx, rsi
0x18001f04d  jz      short loc_18001F06C
0x18001f04f  test    byte ptr [rcx+1Ch], 1
0x18001f053  jz      short loc_18001F06C
0x18001f055  cmp     byte ptr [rcx+19h], 5
0x18001f059  jb      short loc_18001F06C
0x18001f05b  mov     rcx, [rcx+10h]
0x18001f05f  mov     edx, 0Ch
0x18001f064  mov     r8, r15
0x18001f067  call    WPP_SF_
0x18001f06c  mov     eax, ebx
0x18001f06e  add     rsp, 28h
0x18001f072  pop     r15
0x18001f074  pop     rdi
0x18001f075  pop     rsi
0x18001f076  pop     rbx
0x18001f077  retn
```
