# FwCopyAuthSet

- ea: `0x1800159a0`
- end: `0x180015c49`
- name: `FwCopyAuthSet`
- size: `681`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180021f20`
- `0x180022250`

## callees

- `0x1800042c4`
- `0x1800159a0`
- `0x180015c50`
- `0x18001e400`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x1800159c3`
- `fwbase!FwAlloc` at `0x1800159c3`
- `fwbase!FwStringCopy` at `0x180015ad3`
- `fwbase!FwStringCopy` at `0x180015b15`
- `fwbase!FwStringCopy` at `0x180015b57`
- `fwbase!FwStringCopy` at `0x180015b96`
- `fwbase!FwStringCopy` at `0x180015bcd`
- `fwbase!FwStringCopy` at `0x180015ad3`
- `fwbase!FwStringCopy` at `0x180015b15`
- `fwbase!FwStringCopy` at `0x180015b57`
- `fwbase!FwStringCopy` at `0x180015b96`
- `fwbase!FwStringCopy` at `0x180015bcd`
- `fwbase!FwAllocCheckSize` at `0x180015a4c`
- `fwbase!FwAllocCheckSize` at `0x180015a4c`

## pseudocode

```c
__int64 __fastcall FwCopyAuthSet(__int64 a1, _QWORD *a2)
{
  void *v4; // rax
  int v5; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(88);
  *a2 = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 102;
    goto LABEL_33;
  }
  memset_0(v4, 0, 0x58u);
  *(_WORD *)(*a2 + 8LL) = *(_WORD *)(a1 + 8);
  *(_DWORD *)(*a2 + 12LL) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(*a2 + 64LL) = *(_DWORD *)(a1 + 64);
  *(_DWORD *)(*a2 + 80LL) = *(_DWORD *)(a1 + 80);
  *(_DWORD *)(*a2 + 48LL) = *(_DWORD *)(a1 + 48);
  v5 = FwAllocCheckSize(24, *(unsigned int *)(a1 + 48), *a2 + 56LL);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 103;
    goto LABEL_33;
  }
  v5 = FwCopyAuthSuites(
         *(struct _tag_FW_AUTH_SUITE **)(a1 + 56),
         *(struct _tag_FW_AUTH_SUITE **)(*a2 + 56LL),
         *(_DWORD *)(a1 + 48));
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 104;
    goto LABEL_33;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 16), *a2 + 16LL);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 105;
    goto LABEL_33;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 24), *a2 + 24LL);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 106;
    goto LABEL_33;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 32), *a2 + 32LL);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 107;
    goto LABEL_33;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 40), *a2 + 40LL);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v7 = 108;
    goto LABEL_33;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 72), *a2 + 72LL);
  if ( v5 >= 0 )
  {
    *(_DWORD *)(*a2 + 64LL) = *(_DWORD *)(a1 + 64);
    *(_DWORD *)(*a2 + 80LL) = *(_DWORD *)(a1 + 80);
    *(_QWORD *)*a2 = 0;
    return (unsigned int)v5;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v7 = 109;
LABEL_33:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
  }
LABEL_34:
  FwAuthSetFree(*a2);
  *a2 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800159a0  mov     [rsp+arg_0], rbx
0x1800159a5  mov     [rsp+arg_8], rsi
0x1800159aa  push    rdi
0x1800159ab  sub     rsp, 20h
0x1800159af  mov     rsi, rcx
0x1800159b2  mov     qword ptr [rdx], 0
0x1800159b9  mov     ebx, 58h ; 'X'
0x1800159be  mov     rdi, rdx
0x1800159c1  mov     ecx, ebx
0x1800159c3  call    cs:__imp_FwAlloc
0x1800159c9  mov     [rdi], rax
0x1800159cc  test    rax, rax
0x1800159cf  jnz     short loc_180015A01
0x1800159d1  mov     ebx, 8007000Eh
0x1800159d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159dd  lea     rax, WPP_GLOBAL_Control
0x1800159e4  cmp     rcx, rax
0x1800159e7  jz      loc_180015C0A
0x1800159ed  test    byte ptr [rcx+1Ch], 1
0x1800159f1  jz      loc_180015C0A
0x1800159f7  mov     edx, 66h ; 'f'
0x1800159fc  jmp     loc_180015BF7
0x180015a01  mov     r8, rbx; Size
0x180015a04  xor     edx, edx; Val
0x180015a06  mov     rcx, rax; void *
0x180015a09  call    memset_0
0x180015a0e  mov     rcx, [rdi]
0x180015a11  movzx   eax, word ptr [rsi+8]
0x180015a15  mov     [rcx+8], ax
0x180015a19  mov     rcx, [rdi]
0x180015a1c  mov     eax, [rsi+0Ch]
0x180015a1f  mov     [rcx+0Ch], eax
0x180015a22  mov     rcx, [rdi]
0x180015a25  mov     eax, [rsi+40h]
0x180015a28  mov     [rcx+40h], eax
0x180015a2b  mov     rcx, [rdi]
0x180015a2e  mov     eax, [rsi+50h]
0x180015a31  mov     [rcx+50h], eax
0x180015a34  mov     rcx, [rdi]
0x180015a37  mov     eax, [rsi+30h]
0x180015a3a  mov     [rcx+30h], eax
0x180015a3d  mov     ecx, 18h
0x180015a42  mov     r8, [rdi]
0x180015a45  mov     edx, [rsi+30h]
0x180015a48  add     r8, 38h ; '8'
0x180015a4c  call    cs:__imp_FwAllocCheckSize
0x180015a52  mov     ebx, eax
0x180015a54  test    eax, eax
0x180015a56  jns     short loc_180015A83
0x180015a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a5f  lea     rax, WPP_GLOBAL_Control
0x180015a66  cmp     rcx, rax
0x180015a69  jz      loc_180015C0A
0x180015a6f  test    byte ptr [rcx+1Ch], 1
0x180015a73  jz      loc_180015C0A
0x180015a79  mov     edx, 67h ; 'g'
0x180015a7e  jmp     loc_180015BF7
0x180015a83  mov     rdx, [rdi]
0x180015a86  mov     r8d, [rsi+30h]; unsigned int
0x180015a8a  mov     rcx, [rsi+38h]; struct _tag_FW_AUTH_SUITE *
0x180015a8e  mov     rdx, [rdx+38h]; struct _tag_FW_AUTH_SUITE *
0x180015a92  call    ?FwCopyAuthSuites@@YAJPEAU_tag_FW_AUTH_SUITE@@0K@Z; FwCopyAuthSuites(_tag_FW_AUTH_SUITE *,_tag_FW_AUTH_SUITE *,ulong)
0x180015a97  mov     ebx, eax
0x180015a99  test    eax, eax
0x180015a9b  jns     short loc_180015AC8
0x180015a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aa4  lea     rax, WPP_GLOBAL_Control
0x180015aab  cmp     rcx, rax
0x180015aae  jz      loc_180015C0A
0x180015ab4  test    byte ptr [rcx+1Ch], 1
0x180015ab8  jz      loc_180015C0A
0x180015abe  mov     edx, 68h ; 'h'
0x180015ac3  jmp     loc_180015BF7
0x180015ac8  mov     rdx, [rdi]
0x180015acb  mov     rcx, [rsi+10h]
0x180015acf  add     rdx, 10h
0x180015ad3  call    cs:__imp_FwStringCopy
0x180015ad9  mov     ebx, eax
0x180015adb  test    eax, eax
0x180015add  jns     short loc_180015B0A
0x180015adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ae6  lea     rax, WPP_GLOBAL_Control
0x180015aed  cmp     rcx, rax
0x180015af0  jz      loc_180015C0A
0x180015af6  test    byte ptr [rcx+1Ch], 1
0x180015afa  jz      loc_180015C0A
0x180015b00  mov     edx, 69h ; 'i'
0x180015b05  jmp     loc_180015BF7
0x180015b0a  mov     rdx, [rdi]
0x180015b0d  mov     rcx, [rsi+18h]
0x180015b11  add     rdx, 18h
0x180015b15  call    cs:__imp_FwStringCopy
0x180015b1b  mov     ebx, eax
0x180015b1d  test    eax, eax
0x180015b1f  jns     short loc_180015B4C
0x180015b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b28  lea     rax, WPP_GLOBAL_Control
0x180015b2f  cmp     rcx, rax
0x180015b32  jz      loc_180015C0A
0x180015b38  test    byte ptr [rcx+1Ch], 1
0x180015b3c  jz      loc_180015C0A
0x180015b42  mov     edx, 6Ah ; 'j'
0x180015b47  jmp     loc_180015BF7
0x180015b4c  mov     rdx, [rdi]
0x180015b4f  mov     rcx, [rsi+20h]
0x180015b53  add     rdx, 20h ; ' '
0x180015b57  call    cs:__imp_FwStringCopy
0x180015b5d  mov     ebx, eax
0x180015b5f  test    eax, eax
0x180015b61  jns     short loc_180015B8B
0x180015b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b6a  lea     rax, WPP_GLOBAL_Control
0x180015b71  cmp     rcx, rax
0x180015b74  jz      loc_180015C0A
0x180015b7a  test    byte ptr [rcx+1Ch], 1
0x180015b7e  jz      loc_180015C0A
0x180015b84  mov     edx, 6Bh ; 'k'
0x180015b89  jmp     short loc_180015BF7
0x180015b8b  mov     rdx, [rdi]
0x180015b8e  mov     rcx, [rsi+28h]
0x180015b92  add     rdx, 28h ; '('
0x180015b96  call    cs:__imp_FwStringCopy
0x180015b9c  mov     ebx, eax
0x180015b9e  test    eax, eax
0x180015ba0  jns     short loc_180015BC2
0x180015ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ba9  lea     rax, WPP_GLOBAL_Control
0x180015bb0  cmp     rcx, rax
0x180015bb3  jz      short loc_180015C0A
0x180015bb5  test    byte ptr [rcx+1Ch], 1
0x180015bb9  jz      short loc_180015C0A
0x180015bbb  mov     edx, 6Ch ; 'l'
0x180015bc0  jmp     short loc_180015BF7
0x180015bc2  mov     rdx, [rdi]
0x180015bc5  mov     rcx, [rsi+48h]
0x180015bc9  add     rdx, 48h ; 'H'
0x180015bcd  call    cs:__imp_FwStringCopy
0x180015bd3  mov     ebx, eax
0x180015bd5  test    eax, eax
0x180015bd7  jns     short loc_180015C1B
0x180015bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015be0  lea     rax, WPP_GLOBAL_Control
0x180015be7  cmp     rcx, rax
0x180015bea  jz      short loc_180015C0A
0x180015bec  test    byte ptr [rcx+1Ch], 1
0x180015bf0  jz      short loc_180015C0A
0x180015bf2  mov     edx, 6Dh ; 'm'
0x180015bf7  mov     rcx, [rcx+10h]
0x180015bfb  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180015c02  mov     r9d, ebx
0x180015c05  call    WPP_SF_d
0x180015c0a  mov     rcx, [rdi]
0x180015c0d  call    FwAuthSetFree
0x180015c12  mov     qword ptr [rdi], 0
0x180015c19  jmp     short loc_180015C37
0x180015c1b  mov     eax, [rsi+40h]
0x180015c1e  mov     rcx, [rdi]
0x180015c21  mov     [rcx+40h], eax
0x180015c24  mov     eax, [rsi+50h]
0x180015c27  mov     rcx, [rdi]
0x180015c2a  mov     [rcx+50h], eax
0x180015c2d  mov     rax, [rdi]
0x180015c30  mov     qword ptr [rax], 0
0x180015c37  mov     rsi, [rsp+28h+arg_8]
0x180015c3c  mov     eax, ebx
0x180015c3e  mov     rbx, [rsp+28h+arg_0]
0x180015c43  add     rsp, 20h
0x180015c47  pop     rdi
0x180015c48  retn
```
