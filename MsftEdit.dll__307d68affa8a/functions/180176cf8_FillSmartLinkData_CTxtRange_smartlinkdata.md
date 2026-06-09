# FillSmartLinkData(CTxtRange &,_smartlinkdata *)

- ea: `0x180176cf8`
- end: `0x180176f50`
- name: `?FillSmartLinkData@@YAJAEAVCTxtRange@@PEAU_smartlinkdata@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct CTxtRange *this, struct _smartlinkdata *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007786c`

## callees

- `0x18001c6e0`
- `0x180021150`
- `0x180021a20`
- `0x180021b88`
- `0x180078188`
- `0x180118454`
- `0x18013bad0`
- `0x180176cf8`
- `0x180177784`
- `0x1801778f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176e68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176ead`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176ef3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176e68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176ead`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176ef3`

## pseudocode

```c
__int64 __fastcall FillSmartLinkData(struct CTxtRange *this, struct _smartlinkdata *a2)
{
  char v2; // r13
  int v6; // ebx
  int v7; // r15d
  unsigned int v8; // edx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r14
  unsigned int HiddentText; // esi
  __m128i v12; // xmm1
  char v13; // r12
  int v14; // r14d
  char v15; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+34h] [rbp-3Ch] BYREF
  int v17; // [rsp+38h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  WCHAR String1[2]; // [rsp+58h] [rbp-18h] BYREF

  v2 = 0;
  if ( !a2 )
    return 2147942487LL;
  v16 = *(_DWORD *)a2;
  v17 = 0;
  *(_DWORD *)String1 = 0;
  if ( !(unsigned int)CTxtRange::GetURLInstruction(this, &v16, &v17, (int *)String1) )
    return 1;
  v6 = v17 - v16;
  v7 = *(_DWORD *)String1;
  v8 = v17 - v16;
  *((_DWORD *)a2 + 1) = *(_DWORD *)String1;
  v9 = CW32System::SysAllocStringLen(0, v8);
  *((_QWORD *)a2 + 3) = v9;
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  HiddentText = 0;
  CTxtRange::SetCp(this, v16, 0);
  v12 = (__m128i)*((unsigned __int64 *)this + 5);
  v18 = *(_OWORD *)((char *)this + 24);
  v19 = v12.m128i_i64[0];
  CTxtPtr::Move((CTxtPtr *)&v18, v16 - _mm_cvtsi128_si32(v12));
  CTxtPtr::GetText((CTxtPtr *)&v18, v6, v10);
  v15 = 0;
  v13 = 0;
  CTxtPtr::Move((CTxtPtr *)&v18, v6 - v19 + v16 + 1);
  do
  {
    v14 = v19;
    if ( (int)v19 >= v7 )
      break;
    if ( CTxtPtr::GetChar((CTxtPtr *)&v18) == 32 )
    {
      while ( v14 < v7 )
      {
        CTxtPtr::Move((CTxtPtr *)&v18, 1);
        if ( CTxtPtr::GetChar((CTxtPtr *)&v18) != 32 )
          break;
        v14 = v19;
      }
    }
    CTxtPtr::GetText((CTxtPtr *)&v18, 4, String1);
    if ( v15 || CompareStringOrdinal(String1, 3, L"-ID", 3, 1) != 2 )
    {
      if ( v2 || CompareStringOrdinal(String1, 3, L"-TY", 3, 1) != 2 )
      {
        if ( v13 || CompareStringOrdinal(String1, 4, L"-AT ", 4, 1) != 2 )
          return 1;
        v13 = 1;
        CTxtPtr::Move((CTxtPtr *)&v18, 4);
        HiddentText = GetHiddentText((struct CTxtPtr *)&v18, v7, (unsigned __int16 **)a2 + 4);
      }
      else
      {
        v2 = 1;
        CTxtPtr::Move((CTxtPtr *)&v18, 3);
        *((_DWORD *)a2 + 3) = GetCurrentWord((struct CTxtPtr *)&v18);
      }
    }
    else
    {
      v15 = 1;
      CTxtPtr::Move((CTxtPtr *)&v18, 3);
      *((_DWORD *)a2 + 4) = GetCurrentWord((struct CTxtPtr *)&v18);
    }
  }
  while ( !HiddentText );
  return HiddentText;
}

```

## disassembly

```asm
0x180176cf8  mov     [rsp-38h+arg_10], rbx
0x180176cfd  push    rbp
0x180176cfe  push    rsi
0x180176cff  push    rdi
0x180176d00  push    r12
0x180176d02  push    r13
0x180176d04  push    r14
0x180176d06  push    r15
0x180176d08  mov     rbp, rsp
0x180176d0b  sub     rsp, 70h
0x180176d0f  mov     rax, cs:__security_cookie
0x180176d16  xor     rax, rsp
0x180176d19  mov     [rbp+var_10], rax
0x180176d1d  xor     r13d, r13d
0x180176d20  mov     rdi, rdx
0x180176d23  mov     r12, rcx
0x180176d26  test    rdx, rdx
0x180176d29  jnz     short loc_180176D35
0x180176d2b  mov     eax, 80070057h
0x180176d30  jmp     loc_180176F2C
0x180176d35  mov     eax, [rdx]
0x180176d37  lea     r9, [rbp+String1]; int *
0x180176d3b  lea     rdx, [rbp+var_3C]; int *
0x180176d3f  mov     [rbp+var_3C], eax
0x180176d42  lea     r8, [rbp+var_38]; int *
0x180176d46  mov     [rbp+var_38], r13d
0x180176d4a  mov     dword ptr [rbp+String1], r13d
0x180176d4e  call    ?GetURLInstruction@CTxtRange@@QEAAHAEAJ0PEAJ@Z; CTxtRange::GetURLInstruction(long &,long &,long *)
0x180176d53  test    eax, eax
0x180176d55  jnz     short loc_180176D61
0x180176d57  mov     eax, 1
0x180176d5c  jmp     loc_180176F2C
0x180176d61  mov     ebx, [rbp+var_38]
0x180176d64  xor     ecx, ecx; unsigned __int16 *
0x180176d66  sub     ebx, [rbp+var_3C]
0x180176d69  mov     r15d, dword ptr [rbp+String1]
0x180176d6d  mov     edx, ebx; unsigned int
0x180176d6f  mov     [rdi+4], r15d
0x180176d73  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x180176d78  mov     [rdi+18h], rax
0x180176d7c  mov     r14, rax
0x180176d7f  test    rax, rax
0x180176d82  jnz     short loc_180176D8E
0x180176d84  mov     eax, 8007000Eh
0x180176d89  jmp     loc_180176F2C
0x180176d8e  mov     edx, [rbp+var_3C]; int
0x180176d91  xor     r8d, r8d; int
0x180176d94  mov     rcx, r12; this
0x180176d97  mov     esi, r13d
0x180176d9a  call    ?SetCp@CTxtRange@@QEAAJJH@Z; CTxtRange::SetCp(long,int)
0x180176d9f  movsd   xmm1, qword ptr [r12+28h]
0x180176da6  lea     rcx, [rbp+var_30]; this
0x180176daa  mov     edx, [rbp+var_3C]
0x180176dad  movups  xmm0, xmmword ptr [r12+18h]
0x180176db3  movd    eax, xmm1
0x180176db7  movups  [rbp+var_30], xmm0
0x180176dbb  sub     edx, eax; int
0x180176dbd  movsd   [rbp+var_20], xmm1
0x180176dc2  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176dc7  mov     r8, r14; unsigned __int16 *
0x180176dca  lea     rcx, [rbp+var_30]; this
0x180176dce  mov     edx, ebx; int
0x180176dd0  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x180176dd5  mov     edx, [rbp+var_3C]
0x180176dd8  lea     rcx, [rbp+var_30]; this
0x180176ddc  sub     ebx, dword ptr [rbp+var_20]
0x180176ddf  inc     edx
0x180176de1  add     edx, ebx; int
0x180176de3  mov     [rbp+var_40], r13b
0x180176de7  xor     r12b, r12b
0x180176dea  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176def  mov     ebx, 1
0x180176df4  mov     r14d, dword ptr [rbp+var_20]
0x180176df8  cmp     r14d, r15d
0x180176dfb  jge     loc_180176F2A
0x180176e01  lea     rcx, [rbp+var_30]; this
0x180176e05  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x180176e0a  cmp     ax, 20h ; ' '
0x180176e0e  jnz     short loc_180176E35
0x180176e10  cmp     r14d, r15d
0x180176e13  jge     short loc_180176E35
0x180176e15  mov     edx, ebx; int
0x180176e17  lea     rcx, [rbp+var_30]; this
0x180176e1b  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176e20  lea     rcx, [rbp+var_30]; this
0x180176e24  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x180176e29  cmp     ax, 20h ; ' '
0x180176e2d  jnz     short loc_180176E35
0x180176e2f  mov     r14d, dword ptr [rbp+var_20]
0x180176e33  jmp     short loc_180176E10
0x180176e35  lea     r8, [rbp+String1]; unsigned __int16 *
0x180176e39  mov     edx, 4; int
0x180176e3e  lea     rcx, [rbp+var_30]; this
0x180176e42  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x180176e47  cmp     [rbp+var_40], 0
0x180176e4b  mov     r14d, 3
0x180176e51  jnz     short loc_180176E93
0x180176e53  mov     r9d, r14d; cchCount2
0x180176e56  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180176e5a  lea     r8, String2; "-ID"
0x180176e61  mov     edx, r14d; cchCount1
0x180176e64  lea     rcx, [rbp+String1]; lpString1
0x180176e68  call    cs:__imp_CompareStringOrdinal
0x180176e6e  cmp     eax, 2
0x180176e71  jnz     short loc_180176E93
0x180176e73  mov     edx, r14d; int
0x180176e76  mov     [rbp+var_40], bl
0x180176e79  lea     rcx, [rbp+var_30]; this
0x180176e7d  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176e82  lea     rcx, [rbp+var_30]; this
0x180176e86  call    ?GetCurrentWord@@YAKAEAVCTxtPtr@@@Z; GetCurrentWord(CTxtPtr &)
0x180176e8b  mov     [rdi+10h], eax
0x180176e8e  jmp     loc_180176F1E
0x180176e93  test    r13b, r13b
0x180176e96  jnz     short loc_180176ED5
0x180176e98  mov     r9d, r14d; cchCount2
0x180176e9b  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180176e9f  lea     r8, aTy_0; "-TY"
0x180176ea6  mov     edx, r14d; cchCount1
0x180176ea9  lea     rcx, [rbp+String1]; lpString1
0x180176ead  call    cs:__imp_CompareStringOrdinal
0x180176eb3  cmp     eax, 2
0x180176eb6  jnz     short loc_180176ED5
0x180176eb8  mov     edx, r14d; int
0x180176ebb  lea     rcx, [rbp+var_30]; this
0x180176ebf  mov     r13b, bl
0x180176ec2  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176ec7  lea     rcx, [rbp+var_30]; this
0x180176ecb  call    ?GetCurrentWord@@YAKAEAVCTxtPtr@@@Z; GetCurrentWord(CTxtPtr &)
0x180176ed0  mov     [rdi+0Ch], eax
0x180176ed3  jmp     short loc_180176F1E
0x180176ed5  test    r12b, r12b
0x180176ed8  jnz     short loc_180176F28
0x180176eda  mov     esi, 4
0x180176edf  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180176ee3  mov     r9d, esi; cchCount2
0x180176ee6  lea     r8, aAt_0; "-AT "
0x180176eed  mov     edx, esi; cchCount1
0x180176eef  lea     rcx, [rbp+String1]; lpString1
0x180176ef3  call    cs:__imp_CompareStringOrdinal
0x180176ef9  cmp     eax, 2
0x180176efc  jnz     short loc_180176F28
0x180176efe  mov     edx, esi; int
0x180176f00  lea     rcx, [rbp+var_30]; this
0x180176f04  mov     r12b, bl
0x180176f07  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180176f0c  lea     r8, [rdi+20h]; unsigned __int16 **
0x180176f10  mov     edx, r15d; int
0x180176f13  lea     rcx, [rbp+var_30]; this
0x180176f17  call    ?GetHiddentText@@YAJAEAVCTxtPtr@@JAEAPEAG@Z; GetHiddentText(CTxtPtr &,long,ushort * &)
0x180176f1c  mov     esi, eax
0x180176f1e  test    esi, esi
0x180176f20  jz      loc_180176DF4
0x180176f26  jmp     short loc_180176F2A
0x180176f28  mov     esi, ebx
0x180176f2a  mov     eax, esi
0x180176f2c  mov     rcx, [rbp+var_10]
0x180176f30  xor     rcx, rsp; StackCookie
0x180176f33  call    __security_check_cookie
0x180176f38  mov     rbx, [rsp+70h+arg_10]
0x180176f40  add     rsp, 70h
0x180176f44  pop     r15
0x180176f46  pop     r14
0x180176f48  pop     r13
0x180176f4a  pop     r12
0x180176f4c  pop     rdi
0x180176f4d  pop     rsi
0x180176f4e  pop     rbp
0x180176f4f  retn
```
